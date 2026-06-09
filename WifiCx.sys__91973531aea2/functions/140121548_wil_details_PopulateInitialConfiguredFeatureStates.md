# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140121548`
- end: `0x140121627`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140121488`

## callees

- `0x1400d94bc`
- `0x1400dfd00`
- `0x14011fd90`
- `0x140121548`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1401215a9`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1401215a9`

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
0x140121548  push    rbx
0x14012154a  sub     rsp, 50h
0x14012154e  mov     rax, cs:__security_cookie
0x140121555  xor     rax, rsp
0x140121558  mov     [rsp+58h+var_18], rax
0x14012155d  lea     rcx, wil_details_featureDescriptors_a
0x140121564  call    wil_details_FeatureDescriptors_SkipPadding
0x140121569  mov     rbx, rax
0x14012156c  test    rax, rax
0x14012156f  jz      short loc_1401215E9
0x140121571  xor     eax, eax
0x140121573  mov     [rsp+58h+var_28], rax
0x140121578  mov     [rsp+58h+var_20], eax
0x14012157c  mov     [rsp+58h+var_30], rax
0x140121581  mov     [rsp+58h+var_38], rax
0x140121586  cmp     [rbx+1Dh], al
0x140121589  jnz     short loc_1401215FD
0x14012158b  cmp     [rbx+1Eh], al
0x14012158e  jnz     short loc_1401215FD
0x140121590  mov     al, [rbx+1Ch]
0x140121593  lea     r9, [rsp+58h+var_28]
0x140121598  mov     ecx, [rbx+18h]
0x14012159b  lea     r8, [rsp+58h+var_30]
0x1401215a0  xor     edx, edx
0x1401215a2  sub     al, 2
0x1401215a4  cmp     al, 1
0x1401215a6  setnbe  dl
0x1401215a9  call    cs:__imp_RtlQueryFeatureConfiguration
0x1401215b0  nop     dword ptr [rax+rax+00h]
0x1401215b5  cmp     eax, 80000022h
0x1401215ba  jnz     short loc_140121602
0x1401215bc  mov     [rsp+58h+var_38], 0
0x1401215c5  mov     dword ptr [rsp+58h+var_38], 206h
0x1401215cd  mov     rdx, [rsp+58h+var_38]
0x1401215d2  mov     rax, [rbx]
0x1401215d5  lea     rcx, [rbx+38h]
0x1401215d9  mov     [rax], rdx
0x1401215dc  call    wil_details_FeatureDescriptors_SkipPadding
0x1401215e1  mov     rbx, rax
0x1401215e4  test    rax, rax
0x1401215e7  jnz     short loc_1401215D2
0x1401215e9  mov     rcx, [rsp+58h+var_18]
0x1401215ee  xor     rcx, rsp; StackCookie
0x1401215f1  call    __security_check_cookie
0x1401215f6  add     rsp, 50h
0x1401215fa  pop     rbx
0x1401215fb  retn
0x1401215fd  mov     eax, 0C0000225h
0x140121602  lea     r8, [rsp+58h+var_38]
0x140121607  mov     ecx, eax
0x140121609  lea     rdx, [rsp+58h+var_28]
0x14012160e  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140121613  mov     rcx, [rbx]
0x140121616  mov     rax, [rsp+58h+var_38]
0x14012161b  mov     [rcx], rax
0x14012161e  lea     rcx, [rbx+38h]
0x140121622  jmp     loc_140121564
```
