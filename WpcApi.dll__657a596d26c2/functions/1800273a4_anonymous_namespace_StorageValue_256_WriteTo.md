# _anonymous_namespace_::StorageValue_256_::WriteTo

- ea: `0x1800273a4`
- end: `0x180027692`
- name: `_anonymous_namespace_::StorageValue_256_::WriteTo`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180027390`

## callees

- `0x1800032a0`
- `0x180003d20`
- `0x180005f9c`
- `0x18000bbac`
- `0x1800195c4`
- `0x180025cf4`
- `0x1800273a4`
- `0x18002c010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800273fe`
- `ADVAPI32!RegQueryValueExW` at `0x1800273fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall anonymous_namespace_::StorageValue_256_::WriteTo(__int64 a1, __int64 *a2)
{
  const WCHAR *v4; // rdx
  __int64 v5; // rsi
  __int64 v6; // rcx
  _QWORD *v7; // rdx
  __int64 v8; // rsi
  __int64 v9; // rcx
  unsigned int *v10; // rdx
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rcx
  struct IConstHierarchicalStorage *v17; // rbx
  IHierarchicalStorage **v18; // rax
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  DWORD Type; // [rsp+30h] [rbp-29h] BYREF
  struct IConstHierarchicalStorage *v21; // [rsp+38h] [rbp-21h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v23[4]; // [rsp+68h] [rbp+Fh] BYREF
  char **v24; // [rsp+88h] [rbp+2Fh]
  char **v25; // [rsp+90h] [rbp+37h]

  Type = 0;
  v4 = (const WCHAR *)(a1 - 56);
  if ( *(_QWORD *)(a1 - 56 + 24) > 7u )
    v4 = *(const WCHAR **)v4;
  if ( RegQueryValueExW(*(HKEY *)(a1 - 24), v4, 0, &Type, 0, 0) )
  {
    v16 = a1 - 64 + *(int *)(*(_QWORD *)(a1 - 64) + 4LL);
    (*(void (__fastcall **)(__int64, struct IConstHierarchicalStorage **))(*(_QWORD *)v16 + 56LL))(v16, &v21);
    v17 = v21;
    if ( v21 )
    {
      v18 = (IHierarchicalStorage **)(*(__int64 (__fastcall **)(__int64 *, _QWORD *))(*a2 + 48))(a2, v23);
      IHierarchicalStorage::CopyFrom(*v18, v17);
      if ( v23[0] )
      {
        v19 = (void (__fastcall ***)(_QWORD, __int64))(v23[0] + *(int *)(*(_QWORD *)(v23[0] + 8LL) + 4LL) + 8LL);
        (**v19)(v19, 1);
      }
      if ( v21 )
        (**(void (__fastcall ***)(struct IConstHierarchicalStorage *, __int64))v21)(v21, 1);
      return 1;
    }
  }
  else
  {
    switch ( Type )
    {
      case 1u:
        v14 = *a2;
        v15 = a1 + *(int *)(*(_QWORD *)(a1 - 64) + 4LL) - 64LL;
        if ( !*(_QWORD *)((*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v15 + 40LL))(v15, v23) + 40) )
        {
          ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
          throw (ErrorCodeException *)pExceptionObject;
        }
        (*(void (__fastcall **)(__int64 *))(v14 + 32))(a2);
        if ( v25 )
          std::wstring::~wstring(v25);
        return 1;
      case 3u:
        v12 = a1 + *(int *)(*(_QWORD *)(a1 - 64) + 4LL) - 64LL;
        v13 = *(_QWORD **)((*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v12 + 8LL))(v12, v23) + 32);
        if ( !v13 )
        {
          ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
          throw (ErrorCodeException *)pExceptionObject;
        }
        (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))*a2)(a2, *v13, v13[1] - *v13);
        if ( v24 )
          std::vector<char>::~vector<char>(v24);
        return 1;
      case 4u:
        v8 = *a2;
        v9 = a1 + *(int *)(*(_QWORD *)(a1 - 64) + 4LL) - 64LL;
        v10 = *(unsigned int **)((*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v9 + 16LL))(v9, v23) + 8);
        if ( !v10 )
        {
          ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
          throw (ErrorCodeException *)pExceptionObject;
        }
        (*(void (__fastcall **)(__int64 *, _QWORD))(v8 + 8))(a2, *v10);
        return 1;
      case 0xBu:
        v5 = *a2;
        v6 = a1 + *(int *)(*(_QWORD *)(a1 - 64) + 4LL) - 64LL;
        v7 = *(_QWORD **)((*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v6 + 24LL))(v6, v23) + 16);
        if ( !v7 )
        {
          ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
          throw (ErrorCodeException *)pExceptionObject;
        }
        (*(void (__fastcall **)(__int64 *, _QWORD))(v5 + 16))(a2, *v7);
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800273a4  mov     [rsp-8+arg_10], rbx
0x1800273a9  push    rbp
0x1800273aa  push    rsi
0x1800273ab  push    rdi
0x1800273ac  lea     rbp, [rsp-47h]
0x1800273b1  sub     rsp, 0A0h
0x1800273b8  mov     rax, cs:__security_cookie
0x1800273bf  xor     rax, rsp
0x1800273c2  mov     [rbp+57h+var_18], rax
0x1800273c6  mov     rdi, rdx
0x1800273c9  mov     rbx, rcx
0x1800273cc  mov     [rbp+57h+Type], 0
0x1800273d3  lea     rdx, [rcx-38h]
0x1800273d7  cmp     qword ptr [rdx+18h], 7
0x1800273dc  jbe     short loc_1800273E1
0x1800273de  mov     rdx, [rdx]; lpValueName
0x1800273e1  mov     [rsp+0B0h+lpcbData], 0; lpcbData
0x1800273ea  mov     [rsp+0B0h+lpData], 0; lpData
0x1800273f3  lea     r9, [rbp+57h+Type]; lpType
0x1800273f7  xor     r8d, r8d; lpReserved
0x1800273fa  mov     rcx, [rcx-18h]; hKey
0x1800273fe  call    cs:__imp_RegQueryValueExW
0x180027404  test    eax, eax
0x180027406  jnz     loc_180027561
0x18002740c  mov     eax, [rbp+57h+Type]
0x18002740f  sub     eax, 1
0x180027412  jz      loc_18002750D
0x180027418  sub     eax, 2
0x18002741b  jz      loc_1800274B7
0x180027421  sub     eax, 1
0x180027424  jz      short loc_180027471
0x180027426  cmp     eax, 7
0x180027429  jnz     loc_1800275F5
0x18002742f  mov     rsi, [rdi]
0x180027432  mov     rax, [rbx-40h]
0x180027436  movsxd  rcx, dword ptr [rax+4]
0x18002743a  add     rcx, 0FFFFFFFFFFFFFFC0h
0x18002743e  add     rcx, rbx
0x180027441  mov     rax, [rcx]
0x180027444  lea     rdx, [rbp+57h+var_48]
0x180027448  mov     rax, [rax+18h]
0x18002744c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027451  nop
0x180027452  mov     rdx, [rax+10h]
0x180027456  test    rdx, rdx
0x180027459  jz      loc_180027635
0x18002745f  mov     rdx, [rdx]
0x180027462  mov     rcx, rdi
0x180027465  mov     rax, [rsi+10h]
0x180027469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002746e  nop
0x18002746f  jmp     short loc_1800274B0
0x180027471  mov     rsi, [rdi]
0x180027474  mov     rax, [rbx-40h]
0x180027478  movsxd  rcx, dword ptr [rax+4]
0x18002747c  add     rcx, 0FFFFFFFFFFFFFFC0h
0x180027480  add     rcx, rbx
0x180027483  mov     rax, [rcx]
0x180027486  lea     rdx, [rbp+57h+var_48]
0x18002748a  mov     rax, [rax+10h]
0x18002748e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027493  nop
0x180027494  mov     rdx, [rax+8]
0x180027498  test    rdx, rdx
0x18002749b  jz      loc_180027654
0x1800274a1  mov     edx, [rdx]
0x1800274a3  mov     rcx, rdi
0x1800274a6  mov     rax, [rsi+8]
0x1800274aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274af  nop
0x1800274b0  mov     al, 1
0x1800274b2  jmp     loc_1800275F7
0x1800274b7  mov     rax, [rbx-40h]
0x1800274bb  movsxd  rcx, dword ptr [rax+4]
0x1800274bf  add     rcx, 0FFFFFFFFFFFFFFC0h
0x1800274c3  add     rcx, rbx
0x1800274c6  mov     rax, [rcx]
0x1800274c9  lea     rdx, [rbp+57h+var_48]
0x1800274cd  mov     rax, [rax+8]
0x1800274d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274d6  nop
0x1800274d7  mov     rdx, [rax+20h]
0x1800274db  test    rdx, rdx
0x1800274de  jz      loc_180027673
0x1800274e4  mov     rax, [rdi]
0x1800274e7  mov     r8, [rdx+8]
0x1800274eb  sub     r8, [rdx]
0x1800274ee  mov     rdx, [rdx]
0x1800274f1  mov     rcx, rdi
0x1800274f4  mov     rax, [rax]
0x1800274f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274fc  nop
0x1800274fd  mov     rcx, [rbp+57h+var_28]
0x180027501  test    rcx, rcx
0x180027504  jz      short loc_1800274B0
0x180027506  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18002750b  jmp     short loc_1800274B0
0x18002750d  mov     rsi, [rdi]
0x180027510  mov     rax, [rbx-40h]
0x180027514  movsxd  rcx, dword ptr [rax+4]
0x180027518  add     rcx, 0FFFFFFFFFFFFFFC0h
0x18002751c  add     rcx, rbx
0x18002751f  mov     rax, [rcx]
0x180027522  lea     rdx, [rbp+57h+var_48]
0x180027526  mov     rax, [rax+28h]
0x18002752a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002752f  nop
0x180027530  mov     rdx, [rax+28h]
0x180027534  test    rdx, rdx
0x180027537  jz      loc_180027616
0x18002753d  mov     rcx, rdi
0x180027540  mov     rax, [rsi+20h]
0x180027544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027549  nop
0x18002754a  mov     rcx, [rbp+57h+var_20]
0x18002754e  test    rcx, rcx
0x180027551  jz      loc_1800274B0
0x180027557  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002755c  jmp     loc_1800274B0
0x180027561  mov     rax, [rbx-40h]
0x180027565  movsxd  rcx, dword ptr [rax+4]
0x180027569  add     rbx, 0FFFFFFFFFFFFFFC0h
0x18002756d  add     rcx, rbx
0x180027570  mov     rax, [rcx]
0x180027573  lea     rdx, [rbp+57h+var_78]
0x180027577  mov     rax, [rax+38h]
0x18002757b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027580  nop
0x180027581  mov     rbx, [rbp+57h+var_78]
0x180027585  test    rbx, rbx
0x180027588  jz      short loc_1800275F5
0x18002758a  mov     rax, [rdi]
0x18002758d  lea     rdx, [rbp+57h+var_48]
0x180027591  mov     rcx, rdi
0x180027594  mov     rax, [rax+30h]
0x180027598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002759d  nop
0x18002759e  mov     rdx, rbx; struct IConstHierarchicalStorage *
0x1800275a1  mov     rcx, [rax]; this
0x1800275a4  call    ?CopyFrom@IHierarchicalStorage@@QEAAXAEBUIConstHierarchicalStorage@@@Z; IHierarchicalStorage::CopyFrom(IConstHierarchicalStorage const &)
0x1800275a9  nop
0x1800275aa  mov     rdx, [rbp+57h+var_48]
0x1800275ae  test    rdx, rdx
0x1800275b1  jz      short loc_1800275D3
0x1800275b3  mov     rax, [rdx+8]
0x1800275b7  movsxd  rcx, dword ptr [rax+4]
0x1800275bb  add     rcx, 8
0x1800275bf  add     rcx, rdx
0x1800275c2  mov     rax, [rcx]
0x1800275c5  mov     edx, 1
0x1800275ca  mov     rax, [rax]
0x1800275cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275d2  nop
0x1800275d3  mov     rcx, [rbp+57h+var_78]
0x1800275d7  test    rcx, rcx
0x1800275da  jz      loc_1800274B0
0x1800275e0  mov     rax, [rcx]
0x1800275e3  mov     edx, 1
0x1800275e8  mov     rax, [rax]
0x1800275eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275f0  jmp     loc_1800274B0
0x1800275f5  xor     al, al
0x1800275f7  mov     rcx, [rbp+57h+var_18]
0x1800275fb  xor     rcx, rsp; StackCookie
0x1800275fe  call    __security_check_cookie
0x180027603  mov     rbx, [rsp+0B0h+arg_10]
0x18002760b  add     rsp, 0A0h
0x180027612  pop     rdi
0x180027613  pop     rsi
0x180027614  pop     rbp
0x180027615  retn
0x180027616  mov     edx, 80004003h; int
0x18002761b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002761f  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027624  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18002762b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002762f  call    _CxxThrowException_0
0x180027635  mov     edx, 80004003h; int
0x18002763a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002763e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027643  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18002764a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002764e  call    _CxxThrowException_0
0x180027654  mov     edx, 80004003h; int
0x180027659  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002765d  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027662  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180027669  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002766d  call    _CxxThrowException_0
0x180027673  mov     edx, 80004003h; int
0x180027678  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18002767c  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027681  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180027688  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002768c  call    _CxxThrowException_0
```
