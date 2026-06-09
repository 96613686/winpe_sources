# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x14001ead4`
- end: `0x14001eb60`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14001e944`

## callees

- `0x140004784`
- `0x14001ead4`

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
0x14001ead4  sub     rsp, 28h
0x14001ead8  lea     rcx, wil_details_featureDescriptors_a
0x14001eadf  mov     [rsp+28h+arg_0], 0
0x14001eae8  call    wil_details_FeatureDescriptors_SkipPadding
0x14001eaed  mov     rdx, rax
0x14001eaf0  test    rax, rax
0x14001eaf3  jz      short loc_14001EB5A
0x14001eaf5  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14001eafa  mov     rcx, [rdx]
0x14001eafd  mov     r8d, [rcx]
0x14001eb00  bt      r8d, 9
0x14001eb05  jnb     short loc_14001EB49
0x14001eb07  mov     ecx, r8d
0x14001eb0a  and     ecx, 180h
0x14001eb10  jnz     short loc_14001EB1C
0x14001eb12  xor     eax, eax
0x14001eb14  cmp     [rdx+1Fh], al
0x14001eb17  setnz   al
0x14001eb1a  jmp     short loc_14001EB27
0x14001eb1c  xor     eax, eax
0x14001eb1e  cmp     ecx, 100h
0x14001eb24  setz    al
0x14001eb27  shr     r8d, 6
0x14001eb2b  and     r8d, 1
0x14001eb2f  xor     r8d, eax
0x14001eb32  mov     eax, r9d
0x14001eb35  shl     r8d, 6
0x14001eb39  and     eax, 0FFFFFFBFh
0x14001eb3c  mov     r9d, r8d
0x14001eb3f  or      r9d, eax
0x14001eb42  mov     rax, [rdx]
0x14001eb45  lock xor [rax], r9d
0x14001eb49  lea     rcx, [rdx+38h]
0x14001eb4d  call    wil_details_FeatureDescriptors_SkipPadding
0x14001eb52  mov     rdx, rax
0x14001eb55  test    rax, rax
0x14001eb58  jnz     short loc_14001EAFA
0x14001eb5a  add     rsp, 28h
0x14001eb5e  retn
```
