# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14003036c`
- end: `0x140030451`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400302ac`

## callees

- `0x140004dd8`
- `0x14001adc0`
- `0x14002a114`
- `0x14003036c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400303c5`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400303c5`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  int **i; // rcx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 result; // rax
  _QWORD **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (_QWORD **)result;
    if ( !result )
      break;
    v7 = 0;
    v8 = 0;
    v6 = 0;
    v5 = 0;
    if ( *(_BYTE *)(result + 29) || *(_BYTE *)(result + 30) )
    {
      v1 = -1073741275;
    }
    else
    {
      v1 = RtlQueryFeatureConfiguration(
             *(unsigned int *)(result + 24),
             (unsigned __int8)(*(_BYTE *)(result + 28) - 2) > 1u,
             &v6,
             &v7);
      if ( v1 == -2147483614 )
      {
        v5 = 518;
        v2 = 518;
        do
        {
          **v4 = v2;
          result = wil_details_FeatureDescriptors_SkipPadding(v4 + 7);
          v4 = (_QWORD **)result;
        }
        while ( result );
        return result;
      }
    }
    wil_details_BuildFeatureStateCacheFromQueryResults(v1, &v7, &v5);
    **v4 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x14003036c  push    rbx
0x14003036e  sub     rsp, 50h
0x140030372  mov     rax, cs:__security_cookie
0x140030379  xor     rax, rsp
0x14003037c  mov     [rsp+58h+var_18], rax
0x140030381  lea     rcx, wil_details_featureDescriptors_a
0x140030388  jmp     loc_14003043E
0x14003038d  xor     eax, eax
0x14003038f  mov     [rsp+58h+var_28], rax
0x140030394  mov     [rsp+58h+var_20], eax
0x140030398  mov     [rsp+58h+var_30], rax
0x14003039d  mov     [rsp+58h+var_38], rax
0x1400303a2  cmp     [rbx+1Dh], al
0x1400303a5  jnz     short loc_140030419
0x1400303a7  cmp     [rbx+1Eh], al
0x1400303aa  jnz     short loc_140030419
0x1400303ac  mov     al, [rbx+1Ch]
0x1400303af  lea     r9, [rsp+58h+var_28]
0x1400303b4  mov     ecx, [rbx+18h]
0x1400303b7  lea     r8, [rsp+58h+var_30]
0x1400303bc  xor     edx, edx
0x1400303be  sub     al, 2
0x1400303c0  cmp     al, 1
0x1400303c2  setnbe  dl
0x1400303c5  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400303cc  nop     dword ptr [rax+rax+00h]
0x1400303d1  cmp     eax, 80000022h
0x1400303d6  jnz     short loc_14003041E
0x1400303d8  mov     [rsp+58h+var_38], 0
0x1400303e1  mov     dword ptr [rsp+58h+var_38], 206h
0x1400303e9  mov     rdx, [rsp+58h+var_38]
0x1400303ee  mov     rax, [rbx]
0x1400303f1  lea     rcx, [rbx+38h]
0x1400303f5  mov     [rax], rdx
0x1400303f8  call    wil_details_FeatureDescriptors_SkipPadding
0x1400303fd  mov     rbx, rax
0x140030400  test    rax, rax
0x140030403  jnz     short loc_1400303EE
0x140030405  mov     rcx, [rsp+58h+var_18]
0x14003040a  xor     rcx, rsp; StackCookie
0x14003040d  call    __security_check_cookie
0x140030412  add     rsp, 50h
0x140030416  pop     rbx
0x140030417  retn
0x140030419  mov     eax, 0C0000225h
0x14003041e  lea     r8, [rsp+58h+var_38]
0x140030423  mov     ecx, eax
0x140030425  lea     rdx, [rsp+58h+var_28]
0x14003042a  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14003042f  mov     rcx, [rbx]
0x140030432  mov     rax, [rsp+58h+var_38]
0x140030437  mov     [rcx], rax
0x14003043a  lea     rcx, [rbx+38h]
0x14003043e  call    wil_details_FeatureDescriptors_SkipPadding
0x140030443  mov     rbx, rax
0x140030446  test    rax, rax
0x140030449  jnz     loc_14003038D
0x14003044f  jmp     short loc_140030405
```
