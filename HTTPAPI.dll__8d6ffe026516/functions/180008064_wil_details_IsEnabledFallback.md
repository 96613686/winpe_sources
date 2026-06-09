# wil_details_IsEnabledFallback

- ea: `0x180008064`
- end: `0x1800080dc`
- name: `wil_details_IsEnabledFallback`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800074b4`
- `0x1800074f8`

## callees

- `0x180007c08`
- `0x180007da0`
- `0x180007eb8`
- `0x180008064`

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
0x180008064  push    rbx
0x180008066  push    rsi
0x180008067  push    rdi
0x180008068  push    r14
0x18000806a  sub     rsp, 28h
0x18000806e  mov     [rsp+48h+arg_0], 0
0x180008077  mov     r14, r8
0x18000807a  mov     dword ptr [rsp+48h+arg_0], ecx
0x18000807e  mov     esi, edx
0x180008080  mov     rbx, rcx
0x180008083  test    cl, 2
0x180008086  jnz     short loc_1800080A1
0x180008088  mov     rdx, rcx
0x18000808b  mov     rcx, [r8]
0x18000808e  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180008093  mov     [rsp+48h+arg_0], rax
0x180008098  mov     rdi, rax
0x18000809b  mov     ebx, dword ptr [rsp+48h+arg_0]
0x18000809f  jmp     short loc_1800080A6
0x1800080a1  mov     rdi, [rsp+48h+arg_0]
0x1800080a6  test    esi, esi
0x1800080a8  jz      short loc_1800080CD
0x1800080aa  mov     r8d, esi
0x1800080ad  mov     rdx, rdi
0x1800080b0  mov     rcx, r14
0x1800080b3  call    wil_details_FeatureReporting_ReportUsageToService
0x1800080b8  lea     eax, [rsi-3]
0x1800080bb  cmp     eax, 1
0x1800080be  ja      short loc_1800080CD
0x1800080c0  mov     r8, r14
0x1800080c3  mov     edx, esi
0x1800080c5  mov     rcx, rdi
0x1800080c8  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1800080cd  and     ebx, 1
0x1800080d0  mov     eax, ebx
0x1800080d2  add     rsp, 28h
0x1800080d6  pop     r14
0x1800080d8  pop     rdi
0x1800080d9  pop     rsi
0x1800080da  pop     rbx
0x1800080db  retn
```
