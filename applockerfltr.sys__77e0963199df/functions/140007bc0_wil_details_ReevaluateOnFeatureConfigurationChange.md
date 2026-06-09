# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140007bc0`
- end: `0x140007ce4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140001820`
- `0x140007970`
- `0x140007bc0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140007c3f`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140007c3f`

## pseudocode

```c
__int64 wil_details_ReevaluateOnFeatureConfigurationChange()
{
  __int64 *i; // rbx
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
0x140007bc0  mov     [rsp+arg_0], rbx
0x140007bc5  push    rsi
0x140007bc6  sub     rsp, 40h
0x140007bca  mov     rax, cs:__security_cookie
0x140007bd1  xor     rax, rsp
0x140007bd4  mov     [rsp+48h+var_10], rax
0x140007bd9  lea     rbx, wil_details_featureDescriptors_a
0x140007be0  lea     rsi, wil_details_featureDescriptors_a
0x140007be7  jmp     short loc_140007BF7
0x140007be9  cmp     qword ptr [rbx], 0
0x140007bed  jnz     loc_140007CBD
0x140007bf3  add     rbx, 8
0x140007bf7  cmp     rbx, rsi
0x140007bfa  jb      short loc_140007BE9
0x140007bfc  jmp     loc_140007CC6
0x140007c01  cmp     byte ptr [rbx+1Dh], 0
0x140007c05  jnz     loc_140007CA6
0x140007c0b  cmp     byte ptr [rbx+1Eh], 0
0x140007c0f  jnz     loc_140007CA6
0x140007c15  cmp     byte ptr [rbx+1Ch], 0
0x140007c19  jnz     loc_140007CA6
0x140007c1f  mov     ecx, [rbx+18h]
0x140007c22  lea     r9, [rsp+48h+var_20]
0x140007c27  xor     eax, eax
0x140007c29  lea     r8, [rsp+48h+var_28]
0x140007c2e  mov     [rsp+48h+var_20], rax
0x140007c33  mov     [rsp+48h+var_18], eax
0x140007c37  mov     [rsp+48h+var_28], rax
0x140007c3c  lea     edx, [rax+1]
0x140007c3f  call    cs:__imp_RtlQueryFeatureConfiguration
0x140007c46  nop     dword ptr [rax+rax+00h]
0x140007c4b  cmp     eax, 80000022h
0x140007c50  jz      short loc_140007C8E
0x140007c52  cmp     eax, 0C0000225h
0x140007c57  jz      short loc_140007C8E
0x140007c59  test    eax, eax
0x140007c5b  jz      short loc_140007C70
0x140007c5d  cmp     eax, 117h
0x140007c62  jnz     short loc_140007C8E
0x140007c64  mov     edx, dword ptr [rsp+48h+var_20+4]
0x140007c68  and     edx, 80h
0x140007c6e  jmp     short loc_140007C83
0x140007c70  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140007c74  mov     edx, eax
0x140007c76  and     edx, 0FFFFFFD0h
0x140007c79  and     eax, 0B0h
0x140007c7e  shl     edx, 2
0x140007c81  or      edx, eax
0x140007c83  shl     edx, 3
0x140007c86  or      edx, 206h
0x140007c8c  jmp     short loc_140007C93
0x140007c8e  mov     edx, 206h
0x140007c93  mov     rax, [rbx]
0x140007c96  mov     ecx, [rax]
0x140007c98  mov     rax, [rbx]
0x140007c9b  xor     ecx, edx
0x140007c9d  and     ecx, 0F80h
0x140007ca3  lock xor [rax], ecx
0x140007ca6  add     rbx, 38h ; '8'
0x140007caa  jmp     short loc_140007CB6
0x140007cac  cmp     qword ptr [rbx], 0
0x140007cb0  jnz     short loc_140007CBD
0x140007cb2  add     rbx, 8
0x140007cb6  cmp     rbx, rsi
0x140007cb9  jb      short loc_140007CAC
0x140007cbb  jmp     short loc_140007CC6
0x140007cbd  test    rbx, rbx
0x140007cc0  jnz     loc_140007C01
0x140007cc6  call    wil_details_EvaluateFeatureDependencies
0x140007ccb  mov     rcx, [rsp+48h+var_10]
0x140007cd0  xor     rcx, rsp; StackCookie
0x140007cd3  call    __security_check_cookie
0x140007cd8  mov     rbx, [rsp+48h+arg_0]
0x140007cdd  add     rsp, 40h
0x140007ce1  pop     rsi
0x140007ce2  retn
```
