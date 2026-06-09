# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000ba2c`
- end: `0x18000bb51`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000711c`

## callees

- `0x1800021d0`
- `0x18000b670`
- `0x18000ba2c`
- `0x180024010`

## string_xrefs

- `0x18000ba78`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v9; // r8d
  unsigned int v10; // r9d
  int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // ecx
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+38h] [rbp-30h] BYREF
  int v17; // [rsp+40h] [rbp-28h]

  v15 = 0;
  v7 = a3 == 0;
  v16 = 0;
  v17 = 0;
  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
    {
      v9 = -1073741511;
LABEL_4:
      v10 = 0;
      goto LABEL_5;
    }
  }
  v12 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v7, &v15, &v16);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 != 279 )
      goto LABEL_4;
    v10 = 1;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v16) >> 7) & 1;
  }
  else
  {
    v13 = HIDWORD(v16);
    v10 = 1;
    v14 = HIDWORD(v16);
    *(_DWORD *)(a1 + 12) = v17;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v14 >> 14;
    *(_DWORD *)a1 = (v14 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v13) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v13 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v13 >> 6) & 1;
  }
LABEL_5:
  if ( a4 )
    *a4 = v9 != -2147483614;
  return v10;
}

```

## disassembly

```asm
0x18000ba2c  mov     [rsp+arg_10], rbx
0x18000ba31  push    rbp
0x18000ba32  push    rsi
0x18000ba33  push    rdi
0x18000ba34  sub     rsp, 50h
0x18000ba38  mov     rax, cs:__security_cookie
0x18000ba3f  xor     rax, rsp
0x18000ba42  mov     [rsp+68h+var_20], rax
0x18000ba47  xor     esi, esi
0x18000ba49  mov     [rsp+68h+var_38], 0
0x18000ba52  test    r8d, r8d
0x18000ba55  mov     rdi, r9
0x18000ba58  mov     ebp, edx
0x18000ba5a  mov     rbx, rcx
0x18000ba5d  setz    sil
0x18000ba61  xor     eax, eax
0x18000ba63  mov     [rsp+68h+var_30], rax
0x18000ba68  mov     [rsp+68h+var_28], eax
0x18000ba6c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000ba73  test    rax, rax
0x18000ba76  jnz     short loc_18000BACC
0x18000ba78  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000ba7f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000ba84  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000ba8b  test    rax, rax
0x18000ba8e  jnz     short loc_18000BACC
0x18000ba90  mov     r8d, 0C0000139h
0x18000ba96  xor     r9d, r9d
0x18000ba99  test    rdi, rdi
0x18000ba9c  jz      short loc_18000BAAC
0x18000ba9e  xor     ecx, ecx
0x18000baa0  cmp     r8d, 80000022h
0x18000baa7  setnz   cl
0x18000baaa  mov     [rdi], ecx
0x18000baac  mov     eax, r9d
0x18000baaf  mov     rcx, [rsp+68h+var_20]
0x18000bab4  xor     rcx, rsp; StackCookie
0x18000bab7  call    __security_check_cookie
0x18000babc  mov     rbx, [rsp+68h+arg_10]
0x18000bac4  add     rsp, 50h
0x18000bac8  pop     rdi
0x18000bac9  pop     rsi
0x18000baca  pop     rbp
0x18000bacb  retn
0x18000bacc  lea     r9, [rsp+68h+var_30]
0x18000bad1  mov     edx, esi
0x18000bad3  lea     r8, [rsp+68h+var_38]
0x18000bad8  mov     ecx, ebp
0x18000bada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000badf  mov     r8d, eax
0x18000bae2  test    eax, eax
0x18000bae4  jnz     short loc_18000BB2E
0x18000bae6  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000baea  lea     r9d, [r8+1]
0x18000baee  mov     eax, [rsp+68h+var_28]
0x18000baf2  mov     ecx, edx
0x18000baf4  mov     [rbx+0Ch], eax
0x18000baf7  mov     eax, edx
0x18000baf9  shr     eax, 0Eh
0x18000bafc  shr     ecx, 4
0x18000baff  and     eax, 3
0x18000bb02  and     ecx, 3
0x18000bb05  mov     [rbx+8], eax
0x18000bb08  mov     [rbx], ecx
0x18000bb0a  mov     eax, edx
0x18000bb0c  mov     ecx, edx
0x18000bb0e  shr     eax, 6
0x18000bb11  shr     ecx, 8
0x18000bb14  and     eax, r9d
0x18000bb17  and     cl, 3Fh
0x18000bb1a  shr     edx, 7
0x18000bb1d  and     edx, r9d
0x18000bb20  mov     [rbx+4], cl
0x18000bb23  mov     [rbx+10h], edx
0x18000bb26  mov     [rbx+14h], eax
0x18000bb29  jmp     loc_18000BA99
0x18000bb2e  cmp     eax, 117h
0x18000bb33  jnz     loc_18000BA96
0x18000bb39  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000bb3d  mov     r9d, 1
0x18000bb43  shr     eax, 7
0x18000bb46  and     eax, r9d
0x18000bb49  mov     [rbx+10h], eax
0x18000bb4c  jmp     loc_18000BA99
```
