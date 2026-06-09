# winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::WaaSAssessmentHelper,winrt::Windows::Internal::WaasMedicDocked::IWaaSAssessmentHelper>::GetOSQualityAssessment(winrt::impl::struct_Windows_Internal_WaasMedicDocked_WaaSAssessmentUpdate *,bool,winrt::hresult *)

- ea: `0x18000a920`
- end: `0x18000a9c7`
- name: `?GetOSQualityAssessment@?$produce@VWaaSAssessmentHelper@implementation@WaasMedicDocked@Internal@Windows@winrt@@UIWaaSAssessmentHelper@3456@@impl@winrt@@UEAAHPEAUstruct_Windows_Internal_WaasMedicDocked_WaaSAssessmentUpdate@23@_NPEAUhresult@3@@Z`
- size: `167`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001570`
- `0x1800048e4`
- `0x18000a920`
- `0x18000d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::Windows::Internal::WaasMedicDocked::implementation::WaaSAssessmentHelper,winrt::Windows::Internal::WaasMedicDocked::IWaaSAssessmentHelper>::GetOSQualityAssessment(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int *a4)
{
  __int64 v6; // rax
  int v7; // eax
  int v8; // ebx
  __int64 result; // rax
  int v10; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+28h] [rbp-30h] BYREF
  int v12; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v11 = 0;
  v12 = 0;
  v6 = a1 + 8;
  if ( !a1 )
    v6 = 24;
  try
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v6 + 40LL))(*(_QWORD *)v6, &v11);
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
        (void *)0x24,
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
0x18000a920  push    rbx
0x18000a922  push    rsi
0x18000a923  push    rdi
0x18000a924  sub     rsp, 40h
0x18000a928  mov     rax, cs:__security_cookie
0x18000a92f  xor     rax, rsp
0x18000a932  mov     [rsp+58h+var_20], rax
0x18000a937  mov     rsi, r9
0x18000a93a  mov     rdi, rdx
0x18000a93d  xor     eax, eax
0x18000a93f  mov     [rsp+58h+var_30], rax
0x18000a944  mov     [rsp+58h+var_28], eax
0x18000a948  lea     rax, [rcx+8]
0x18000a94c  mov     edx, 18h
0x18000a951  test    rcx, rcx
0x18000a954  cmovz   rax, rdx
0x18000a958  mov     rcx, [rax]
0x18000a95b  mov     rax, [rcx]
0x18000a95e  movzx   r8d, r8b
0x18000a962  lea     rdx, [rsp+58h+var_30]
0x18000a967  mov     rax, [rax+28h]
0x18000a96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a970  mov     ebx, eax
0x18000a972  test    eax, eax
0x18000a974  jns     short loc_18000A991
0x18000a976  mov     rcx, [rsp+58h]; this
0x18000a97b  mov     r9d, eax; char *
0x18000a97e  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\dockedapi"...
0x18000a985  mov     edx, 24h ; '$'; void *
0x18000a98a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a98f  jmp     short loc_18000A9A7
0x18000a991  mov     eax, dword ptr [rsp+58h+var_30]
0x18000a995  mov     [rdi], eax
0x18000a997  mov     eax, dword ptr [rsp+58h+var_30+4]
0x18000a99b  mov     [rdi+4], eax
0x18000a99e  mov     eax, [rsp+58h+var_28]
0x18000a9a2  mov     [rdi+8], eax
0x18000a9a5  xor     ebx, ebx
0x18000a9a7  mov     [rsi], ebx
0x18000a9a9  xor     eax, eax
0x18000a9ab  jmp     short loc_18000A9B1
0x18000a9ad  mov     eax, [rsp+58h+var_38]
0x18000a9b1  mov     rcx, [rsp+58h+var_20]
0x18000a9b6  xor     rcx, rsp; StackCookie
0x18000a9b9  call    __security_check_cookie
0x18000a9be  add     rsp, 40h
0x18000a9c2  pop     rdi
0x18000a9c3  pop     rsi
0x18000a9c4  pop     rbx
0x18000a9c5  retn
```
