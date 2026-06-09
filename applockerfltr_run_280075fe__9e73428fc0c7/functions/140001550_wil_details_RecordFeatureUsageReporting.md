# wil_details_RecordFeatureUsageReporting

- ea: `0x140001550`
- end: `0x1400015d7`
- name: `wil_details_RecordFeatureUsageReporting`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001550`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400015bf`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400015bf`
- `ntoskrnl!RtlArmFeatureUsageProviderFlushNotification` at `0x14000158d`
- `ntoskrnl!RtlArmFeatureUsageProviderFlushNotification` at `0x14000158d`

## pseudocode

```c
void __fastcall wil_details_RecordFeatureUsageReporting(int a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v6; // [rsp+20h] [rbp-18h] BYREF

  v6 = 0;
  if ( *(_DWORD *)a5
    && !_InterlockedExchange(&g_wil_details_featureUsageCached, 1)
    && g_wil_details_featureUsageProvider )
  {
    RtlArmFeatureUsageProviderFlushNotification(g_wil_details_featureUsageProvider, 1);
  }
  if ( *(_DWORD *)(a5 + 4) )
  {
    WORD2(v6) = *(_WORD *)(a5 + 8);
    HIWORD(v6) = *(_WORD *)(a5 + 4);
    LODWORD(v6) = a1;
    RtlRecordFeatureUsage(&v6);
  }
}

```

## disassembly

```asm
0x140001550  mov     [rsp+arg_0], rbx
0x140001555  push    rdi
0x140001556  sub     rsp, 30h
0x14000155a  mov     rbx, [rsp+38h+arg_20]
0x14000155f  mov     edi, ecx
0x140001561  mov     [rsp+38h+var_18], 0
0x14000156a  cmp     dword ptr [rbx], 0
0x14000156d  jz      short loc_140001599
0x14000156f  mov     eax, 1
0x140001574  xchg    eax, cs:g_wil_details_featureUsageCached
0x14000157a  test    eax, eax
0x14000157c  jnz     short loc_140001599
0x14000157e  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140001585  test    rcx, rcx
0x140001588  jz      short loc_140001599
0x14000158a  lea     edx, [rax+1]
0x14000158d  call    cs:__imp_RtlArmFeatureUsageProviderFlushNotification
0x140001594  nop     dword ptr [rax+rax+00h]
0x140001599  cmp     dword ptr [rbx+4], 0
0x14000159d  jbe     short loc_1400015CB
0x14000159f  movzx   eax, word ptr [rbx+8]
0x1400015a3  lea     rcx, [rsp+38h+var_18]
0x1400015a8  mov     word ptr [rsp+38h+var_18+4], ax
0x1400015ad  mov     edx, 1
0x1400015b2  movzx   eax, word ptr [rbx+4]
0x1400015b6  mov     word ptr [rsp+38h+var_18+6], ax
0x1400015bb  mov     dword ptr [rsp+38h+var_18], edi
0x1400015bf  call    cs:__imp_RtlRecordFeatureUsage
0x1400015c6  nop     dword ptr [rax+rax+00h]
0x1400015cb  mov     rbx, [rsp+38h+arg_0]
0x1400015d0  add     rsp, 30h
0x1400015d4  pop     rdi
0x1400015d5  retn
```
