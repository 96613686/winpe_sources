# MakeSafeSource(ushort const *,ushort const *,Common::StringBuffer *)

- ea: `0x180022df8`
- end: `0x1800230d8`
- name: `?MakeSafeSource@@YAJPEBG0PEAVStringBuffer@Common@@@Z`
- size: `736`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, const unsigned __int16 *, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026390`

## callees

- `0x18000cfe8`
- `0x18001c5b8`
- `0x180022510`
- `0x180022df8`
- `0x1800268e4`
- `0x1800273c8`
- `0x180065b0c`
- `0x180066df0`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x180022ead`
- `msvcrt!_wsplitpath_s` at `0x180022ead`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180022e34`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180022fda`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180023041`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002306f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180022e34`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180022fda`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180023041`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002306f`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180022ff0`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180022ff0`
- `DMCmnUtils!DmRevertToSelf` at `0x180022fbb`
- `DMCmnUtils!DmRevertToSelf` at `0x180023022`
- `DMCmnUtils!DmRevertToSelf` at `0x180023054`
- `DMCmnUtils!DmRevertToSelf` at `0x180022fbb`
- `DMCmnUtils!DmRevertToSelf` at `0x180023022`
- `DMCmnUtils!DmRevertToSelf` at `0x180023054`

## string_xrefs

- `0x180022ec1`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180022f00`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180022f82`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180022fa2`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180023009`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MakeSafeSource(LPCWSTR lpExistingFileName, const unsigned __int16 *a2, void **a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  signed int appended; // edi
  __int64 v11; // rdx
  int v12; // eax
  int v13; // eax
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // r8
  int DirCount; // [rsp+20h] [rbp-E0h]
  int DirCounta; // [rsp+20h] [rbp-E0h]
  int DirCountb; // [rsp+20h] [rbp-E0h]
  void **v22; // [rsp+50h] [rbp-B0h] BYREF
  char v23; // [rsp+58h] [rbp-A8h]
  __int128 v24; // [rsp+60h] [rbp-A0h]
  int v25; // [rsp+70h] [rbp-90h]
  unsigned int *v26[3]; // [rsp+78h] [rbp-88h] BYREF
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
  v26[1] = (unsigned int *)a3;
  v26[0] = (unsigned int *)&Common::StringBufferBuilder::`vftable';
  v26[2] = (unsigned int *)a3;
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
      appended = Common::StringBuilder::AppendString(v26, a2);
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
      appended = Common::StringBuilder::AppendString(v26, Filename);
      if ( appended < 0 )
      {
        v11 = 212;
        goto LABEL_13;
      }
      appended = Common::StringBuilder::AppendString(v26, Ext);
      if ( appended < 0 )
      {
        v11 = 213;
        goto LABEL_13;
      }
      v22 = &ImpersonateUserHelper::`vftable';
      v23 = 0;
      v24 = 0;
      v25 = 0;
      v12 = (unsigned int)ImpersonateUserHelper::ImpersonateUser((ImpersonateUser *)&v22);
      if ( v12 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xDA,
          (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v12);
        v7 = -2147024891;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)0x80070005LL,
          DirCount);
        if ( v23 )
        {
          v13 = DmRevertToSelf();
          if ( v13 < 0 )
            wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v14, (const char *)(unsigned int)v13, DirCounta);
        }
        if ( *((_QWORD *)&v24 + 1) )
          operator delete[](*((void **)&v24 + 1));
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
        if ( v23 )
        {
          v15 = DmRevertToSelf();
          if ( v15 < 0 )
            wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v16, (const char *)(unsigned int)v15, DirCountb);
        }
        if ( *((_QWORD *)&v24 + 1) )
          operator delete[](*((void **)&v24 + 1));
        return v7;
      }
      if ( v23 )
      {
        v17 = DmRevertToSelf();
        if ( v17 < 0 )
          wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v18, (const char *)(unsigned int)v17, DirCount);
      }
      if ( *((_QWORD *)&v24 + 1) )
        operator delete[](*((void **)&v24 + 1));
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
0x180022df8  push    rbp
0x180022dfa  push    rbx
0x180022dfb  push    rsi
0x180022dfc  push    rdi
0x180022dfd  push    r14
0x180022dff  lea     rbp, [rsp-3C0h]
0x180022e07  sub     rsp, 4C0h
0x180022e0e  mov     rax, cs:__security_cookie
0x180022e15  xor     rax, rsp
0x180022e18  mov     [rbp+3E0h+var_30], rax
0x180022e1f  mov     rbx, r8
0x180022e22  mov     rdi, rdx
0x180022e25  mov     rsi, rcx
0x180022e28  xor     r14d, r14d
0x180022e2b  test    r8, r8
0x180022e2e  jz      short loc_180022E45
0x180022e30  mov     rcx, [r8+8]
0x180022e34  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180022e3a  mov     [rbx+8], r14
0x180022e3e  mov     [rbx], r14d
0x180022e41  mov     [rbx+10h], r14d
0x180022e45  mov     [rbp+3E0h+var_460], rbx
0x180022e49  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180022e50  mov     [rsp+4E0h+var_468], rax
0x180022e55  mov     [rbp+3E0h+var_458], rbx
0x180022e59  test    rsi, rsi
0x180022e5c  jz      loc_18002308F
0x180022e62  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022e66  inc     rax
0x180022e69  cmp     [rsi+rax*2], r14w
0x180022e6e  jnz     short loc_180022E66
0x180022e70  test    rax, rax
0x180022e73  jz      loc_18002308F
0x180022e79  mov     ecx, 104h
0x180022e7e  mov     [rsp+4E0h+ExtCount], rcx; ExtCount
0x180022e83  lea     rax, [rbp+3E0h+var_240]
0x180022e8a  mov     [rsp+4E0h+Ext], rax; Ext
0x180022e8f  mov     [rsp+4E0h+FilenameCount], rcx; FilenameCount
0x180022e94  lea     rax, [rbp+3E0h+var_450]
0x180022e98  mov     [rsp+4E0h+Filename], rax; Filename
0x180022e9d  mov     [rsp+4E0h+DirCount], r14; int
0x180022ea2  xor     r9d, r9d; Dir
0x180022ea5  xor     r8d, r8d; DriveCount
0x180022ea8  xor     edx, edx; Drive
0x180022eaa  mov     rcx, rsi; FullPath
0x180022ead  call    cs:__imp__wsplitpath_s
0x180022eb3  test    eax, eax
0x180022eb5  jz      short loc_180022EDE
0x180022eb7  mov     ebx, 80004005h
0x180022ebc  mov     edx, 0D0h; void *
0x180022ec1  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180022ec8  mov     r9d, ebx; char *
0x180022ecb  mov     rcx, [rbp+3E8h]; this
0x180022ed2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022ed7  mov     eax, ebx
0x180022ed9  jmp     loc_180023091
0x180022ede  mov     rdx, rdi; unsigned __int16 *
0x180022ee1  lea     rcx, [rsp+4E0h+var_468]; this
0x180022ee6  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180022eeb  mov     edi, eax
0x180022eed  test    eax, eax
0x180022eef  jns     short loc_180022F13
0x180022ef1  mov     edx, 0D3h; void *
0x180022ef6  mov     rcx, [rbp+3E8h]; this
0x180022efd  mov     r9d, edi; char *
0x180022f00  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180022f07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f0c  mov     eax, edi
0x180022f0e  jmp     loc_180023091
0x180022f13  lea     rdx, [rbp+3E0h+var_450]; unsigned __int16 *
0x180022f17  lea     rcx, [rsp+4E0h+var_468]; this
0x180022f1c  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180022f21  mov     edi, eax
0x180022f23  test    eax, eax
0x180022f25  jns     short loc_180022F2E
0x180022f27  mov     edx, 0D4h
0x180022f2c  jmp     short loc_180022EF6
0x180022f2e  lea     rdx, [rbp+3E0h+var_240]; unsigned __int16 *
0x180022f35  lea     rcx, [rsp+4E0h+var_468]; this
0x180022f3a  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180022f3f  mov     edi, eax
0x180022f41  test    eax, eax
0x180022f43  jns     short loc_180022F4C
0x180022f45  mov     edx, 0D5h
0x180022f4a  jmp     short loc_180022EF6
0x180022f4c  lea     rax, ??_7ImpersonateUserHelper@@6B@; const ImpersonateUserHelper::`vftable'
0x180022f53  mov     [rsp+4E0h+var_490], rax
0x180022f58  mov     [rsp+4E0h+var_488], r14b
0x180022f5d  xorps   xmm0, xmm0
0x180022f60  movups  [rsp+4E0h+var_480], xmm0
0x180022f65  mov     [rsp+4E0h+var_470], r14d
0x180022f6a  lea     rcx, [rsp+4E0h+var_490]; this
0x180022f6f  call    ?ImpersonateUser@ImpersonateUserHelper@@QEAAJXZ; ImpersonateUserHelper::ImpersonateUser(void)
0x180022f74  mov     rcx, [rbp+3E8h]; this
0x180022f7b  test    eax, eax
0x180022f7d  jns     short loc_180022FE6
0x180022f7f  mov     r9d, eax; char *
0x180022f82  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180022f89  mov     edx, 0DAh; void *
0x180022f8e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022f93  mov     rcx, [rbp+3E8h]; this
0x180022f9a  mov     ebx, 80070005h
0x180022f9f  mov     r9d, ebx; char *
0x180022fa2  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180022fa9  mov     edx, 0DCh; void *
0x180022fae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022fb3  nop
0x180022fb4  cmp     [rsp+4E0h+var_488], r14b
0x180022fb9  jz      short loc_180022FD0
0x180022fbb  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180022fc1  mov     rcx, [rbp+3E8h]; this
0x180022fc8  test    eax, eax
0x180022fca  js      loc_1800230BC
0x180022fd0  mov     rcx, qword ptr [rsp+4E0h+var_480+8]
0x180022fd5  test    rcx, rcx
0x180022fd8  jz      short loc_180022FE1
0x180022fda  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180022fe0  nop
0x180022fe1  jmp     loc_180022ED7
0x180022fe6  xor     r8d, r8d; bFailIfExists
0x180022fe9  mov     rdx, [rbx+8]; lpNewFileName
0x180022fed  mov     rcx, rsi; lpExistingFileName
0x180022ff0  call    cs:__imp_CopyFileW
0x180022ff6  test    eax, eax
0x180022ff8  jnz     short loc_18002304D
0x180022ffa  mov     rcx, [rbp+3E8h]; this
0x180023001  mov     ebx, 80004005h
0x180023006  mov     r9d, ebx; char *
0x180023009  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180023010  mov     edx, 0DFh; void *
0x180023015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002301a  nop
0x18002301b  cmp     [rsp+4E0h+var_488], r14b
0x180023020  jz      short loc_180023037
0x180023022  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180023028  mov     rcx, [rbp+3E8h]; this
0x18002302f  test    eax, eax
0x180023031  js      loc_1800230CA
0x180023037  mov     rcx, qword ptr [rsp+4E0h+var_480+8]
0x18002303c  test    rcx, rcx
0x18002303f  jz      short loc_180023048
0x180023041  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180023047  nop
0x180023048  jmp     loc_180022ED7
0x18002304d  cmp     [rsp+4E0h+var_488], r14b
0x180023052  jz      short loc_180023065
0x180023054  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18002305a  mov     rcx, [rbp+3E8h]; this
0x180023061  test    eax, eax
0x180023063  js      short loc_1800230AE
0x180023065  mov     rcx, qword ptr [rsp+4E0h+var_480+8]
0x18002306a  test    rcx, rcx
0x18002306d  jz      short loc_180023076
0x18002306f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180023075  nop
0x180023076  mov     rcx, [rbx+8]; pObjectName
0x18002307a  call    ?TakeOwnership@@YAJPEAG@Z; TakeOwnership(ushort *)
0x18002307f  mov     ebx, eax
0x180023081  test    eax, eax
0x180023083  jns     short loc_18002308F
0x180023085  mov     edx, 0E3h
0x18002308a  jmp     loc_180022EC1
0x18002308f  xor     eax, eax
0x180023091  mov     rcx, [rbp+3E0h+var_30]
0x180023098  xor     rcx, rsp; StackCookie
0x18002309b  call    __security_check_cookie
0x1800230a0  add     rsp, 4C0h
0x1800230a7  pop     r14
0x1800230a9  pop     rdi
0x1800230aa  pop     rsi
0x1800230ab  pop     rbx
0x1800230ac  pop     rbp
0x1800230ad  retn
0x1800230ae  mov     r9d, eax; char *
0x1800230b1  mov     edx, 4Bh ; 'K'; void *
0x1800230b6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800230bc  mov     r9d, eax; char *
0x1800230bf  mov     edx, 4Bh ; 'K'; void *
0x1800230c4  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800230ca  mov     r9d, eax; char *
0x1800230cd  mov     edx, 4Bh ; 'K'; void *
0x1800230d2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
