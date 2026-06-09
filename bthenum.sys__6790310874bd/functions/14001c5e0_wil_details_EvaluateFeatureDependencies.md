# wil_details_EvaluateFeatureDependencies

- ea: `0x14001c5e0`
- end: `0x14001c6ef`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001c8d0`
- `0x14002059c`

## callees

- `0x14001c5e0`
- `0x14001c734`

## pseudocode

```c
void wil_details_EvaluateFeatureDependencies()
{
  volatile signed __int32 **v0; // rbx
  volatile signed __int32 **v1; // rcx
  unsigned int v2; // r9d
  volatile unsigned __int32 v3; // edx
  BOOL v4; // eax
  unsigned __int32 v5; // [rsp+30h] [rbp+8h]

  v0 = (volatile signed __int32 **)wil_details_featureDescriptors_a;
  v1 = (volatile signed __int32 **)wil_details_featureDescriptors_a;
  if ( wil_details_featureDescriptors_a < (__int64 **)wil_details_featureDescriptors_z )
  {
    while ( !*v1 )
    {
      if ( ++v1 >= (volatile signed __int32 **)wil_details_featureDescriptors_z )
        goto LABEL_21;
    }
    if ( !v1 )
      goto LABEL_21;
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
        v2 = v2 & 0xFFFFFFBF | ((v4 ^ (v3 >> 6) & 1) << 6);
        _InterlockedXor(*v1, v2);
      }
      for ( v1 += 7; ; ++v1 )
      {
        if ( v1 >= (volatile signed __int32 **)wil_details_featureDescriptors_z )
          goto LABEL_21;
        if ( *v1 )
          break;
      }
    }
    while ( v1 );
LABEL_21:
    while ( v0 < (volatile signed __int32 **)wil_details_featureDescriptors_z )
    {
      if ( *v0 )
      {
LABEL_30:
        if ( v0 )
        {
          v5 = **v0;
          if ( (v5 & 0x200) != 0 )
            wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(*v0, v5, (__int64)v0);
          for ( v0 += 7; v0 < (volatile signed __int32 **)wil_details_featureDescriptors_z; ++v0 )
          {
            if ( *v0 )
              goto LABEL_30;
          }
        }
        return;
      }
      ++v0;
    }
  }
}

```

## disassembly

```asm
0x14001c5e0  mov     [rsp+arg_8], rbx
0x14001c5e5  push    rsi
0x14001c5e6  sub     rsp, 20h
0x14001c5ea  lea     rbx, wil_details_featureDescriptors_a
0x14001c5f1  mov     [rsp+28h+arg_0], 0
0x14001c5fa  lea     rsi, wil_details_featureDescriptors_z
0x14001c601  mov     rcx, rbx
0x14001c604  cmp     rbx, rsi
0x14001c607  jnb     loc_14001C6E3
0x14001c60d  cmp     qword ptr [rcx], 0
0x14001c611  jnz     short loc_14001C61E
0x14001c613  add     rcx, 8
0x14001c617  cmp     rcx, rsi
0x14001c61a  jb      short loc_14001C60D
0x14001c61c  jmp     short loc_14001C69B
0x14001c61e  test    rcx, rcx
0x14001c621  jz      short loc_14001C69B
0x14001c623  mov     r9d, dword ptr [rsp+28h+arg_0]
0x14001c628  mov     rax, [rcx]
0x14001c62b  mov     edx, [rax]
0x14001c62d  bt      edx, 9
0x14001c631  jnb     short loc_14001C673
0x14001c633  mov     r8d, edx
0x14001c636  and     r8d, 180h
0x14001c63d  jnz     short loc_14001C649
0x14001c63f  xor     eax, eax
0x14001c641  cmp     [rcx+1Fh], al
0x14001c644  setnz   al
0x14001c647  jmp     short loc_14001C655
0x14001c649  xor     eax, eax
0x14001c64b  cmp     r8d, 100h
0x14001c652  setz    al
0x14001c655  shr     edx, 6
0x14001c658  and     edx, 1
0x14001c65b  xor     edx, eax
0x14001c65d  mov     eax, r9d
0x14001c660  shl     edx, 6
0x14001c663  and     eax, 0FFFFFFBFh
0x14001c666  mov     r9d, edx
0x14001c669  or      r9d, eax
0x14001c66c  mov     rax, [rcx]
0x14001c66f  lock xor [rax], r9d
0x14001c673  add     rcx, 38h ; '8'
0x14001c677  jmp     short loc_14001C683
0x14001c679  cmp     qword ptr [rcx], 0
0x14001c67d  jnz     short loc_14001C68A
0x14001c67f  add     rcx, 8
0x14001c683  cmp     rcx, rsi
0x14001c686  jb      short loc_14001C679
0x14001c688  jmp     short loc_14001C69B
0x14001c68a  test    rcx, rcx
0x14001c68d  jnz     short loc_14001C628
0x14001c68f  jmp     short loc_14001C69B
0x14001c691  cmp     qword ptr [rbx], 0
0x14001c695  jnz     short loc_14001C6DE
0x14001c697  add     rbx, 8
0x14001c69b  cmp     rbx, rsi
0x14001c69e  jb      short loc_14001C691
0x14001c6a0  jmp     short loc_14001C6E3
0x14001c6a2  mov     rcx, [rbx]
0x14001c6a5  mov     [rsp+28h+arg_0], 0
0x14001c6ae  mov     eax, [rcx]
0x14001c6b0  mov     dword ptr [rsp+28h+arg_0], eax
0x14001c6b4  bt      eax, 9
0x14001c6b8  jnb     short loc_14001C6C7
0x14001c6ba  mov     rdx, [rsp+28h+arg_0]
0x14001c6bf  mov     r8, rbx
0x14001c6c2  call    wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState
0x14001c6c7  add     rbx, 38h ; '8'
0x14001c6cb  jmp     short loc_14001C6D7
0x14001c6cd  cmp     qword ptr [rbx], 0
0x14001c6d1  jnz     short loc_14001C6DE
0x14001c6d3  add     rbx, 8
0x14001c6d7  cmp     rbx, rsi
0x14001c6da  jb      short loc_14001C6CD
0x14001c6dc  jmp     short loc_14001C6E3
0x14001c6de  test    rbx, rbx
0x14001c6e1  jnz     short loc_14001C6A2
0x14001c6e3  mov     rbx, [rsp+28h+arg_8]
0x14001c6e8  add     rsp, 20h
0x14001c6ec  pop     rsi
0x14001c6ed  retn
```
