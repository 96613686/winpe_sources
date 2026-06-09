# winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::WaaSAssessmentHelper,winrt::Windows::Internal::WaasMedicDocked::IWaaSAssessmentHelper>::Initialize(winrt::hresult *)

- ea: `0x18000aa70`
- end: `0x18000ab01`
- name: `?Initialize@?$produce@VWaaSAssessmentHelper@implementation@WaasMedicDocked@Internal@Windows@winrt@@UIWaaSAssessmentHelper@3456@@impl@winrt@@UEAAHPEAUhresult@3@@Z`
- size: `145`
- prototype: `__int64 __fastcall(__int64, HRESULT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800048e4`
- `0x18000aa70`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aac2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aac2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::WaaSAssessmentHelper,winrt::Windows::Internal::WaasMedicDocked::IWaaSAssessmentHelper>::Initialize(
        __int64 a1,
        HRESULT *a2)
{
  LPVOID *v3; // rbx
  LPVOID v4; // rcx
  HRESULT Instance; // eax
  HRESULT v6; // ebx
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v10; // [rsp+40h] [rbp+8h] BYREF

  v3 = (LPVOID *)(a1 + 8);
  if ( !a1 )
    v3 = (LPVOID *)24;
  try
  {
    v4 = *v3;
    *v3 = 0;
    if ( v4 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    Instance = CoCreateInstance(
                 &GUID_098ef871_fa9f_46af_8958_c083515d7c9c,
                 0,
                 1u,
                 &GUID_28f36eb8_3990_460a_bda9_3f06f8514de9,
                 v3);
    v6 = Instance;
    if ( Instance >= 0 )
      v6 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.waasassessmenthelper.cpp",
        (const char *)(unsigned int)Instance,
        ppv);
    *a2 = v6;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v10);
  }
  return result;
}

```

## disassembly

```asm
0x18000aa70  mov     [rsp+arg_8], rbx
0x18000aa75  push    rdi
0x18000aa76  sub     rsp, 30h
0x18000aa7a  mov     rdi, rdx
0x18000aa7d  lea     rbx, [rcx+8]
0x18000aa81  mov     eax, 18h
0x18000aa86  test    rcx, rcx
0x18000aa89  cmovz   rbx, rax
0x18000aa8d  mov     rcx, [rbx]
0x18000aa90  mov     qword ptr [rbx], 0
0x18000aa97  test    rcx, rcx
0x18000aa9a  jz      short loc_18000AAA9
0x18000aa9c  mov     rax, [rcx]
0x18000aa9f  mov     rax, [rax+10h]
0x18000aaa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaa8  nop
0x18000aaa9  mov     qword ptr [rsp+38h+ppv], rbx; int
0x18000aaae  lea     r9, _GUID_28f36eb8_3990_460a_bda9_3f06f8514de9; riid
0x18000aab5  xor     edx, edx; pUnkOuter
0x18000aab7  lea     r8d, [rdx+1]; dwClsContext
0x18000aabb  lea     rcx, _GUID_098ef871_fa9f_46af_8958_c083515d7c9c; rclsid
0x18000aac2  call    cs:__imp_CoCreateInstance
0x18000aac8  mov     ebx, eax
0x18000aaca  test    eax, eax
0x18000aacc  jns     short loc_18000AAE9
0x18000aace  mov     rcx, [rsp+38h]; this
0x18000aad3  mov     r9d, eax; char *
0x18000aad6  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\dockedapi"...
0x18000aadd  mov     edx, 33h ; '3'; void *
0x18000aae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aae7  jmp     short loc_18000AAEB
0x18000aae9  xor     ebx, ebx
0x18000aaeb  mov     [rdi], ebx
0x18000aaed  xor     eax, eax
0x18000aaef  jmp     short loc_18000AAF5
0x18000aaf1  mov     eax, [rsp+38h+arg_0]
0x18000aaf5  mov     rbx, [rsp+38h+arg_8]
0x18000aafa  add     rsp, 30h
0x18000aafe  pop     rdi
0x18000aaff  retn
```
