# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400850fc`
- end: `0x1400851db`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14008503c`

## callees

- `0x140046e28`
- `0x140059970`
- `0x14007b84c`
- `0x1400850fc`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14008515d`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14008515d`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  _UNKNOWN **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v2 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v2 = (_QWORD **)result;
    if ( !result )
      break;
    v7 = 0;
    v8 = 0;
    v6 = 0;
    v5 = 0;
    if ( *(_BYTE *)(result + 29) || *(_BYTE *)(result + 30) )
    {
      v3 = -1073741275;
    }
    else
    {
      v3 = RtlQueryFeatureConfiguration(
             *(unsigned int *)(result + 24),
             (unsigned __int8)(*(_BYTE *)(result + 28) - 2) > 1u,
             &v6,
             &v7);
      if ( v3 == -2147483614 )
      {
        v5 = 518;
        v4 = 518;
        do
        {
          **v2 = v4;
          result = wil_details_FeatureDescriptors_SkipPadding(v2 + 7);
          v2 = (_QWORD **)result;
        }
        while ( result );
        return result;
      }
    }
    wil_details_BuildFeatureStateCacheFromQueryResults(v3, &v7, &v5);
    **v2 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x1400850fc  push    rbx
0x1400850fe  sub     rsp, 50h
0x140085102  mov     rax, cs:__security_cookie
0x140085109  xor     rax, rsp
0x14008510c  mov     [rsp+58h+var_18], rax
0x140085111  lea     rcx, wil_details_featureDescriptors_a
0x140085118  call    wil_details_FeatureDescriptors_SkipPadding
0x14008511d  mov     rbx, rax
0x140085120  test    rax, rax
0x140085123  jz      short loc_14008519D
0x140085125  xor     eax, eax
0x140085127  mov     [rsp+58h+var_28], rax
0x14008512c  mov     [rsp+58h+var_20], eax
0x140085130  mov     [rsp+58h+var_30], rax
0x140085135  mov     [rsp+58h+var_38], rax
0x14008513a  cmp     [rbx+1Dh], al
0x14008513d  jnz     short loc_1400851B1
0x14008513f  cmp     [rbx+1Eh], al
0x140085142  jnz     short loc_1400851B1
0x140085144  mov     al, [rbx+1Ch]
0x140085147  lea     r9, [rsp+58h+var_28]
0x14008514c  mov     ecx, [rbx+18h]
0x14008514f  lea     r8, [rsp+58h+var_30]
0x140085154  xor     edx, edx
0x140085156  sub     al, 2
0x140085158  cmp     al, 1
0x14008515a  setnbe  dl
0x14008515d  call    cs:__imp_RtlQueryFeatureConfiguration
0x140085164  nop     dword ptr [rax+rax+00h]
0x140085169  cmp     eax, 80000022h
0x14008516e  jnz     short loc_1400851B6
0x140085170  mov     [rsp+58h+var_38], 0
0x140085179  mov     dword ptr [rsp+58h+var_38], 206h
0x140085181  mov     rdx, [rsp+58h+var_38]
0x140085186  mov     rax, [rbx]
0x140085189  lea     rcx, [rbx+38h]
0x14008518d  mov     [rax], rdx
0x140085190  call    wil_details_FeatureDescriptors_SkipPadding
0x140085195  mov     rbx, rax
0x140085198  test    rax, rax
0x14008519b  jnz     short loc_140085186
0x14008519d  mov     rcx, [rsp+58h+var_18]
0x1400851a2  xor     rcx, rsp; StackCookie
0x1400851a5  call    __security_check_cookie
0x1400851aa  add     rsp, 50h
0x1400851ae  pop     rbx
0x1400851af  retn
0x1400851b1  mov     eax, 0C0000225h
0x1400851b6  lea     r8, [rsp+58h+var_38]
0x1400851bb  mov     ecx, eax
0x1400851bd  lea     rdx, [rsp+58h+var_28]
0x1400851c2  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1400851c7  mov     rcx, [rbx]
0x1400851ca  mov     rax, [rsp+58h+var_38]
0x1400851cf  mov     [rcx], rax
0x1400851d2  lea     rcx, [rbx+38h]
0x1400851d6  jmp     loc_140085118
```
