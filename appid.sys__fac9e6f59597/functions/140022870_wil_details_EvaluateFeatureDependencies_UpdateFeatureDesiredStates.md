# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140022870`
- end: `0x1400228fc`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400226e0`

## callees

- `0x140001760`
- `0x140022870`

## pseudocode

```c
__int64 *wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 *result; // rax
  __int64 *v1; // rdx
  int v2; // r9d
  unsigned int v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding((__int64 *)wil_details_featureDescriptors_a);
  v1 = result;
  if ( result )
  {
    v2 = 0;
    do
    {
      v3 = *(_DWORD *)*v1;
      if ( (v3 & 0x200) != 0 )
      {
        if ( (v3 & 0x180) != 0 )
          v4 = (*(_DWORD *)*v1 & 0x180) == 256;
        else
          v4 = *((_BYTE *)v1 + 31) != 0;
        _InterlockedXor((volatile signed __int32 *)*v1, v2 & 0xFFFFFFBF | ((v4 ^ (v3 >> 6) & 1) << 6));
      }
      result = wil_details_FeatureDescriptors_SkipPadding(v1 + 7);
      v1 = result;
    }
    while ( result );
  }
  return result;
}

```

## disassembly

```asm
0x140022870  sub     rsp, 28h
0x140022874  lea     rcx, wil_details_featureDescriptors_a
0x14002287b  mov     [rsp+28h+arg_0], 0
0x140022884  call    wil_details_FeatureDescriptors_SkipPadding
0x140022889  mov     rdx, rax
0x14002288c  test    rax, rax
0x14002288f  jz      short loc_1400228F6
0x140022891  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140022896  mov     rcx, [rdx]
0x140022899  mov     r8d, [rcx]
0x14002289c  bt      r8d, 9
0x1400228a1  jnb     short loc_1400228E5
0x1400228a3  mov     ecx, r8d
0x1400228a6  and     ecx, 180h
0x1400228ac  jnz     short loc_1400228B8
0x1400228ae  xor     eax, eax
0x1400228b0  cmp     [rdx+1Fh], al
0x1400228b3  setnz   al
0x1400228b6  jmp     short loc_1400228C3
0x1400228b8  xor     eax, eax
0x1400228ba  cmp     ecx, 100h
0x1400228c0  setz    al
0x1400228c3  shr     r8d, 6
0x1400228c7  and     r8d, 1
0x1400228cb  xor     r8d, eax
0x1400228ce  mov     eax, r9d
0x1400228d1  shl     r8d, 6
0x1400228d5  and     eax, 0FFFFFFBFh
0x1400228d8  mov     r9d, r8d
0x1400228db  or      r9d, eax
0x1400228de  mov     rax, [rdx]
0x1400228e1  lock xor [rax], r9d
0x1400228e5  lea     rcx, [rdx+38h]
0x1400228e9  call    wil_details_FeatureDescriptors_SkipPadding
0x1400228ee  mov     rdx, rax
0x1400228f1  test    rax, rax
0x1400228f4  jnz     short loc_140022896
0x1400228f6  add     rsp, 28h
0x1400228fa  retn
```
