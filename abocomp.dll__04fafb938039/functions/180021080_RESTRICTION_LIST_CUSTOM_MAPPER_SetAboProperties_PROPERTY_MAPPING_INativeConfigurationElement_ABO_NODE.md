# RESTRICTION_LIST_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x180021080`
- end: `0x18002155b`
- name: `?SetAboProperties@RESTRICTION_LIST_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `1243`
- prototype: `int(RESTRICTION_LIST_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x18000341a`
- `0x180003460`
- `0x18000a838`
- `0x180021080`
- `0x180026a60`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211a1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002136e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002136e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800210d9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800210fe`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800210d9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800210fe`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021523`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002152d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021523`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002152d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180021382`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002143c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180021382`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002143c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002138f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800213aa`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800213d0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800213e9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002140f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180021428`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002138f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800213aa`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800213d0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800213e9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002140f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180021428`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180021108`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180021108`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x1800214ae`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x1800214ae`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180021197`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180021207`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180021449`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180021197`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180021207`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180021449`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x1800214bc`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x1800214bc`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180021519`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180021519`

## string_xrefs

- `0x1800211f8`: `1,*.dll`
- `0x1800211f1`: `0,*.dll`

## pseudocode

```c
__int64 __fastcall RESTRICTION_LIST_CUSTOM_MAPPER::SetAboProperties(
        RESTRICTION_LIST_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  signed int v7; // ebx
  const unsigned __int16 *v8; // rdx
  signed int LastError; // eax
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // edi
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v14; // rax
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v20; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v21; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSrc; // [rsp+60h] [rbp-A0h] BYREF
  struct _METADATA_RECORD v23; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v24[56]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v25[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v26[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v27[256]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v28[256]; // [rsp+340h] [rbp+240h] BYREF

  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v24, v27, 0x100u);
  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v26, v28, 0x100u);
  MULTISZ::MULTISZ((MULTISZ *)v25);
  v17 = 0;
  v19 = 0;
  v18 = 0;
  lpSrc = 0;
  v20 = 0;
  v21 = 0;
  v16 = 0;
  if ( a2 && a3 && a4 )
  {
    v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)a3 + 72LL))(
           a3,
           L"notListedCgisAllowed",
           &v16,
           0,
           0);
    if ( v7 < 0 )
      goto LABEL_38;
    v8 = L"1,*.exe";
    if ( !v16 )
      v8 = L"0,*.exe";
    if ( !MULTISZ::Append((MULTISZ *)v25, v8) )
      goto LABEL_8;
    v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)a3 + 72LL))(
           a3,
           L"notListedIsapisAllowed",
           &v16,
           0,
           0);
    if ( v7 < 0 )
      goto LABEL_38;
    v10 = L"1,*.dll";
    if ( !v16 )
      v10 = L"0,*.dll";
    if ( MULTISZ::Append((MULTISZ *)v25, v10) )
    {
      v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a3 + 40LL))(a3, &v19);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 24LL))(v19, &v18);
        if ( v7 >= 0 )
        {
          v11 = 0;
          if ( v18 )
          {
            while ( 1 )
            {
              v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 32LL))(v19, v11, &v17);
              if ( v7 < 0 )
                break;
              v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                     v17,
                     L"path",
                     &lpSrc,
                     0,
                     0);
              if ( v7 < 0 )
                break;
              v7 = ExpandEnvironmentVariables(lpSrc, (struct STRU *)v26);
              if ( v7 < 0 )
                break;
              v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v17 + 72LL))(
                     v17,
                     L"allowed",
                     &v16,
                     0,
                     0);
              if ( v7 < 0 )
                break;
              v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                     v17,
                     L"groupId",
                     &v20,
                     0,
                     0);
              if ( v7 < 0 )
                break;
              v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                     v17,
                     L"description",
                     &v21,
                     0,
                     0);
              if ( v7 < 0 )
                break;
              v12 = L"1,";
              if ( !v16 )
                v12 = L"0,";
              v7 = STRU::Copy((STRU *)v24, v12);
              if ( v7 < 0 )
                break;
              Str = STRU::QueryStr((STRU *)v26);
              v7 = STRU::Append((STRU *)v24, Str);
              if ( v7 < 0 )
                break;
              v7 = STRU::Append((STRU *)v24, L",1");
              if ( v7 < 0 )
                break;
              if ( *v20 )
              {
                v7 = STRU::Append((STRU *)v24, L",");
                if ( v7 < 0 )
                  break;
                v7 = STRU::Append((STRU *)v24, v20);
                if ( v7 < 0 )
                  break;
              }
              if ( *v21 )
              {
                v7 = STRU::Append((STRU *)v24, L",");
                if ( v7 < 0 )
                  break;
                v7 = STRU::Append((STRU *)v24, v21);
                if ( v7 < 0 )
                  break;
              }
              v14 = STRU::QueryStr((STRU *)v24);
              if ( !MULTISZ::Append((MULTISZ *)v25, v14) )
                goto LABEL_8;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              ++v11;
              v17 = 0;
              if ( v11 >= v18 )
                goto LABEL_36;
            }
          }
          else
          {
LABEL_36:
            v23.dwMDIdentifier = *((_DWORD *)a2 + 36);
            v23.dwMDUserType = *((_DWORD *)a2 + 37);
            v23.dwMDDataType = *((_DWORD *)a2 + 38);
            v23.dwMDAttributes = *((_DWORD *)a2 + 39);
            *(&v23.dwMDDataLen + 1) = 0;
            *(_QWORD *)&v23.dwMDDataTag = 0;
            v23.pbMDData = (unsigned __int8 *)MULTISZ::QueryStr((MULTISZ *)v25);
            v23.dwMDDataLen = MULTISZ::QueryCB((MULTISZ *)v25);
            v7 = ABO_NODE::SetDataByMapping(a4, &v23, a2);
          }
        }
      }
    }
    else
    {
LABEL_8:
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v7 = -2147024809;
  }
LABEL_38:
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v25);
  STRU::~STRU((STRU *)v26);
  STRU::~STRU((STRU *)v24);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180021080  mov     [rsp-8+arg_0], rbx
0x180021085  push    rbp
0x180021086  push    rsi
0x180021087  push    rdi
0x180021088  push    r14
0x18002108a  push    r15
0x18002108c  lea     rbp, [rsp-450h]
0x180021094  sub     rsp, 550h
0x18002109b  mov     rax, cs:__security_cookie
0x1800210a2  xor     rax, rsp
0x1800210a5  mov     [rbp+470h+var_30], rax
0x1800210ac  mov     rdi, r8
0x1800210af  lea     rcx, [rbp+470h+var_430]; void *
0x1800210b3  mov     rsi, rdx
0x1800210b6  mov     r15d, 200h
0x1800210bc  mov     r8d, r15d; Size
0x1800210bf  xor     edx, edx; Val
0x1800210c1  mov     r14, r9
0x1800210c4  call    memset_0
0x1800210c9  mov     ebx, 100h
0x1800210ce  lea     rdx, [rbp+470h+var_430]
0x1800210d2  mov     r8d, ebx
0x1800210d5  lea     rcx, [rbp+470h+var_4E0]
0x1800210d9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800210df  mov     r8d, r15d; Size
0x1800210e2  lea     rcx, [rbp+470h+var_230]; void *
0x1800210e9  xor     edx, edx; Val
0x1800210eb  call    memset_0
0x1800210f0  mov     r8d, ebx
0x1800210f3  lea     rdx, [rbp+470h+var_230]
0x1800210fa  lea     rcx, [rbp+470h+var_470]
0x1800210fe  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180021104  lea     rcx, [rbp+470h+var_4A8]
0x180021108  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18002110e  xor     r15d, r15d
0x180021111  mov     [rsp+570h+var_538], r15
0x180021116  mov     [rsp+570h+var_528], r15
0x18002111b  mov     [rsp+570h+var_530], r15d
0x180021120  mov     [rsp+570h+lpSrc], r15
0x180021125  mov     [rsp+570h+var_520], r15
0x18002112a  mov     [rsp+570h+var_518], r15
0x18002112f  mov     [rsp+570h+var_540], r15d
0x180021134  test    rsi, rsi
0x180021137  jz      loc_1800214DA
0x18002113d  test    rdi, rdi
0x180021140  jz      loc_1800214DA
0x180021146  test    r14, r14
0x180021149  jz      loc_1800214DA
0x18002114f  mov     rax, [rdi]
0x180021152  lea     r8, [rsp+570h+var_540]
0x180021157  xor     r9d, r9d
0x18002115a  mov     [rsp+570h+var_550], r15
0x18002115f  lea     rdx, aNotlistedcgisa; "notListedCgisAllowed"
0x180021166  mov     rcx, rdi
0x180021169  mov     rax, [rax+48h]
0x18002116d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021172  mov     ebx, eax
0x180021174  test    eax, eax
0x180021176  js      loc_1800214DF
0x18002117c  cmp     [rsp+570h+var_540], r15d
0x180021181  lea     rax, a0Exe; "0,*.exe"
0x180021188  lea     rdx, a1Exe; "1,*.exe"
0x18002118f  cmovz   rdx, rax
0x180021193  lea     rcx, [rbp+470h+var_4A8]
0x180021197  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18002119d  test    eax, eax
0x18002119f  jnz     short loc_1800211BF
0x1800211a1  call    cs:__imp_GetLastError
0x1800211a7  mov     ebx, eax
0x1800211a9  test    eax, eax
0x1800211ab  jle     loc_1800214DF
0x1800211b1  movzx   ebx, ax
0x1800211b4  or      ebx, 80070000h
0x1800211ba  jmp     loc_1800214DF
0x1800211bf  mov     rax, [rdi]
0x1800211c2  lea     r8, [rsp+570h+var_540]
0x1800211c7  xor     r9d, r9d
0x1800211ca  mov     [rsp+570h+var_550], r15
0x1800211cf  lea     rdx, aNotlistedisapi; "notListedIsapisAllowed"
0x1800211d6  mov     rcx, rdi
0x1800211d9  mov     rax, [rax+48h]
0x1800211dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211e2  mov     ebx, eax
0x1800211e4  test    eax, eax
0x1800211e6  js      loc_1800214DF
0x1800211ec  cmp     [rsp+570h+var_540], r15d
0x1800211f1  lea     rax, a0Dll; "0,*.dll"
0x1800211f8  lea     rdx, a1Dll; "1,*.dll"
0x1800211ff  cmovz   rdx, rax
0x180021203  lea     rcx, [rbp+470h+var_4A8]
0x180021207  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18002120d  test    eax, eax
0x18002120f  jz      short loc_1800211A1
0x180021211  mov     rax, [rdi]
0x180021214  lea     rdx, [rsp+570h+var_528]
0x180021219  mov     rcx, rdi
0x18002121c  mov     rax, [rax+28h]
0x180021220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021225  mov     ebx, eax
0x180021227  test    eax, eax
0x180021229  js      loc_1800214DF
0x18002122f  mov     rcx, [rsp+570h+var_528]
0x180021234  lea     rdx, [rsp+570h+var_530]
0x180021239  mov     rax, [rcx]
0x18002123c  mov     rax, [rax+18h]
0x180021240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021245  mov     ebx, eax
0x180021247  test    eax, eax
0x180021249  js      loc_1800214DF
0x18002124f  mov     edi, r15d
0x180021252  cmp     [rsp+570h+var_530], r15d
0x180021257  jbe     loc_180021479
0x18002125d  mov     rcx, [rsp+570h+var_528]
0x180021262  lea     r8, [rsp+570h+var_538]
0x180021267  mov     edx, edi
0x180021269  mov     rax, [rcx]
0x18002126c  mov     rax, [rax+20h]
0x180021270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021275  mov     ebx, eax
0x180021277  test    eax, eax
0x180021279  js      loc_1800214DF
0x18002127f  mov     rcx, [rsp+570h+var_538]
0x180021284  lea     r8, [rsp+570h+lpSrc]
0x180021289  xor     r9d, r9d
0x18002128c  mov     [rsp+570h+var_550], r15
0x180021291  lea     rdx, aPath; "path"
0x180021298  mov     rax, [rcx]
0x18002129b  mov     rax, [rax+40h]
0x18002129f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212a4  mov     ebx, eax
0x1800212a6  test    eax, eax
0x1800212a8  js      loc_1800214DF
0x1800212ae  mov     rcx, [rsp+570h+lpSrc]; lpSrc
0x1800212b3  lea     rdx, [rbp+470h+var_470]; struct STRU *
0x1800212b7  call    ?ExpandEnvironmentVariables@@YAJPEBGPEAVSTRU@@@Z; ExpandEnvironmentVariables(ushort const *,STRU *)
0x1800212bc  mov     ebx, eax
0x1800212be  test    eax, eax
0x1800212c0  js      loc_1800214DF
0x1800212c6  mov     rcx, [rsp+570h+var_538]
0x1800212cb  lea     r8, [rsp+570h+var_540]
0x1800212d0  xor     r9d, r9d
0x1800212d3  mov     [rsp+570h+var_550], r15
0x1800212d8  lea     rdx, aAllowed; "allowed"
0x1800212df  mov     rax, [rcx]
0x1800212e2  mov     rax, [rax+48h]
0x1800212e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212eb  mov     ebx, eax
0x1800212ed  test    eax, eax
0x1800212ef  js      loc_1800214DF
0x1800212f5  mov     rcx, [rsp+570h+var_538]
0x1800212fa  lea     r8, [rsp+570h+var_520]
0x1800212ff  xor     r9d, r9d
0x180021302  mov     [rsp+570h+var_550], r15
0x180021307  lea     rdx, aGroupid; "groupId"
0x18002130e  mov     rax, [rcx]
0x180021311  mov     rax, [rax+40h]
0x180021315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002131a  mov     ebx, eax
0x18002131c  test    eax, eax
0x18002131e  js      loc_1800214DF
0x180021324  mov     rcx, [rsp+570h+var_538]
0x180021329  lea     r8, [rsp+570h+var_518]
0x18002132e  xor     r9d, r9d
0x180021331  mov     [rsp+570h+var_550], r15
0x180021336  lea     rdx, aDescription; "description"
0x18002133d  mov     rax, [rcx]
0x180021340  mov     rax, [rax+40h]
0x180021344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021349  mov     ebx, eax
0x18002134b  test    eax, eax
0x18002134d  js      loc_1800214DF
0x180021353  cmp     [rsp+570h+var_540], r15d
0x180021358  lea     rax, a0_0; "0,"
0x18002135f  lea     rdx, a1; "1,"
0x180021366  cmovz   rdx, rax
0x18002136a  lea     rcx, [rbp+470h+var_4E0]
0x18002136e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180021374  mov     ebx, eax
0x180021376  test    eax, eax
0x180021378  js      loc_1800214DF
0x18002137e  lea     rcx, [rbp+470h+var_470]
0x180021382  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180021388  mov     rdx, rax
0x18002138b  lea     rcx, [rbp+470h+var_4E0]
0x18002138f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180021395  mov     ebx, eax
0x180021397  test    eax, eax
0x180021399  js      loc_1800214DF
0x18002139f  lea     rdx, a1_0; ",1"
0x1800213a6  lea     rcx, [rbp+470h+var_4E0]
0x1800213aa  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800213b0  mov     ebx, eax
0x1800213b2  test    eax, eax
0x1800213b4  js      loc_1800214DF
0x1800213ba  mov     rax, [rsp+570h+var_520]
0x1800213bf  cmp     [rax], r15w
0x1800213c3  jz      short loc_1800213F9
0x1800213c5  lea     rdx, asc_180032E60; ","
0x1800213cc  lea     rcx, [rbp+470h+var_4E0]
0x1800213d0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800213d6  mov     ebx, eax
0x1800213d8  test    eax, eax
0x1800213da  js      loc_1800214DF
0x1800213e0  mov     rdx, [rsp+570h+var_520]
0x1800213e5  lea     rcx, [rbp+470h+var_4E0]
0x1800213e9  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800213ef  mov     ebx, eax
0x1800213f1  test    eax, eax
0x1800213f3  js      loc_1800214DF
0x1800213f9  mov     rax, [rsp+570h+var_518]
0x1800213fe  cmp     [rax], r15w
0x180021402  jz      short loc_180021438
0x180021404  lea     rdx, asc_180032E60; ","
0x18002140b  lea     rcx, [rbp+470h+var_4E0]
0x18002140f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180021415  mov     ebx, eax
0x180021417  test    eax, eax
0x180021419  js      loc_1800214DF
0x18002141f  mov     rdx, [rsp+570h+var_518]
0x180021424  lea     rcx, [rbp+470h+var_4E0]
0x180021428  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002142e  mov     ebx, eax
0x180021430  test    eax, eax
0x180021432  js      loc_1800214DF
0x180021438  lea     rcx, [rbp+470h+var_4E0]
0x18002143c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180021442  mov     rdx, rax
0x180021445  lea     rcx, [rbp+470h+var_4A8]
0x180021449  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18002144f  test    eax, eax
0x180021451  jz      loc_1800211A1
0x180021457  mov     rcx, [rsp+570h+var_538]
0x18002145c  mov     rax, [rcx]
0x18002145f  mov     rax, [rax+10h]
0x180021463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021468  inc     edi
0x18002146a  mov     [rsp+570h+var_538], r15
0x18002146f  cmp     edi, [rsp+570h+var_530]
0x180021473  jb      loc_18002125D
0x180021479  mov     eax, [rsi+90h]
0x18002147f  lea     rcx, [rbp+470h+var_4A8]
0x180021483  mov     [rsp+570h+var_508.dwMDIdentifier], eax
0x180021487  mov     eax, [rsi+94h]
0x18002148d  mov     [rsp+570h+var_508.dwMDUserType], eax
0x180021491  mov     eax, [rsi+98h]
0x180021497  mov     [rsp+570h+var_508.dwMDDataType], eax
0x18002149b  mov     eax, [rsi+9Ch]
0x1800214a1  mov     [rsp+570h+var_508.dwMDAttributes], eax
0x1800214a5  mov     dword ptr [rsp+570h+var_508+14h], r15d
0x1800214aa  mov     qword ptr [rbp+470h+var_508.dwMDDataTag], r15
0x1800214ae  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x1800214b4  lea     rcx, [rbp+470h+var_4A8]
0x1800214b8  mov     [rbp+470h+var_508.pbMDData], rax
0x1800214bc  call    cs:__imp_?QueryCB@MULTISZ@@QEBAIXZ; MULTISZ::QueryCB(void)
0x1800214c2  mov     r8, rsi; struct PROPERTY_MAPPING *
0x1800214c5  lea     rdx, [rsp+570h+var_508]; struct _METADATA_RECORD *
0x1800214ca  mov     rcx, r14; this
0x1800214cd  mov     [rsp+570h+var_508.dwMDDataLen], eax
0x1800214d1  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x1800214d6  mov     ebx, eax
0x1800214d8  jmp     short loc_1800214DF
0x1800214da  mov     ebx, 80070057h
0x1800214df  mov     rcx, [rsp+570h+var_538]
0x1800214e4  test    rcx, rcx
0x1800214e7  jz      short loc_1800214FA
0x1800214e9  mov     rax, [rcx]
0x1800214ec  mov     rax, [rax+10h]
0x1800214f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214f5  mov     [rsp+570h+var_538], r15
0x1800214fa  mov     rcx, [rsp+570h+var_528]
0x1800214ff  test    rcx, rcx
0x180021502  jz      short loc_180021515
0x180021504  mov     rax, [rcx]
0x180021507  mov     rax, [rax+10h]
0x18002150b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021510  mov     [rsp+570h+var_528], r15
0x180021515  lea     rcx, [rbp+470h+var_4A8]
0x180021519  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18002151f  lea     rcx, [rbp+470h+var_470]
0x180021523  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180021529  lea     rcx, [rbp+470h+var_4E0]
0x18002152d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180021533  mov     eax, ebx
0x180021535  mov     rcx, [rbp+470h+var_30]
0x18002153c  xor     rcx, rsp; StackCookie
0x18002153f  call    __security_check_cookie
0x180021544  mov     rbx, [rsp+570h+arg_0]
0x18002154c  add     rsp, 550h
0x180021553  pop     r15
0x180021555  pop     r14
0x180021557  pop     rdi
0x180021558  pop     rsi
0x180021559  pop     rbp
0x18002155a  retn
```
