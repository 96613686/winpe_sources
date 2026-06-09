# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x1400657d0`
- end: `0x1400658f4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140047e50`
- `0x140065564`
- `0x1400657d0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14006584f`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14006584f`

## pseudocode

```c
__int64 wil_details_ReevaluateOnFeatureConfigurationChange()
{
  int **i; // rbx
  __int64 v1; // rcx
  int v2; // eax
  __int16 v3; // dx
  __int16 v4; // dx
  __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF
  int v8; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; i < (int **)wil_details_featureDescriptors_z; ++i )
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
        _InterlockedXor(*i, ((unsigned __int16)v4 ^ (unsigned __int16)**i) & 0xF80);
      }
      for ( i += 7; i < (int **)wil_details_featureDescriptors_z; ++i )
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
0x1400657d0  mov     [rsp+arg_0], rbx
0x1400657d5  push    rsi
0x1400657d6  sub     rsp, 40h
0x1400657da  mov     rax, cs:__security_cookie
0x1400657e1  xor     rax, rsp
0x1400657e4  mov     [rsp+48h+var_10], rax
0x1400657e9  lea     rbx, wil_details_featureDescriptors_a
0x1400657f0  lea     rsi, wil_details_featureDescriptors_z
0x1400657f7  jmp     short loc_140065807
0x1400657f9  cmp     qword ptr [rbx], 0
0x1400657fd  jnz     loc_1400658CD
0x140065803  add     rbx, 8
0x140065807  cmp     rbx, rsi
0x14006580a  jb      short loc_1400657F9
0x14006580c  jmp     loc_1400658D6
0x140065811  cmp     byte ptr [rbx+1Dh], 0
0x140065815  jnz     loc_1400658B6
0x14006581b  cmp     byte ptr [rbx+1Eh], 0
0x14006581f  jnz     loc_1400658B6
0x140065825  cmp     byte ptr [rbx+1Ch], 0
0x140065829  jnz     loc_1400658B6
0x14006582f  mov     ecx, [rbx+18h]
0x140065832  lea     r9, [rsp+48h+var_20]
0x140065837  xor     eax, eax
0x140065839  lea     r8, [rsp+48h+var_28]
0x14006583e  mov     [rsp+48h+var_20], rax
0x140065843  mov     [rsp+48h+var_18], eax
0x140065847  mov     [rsp+48h+var_28], rax
0x14006584c  lea     edx, [rax+1]
0x14006584f  call    cs:__imp_RtlQueryFeatureConfiguration
0x140065856  nop     dword ptr [rax+rax+00h]
0x14006585b  cmp     eax, 80000022h
0x140065860  jz      short loc_14006589E
0x140065862  cmp     eax, 0C0000225h
0x140065867  jz      short loc_14006589E
0x140065869  test    eax, eax
0x14006586b  jz      short loc_140065880
0x14006586d  cmp     eax, 117h
0x140065872  jnz     short loc_14006589E
0x140065874  mov     edx, dword ptr [rsp+48h+var_20+4]
0x140065878  and     edx, 80h
0x14006587e  jmp     short loc_140065893
0x140065880  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140065884  mov     edx, eax
0x140065886  and     edx, 0FFFFFFD0h
0x140065889  and     eax, 0B0h
0x14006588e  shl     edx, 2
0x140065891  or      edx, eax
0x140065893  shl     edx, 3
0x140065896  or      edx, 206h
0x14006589c  jmp     short loc_1400658A3
0x14006589e  mov     edx, 206h
0x1400658a3  mov     rax, [rbx]
0x1400658a6  mov     ecx, [rax]
0x1400658a8  mov     rax, [rbx]
0x1400658ab  xor     ecx, edx
0x1400658ad  and     ecx, 0F80h
0x1400658b3  lock xor [rax], ecx
0x1400658b6  add     rbx, 38h ; '8'
0x1400658ba  jmp     short loc_1400658C6
0x1400658bc  cmp     qword ptr [rbx], 0
0x1400658c0  jnz     short loc_1400658CD
0x1400658c2  add     rbx, 8
0x1400658c6  cmp     rbx, rsi
0x1400658c9  jb      short loc_1400658BC
0x1400658cb  jmp     short loc_1400658D6
0x1400658cd  test    rbx, rbx
0x1400658d0  jnz     loc_140065811
0x1400658d6  call    wil_details_EvaluateFeatureDependencies
0x1400658db  mov     rcx, [rsp+48h+var_10]
0x1400658e0  xor     rcx, rsp; StackCookie
0x1400658e3  call    __security_check_cookie
0x1400658e8  mov     rbx, [rsp+48h+arg_0]
0x1400658ed  add     rsp, 40h
0x1400658f1  pop     rsi
0x1400658f2  retn
```
