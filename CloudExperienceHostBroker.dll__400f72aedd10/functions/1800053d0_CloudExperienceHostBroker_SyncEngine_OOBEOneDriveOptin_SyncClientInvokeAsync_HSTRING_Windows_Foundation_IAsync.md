# CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::SyncClientInvokeAsync(HSTRING__ *,Windows::Foundation::IAsyncOperation<HSTRING__ *> * *)

- ea: `0x1800053d0`
- end: `0x1800054a8`
- name: `?SyncClientInvokeAsync@OOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@UEAAJPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@Z`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800053d0`
- `0x180008344`
- `0x180028974`
- `0x180028bf4`
- `0x180029eb8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800053fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800053fe`

## string_xrefs

- `0x180005412`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::SyncClientInvokeAsync(
        __int64 a1,
        HSTRING a2,
        _QWORD *a3)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v7; // rax
  __int64 v8; // r8
  int v9; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+24h] [rbp-34h]
  HSTRING string; // [rsp+30h] [rbp-28h] BYREF
  char v12; // [rsp+38h] [rbp-20h]
  _BYTE v13[24]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HSTRING newString; // [rsp+70h] [rbp+18h] BYREF

  *a3 = 0;
  string = 0;
  v12 = 0;
  newString = 0;
  v4 = WindowsDuplicateString(a2, &newString);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)v4,
      v9);
    return v5;
  }
  string = newString;
  WindowsDeleteString(0);
  v7 = lambda_dd11ce7ba0bdb9c3bc985d445b6cb388_::_lambda_dd11ce7ba0bdb9c3bc985d445b6cb388_(v13, &string);
  v9 = 3;
  v10 = 128;
  v5 = ((__int64 (__fastcall *)(int *, _QWORD *, __int64, __int64))Windows::Internal::MakeAsyncOperation_Windows::Internal::CHSTRINGResult_HSTRING_____Windows::Internal::ComTaskPoolHandler__lambda_dd11ce7ba0bdb9c3bc985d445b6cb388___)(
         &v9,
         a3,
         v8,
         v7);
  lambda_efa6c27f00621b0780f7e4e4e9ad3296_::__lambda_efa6c27f00621b0780f7e4e4e9ad3296_(v13);
  if ( !string )
    return v5;
  WindowsDeleteString(string);
  return v5;
}

```

## disassembly

```asm
0x1800053d0  mov     [rsp+arg_0], rbx
0x1800053d5  mov     [rsp+arg_8], rsi
0x1800053da  push    rdi
0x1800053db  sub     rsp, 50h
0x1800053df  mov     rdi, r8
0x1800053e2  mov     rcx, rdx; string
0x1800053e5  xor     esi, esi
0x1800053e7  mov     [r8], rsi
0x1800053ea  mov     [rsp+58h+string], rsi
0x1800053ef  mov     [rsp+58h+var_20], sil
0x1800053f4  mov     [rsp+58h+newString], rsi
0x1800053f9  lea     rdx, [rsp+58h+newString]; newString
0x1800053fe  call    cs:__imp_WindowsDuplicateString
0x180005404  mov     ebx, eax
0x180005406  test    eax, eax
0x180005408  jns     short loc_180005436
0x18000540a  mov     rcx, [rsp+58h]; this
0x18000540f  mov     r9d, eax; char *
0x180005412  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x180005419  mov     edx, 71h ; 'q'; void *
0x18000541e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005423  nop
0x180005424  mov     eax, ebx
0x180005426  mov     rbx, [rsp+58h+arg_0]
0x18000542b  mov     rsi, [rsp+58h+arg_8]
0x180005430  add     rsp, 50h
0x180005434  pop     rdi
0x180005435  retn
0x180005436  mov     rax, [rsp+58h+newString]
0x18000543b  mov     [rsp+58h+string], rax
0x180005440  xor     ecx, ecx; string
0x180005442  call    cs:__imp_WindowsDeleteString
0x180005448  lea     rdx, [rsp+58h+string]
0x18000544d  lea     rcx, [rsp+58h+var_18]
0x180005452  call    _lambda_dd11ce7ba0bdb9c3bc985d445b6cb388____lambda_dd11ce7ba0bdb9c3bc985d445b6cb388_
0x180005457  nop
0x180005458  mov     [rsp+58h+var_38], 3
0x180005460  mov     [rsp+58h+var_34], 80h
0x180005469  mov     r9, rax
0x18000546c  mov     rdx, rdi
0x18000546f  lea     rcx, [rsp+58h+var_38]
0x180005474  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CHSTRINGResult_HSTRING_____Windows__Internal__ComTaskPoolHandler__lambda_dd11ce7ba0bdb9c3bc985d445b6cb388___
0x180005479  mov     ebx, eax
0x18000547b  lea     rcx, [rsp+58h+var_18]
0x180005480  call    _lambda_efa6c27f00621b0780f7e4e4e9ad3296_____lambda_efa6c27f00621b0780f7e4e4e9ad3296_
0x180005485  nop
0x180005486  mov     rcx, [rsp+58h+string]; string
0x18000548b  test    rcx, rcx
0x18000548e  jz      short loc_180005424
0x180005490  call    cs:__imp_WindowsDeleteString
0x180005496  mov     eax, ebx
0x180005498  mov     rbx, [rsp+58h+arg_0]
0x18000549d  mov     rsi, [rsp+58h+arg_8]
0x1800054a2  add     rsp, 50h
0x1800054a6  pop     rdi
0x1800054a7  retn
```
