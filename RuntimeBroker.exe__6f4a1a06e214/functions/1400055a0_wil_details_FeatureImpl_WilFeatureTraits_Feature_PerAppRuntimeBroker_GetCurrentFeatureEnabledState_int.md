# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1400055a0`
- end: `0x14000562e`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PerAppRuntimeBroker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000548c`

## callees

- `0x1400055a0`
- `0x140010010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // r8d
  int v5; // edx
  int v6; // eax
  _QWORD *result; // rax

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(8482243, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = 64;
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v6 = 0;
    if ( (v4 & 0xFFFFFF3F) == 2 )
      v6 = 64;
    v5 = v6;
  }
  result = a2;
  *(_DWORD *)a2 = v5 | (8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))))) | 1;
  return result;
}

```

## disassembly

```asm
0x1400055a0  push    rbx
0x1400055a2  sub     rsp, 20h
0x1400055a6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400055ad  mov     rbx, rdx
0x1400055b0  test    rax, rax
0x1400055b3  jz      short loc_1400055C9
0x1400055b5  mov     edx, 3
0x1400055ba  mov     ecx, 816DC3h
0x1400055bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055c4  mov     r8d, eax
0x1400055c7  jmp     short loc_1400055D8
0x1400055c9  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400055d0  test    rax, rax
0x1400055d3  jnz     short loc_1400055B5
0x1400055d5  xor     r8d, r8d
0x1400055d8  mov     r9d, r8d
0x1400055db  mov     qword ptr [rbx], 0
0x1400055e2  and     r9d, 0FFFFFF3Fh
0x1400055e9  mov     eax, r8d
0x1400055ec  and     r8d, 80h
0x1400055f3  mov     ecx, r9d
0x1400055f6  and     ecx, 3
0x1400055f9  mov     edx, 40h ; '@'
0x1400055fe  shl     ecx, 2
0x140005601  and     eax, edx
0x140005603  or      ecx, eax
0x140005605  shl     ecx, 2
0x140005608  or      ecx, r8d
0x14000560b  shl     ecx, 3
0x14000560e  test    r9d, r9d
0x140005611  jz      short loc_14000561E
0x140005613  xor     eax, eax
0x140005615  cmp     r9d, 2
0x140005619  cmovz   eax, edx
0x14000561c  mov     edx, eax
0x14000561e  or      ecx, edx
0x140005620  mov     rax, rbx
0x140005623  or      ecx, 1
0x140005626  mov     [rbx], ecx
0x140005628  add     rsp, 20h
0x14000562c  pop     rbx
0x14000562d  retn
```
