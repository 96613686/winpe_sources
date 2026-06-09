# OobeEsimTaskManager::IsOobeInProgress(void)

- ea: `0x18001bc44`
- end: `0x18001bd78`
- name: `?IsOobeInProgress@OobeEsimTaskManager@@AEAA_NXZ`
- size: `308`
- prototype: `bool __fastcall(OobeEsimTaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800079a0`

## callees

- `0x180002150`
- `0x18001bc44`
- `0x18001bdb8`
- `0x18002cd20`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001bc9d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001bc9d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001bcc2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001bcc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bc87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bc87`

## string_xrefs

- `0x18001bcd4`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x18001bd2c`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
bool __fastcall OobeEsimTaskManager::IsOobeInProgress(OobeEsimTaskManager *this)
{
  HRESULT v1; // eax
  HSTRING v2; // rbx
  int ActivationFactory; // eax
  __int64 v4; // rcx
  int v6; // eax
  bool v7; // bl
  __int64 v8; // [rsp+20h] [rbp-48h] BYREF
  int v9; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER v10; // [rsp+30h] [rbp-38h] BYREF
  HSTRING v11; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v9 = 0;
  v8 = 0;
  v11 = 0;
  v1 = WindowsCreateStringReference(L"Windows.System.Profile.SystemSetupInfo", 0x26u, &v10, &v11);
  if ( v1 < 0 )
  {
    RaiseException(v1, 1u, 0, 0);
    __debugbreak();
  }
  v2 = v11;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_b8366a4b_fb6a_4571_be0a_9a0f67954123, &v8);
  if ( ActivationFactory >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 48LL))(v8, &v9);
    if ( v6 >= 0 )
    {
      v7 = v9 != 2;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
      return v7;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4F,
        (int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v6);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x49,
      (int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
      (const char *)(unsigned int)ActivationFactory);
    v4 = v8;
    if ( v8 )
    {
      v8 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18001bc44  mov     r11, rsp
0x18001bc47  push    rbx
0x18001bc48  sub     rsp, 60h
0x18001bc4c  mov     rax, cs:__security_cookie
0x18001bc53  xor     rax, rsp
0x18001bc56  mov     [rsp+68h+var_18], rax
0x18001bc5b  mov     [rsp+68h+var_40], 0
0x18001bc63  mov     qword ptr [r11-48h], 0
0x18001bc6b  mov     qword ptr [r11-20h], 0
0x18001bc73  lea     r9, [r11-20h]; string
0x18001bc77  lea     r8, [r11-38h]; hstringHeader
0x18001bc7b  mov     edx, 26h ; '&'; length
0x18001bc80  lea     rcx, ?RuntimeClass_Windows_System_Profile_SystemSetupInfo@@3QBGB; "Windows.System.Profile.SystemSetupInfo"
0x18001bc87  call    cs:__imp_WindowsCreateStringReference
0x18001bc8d  test    eax, eax
0x18001bc8f  jns     short loc_18001BCA4
0x18001bc91  xor     r9d, r9d; lpArguments
0x18001bc94  xor     r8d, r8d; nNumberOfArguments
0x18001bc97  lea     edx, [r9+1]; dwExceptionFlags
0x18001bc9b  mov     ecx, eax; dwExceptionCode
0x18001bc9d  call    cs:__imp_RaiseException
0x18001bca3  int     3; Trap to Debugger
0x18001bca4  mov     rbx, [rsp+68h+var_20]
0x18001bca9  lea     rcx, [rsp+68h+var_48]
0x18001bcae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001bcb3  lea     r8, [rsp+68h+var_48]
0x18001bcb8  lea     rdx, _GUID_b8366a4b_fb6a_4571_be0a_9a0f67954123
0x18001bcbf  mov     rcx, rbx
0x18001bcc2  call    cs:__imp_RoGetActivationFactory
0x18001bcc8  mov     rcx, [rsp+68h]; this
0x18001bccd  test    eax, eax
0x18001bccf  jns     short loc_18001BD0A
0x18001bcd1  mov     r9d, eax; char *
0x18001bcd4  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001bcdb  mov     edx, 49h ; 'I'; void *
0x18001bce0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bce5  nop
0x18001bce6  mov     rcx, [rsp+68h+var_48]
0x18001bceb  test    rcx, rcx
0x18001bcee  jz      short loc_18001BD06
0x18001bcf0  mov     [rsp+68h+var_48], 0
0x18001bcf9  mov     rax, [rcx]
0x18001bcfc  mov     rax, [rax+10h]
0x18001bd00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd05  nop
0x18001bd06  xor     al, al
0x18001bd08  jmp     short loc_18001BD64
0x18001bd0a  mov     rcx, [rsp+68h+var_48]
0x18001bd0f  mov     rax, [rcx]
0x18001bd12  lea     rdx, [rsp+68h+var_40]
0x18001bd17  mov     rax, [rax+30h]
0x18001bd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd20  mov     rcx, [rsp+68h]; this
0x18001bd25  test    eax, eax
0x18001bd27  jns     short loc_18001BD4C
0x18001bd29  mov     r9d, eax; char *
0x18001bd2c  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001bd33  mov     edx, 4Fh ; 'O'; void *
0x18001bd38  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bd3d  nop
0x18001bd3e  lea     rcx, [rsp+68h+var_48]
0x18001bd43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001bd48  xor     al, al
0x18001bd4a  jmp     short loc_18001BD64
0x18001bd4c  cmp     [rsp+68h+var_40], 2
0x18001bd51  setnz   bl
0x18001bd54  lea     rcx, [rsp+68h+var_48]
0x18001bd59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001bd5e  mov     al, bl
0x18001bd60  jmp     short loc_18001BD64
0x18001bd62  xor     al, al
0x18001bd64  mov     rcx, [rsp+68h+var_18]
0x18001bd69  xor     rcx, rsp; StackCookie
0x18001bd6c  call    __security_check_cookie
0x18001bd71  add     rsp, 60h
0x18001bd75  pop     rbx
0x18001bd76  retn
```
