# wil_details_IsEnabledFallback

- ea: `0x140003560`
- end: `0x1400035d2`
- name: `wil_details_IsEnabledFallback`
- size: `114`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140003520`
- `0x140003540`
- `0x14000b31c`
- `0x140012b4c`

## callees

- `0x140003560`
- `0x140004910`
- `0x140004a78`
- `0x140004b90`

## pseudocode

```c
__int64 __fastcall wil_details_IsEnabledFallback(__int64 a1, unsigned int a2, volatile signed __int32 **a3)
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
    if ( a2 - 3 <= 1 )
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v6, a2, (__int64)a3);
  }
  return v5 & 1;
}

```

## disassembly

```asm
0x140003560  push    rbx
0x140003562  push    rsi
0x140003563  push    rdi
0x140003564  push    r14
0x140003566  sub     rsp, 28h
0x14000356a  mov     [rsp+48h+arg_0], 0
0x140003573  mov     r14, r8
0x140003576  mov     dword ptr [rsp+48h+arg_0], ecx
0x14000357a  mov     esi, edx
0x14000357c  mov     rbx, rcx
0x14000357f  test    cl, 2
0x140003582  jnz     short loc_140003596
0x140003584  mov     rdx, rcx
0x140003587  mov     rcx, [r8]
0x14000358a  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x14000358f  mov     rdi, rax
0x140003592  mov     ebx, eax
0x140003594  jmp     short loc_14000359B
0x140003596  mov     rdi, [rsp+48h+arg_0]
0x14000359b  test    esi, esi
0x14000359d  jz      short loc_1400035C2
0x14000359f  mov     r8d, esi
0x1400035a2  mov     rdx, rdi
0x1400035a5  mov     rcx, r14
0x1400035a8  call    wil_details_FeatureReporting_ReportUsageToService
0x1400035ad  lea     eax, [rsi-3]
0x1400035b0  cmp     eax, 1
0x1400035b3  ja      short loc_1400035C2
0x1400035b5  mov     r8, r14
0x1400035b8  mov     edx, esi
0x1400035ba  mov     rcx, rdi
0x1400035bd  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400035c2  and     ebx, 1
0x1400035c5  mov     eax, ebx
0x1400035c7  add     rsp, 28h
0x1400035cb  pop     r14
0x1400035cd  pop     rdi
0x1400035ce  pop     rsi
0x1400035cf  pop     rbx
0x1400035d0  retn
```
