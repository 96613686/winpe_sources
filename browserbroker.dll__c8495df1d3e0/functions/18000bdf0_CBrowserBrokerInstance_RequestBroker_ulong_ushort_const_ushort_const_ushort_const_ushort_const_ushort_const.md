# CBrowserBrokerInstance::RequestBroker(ulong,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000bdf0`
- end: `0x18000c03a`
- name: `?RequestBroker@CBrowserBrokerInstance@@UEAAJKPEBG0000@Z`
- size: `586`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *this, DWORD dwProcessId, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR StringSid, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006938`
- `0x1800085d0`
- `0x180008b94`
- `0x18000bdf0`
- `0x18000dc74`
- `0x18000e4b8`
- `0x18000e708`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bf59`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bf9a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bf59`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000bf9a`
- `iertutil!__imp_?SetProcessModelData@@YAJW4IEConfigurationID@@PEBG1@Z` at `0x18000be9f`
- `iertutil!__imp_?SetProcessModelData@@YAJW4IEConfigurationID@@PEBG1@Z` at `0x18000be9f`
- `iertutil!__imp_DeleteKey` at `0x18000bfb7`
- `iertutil!__imp_DeleteKey` at `0x18000bfb7`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x18000beac`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x18000beac`
- `iertutil!__imp_?IEConfiguration_SetBrowserAppProfile@@YAJPEBGKK@Z` at `0x18000be7a`
- `iertutil!__imp_?IEConfiguration_SetBrowserAppProfile@@YAJPEBGKK@Z` at `0x18000be7a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000bf1b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000bf1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfe1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000bee7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000bee7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000bf6a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000bf6a`

## string_xrefs

- `0x18000bfff`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`
- `0x18000c025`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`
- `0x18000c00e`: `Failed to open the manager PID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBrowserBrokerInstance::RequestBroker(
        CBrowserBrokerInstance *this,
        DWORD dwProcessId,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        LPCWSTR StringSid,
        const unsigned __int16 *a7)
{
  signed int v10; // ebx
  unsigned int *v11; // r14
  const WCHAR *v12; // rbp
  __int64 v13; // rdx
  HANDLE v14; // rax
  signed int v15; // eax
  signed int v16; // eax
  signed int LastError; // eax
  unsigned int v19; // eax
  int dwMilliseconds; // [rsp+20h] [rbp-28h]
  const char *dwFlags; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v23; // [rsp+58h] [rbp+10h] BYREF

  v10 = -2147024891;
  if ( !dwProcessId || _InterlockedCompareExchange((volatile signed __int32 *)this + 8, dwProcessId, 0) )
    return (unsigned int)v10;
  v11 = (unsigned int *)((char *)this + 56);
  v10 = BrokerAuthenticateCOMCaller((unsigned int *)this + 14, (const unsigned __int16 **)this + 6, 0);
  if ( v10 < 0 )
  {
LABEL_24:
    CBrowserBrokerInstance::Detach(this);
    return (unsigned int)v10;
  }
  if ( *v11 == 255 )
    goto LABEL_5;
  v10 = BrokerSetSpartanPackageBrokerInstance(1, *v11, this);
  if ( v10 < 0 )
    goto LABEL_24;
  v10 = IEConfiguration_SetBrowserAppProfile(a4, 2u, dwProcessId);
  if ( v10 < 0 )
    goto LABEL_24;
  v12 = StringSid;
  SetProcessModelData(268435519, StringSid, a7);
  LOBYTE(v13) = 1;
  IEConfiguration_SetBool(536870923, v13);
  v23 = 0;
  v10 = BrokerAuthenticateCOMCaller(0, 0, &v23);
  if ( v10 < 0 )
    goto LABEL_24;
  if ( v23 != 122 )
  {
LABEL_5:
    v10 = -2147024891;
    goto LABEL_24;
  }
  v14 = OpenProcess(0x100441u, 0, dwProcessId);
  *((_QWORD *)this + 3) = v14;
  if ( !v14 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v19 = wil::verify_hresult<long>((unsigned int)LastError);
    wil::details::in1diag3::FailFast_HrMsg(
      retaddr,
      (void *)0x3CE,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
      (const char *)v19,
      (int)"Failed to open the manager PID",
      dwFlags);
  }
  if ( RegisterWaitForSingleObject((PHANDLE)this + 5, v14, s_WaitOnAttachedProcess_Callback, this, 0xFFFFFFFF, 8u) )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    if ( !(unsigned int)_o_wcscpy_s((char *)this + 96, 256, v12) )
    {
      if ( ConvertStringSidToSidW(v12, (PSID *)this + 11) )
        goto LABEL_32;
      v16 = GetLastError();
      v10 = v16;
      if ( v16 > 0 )
        v10 = (unsigned __int16)v16 | 0x80070000;
      if ( v10 >= 0 )
      {
LABEL_32:
        if ( !(unsigned int)_o_wcscpy_s((char *)this + 608, 256, v12) )
        {
          *((_WORD *)this + 311) = 51;
          DeleteKey(SettingStore::IEKEY_BrokeredRead_DesktopUrlIds, 2);
          return (unsigned int)v10;
        }
      }
    }
    v10 = -2147467259;
    goto LABEL_24;
  }
  v15 = GetLastError();
  v10 = v15;
  if ( v15 > 0 )
    v10 = (unsigned __int16)v15 | 0x80070000;
  if ( v10 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x3D5,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
      (const char *)(unsigned int)v10,
      dwMilliseconds);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000bdf0  mov     [rsp+arg_0], rbx
0x18000bdf5  mov     [rsp+arg_10], rbp
0x18000bdfa  push    rsi
0x18000bdfb  push    rdi
0x18000bdfc  push    r14
0x18000bdfe  sub     rsp, 30h
0x18000be02  mov     rbp, r9
0x18000be05  mov     esi, edx
0x18000be07  mov     rdi, rcx
0x18000be0a  mov     ebx, 80070005h
0x18000be0f  test    edx, edx
0x18000be11  jz      loc_18000BFCC
0x18000be17  xor     eax, eax
0x18000be19  lock cmpxchg [rcx+20h], esi
0x18000be1e  jnz     loc_18000BFCC
0x18000be24  lea     r14, [rcx+38h]
0x18000be28  xor     r8d, r8d; unsigned int *
0x18000be2b  lea     rdx, [rcx+30h]; unsigned __int16 **
0x18000be2f  mov     rcx, r14; unsigned int *
0x18000be32  call    ?BrokerAuthenticateCOMCaller@@YAJPEAKPEAPEBG0@Z; BrokerAuthenticateCOMCaller(ulong *,ushort const * *,ulong *)
0x18000be37  mov     ebx, eax
0x18000be39  test    eax, eax
0x18000be3b  js      loc_18000BFC4
0x18000be41  cmp     dword ptr [r14], 0FFh
0x18000be48  jnz     short loc_18000BE54
0x18000be4a  mov     ebx, 80070005h
0x18000be4f  jmp     loc_18000BFC4
0x18000be54  mov     edx, [r14]; unsigned int
0x18000be57  mov     r8, rdi; struct CBrowserBrokerInstance *
0x18000be5a  mov     cl, 1; bool
0x18000be5c  call    ?BrokerSetSpartanPackageBrokerInstance@@YAJ_NKPEAVCBrowserBrokerInstance@@@Z; BrokerSetSpartanPackageBrokerInstance(bool,ulong,CBrowserBrokerInstance *)
0x18000be61  mov     ebx, eax
0x18000be63  test    eax, eax
0x18000be65  js      loc_18000BFC4
0x18000be6b  mov     r14d, 2
0x18000be71  mov     r8d, esi
0x18000be74  mov     edx, r14d
0x18000be77  mov     rcx, rbp
0x18000be7a  call    cs:__imp_?IEConfiguration_SetBrowserAppProfile@@YAJPEBGKK@Z; IEConfiguration_SetBrowserAppProfile(ushort const *,ulong,ulong)
0x18000be80  mov     ebx, eax
0x18000be82  test    eax, eax
0x18000be84  js      loc_18000BFC4
0x18000be8a  mov     rbp, [rsp+48h+StringSid]
0x18000be8f  mov     ecx, 1000003Fh
0x18000be94  mov     r8, [rsp+48h+arg_30]
0x18000be9c  mov     rdx, rbp
0x18000be9f  call    cs:__imp_?SetProcessModelData@@YAJW4IEConfigurationID@@PEBG1@Z; SetProcessModelData(IEConfigurationID,ushort const *,ushort const *)
0x18000bea5  mov     dl, 1
0x18000bea7  mov     ecx, 2000000Bh
0x18000beac  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x18000beb2  lea     r8, [rsp+48h+arg_8]; unsigned int *
0x18000beb7  mov     [rsp+48h+arg_8], 0
0x18000bebf  xor     edx, edx; unsigned __int16 **
0x18000bec1  xor     ecx, ecx; unsigned int *
0x18000bec3  call    ?BrokerAuthenticateCOMCaller@@YAJPEAKPEAPEBG0@Z; BrokerAuthenticateCOMCaller(ulong *,ushort const * *,ulong *)
0x18000bec8  mov     ebx, eax
0x18000beca  test    eax, eax
0x18000becc  js      loc_18000BFC4
0x18000bed2  cmp     [rsp+48h+arg_8], 7Ah ; 'z'
0x18000bed7  jnz     loc_18000BE4A
0x18000bedd  mov     r8d, esi; dwProcessId
0x18000bee0  xor     edx, edx; bInheritHandle
0x18000bee2  mov     ecx, 100441h; dwDesiredAccess
0x18000bee7  call    cs:__imp_OpenProcess
0x18000beed  mov     [rdi+18h], rax
0x18000bef1  test    rax, rax
0x18000bef4  jz      loc_18000BFE1
0x18000befa  lea     rcx, [rdi+28h]; phNewWaitObject
0x18000befe  mov     [rsp+48h+dwFlags], 8; dwFlags
0x18000bf06  mov     r9, rdi; Context
0x18000bf09  mov     [rsp+48h+dwMilliseconds], 0FFFFFFFFh; int
0x18000bf11  lea     r8, s_WaitOnAttachedProcess_Callback; Callback
0x18000bf18  mov     rdx, rax; hObject
0x18000bf1b  call    cs:__imp_RegisterWaitForSingleObject
0x18000bf21  test    eax, eax
0x18000bf23  jnz     short loc_18000BF47
0x18000bf25  call    cs:__imp_GetLastError
0x18000bf2b  mov     ebx, eax
0x18000bf2d  test    eax, eax
0x18000bf2f  jle     short loc_18000BF3A
0x18000bf31  movzx   ebx, ax
0x18000bf34  or      ebx, 80070000h
0x18000bf3a  test    ebx, ebx
0x18000bf3c  js      loc_18000C020
0x18000bf42  jmp     loc_18000BFCC
0x18000bf47  lock inc dword ptr [rdi+8]
0x18000bf4b  mov     esi, 100h
0x18000bf50  lea     rcx, [rdi+60h]
0x18000bf54  mov     edx, esi
0x18000bf56  mov     r8, rbp
0x18000bf59  call    cs:__imp__o_wcscpy_s
0x18000bf5f  test    eax, eax
0x18000bf61  jnz     short loc_18000BFBF
0x18000bf63  lea     rdx, [rdi+58h]; Sid
0x18000bf67  mov     rcx, rbp; StringSid
0x18000bf6a  call    cs:__imp_ConvertStringSidToSidW
0x18000bf70  test    eax, eax
0x18000bf72  jnz     short loc_18000BF8D
0x18000bf74  call    cs:__imp_GetLastError
0x18000bf7a  mov     ebx, eax
0x18000bf7c  test    eax, eax
0x18000bf7e  jle     short loc_18000BF89
0x18000bf80  movzx   ebx, ax
0x18000bf83  or      ebx, 80070000h
0x18000bf89  test    ebx, ebx
0x18000bf8b  js      short loc_18000BFBF
0x18000bf8d  lea     rcx, [rdi+260h]
0x18000bf94  mov     r8, rbp
0x18000bf97  mov     rdx, rsi
0x18000bf9a  call    cs:__imp__o_wcscpy_s
0x18000bfa0  test    eax, eax
0x18000bfa2  jnz     short loc_18000BFBF
0x18000bfa4  mov     rcx, cs:?IEKEY_BrokeredRead_DesktopUrlIds@SettingStore@@3UKEYID@1@B; SettingStore::KEYID const SettingStore::IEKEY_BrokeredRead_DesktopUrlIds
0x18000bfab  mov     edx, r14d
0x18000bfae  mov     word ptr [rdi+26Eh], 33h ; '3'
0x18000bfb7  call    cs:__imp_DeleteKey
0x18000bfbd  jmp     short loc_18000BFCC
0x18000bfbf  mov     ebx, 80004005h
0x18000bfc4  mov     rcx, rdi; this
0x18000bfc7  call    ?Detach@CBrowserBrokerInstance@@QEAAXXZ; CBrowserBrokerInstance::Detach(void)
0x18000bfcc  mov     rbp, [rsp+48h+arg_10]
0x18000bfd1  mov     eax, ebx
0x18000bfd3  mov     rbx, [rsp+48h+arg_0]
0x18000bfd8  add     rsp, 30h
0x18000bfdc  pop     r14
0x18000bfde  pop     rdi
0x18000bfdf  pop     rsi
0x18000bfe0  retn
0x18000bfe1  call    cs:__imp_GetLastError
0x18000bfe7  test    eax, eax
0x18000bfe9  jle     short loc_18000BFF3
0x18000bfeb  movzx   eax, ax
0x18000bfee  or      eax, 80070000h
0x18000bff3  mov     ecx, eax
0x18000bff5  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000bffa  mov     rcx, [rsp+48h]; this
0x18000bfff  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18000c006  mov     r9d, eax; char *
0x18000c009  mov     edx, 3CEh; void *
0x18000c00e  lea     rax, aFailedToOpenTh; "Failed to open the manager PID"
0x18000c015  mov     qword ptr [rsp+48h+dwMilliseconds], rax; int
0x18000c01a  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000c020  mov     rcx, [rsp+48h]; this
0x18000c025  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18000c02c  mov     r9d, ebx; char *
0x18000c02f  mov     edx, 3D5h; void *
0x18000c034  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
