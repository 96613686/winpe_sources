# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x18001d3a0`
- end: `0x18001d4c4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180012200`
- `0x18001d090`
- `0x18001d3a0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18001d41f`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18001d41f`

## pseudocode

```c
__int64 wil_details_ReevaluateOnFeatureConfigurationChange()
{
  _QWORD *i; // rbx
  __int64 v1; // rcx
  int v2; // eax
  __int16 v3; // dx
  __int16 v4; // dx
  __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF
  int v8; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; i < wil_details_featureDescriptors_a; ++i )
  {
    if ( *i )
    {
LABEL_23:
      if ( !i )
        return wil_details_EvaluateFeatureDependencies();
      if ( !*((_BYTE *)i + 29) && !*((_BYTE *)i + 30) && !*((_BYTE *)i + 28) )
      {
        v1 = *((unsigned int *)i + 6);
        v7 = 0;
        v8 = 0;
        v6 = 0;
        v2 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(
               v1,
               1,
               &v6,
               &v7);
        if ( v2 == -2147483614 || v2 == -1073741275 )
          goto LABEL_16;
        if ( v2 )
        {
          if ( v2 == 279 )
          {
            v3 = BYTE4(v7) & 0x80;
            goto LABEL_15;
          }
LABEL_16:
          v4 = 518;
        }
        else
        {
          v3 = BYTE4(v7) & 0xB0 | (4 * (WORD2(v7) & 0xFFD0));
LABEL_15:
          v4 = (8 * v3) | 0x206;
        }
        _InterlockedXor((volatile signed __int32 *)*i, ((unsigned __int16)v4 ^ (unsigned __int16)*(_DWORD *)*i) & 0xF80);
      }
      for ( i += 7; i < wil_details_featureDescriptors_a; ++i )
      {
        if ( *i )
          goto LABEL_23;
      }
      return wil_details_EvaluateFeatureDependencies();
    }
  }
  return wil_details_EvaluateFeatureDependencies();
}

```

## disassembly

```asm
0x18001d3a0  mov     [rsp+arg_0], rbx
0x18001d3a5  push    rsi
0x18001d3a6  sub     rsp, 40h
0x18001d3aa  mov     rax, cs:__security_cookie
0x18001d3b1  xor     rax, rsp
0x18001d3b4  mov     [rsp+48h+var_10], rax
0x18001d3b9  lea     rbx, wil_details_featureDescriptors_a
0x18001d3c0  lea     rsi, wil_details_featureDescriptors_a
0x18001d3c7  jmp     short loc_18001D3D7
0x18001d3c9  cmp     qword ptr [rbx], 0
0x18001d3cd  jnz     loc_18001D49D
0x18001d3d3  add     rbx, 8
0x18001d3d7  cmp     rbx, rsi
0x18001d3da  jb      short loc_18001D3C9
0x18001d3dc  jmp     loc_18001D4A6
0x18001d3e1  cmp     byte ptr [rbx+1Dh], 0
0x18001d3e5  jnz     loc_18001D486
0x18001d3eb  cmp     byte ptr [rbx+1Eh], 0
0x18001d3ef  jnz     loc_18001D486
0x18001d3f5  cmp     byte ptr [rbx+1Ch], 0
0x18001d3f9  jnz     loc_18001D486
0x18001d3ff  mov     ecx, [rbx+18h]
0x18001d402  lea     r9, [rsp+48h+var_20]
0x18001d407  xor     eax, eax
0x18001d409  lea     r8, [rsp+48h+var_28]
0x18001d40e  mov     [rsp+48h+var_20], rax
0x18001d413  mov     [rsp+48h+var_18], eax
0x18001d417  mov     [rsp+48h+var_28], rax
0x18001d41c  lea     edx, [rax+1]
0x18001d41f  call    cs:__imp_RtlQueryFeatureConfiguration
0x18001d426  nop     dword ptr [rax+rax+00h]
0x18001d42b  cmp     eax, 80000022h
0x18001d430  jz      short loc_18001D46E
0x18001d432  cmp     eax, 0C0000225h
0x18001d437  jz      short loc_18001D46E
0x18001d439  test    eax, eax
0x18001d43b  jz      short loc_18001D450
0x18001d43d  cmp     eax, 117h
0x18001d442  jnz     short loc_18001D46E
0x18001d444  mov     edx, dword ptr [rsp+48h+var_20+4]
0x18001d448  and     edx, 80h
0x18001d44e  jmp     short loc_18001D463
0x18001d450  mov     eax, dword ptr [rsp+48h+var_20+4]
0x18001d454  mov     edx, eax
0x18001d456  and     edx, 0FFFFFFD0h
0x18001d459  and     eax, 0B0h
0x18001d45e  shl     edx, 2
0x18001d461  or      edx, eax
0x18001d463  shl     edx, 3
0x18001d466  or      edx, 206h
0x18001d46c  jmp     short loc_18001D473
0x18001d46e  mov     edx, 206h
0x18001d473  mov     rax, [rbx]
0x18001d476  mov     ecx, [rax]
0x18001d478  mov     rax, [rbx]
0x18001d47b  xor     ecx, edx
0x18001d47d  and     ecx, 0F80h
0x18001d483  lock xor [rax], ecx
0x18001d486  add     rbx, 38h ; '8'
0x18001d48a  jmp     short loc_18001D496
0x18001d48c  cmp     qword ptr [rbx], 0
0x18001d490  jnz     short loc_18001D49D
0x18001d492  add     rbx, 8
0x18001d496  cmp     rbx, rsi
0x18001d499  jb      short loc_18001D48C
0x18001d49b  jmp     short loc_18001D4A6
0x18001d49d  test    rbx, rbx
0x18001d4a0  jnz     loc_18001D3E1
0x18001d4a6  call    wil_details_EvaluateFeatureDependencies
0x18001d4ab  mov     rcx, [rsp+48h+var_10]
0x18001d4b0  xor     rcx, rsp; StackCookie
0x18001d4b3  call    __security_check_cookie
0x18001d4b8  mov     rbx, [rsp+48h+arg_0]
0x18001d4bd  add     rsp, 40h
0x18001d4c1  pop     rsi
0x18001d4c2  retn
```
