# SdbpGetPathAppraiser

- ea: `0x14002d480`
- end: `0x14002d5af`
- name: `SdbpGetPathAppraiser`
- size: `303`
- prototype: `__int64 __fastcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x1400079f0`
- `0x14002d480`
- `0x14002d830`
- `0x140032adc`
- `0x14003e364`
- `0x140040a5c`

## string_xrefs

- `0x14002d522`: `AslPathCombine failed [%x]`
- `0x14002d52f`: `SdbpGetPathAppraiser`

## pseudocode

```c
__int64 __fastcall SdbpGetPathAppraiser(NTSTRSAFE_PWSTR pszDest, size_t cchDest, const wchar_t *a3, __int64 a4)
{
  const wchar_t *v5; // r10
  int ProcessHostGuestArchitectures; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 v12; // r8
  _WORD v13[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v14; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t pszSrc[12]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t pszDesta[264]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = a3;
  wcscpy(pszSrc, L"\\appraser");
  if ( cchDest < 0xB )
    return 3221225507LL;
  *pszDest = 0;
  pszDesta[0] = 0;
  v14 = -1;
  v13[0] = -1;
  if ( !a3 )
    v5 = &::pszSrc;
  ProcessHostGuestArchitectures = AslPathCombine(pszSrc, v5, pszDesta, 0x104u);
  v10 = ProcessHostGuestArchitectures;
  if ( ProcessHostGuestArchitectures >= 0 )
  {
    ProcessHostGuestArchitectures = SdbpGetProcessHostGuestArchitectures(&v14, v13, a4);
    v10 = ProcessHostGuestArchitectures;
    if ( ProcessHostGuestArchitectures >= 0 )
      return (unsigned int)AslEnvGetSysNativeDirPathForGuestBuf(pszDest, cchDest, pszDesta, v14, v13);
    v11 = "SdbpGetProcessHostGuestArchitectures failed [%x]";
    v12 = 1309;
  }
  else
  {
    v11 = "AslPathCombine failed [%x]";
    v12 = 1303;
  }
  AslLogCallPrintf(1, "SdbpGetPathAppraiser", v12, v11, ProcessHostGuestArchitectures);
  return v10;
}

```

## disassembly

```asm
0x14002d480  push    rbp
0x14002d482  push    rbx
0x14002d483  push    rsi
0x14002d484  push    rdi
0x14002d485  push    r14
0x14002d487  lea     rbp, [rsp-170h]
0x14002d48f  sub     rsp, 270h
0x14002d496  mov     rax, cs:__security_cookie
0x14002d49d  xor     rax, rsp
0x14002d4a0  mov     [rbp+190h+var_30], rax
0x14002d4a7  movsd   xmm1, qword ptr cs:aAppraiser+0Eh; "ser"
0x14002d4af  mov     r14, r9
0x14002d4b2  mov     r10, r8
0x14002d4b5  mov     rdi, rdx
0x14002d4b8  mov     rsi, rcx
0x14002d4bb  movups  xmm0, xmmword ptr cs:aAppraiser; "\\appraiser"
0x14002d4c2  movups  xmmword ptr [rsp+290h+pszSrc], xmm0
0x14002d4c7  movsd   qword ptr [rsp+290h+pszSrc+0Eh], xmm1
0x14002d4cd  cmp     rdx, 0Bh
0x14002d4d1  jnb     short loc_14002D4DD
0x14002d4d3  mov     eax, 0C0000023h
0x14002d4d8  jmp     loc_14002D591
0x14002d4dd  xor     eax, eax
0x14002d4df  lea     r8, [rsp+290h+pszDest]; pszDest
0x14002d4e4  mov     [rcx], ax
0x14002d4e7  test    r10, r10
0x14002d4ea  mov     [rsp+290h+pszDest], ax
0x14002d4ef  lea     rcx, [rsp+290h+pszSrc]; pszSrc
0x14002d4f4  mov     eax, 0FFFFh
0x14002d4f9  mov     r9d, 104h; cchDest
0x14002d4ff  mov     word ptr [rsp+290h+var_260+4], ax
0x14002d504  mov     word ptr [rsp+290h+var_260], ax
0x14002d509  lea     rax, pszSrc
0x14002d510  cmovz   r10, rax
0x14002d514  mov     rdx, r10; NTSTRSAFE_PCWSTR
0x14002d517  call    AslPathCombine
0x14002d51c  mov     ebx, eax
0x14002d51e  test    eax, eax
0x14002d520  jns     short loc_14002D546
0x14002d522  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x14002d529  mov     r8d, 517h
0x14002d52f  lea     rdx, aSdbpgetpathapp_1; "SdbpGetPathAppraiser"
0x14002d536  mov     dword ptr [rsp+290h+var_270], eax
0x14002d53a  mov     ecx, 1
0x14002d53f  call    AslLogCallPrintf
0x14002d544  jmp     short loc_14002D58F
0x14002d546  mov     r8, r14
0x14002d549  lea     rdx, [rsp+290h+var_260]
0x14002d54e  lea     rcx, [rsp+290h+var_260+4]
0x14002d553  call    SdbpGetProcessHostGuestArchitectures
0x14002d558  mov     ebx, eax
0x14002d55a  test    eax, eax
0x14002d55c  jns     short loc_14002D56D
0x14002d55e  lea     r9, aSdbpgetprocess; "SdbpGetProcessHostGuestArchitectures fa"...
0x14002d565  mov     r8d, 51Dh
0x14002d56b  jmp     short loc_14002D52F
0x14002d56d  movzx   r9d, word ptr [rsp+290h+var_260+4]
0x14002d573  lea     rax, [rsp+290h+var_260]
0x14002d578  lea     r8, [rsp+290h+pszDest]; NTSTRSAFE_PCWSTR
0x14002d57d  mov     [rsp+290h+var_270], rax; __int64
0x14002d582  mov     rdx, rdi; cchDest
0x14002d585  mov     rcx, rsi; pszDest
0x14002d588  call    AslEnvGetSysNativeDirPathForGuestBuf
0x14002d58d  mov     ebx, eax
0x14002d58f  mov     eax, ebx
0x14002d591  mov     rcx, [rbp+190h+var_30]
0x14002d598  xor     rcx, rsp; StackCookie
0x14002d59b  call    __security_check_cookie
0x14002d5a0  add     rsp, 270h
0x14002d5a7  pop     r14
0x14002d5a9  pop     rdi
0x14002d5aa  pop     rsi
0x14002d5ab  pop     rbx
0x14002d5ac  pop     rbp
0x14002d5ad  retn
```
