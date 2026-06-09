# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14001f650`
- end: `0x14001f72f`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001f590`

## callees

- `0x140004784`
- `0x140013860`
- `0x14001e8e4`
- `0x14001f650`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001f6b1`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001f6b1`

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
0x14001f650  push    rbx
0x14001f652  sub     rsp, 50h
0x14001f656  mov     rax, cs:__security_cookie
0x14001f65d  xor     rax, rsp
0x14001f660  mov     [rsp+58h+var_18], rax
0x14001f665  lea     rcx, wil_details_featureDescriptors_a
0x14001f66c  call    wil_details_FeatureDescriptors_SkipPadding
0x14001f671  mov     rbx, rax
0x14001f674  test    rax, rax
0x14001f677  jz      short loc_14001F6F1
0x14001f679  xor     eax, eax
0x14001f67b  mov     [rsp+58h+var_28], rax
0x14001f680  mov     [rsp+58h+var_20], eax
0x14001f684  mov     [rsp+58h+var_30], rax
0x14001f689  mov     [rsp+58h+var_38], rax
0x14001f68e  cmp     [rbx+1Dh], al
0x14001f691  jnz     short loc_14001F705
0x14001f693  cmp     [rbx+1Eh], al
0x14001f696  jnz     short loc_14001F705
0x14001f698  mov     al, [rbx+1Ch]
0x14001f69b  lea     r9, [rsp+58h+var_28]
0x14001f6a0  mov     ecx, [rbx+18h]
0x14001f6a3  lea     r8, [rsp+58h+var_30]
0x14001f6a8  xor     edx, edx
0x14001f6aa  sub     al, 2
0x14001f6ac  cmp     al, 1
0x14001f6ae  setnbe  dl
0x14001f6b1  call    cs:__imp_RtlQueryFeatureConfiguration
0x14001f6b8  nop     dword ptr [rax+rax+00h]
0x14001f6bd  cmp     eax, 80000022h
0x14001f6c2  jnz     short loc_14001F70A
0x14001f6c4  mov     [rsp+58h+var_38], 0
0x14001f6cd  mov     dword ptr [rsp+58h+var_38], 206h
0x14001f6d5  mov     rdx, [rsp+58h+var_38]
0x14001f6da  mov     rax, [rbx]
0x14001f6dd  lea     rcx, [rbx+38h]
0x14001f6e1  mov     [rax], rdx
0x14001f6e4  call    wil_details_FeatureDescriptors_SkipPadding
0x14001f6e9  mov     rbx, rax
0x14001f6ec  test    rax, rax
0x14001f6ef  jnz     short loc_14001F6DA
0x14001f6f1  mov     rcx, [rsp+58h+var_18]
0x14001f6f6  xor     rcx, rsp; StackCookie
0x14001f6f9  call    __security_check_cookie
0x14001f6fe  add     rsp, 50h
0x14001f702  pop     rbx
0x14001f703  retn
0x14001f705  mov     eax, 0C0000225h
0x14001f70a  lea     r8, [rsp+58h+var_38]
0x14001f70f  mov     ecx, eax
0x14001f711  lea     rdx, [rsp+58h+var_28]
0x14001f716  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14001f71b  mov     rcx, [rbx]
0x14001f71e  mov     rax, [rsp+58h+var_38]
0x14001f723  mov     [rcx], rax
0x14001f726  lea     rcx, [rbx+38h]
0x14001f72a  jmp     loc_14001F66C
```
