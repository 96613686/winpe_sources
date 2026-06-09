# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140018560`
- end: `0x140018684`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x14000ddc0`
- `0x140018250`
- `0x140018560`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400185df`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400185df`

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
0x140018560  mov     [rsp+arg_0], rbx
0x140018565  push    rsi
0x140018566  sub     rsp, 40h
0x14001856a  mov     rax, cs:__security_cookie
0x140018571  xor     rax, rsp
0x140018574  mov     [rsp+48h+var_10], rax
0x140018579  lea     rbx, wil_details_featureDescriptors_a
0x140018580  lea     rsi, wil_details_featureDescriptors_a
0x140018587  jmp     short loc_140018597
0x140018589  cmp     qword ptr [rbx], 0
0x14001858d  jnz     loc_14001865D
0x140018593  add     rbx, 8
0x140018597  cmp     rbx, rsi
0x14001859a  jb      short loc_140018589
0x14001859c  jmp     loc_140018666
0x1400185a1  cmp     byte ptr [rbx+1Dh], 0
0x1400185a5  jnz     loc_140018646
0x1400185ab  cmp     byte ptr [rbx+1Eh], 0
0x1400185af  jnz     loc_140018646
0x1400185b5  cmp     byte ptr [rbx+1Ch], 0
0x1400185b9  jnz     loc_140018646
0x1400185bf  mov     ecx, [rbx+18h]
0x1400185c2  lea     r9, [rsp+48h+var_20]
0x1400185c7  xor     eax, eax
0x1400185c9  lea     r8, [rsp+48h+var_28]
0x1400185ce  mov     [rsp+48h+var_20], rax
0x1400185d3  mov     [rsp+48h+var_18], eax
0x1400185d7  mov     [rsp+48h+var_28], rax
0x1400185dc  lea     edx, [rax+1]
0x1400185df  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400185e6  nop     dword ptr [rax+rax+00h]
0x1400185eb  cmp     eax, 80000022h
0x1400185f0  jz      short loc_14001862E
0x1400185f2  cmp     eax, 0C0000225h
0x1400185f7  jz      short loc_14001862E
0x1400185f9  test    eax, eax
0x1400185fb  jz      short loc_140018610
0x1400185fd  cmp     eax, 117h
0x140018602  jnz     short loc_14001862E
0x140018604  mov     edx, dword ptr [rsp+48h+var_20+4]
0x140018608  and     edx, 80h
0x14001860e  jmp     short loc_140018623
0x140018610  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140018614  mov     edx, eax
0x140018616  and     edx, 0FFFFFFD0h
0x140018619  and     eax, 0B0h
0x14001861e  shl     edx, 2
0x140018621  or      edx, eax
0x140018623  shl     edx, 3
0x140018626  or      edx, 206h
0x14001862c  jmp     short loc_140018633
0x14001862e  mov     edx, 206h
0x140018633  mov     rax, [rbx]
0x140018636  mov     ecx, [rax]
0x140018638  mov     rax, [rbx]
0x14001863b  xor     ecx, edx
0x14001863d  and     ecx, 0F80h
0x140018643  lock xor [rax], ecx
0x140018646  add     rbx, 38h ; '8'
0x14001864a  jmp     short loc_140018656
0x14001864c  cmp     qword ptr [rbx], 0
0x140018650  jnz     short loc_14001865D
0x140018652  add     rbx, 8
0x140018656  cmp     rbx, rsi
0x140018659  jb      short loc_14001864C
0x14001865b  jmp     short loc_140018666
0x14001865d  test    rbx, rbx
0x140018660  jnz     loc_1400185A1
0x140018666  call    wil_details_EvaluateFeatureDependencies
0x14001866b  mov     rcx, [rsp+48h+var_10]
0x140018670  xor     rcx, rsp; StackCookie
0x140018673  call    __security_check_cookie
0x140018678  mov     rbx, [rsp+48h+arg_0]
0x14001867d  add     rsp, 40h
0x140018681  pop     rsi
0x140018682  retn
```
