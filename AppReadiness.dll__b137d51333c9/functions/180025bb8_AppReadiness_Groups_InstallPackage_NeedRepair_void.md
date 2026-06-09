# AppReadiness::Groups::InstallPackage::NeedRepair(void)

- ea: `0x180025bb8`
- end: `0x180025d5d`
- name: `?NeedRepair@InstallPackage@Groups@AppReadiness@@AEAA_NXZ`
- size: `421`
- prototype: `char __fastcall(AppReadiness::Groups::InstallPackage *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x180005a70`

## callees

- `0x180001e94`
- `0x180005270`
- `0x18000a470`
- `0x180019260`
- `0x18002503c`
- `0x180025bb8`
- `0x18003e210`
- `0x18003eca8`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180025ca8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180025ca8`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicitForUserSidString` at `0x180025c57`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicitForUserSidString` at `0x180025c57`
- `api-ms-win-appmodel-state-l1-2-0!GetStateFolder` at `0x180025c95`
- `api-ms-win-appmodel-state-l1-2-0!GetStateFolder` at `0x180025c95`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180025d0d`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180025d2a`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180025d0d`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180025d2a`

## pseudocode

```c
char __fastcall AppReadiness::Groups::InstallPackage::NeedRepair(AppReadiness::Groups::InstallPackage *this)
{
  char *v1; // rsi
  __int64 v2; // rax
  _QWORD *v3; // rdi
  _QWORD *v4; // rbx
  __int64 v5; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rbx
  DWORD FileAttributesW; // eax
  int v9; // r8d
  int v10; // r9d
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v14; // [rsp+40h] [rbp-C0h]
  _QWORD *v15; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v16; // [rsp+50h] [rbp-B0h]
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = (char *)this + 8;
  v2 = (*(__int64 (__fastcall **)(char *, _QWORD **))(*((_QWORD *)this + 1) + 80LL))((char *)this + 8, &v15);
  std::weak_ptr<AppReadiness::PackageInfo>::lock(v2, &v13);
  if ( v16 )
    std::_Ref_count_base::_Decwref(v16);
  if ( (*(_BYTE *)(v13 + 140) & 0x40) != 0 )
  {
    v3 = (_QWORD *)(v13 + 40);
    if ( *(_QWORD *)(v13 + 64) <= 7u )
      v4 = (_QWORD *)(v13 + 40);
    else
      v4 = (_QWORD *)*v3;
    v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v1 + 112LL))(v1);
    v6 = (_QWORD *)(v5 + 64);
    if ( *(_QWORD *)(v5 + 88) > 7u )
      v6 = (_QWORD *)*v6;
    v7 = OpenStateExplicitForUserSidString(v6, v4);
    if ( v7 )
    {
      memset_0(FileName, 0, 0x208u);
      v12 = 260;
      if ( (unsigned int)GetStateFolder(v7, 1, FileName, &v12) )
      {
        FileAttributesW = GetFileAttributesW(FileName);
        if ( FileAttributesW != -1 && (FileAttributesW & 0x400) != 0 )
        {
          if ( (unsigned int)dword_1800A2278 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800A2278, 0x400000000000LL) )
          {
            if ( v3[3] > 7u )
              v3 = (_QWORD *)*v3;
            v15 = v3;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (unsigned int)&dword_1800A2278,
              (unsigned int)word_18009349A,
              v9,
              v10,
              (__int64)&v15);
          }
          CloseState(v7);
          if ( v14 )
            std::_Ref_count_base::_Decref(v14);
          return 1;
        }
      }
      CloseState(v7);
    }
  }
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  return 0;
}

```

## disassembly

```asm
0x180025bb8  push    rbp
0x180025bba  push    rbx
0x180025bbb  push    rsi
0x180025bbc  push    rdi
0x180025bbd  lea     rbp, [rsp-188h]
0x180025bc5  sub     rsp, 288h
0x180025bcc  mov     rax, cs:__security_cookie
0x180025bd3  xor     rax, rsp
0x180025bd6  mov     [rbp+1A0h+var_30], rax
0x180025bdd  lea     rsi, [rcx+8]
0x180025be1  mov     rax, [rsi]
0x180025be4  lea     rdx, [rsp+2A0h+var_258]
0x180025be9  mov     rcx, rsi
0x180025bec  mov     rax, [rax+50h]
0x180025bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bf5  lea     rdx, [rsp+2A0h+var_268]
0x180025bfa  mov     rcx, rax
0x180025bfd  call    ?lock@?$weak_ptr@VPackageInfo@AppReadiness@@@std@@QEBA?AV?$shared_ptr@VPackageInfo@AppReadiness@@@2@XZ; std::weak_ptr<AppReadiness::PackageInfo>::lock(void)
0x180025c02  nop
0x180025c03  mov     rcx, [rsp+2A0h+var_250]; this
0x180025c08  test    rcx, rcx
0x180025c0b  jz      short loc_180025C12
0x180025c0d  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180025c12  mov     rdi, [rsp+2A0h+var_268]
0x180025c17  test    byte ptr [rdi+8Ch], 40h
0x180025c1e  jz      loc_180025D31
0x180025c24  add     rdi, 28h ; '('
0x180025c28  cmp     qword ptr [rdi+18h], 7
0x180025c2d  jbe     short loc_180025C34
0x180025c2f  mov     rbx, [rdi]
0x180025c32  jmp     short loc_180025C37
0x180025c34  mov     rbx, rdi
0x180025c37  mov     rax, [rsi]
0x180025c3a  mov     rcx, rsi
0x180025c3d  mov     rax, [rax+70h]
0x180025c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c46  lea     rcx, [rax+40h]
0x180025c4a  cmp     qword ptr [rcx+18h], 7
0x180025c4f  jbe     short loc_180025C54
0x180025c51  mov     rcx, [rcx]
0x180025c54  mov     rdx, rbx
0x180025c57  call    cs:__imp_OpenStateExplicitForUserSidString
0x180025c5d  mov     rbx, rax
0x180025c60  test    rax, rax
0x180025c63  jz      loc_180025D31
0x180025c69  xor     edx, edx; Val
0x180025c6b  mov     r8d, 208h; Size
0x180025c71  lea     rcx, [rsp+2A0h+FileName]; void *
0x180025c76  call    memset_0
0x180025c7b  mov     [rsp+2A0h+var_270], 104h
0x180025c83  lea     r9, [rsp+2A0h+var_270]
0x180025c88  lea     r8, [rsp+2A0h+FileName]
0x180025c8d  mov     edx, 1
0x180025c92  mov     rcx, rbx
0x180025c95  call    cs:__imp_GetStateFolder
0x180025c9b  test    eax, eax
0x180025c9d  jz      loc_180025D27
0x180025ca3  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x180025ca8  call    cs:__imp_GetFileAttributesW
0x180025cae  cmp     eax, 0FFFFFFFFh
0x180025cb1  jz      short loc_180025D27
0x180025cb3  bt      eax, 0Ah
0x180025cb7  jnb     short loc_180025D27
0x180025cb9  mov     eax, cs:dword_1800A2278
0x180025cbf  cmp     eax, 5
0x180025cc2  jbe     short loc_180025D0A
0x180025cc4  mov     rdx, 400000000000h
0x180025cce  lea     rcx, dword_1800A2278
0x180025cd5  call    _tlgKeywordOn
0x180025cda  test    al, al
0x180025cdc  jz      short loc_180025D0A
0x180025cde  cmp     qword ptr [rdi+18h], 7
0x180025ce3  jbe     short loc_180025CE8
0x180025ce5  mov     rdi, [rdi]
0x180025ce8  mov     [rsp+2A0h+var_258], rdi
0x180025ced  lea     rax, [rsp+2A0h+var_258]
0x180025cf2  mov     [rsp+2A0h+var_280], rax
0x180025cf7  lea     rdx, word_18009349A
0x180025cfe  lea     rcx, dword_1800A2278
0x180025d05  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180025d0a  mov     rcx, rbx
0x180025d0d  call    cs:__imp_CloseState
0x180025d13  nop
0x180025d14  mov     rcx, [rsp+2A0h+var_260]; this
0x180025d19  test    rcx, rcx
0x180025d1c  jz      short loc_180025D23
0x180025d1e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025d23  mov     al, 1
0x180025d25  jmp     short loc_180025D42
0x180025d27  mov     rcx, rbx
0x180025d2a  call    cs:__imp_CloseState
0x180025d30  nop
0x180025d31  mov     rcx, [rsp+2A0h+var_260]; this
0x180025d36  test    rcx, rcx
0x180025d39  jz      short loc_180025D40
0x180025d3b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025d40  xor     al, al
0x180025d42  mov     rcx, [rbp+1A0h+var_30]
0x180025d49  xor     rcx, rsp; StackCookie
0x180025d4c  call    __security_check_cookie
0x180025d51  add     rsp, 288h
0x180025d58  pop     rdi
0x180025d59  pop     rsi
0x180025d5a  pop     rbx
0x180025d5b  pop     rbp
0x180025d5c  retn
```
