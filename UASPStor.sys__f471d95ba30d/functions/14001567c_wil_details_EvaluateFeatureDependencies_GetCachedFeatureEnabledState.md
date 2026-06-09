# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14001567c`
- end: `0x1400156af`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400156b8`

## callees

- `0x14001567c`
- `0x1400156b8`

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
0x14001567c  sub     rsp, 28h
0x140015680  mov     eax, [rcx]
0x140015682  mov     [rsp+28h+arg_0], 0
0x14001568b  mov     dword ptr [rsp+28h+arg_0], eax
0x14001568f  bt      eax, 9
0x140015693  jb      short loc_14001569C
0x140015695  mov     rax, [rsp+28h+arg_0]
0x14001569a  jmp     short loc_1400156A9
0x14001569c  mov     r8, rdx
0x14001569f  mov     rdx, [rsp+28h+arg_0]
0x1400156a4  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x1400156a9  add     rsp, 28h
0x1400156ad  retn
```
