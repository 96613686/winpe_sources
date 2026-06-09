# RegistryPath::Append(ushort const *)

- ea: `0x18002fd54`
- end: `0x18002ffdb`
- name: `?Append@RegistryPath@@QEAAKPEBG@Z`
- size: `647`
- prototype: `unsigned int __fastcall(RegistryPath *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001f540`
- `0x18003607c`
- `0x1800abae4`

## callees

- `0x18001a100`
- `0x18001ea7c`
- `0x1800215e4`
- `0x18002fd54`
- `0x18004aa08`
- `0x18004d79c`
- `0x180051974`
- `0x18005dcc0`
- `0x18005dd14`
- `0x1800ac89c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002fd97`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002fdf4`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002fd97`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002fdf4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fec8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fec8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002feba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002feba`

## string_xrefs

- `0x18002fdac`: `RegistryPath::Append`
- `0x18002fdcf`: `RegistryPath::Append`
- `0x18002fe5b`: `RegistryPath::Append`
- `0x18002fea4`: `RegistryPath::Append`
- `0x18002ff6e`: `RegistryPath::Append`
- `0x18002fda5`: `%s: subPath is longer than %d characters`
- `0x18002fe02`: `%s: Registry path is longer than %d characters`
- `0x18002fdd6`: `%s: subPath is empty. Nothing to do.`

## pseudocode

```c
__int64 __fastcall RegistryPath::Append(const wchar_t **this, const unsigned __int16 *a2)
{
  size_t v2; // rsi
  const wchar_t *v3; // r12
  unsigned int v5; // ebp
  size_t v6; // rbx
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // rdx
  _WORD *v9; // r14
  int v10; // eax
  unsigned int v11; // r13d
  wchar_t *v12; // rax
  HANDLE ProcessHeap; // rax
  char v14; // r15
  int v15; // eax
  unsigned int v16; // esi
  wchar_t *v17; // rax
  const wchar_t *v18; // rcx

  v2 = 0;
  v3 = a2;
  if ( a2 )
  {
    while ( a2[v2] == 92 )
    {
      if ( ++v2 >= 0x400 )
        goto LABEL_6;
    }
    v3 = &a2[v2];
    v2 = wcsnlen(v3, 0x400u);
LABEL_6:
    if ( v2 == 1024 )
    {
      Logger::TraceError(L"%s: subPath is longer than %d characters", L"RegistryPath::Append", 1023);
      return 87;
    }
  }
  v5 = 0;
  if ( !v2 )
  {
    Logger::TraceVerbose(L"%s: subPath is empty. Nothing to do.", L"RegistryPath::Append");
    return v5;
  }
  v6 = 0;
  if ( *this && (v6 = wcsnlen(*this, 0x400u), v6 == 1024) || (v7 = v2 + v6 + 2, v7 > 0x400) )
  {
    Logger::TraceError(L"%s: Registry path is longer than %d characters", L"RegistryPath::Append", 1023);
    return 87;
  }
  if ( v7 <= (unsigned __int64)this[1] )
  {
    v9 = *this;
  }
  else
  {
    v8 = v7 / 0x96 + 1;
    if ( 150 * v8 - v7 <= 1024 - v7 )
      v7 = 150 * v8;
    v9 = MIDL_user_allocate(2 * v7);
    if ( !v9 )
    {
      v5 = 14;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegistryPath::Append");
      return v5;
    }
    v9[v6] = 0;
    if ( v6 )
    {
      v10 = o_wcsncpy_s_0(v9, v7, *this, v6);
      v11 = v10;
      if ( v10 )
      {
        v12 = wcserror(v10);
        Logger::TraceError(L"%s: wcsncpy_s failed with errno %d (%s).", L"RegistryPath::Append", v11, v12);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
        return wcsncpy_s_error(v11);
      }
    }
    SafeFree((void *)*this);
    *this = v9;
    this[1] = (const wchar_t *)v7;
  }
  if ( v6 )
  {
    if ( v9[v6 - 1] == 92 && *v3 == 92 )
    {
      --v6;
      v14 = 0;
      v9[v6] = 0;
    }
    else
    {
      v14 = 0;
      if ( v9[v6 - 1] != 92 && *v3 != 92 )
      {
        v9[v6] = 92;
        v14 = 1;
        (*this)[++v6] = 0;
      }
    }
  }
  else
  {
    v14 = 0;
  }
  v15 = o_wcsncpy_s_0(&(*this)[v6], (char *)this[1] - v6, v3, v2 + 1);
  v16 = v15;
  if ( v15 )
  {
    v17 = wcserror(v15);
    Logger::TraceError(L"%s: wcsncpy_s failed with errno %d (%s).", L"RegistryPath::Append", v16, v17);
    v5 = wcsncpy_s_error(v16);
    if ( v14 )
      (*this)[--v6] = 0;
    if ( (unsigned __int64)this[3] > v6 )
      this[3] = (const wchar_t *)v6;
  }
  else
  {
    v18 = this[3];
    if ( (*this)[(_QWORD)v18] == 92 )
      this[3] = (const wchar_t *)((char *)v18 + 1);
    RegistryPath::CloseSubKey((RegistryPath *)this);
  }
  return v5;
}

```

## disassembly

```asm
0x18002fd54  push    rbx
0x18002fd56  push    rbp
0x18002fd57  push    rsi
0x18002fd58  push    rdi
0x18002fd59  push    r12
0x18002fd5b  push    r13
0x18002fd5d  push    r14
0x18002fd5f  push    r15
0x18002fd61  sub     rsp, 28h
0x18002fd65  xor     esi, esi
0x18002fd67  mov     r12, rdx
0x18002fd6a  mov     rdi, rcx
0x18002fd6d  mov     r14d, 400h
0x18002fd73  lea     r13d, [rsi+5Ch]
0x18002fd77  test    rdx, rdx
0x18002fd7a  jz      short loc_18002FDC8
0x18002fd7c  cmp     [rdx+rsi*2], r13w
0x18002fd81  jnz     short loc_18002FD8D
0x18002fd83  inc     rsi
0x18002fd86  cmp     rsi, r14
0x18002fd89  jb      short loc_18002FD7C
0x18002fd8b  jmp     short loc_18002FDA0
0x18002fd8d  lea     r12, [rdx+rsi*2]
0x18002fd91  mov     rdx, r14; MaxCount
0x18002fd94  mov     rcx, r12; Source
0x18002fd97  call    cs:__imp_wcsnlen
0x18002fd9d  mov     rsi, rax
0x18002fda0  cmp     rsi, r14
0x18002fda3  jnz     short loc_18002FDC8
0x18002fda5  lea     rcx, aSSubpathIsLong; "%s: subPath is longer than %d character"...
0x18002fdac  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18002fdb3  mov     r8d, 3FFh
0x18002fdb9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002fdbe  mov     ebp, 57h ; 'W'
0x18002fdc3  jmp     loc_18002FFC8
0x18002fdc8  xor     ebp, ebp
0x18002fdca  test    rsi, rsi
0x18002fdcd  jnz     short loc_18002FDE7
0x18002fdcf  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18002fdd6  lea     rcx, aSSubpathIsEmpt; "%s: subPath is empty. Nothing to do."
0x18002fddd  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002fde2  jmp     loc_18002FFC8
0x18002fde7  mov     rcx, [rdi]; Source
0x18002fdea  xor     ebx, ebx
0x18002fdec  test    rcx, rcx
0x18002fdef  jz      short loc_18002FE0B
0x18002fdf1  mov     rdx, r14; MaxCount
0x18002fdf4  call    cs:__imp_wcsnlen
0x18002fdfa  mov     rbx, rax
0x18002fdfd  cmp     rax, r14
0x18002fe00  jnz     short loc_18002FE0B
0x18002fe02  lea     rcx, aSRegistryPathI; "%s: Registry path is longer than %d cha"...
0x18002fe09  jmp     short loc_18002FDAC
0x18002fe0b  lea     r15, [rbx+2]
0x18002fe0f  add     r15, rsi
0x18002fe12  cmp     r15, r14
0x18002fe15  ja      short loc_18002FE02
0x18002fe17  cmp     r15, [rdi+8]
0x18002fe1b  jbe     loc_18002FEF4
0x18002fe21  mov     rax, 6D3A06D3A06D3A07h
0x18002fe2b  sub     r14, r15
0x18002fe2e  mul     r15
0x18002fe31  shr     rdx, 6
0x18002fe35  inc     rdx
0x18002fe38  imul    rax, rdx, 96h
0x18002fe3f  sub     rax, r15
0x18002fe42  cmp     rax, r14
0x18002fe45  ja      short loc_18002FE4A
0x18002fe47  add     r15, rax
0x18002fe4a  lea     rcx, [r15+r15]; size
0x18002fe4e  call    MIDL_user_allocate
0x18002fe53  mov     r14, rax
0x18002fe56  test    rax, rax
0x18002fe59  jnz     short loc_18002FE76
0x18002fe5b  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18002fe62  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18002fe69  lea     ebp, [rax+0Eh]
0x18002fe6c  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18002fe71  jmp     loc_18002FFC8
0x18002fe76  xor     eax, eax
0x18002fe78  mov     [r14+rbx*2], ax
0x18002fe7d  test    rbx, rbx
0x18002fe80  jz      short loc_18002FEE3
0x18002fe82  mov     r8, [rdi]
0x18002fe85  mov     r9, rbx
0x18002fe88  mov     rdx, r15
0x18002fe8b  mov     rcx, r14
0x18002fe8e  call    _o_wcsncpy_s_0
0x18002fe93  mov     r13d, eax
0x18002fe96  test    eax, eax
0x18002fe98  jz      short loc_18002FEDD
0x18002fe9a  mov     ecx, eax; ErrorNumber
0x18002fe9c  call    _wcserror
0x18002fea1  mov     r9, rax
0x18002fea4  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18002feab  mov     r8d, r13d
0x18002feae  lea     rcx, aSWcsncpySFaile; "%s: wcsncpy_s failed with errno %d (%s)"...
0x18002feb5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002feba  call    cs:__imp_GetProcessHeap
0x18002fec0  mov     r8, r14; lpMem
0x18002fec3  xor     edx, edx; dwFlags
0x18002fec5  mov     rcx, rax; hHeap
0x18002fec8  call    cs:__imp_HeapFree
0x18002fece  mov     ecx, r13d; int
0x18002fed1  call    ?wcsncpy_s_error@@YAKH@Z; wcsncpy_s_error(int)
0x18002fed6  mov     ebp, eax
0x18002fed8  jmp     loc_18002FFC8
0x18002fedd  mov     r13d, 5Ch ; '\'
0x18002fee3  mov     rcx, [rdi]; void *
0x18002fee6  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002feeb  mov     [rdi], r14
0x18002feee  mov     [rdi+8], r15
0x18002fef2  jmp     short loc_18002FEF7
0x18002fef4  mov     r14, [rdi]
0x18002fef7  test    rbx, rbx
0x18002fefa  jz      short loc_18002FF41
0x18002fefc  cmp     [r14+rbx*2-2], r13w
0x18002ff02  setz    al
0x18002ff05  jnz     short loc_18002FF1D
0x18002ff07  cmp     [r12], r13w
0x18002ff0c  jnz     short loc_18002FF1D
0x18002ff0e  dec     rbx
0x18002ff11  xor     r15b, r15b
0x18002ff14  xor     eax, eax
0x18002ff16  mov     [r14+rbx*2], ax
0x18002ff1b  jmp     short loc_18002FF44
0x18002ff1d  xor     r15b, r15b
0x18002ff20  test    al, al
0x18002ff22  jnz     short loc_18002FF44
0x18002ff24  cmp     [r12], r13w
0x18002ff29  jz      short loc_18002FF44
0x18002ff2b  mov     [r14+rbx*2], r13w
0x18002ff30  mov     r15b, 1
0x18002ff33  mov     rcx, [rdi]
0x18002ff36  inc     rbx
0x18002ff39  xor     eax, eax
0x18002ff3b  mov     [rcx+rbx*2], ax
0x18002ff3f  jmp     short loc_18002FF44
0x18002ff41  xor     r15b, r15b
0x18002ff44  mov     rax, [rdi]
0x18002ff47  lea     r9, [rsi+1]
0x18002ff4b  mov     rdx, [rdi+8]
0x18002ff4f  mov     r8, r12
0x18002ff52  sub     rdx, rbx
0x18002ff55  lea     rcx, [rax+rbx*2]
0x18002ff59  call    _o_wcsncpy_s_0
0x18002ff5e  mov     esi, eax
0x18002ff60  test    eax, eax
0x18002ff62  jz      short loc_18002FFAA
0x18002ff64  mov     ecx, eax; ErrorNumber
0x18002ff66  call    _wcserror
0x18002ff6b  mov     r9, rax
0x18002ff6e  lea     rdx, aRegistrypathAp; "RegistryPath::Append"
0x18002ff75  mov     r8d, esi
0x18002ff78  lea     rcx, aSWcsncpySFaile; "%s: wcsncpy_s failed with errno %d (%s)"...
0x18002ff7f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002ff84  mov     ecx, esi; int
0x18002ff86  call    ?wcsncpy_s_error@@YAKH@Z; wcsncpy_s_error(int)
0x18002ff8b  mov     ebp, eax
0x18002ff8d  test    r15b, r15b
0x18002ff90  jz      short loc_18002FF9E
0x18002ff92  mov     rcx, [rdi]
0x18002ff95  dec     rbx
0x18002ff98  xor     eax, eax
0x18002ff9a  mov     [rcx+rbx*2], ax
0x18002ff9e  cmp     [rdi+18h], rbx
0x18002ffa2  jbe     short loc_18002FFC8
0x18002ffa4  mov     [rdi+18h], rbx
0x18002ffa8  jmp     short loc_18002FFC8
0x18002ffaa  mov     rcx, [rdi+18h]
0x18002ffae  mov     rax, [rdi]
0x18002ffb1  cmp     [rax+rcx*2], r13w
0x18002ffb6  jnz     short loc_18002FFC0
0x18002ffb8  lea     rax, [rcx+1]
0x18002ffbc  mov     [rdi+18h], rax
0x18002ffc0  mov     rcx, rdi; this
0x18002ffc3  call    ?CloseSubKey@RegistryPath@@QEAAXXZ; RegistryPath::CloseSubKey(void)
0x18002ffc8  mov     eax, ebp
0x18002ffca  add     rsp, 28h
0x18002ffce  pop     r15
0x18002ffd0  pop     r14
0x18002ffd2  pop     r13
0x18002ffd4  pop     r12
0x18002ffd6  pop     rdi
0x18002ffd7  pop     rsi
0x18002ffd8  pop     rbp
0x18002ffd9  pop     rbx
0x18002ffda  retn
```
