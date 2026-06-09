# Windows::Internal::GenericLightDismissClient::_GetLightDismissManager(ILightDismissProvider * *)

- ea: `0x18003c43c`
- end: `0x18003c56f`
- name: `?_GetLightDismissManager@GenericLightDismissClient@Internal@Windows@@AEAAJPEAPEAUILightDismissProvider@@@Z`
- size: `307`
- prototype: `int(Windows::Internal::GenericLightDismissClient *__hidden this, struct ILightDismissProvider **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c248`

## callees

- `0x18003217c`
- `0x18003c43c`
- `0x180050ba0`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c4c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c4c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c45f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c45f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c4ff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c54a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c4ff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c54a`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18003c4a5`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18003c4a5`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18003c467`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18003c467`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::GenericLightDismissClient::_GetLightDismissManager(
        Windows::Internal::GenericLightDismissClient *this,
        LPVOID *a2)
{
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rcx
  HRESULT v5; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-48h] BYREF
  __int128 v8; // [rsp+38h] [rbp-40h] BYREF
  wchar_t v9; // [rsp+48h] [rbp-30h]
  _BYTE pvInfo[16]; // [rsp+50h] [rbp-28h] BYREF
  __int16 v11; // [rsp+60h] [rbp-18h]

  *a2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( ThreadDesktop
    && (v8 = *(_OWORD *)L"Winlogon", v9 = aWinlogon[8], GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x12u, 0))
    && (v11 = 0, !(unsigned int)_o__wcsicmp(pvInfo, &v8)) )
  {
    v5 = 0;
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v5 = CoCreateInstance(&CLSID_ImmersiveShellBroker, 0, 4u, &GUID_9767060c_9476_42e2_8f7b_2f10fd13765c, &ppv);
    if ( v5 >= 0 )
      v5 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)ppv + 24LL))(ppv, a2);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  }
  if ( !*a2 )
    return (unsigned int)CoCreateInstance(
                           &CLSID_SimpleLightDismissProvider,
                           0,
                           1u,
                           &GUID_b849acb5_8ac5_4fb8_88b6_55c749d25a44,
                           a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003c43c  mov     [rsp+arg_0], rbx
0x18003c441  push    rdi
0x18003c442  sub     rsp, 70h
0x18003c446  mov     rax, cs:__security_cookie
0x18003c44d  xor     rax, rsp
0x18003c450  mov     [rsp+78h+var_10], rax
0x18003c455  mov     rdi, rdx
0x18003c458  mov     qword ptr [rdx], 0
0x18003c45f  call    cs:__imp_GetCurrentThreadId
0x18003c465  mov     ecx, eax; dwThreadId
0x18003c467  call    cs:__imp_GetThreadDesktop
0x18003c46d  mov     rcx, rax; hObj
0x18003c470  test    rax, rax
0x18003c473  jz      short loc_18003C4CE
0x18003c475  movups  xmm0, xmmword ptr cs:aWinlogon; "Winlogon"
0x18003c47c  movups  [rsp+78h+var_40], xmm0
0x18003c481  movzx   eax, word ptr cs:aWinlogon+10h; ""
0x18003c488  mov     [rsp+78h+var_30], ax
0x18003c48d  mov     [rsp+78h+lpnLengthNeeded], 0; lpnLengthNeeded
0x18003c496  mov     r9d, 12h; nLength
0x18003c49c  lea     r8, [rsp+78h+pvInfo]; pvInfo
0x18003c4a1  lea     edx, [r9-10h]; nIndex
0x18003c4a5  call    cs:__imp_GetUserObjectInformationW
0x18003c4ab  test    eax, eax
0x18003c4ad  jz      short loc_18003C4CE
0x18003c4af  xor     eax, eax
0x18003c4b1  mov     [rsp+78h+var_18], ax
0x18003c4b6  lea     rdx, [rsp+78h+var_40]
0x18003c4bb  lea     rcx, [rsp+78h+pvInfo]
0x18003c4c0  call    cs:__imp__o__wcsicmp
0x18003c4c6  test    eax, eax
0x18003c4c8  jnz     short loc_18003C4CE
0x18003c4ca  xor     ebx, ebx
0x18003c4cc  jmp     short loc_18003C52B
0x18003c4ce  mov     [rsp+78h+ppv], 0
0x18003c4d7  lea     rcx, [rsp+78h+ppv]
0x18003c4dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c4e1  lea     rax, [rsp+78h+ppv]
0x18003c4e6  mov     [rsp+78h+lpnLengthNeeded], rax; ppv
0x18003c4eb  lea     r9, _GUID_9767060c_9476_42e2_8f7b_2f10fd13765c; riid
0x18003c4f2  xor     edx, edx; pUnkOuter
0x18003c4f4  lea     r8d, [rdx+4]; dwClsContext
0x18003c4f8  lea     rcx, CLSID_ImmersiveShellBroker; rclsid
0x18003c4ff  call    cs:__imp_CoCreateInstance
0x18003c505  mov     ebx, eax
0x18003c507  test    eax, eax
0x18003c509  js      short loc_18003C521
0x18003c50b  mov     rcx, [rsp+78h+ppv]
0x18003c510  mov     rax, [rcx]
0x18003c513  mov     rdx, rdi
0x18003c516  mov     rax, [rax+18h]
0x18003c51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c51f  mov     ebx, eax
0x18003c521  lea     rcx, [rsp+78h+ppv]
0x18003c526  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c52b  cmp     qword ptr [rdi], 0
0x18003c52f  jnz     short loc_18003C552
0x18003c531  mov     [rsp+78h+lpnLengthNeeded], rdi; ppv
0x18003c536  lea     r9, _GUID_b849acb5_8ac5_4fb8_88b6_55c749d25a44; riid
0x18003c53d  xor     edx, edx; pUnkOuter
0x18003c53f  lea     r8d, [rdx+1]; dwClsContext
0x18003c543  lea     rcx, CLSID_SimpleLightDismissProvider; rclsid
0x18003c54a  call    cs:__imp_CoCreateInstance
0x18003c550  mov     ebx, eax
0x18003c552  mov     eax, ebx
0x18003c554  mov     rcx, [rsp+78h+var_10]
0x18003c559  xor     rcx, rsp; StackCookie
0x18003c55c  call    __security_check_cookie
0x18003c561  mov     rbx, [rsp+78h+arg_0]
0x18003c569  add     rsp, 70h
0x18003c56d  pop     rdi
0x18003c56e  retn
```
