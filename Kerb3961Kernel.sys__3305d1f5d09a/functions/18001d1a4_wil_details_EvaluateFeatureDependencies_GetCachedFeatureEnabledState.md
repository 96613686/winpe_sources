# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x18001d1a4`
- end: `0x18001d1d7`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d1e0`

## callees

- `0x18001d1a4`
- `0x18001d1e0`

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
0x18001d1a4  sub     rsp, 28h
0x18001d1a8  mov     eax, [rcx]
0x18001d1aa  mov     [rsp+28h+arg_0], 0
0x18001d1b3  mov     dword ptr [rsp+28h+arg_0], eax
0x18001d1b7  bt      eax, 9
0x18001d1bb  jb      short loc_18001D1C4
0x18001d1bd  mov     rax, [rsp+28h+arg_0]
0x18001d1c2  jmp     short loc_18001D1D1
0x18001d1c4  mov     r8, rdx
0x18001d1c7  mov     rdx, [rsp+28h+arg_0]
0x18001d1cc  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x18001d1d1  add     rsp, 28h
0x18001d1d5  retn
```
