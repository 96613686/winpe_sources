# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14002b138`
- end: `0x14002b21d`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002b078`

## callees

- `0x140011224`
- `0x140013950`
- `0x14002138c`
- `0x14002b138`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002b191`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002b191`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 *i; // rcx
  unsigned int v1; // eax
  __int64 v2; // rdx
  __int64 result; // rax
  _QWORD **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v4 + 7) )
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
0x14002b138  push    rbx
0x14002b13a  sub     rsp, 50h
0x14002b13e  mov     rax, cs:__security_cookie
0x14002b145  xor     rax, rsp
0x14002b148  mov     [rsp+58h+var_18], rax
0x14002b14d  lea     rcx, wil_details_featureDescriptors_a
0x14002b154  jmp     loc_14002B20A
0x14002b159  xor     eax, eax
0x14002b15b  mov     [rsp+58h+var_28], rax
0x14002b160  mov     [rsp+58h+var_20], eax
0x14002b164  mov     [rsp+58h+var_30], rax
0x14002b169  mov     [rsp+58h+var_38], rax
0x14002b16e  cmp     [rbx+1Dh], al
0x14002b171  jnz     short loc_14002B1E5
0x14002b173  cmp     [rbx+1Eh], al
0x14002b176  jnz     short loc_14002B1E5
0x14002b178  mov     al, [rbx+1Ch]
0x14002b17b  lea     r9, [rsp+58h+var_28]
0x14002b180  mov     ecx, [rbx+18h]
0x14002b183  lea     r8, [rsp+58h+var_30]
0x14002b188  xor     edx, edx
0x14002b18a  sub     al, 2
0x14002b18c  cmp     al, 1
0x14002b18e  setnbe  dl
0x14002b191  call    cs:__imp_RtlQueryFeatureConfiguration
0x14002b198  nop     dword ptr [rax+rax+00h]
0x14002b19d  cmp     eax, 80000022h
0x14002b1a2  jnz     short loc_14002B1EA
0x14002b1a4  mov     [rsp+58h+var_38], 0
0x14002b1ad  mov     dword ptr [rsp+58h+var_38], 206h
0x14002b1b5  mov     rdx, [rsp+58h+var_38]
0x14002b1ba  mov     rax, [rbx]
0x14002b1bd  lea     rcx, [rbx+38h]
0x14002b1c1  mov     [rax], rdx
0x14002b1c4  call    wil_details_FeatureDescriptors_SkipPadding
0x14002b1c9  mov     rbx, rax
0x14002b1cc  test    rax, rax
0x14002b1cf  jnz     short loc_14002B1BA
0x14002b1d1  mov     rcx, [rsp+58h+var_18]
0x14002b1d6  xor     rcx, rsp; StackCookie
0x14002b1d9  call    __security_check_cookie
0x14002b1de  add     rsp, 50h
0x14002b1e2  pop     rbx
0x14002b1e3  retn
0x14002b1e5  mov     eax, 0C0000225h
0x14002b1ea  lea     r8, [rsp+58h+var_38]
0x14002b1ef  mov     ecx, eax
0x14002b1f1  lea     rdx, [rsp+58h+var_28]
0x14002b1f6  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14002b1fb  mov     rcx, [rbx]
0x14002b1fe  mov     rax, [rsp+58h+var_38]
0x14002b203  mov     [rcx], rax
0x14002b206  lea     rcx, [rbx+38h]
0x14002b20a  call    wil_details_FeatureDescriptors_SkipPadding
0x14002b20f  mov     rbx, rax
0x14002b212  test    rax, rax
0x14002b215  jnz     loc_14002B159
0x14002b21b  jmp     short loc_14002B1D1
```
