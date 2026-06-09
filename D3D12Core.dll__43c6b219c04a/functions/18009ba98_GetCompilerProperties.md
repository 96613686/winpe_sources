# GetCompilerProperties

- ea: `0x18009ba98`
- end: `0x18009bd52`
- name: `GetCompilerProperties`
- size: `698`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012b770`
- `0x18012c8a4`

## callees

- `0x180074d90`
- `0x18007f054`
- `0x18009ba98`
- `0x18009bd64`
- `0x18009bdb0`
- `0x18009d704`
- `0x1800af350`
- `0x1800bb480`
- `0x1800bc094`
- `0x18012cc6c`
- `0x1802246e0`
- `0x18022473c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18009bc41`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18009bc41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009bb3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009bb3f`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18009bb50`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18009bb50`

## string_xrefs

- `0x18009bb00`: `UserModeDriverCompilerWow`
- `0x18009bbed`: `Query for adapter compiler plugin failed, skipping target.`
- `0x18009bad6`: `UserModeDriverCompiler`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall GetCompilerProperties(void *a1, __int64 *a2, unsigned int *a3, __int64 a4)
{
  __int64 ApplicationProfileVersion; // r15
  HANDLE CurrentProcess; // rax
  unsigned __int16 *v10; // rax
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // r14
  __int64 v13; // rsi
  unsigned int v14; // r8d
  int Status; // eax
  int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // r9
  unsigned __int16 *Sz; // rax
  _QWORD *v20; // rbx
  _OWORD *result; // rax
  _OWORD *v22; // rcx
  __int64 v23; // rdx
  __int16 v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v25; // [rsp+38h] [rbp-C8h]
  __int64 v26; // [rsp+40h] [rbp-C0h]
  _DWORD *v27; // [rsp+48h] [rbp-B8h]
  _BYTE v28[288]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[128]; // [rsp+170h] [rbp+70h] BYREF
  _OWORD v30[3]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v31; // [rsp+220h] [rbp+120h]
  __int128 v32; // [rsp+228h] [rbp+128h] BYREF
  _OWORD v33[2]; // [rsp+238h] [rbp+138h]

  v27 = a3;
  v32 = *(_OWORD *)L"UserModeDriverCompiler";
  v33[0] = *(_OWORD *)L"DriverCompiler";
  *(_OWORD *)((char *)v33 + 14) = *(_OWORD *)L"ompiler";
  v30[0] = *(_OWORD *)L"UserModeDriverCompilerWow";
  v30[1] = *(_OWORD *)L"DriverCompilerWow";
  v30[2] = *(_OWORD *)L"mpilerWow";
  v31 = *(_DWORD *)L"w";
  ApplicationProfileVersion = 0;
  v24 = 0;
  CurrentProcess = GetCurrentProcess();
  IsWow64Process2(CurrentProcess, &v24, 0);
  v10 = (unsigned __int16 *)&v32;
  if ( v24 )
    v10 = (unsigned __int16 *)v30;
  v25 = v10;
  v11 = 0;
  v12 = *a3;
  v13 = *a2;
  v26 = a2[1];
  if ( v13 != v26 )
  {
    while ( 1 )
    {
      if ( !a1
        || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12QueryUserModeDriverCompiler>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12QueryUserModeDriverCompiler>::GetImpl'::`2'::impl) )
      {
        goto LABEL_12;
      }
      QueryAdapterRegistry::QueryAdapterRegistry((QueryAdapterRegistry *)v29, (const struct _LUID *)(v13 + 280));
      ApplicationProfileVersion = 0;
      if ( QueryAdapterRegistry::Query((QueryAdapterRegistry *)v29, v25, v14) )
        break;
      Status = QueryAdapterRegistry::GetStatus((QueryAdapterRegistry *)v29);
      v16 = Status;
      if ( Status < 0 && (unsigned int)CLayeredObject<CCommandAllocator>::AddRef((unsigned int)Status) == 1 )
        CJournal::RecordJournal(v17, v16, (__int64)"Query for adapter compiler plugin failed, skipping target.", v18, 0);
      QueryAdapterRegistry::~QueryAdapterRegistry((QueryAdapterRegistry *)v29);
LABEL_15:
      v13 += 288;
      if ( v13 == v26 )
        goto LABEL_16;
    }
    Sz = (unsigned __int16 *)QueryAdapterRegistry::GetSz((QueryAdapterRegistry *)v29);
    ApplicationProfileVersion = QueryApplicationProfileVersion(Sz, (unsigned __int16 *)v13, a1);
    QueryAdapterRegistry::~QueryAdapterRegistry((QueryAdapterRegistry *)v29);
LABEL_12:
    if ( v11 < v12 )
    {
      v20 = (_QWORD *)(a4 + 288 * v11);
      _o_wcscpy_s(v20, 128, v13);
      v20[32] = *(_QWORD *)(v13 + 256);
      v20[33] = *(_QWORD *)(v13 + 264);
      v20[34] = *(_QWORD *)(v13 + 272);
      v20[35] = ApplicationProfileVersion;
    }
    ++v11;
    ApplicationProfileVersion = 0;
    goto LABEL_15;
  }
LABEL_16:
  result = v27;
  *v27 = v11;
  while ( v11 < v12 )
  {
    memset_0(v28, 0, sizeof(v28));
    v22 = (_OWORD *)(a4 + 288 * v11);
    result = v28;
    v23 = 2;
    do
    {
      *v22 = *result;
      v22[1] = result[1];
      v22[2] = result[2];
      v22[3] = result[3];
      v22[4] = result[4];
      v22[5] = result[5];
      v22[6] = result[6];
      v22[7] = result[7];
      v22 += 8;
      result += 8;
      --v23;
    }
    while ( v23 );
    *v22 = *result;
    v22[1] = result[1];
    ++v11;
  }
  return result;
}

```

## disassembly

```asm
0x18009ba98  push    rbp
0x18009ba9a  push    rbx
0x18009ba9b  push    rsi
0x18009ba9c  push    rdi
0x18009ba9d  push    r12
0x18009ba9f  push    r13
0x18009baa1  push    r14
0x18009baa3  push    r15
0x18009baa5  lea     rbp, [rsp-168h]
0x18009baad  sub     rsp, 268h
0x18009bab4  mov     rax, cs:__security_cookie
0x18009babb  xor     rax, rsp
0x18009babe  mov     [rbp+1A0h+var_48], rax
0x18009bac5  mov     r13, r9
0x18009bac8  mov     rsi, r8
0x18009bacb  mov     [rsp+2A0h+var_258], r8
0x18009bad0  mov     rbx, rdx
0x18009bad3  mov     r12, rcx
0x18009bad6  movups  xmm0, xmmword ptr cs:aUsermodedriver_0; "UserModeDriverCompiler"
0x18009badd  movups  [rbp+1A0h+var_78], xmm0
0x18009bae4  movups  xmm1, xmmword ptr cs:aUsermodedriver_0+10h; "DriverCompiler"
0x18009baeb  movups  xmmword ptr [rbp+1A0h+var_68], xmm1
0x18009baf2  movups  xmm0, xmmword ptr cs:aUsermodedriver_0+1Eh; "ompiler"
0x18009baf9  movups  xmmword ptr [rbp+1A0h+var_68+0Eh], xmm0
0x18009bb00  movups  xmm1, xmmword ptr cs:aUsermodedriver; "UserModeDriverCompilerWow"
0x18009bb07  movups  [rbp+1A0h+var_B0], xmm1
0x18009bb0e  movups  xmm0, xmmword ptr cs:aUsermodedriver+10h; "DriverCompilerWow"
0x18009bb15  movups  [rbp+1A0h+var_A0], xmm0
0x18009bb1c  movups  xmm1, xmmword ptr cs:aUsermodedriver+20h; "mpilerWow"
0x18009bb23  movups  [rbp+1A0h+var_90], xmm1
0x18009bb2a  mov     eax, dword ptr cs:aUsermodedriver+30h; "w"
0x18009bb30  mov     [rbp+1A0h+var_80], eax
0x18009bb36  xor     r15d, r15d
0x18009bb39  mov     [rsp+2A0h+var_270], r15w
0x18009bb3f  call    cs:__imp_GetCurrentProcess
0x18009bb45  mov     rcx, rax
0x18009bb48  xor     r8d, r8d
0x18009bb4b  lea     rdx, [rsp+2A0h+var_270]
0x18009bb50  call    cs:__imp_IsWow64Process2
0x18009bb56  lea     rax, [rbp+1A0h+var_78]
0x18009bb5d  lea     rcx, [rbp+1A0h+var_B0]
0x18009bb64  cmp     [rsp+2A0h+var_270], r15w
0x18009bb6a  cmovnz  rax, rcx
0x18009bb6e  mov     [rsp+2A0h+var_268], rax
0x18009bb73  mov     edi, r15d
0x18009bb76  mov     r14d, [rsi]
0x18009bb79  mov     rsi, [rbx]
0x18009bb7c  mov     rax, [rbx+8]
0x18009bb80  mov     [rsp+2A0h+var_260], rax
0x18009bb85  cmp     rsi, rax
0x18009bb88  jz      loc_18009BC90
0x18009bb8e  test    r12, r12
0x18009bb91  jz      loc_18009BC26
0x18009bb97  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12QueryUserModeDriverCompiler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12QueryUserModeDriverCompiler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12QueryUserModeDriverCompiler> `wil::Feature<__WilFeatureTraits_Feature_D3D12QueryUserModeDriverCompiler>::GetImpl(void)'::`2'::impl
0x18009bb9e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12QueryUserModeDriverCompiler@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12QueryUserModeDriverCompiler>::__private_IsEnabled(void)
0x18009bba3  test    al, al
0x18009bba5  jz      short loc_18009BC26
0x18009bba7  lea     rdx, [rsi+118h]; struct _LUID *
0x18009bbae  lea     rcx, [rbp+1A0h+var_130]; this
0x18009bbb2  call    ??0QueryAdapterRegistry@@QEAA@AEBU_LUID@@@Z; QueryAdapterRegistry::QueryAdapterRegistry(_LUID const &)
0x18009bbb7  nop
0x18009bbb8  mov     rdx, [rsp+2A0h+var_268]; unsigned __int16 *
0x18009bbbd  lea     rcx, [rbp+1A0h+var_130]; this
0x18009bbc1  call    ?Query@QueryAdapterRegistry@@QEAA_NPEBGK@Z; QueryAdapterRegistry::Query(ushort const *,ulong)
0x18009bbc6  xor     r15d, r15d
0x18009bbc9  lea     rcx, [rbp+1A0h+var_130]; this
0x18009bbcd  test    al, al
0x18009bbcf  jnz     short loc_18009BC07
0x18009bbd1  call    ?GetStatus@QueryAdapterRegistry@@QEAAJXZ; QueryAdapterRegistry::GetStatus(void)
0x18009bbd6  mov     ebx, eax
0x18009bbd8  test    eax, eax
0x18009bbda  jns     short loc_18009BBFC
0x18009bbdc  mov     ecx, eax
0x18009bbde  call    ?AddRef@?$CLayeredObject@VCCommandAllocator@@@@UEAAKXZ; CLayeredObject<CCommandAllocator>::AddRef(void)
0x18009bbe3  cmp     eax, 1
0x18009bbe6  jnz     short loc_18009BBFC
0x18009bbe8  mov     [rsp+2A0h+var_280], r15d
0x18009bbed  lea     r8, aQueryForAdapte; "Query for adapter compiler plugin faile"...
0x18009bbf4  mov     edx, ebx
0x18009bbf6  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18009bbfb  nop
0x18009bbfc  lea     rcx, [rbp+1A0h+var_130]; this
0x18009bc00  call    ??1QueryAdapterRegistry@@QEAA@XZ; QueryAdapterRegistry::~QueryAdapterRegistry(void)
0x18009bc05  jmp     short loc_18009BC7E
0x18009bc07  call    ?GetSz@QueryAdapterRegistry@@QEAAPEBGXZ; QueryAdapterRegistry::GetSz(void)
0x18009bc0c  mov     rcx, rax
0x18009bc0f  mov     r8, r12
0x18009bc12  mov     rdx, rsi
0x18009bc15  call    QueryApplicationProfileVersion
0x18009bc1a  mov     r15, rax
0x18009bc1d  lea     rcx, [rbp+1A0h+var_130]; this
0x18009bc21  call    ??1QueryAdapterRegistry@@QEAA@XZ; QueryAdapterRegistry::~QueryAdapterRegistry(void)
0x18009bc26  cmp     rdi, r14
0x18009bc29  jnb     short loc_18009BC78
0x18009bc2b  lea     rbx, [rdi+rdi*8]
0x18009bc2f  shl     rbx, 5
0x18009bc33  add     rbx, r13
0x18009bc36  mov     r8, rsi
0x18009bc39  mov     edx, 80h
0x18009bc3e  mov     rcx, rbx
0x18009bc41  call    cs:__imp__o_wcscpy_s
0x18009bc47  mov     rax, [rsi+100h]
0x18009bc4e  mov     [rbx+100h], rax
0x18009bc55  mov     rax, [rsi+108h]
0x18009bc5c  mov     [rbx+108h], rax
0x18009bc63  mov     rax, [rsi+110h]
0x18009bc6a  mov     [rbx+110h], rax
0x18009bc71  mov     [rbx+118h], r15
0x18009bc78  inc     rdi
0x18009bc7b  xor     r15d, r15d
0x18009bc7e  add     rsi, 120h
0x18009bc85  cmp     rsi, [rsp+2A0h+var_260]
0x18009bc8a  jnz     loc_18009BB8E
0x18009bc90  mov     rax, [rsp+2A0h+var_258]
0x18009bc95  mov     [rax], edi
0x18009bc97  jmp     loc_18009BD26
0x18009bc9c  xor     edx, edx; Val
0x18009bc9e  mov     r8d, 120h; Size
0x18009bca4  lea     rcx, [rsp+2A0h+var_250]; void *
0x18009bca9  call    memset_0
0x18009bcae  lea     rcx, [rdi+rdi*8]
0x18009bcb2  shl     rcx, 5
0x18009bcb6  add     rcx, r13
0x18009bcb9  lea     rax, [rsp+2A0h+var_250]
0x18009bcbe  mov     edx, 2
0x18009bcc3  movups  xmm0, xmmword ptr [rax]
0x18009bcc6  movups  xmmword ptr [rcx], xmm0
0x18009bcc9  movups  xmm1, xmmword ptr [rax+10h]
0x18009bccd  movups  xmmword ptr [rcx+10h], xmm1
0x18009bcd1  movups  xmm0, xmmword ptr [rax+20h]
0x18009bcd5  movups  xmmword ptr [rcx+20h], xmm0
0x18009bcd9  movups  xmm1, xmmword ptr [rax+30h]
0x18009bcdd  movups  xmmword ptr [rcx+30h], xmm1
0x18009bce1  movups  xmm0, xmmword ptr [rax+40h]
0x18009bce5  movups  xmmword ptr [rcx+40h], xmm0
0x18009bce9  movups  xmm1, xmmword ptr [rax+50h]
0x18009bced  movups  xmmword ptr [rcx+50h], xmm1
0x18009bcf1  movups  xmm0, xmmword ptr [rax+60h]
0x18009bcf5  movups  xmmword ptr [rcx+60h], xmm0
0x18009bcf9  movups  xmm1, xmmword ptr [rax+70h]
0x18009bcfd  movups  xmmword ptr [rcx+70h], xmm1
0x18009bd01  lea     rcx, [rcx+80h]
0x18009bd08  lea     rax, [rax+80h]
0x18009bd0f  sub     rdx, 1
0x18009bd13  jnz     short loc_18009BCC3
0x18009bd15  movups  xmm0, xmmword ptr [rax]
0x18009bd18  movups  xmmword ptr [rcx], xmm0
0x18009bd1b  movups  xmm1, xmmword ptr [rax+10h]
0x18009bd1f  movups  xmmword ptr [rcx+10h], xmm1
0x18009bd23  inc     rdi
0x18009bd26  cmp     rdi, r14
0x18009bd29  jb      loc_18009BC9C
0x18009bd2f  mov     rcx, [rbp+1A0h+var_48]
0x18009bd36  xor     rcx, rsp; StackCookie
0x18009bd39  call    __security_check_cookie
0x18009bd3e  add     rsp, 268h
0x18009bd45  pop     r15
0x18009bd47  pop     r14
0x18009bd49  pop     r13
0x18009bd4b  pop     r12
0x18009bd4d  pop     rdi
0x18009bd4e  pop     rsi
0x18009bd4f  pop     rbx
0x18009bd50  pop     rbp
0x18009bd51  retn
```
