# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400162ac`
- end: `0x14001638b`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400161ec`

## callees

- `0x1400018fc`
- `0x1400026d0`
- `0x14000b534`
- `0x1400162ac`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001630d`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001630d`

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
0x1400162ac  push    rbx
0x1400162ae  sub     rsp, 50h
0x1400162b2  mov     rax, cs:__security_cookie
0x1400162b9  xor     rax, rsp
0x1400162bc  mov     [rsp+58h+var_18], rax
0x1400162c1  lea     rcx, wil_details_featureDescriptors_a
0x1400162c8  call    wil_details_FeatureDescriptors_SkipPadding
0x1400162cd  mov     rbx, rax
0x1400162d0  test    rax, rax
0x1400162d3  jz      short loc_14001634D
0x1400162d5  xor     eax, eax
0x1400162d7  mov     [rsp+58h+var_28], rax
0x1400162dc  mov     [rsp+58h+var_20], eax
0x1400162e0  mov     [rsp+58h+var_30], rax
0x1400162e5  mov     [rsp+58h+var_38], rax
0x1400162ea  cmp     [rbx+1Dh], al
0x1400162ed  jnz     short loc_140016361
0x1400162ef  cmp     [rbx+1Eh], al
0x1400162f2  jnz     short loc_140016361
0x1400162f4  mov     al, [rbx+1Ch]
0x1400162f7  lea     r9, [rsp+58h+var_28]
0x1400162fc  mov     ecx, [rbx+18h]
0x1400162ff  lea     r8, [rsp+58h+var_30]
0x140016304  xor     edx, edx
0x140016306  sub     al, 2
0x140016308  cmp     al, 1
0x14001630a  setnbe  dl
0x14001630d  call    cs:__imp_RtlQueryFeatureConfiguration
0x140016314  nop     dword ptr [rax+rax+00h]
0x140016319  cmp     eax, 80000022h
0x14001631e  jnz     short loc_140016366
0x140016320  mov     [rsp+58h+var_38], 0
0x140016329  mov     dword ptr [rsp+58h+var_38], 206h
0x140016331  mov     rdx, [rsp+58h+var_38]
0x140016336  mov     rax, [rbx]
0x140016339  lea     rcx, [rbx+38h]
0x14001633d  mov     [rax], rdx
0x140016340  call    wil_details_FeatureDescriptors_SkipPadding
0x140016345  mov     rbx, rax
0x140016348  test    rax, rax
0x14001634b  jnz     short loc_140016336
0x14001634d  mov     rcx, [rsp+58h+var_18]
0x140016352  xor     rcx, rsp; StackCookie
0x140016355  call    __security_check_cookie
0x14001635a  add     rsp, 50h
0x14001635e  pop     rbx
0x14001635f  retn
0x140016361  mov     eax, 0C0000225h
0x140016366  lea     r8, [rsp+58h+var_38]
0x14001636b  mov     ecx, eax
0x14001636d  lea     rdx, [rsp+58h+var_28]
0x140016372  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140016377  mov     rcx, [rbx]
0x14001637a  mov     rax, [rsp+58h+var_38]
0x14001637f  mov     [rcx], rax
0x140016382  lea     rcx, [rbx+38h]
0x140016386  jmp     loc_1400162C8
```
