# AdjustPrivilege(ushort const *,EPrivilegeStatus)

- ea: `0x1400066f4`
- end: `0x1400068b4`
- name: `?AdjustPrivilege@@YAJPEBGW4EPrivilegeStatus@@@Z`
- size: `448`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140009344`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x1400066f4`
- `0x14000ae60`

## import_xrefs

- `ADVAPI32!AdjustTokenPrivileges` at `0x1400067bd`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1400067bd`
- `ADVAPI32!LookupPrivilegeValueW` at `0x14000676b`
- `ADVAPI32!LookupPrivilegeValueW` at `0x14000676b`
- `ADVAPI32!OpenProcessToken` at `0x140006733`
- `ADVAPI32!OpenProcessToken` at `0x140006733`
- `KERNEL32!IsDebuggerPresent` at `0x140006823`
- `KERNEL32!IsDebuggerPresent` at `0x140006823`
- `KERNEL32!GetLastError` at `0x14000673d`
- `KERNEL32!GetLastError` at `0x140006775`
- `KERNEL32!GetLastError` at `0x1400067cb`
- `KERNEL32!GetLastError` at `0x14000673d`
- `KERNEL32!GetLastError` at `0x140006775`
- `KERNEL32!GetLastError` at `0x1400067cb`
- `KERNEL32!CloseHandle` at `0x140006893`
- `KERNEL32!CloseHandle` at `0x140006893`
- `KERNEL32!GetCurrentProcess` at `0x140006720`
- `KERNEL32!GetCurrentProcess` at `0x140006720`

## string_xrefs

- `0x140006808`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140006831`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140006861`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400067f4`: `AdjustPrivilege`
- `0x140006764`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 AdjustPrivilege()
{
  HANDLE CurrentProcess; // rax
  signed int v1; // eax
  signed int v2; // ebx
  unsigned int v3; // r12d
  signed int v4; // eax
  signed int LastError; // eax
  signed int v7; // [rsp+30h] [rbp-58h]
  signed int v8; // [rsp+38h] [rbp-50h]
  void *TokenHandle; // [rsp+40h] [rbp-48h] BYREF
  _LUID Luid[2]; // [rsp+48h] [rbp-40h] BYREF

  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart) )
    {
      v2 = 0;
      Luid[0].LowPart = 1;
      Luid[1].HighPart = 2;
      if ( AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
        goto LABEL_18;
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v3 = 1353;
    }
    else
    {
      v4 = GetLastError();
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      v3 = 1347;
    }
  }
  else
  {
    v1 = GetLastError();
    v2 = v1;
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    v3 = 1340;
  }
  if ( v2 >= 0 )
    v2 = -2147467259;
  LOGASSERTHR(L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp", v3, L"AdjustPrivilege", L"CBRAEx", L"fSuccess", v2);
  if ( IsDebuggerPresent() )
  {
    v8 = v2;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v3,
      L"AdjustPrivilege",
      L"CBRAEx",
      L"fSuccess",
      v8);
  }
  else
  {
    v7 = v2;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v3,
      L"AdjustPrivilege",
      L"CBRAEx",
      L"fSuccess",
      v7);
  }
LABEL_18:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400066f4  push    rbx
0x1400066f6  push    rbp
0x1400066f7  push    rsi
0x1400066f8  push    r12
0x1400066fa  push    r14
0x1400066fc  sub     rsp, 60h
0x140006700  mov     rax, cs:__security_cookie
0x140006707  xor     rax, rsp
0x14000670a  mov     [rsp+88h+var_30], rax
0x14000670f  xorps   xmm0, xmm0
0x140006712  mov     [rsp+88h+TokenHandle], 0
0x14000671b  movups  xmmword ptr [rsp+88h+Luid.LowPart], xmm0
0x140006720  call    cs:__imp_GetCurrentProcess
0x140006726  lea     r8, [rsp+88h+TokenHandle]; TokenHandle
0x14000672b  mov     edx, 28h ; '('; DesiredAccess
0x140006730  mov     rcx, rax; ProcessHandle
0x140006733  call    cs:__imp_OpenProcessToken
0x140006739  test    eax, eax
0x14000673b  jnz     short loc_14000675D
0x14000673d  call    cs:__imp_GetLastError
0x140006743  mov     ebx, eax
0x140006745  test    eax, eax
0x140006747  jle     short loc_140006752
0x140006749  movzx   ebx, ax
0x14000674c  or      ebx, 80070000h
0x140006752  mov     r12d, 53Ch
0x140006758  jmp     loc_1400067E6
0x14000675d  lea     r8, [rsp+88h+Luid.HighPart]; lpLuid
0x140006762  xor     ecx, ecx; lpSystemName
0x140006764  lea     rdx, Name; "SeShutdownPrivilege"
0x14000676b  call    cs:__imp_LookupPrivilegeValueW
0x140006771  test    eax, eax
0x140006773  jnz     short loc_140006792
0x140006775  call    cs:__imp_GetLastError
0x14000677b  mov     ebx, eax
0x14000677d  test    eax, eax
0x14000677f  jle     short loc_14000678A
0x140006781  movzx   ebx, ax
0x140006784  or      ebx, 80070000h
0x14000678a  mov     r12d, 543h
0x140006790  jmp     short loc_1400067E6
0x140006792  mov     rcx, [rsp+88h+TokenHandle]; TokenHandle
0x140006797  lea     r8, [rsp+88h+Luid]; NewState
0x14000679c  xor     ebx, ebx
0x14000679e  mov     [rsp+88h+Luid.LowPart], 1
0x1400067a6  mov     [rsp+88h+ReturnLength], rbx; ReturnLength
0x1400067ab  xor     r9d, r9d; BufferLength
0x1400067ae  xor     edx, edx; DisableAllPrivileges
0x1400067b0  mov     [rsp+88h+PreviousState], rbx; PreviousState
0x1400067b5  mov     [rsp+88h+Luid.HighPart+8], 2
0x1400067bd  call    cs:__imp_AdjustTokenPrivileges
0x1400067c3  test    eax, eax
0x1400067c5  jnz     loc_140006884
0x1400067cb  call    cs:__imp_GetLastError
0x1400067d1  mov     ebx, eax
0x1400067d3  test    eax, eax
0x1400067d5  jle     short loc_1400067E0
0x1400067d7  movzx   ebx, ax
0x1400067da  or      ebx, 80070000h
0x1400067e0  mov     r12d, 549h
0x1400067e6  mov     eax, 80004005h
0x1400067eb  lea     r14, aCbraex; "CBRAEx"
0x1400067f2  test    ebx, ebx
0x1400067f4  lea     rsi, aAdjustprivileg; "AdjustPrivilege"
0x1400067fb  lea     rbp, aFsuccess; "fSuccess"
0x140006802  mov     r9, r14; unsigned __int16 *
0x140006805  cmovns  ebx, eax
0x140006808  lea     rcx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14000680f  mov     dword ptr [rsp+88h+ReturnLength], ebx; int
0x140006813  mov     r8, rsi; unsigned __int16 *
0x140006816  mov     edx, r12d; unsigned int
0x140006819  mov     [rsp+88h+PreviousState], rbp; unsigned __int16 *
0x14000681e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140006823  call    cs:__imp_IsDebuggerPresent
0x140006829  test    eax, eax
0x14000682b  jz      short loc_14000685D
0x14000682d  mov     [rsp+88h+var_50], ebx
0x140006831  lea     r8, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140006838  mov     [rsp+88h+var_58], rbp
0x14000683d  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140006844  mov     [rsp+88h+ReturnLength], r14
0x140006849  mov     r9d, r12d
0x14000684c  mov     ecx, 2; unsigned __int8
0x140006851  mov     [rsp+88h+PreviousState], rsi
0x140006856  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000685b  jmp     short loc_140006884
0x14000685d  mov     dword ptr [rsp+88h+var_58], ebx
0x140006861  lea     rdx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140006868  mov     [rsp+88h+ReturnLength], rbp
0x14000686d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140006874  mov     r9, rsi
0x140006877  mov     [rsp+88h+PreviousState], r14
0x14000687c  mov     r8d, r12d
0x14000687f  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140006884  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x140006889  lea     rdx, [rcx-1]
0x14000688d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140006891  ja      short loc_140006899
0x140006893  call    cs:__imp_CloseHandle
0x140006899  mov     eax, ebx
0x14000689b  mov     rcx, [rsp+88h+var_30]
0x1400068a0  xor     rcx, rsp; StackCookie
0x1400068a3  call    __security_check_cookie
0x1400068a8  add     rsp, 60h
0x1400068ac  pop     r14
0x1400068ae  pop     r12
0x1400068b0  pop     rsi
0x1400068b1  pop     rbp
0x1400068b2  pop     rbx
0x1400068b3  retn
```
