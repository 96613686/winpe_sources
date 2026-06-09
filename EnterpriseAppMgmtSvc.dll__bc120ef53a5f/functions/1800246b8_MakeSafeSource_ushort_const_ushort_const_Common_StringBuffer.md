# MakeSafeSource(ushort const *,ushort const *,Common::StringBuffer *)

- ea: `0x1800246b8`
- end: `0x1800249cf`
- name: `?MakeSafeSource@@YAJPEBG0PEAVStringBuffer@Common@@@Z`
- size: `791`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, const unsigned __int16 *, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002817c`

## callees

- `0x18000d3dc`
- `0x18001d65c`
- `0x180023d74`
- `0x1800246b8`
- `0x180028768`
- `0x180029444`
- `0x18006b4ec`
- `0x18006c910`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x180024773`
- `msvcrt!_wsplitpath_s` at `0x180024773`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800246f4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800248ac`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180024925`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002495f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800246f4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800248ac`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180024925`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002495f`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800248c8`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800248c8`
- `DMCmnUtils!DmRevertToSelf` at `0x180024887`
- `DMCmnUtils!DmRevertToSelf` at `0x180024900`
- `DMCmnUtils!DmRevertToSelf` at `0x18002493e`
- `DMCmnUtils!DmRevertToSelf` at `0x180024887`
- `DMCmnUtils!DmRevertToSelf` at `0x180024900`
- `DMCmnUtils!DmRevertToSelf` at `0x18002493e`

## string_xrefs

- `0x18002478d`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800247cc`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002484e`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002486e`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800248e7`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MakeSafeSource(LPCWSTR lpExistingFileName, const unsigned __int16 *a2, void **a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int appended; // edi
  __int64 v11; // rdx
  int v12; // eax
  int v13; // eax
  unsigned int v14; // r8d
  int v15; // eax
  unsigned int v16; // r8d
  int v17; // eax
  unsigned int v18; // r8d
  int DirCount; // [rsp+20h] [rbp-E0h]
  int DirCountc; // [rsp+20h] [rbp-E0h]
  int DirCounta; // [rsp+20h] [rbp-E0h]
  int DirCountb; // [rsp+20h] [rbp-E0h]
  void **v23; // [rsp+50h] [rbp-B0h] BYREF
  char v24; // [rsp+58h] [rbp-A8h]
  __int128 v25; // [rsp+60h] [rbp-A0h]
  int v26; // [rsp+70h] [rbp-90h]
  _QWORD v27[3]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Ext[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+3E8h]

  if ( a3 )
  {
    operator delete[](a3[1]);
    a3[1] = 0;
    *(_DWORD *)a3 = 0;
    *((_DWORD *)a3 + 4) = 0;
  }
  v27[1] = a3;
  v27[0] = &Common::StringBufferBuilder::`vftable';
  v27[2] = a3;
  if ( lpExistingFileName )
  {
    v6 = -1;
    do
      ++v6;
    while ( lpExistingFileName[v6] );
    if ( v6 )
    {
      if ( _wsplitpath_s(lpExistingFileName, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u) )
      {
        v7 = -2147467259;
        v8 = 208;
LABEL_9:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)v7,
          DirCount);
        return v7;
      }
      appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v27, a2);
      if ( appended < 0 )
      {
        v11 = 211;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)appended,
          DirCount);
        return (unsigned int)appended;
      }
      appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v27, Filename);
      if ( appended < 0 )
      {
        v11 = 212;
        goto LABEL_13;
      }
      appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v27, Ext);
      if ( appended < 0 )
      {
        v11 = 213;
        goto LABEL_13;
      }
      v23 = &ImpersonateUserHelper::`vftable';
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v12 = (unsigned int)ImpersonateUserHelper::ImpersonateUser((ImpersonateUser *)&v23);
      if ( v12 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xDA,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v12,
          DirCount);
        v7 = -2147024891;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)0x80070005LL,
          DirCountc);
        if ( v24 )
        {
          v13 = DmRevertToSelf();
          if ( v13 < 0 )
            wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v14, (const char *)(unsigned int)v13, DirCounta);
        }
        if ( *((_QWORD *)&v25 + 1) )
          operator delete[](*((void **)&v25 + 1));
        return v7;
      }
      if ( !CopyFileW(lpExistingFileName, (LPCWSTR)a3[1], 0) )
      {
        v7 = -2147467259;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDF,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)0x80004005LL,
          DirCount);
        if ( v24 )
        {
          v15 = DmRevertToSelf();
          if ( v15 < 0 )
            wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v16, (const char *)(unsigned int)v15, DirCountb);
        }
        if ( *((_QWORD *)&v25 + 1) )
          operator delete[](*((void **)&v25 + 1));
        return v7;
      }
      if ( v24 )
      {
        v17 = DmRevertToSelf();
        if ( v17 < 0 )
          wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v18, (const char *)(unsigned int)v17, DirCount);
      }
      if ( *((_QWORD *)&v25 + 1) )
        operator delete[](*((void **)&v25 + 1));
      v7 = TakeOwnership((LPWSTR)a3[1]);
      if ( (v7 & 0x80000000) != 0 )
      {
        v8 = 227;
        goto LABEL_9;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800246b8  push    rbp
0x1800246ba  push    rbx
0x1800246bb  push    rsi
0x1800246bc  push    rdi
0x1800246bd  push    r14
0x1800246bf  lea     rbp, [rsp-3C0h]
0x1800246c7  sub     rsp, 4C0h
0x1800246ce  mov     rax, cs:__security_cookie
0x1800246d5  xor     rax, rsp
0x1800246d8  mov     [rbp+3E0h+var_30], rax
0x1800246df  mov     rbx, r8
0x1800246e2  mov     rdi, rdx
0x1800246e5  mov     rsi, rcx
0x1800246e8  xor     r14d, r14d
0x1800246eb  test    r8, r8
0x1800246ee  jz      short loc_18002470B
0x1800246f0  mov     rcx, [r8+8]
0x1800246f4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800246fb  nop     dword ptr [rax+rax+00h]
0x180024700  mov     [rbx+8], r14
0x180024704  mov     [rbx], r14d
0x180024707  mov     [rbx+10h], r14d
0x18002470b  mov     [rbp+3E0h+var_460], rbx
0x18002470f  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180024716  mov     [rsp+4E0h+var_468], rax
0x18002471b  mov     [rbp+3E0h+var_458], rbx
0x18002471f  test    rsi, rsi
0x180024722  jz      loc_180024985
0x180024728  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002472c  inc     rax
0x18002472f  cmp     [rsi+rax*2], r14w
0x180024734  jnz     short loc_18002472C
0x180024736  test    rax, rax
0x180024739  jz      loc_180024985
0x18002473f  mov     ecx, 104h
0x180024744  mov     [rsp+4E0h+ExtCount], rcx; ExtCount
0x180024749  lea     rax, [rbp+3E0h+var_240]
0x180024750  mov     [rsp+4E0h+Ext], rax; Ext
0x180024755  mov     [rsp+4E0h+FilenameCount], rcx; FilenameCount
0x18002475a  lea     rax, [rbp+3E0h+var_450]
0x18002475e  mov     [rsp+4E0h+Filename], rax; Filename
0x180024763  mov     [rsp+4E0h+DirCount], r14; int
0x180024768  xor     r9d, r9d; Dir
0x18002476b  xor     r8d, r8d; DriveCount
0x18002476e  xor     edx, edx; Drive
0x180024770  mov     rcx, rsi; FullPath
0x180024773  call    cs:__imp__wsplitpath_s
0x18002477a  nop     dword ptr [rax+rax+00h]
0x18002477f  test    eax, eax
0x180024781  jz      short loc_1800247AA
0x180024783  mov     ebx, 80004005h
0x180024788  mov     edx, 0D0h; void *
0x18002478d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180024794  mov     r9d, ebx; char *
0x180024797  mov     rcx, [rbp+3E8h]; this
0x18002479e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800247a3  mov     eax, ebx
0x1800247a5  jmp     loc_180024987
0x1800247aa  mov     rdx, rdi; unsigned __int16 *
0x1800247ad  lea     rcx, [rsp+4E0h+var_468]; this
0x1800247b2  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800247b7  mov     edi, eax
0x1800247b9  test    eax, eax
0x1800247bb  jns     short loc_1800247DF
0x1800247bd  mov     edx, 0D3h; void *
0x1800247c2  mov     rcx, [rbp+3E8h]; this
0x1800247c9  mov     r9d, edi; char *
0x1800247cc  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800247d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800247d8  mov     eax, edi
0x1800247da  jmp     loc_180024987
0x1800247df  lea     rdx, [rbp+3E0h+var_450]; unsigned __int16 *
0x1800247e3  lea     rcx, [rsp+4E0h+var_468]; this
0x1800247e8  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800247ed  mov     edi, eax
0x1800247ef  test    eax, eax
0x1800247f1  jns     short loc_1800247FA
0x1800247f3  mov     edx, 0D4h
0x1800247f8  jmp     short loc_1800247C2
0x1800247fa  lea     rdx, [rbp+3E0h+var_240]; unsigned __int16 *
0x180024801  lea     rcx, [rsp+4E0h+var_468]; this
0x180024806  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18002480b  mov     edi, eax
0x18002480d  test    eax, eax
0x18002480f  jns     short loc_180024818
0x180024811  mov     edx, 0D5h
0x180024816  jmp     short loc_1800247C2
0x180024818  lea     rax, ??_7ImpersonateUserHelper@@6B@; const ImpersonateUserHelper::`vftable'
0x18002481f  mov     [rsp+4E0h+var_490], rax
0x180024824  mov     [rsp+4E0h+var_488], r14b
0x180024829  xorps   xmm0, xmm0
0x18002482c  movups  [rsp+4E0h+var_480], xmm0
0x180024831  mov     [rsp+4E0h+var_470], r14d
0x180024836  lea     rcx, [rsp+4E0h+var_490]; this
0x18002483b  call    ?ImpersonateUser@ImpersonateUserHelper@@QEAAJXZ; ImpersonateUserHelper::ImpersonateUser(void)
0x180024840  mov     rcx, [rbp+3E8h]; this
0x180024847  test    eax, eax
0x180024849  jns     short loc_1800248BE
0x18002484b  mov     r9d, eax; char *
0x18002484e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180024855  mov     edx, 0DAh; void *
0x18002485a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002485f  mov     rcx, [rbp+3E8h]; this
0x180024866  mov     ebx, 80070005h
0x18002486b  mov     r9d, ebx; char *
0x18002486e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180024875  mov     edx, 0DCh; void *
0x18002487a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002487f  nop
0x180024880  cmp     [rsp+4E0h+var_488], r14b
0x180024885  jz      short loc_1800248A2
0x180024887  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18002488e  nop     dword ptr [rax+rax+00h]
0x180024893  mov     rcx, [rbp+3E8h]; this
0x18002489a  test    eax, eax
0x18002489c  js      loc_1800249B3
0x1800248a2  mov     rcx, qword ptr [rsp+4E0h+var_480+8]
0x1800248a7  test    rcx, rcx
0x1800248aa  jz      short loc_1800248B9
0x1800248ac  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800248b3  nop     dword ptr [rax+rax+00h]
0x1800248b8  nop
0x1800248b9  jmp     loc_1800247A3
0x1800248be  xor     r8d, r8d; bFailIfExists
0x1800248c1  mov     rdx, [rbx+8]; lpNewFileName
0x1800248c5  mov     rcx, rsi; lpExistingFileName
0x1800248c8  call    cs:__imp_CopyFileW
0x1800248cf  nop     dword ptr [rax+rax+00h]
0x1800248d4  test    eax, eax
0x1800248d6  jnz     short loc_180024937
0x1800248d8  mov     rcx, [rbp+3E8h]; this
0x1800248df  mov     ebx, 80004005h
0x1800248e4  mov     r9d, ebx; char *
0x1800248e7  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800248ee  mov     edx, 0DFh; void *
0x1800248f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800248f8  nop
0x1800248f9  cmp     [rsp+4E0h+var_488], r14b
0x1800248fe  jz      short loc_18002491B
0x180024900  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180024907  nop     dword ptr [rax+rax+00h]
0x18002490c  mov     rcx, [rbp+3E8h]; this
0x180024913  test    eax, eax
0x180024915  js      loc_1800249C1
0x18002491b  mov     rcx, qword ptr [rsp+4E0h+var_480+8]
0x180024920  test    rcx, rcx
0x180024923  jz      short loc_180024932
0x180024925  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002492c  nop     dword ptr [rax+rax+00h]
0x180024931  nop
0x180024932  jmp     loc_1800247A3
0x180024937  cmp     [rsp+4E0h+var_488], r14b
0x18002493c  jz      short loc_180024955
0x18002493e  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180024945  nop     dword ptr [rax+rax+00h]
0x18002494a  mov     rcx, [rbp+3E8h]; this
0x180024951  test    eax, eax
0x180024953  js      short loc_1800249A5
0x180024955  mov     rcx, qword ptr [rsp+4E0h+var_480+8]
0x18002495a  test    rcx, rcx
0x18002495d  jz      short loc_18002496C
0x18002495f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180024966  nop     dword ptr [rax+rax+00h]
0x18002496b  nop
0x18002496c  mov     rcx, [rbx+8]; pObjectName
0x180024970  call    ?TakeOwnership@@YAJPEAG@Z; TakeOwnership(ushort *)
0x180024975  mov     ebx, eax
0x180024977  test    eax, eax
0x180024979  jns     short loc_180024985
0x18002497b  mov     edx, 0E3h
0x180024980  jmp     loc_18002478D
0x180024985  xor     eax, eax
0x180024987  mov     rcx, [rbp+3E0h+var_30]
0x18002498e  xor     rcx, rsp; StackCookie
0x180024991  call    __security_check_cookie
0x180024996  add     rsp, 4C0h
0x18002499d  pop     r14
0x18002499f  pop     rdi
0x1800249a0  pop     rsi
0x1800249a1  pop     rbx
0x1800249a2  pop     rbp
0x1800249a3  retn
0x1800249a5  mov     r9d, eax; char *
0x1800249a8  mov     edx, 4Bh ; 'K'; void *
0x1800249ad  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800249b3  mov     r9d, eax; char *
0x1800249b6  mov     edx, 4Bh ; 'K'; void *
0x1800249bb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800249c1  mov     r9d, eax; char *
0x1800249c4  mov     edx, 4Bh ; 'K'; void *
0x1800249c9  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
