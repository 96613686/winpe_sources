# wil_details_IsEnabledFallback

- ea: `0x140003690`
- end: `0x140003702`
- name: `wil_details_IsEnabledFallback`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140003650`
- `0x140003670`
- `0x14000b4ac`

## callees

- `0x140003690`
- `0x140004ae0`
- `0x140004c48`
- `0x140004d60`

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
0x140003690  push    rbx
0x140003692  push    rsi
0x140003693  push    rdi
0x140003694  push    r14
0x140003696  sub     rsp, 28h
0x14000369a  mov     [rsp+48h+arg_0], 0
0x1400036a3  mov     r14, r8
0x1400036a6  mov     dword ptr [rsp+48h+arg_0], ecx
0x1400036aa  mov     esi, edx
0x1400036ac  mov     rbx, rcx
0x1400036af  test    cl, 2
0x1400036b2  jnz     short loc_1400036C6
0x1400036b4  mov     rdx, rcx
0x1400036b7  mov     rcx, [r8]
0x1400036ba  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x1400036bf  mov     rdi, rax
0x1400036c2  mov     ebx, eax
0x1400036c4  jmp     short loc_1400036CB
0x1400036c6  mov     rdi, [rsp+48h+arg_0]
0x1400036cb  test    esi, esi
0x1400036cd  jz      short loc_1400036F2
0x1400036cf  mov     r8d, esi
0x1400036d2  mov     rdx, rdi
0x1400036d5  mov     rcx, r14
0x1400036d8  call    wil_details_FeatureReporting_ReportUsageToService
0x1400036dd  lea     eax, [rsi-3]
0x1400036e0  cmp     eax, 1
0x1400036e3  ja      short loc_1400036F2
0x1400036e5  mov     r8, r14
0x1400036e8  mov     edx, esi
0x1400036ea  mov     rcx, rdi
0x1400036ed  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400036f2  and     ebx, 1
0x1400036f5  mov     eax, ebx
0x1400036f7  add     rsp, 28h
0x1400036fb  pop     r14
0x1400036fd  pop     rdi
0x1400036fe  pop     rsi
0x1400036ff  pop     rbx
0x140003700  retn
```
