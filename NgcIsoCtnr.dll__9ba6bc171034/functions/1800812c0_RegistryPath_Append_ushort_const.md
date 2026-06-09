# RegistryPath::Append(ushort const *)

- ea: `0x1800812c0`
- end: `0x18008153d`
- name: `?Append@RegistryPath@@QEAAKPEBG@Z`
- size: `637`
- prototype: `unsigned int __fastcall(RegistryPath *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18007d7ac`
- `0x18007ddc4`
- `0x18008168c`

## callees

- `0x180008444`
- `0x180008498`
- `0x18006b2c0`
- `0x180079de0`
- `0x18007d17c`
- `0x18007d1b8`
- `0x18007d22c`
- `0x1800812c0`
- `0x180081544`
- `0x180081fa0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180081305`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180081362`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180081305`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180081362`

## string_xrefs

- `0x18008131a`: `RegistryPath::Append`
- `0x18008133d`: `RegistryPath::Append`
- `0x1800813c9`: `RegistryPath::Append`
- `0x180081411`: `RegistryPath::Append`
- `0x1800814c6`: `RegistryPath::Append`
- `0x180081344`: `%s: subPath is empty. Nothing to do.`
- `0x180081370`: `%s: Registry path is longer than %d characters`
- `0x180081313`: `%s: subPath is longer than %d characters`

## pseudocode

```c
__int64 __fastcall RegistryPath::Append(const wchar_t **this, const unsigned __int16 *a2)
{
  wchar_t *v2; // rsi
  size_t v3; // r14
  const wchar_t *v4; // r13
  unsigned int v6; // ebp
  size_t v7; // rbx
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // r12d
  wchar_t *v12; // rax
  char v13; // r15
  int v14; // eax
  unsigned int v15; // esi
  wchar_t *v16; // rax
  const wchar_t *v17; // rcx

  v2 = 0;
  v3 = 0;
  v4 = a2;
  if ( a2 )
  {
    while ( a2[v3] == 92 )
    {
      if ( ++v3 >= 0x400 )
        goto LABEL_6;
    }
    v4 = &a2[v3];
    v3 = wcsnlen(v4, 0x400u);
LABEL_6:
    if ( v3 == 1024 )
    {
      Logger::TraceError(L"%s: subPath is longer than %d characters", L"RegistryPath::Append", 1023);
LABEL_8:
      v6 = 87;
      goto LABEL_42;
    }
  }
  v6 = 0;
  if ( !v3 )
  {
    Logger::TraceVerbose(L"%s: subPath is empty. Nothing to do.", L"RegistryPath::Append");
    goto LABEL_42;
  }
  v7 = 0;
  if ( *this && (v7 = wcsnlen(*this, 0x400u), v7 == 1024) || (v8 = v3 + v7 + 2, v8 > 0x400) )
  {
    Logger::TraceError(L"%s: Registry path is longer than %d characters", L"RegistryPath::Append", 1023);
    goto LABEL_8;
  }
  if ( v8 <= (unsigned __int64)this[1] )
  {
    v2 = (wchar_t *)*this;
  }
  else
  {
    v9 = v8 / 0x96 + 1;
    if ( 150 * v9 - v8 <= 1024 - v8 )
      v8 = 150 * v9;
    v2 = (wchar_t *)MIDL_user_allocate(2 * v8);
    if ( !v2 )
    {
      v6 = 14;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegistryPath::Append");
      goto LABEL_42;
    }
    v2[v7] = 0;
    if ( v7 )
    {
      v10 = o_wcsncpy_s_0(v2, v8, *this, v7);
      v11 = v10;
      if ( v10 )
      {
        v12 = wcserror(v10);
        Logger::TraceError(L"%s: wcsncpy_s failed with errno %d (%s).", L"RegistryPath::Append", v11, v12);
        v6 = wcsncpy_s_error(v11);
        goto LABEL_42;
      }
    }
    SafeFree((void *)*this);
    *this = v2;
    this[1] = (const wchar_t *)v8;
  }
  if ( v7 )
  {
    if ( v2[v7 - 1] == 92 && *v4 == 92 )
    {
      --v7;
      v13 = 0;
      v2[v7] = 0;
    }
    else
    {
      v13 = 0;
      if ( v2[v7 - 1] != 92 && *v4 != 92 )
      {
        v2[v7] = 92;
        v13 = 1;
        (*this)[++v7] = 0;
      }
    }
  }
  else
  {
    v13 = 0;
  }
  v14 = o_wcsncpy_s_0(&(*this)[v7], (char *)this[1] - v7, v4, v3 + 1);
  v15 = v14;
  if ( v14 )
  {
    v16 = wcserror(v14);
    Logger::TraceError(L"%s: wcsncpy_s failed with errno %d (%s).", L"RegistryPath::Append", v15, v16);
    v6 = wcsncpy_s_error(v15);
    if ( v13 )
      (*this)[--v7] = 0;
    if ( (unsigned __int64)this[3] > v7 )
      this[3] = (const wchar_t *)v7;
  }
  else
  {
    v17 = this[3];
    if ( (*this)[(_QWORD)v17] == 92 )
      this[3] = (const wchar_t *)((char *)v17 + 1);
    RegistryPath::CloseSubKey((RegistryPath *)this);
  }
  v2 = 0;
LABEL_42:
  SafeFree(v2);
  return v6;
}

```

## disassembly

```asm
0x1800812c0  push    rbx
0x1800812c2  push    rbp
0x1800812c3  push    rsi
0x1800812c4  push    rdi
0x1800812c5  push    r12
0x1800812c7  push    r13
0x1800812c9  push    r14
0x1800812cb  push    r15
0x1800812cd  sub     rsp, 28h
0x1800812d1  xor     esi, esi
0x1800812d3  xor     r14d, r14d
0x1800812d6  mov     r13, rdx
0x1800812d9  mov     rdi, rcx
0x1800812dc  mov     r12d, 400h
0x1800812e2  lea     eax, [rsi+5Ch]
0x1800812e5  test    rdx, rdx
0x1800812e8  jz      short loc_180081336
0x1800812ea  cmp     [rdx+r14*2], ax
0x1800812ef  jnz     short loc_1800812FB
0x1800812f1  inc     r14
0x1800812f4  cmp     r14, r12
0x1800812f7  jb      short loc_1800812EA
0x1800812f9  jmp     short loc_18008130E
0x1800812fb  lea     r13, [rdx+r14*2]
0x1800812ff  mov     rdx, r12; MaxCount
0x180081302  mov     rcx, r13; Source
0x180081305  call    cs:__imp_wcsnlen
0x18008130b  mov     r14, rax
0x18008130e  cmp     r14, r12
0x180081311  jnz     short loc_180081336
0x180081313  lea     rcx, aSSubpathIsLong; "%s: subPath is longer than %d character"...
0x18008131a  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x180081321  mov     r8d, 3FFh
0x180081327  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008132c  mov     ebp, 57h ; 'W'
0x180081331  jmp     loc_180081522
0x180081336  xor     ebp, ebp
0x180081338  test    r14, r14
0x18008133b  jnz     short loc_180081355
0x18008133d  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x180081344  lea     rcx, aSSubpathIsEmpt; "%s: subPath is empty. Nothing to do."
0x18008134b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180081350  jmp     loc_180081522
0x180081355  mov     rcx, [rdi]; Source
0x180081358  xor     ebx, ebx
0x18008135a  test    rcx, rcx
0x18008135d  jz      short loc_180081379
0x18008135f  mov     rdx, r12; MaxCount
0x180081362  call    cs:__imp_wcsnlen
0x180081368  mov     rbx, rax
0x18008136b  cmp     rax, r12
0x18008136e  jnz     short loc_180081379
0x180081370  lea     rcx, aSRegistryPathI; "%s: Registry path is longer than %d cha"...
0x180081377  jmp     short loc_18008131A
0x180081379  lea     r15, [rbx+2]
0x18008137d  add     r15, r14
0x180081380  cmp     r15, r12
0x180081383  ja      short loc_180081370
0x180081385  cmp     r15, [rdi+8]
0x180081389  jbe     loc_180081447
0x18008138f  mov     rax, 6D3A06D3A06D3A07h
0x180081399  sub     r12, r15
0x18008139c  mul     r15
0x18008139f  shr     rdx, 6
0x1800813a3  inc     rdx
0x1800813a6  imul    rax, rdx, 96h
0x1800813ad  sub     rax, r15
0x1800813b0  cmp     rax, r12
0x1800813b3  ja      short loc_1800813B8
0x1800813b5  add     r15, rax
0x1800813b8  lea     rcx, [r15+r15]; size
0x1800813bc  call    MIDL_user_allocate
0x1800813c1  mov     rsi, rax
0x1800813c4  test    rax, rax
0x1800813c7  jnz     short loc_1800813E4
0x1800813c9  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x1800813d0  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x1800813d7  lea     ebp, [rax+0Eh]
0x1800813da  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800813df  jmp     loc_180081522
0x1800813e4  xor     eax, eax
0x1800813e6  mov     [rsi+rbx*2], ax
0x1800813ea  test    rbx, rbx
0x1800813ed  jz      short loc_180081436
0x1800813ef  mov     r8, [rdi]
0x1800813f2  mov     r9, rbx
0x1800813f5  mov     rdx, r15
0x1800813f8  mov     rcx, rsi
0x1800813fb  call    _o_wcsncpy_s_0
0x180081400  mov     r12d, eax
0x180081403  test    eax, eax
0x180081405  jz      short loc_180081436
0x180081407  mov     ecx, eax; ErrorNumber
0x180081409  call    _wcserror
0x18008140e  mov     r9, rax
0x180081411  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x180081418  mov     r8d, r12d
0x18008141b  lea     rcx, aSWcsncpySFaile; "%s: wcsncpy_s failed with errno %d (%s)"...
0x180081422  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081427  mov     ecx, r12d; int
0x18008142a  call    ?wcsncpy_s_error@@YAKH@Z; wcsncpy_s_error(int)
0x18008142f  mov     ebp, eax
0x180081431  jmp     loc_180081522
0x180081436  mov     rcx, [rdi]; void *
0x180081439  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008143e  mov     [rdi], rsi
0x180081441  mov     [rdi+8], r15
0x180081445  jmp     short loc_18008144A
0x180081447  mov     rsi, [rdi]
0x18008144a  mov     r12d, 5Ch ; '\'
0x180081450  test    rbx, rbx
0x180081453  jz      short loc_180081499
0x180081455  cmp     [rsi+rbx*2-2], r12w
0x18008145b  setz    al
0x18008145e  jnz     short loc_180081475
0x180081460  cmp     [r13+0], r12w
0x180081465  jnz     short loc_180081475
0x180081467  dec     rbx
0x18008146a  xor     r15b, r15b
0x18008146d  xor     eax, eax
0x18008146f  mov     [rsi+rbx*2], ax
0x180081473  jmp     short loc_18008149C
0x180081475  xor     r15b, r15b
0x180081478  test    al, al
0x18008147a  jnz     short loc_18008149C
0x18008147c  cmp     [r13+0], r12w
0x180081481  jz      short loc_18008149C
0x180081483  mov     [rsi+rbx*2], r12w
0x180081488  mov     r15b, 1
0x18008148b  mov     rcx, [rdi]
0x18008148e  inc     rbx
0x180081491  xor     eax, eax
0x180081493  mov     [rcx+rbx*2], ax
0x180081497  jmp     short loc_18008149C
0x180081499  xor     r15b, r15b
0x18008149c  mov     rax, [rdi]
0x18008149f  lea     r9, [r14+1]
0x1800814a3  mov     rdx, [rdi+8]
0x1800814a7  mov     r8, r13
0x1800814aa  sub     rdx, rbx
0x1800814ad  lea     rcx, [rax+rbx*2]
0x1800814b1  call    _o_wcsncpy_s_0
0x1800814b6  mov     esi, eax
0x1800814b8  test    eax, eax
0x1800814ba  jz      short loc_180081502
0x1800814bc  mov     ecx, eax; ErrorNumber
0x1800814be  call    _wcserror
0x1800814c3  mov     r9, rax
0x1800814c6  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x1800814cd  mov     r8d, esi
0x1800814d0  lea     rcx, aSWcsncpySFaile; "%s: wcsncpy_s failed with errno %d (%s)"...
0x1800814d7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800814dc  mov     ecx, esi; int
0x1800814de  call    ?wcsncpy_s_error@@YAKH@Z; wcsncpy_s_error(int)
0x1800814e3  mov     ebp, eax
0x1800814e5  test    r15b, r15b
0x1800814e8  jz      short loc_1800814F6
0x1800814ea  mov     rcx, [rdi]
0x1800814ed  dec     rbx
0x1800814f0  xor     eax, eax
0x1800814f2  mov     [rcx+rbx*2], ax
0x1800814f6  cmp     [rdi+18h], rbx
0x1800814fa  jbe     short loc_180081520
0x1800814fc  mov     [rdi+18h], rbx
0x180081500  jmp     short loc_180081520
0x180081502  mov     rcx, [rdi+18h]
0x180081506  mov     rax, [rdi]
0x180081509  cmp     [rax+rcx*2], r12w
0x18008150e  jnz     short loc_180081518
0x180081510  lea     rax, [rcx+1]
0x180081514  mov     [rdi+18h], rax
0x180081518  mov     rcx, rdi; this
0x18008151b  call    ?CloseSubKey@RegistryPath@@QEAAXXZ; RegistryPath::CloseSubKey(void)
0x180081520  xor     esi, esi
0x180081522  mov     rcx, rsi; void *
0x180081525  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008152a  mov     eax, ebp
0x18008152c  add     rsp, 28h
0x180081530  pop     r15
0x180081532  pop     r14
0x180081534  pop     r13
0x180081536  pop     r12
0x180081538  pop     rdi
0x180081539  pop     rsi
0x18008153a  pop     rbp
0x18008153b  pop     rbx
0x18008153c  retn
```
