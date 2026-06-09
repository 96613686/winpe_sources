# CGrepQuery::_EnumFolder(IShellFolder *)

- ea: `0x180022d60`
- end: `0x1800230a8`
- name: `?_EnumFolder@CGrepQuery@@AEAAJPEAUIShellFolder@@@Z`
- size: `840`
- prototype: `int(CGrepQuery *__hidden this, struct IShellFolder *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180024130`

## callees

- `0x180006ca8`
- `0x180014498`
- `0x180022d60`
- `0x180071dc0`
- `0x180072cd0`
- `0x1800920d8`
- `0x180092580`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180022f41`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180022f41`
- `SHCORE!IUnknown_Set` at `0x180022ea8`
- `SHCORE!IUnknown_Set` at `0x180022ea8`
- `SHCORE!IUnknown_SetSite` at `0x180022df3`
- `SHCORE!IUnknown_SetSite` at `0x18002309d`
- `SHCORE!IUnknown_SetSite` at `0x180022df3`
- `SHCORE!IUnknown_SetSite` at `0x18002309d`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x180022dcf`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x180022dcf`
- `Windows.Storage!ILFree` at `0x180022fd4`
- `Windows.Storage!ILFree` at `0x180022fd4`
- `Windows.Storage!SHGetIDListFromObject` at `0x180022f76`
- `Windows.Storage!SHGetIDListFromObject` at `0x180022f76`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180022da3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180022da3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022fc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022fc9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180022f35`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180022f35`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CGrepQuery::_EnumFolder(CGrepQuery *this, IUnknown *a2)
{
  int v4; // r12d
  bool v5; // r15
  char v6; // r12
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // ebx
  wchar_t *v12; // rdi
  LPWSTR FileNameW; // rax
  unsigned int i; // ebx
  __int64 v15; // rdx
  __int64 v16; // rdx
  HRESULT (__stdcall *QueryInterface)(IShellFolder *, const IID *const, void **); // rbx
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int128 Buf1; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( GetModuleFileNameW(0, Filename, 0x104u) - 1 <= 0x103 )
  {
    v4 = 1;
    for ( i = 0; i < 3; ++i )
    {
      v12 = off_1800F2D40[i];
      FileNameW = PathFindFileNameW(Filename);
      if ( !(unsigned int)_o__wcsicmp(FileNameW, v12) )
      {
        v4 = 0;
        break;
      }
    }
  }
  else
  {
    v4 = -2147024774;
  }
  Buf1 = 0;
  v5 = (int)IUnknown_GetClassID(a2, &Buf1) >= 0 && !memcmp_0(&Buf1, &CLSID_PCSettings, 0x10u);
  if ( !v4 || v5 )
  {
    v6 = 1;
    IUnknown_SetSite(a2, *((IUnknown **)this + 3));
  }
  else
  {
    v6 = 0;
  }
  v20 = 0;
  if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_f93f9470_36a7_4a92_afdb_aed751464f32,
         &v20) >= 0 )
  {
    ppidl = 0;
    if ( SHGetIDListFromObject(a2, &ppidl) >= 0 )
    {
      pv = 0;
      if ( (unsigned int)ILGetHiddenStringAllocW(ppidl, v15, &pv) )
      {
        (*(void (__fastcall **)(__int64, LPVOID, _QWORD))(*(_QWORD *)v20 + 24LL))(v20, pv, *((_QWORD *)this + 7));
        SafeRelease<IShellItemArray>((__int64 *)this + 7);
        SafeRelease<IShellItemArray>((__int64 *)this + 8);
        CoTaskMemFree(pv);
      }
      ILFree(ppidl);
    }
    *((_DWORD *)this + 45) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( v5 )
  {
    ppidl = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppidl);
    if ( (int)CreatePropertyBagForPCSettingsQuery(*((IUnknown **)this + 8), v16, (void **)&ppidl) >= 0 )
    {
      pv = 0;
      QueryInterface = (HRESULT (__stdcall *)(IShellFolder *, const IID *const, void **))a2->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pv);
      if ( ((int (__fastcall *)(IUnknown *, GUID *, LPVOID *))QueryInterface)(
             a2,
             &GUID_37d84f60_42cb_11ce_8135_00aa004bb851,
             &pv) >= 0
        && (*(int (__fastcall **)(LPVOID, LPITEMIDLIST, _QWORD))(*(_QWORD *)pv + 40LL))(pv, ppidl, 0) >= 0 )
      {
        SafeRelease<IShellItemArray>((__int64 *)this + 7);
        SafeRelease<IShellItemArray>((__int64 *)this + 8);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pv);
    }
    *((_DWORD *)this + 45) = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppidl);
  }
  v7 = 32 * (*((_DWORD *)this + 38) & 0x100 | 0x887);
  v8 = *((_QWORD *)this + 21);
  *((_QWORD *)this + 21) = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = *((_QWORD *)this + 23);
  *((_QWORD *)this + 23) = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, char *))a2->lpVtbl[1].AddRef)(
          a2,
          0,
          v7,
          (char *)this + 168);
  if ( v10 >= 0 )
    IUnknown_Set((IUnknown **)this + 23, a2);
  if ( v6 )
    IUnknown_SetSite(a2, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180022d60  mov     [rsp-8+arg_10], rbx
0x180022d65  push    rbp
0x180022d66  push    rsi
0x180022d67  push    rdi
0x180022d68  push    r12
0x180022d6a  push    r13
0x180022d6c  push    r14
0x180022d6e  push    r15
0x180022d70  lea     rbp, [rsp-180h]
0x180022d78  sub     rsp, 280h
0x180022d7f  mov     rax, cs:__security_cookie
0x180022d86  xor     rax, rsp
0x180022d89  mov     [rbp+1B0h+var_40], rax
0x180022d90  mov     rsi, rdx
0x180022d93  mov     r14, rcx
0x180022d96  mov     r8d, 104h; nSize
0x180022d9c  lea     rdx, [rsp+2B0h+Filename]; lpFilename
0x180022da1  xor     ecx, ecx; hModule
0x180022da3  call    cs:__imp_GetModuleFileNameW
0x180022da9  dec     eax
0x180022dab  xor     r13d, r13d
0x180022dae  cmp     eax, 103h
0x180022db3  jbe     loc_180022F57
0x180022db9  mov     r12d, 8007007Ah
0x180022dbf  xorps   xmm0, xmm0
0x180022dc2  movups  [rsp+2B0h+Buf1], xmm0
0x180022dc7  lea     rdx, [rsp+2B0h+Buf1]
0x180022dcc  mov     rcx, rsi
0x180022dcf  call    cs:__imp_IUnknown_GetClassID
0x180022dd5  test    eax, eax
0x180022dd7  jns     loc_180022EF4
0x180022ddd  xor     r15b, r15b
0x180022de0  test    r12d, r12d
0x180022de3  jnz     loc_180022EE3
0x180022de9  mov     r12b, 1
0x180022dec  mov     rdx, [r14+18h]; punkSite
0x180022df0  mov     rcx, rsi; punk
0x180022df3  call    cs:__imp_IUnknown_SetSite
0x180022df9  mov     [rsp+2B0h+var_270], r13
0x180022dfe  mov     rax, [rsi]
0x180022e01  lea     r8, [rsp+2B0h+var_270]
0x180022e06  lea     rdx, _GUID_f93f9470_36a7_4a92_afdb_aed751464f32
0x180022e0d  mov     rcx, rsi
0x180022e10  mov     rax, [rax]
0x180022e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e18  test    eax, eax
0x180022e1a  jns     loc_180022F69
0x180022e20  test    r15b, r15b
0x180022e23  jnz     loc_180022FF7
0x180022e29  mov     ebx, [r14+98h]
0x180022e30  and     ebx, 100h
0x180022e36  or      ebx, 887h
0x180022e3c  shl     ebx, 5
0x180022e3f  mov     rcx, [r14+0A8h]
0x180022e46  mov     [r14+0A8h], r13
0x180022e4d  test    rcx, rcx
0x180022e50  jz      short loc_180022E5E
0x180022e52  mov     rax, [rcx]
0x180022e55  mov     rax, [rax+10h]
0x180022e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e5e  mov     rcx, [r14+0B8h]
0x180022e65  mov     [r14+0B8h], r13
0x180022e6c  test    rcx, rcx
0x180022e6f  jz      short loc_180022E7D
0x180022e71  mov     rax, [rcx]
0x180022e74  mov     rax, [rax+10h]
0x180022e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e7d  mov     rax, [rsi]
0x180022e80  lea     r9, [r14+0A8h]
0x180022e87  mov     r8d, ebx
0x180022e8a  xor     edx, edx
0x180022e8c  mov     rcx, rsi
0x180022e8f  mov     rax, [rax+20h]
0x180022e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e98  mov     ebx, eax
0x180022e9a  test    eax, eax
0x180022e9c  js      short loc_180022EAE
0x180022e9e  mov     rdx, rsi; punk
0x180022ea1  lea     rcx, [r14+0B8h]; ppunk
0x180022ea8  call    cs:__imp_IUnknown_Set
0x180022eae  test    r12b, r12b
0x180022eb1  jnz     loc_180023098
0x180022eb7  mov     eax, ebx
0x180022eb9  mov     rcx, [rbp+1B0h+var_40]
0x180022ec0  xor     rcx, rsp; StackCookie
0x180022ec3  call    __security_check_cookie
0x180022ec8  mov     rbx, [rsp+2B0h+arg_10]
0x180022ed0  add     rsp, 280h
0x180022ed7  pop     r15
0x180022ed9  pop     r14
0x180022edb  pop     r13
0x180022edd  pop     r12
0x180022edf  pop     rdi
0x180022ee0  pop     rsi
0x180022ee1  pop     rbp
0x180022ee2  retn
0x180022ee3  test    r15b, r15b
0x180022ee6  jnz     loc_180022DE9
0x180022eec  xor     r12b, r12b
0x180022eef  jmp     loc_180022DF9
0x180022ef4  mov     r8d, 10h; Size
0x180022efa  lea     rdx, CLSID_PCSettings; Buf2
0x180022f01  lea     rcx, [rsp+2B0h+Buf1]; Buf1
0x180022f06  call    memcmp_0
0x180022f0b  test    eax, eax
0x180022f0d  jnz     loc_180022DDD
0x180022f13  mov     r15b, 1
0x180022f16  jmp     loc_180022DE0
0x180022f20  cmp     ebx, 3
0x180022f23  jnb     loc_180022DBF
0x180022f29  movsxd  rax, ebx
0x180022f2c  mov     rdi, [r15+rax*8]
0x180022f30  lea     rcx, [rsp+2B0h+Filename]; pszPath
0x180022f35  call    cs:__imp_PathFindFileNameW
0x180022f3b  mov     rdx, rdi
0x180022f3e  mov     rcx, rax
0x180022f41  call    cs:__imp__o__wcsicmp
0x180022f47  test    eax, eax
0x180022f49  jz      short loc_180022F4F
0x180022f4b  inc     ebx
0x180022f4d  jmp     short loc_180022F20
0x180022f4f  mov     r12d, r13d
0x180022f52  jmp     loc_180022DBF
0x180022f57  mov     r12d, 1
0x180022f5d  mov     ebx, r13d
0x180022f60  lea     r15, off_1800F2D40; "pickerhost.exe"
0x180022f67  jmp     short loc_180022F20
0x180022f69  mov     [rsp+2B0h+ppidl], r13
0x180022f6e  lea     rdx, [rsp+2B0h+ppidl]; ppidl
0x180022f73  mov     rcx, rsi; punk
0x180022f76  call    cs:__imp_SHGetIDListFromObject
0x180022f7c  test    eax, eax
0x180022f7e  js      short loc_180022FDA
0x180022f80  mov     [rsp+2B0h+pv], r13
0x180022f85  lea     r8, [rsp+2B0h+pv]
0x180022f8a  mov     rcx, [rsp+2B0h+ppidl]
0x180022f8f  call    ?ILGetHiddenStringAllocW@@YAHPEFBU_ITEMIDLIST_RELATIVE@@W4IDLHID@@PEAPEAG@Z; ILGetHiddenStringAllocW(_ITEMIDLIST_RELATIVE const *,IDLHID,ushort * *)
0x180022f94  test    eax, eax
0x180022f96  jz      short loc_180022FCF
0x180022f98  mov     rcx, [rsp+2B0h+var_270]
0x180022f9d  mov     rax, [rcx]
0x180022fa0  mov     r8, [r14+38h]
0x180022fa4  mov     rdx, [rsp+2B0h+pv]
0x180022fa9  mov     rax, [rax+18h]
0x180022fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fb2  lea     rcx, [r14+38h]
0x180022fb6  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180022fbb  lea     rcx, [r14+40h]
0x180022fbf  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180022fc4  mov     rcx, [rsp+2B0h+pv]; pv
0x180022fc9  call    cs:__imp_CoTaskMemFree
0x180022fcf  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x180022fd4  call    cs:__imp_ILFree
0x180022fda  mov     [r14+0B4h], r13d
0x180022fe1  mov     rcx, [rsp+2B0h+var_270]
0x180022fe6  mov     rax, [rcx]
0x180022fe9  mov     rax, [rax+10h]
0x180022fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ff2  jmp     loc_180022E20
0x180022ff7  mov     [rsp+2B0h+ppidl], r13
0x180022ffc  lea     rcx, [rsp+2B0h+ppidl]
0x180023001  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023006  lea     r8, [rsp+2B0h+ppidl]
0x18002300b  mov     rcx, [r14+40h]
0x18002300f  call    ?CreatePropertyBagForPCSettingsQuery@@YAJPEAUICondition@@W4Type@PCSetting@@PEAPEAUIPropertyBag@@@Z; CreatePropertyBagForPCSettingsQuery(ICondition *,PCSetting::Type,IPropertyBag * *)
0x180023014  test    eax, eax
0x180023016  js      short loc_180023082
0x180023018  mov     [rsp+2B0h+pv], r13
0x18002301d  mov     rax, [rsi]
0x180023020  mov     rbx, [rax]
0x180023023  lea     rcx, [rsp+2B0h+pv]
0x180023028  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002302d  lea     r8, [rsp+2B0h+pv]
0x180023032  lea     rdx, _GUID_37d84f60_42cb_11ce_8135_00aa004bb851
0x180023039  mov     rcx, rsi
0x18002303c  mov     rax, rbx
0x18002303f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023044  test    eax, eax
0x180023046  js      short loc_180023078
0x180023048  mov     rcx, [rsp+2B0h+pv]
0x18002304d  mov     rax, [rcx]
0x180023050  xor     r8d, r8d
0x180023053  mov     rdx, [rsp+2B0h+ppidl]
0x180023058  mov     rax, [rax+28h]
0x18002305c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023061  test    eax, eax
0x180023063  js      short loc_180023078
0x180023065  lea     rcx, [r14+38h]
0x180023069  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x18002306e  lea     rcx, [r14+40h]
0x180023072  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180023077  nop
0x180023078  lea     rcx, [rsp+2B0h+pv]
0x18002307d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023082  mov     [r14+0B4h], r13d
0x180023089  lea     rcx, [rsp+2B0h+ppidl]
0x18002308e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023093  jmp     loc_180022E29
0x180023098  xor     edx, edx; punkSite
0x18002309a  mov     rcx, rsi; punk
0x18002309d  call    cs:__imp_IUnknown_SetSite
0x1800230a3  jmp     loc_180022EB7
```
