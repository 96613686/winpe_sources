# winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::WaaSAssessmentHelper,winrt::Windows::Internal::WaasMedicDocked::IWaaSAssessmentHelper>::GetOSFeatureAssessment(winrt::impl::struct_Windows_Internal_WaasMedicDocked_WaaSAssessmentUpdate *,bool,winrt::hresult *)

- ea: `0x18000a870`
- end: `0x18000a91a`
- name: `?GetOSFeatureAssessment@?$produce@VWaaSAssessmentHelper@implementation@WaasMedicDocked@Internal@Windows@winrt@@UIWaaSAssessmentHelper@3456@@impl@winrt@@UEAAHPEAUstruct_Windows_Internal_WaasMedicDocked_WaaSAssessmentUpdate@23@_NPEAUhresult@3@@Z`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001570`
- `0x1800048e4`
- `0x18000a870`
- `0x18000d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::WaaSAssessmentHelper,winrt::Windows::Internal::WaasMedicDocked::IWaaSAssessmentHelper>::GetOSFeatureAssessment(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int *a4)
{
  __int64 v6; // rax
  int v7; // eax
  int v8; // ebx
  __int64 result; // rax
  int v10; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+28h] [rbp-40h] BYREF
  int v12; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v11 = 0;
  v12 = 0;
  v6 = a1 + 8;
  if ( !a1 )
    v6 = 24;
  try
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v6 + 32LL))(*(_QWORD *)v6, &v11);
    v8 = v7;
    if ( v7 >= 0 )
    {
      *(_QWORD *)a2 = v11;
      *(_DWORD *)(a2 + 8) = v12;
      v8 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.waasassessmenthelper.cpp",
        (const char *)(unsigned int)v7,
        v10);
    }
    *a4 = v8;
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
0x18000a870  push    rbx
0x18000a872  push    rsi
0x18000a873  push    rdi
0x18000a874  push    r14
0x18000a876  sub     rsp, 48h
0x18000a87a  mov     rax, cs:__security_cookie
0x18000a881  xor     rax, rsp
0x18000a884  mov     [rsp+68h+var_30], rax
0x18000a889  mov     rsi, r9
0x18000a88c  mov     rdi, rdx
0x18000a88f  xor     eax, eax
0x18000a891  mov     [rsp+68h+var_40], rax
0x18000a896  mov     [rsp+68h+var_38], eax
0x18000a89a  lea     rax, [rcx+8]
0x18000a89e  mov     r14d, 18h
0x18000a8a4  test    rcx, rcx
0x18000a8a7  cmovz   rax, r14
0x18000a8ab  mov     rcx, [rax]
0x18000a8ae  mov     rax, [rcx]
0x18000a8b1  movzx   r8d, r8b
0x18000a8b5  lea     rdx, [rsp+68h+var_40]
0x18000a8ba  mov     rax, [rax+20h]
0x18000a8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8c3  mov     ebx, eax
0x18000a8c5  test    eax, eax
0x18000a8c7  jns     short loc_18000A8E2
0x18000a8c9  mov     rcx, [rsp+68h]; this
0x18000a8ce  mov     r9d, eax; char *
0x18000a8d1  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\dockedapi"...
0x18000a8d8  mov     edx, r14d; void *
0x18000a8db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8e0  jmp     short loc_18000A8F8
0x18000a8e2  mov     eax, dword ptr [rsp+68h+var_40]
0x18000a8e6  mov     [rdi], eax
0x18000a8e8  mov     eax, dword ptr [rsp+68h+var_40+4]
0x18000a8ec  mov     [rdi+4], eax
0x18000a8ef  mov     eax, [rsp+68h+var_38]
0x18000a8f3  mov     [rdi+8], eax
0x18000a8f6  xor     ebx, ebx
0x18000a8f8  mov     [rsi], ebx
0x18000a8fa  xor     eax, eax
0x18000a8fc  jmp     short loc_18000A902
0x18000a8fe  mov     eax, [rsp+68h+var_48]
0x18000a902  mov     rcx, [rsp+68h+var_30]
0x18000a907  xor     rcx, rsp; StackCookie
0x18000a90a  call    __security_check_cookie
0x18000a90f  add     rsp, 48h
0x18000a913  pop     r14
0x18000a915  pop     rdi
0x18000a916  pop     rsi
0x18000a917  pop     rbx
0x18000a918  retn
```
