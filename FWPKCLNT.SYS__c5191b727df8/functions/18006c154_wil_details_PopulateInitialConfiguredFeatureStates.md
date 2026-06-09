# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x18006c154`
- end: `0x18006c239`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006c078`

## callees

- `0x18000cec4`
- `0x1800203c0`
- `0x180052bcc`
- `0x18006c154`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18006c1ad`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x18006c1ad`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  _UNKNOWN **i; // rcx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 result; // rax
  _QWORD **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  int v7; // [rsp+30h] [rbp-28h]
  __int64 v8; // [rsp+38h] [rbp-20h] BYREF

  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (_QWORD **)result;
    if ( !result )
      break;
    v6 = 0;
    v7 = 0;
    v8 = 0;
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
             &v8,
             &v6);
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
    wil_details_BuildFeatureStateCacheFromQueryResults(v1, &v6, &v5);
    **v4 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x18006c154  push    rbx
0x18006c156  sub     rsp, 50h
0x18006c15a  mov     rax, cs:__security_cookie
0x18006c161  xor     rax, rsp
0x18006c164  mov     [rsp+58h+var_18], rax
0x18006c169  lea     rcx, wil_details_featureDescriptors_a
0x18006c170  jmp     loc_18006C226
0x18006c175  xor     eax, eax
0x18006c177  mov     [rsp+58h+var_30], rax
0x18006c17c  mov     [rsp+58h+var_28], eax
0x18006c180  mov     [rsp+58h+var_20], rax
0x18006c185  mov     [rsp+58h+var_38], rax
0x18006c18a  cmp     [rbx+1Dh], al
0x18006c18d  jnz     short loc_18006C201
0x18006c18f  cmp     [rbx+1Eh], al
0x18006c192  jnz     short loc_18006C201
0x18006c194  mov     al, [rbx+1Ch]
0x18006c197  lea     r9, [rsp+58h+var_30]
0x18006c19c  mov     ecx, [rbx+18h]
0x18006c19f  lea     r8, [rsp+58h+var_20]
0x18006c1a4  xor     edx, edx
0x18006c1a6  sub     al, 2
0x18006c1a8  cmp     al, 1
0x18006c1aa  setnbe  dl
0x18006c1ad  call    cs:__imp_RtlQueryFeatureConfiguration
0x18006c1b4  nop     dword ptr [rax+rax+00h]
0x18006c1b9  cmp     eax, 80000022h
0x18006c1be  jnz     short loc_18006C206
0x18006c1c0  mov     [rsp+58h+var_38], 0
0x18006c1c9  mov     dword ptr [rsp+58h+var_38], 206h
0x18006c1d1  mov     rdx, [rsp+58h+var_38]
0x18006c1d6  mov     rax, [rbx]
0x18006c1d9  lea     rcx, [rbx+38h]
0x18006c1dd  mov     [rax], rdx
0x18006c1e0  call    wil_details_FeatureDescriptors_SkipPadding
0x18006c1e5  mov     rbx, rax
0x18006c1e8  test    rax, rax
0x18006c1eb  jnz     short loc_18006C1D6
0x18006c1ed  mov     rcx, [rsp+58h+var_18]
0x18006c1f2  xor     rcx, rsp; StackCookie
0x18006c1f5  call    __security_check_cookie
0x18006c1fa  add     rsp, 50h
0x18006c1fe  pop     rbx
0x18006c1ff  retn
0x18006c201  mov     eax, 0C0000225h
0x18006c206  lea     r8, [rsp+58h+var_38]
0x18006c20b  mov     ecx, eax
0x18006c20d  lea     rdx, [rsp+58h+var_30]
0x18006c212  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x18006c217  mov     rcx, [rbx]
0x18006c21a  mov     rax, [rsp+58h+var_38]
0x18006c21f  mov     [rcx], rax
0x18006c222  lea     rcx, [rbx+38h]
0x18006c226  call    wil_details_FeatureDescriptors_SkipPadding
0x18006c22b  mov     rbx, rax
0x18006c22e  test    rax, rax
0x18006c231  jnz     loc_18006C175
0x18006c237  jmp     short loc_18006C1ED
```
