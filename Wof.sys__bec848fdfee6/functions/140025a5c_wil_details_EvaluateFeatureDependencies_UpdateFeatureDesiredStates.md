# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x140025a5c`
- end: `0x140025ae8`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400258cc`

## callees

- `0x14000f4cc`
- `0x140025a5c`

## pseudocode

```c
__int64 wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 result; // rax
  volatile signed __int32 **v1; // rdx
  int v2; // r9d
  volatile unsigned __int32 v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding(&wil_details_featureDescriptors_a);
  v1 = (volatile signed __int32 **)result;
  if ( result )
  {
    v2 = 0;
    do
    {
      v3 = **v1;
      if ( (v3 & 0x200) != 0 )
      {
        if ( (v3 & 0x180) != 0 )
          v4 = (**v1 & 0x180) == 256;
        else
          v4 = *((_BYTE *)v1 + 31) != 0;
        _InterlockedXor(*v1, v2 & 0xFFFFFFBF | ((v4 ^ (v3 >> 6) & 1) << 6));
      }
      result = wil_details_FeatureDescriptors_SkipPadding(v1 + 7);
      v1 = (volatile signed __int32 **)result;
    }
    while ( result );
  }
  return result;
}

```

## disassembly

```asm
0x140025a5c  sub     rsp, 28h
0x140025a60  lea     rcx, wil_details_featureDescriptors_a
0x140025a67  mov     [rsp+28h+arg_0], 0
0x140025a70  call    wil_details_FeatureDescriptors_SkipPadding
0x140025a75  mov     rdx, rax
0x140025a78  test    rax, rax
0x140025a7b  jz      short loc_140025AE2
0x140025a7d  mov     r9d, dword ptr [rsp+28h+arg_0]
0x140025a82  mov     rcx, [rdx]
0x140025a85  mov     r8d, [rcx]
0x140025a88  bt      r8d, 9
0x140025a8d  jnb     short loc_140025AD1
0x140025a8f  mov     ecx, r8d
0x140025a92  and     ecx, 180h
0x140025a98  jnz     short loc_140025AA4
0x140025a9a  xor     eax, eax
0x140025a9c  cmp     [rdx+1Fh], al
0x140025a9f  setnz   al
0x140025aa2  jmp     short loc_140025AAF
0x140025aa4  xor     eax, eax
0x140025aa6  cmp     ecx, 100h
0x140025aac  setz    al
0x140025aaf  shr     r8d, 6
0x140025ab3  and     r8d, 1
0x140025ab7  xor     r8d, eax
0x140025aba  mov     eax, r9d
0x140025abd  shl     r8d, 6
0x140025ac1  and     eax, 0FFFFFFBFh
0x140025ac4  mov     r9d, r8d
0x140025ac7  or      r9d, eax
0x140025aca  mov     rax, [rdx]
0x140025acd  lock xor [rax], r9d
0x140025ad1  lea     rcx, [rdx+38h]
0x140025ad5  call    wil_details_FeatureDescriptors_SkipPadding
0x140025ada  mov     rdx, rax
0x140025add  test    rax, rax
0x140025ae0  jnz     short loc_140025A82
0x140025ae2  add     rsp, 28h
0x140025ae6  retn
```
