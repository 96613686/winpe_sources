# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14002142c`
- end: `0x14002145f`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400213ec`
- `0x140021468`

## callees

- `0x14002142c`
- `0x140021468`

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
0x14002142c  sub     rsp, 28h
0x140021430  mov     eax, [rcx]
0x140021432  mov     [rsp+28h+arg_0], 0
0x14002143b  mov     dword ptr [rsp+28h+arg_0], eax
0x14002143f  bt      eax, 9
0x140021443  jb      short loc_14002144C
0x140021445  mov     rax, [rsp+28h+arg_0]
0x14002144a  jmp     short loc_140021459
0x14002144c  mov     r8, rdx
0x14002144f  mov     rdx, [rsp+28h+arg_0]
0x140021454  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x140021459  add     rsp, 28h
0x14002145d  retn
```
