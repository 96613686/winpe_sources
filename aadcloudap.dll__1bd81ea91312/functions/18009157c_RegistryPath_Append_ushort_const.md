# RegistryPath::Append(ushort const *)

- ea: `0x18009157c`
- end: `0x1800917f9`
- name: `?Append@RegistryPath@@QEAAKPEBG@Z`
- size: `637`
- prototype: `__int64 __fastcall(const wchar_t **this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18008c6fc`
- `0x18008cde4`
- `0x180091c18`

## callees

- `0x180004964`
- `0x1800049f4`
- `0x180087188`
- `0x1800871b4`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18009157c`
- `0x180091800`
- `0x18009277c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800915c1`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18009161e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800915c1`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18009161e`

## string_xrefs

- `0x1800915d6`: `RegistryPath::Append`
- `0x1800915f9`: `RegistryPath::Append`
- `0x180091685`: `RegistryPath::Append`
- `0x1800916cd`: `RegistryPath::Append`
- `0x180091782`: `RegistryPath::Append`
- `0x1800915cf`: `%s: subPath is longer than %d characters`
- `0x180091600`: `%s: subPath is empty. Nothing to do.`
- `0x18009162c`: `%s: Registry path is longer than %d characters`

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
    v2 = (wchar_t *)SafeAlloc(2 * v8);
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
0x18009157c  push    rbx
0x18009157e  push    rbp
0x18009157f  push    rsi
0x180091580  push    rdi
0x180091581  push    r12
0x180091583  push    r13
0x180091585  push    r14
0x180091587  push    r15
0x180091589  sub     rsp, 28h
0x18009158d  xor     esi, esi
0x18009158f  xor     r14d, r14d
0x180091592  mov     r13, rdx
0x180091595  mov     rdi, rcx
0x180091598  mov     r12d, 400h
0x18009159e  lea     eax, [rsi+5Ch]
0x1800915a1  test    rdx, rdx
0x1800915a4  jz      short loc_1800915F2
0x1800915a6  cmp     [rdx+r14*2], ax
0x1800915ab  jnz     short loc_1800915B7
0x1800915ad  inc     r14
0x1800915b0  cmp     r14, r12
0x1800915b3  jb      short loc_1800915A6
0x1800915b5  jmp     short loc_1800915CA
0x1800915b7  lea     r13, [rdx+r14*2]
0x1800915bb  mov     rdx, r12; MaxCount
0x1800915be  mov     rcx, r13; Source
0x1800915c1  call    cs:__imp_wcsnlen
0x1800915c7  mov     r14, rax
0x1800915ca  cmp     r14, r12
0x1800915cd  jnz     short loc_1800915F2
0x1800915cf  lea     rcx, aSSubpathIsLong; "%s: subPath is longer than %d character"...
0x1800915d6  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x1800915dd  mov     r8d, 3FFh
0x1800915e3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800915e8  mov     ebp, 57h ; 'W'
0x1800915ed  jmp     loc_1800917DE
0x1800915f2  xor     ebp, ebp
0x1800915f4  test    r14, r14
0x1800915f7  jnz     short loc_180091611
0x1800915f9  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x180091600  lea     rcx, aSSubpathIsEmpt; "%s: subPath is empty. Nothing to do."
0x180091607  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009160c  jmp     loc_1800917DE
0x180091611  mov     rcx, [rdi]; Source
0x180091614  xor     ebx, ebx
0x180091616  test    rcx, rcx
0x180091619  jz      short loc_180091635
0x18009161b  mov     rdx, r12; MaxCount
0x18009161e  call    cs:__imp_wcsnlen
0x180091624  mov     rbx, rax
0x180091627  cmp     rax, r12
0x18009162a  jnz     short loc_180091635
0x18009162c  lea     rcx, aSRegistryPathI; "%s: Registry path is longer than %d cha"...
0x180091633  jmp     short loc_1800915D6
0x180091635  lea     r15, [rbx+2]
0x180091639  add     r15, r14
0x18009163c  cmp     r15, r12
0x18009163f  ja      short loc_18009162C
0x180091641  cmp     r15, [rdi+8]
0x180091645  jbe     loc_180091703
0x18009164b  mov     rax, 6D3A06D3A06D3A07h
0x180091655  sub     r12, r15
0x180091658  mul     r15
0x18009165b  shr     rdx, 6
0x18009165f  inc     rdx
0x180091662  imul    rax, rdx, 96h
0x180091669  sub     rax, r15
0x18009166c  cmp     rax, r12
0x18009166f  ja      short loc_180091674
0x180091671  add     r15, rax
0x180091674  lea     rcx, [r15+r15]; unsigned __int64
0x180091678  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18009167d  mov     rsi, rax
0x180091680  test    rax, rax
0x180091683  jnz     short loc_1800916A0
0x180091685  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18009168c  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180091693  lea     ebp, [rax+0Eh]
0x180091696  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18009169b  jmp     loc_1800917DE
0x1800916a0  xor     eax, eax
0x1800916a2  mov     [rsi+rbx*2], ax
0x1800916a6  test    rbx, rbx
0x1800916a9  jz      short loc_1800916F2
0x1800916ab  mov     r8, [rdi]
0x1800916ae  mov     r9, rbx
0x1800916b1  mov     rdx, r15
0x1800916b4  mov     rcx, rsi
0x1800916b7  call    _o_wcsncpy_s_0
0x1800916bc  mov     r12d, eax
0x1800916bf  test    eax, eax
0x1800916c1  jz      short loc_1800916F2
0x1800916c3  mov     ecx, eax; ErrorNumber
0x1800916c5  call    _wcserror
0x1800916ca  mov     r9, rax
0x1800916cd  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x1800916d4  mov     r8d, r12d
0x1800916d7  lea     rcx, aSWcsncpySFaile; "%s: wcsncpy_s failed with errno %d (%s)"...
0x1800916de  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800916e3  mov     ecx, r12d; int
0x1800916e6  call    ?wcsncpy_s_error@@YAKH@Z; wcsncpy_s_error(int)
0x1800916eb  mov     ebp, eax
0x1800916ed  jmp     loc_1800917DE
0x1800916f2  mov     rcx, [rdi]; void *
0x1800916f5  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800916fa  mov     [rdi], rsi
0x1800916fd  mov     [rdi+8], r15
0x180091701  jmp     short loc_180091706
0x180091703  mov     rsi, [rdi]
0x180091706  mov     r12d, 5Ch ; '\'
0x18009170c  test    rbx, rbx
0x18009170f  jz      short loc_180091755
0x180091711  cmp     [rsi+rbx*2-2], r12w
0x180091717  setz    al
0x18009171a  jnz     short loc_180091731
0x18009171c  cmp     [r13+0], r12w
0x180091721  jnz     short loc_180091731
0x180091723  dec     rbx
0x180091726  xor     r15b, r15b
0x180091729  xor     eax, eax
0x18009172b  mov     [rsi+rbx*2], ax
0x18009172f  jmp     short loc_180091758
0x180091731  xor     r15b, r15b
0x180091734  test    al, al
0x180091736  jnz     short loc_180091758
0x180091738  cmp     [r13+0], r12w
0x18009173d  jz      short loc_180091758
0x18009173f  mov     [rsi+rbx*2], r12w
0x180091744  mov     r15b, 1
0x180091747  mov     rcx, [rdi]
0x18009174a  inc     rbx
0x18009174d  xor     eax, eax
0x18009174f  mov     [rcx+rbx*2], ax
0x180091753  jmp     short loc_180091758
0x180091755  xor     r15b, r15b
0x180091758  mov     rax, [rdi]
0x18009175b  lea     r9, [r14+1]
0x18009175f  mov     rdx, [rdi+8]
0x180091763  mov     r8, r13
0x180091766  sub     rdx, rbx
0x180091769  lea     rcx, [rax+rbx*2]
0x18009176d  call    _o_wcsncpy_s_0
0x180091772  mov     esi, eax
0x180091774  test    eax, eax
0x180091776  jz      short loc_1800917BE
0x180091778  mov     ecx, eax; ErrorNumber
0x18009177a  call    _wcserror
0x18009177f  mov     r9, rax
0x180091782  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x180091789  mov     r8d, esi
0x18009178c  lea     rcx, aSWcsncpySFaile; "%s: wcsncpy_s failed with errno %d (%s)"...
0x180091793  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180091798  mov     ecx, esi; int
0x18009179a  call    ?wcsncpy_s_error@@YAKH@Z; wcsncpy_s_error(int)
0x18009179f  mov     ebp, eax
0x1800917a1  test    r15b, r15b
0x1800917a4  jz      short loc_1800917B2
0x1800917a6  mov     rcx, [rdi]
0x1800917a9  dec     rbx
0x1800917ac  xor     eax, eax
0x1800917ae  mov     [rcx+rbx*2], ax
0x1800917b2  cmp     [rdi+18h], rbx
0x1800917b6  jbe     short loc_1800917DC
0x1800917b8  mov     [rdi+18h], rbx
0x1800917bc  jmp     short loc_1800917DC
0x1800917be  mov     rcx, [rdi+18h]
0x1800917c2  mov     rax, [rdi]
0x1800917c5  cmp     [rax+rcx*2], r12w
0x1800917ca  jnz     short loc_1800917D4
0x1800917cc  lea     rax, [rcx+1]
0x1800917d0  mov     [rdi+18h], rax
0x1800917d4  mov     rcx, rdi; this
0x1800917d7  call    ?CloseSubKey@RegistryPath@@QEAAXXZ; RegistryPath::CloseSubKey(void)
0x1800917dc  xor     esi, esi
0x1800917de  mov     rcx, rsi; void *
0x1800917e1  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800917e6  mov     eax, ebp
0x1800917e8  add     rsp, 28h
0x1800917ec  pop     r15
0x1800917ee  pop     r14
0x1800917f0  pop     r13
0x1800917f2  pop     r12
0x1800917f4  pop     rdi
0x1800917f5  pop     rsi
0x1800917f6  pop     rbp
0x1800917f7  pop     rbx
0x1800917f8  retn
```
