# ReadDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *,ulong &)

- ea: `0x1800298c8`
- end: `0x180029a6a`
- name: `?ReadDwordFromInfFile@@YA_NAEAVInfFile@@PEB_W11AEAK@Z`
- size: `418`
- prototype: `char __fastcall(void **, const wchar_t *, const wchar_t *, const wchar_t *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180020d28`
- `0x180022370`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008c78`
- `0x1800298c8`
- `0x180029a70`
- `0x180029b84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002993c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002993c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299e7`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupFindFirstLineW` at `0x18002991e`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupFindFirstLineW` at `0x18002991e`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupGetLineTextW` at `0x1800299cc`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupGetLineTextW` at `0x1800299cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ReadDwordFromInfFile(
        void **a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        unsigned int *a5)
{
  void *v5; // rcx
  int v8; // r14d
  DWORD LastError; // eax
  int v11; // r8d
  signed int v12; // ebx
  DWORD v13; // eax
  int v14; // r8d
  signed int v15; // ebx
  DWORD RequiredSize; // [rsp+40h] [rbp-C0h] BYREF
  _INFCONTEXT Context; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pExceptionObject[256]; // [rsp+60h] [rbp-A0h] BYREF

  v5 = *a1;
  v8 = (int)a2;
  memset(&Context, 0, sizeof(Context));
  if ( !SetupFindFirstLineW(v5, a3, a4, &Context) )
  {
    if ( GetLastError() == -536870654 )
      return 0;
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v11, v8, (__int64)a3, (__int64)a4, LastError);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v12);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  RequiredSize = 256;
  if ( !SetupGetLineTextW(&Context, 0, 0, 0, pExceptionObject, 0x100u, &RequiredSize)
    || !(unsigned int)pSetupAToI(pExceptionObject, a5) )
  {
    v13 = GetLastError();
    v15 = v13;
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v14, v8, (__int64)a3, (__int64)a4, v13);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v15);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800298c8  push    rbp
0x1800298ca  push    rbx
0x1800298cb  push    rsi
0x1800298cc  push    rdi
0x1800298cd  push    r14
0x1800298cf  push    r15
0x1800298d1  lea     rbp, [rsp-178h]
0x1800298d9  sub     rsp, 278h
0x1800298e0  mov     rax, cs:__security_cookie
0x1800298e7  xor     rax, rsp
0x1800298ea  mov     [rbp+1A0h+var_40], rax
0x1800298f1  mov     rcx, [rcx]; InfHandle
0x1800298f4  mov     rsi, r9
0x1800298f7  mov     r15, [rbp+1A0h+arg_20]
0x1800298fe  lea     r9, [rsp+2A0h+Context]; Context
0x180029903  mov     rdi, r8
0x180029906  mov     r14, rdx
0x180029909  xorps   xmm0, xmm0
0x18002990c  xor     eax, eax
0x18002990e  mov     r8, rsi; Key
0x180029911  mov     qword ptr [rsp+2A0h+Context.Section], rax
0x180029916  mov     rdx, rdi; Section
0x180029919  movups  xmmword ptr [rsp+2A0h+Context.Inf], xmm0
0x18002991e  call    cs:__imp_SetupFindFirstLineW
0x180029924  test    eax, eax
0x180029926  jnz     short loc_18002999E
0x180029928  call    cs:__imp_GetLastError
0x18002992e  cmp     eax, 0E0000102h
0x180029933  jnz     short loc_18002993C
0x180029935  xor     al, al
0x180029937  jmp     loc_180029A4B
0x18002993c  call    cs:__imp_GetLastError
0x180029942  mov     ebx, eax
0x180029944  test    eax, eax
0x180029946  jz      short loc_18002999E
0x180029948  mov     rcx, cs:WPP_GLOBAL_Control
0x18002994f  lea     rdx, WPP_GLOBAL_Control
0x180029956  cmp     rcx, rdx
0x180029959  jz      short loc_180029980
0x18002995b  cmp     byte ptr [rcx+19h], 2
0x18002995f  jb      short loc_180029980
0x180029961  mov     rcx, [rcx+10h]
0x180029965  mov     edx, 0Ch
0x18002996a  mov     dword ptr [rsp+2A0h+RequiredSize], eax
0x18002996e  mov     r9, r14
0x180029971  mov     qword ptr [rsp+2A0h+ReturnBufferSize], rsi
0x180029976  mov     [rsp+2A0h+ReturnBuffer], rdi
0x18002997b  call    WPP_SF_SSSD
0x180029980  mov     edx, ebx; int
0x180029982  lea     rcx, [rsp+2A0h+pExceptionObject]; this
0x180029987  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18002998c  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180029993  lea     rcx, [rsp+2A0h+pExceptionObject]; pExceptionObject
0x180029998  call    _CxxThrowException_0
0x18002999e  mov     ecx, 100h
0x1800299a3  lea     rax, [rsp+2A0h+var_260]
0x1800299a8  mov     [rsp+2A0h+RequiredSize], rax; RequiredSize
0x1800299ad  xor     r9d, r9d; Key
0x1800299b0  mov     [rsp+2A0h+ReturnBufferSize], ecx; ReturnBufferSize
0x1800299b4  lea     rax, [rsp+2A0h+pExceptionObject]
0x1800299b9  mov     [rsp+2A0h+var_260], ecx
0x1800299bd  xor     r8d, r8d; Section
0x1800299c0  lea     rcx, [rsp+2A0h+Context]; Context
0x1800299c5  mov     [rsp+2A0h+ReturnBuffer], rax; ReturnBuffer
0x1800299ca  xor     edx, edx; InfHandle
0x1800299cc  call    cs:__imp_SetupGetLineTextW
0x1800299d2  test    eax, eax
0x1800299d4  jz      short loc_1800299E7
0x1800299d6  mov     rdx, r15
0x1800299d9  lea     rcx, [rsp+2A0h+pExceptionObject]
0x1800299de  call    pSetupAToI
0x1800299e3  test    eax, eax
0x1800299e5  jnz     short loc_180029A49
0x1800299e7  call    cs:__imp_GetLastError
0x1800299ed  mov     ebx, eax
0x1800299ef  test    eax, eax
0x1800299f1  jz      short loc_180029A49
0x1800299f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800299fa  lea     rdx, WPP_GLOBAL_Control
0x180029a01  cmp     rcx, rdx
0x180029a04  jz      short loc_180029A2B
0x180029a06  cmp     byte ptr [rcx+19h], 2
0x180029a0a  jb      short loc_180029A2B
0x180029a0c  mov     rcx, [rcx+10h]
0x180029a10  mov     edx, 0Dh
0x180029a15  mov     dword ptr [rsp+2A0h+RequiredSize], eax
0x180029a19  mov     r9, r14
0x180029a1c  mov     qword ptr [rsp+2A0h+ReturnBufferSize], rsi
0x180029a21  mov     [rsp+2A0h+ReturnBuffer], rdi
0x180029a26  call    WPP_SF_SSSD
0x180029a2b  mov     edx, ebx; int
0x180029a2d  lea     rcx, [rsp+2A0h+pExceptionObject]; this
0x180029a32  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180029a37  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180029a3e  lea     rcx, [rsp+2A0h+pExceptionObject]; pExceptionObject
0x180029a43  call    _CxxThrowException_0
0x180029a49  mov     al, 1
0x180029a4b  mov     rcx, [rbp+1A0h+var_40]
0x180029a52  xor     rcx, rsp; StackCookie
0x180029a55  call    __security_check_cookie
0x180029a5a  add     rsp, 278h
0x180029a61  pop     r15
0x180029a63  pop     r14
0x180029a65  pop     rdi
0x180029a66  pop     rsi
0x180029a67  pop     rbx
0x180029a68  pop     rbp
0x180029a69  retn
```
