# wil_details_IsEnabledFallback

- ea: `0x18000b4a8`
- end: `0x18000b520`
- name: `wil_details_IsEnabledFallback`
- size: `120`
- prototype: `__int64 __fastcall(__int64, int, volatile signed __int32 **)`
- caller_count: `19`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000a634`
- `0x18000a678`
- `0x18000a6bc`
- `0x18000a700`
- `0x18000a744`
- `0x18000a788`
- `0x18000a7cc`
- `0x18000a810`
- `0x18000a854`
- `0x18000a898`
- `0x18000a8dc`
- `0x18000a920`
- `0x18000a964`
- `0x18000a9a8`
- `0x18000a9ec`
- `0x18000aa30`
- `0x18000aa74`
- `0x18000aab8`
- `0x18000aafc`

## callees

- `0x18000afd8`
- `0x18000b1e4`
- `0x18000b2fc`
- `0x18000b4a8`

## pseudocode

```c
__int64 __fastcall wil_details_IsEnabledFallback(__int64 a1, int a2, volatile signed __int32 **a3)
{
  char v5; // bl
  __int64 v6; // rdi

  v5 = a1;
  if ( (a1 & 2) != 0 )
  {
    v6 = (unsigned int)a1;
  }
  else
  {
    v6 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*a3, a1, (__int64)a3);
    v5 = v6;
  }
  if ( a2 )
  {
    wil_details_FeatureReporting_ReportUsageToService((__int64)a3, v6, a2);
    if ( (unsigned int)(a2 - 3) <= 1 )
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v6, a2, (__int64)a3);
  }
  return v5 & 1;
}

```

## disassembly

```asm
0x18000b4a8  push    rbx
0x18000b4aa  push    rsi
0x18000b4ab  push    rdi
0x18000b4ac  push    r14
0x18000b4ae  sub     rsp, 28h
0x18000b4b2  mov     [rsp+48h+arg_0], 0
0x18000b4bb  mov     r14, r8
0x18000b4be  mov     dword ptr [rsp+48h+arg_0], ecx
0x18000b4c2  mov     esi, edx
0x18000b4c4  mov     rbx, rcx
0x18000b4c7  test    cl, 2
0x18000b4ca  jnz     short loc_18000B4E5
0x18000b4cc  mov     rdx, rcx
0x18000b4cf  mov     rcx, [r8]
0x18000b4d2  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x18000b4d7  mov     [rsp+48h+arg_0], rax
0x18000b4dc  mov     rdi, rax
0x18000b4df  mov     ebx, dword ptr [rsp+48h+arg_0]
0x18000b4e3  jmp     short loc_18000B4EA
0x18000b4e5  mov     rdi, [rsp+48h+arg_0]
0x18000b4ea  test    esi, esi
0x18000b4ec  jz      short loc_18000B511
0x18000b4ee  mov     r8d, esi
0x18000b4f1  mov     rdx, rdi
0x18000b4f4  mov     rcx, r14
0x18000b4f7  call    wil_details_FeatureReporting_ReportUsageToService
0x18000b4fc  lea     eax, [rsi-3]
0x18000b4ff  cmp     eax, 1
0x18000b502  ja      short loc_18000B511
0x18000b504  mov     r8, r14
0x18000b507  mov     edx, esi
0x18000b509  mov     rcx, rdi
0x18000b50c  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x18000b511  and     ebx, 1
0x18000b514  mov     eax, ebx
0x18000b516  add     rsp, 28h
0x18000b51a  pop     r14
0x18000b51c  pop     rdi
0x18000b51d  pop     rsi
0x18000b51e  pop     rbx
0x18000b51f  retn
```
