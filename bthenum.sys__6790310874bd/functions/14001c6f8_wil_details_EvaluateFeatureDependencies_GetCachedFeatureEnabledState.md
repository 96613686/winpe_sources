# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14001c6f8`
- end: `0x14001c72b`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001c734`

## callees

- `0x14001c6f8`
- `0x14001c734`

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
0x14001c6f8  sub     rsp, 28h
0x14001c6fc  mov     eax, [rcx]
0x14001c6fe  mov     [rsp+28h+arg_0], 0
0x14001c707  mov     dword ptr [rsp+28h+arg_0], eax
0x14001c70b  bt      eax, 9
0x14001c70f  jb      short loc_14001C718
0x14001c711  mov     rax, [rsp+28h+arg_0]
0x14001c716  jmp     short loc_14001C725
0x14001c718  mov     r8, rdx
0x14001c71b  mov     rdx, [rsp+28h+arg_0]
0x14001c720  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14001c725  add     rsp, 28h
0x14001c729  retn
```
