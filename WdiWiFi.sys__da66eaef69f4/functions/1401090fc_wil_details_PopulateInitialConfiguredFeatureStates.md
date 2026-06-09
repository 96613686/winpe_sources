# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1401090fc`
- end: `0x1401091db`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14010903c`

## callees

- `0x1400c6138`
- `0x1400da4f0`
- `0x14010777c`
- `0x1401090fc`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14010915d`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14010915d`

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
0x1401090fc  push    rbx
0x1401090fe  sub     rsp, 50h
0x140109102  mov     rax, cs:__security_cookie
0x140109109  xor     rax, rsp
0x14010910c  mov     [rsp+58h+var_18], rax
0x140109111  lea     rcx, wil_details_featureDescriptors_a
0x140109118  call    wil_details_FeatureDescriptors_SkipPadding
0x14010911d  mov     rbx, rax
0x140109120  test    rax, rax
0x140109123  jz      short loc_14010919D
0x140109125  xor     eax, eax
0x140109127  mov     [rsp+58h+var_28], rax
0x14010912c  mov     [rsp+58h+var_20], eax
0x140109130  mov     [rsp+58h+var_30], rax
0x140109135  mov     [rsp+58h+var_38], rax
0x14010913a  cmp     [rbx+1Dh], al
0x14010913d  jnz     short loc_1401091B1
0x14010913f  cmp     [rbx+1Eh], al
0x140109142  jnz     short loc_1401091B1
0x140109144  mov     al, [rbx+1Ch]
0x140109147  lea     r9, [rsp+58h+var_28]
0x14010914c  mov     ecx, [rbx+18h]
0x14010914f  lea     r8, [rsp+58h+var_30]
0x140109154  xor     edx, edx
0x140109156  sub     al, 2
0x140109158  cmp     al, 1
0x14010915a  setnbe  dl
0x14010915d  call    cs:__imp_RtlQueryFeatureConfiguration
0x140109164  nop     dword ptr [rax+rax+00h]
0x140109169  cmp     eax, 80000022h
0x14010916e  jnz     short loc_1401091B6
0x140109170  mov     [rsp+58h+var_38], 0
0x140109179  mov     dword ptr [rsp+58h+var_38], 206h
0x140109181  mov     rdx, [rsp+58h+var_38]
0x140109186  mov     rax, [rbx]
0x140109189  lea     rcx, [rbx+38h]
0x14010918d  mov     [rax], rdx
0x140109190  call    wil_details_FeatureDescriptors_SkipPadding
0x140109195  mov     rbx, rax
0x140109198  test    rax, rax
0x14010919b  jnz     short loc_140109186
0x14010919d  mov     rcx, [rsp+58h+var_18]
0x1401091a2  xor     rcx, rsp; StackCookie
0x1401091a5  call    __security_check_cookie
0x1401091aa  add     rsp, 50h
0x1401091ae  pop     rbx
0x1401091af  retn
0x1401091b1  mov     eax, 0C0000225h
0x1401091b6  lea     r8, [rsp+58h+var_38]
0x1401091bb  mov     ecx, eax
0x1401091bd  lea     rdx, [rsp+58h+var_28]
0x1401091c2  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x1401091c7  mov     rcx, [rbx]
0x1401091ca  mov     rax, [rsp+58h+var_38]
0x1401091cf  mov     [rcx], rax
0x1401091d2  lea     rcx, [rbx+38h]
0x1401091d6  jmp     loc_140109118
```
