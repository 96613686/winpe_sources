# wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(void)

- ea: `0x180005bc0`
- end: `0x180005c35`
- name: `?EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `117`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800058c0`

## callees

- `0x180005bc0`
- `0x18001307c`
- `0x18001c010`

## string_xrefs

- `0x180005c12`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(
        wil::details::FeatureStateManager *this)
{
  _QWORD *v1; // rbx
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v4; // eax

  v1 = (_QWORD *)((char *)this + 144);
  if ( *((_QWORD *)this + 18) )
  {
    v4 = 0;
  }
  else
  {
    NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    *v1 = 0;
    if ( NtDllProcedureAddress
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0) )
    {
      v4 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), wil::details::FeatureStateManager *, _QWORD, _QWORD *))NtDllProcedureAddress)(
             _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
             this,
             0,
             v1);
    }
    else
    {
      v4 = -1073741511;
    }
  }
  return v4 == 0;
}

```

## disassembly

```asm
0x180005bc0  mov     [rsp+arg_0], rbx
0x180005bc5  push    rdi
0x180005bc6  sub     rsp, 30h
0x180005bca  lea     rbx, [rcx+90h]
0x180005bd1  mov     rdi, rcx
0x180005bd4  cmp     qword ptr [rbx], 0
0x180005bd8  jnz     short loc_180005C31
0x180005bda  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180005be1  mov     qword ptr [rbx], 0
0x180005be8  test    rax, rax
0x180005beb  jz      short loc_180005C12
0x180005bed  mov     r9, rbx
0x180005bf0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180005bf7  xor     r8d, r8d
0x180005bfa  mov     rdx, rdi
0x180005bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c02  mov     rbx, [rsp+38h+arg_0]
0x180005c07  test    eax, eax
0x180005c09  setz    al
0x180005c0c  add     rsp, 30h
0x180005c10  pop     rdi
0x180005c11  retn
0x180005c12  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180005c19  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180005c1e  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180005c25  test    rax, rax
0x180005c28  jnz     short loc_180005BED
0x180005c2a  mov     eax, 0C0000139h
0x180005c2f  jmp     short loc_180005C02
0x180005c31  xor     eax, eax
0x180005c33  jmp     short loc_180005C02
```
