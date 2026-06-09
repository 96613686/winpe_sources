# CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::TryGetOfficeRegistryValue(HSTRING__ *,HSTRING__ *,HSTRING__ * *,uchar *)

- ea: `0x18002f320`
- end: `0x18002f47c`
- name: `?TryGetOfficeRegistryValue@OOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@UEAAJPEAUHSTRING__@@0PEAPEAU4@PEAE@Z`
- size: `348`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin *this, HSTRING, HSTRING, HSTRING *, const WCHAR *sourceString)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x180012408`
- `0x18001dd1c`
- `0x18002f320`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f3b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f3c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f3b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f3c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002f439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002f439`

## string_xrefs

- `0x18002f383`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002f3f2`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::TryGetOfficeRegistryValue(
        CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING *a4,
        const WCHAR *sourceString)
{
  int v8; // r15d
  int v9; // eax
  unsigned int v10; // ebx
  void *v11; // rsi
  __int64 (__fastcall *v12)(void *, PCWSTR, PCWSTR, const WCHAR **); // rdi
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v14; // rax
  HRESULT String; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v19; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  void *v21; // [rsp+98h] [rbp+20h] BYREF

  v8 = (int)sourceString;
  *(_BYTE *)sourceString = 0;
  *a4 = 0;
  v21 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  v9 = CloudExperienceHostCreateOOBEUserObject(
         &GUID_86c815aa_4888_4063_b0ab_03c49f788be4,
         &GUID_426317b8_c7d2_4647_ad76_2554806561b6,
         &v21);
  v10 = v9;
  if ( v9 >= 0 )
  {
    sourceString = 0;
    v11 = v21;
    v12 = *(__int64 (__fastcall **)(void *, PCWSTR, PCWSTR, const WCHAR **))(*(_QWORD *)v21 + 64LL);
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    v14 = WindowsGetStringRawBuffer(a2, 0);
    String = v12(v11, v14, StringRawBuffer, &sourceString);
    v10 = String;
    if ( String >= 0 )
    {
      if ( sourceString )
      {
        v17 = -1;
        do
          ++v17;
        while ( sourceString[v17] );
      }
      else
      {
        LODWORD(v17) = 0;
      }
      String = WindowsCreateString(sourceString, v17, a4);
      v10 = String;
      if ( String >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
        v10 = 0;
        goto LABEL_13;
      }
      v16 = 197;
    }
    else
    {
      v16 = 196;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)String,
      v8);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&sourceString);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC2,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)v9,
      v19);
  }
LABEL_13:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  return v10;
}

```

## disassembly

```asm
0x18002f320  mov     rax, rsp
0x18002f323  push    rbx
0x18002f324  push    rbp
0x18002f325  push    rsi
0x18002f326  push    rdi
0x18002f327  push    r12
0x18002f329  push    r13
0x18002f32b  push    r14
0x18002f32d  push    r15
0x18002f32f  sub     rsp, 38h
0x18002f333  mov     r14, r9
0x18002f336  mov     rbp, r8
0x18002f339  mov     r12, rdx
0x18002f33c  xor     r13d, r13d
0x18002f33f  mov     r15, [rsp+78h+sourceString]
0x18002f347  mov     [r15], r13b
0x18002f34a  mov     [r9], r13
0x18002f34d  mov     [rax+20h], r13
0x18002f351  lea     rcx, [rax+20h]
0x18002f355  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f35a  lea     r8, [rsp+78h+arg_18]; void **
0x18002f362  lea     rdx, _GUID_426317b8_c7d2_4647_ad76_2554806561b6; struct _GUID *
0x18002f369  lea     rcx, _GUID_86c815aa_4888_4063_b0ab_03c49f788be4; struct _GUID *
0x18002f370  call    ?CloudExperienceHostCreateOOBEUserObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateOOBEUserObject(_GUID const &,_GUID const &,void * *)
0x18002f375  mov     ebx, eax
0x18002f377  test    eax, eax
0x18002f379  jns     short loc_18002F399
0x18002f37b  mov     rcx, [rsp+78h]; this
0x18002f380  mov     r9d, eax; char *
0x18002f383  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002f38a  mov     edx, 0C2h; void *
0x18002f38f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f394  jmp     loc_18002F45C
0x18002f399  mov     [rsp+78h+sourceString], r13
0x18002f3a1  mov     rsi, [rsp+78h+arg_18]
0x18002f3a9  mov     rax, [rsi]
0x18002f3ac  mov     rdi, [rax+40h]
0x18002f3b0  xor     edx, edx; length
0x18002f3b2  mov     rcx, rbp; string
0x18002f3b5  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f3bb  mov     rbx, rax
0x18002f3be  xor     edx, edx; length
0x18002f3c0  mov     rcx, r12; string
0x18002f3c3  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f3c9  mov     qword ptr [rsp+78h+var_58], r15; int
0x18002f3ce  lea     r9, [rsp+78h+sourceString]
0x18002f3d6  mov     r8, rbx
0x18002f3d9  mov     rdx, rax
0x18002f3dc  mov     rcx, rsi
0x18002f3df  mov     rax, rdi
0x18002f3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3e7  mov     ebx, eax
0x18002f3e9  test    eax, eax
0x18002f3eb  jns     short loc_18002F416
0x18002f3ed  mov     edx, 0C4h; void *
0x18002f3f2  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002f3f9  mov     r9d, eax; char *
0x18002f3fc  mov     rcx, [rsp+78h]; this
0x18002f401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f406  nop
0x18002f407  lea     rcx, [rsp+78h+sourceString]
0x18002f40f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002f414  jmp     short loc_18002F45C
0x18002f416  mov     rcx, [rsp+78h+sourceString]; sourceString
0x18002f41e  test    rcx, rcx
0x18002f421  jnz     short loc_18002F428
0x18002f423  mov     rdx, r13
0x18002f426  jmp     short loc_18002F436
0x18002f428  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002f42c  inc     rdx; length
0x18002f42f  cmp     [rcx+rdx*2], r13w
0x18002f434  jnz     short loc_18002F42C
0x18002f436  mov     r8, r14; string
0x18002f439  call    cs:__imp_WindowsCreateString
0x18002f43f  mov     ebx, eax
0x18002f441  test    eax, eax
0x18002f443  jns     short loc_18002F44C
0x18002f445  mov     edx, 0C5h
0x18002f44a  jmp     short loc_18002F3F2
0x18002f44c  lea     rcx, [rsp+78h+sourceString]
0x18002f454  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002f459  mov     ebx, r13d
0x18002f45c  lea     rcx, [rsp+78h+arg_18]
0x18002f464  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f469  mov     eax, ebx
0x18002f46b  add     rsp, 38h
0x18002f46f  pop     r15
0x18002f471  pop     r14
0x18002f473  pop     r13
0x18002f475  pop     r12
0x18002f477  pop     rdi
0x18002f478  pop     rsi
0x18002f479  pop     rbp
0x18002f47a  pop     rbx
0x18002f47b  retn
```
