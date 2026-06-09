# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14001c8d0`
- end: `0x14001c9f4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140007d00`
- `0x14001c5e0`
- `0x14001c8d0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001c94f`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001c94f`

## pseudocode

```c
__int64 wil_details_ReevaluateOnFeatureConfigurationChange()
{
  __int64 **i; // rbx
  __int64 v1; // rcx
  int v2; // eax
  __int16 v3; // dx
  __int16 v4; // dx
  __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF
  int v8; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; i < (__int64 **)wil_details_featureDescriptors_z; ++i )
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
      for ( i += 7; i < (__int64 **)wil_details_featureDescriptors_z; ++i )
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
0x14001c8d0  mov     [rsp+arg_0], rbx
0x14001c8d5  push    rsi
0x14001c8d6  sub     rsp, 40h
0x14001c8da  mov     rax, cs:__security_cookie
0x14001c8e1  xor     rax, rsp
0x14001c8e4  mov     [rsp+48h+var_10], rax
0x14001c8e9  lea     rbx, wil_details_featureDescriptors_a
0x14001c8f0  lea     rsi, wil_details_featureDescriptors_z
0x14001c8f7  jmp     short loc_14001C907
0x14001c8f9  cmp     qword ptr [rbx], 0
0x14001c8fd  jnz     loc_14001C9CD
0x14001c903  add     rbx, 8
0x14001c907  cmp     rbx, rsi
0x14001c90a  jb      short loc_14001C8F9
0x14001c90c  jmp     loc_14001C9D6
0x14001c911  cmp     byte ptr [rbx+1Dh], 0
0x14001c915  jnz     loc_14001C9B6
0x14001c91b  cmp     byte ptr [rbx+1Eh], 0
0x14001c91f  jnz     loc_14001C9B6
0x14001c925  cmp     byte ptr [rbx+1Ch], 0
0x14001c929  jnz     loc_14001C9B6
0x14001c92f  mov     ecx, [rbx+18h]
0x14001c932  lea     r9, [rsp+48h+var_20]
0x14001c937  xor     eax, eax
0x14001c939  lea     r8, [rsp+48h+var_28]
0x14001c93e  mov     [rsp+48h+var_20], rax
0x14001c943  mov     [rsp+48h+var_18], eax
0x14001c947  mov     [rsp+48h+var_28], rax
0x14001c94c  lea     edx, [rax+1]
0x14001c94f  call    cs:__imp_RtlQueryFeatureConfiguration
0x14001c956  nop     dword ptr [rax+rax+00h]
0x14001c95b  cmp     eax, 80000022h
0x14001c960  jz      short loc_14001C99E
0x14001c962  cmp     eax, 0C0000225h
0x14001c967  jz      short loc_14001C99E
0x14001c969  test    eax, eax
0x14001c96b  jz      short loc_14001C980
0x14001c96d  cmp     eax, 117h
0x14001c972  jnz     short loc_14001C99E
0x14001c974  mov     edx, dword ptr [rsp+48h+var_20+4]
0x14001c978  and     edx, 80h
0x14001c97e  jmp     short loc_14001C993
0x14001c980  mov     eax, dword ptr [rsp+48h+var_20+4]
0x14001c984  mov     edx, eax
0x14001c986  and     edx, 0FFFFFFD0h
0x14001c989  and     eax, 0B0h
0x14001c98e  shl     edx, 2
0x14001c991  or      edx, eax
0x14001c993  shl     edx, 3
0x14001c996  or      edx, 206h
0x14001c99c  jmp     short loc_14001C9A3
0x14001c99e  mov     edx, 206h
0x14001c9a3  mov     rax, [rbx]
0x14001c9a6  mov     ecx, [rax]
0x14001c9a8  mov     rax, [rbx]
0x14001c9ab  xor     ecx, edx
0x14001c9ad  and     ecx, 0F80h
0x14001c9b3  lock xor [rax], ecx
0x14001c9b6  add     rbx, 38h ; '8'
0x14001c9ba  jmp     short loc_14001C9C6
0x14001c9bc  cmp     qword ptr [rbx], 0
0x14001c9c0  jnz     short loc_14001C9CD
0x14001c9c2  add     rbx, 8
0x14001c9c6  cmp     rbx, rsi
0x14001c9c9  jb      short loc_14001C9BC
0x14001c9cb  jmp     short loc_14001C9D6
0x14001c9cd  test    rbx, rbx
0x14001c9d0  jnz     loc_14001C911
0x14001c9d6  call    wil_details_EvaluateFeatureDependencies
0x14001c9db  mov     rcx, [rsp+48h+var_10]
0x14001c9e0  xor     rcx, rsp; StackCookie
0x14001c9e3  call    __security_check_cookie
0x14001c9e8  mov     rbx, [rsp+48h+arg_0]
0x14001c9ed  add     rsp, 40h
0x14001c9f1  pop     rsi
0x14001c9f2  retn
```
