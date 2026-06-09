# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180027740`
- end: `0x1800277fd`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180027614`

## callees

- `0x180003520`
- `0x180023814`
- `0x180023940`
- `0x180027740`
- `0x18002a010`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebx
  __int64 v6; // rax
  _BYTE v8[24]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v9; // [rsp+48h] [rbp-40h] BYREF
  __int64 v10; // [rsp+58h] [rbp-30h]

  v3 = a2;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v8,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2));
  v9 = *(_OWORD *)v6;
  v10 = *(_QWORD *)(v6 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(*(unsigned int *)(a1 + 24), a3, 1, *(_QWORD *)(a1 + 8), &v9);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
    wil_RtlStagingConfig_RecordFeatureUsage(*(_DWORD *)(a1 + 24), a3, (v3 >> 11) & 1);
  return (_DWORD)v10 == 0;
}

```

## disassembly

```asm
0x180027740  mov     [rsp+arg_18], rbx
0x180027745  push    rbp
0x180027746  push    rsi
0x180027747  push    rdi
0x180027748  sub     rsp, 70h
0x18002774c  mov     rax, cs:__security_cookie
0x180027753  xor     rax, rsp
0x180027756  mov     [rsp+88h+var_28], rax
0x18002775b  mov     r9, rdx
0x18002775e  mov     rbx, rdx
0x180027761  mov     rdx, [rcx+8]
0x180027765  mov     rbp, rcx
0x180027768  shr     r9, 20h
0x18002776c  lea     rcx, [rsp+88h+var_58]
0x180027771  mov     esi, r8d
0x180027774  call    wil_details_FeatureReporting_RecordUsageInCache
0x180027779  movups  xmm1, xmmword ptr [rax]
0x18002777c  movups  [rsp+88h+var_40], xmm1
0x180027781  movsd   xmm0, qword ptr [rax+10h]
0x180027786  mov     rax, cs:g_wil_details_recordFeatureUsage
0x18002778d  movsd   [rsp+88h+var_30], xmm0
0x180027793  test    rax, rax
0x180027796  jz      short loc_1800277B6
0x180027798  mov     r9, [rbp+8]
0x18002779c  lea     rcx, [rsp+88h+var_40]
0x1800277a1  mov     [rsp+88h+var_68], rcx
0x1800277a6  mov     r8d, 1
0x1800277ac  mov     ecx, [rbp+18h]
0x1800277af  mov     edx, esi
0x1800277b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277b6  bt      ebx, 0Ah
0x1800277ba  jnb     short loc_1800277D7
0x1800277bc  cmp     esi, 0FEh
0x1800277c2  jz      short loc_1800277D7
0x1800277c4  mov     ecx, [rbp+18h]
0x1800277c7  mov     edx, esi
0x1800277c9  shr     ebx, 0Bh
0x1800277cc  and     ebx, 1
0x1800277cf  mov     r8d, ebx
0x1800277d2  call    wil_RtlStagingConfig_RecordFeatureUsage
0x1800277d7  xor     eax, eax
0x1800277d9  cmp     dword ptr [rsp+88h+var_30], eax
0x1800277dd  setz    al
0x1800277e0  mov     rcx, [rsp+88h+var_28]
0x1800277e5  xor     rcx, rsp; StackCookie
0x1800277e8  call    __security_check_cookie
0x1800277ed  mov     rbx, [rsp+88h+arg_18]
0x1800277f5  add     rsp, 70h
0x1800277f9  pop     rdi
0x1800277fa  pop     rsi
0x1800277fb  pop     rbp
0x1800277fc  retn
```
