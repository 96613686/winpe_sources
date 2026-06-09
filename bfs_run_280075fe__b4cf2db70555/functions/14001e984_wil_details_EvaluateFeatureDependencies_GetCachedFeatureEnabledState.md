# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14001e984`
- end: `0x14001e9b7`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001e944`
- `0x14001e9c0`

## callees

- `0x14001e984`
- `0x14001e9c0`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(_DWORD *a1, __int64 a2)
{
  __int64 result; // rax

  LODWORD(result) = *a1;
  if ( (*a1 & 0x200) != 0 )
    return wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(a1, (unsigned int)result, a2);
  else
    return (unsigned int)result;
}

```

## disassembly

```asm
0x14001e984  sub     rsp, 28h
0x14001e988  mov     eax, [rcx]
0x14001e98a  mov     [rsp+28h+arg_0], 0
0x14001e993  mov     dword ptr [rsp+28h+arg_0], eax
0x14001e997  bt      eax, 9
0x14001e99b  jb      short loc_14001E9A4
0x14001e99d  mov     rax, [rsp+28h+arg_0]
0x14001e9a2  jmp     short loc_14001E9B1
0x14001e9a4  mov     r8, rdx
0x14001e9a7  mov     rdx, [rsp+28h+arg_0]
0x14001e9ac  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14001e9b1  add     rsp, 28h
0x14001e9b5  retn
```
