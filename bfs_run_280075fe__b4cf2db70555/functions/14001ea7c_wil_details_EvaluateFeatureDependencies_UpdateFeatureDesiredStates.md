# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x14001ea7c`
- end: `0x14001eb08`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001e944`

## callees

- `0x1400045b4`
- `0x14001ea7c`

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
0x14001ea7c  sub     rsp, 28h
0x14001ea80  lea     rcx, wil_details_featureDescriptors_a
0x14001ea87  mov     [rsp+28h+arg_0], 0
0x14001ea90  call    wil_details_FeatureDescriptors_SkipPadding
0x14001ea95  mov     rdx, rax
0x14001ea98  test    rax, rax
0x14001ea9b  jz      short loc_14001EB02
0x14001ea9d  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14001eaa2  mov     rcx, [rdx]
0x14001eaa5  mov     r8d, [rcx]
0x14001eaa8  bt      r8d, 9
0x14001eaad  jnb     short loc_14001EAF1
0x14001eaaf  mov     ecx, r8d
0x14001eab2  and     ecx, 180h
0x14001eab8  jnz     short loc_14001EAC4
0x14001eaba  xor     eax, eax
0x14001eabc  cmp     [rdx+1Fh], al
0x14001eabf  setnz   al
0x14001eac2  jmp     short loc_14001EACF
0x14001eac4  xor     eax, eax
0x14001eac6  cmp     ecx, 100h
0x14001eacc  setz    al
0x14001eacf  shr     r8d, 6
0x14001ead3  and     r8d, 1
0x14001ead7  xor     r8d, eax
0x14001eada  mov     eax, r9d
0x14001eadd  shl     r8d, 6
0x14001eae1  and     eax, 0FFFFFFBFh
0x14001eae4  mov     r9d, r8d
0x14001eae7  or      r9d, eax
0x14001eaea  mov     rax, [rdx]
0x14001eaed  lock xor [rax], r9d
0x14001eaf1  lea     rcx, [rdx+38h]
0x14001eaf5  call    wil_details_FeatureDescriptors_SkipPadding
0x14001eafa  mov     rdx, rax
0x14001eafd  test    rax, rax
0x14001eb00  jnz     short loc_14001EAA2
0x14001eb02  add     rsp, 28h
0x14001eb06  retn
```
