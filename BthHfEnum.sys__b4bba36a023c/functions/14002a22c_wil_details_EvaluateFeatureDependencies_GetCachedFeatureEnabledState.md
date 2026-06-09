# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14002a22c`
- end: `0x14002a25f`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002a174`
- `0x14002a268`

## callees

- `0x14002a22c`
- `0x14002a268`

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
0x14002a22c  sub     rsp, 28h
0x14002a230  mov     eax, [rcx]
0x14002a232  mov     [rsp+28h+arg_0], 0
0x14002a23b  mov     dword ptr [rsp+28h+arg_0], eax
0x14002a23f  bt      eax, 9
0x14002a243  jb      short loc_14002A24C
0x14002a245  mov     rax, [rsp+28h+arg_0]
0x14002a24a  jmp     short loc_14002A259
0x14002a24c  mov     r8, rdx
0x14002a24f  mov     rdx, [rsp+28h+arg_0]
0x14002a254  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14002a259  add     rsp, 28h
0x14002a25d  retn
```
