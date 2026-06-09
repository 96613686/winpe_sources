# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140015850`
- end: `0x140015974`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000d7f0`
- `0x140015564`
- `0x140015850`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400158cf`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400158cf`

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
0x140015850  mov     [rsp+arg_0], rbx
0x140015855  push    rsi
0x140015856  sub     rsp, 40h
0x14001585a  mov     rax, cs:__security_cookie
0x140015861  xor     rax, rsp
0x140015864  mov     [rsp+48h+var_10], rax
0x140015869  lea     rbx, wil_details_featureDescriptors_a
0x140015870  lea     rsi, wil_details_featureDescriptors_a
0x140015877  jmp     short loc_140015887
0x140015879  cmp     qword ptr [rbx], 0
0x14001587d  jnz     loc_14001594D
0x140015883  add     rbx, 8
0x140015887  cmp     rbx, rsi
0x14001588a  jb      short loc_140015879
0x14001588c  jmp     loc_140015956
0x140015891  cmp     byte ptr [rbx+1Dh], 0
0x140015895  jnz     loc_140015936
0x14001589b  cmp     byte ptr [rbx+1Eh], 0
0x14001589f  jnz     loc_140015936
0x1400158a5  cmp     byte ptr [rbx+1Ch], 0
0x1400158a9  jnz     loc_140015936
0x1400158af  mov     ecx, [rbx+18h]
0x1400158b2  lea     r9, [rsp+48h+var_20]
0x1400158b7  xor     eax, eax
0x1400158b9  lea     r8, [rsp+48h+var_28]
0x1400158be  mov     [rsp+48h+var_20], rax
0x1400158c3  mov     [rsp+48h+var_18], eax
0x1400158c7  mov     [rsp+48h+var_28], rax
0x1400158cc  lea     edx, [rax+1]
0x1400158cf  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400158d6  nop     dword ptr [rax+rax+00h]
0x1400158db  cmp     eax, 80000022h
0x1400158e0  jz      short loc_14001591E
0x1400158e2  cmp     eax, 0C0000225h
0x1400158e7  jz      short loc_14001591E
0x1400158e9  test    eax, eax
0x1400158eb  jz      short loc_140015900
0x1400158ed  cmp     eax, 117h
0x1400158f2  jnz     short loc_14001591E
0x1400158f4  mov     edx, dword ptr [rsp+48h+var_20+4]
0x1400158f8  and     edx, 80h
0x1400158fe  jmp     short loc_140015913
0x140015900  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140015904  mov     edx, eax
0x140015906  and     edx, 0FFFFFFD0h
0x140015909  and     eax, 0B0h
0x14001590e  shl     edx, 2
0x140015911  or      edx, eax
0x140015913  shl     edx, 3
0x140015916  or      edx, 206h
0x14001591c  jmp     short loc_140015923
0x14001591e  mov     edx, 206h
0x140015923  mov     rax, [rbx]
0x140015926  mov     ecx, [rax]
0x140015928  mov     rax, [rbx]
0x14001592b  xor     ecx, edx
0x14001592d  and     ecx, 0F80h
0x140015933  lock xor [rax], ecx
0x140015936  add     rbx, 38h ; '8'
0x14001593a  jmp     short loc_140015946
0x14001593c  cmp     qword ptr [rbx], 0
0x140015940  jnz     short loc_14001594D
0x140015942  add     rbx, 8
0x140015946  cmp     rbx, rsi
0x140015949  jb      short loc_14001593C
0x14001594b  jmp     short loc_140015956
0x14001594d  test    rbx, rbx
0x140015950  jnz     loc_140015891
0x140015956  call    wil_details_EvaluateFeatureDependencies
0x14001595b  mov     rcx, [rsp+48h+var_10]
0x140015960  xor     rcx, rsp; StackCookie
0x140015963  call    __security_check_cookie
0x140015968  mov     rbx, [rsp+48h+arg_0]
0x14001596d  add     rsp, 40h
0x140015971  pop     rsi
0x140015972  retn
```
