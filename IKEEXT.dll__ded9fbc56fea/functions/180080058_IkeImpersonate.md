# IkeImpersonate

- ea: `0x180080058`
- end: `0x1800801fb`
- name: `IkeImpersonate`
- size: `419`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001e4e0`
- `0x18007e764`
- `0x180082710`
- `0x180082cd0`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800061ec`
- `0x180008388`
- `0x180019e40`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x180080058`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008019c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008019c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180080192`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180080192`

## string_xrefs

- `0x18008008d`: `IkeImpersonate`
- `0x1800801c1`: `IkeImpersonate`
- `0x1800801cd`: `IkeImpersonate`
- `0x1800801a9`: `ImpersonateLoggedOnUser`
- `0x18008012b`: `Bypassing impersonation for local service`

## pseudocode

```c
__int64 __fastcall IkeImpersonate(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 ImpersonationHandle; // rsi
  __int64 v9; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  int TlsMmLuid; // eax
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // r8d
  int v19; // r9d
  DWORD LastError; // eax
  __int64 v21; // rcx
  HANDLE hToken[2]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v24[32]; // [rsp+40h] [rbp-19h] BYREF
  HANDLE *v25; // [rsp+60h] [rbp+7h]
  __int64 v26; // [rsp+68h] [rbp+Fh]
  _BYTE v27[16]; // [rsp+70h] [rbp+17h] BYREF
  const char *v28; // [rsp+80h] [rbp+27h]
  __int64 v29; // [rsp+88h] [rbp+2Fh]

  hToken[0] = 0;
  TraceLogHelper("IkeImpersonate", 1);
  if ( (*(_DWORD *)(a2 + 72) & 0x40000) != 0 )
  {
    ImpersonationHandle = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v5);
      TlsMmLuid = IkeGetTlsMmLuid(v12, v11, v13, v14);
      WPP_SF_iS(v9, 11, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      hToken[0] = (HANDLE)IkeGetTlsMmLuid(v5, v4, v6, v7);
      v25 = hToken;
      v26 = 8;
      v17 = IkeGetTlsPeerAddr(v16);
      tlgCreate1Sz_wchar_t(v27, v17);
      v29 = 42;
      v28 = "Bypassing impersonation for local service";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&word_180155E5E,
        v18,
        v19,
        5,
        (__int64)v24);
    }
  }
  else
  {
    ImpersonationHandle = IkeGetImpersonationHandle(a1, a2, 0, 1, hToken);
    if ( !ImpersonationHandle && hToken[0] )
    {
      if ( ImpersonateLoggedOnUser(hToken[0]) )
      {
        *(_DWORD *)(a2 + 72) |= 0x400000u;
      }
      else
      {
        LastError = GetLastError();
        ImpersonationHandle = WfpReportSysErrorAsWinError(v21, "ImpersonateLoggedOnUser", LastError, 1);
      }
    }
  }
  TraceLogHelper("IkeImpersonate", 0);
  return IkeReturnError(ImpersonationHandle, "IkeImpersonate");
}

```

## disassembly

```asm
0x180080058  mov     [rsp-8+arg_10], rbx
0x18008005d  push    rbp
0x18008005e  push    rsi
0x18008005f  push    rdi
0x180080060  lea     rbp, [rsp-47h]
0x180080065  sub     rsp, 0A0h
0x18008006c  mov     rax, cs:__security_cookie
0x180080073  xor     rax, rsp
0x180080076  mov     [rbp+57h+var_20], rax
0x18008007a  mov     rbx, rdx
0x18008007d  mov     [rbp+57h+hToken], 0
0x180080085  mov     rdi, rcx
0x180080088  mov     edx, 1
0x18008008d  lea     rcx, aIkeimpersonate; "IkeImpersonate"
0x180080094  call    TraceLogHelper
0x180080099  test    dword ptr [rbx+48h], 40000h
0x1800800a0  jz      loc_180080164
0x1800800a6  xor     esi, esi
0x1800800a8  mov     rdi, cs:WPP_GLOBAL_Control
0x1800800af  lea     rax, WPP_GLOBAL_Control
0x1800800b6  cmp     rdi, rax
0x1800800b9  jz      short loc_1800800F2
0x1800800bb  cmp     byte ptr [rdi+19h], 4
0x1800800bf  jb      short loc_1800800F2
0x1800800c1  test    byte ptr [rdi+1Ch], 10h
0x1800800c5  jz      short loc_1800800F2
0x1800800c7  mov     rdi, [rdi+10h]
0x1800800cb  call    IkeGetTlsPeerAddr
0x1800800d0  mov     rbx, rax
0x1800800d3  call    IkeGetTlsMmLuid
0x1800800d8  mov     r9, rax
0x1800800db  mov     [rsp+0B0h+var_90], rbx
0x1800800e0  lea     edx, [rsi+0Bh]
0x1800800e3  mov     rcx, rdi
0x1800800e6  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x1800800ed  call    WPP_SF_iS
0x1800800f2  mov     eax, cs:dword_180173278
0x1800800f8  cmp     eax, 4
0x1800800fb  jbe     loc_1800801BF
0x180080101  call    IkeGetTlsMmLuid
0x180080106  mov     [rbp+57h+hToken], rax
0x18008010a  lea     rax, [rbp+57h+hToken]
0x18008010e  mov     [rbp+57h+var_50], rax
0x180080112  mov     [rbp+57h+var_48], 8
0x18008011a  call    IkeGetTlsPeerAddr
0x18008011f  mov     rdx, rax
0x180080122  lea     rcx, [rbp+57h+var_40]
0x180080126  call    _tlgCreate1Sz_wchar_t
0x18008012b  lea     rcx, aBypassingImper; "Bypassing impersonation for local servi"...
0x180080132  mov     [rbp+57h+var_28], 2Ah ; '*'
0x18008013a  lea     rax, [rbp+57h+var_70]
0x18008013e  mov     [rbp+57h+var_30], rcx
0x180080142  mov     [rsp+0B0h+var_88], rax
0x180080147  lea     rcx, dword_180173278
0x18008014e  lea     rdx, word_180155E5E
0x180080155  mov     dword ptr [rsp+0B0h+var_90], 5
0x18008015d  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180080162  jmp     short loc_1800801BF
0x180080164  lea     rax, [rbp+57h+hToken]
0x180080168  mov     r9d, 1
0x18008016e  xor     r8d, r8d
0x180080171  mov     [rsp+0B0h+var_90], rax
0x180080176  mov     rdx, rbx
0x180080179  mov     rcx, rdi
0x18008017c  call    IkeGetImpersonationHandle
0x180080181  mov     rsi, rax
0x180080184  test    rax, rax
0x180080187  jnz     short loc_1800801BF
0x180080189  mov     rcx, [rbp+57h+hToken]; hToken
0x18008018d  test    rcx, rcx
0x180080190  jz      short loc_1800801BF
0x180080192  call    cs:__imp_ImpersonateLoggedOnUser
0x180080198  test    eax, eax
0x18008019a  jnz     short loc_1800801BA
0x18008019c  call    cs:__imp_GetLastError
0x1800801a2  mov     r8d, eax
0x1800801a5  lea     r9d, [rsi+1]
0x1800801a9  lea     rdx, aImpersonatelog; "ImpersonateLoggedOnUser"
0x1800801b0  call    WfpReportSysErrorAsWinError
0x1800801b5  mov     rsi, rax
0x1800801b8  jmp     short loc_1800801BF
0x1800801ba  bts     dword ptr [rbx+48h], 16h
0x1800801bf  xor     edx, edx
0x1800801c1  lea     rcx, aIkeimpersonate; "IkeImpersonate"
0x1800801c8  call    TraceLogHelper
0x1800801cd  lea     rdx, aIkeimpersonate; "IkeImpersonate"
0x1800801d4  mov     rcx, rsi
0x1800801d7  call    IkeReturnError
0x1800801dc  mov     rcx, [rbp+57h+var_20]
0x1800801e0  xor     rcx, rsp; StackCookie
0x1800801e3  call    __security_check_cookie
0x1800801e8  mov     rbx, [rsp+0B0h+arg_10]
0x1800801f0  add     rsp, 0A0h
0x1800801f7  pop     rdi
0x1800801f8  pop     rsi
0x1800801f9  pop     rbp
0x1800801fa  retn
```
