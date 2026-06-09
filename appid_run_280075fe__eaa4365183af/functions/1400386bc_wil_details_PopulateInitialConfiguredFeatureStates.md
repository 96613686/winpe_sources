# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400386bc`
- end: `0x14003879b`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400385fc`

## callees

- `0x140001760`
- `0x140006a20`
- `0x140022680`
- `0x1400386bc`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14003871d`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14003871d`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  int **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v2 + 7) )
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
0x1400386bc  push    rbx
0x1400386be  sub     rsp, 50h
0x1400386c2  mov     rax, cs:__security_cookie
0x1400386c9  xor     rax, rsp
0x1400386cc  mov     [rsp+58h+var_18], rax
0x1400386d1  lea     rcx, wil_details_featureDescriptors_a
0x1400386d8  call    wil_details_FeatureDescriptors_SkipPadding
0x1400386dd  mov     rbx, rax
0x1400386e0  test    rax, rax
0x1400386e3  jz      short loc_14003875D
0x1400386e5  xor     eax, eax
0x1400386e7  mov     [rsp+58h+var_28], rax
0x1400386ec  mov     [rsp+58h+var_20], eax
0x1400386f0  mov     [rsp+58h+var_30], rax
0x1400386f5  mov     [rsp+58h+var_38], rax
0x1400386fa  cmp     [rbx+1Dh], al
0x1400386fd  jnz     short loc_140038771
0x1400386ff  cmp     [rbx+1Eh], al
0x140038702  jnz     short loc_140038771
0x140038704  mov     al, [rbx+1Ch]
0x140038707  lea     r9, [rsp+58h+var_28]
0x14003870c  mov     ecx, [rbx+18h]
0x14003870f  lea     r8, [rsp+58h+var_30]
0x140038714  xor     edx, edx
0x140038716  sub     al, 2
0x140038718  cmp     al, 1
0x14003871a  setnbe  dl
0x14003871d  call    cs:__imp_RtlQueryFeatureConfiguration
0x140038724  nop     dword ptr [rax+rax+00h]
0x140038729  cmp     eax, 80000022h
0x14003872e  jnz     short loc_140038776
0x140038730  mov     [rsp+58h+var_38], 0
0x140038739  mov     dword ptr [rsp+58h+var_38], 206h
0x140038741  mov     rdx, [rsp+58h+var_38]
0x140038746  mov     rax, [rbx]
0x140038749  lea     rcx, [rbx+38h]
0x14003874d  mov     [rax], rdx
0x140038750  call    wil_details_FeatureDescriptors_SkipPadding
0x140038755  mov     rbx, rax
0x140038758  test    rax, rax
0x14003875b  jnz     short loc_140038746
0x14003875d  mov     rcx, [rsp+58h+var_18]
0x140038762  xor     rcx, rsp; StackCookie
0x140038765  call    __security_check_cookie
0x14003876a  add     rsp, 50h
0x14003876e  pop     rbx
0x14003876f  retn
0x140038771  mov     eax, 0C0000225h
0x140038776  lea     r8, [rsp+58h+var_38]
0x14003877b  mov     ecx, eax
0x14003877d  lea     rdx, [rsp+58h+var_28]
0x140038782  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140038787  mov     rcx, [rbx]
0x14003878a  mov     rax, [rsp+58h+var_38]
0x14003878f  mov     [rcx], rax
0x140038792  lea     rcx, [rbx+38h]
0x140038796  jmp     loc_1400386D8
```
