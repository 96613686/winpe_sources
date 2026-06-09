# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140018364`
- end: `0x140018397`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400183a0`

## callees

- `0x140018364`
- `0x1400183a0`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2)
{
  if ( (*a1 & 0x200) != 0 )
    return wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(a1, *a1, a2);
  else
    return *(unsigned int *)a1;
}

```

## disassembly

```asm
0x140018364  sub     rsp, 28h
0x140018368  mov     eax, [rcx]
0x14001836a  mov     [rsp+28h+arg_0], 0
0x140018373  mov     dword ptr [rsp+28h+arg_0], eax
0x140018377  bt      eax, 9
0x14001837b  jb      short loc_140018384
0x14001837d  mov     rax, [rsp+28h+arg_0]
0x140018382  jmp     short loc_140018391
0x140018384  mov     r8, rdx
0x140018387  mov     rdx, [rsp+28h+arg_0]
0x14001838c  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140018391  add     rsp, 28h
0x140018395  retn
```
