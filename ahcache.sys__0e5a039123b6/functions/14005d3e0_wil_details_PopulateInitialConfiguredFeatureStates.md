# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14005d3e0`
- end: `0x14005d4bf`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14005d320`

## callees

- `0x1400050d8`
- `0x1400079f0`
- `0x14002cb34`
- `0x14005d3e0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005d441`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14005d441`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = v2 + 7 )
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
0x14005d3e0  push    rbx
0x14005d3e2  sub     rsp, 50h
0x14005d3e6  mov     rax, cs:__security_cookie
0x14005d3ed  xor     rax, rsp
0x14005d3f0  mov     [rsp+58h+var_18], rax
0x14005d3f5  lea     rcx, wil_details_featureDescriptors_a
0x14005d3fc  call    wil_details_FeatureDescriptors_SkipPadding
0x14005d401  mov     rbx, rax
0x14005d404  test    rax, rax
0x14005d407  jz      short loc_14005D481
0x14005d409  xor     eax, eax
0x14005d40b  mov     [rsp+58h+var_28], rax
0x14005d410  mov     [rsp+58h+var_20], eax
0x14005d414  mov     [rsp+58h+var_30], rax
0x14005d419  mov     [rsp+58h+var_38], rax
0x14005d41e  cmp     [rbx+1Dh], al
0x14005d421  jnz     short loc_14005D495
0x14005d423  cmp     [rbx+1Eh], al
0x14005d426  jnz     short loc_14005D495
0x14005d428  mov     al, [rbx+1Ch]
0x14005d42b  lea     r9, [rsp+58h+var_28]
0x14005d430  mov     ecx, [rbx+18h]
0x14005d433  lea     r8, [rsp+58h+var_30]
0x14005d438  xor     edx, edx
0x14005d43a  sub     al, 2
0x14005d43c  cmp     al, 1
0x14005d43e  setnbe  dl
0x14005d441  call    cs:__imp_RtlQueryFeatureConfiguration
0x14005d448  nop     dword ptr [rax+rax+00h]
0x14005d44d  cmp     eax, 80000022h
0x14005d452  jnz     short loc_14005D49A
0x14005d454  mov     [rsp+58h+var_38], 0
0x14005d45d  mov     dword ptr [rsp+58h+var_38], 206h
0x14005d465  mov     rdx, [rsp+58h+var_38]
0x14005d46a  mov     rax, [rbx]
0x14005d46d  lea     rcx, [rbx+38h]
0x14005d471  mov     [rax], rdx
0x14005d474  call    wil_details_FeatureDescriptors_SkipPadding
0x14005d479  mov     rbx, rax
0x14005d47c  test    rax, rax
0x14005d47f  jnz     short loc_14005D46A
0x14005d481  mov     rcx, [rsp+58h+var_18]
0x14005d486  xor     rcx, rsp; StackCookie
0x14005d489  call    __security_check_cookie
0x14005d48e  add     rsp, 50h
0x14005d492  pop     rbx
0x14005d493  retn
0x14005d495  mov     eax, 0C0000225h
0x14005d49a  lea     r8, [rsp+58h+var_38]
0x14005d49f  mov     ecx, eax
0x14005d4a1  lea     rdx, [rsp+58h+var_28]
0x14005d4a6  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14005d4ab  mov     rcx, [rbx]
0x14005d4ae  mov     rax, [rsp+58h+var_38]
0x14005d4b3  mov     [rcx], rax
0x14005d4b6  lea     rcx, [rbx+38h]
0x14005d4ba  jmp     loc_14005D3FC
```
