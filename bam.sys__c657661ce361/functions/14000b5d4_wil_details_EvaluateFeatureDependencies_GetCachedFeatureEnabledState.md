# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14000b5d4`
- end: `0x14000b607`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b594`
- `0x14000b610`

## callees

- `0x14000b5d4`
- `0x14000b610`

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
0x14000b5d4  sub     rsp, 28h
0x14000b5d8  mov     eax, [rcx]
0x14000b5da  mov     [rsp+28h+arg_0], 0
0x14000b5e3  mov     dword ptr [rsp+28h+arg_0], eax
0x14000b5e7  bt      eax, 9
0x14000b5eb  jb      short loc_14000B5F4
0x14000b5ed  mov     rax, [rsp+28h+arg_0]
0x14000b5f2  jmp     short loc_14000B601
0x14000b5f4  mov     r8, rdx
0x14000b5f7  mov     rdx, [rsp+28h+arg_0]
0x14000b5fc  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14000b601  add     rsp, 28h
0x14000b605  retn
```
