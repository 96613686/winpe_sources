# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x14000b724`
- end: `0x14000b7b0`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000b594`

## callees

- `0x1400018fc`
- `0x14000b724`

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
0x14000b724  sub     rsp, 28h
0x14000b728  lea     rcx, wil_details_featureDescriptors_a
0x14000b72f  mov     [rsp+28h+arg_0], 0
0x14000b738  call    wil_details_FeatureDescriptors_SkipPadding
0x14000b73d  mov     rdx, rax
0x14000b740  test    rax, rax
0x14000b743  jz      short loc_14000B7AA
0x14000b745  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14000b74a  mov     rcx, [rdx]
0x14000b74d  mov     r8d, [rcx]
0x14000b750  bt      r8d, 9
0x14000b755  jnb     short loc_14000B799
0x14000b757  mov     ecx, r8d
0x14000b75a  and     ecx, 180h
0x14000b760  jnz     short loc_14000B76C
0x14000b762  xor     eax, eax
0x14000b764  cmp     [rdx+1Fh], al
0x14000b767  setnz   al
0x14000b76a  jmp     short loc_14000B777
0x14000b76c  xor     eax, eax
0x14000b76e  cmp     ecx, 100h
0x14000b774  setz    al
0x14000b777  shr     r8d, 6
0x14000b77b  and     r8d, 1
0x14000b77f  xor     r8d, eax
0x14000b782  mov     eax, r9d
0x14000b785  shl     r8d, 6
0x14000b789  and     eax, 0FFFFFFBFh
0x14000b78c  mov     r9d, r8d
0x14000b78f  or      r9d, eax
0x14000b792  mov     rax, [rdx]
0x14000b795  lock xor [rax], r9d
0x14000b799  lea     rcx, [rdx+38h]
0x14000b79d  call    wil_details_FeatureDescriptors_SkipPadding
0x14000b7a2  mov     rdx, rax
0x14000b7a5  test    rax, rax
0x14000b7a8  jnz     short loc_14000B74A
0x14000b7aa  add     rsp, 28h
0x14000b7ae  retn
```
