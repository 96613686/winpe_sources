# wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates

- ea: `0x14002157c`
- end: `0x140021608`
- name: `wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400213ec`

## callees

- `0x140011224`
- `0x14002157c`

## pseudocode

```c
__int64 *wil_details_EvaluateFeatureDependencies_UpdateFeatureDesiredStates()
{
  __int64 *result; // rax
  __int64 *v1; // rdx
  int v2; // r9d
  unsigned int v3; // r8d
  BOOL v4; // eax

  result = wil_details_FeatureDescriptors_SkipPadding(wil_details_featureDescriptors_a);
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
0x14002157c  sub     rsp, 28h
0x140021580  lea     rcx, wil_details_featureDescriptors_a
0x140021587  mov     [rsp+28h+arg_0], 0
0x140021590  call    wil_details_FeatureDescriptors_SkipPadding
0x140021595  mov     rdx, rax
0x140021598  test    rax, rax
0x14002159b  jz      short loc_140021602
0x14002159d  mov     r9d, dword ptr [rsp+28h+arg_0]
0x1400215a2  mov     rcx, [rdx]
0x1400215a5  mov     r8d, [rcx]
0x1400215a8  bt      r8d, 9
0x1400215ad  jnb     short loc_1400215F1
0x1400215af  mov     ecx, r8d
0x1400215b2  and     ecx, 180h
0x1400215b8  jnz     short loc_1400215C4
0x1400215ba  xor     eax, eax
0x1400215bc  cmp     [rdx+1Fh], al
0x1400215bf  setnz   al
0x1400215c2  jmp     short loc_1400215CF
0x1400215c4  xor     eax, eax
0x1400215c6  cmp     ecx, 100h
0x1400215cc  setz    al
0x1400215cf  shr     r8d, 6
0x1400215d3  and     r8d, 1
0x1400215d7  xor     r8d, eax
0x1400215da  mov     eax, r9d
0x1400215dd  shl     r8d, 6
0x1400215e1  and     eax, 0FFFFFFBFh
0x1400215e4  mov     r9d, r8d
0x1400215e7  or      r9d, eax
0x1400215ea  mov     rax, [rdx]
0x1400215ed  lock xor [rax], r9d
0x1400215f1  lea     rcx, [rdx+38h]
0x1400215f5  call    wil_details_FeatureDescriptors_SkipPadding
0x1400215fa  mov     rdx, rax
0x1400215fd  test    rax, rax
0x140021600  jnz     short loc_1400215A2
0x140021602  add     rsp, 28h
0x140021606  retn
```
