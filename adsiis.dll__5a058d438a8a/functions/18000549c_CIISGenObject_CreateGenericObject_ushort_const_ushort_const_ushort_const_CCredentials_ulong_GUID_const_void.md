# CIISGenObject::CreateGenericObject(ushort const *,ushort const *,ushort const *,CCredentials &,ulong,_GUID const &,void * *)

- ea: `0x18000549c`
- end: `0x1800056dc`
- name: `?CreateGenericObject@CIISGenObject@@SAJPEBG00AEAVCCredentials@@KAEBU_GUID@@PEAPEAX@Z`
- size: `576`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, struct CCredentials *, unsigned int, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002c80`
- `0x180003dbc`
- `0x1800049c0`
- `0x180005350`
- `0x18000d83c`
- `0x180015664`

## callees

- `0x180003260`
- `0x1800042e8`
- `0x180004360`
- `0x18000474c`
- `0x18000549c`
- `0x180013f94`
- `0x1800148a0`
- `0x1800170ac`
- `0x18001e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000559e`
- `msvcrt!_wcsicmp` at `0x1800055b6`
- `msvcrt!_wcsicmp` at `0x1800055ce`
- `msvcrt!_wcsicmp` at `0x1800055e2`
- `msvcrt!_wcsicmp` at `0x1800055f6`
- `msvcrt!_wcsicmp` at `0x18000560a`
- `msvcrt!_wcsicmp` at `0x18000561e`
- `msvcrt!_wcsicmp` at `0x180005632`
- `msvcrt!_wcsicmp` at `0x18000559e`
- `msvcrt!_wcsicmp` at `0x1800055b6`
- `msvcrt!_wcsicmp` at `0x1800055ce`
- `msvcrt!_wcsicmp` at `0x1800055e2`
- `msvcrt!_wcsicmp` at `0x1800055f6`
- `msvcrt!_wcsicmp` at `0x18000560a`
- `msvcrt!_wcsicmp` at `0x18000561e`
- `msvcrt!_wcsicmp` at `0x180005632`

## string_xrefs

- `0x180005614`: `IIsWebDirectory`

## pseudocode

```c
__int64 __fastcall CIISGenObject::CreateGenericObject(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct CCredentials *a4,
        unsigned int a5,
        const struct _GUID *a6,
        void **a7)
{
  unsigned __int16 *v8; // rdi
  int v11; // eax
  unsigned int v12; // edx
  CCoreADsObject *v13; // rsi
  int v14; // ebx
  int v15; // eax
  char *v16; // r14
  void **v17; // r8
  const struct _GUID *v18; // rdx
  struct CADsExtMgr **v20; // [rsp+20h] [rbp-48h]
  CCoreADsObject *v21; // [rsp+70h] [rbp+8h] BYREF
  struct CADsExtMgr *v22; // [rsp+80h] [rbp+18h] BYREF

  v21 = 0;
  v22 = 0;
  v8 = a3;
  if ( !a1 || !a2 || !a3 )
    return (unsigned int)-2147467261;
  v11 = CIISGenObject::AllocateGenObject(a1, a4, &v21);
  v13 = v21;
  v14 = v11;
  if ( v11 < 0 )
    goto LABEL_11;
  v14 = CCoreADsObject::InitializeCoreObject(v21, a1, a2, v8, (const unsigned __int16 *)v20, &CLSID_IISGenObject, a5);
  if ( v14 < 0 )
    goto LABEL_11;
  v14 = CIISGenObject::CacheMetaDataPath(v13);
  if ( v14 < 0 )
    goto LABEL_11;
  v14 = CPropertyCache::InitializePropertyCache(
          *((CPropertyCache **)v13 + 19),
          *((const unsigned __int16 **)v13 + 17),
          a4);
  if ( v14 < 0 )
    goto LABEL_11;
  if ( *((_DWORD *)v13 + 2) != 2 )
    goto LABEL_31;
  v15 = MetaBaseDetectKey(*((struct IMSAdminBaseW **)v13 + 25), *((const unsigned __int16 **)v13 + 18));
  v14 = v15;
  if ( v15 >= 0 )
  {
    v14 = -2147024713;
    goto LABEL_11;
  }
  if ( (_WORD)v15 == 3 )
  {
LABEL_31:
    if ( _wcsicmp(v8, L"IIsFtpServer")
      && _wcsicmp(v8, L"IIsWebServer")
      && _wcsicmp(v8, L"IIsNntpServer")
      && _wcsicmp(v8, L"IIsSmtpServer")
      && _wcsicmp(v8, L"IIsPop3Server")
      && _wcsicmp(v8, L"IIsImapServer") )
    {
      if ( !_wcsicmp(v8, L"IIsWebDirectory") || !_wcsicmp(v8, L"IIsWebVirtualDir") )
        v8 = L"IIsApp";
    }
    else
    {
      v8 = L"IIsServer";
    }
    v16 = (char *)v13 + 64;
    v14 = CADsExtMgr::CreateExtMgr((LPUNKNOWN)v13 + 8, *((struct CAggregatorDispMgr **)v13 + 20), a4, v8, &v22);
    if ( v14 >= 0 )
    {
      v17 = a7;
      v18 = a6;
      *((_QWORD *)v13 + 21) = v22;
      v14 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v16)((__int64)v13 + 64, v18, v17);
      if ( v14 >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))((__int64)v13 + 64);
        return (unsigned int)v14;
      }
    }
  }
LABEL_11:
  if ( v13 )
    CIISGenObject::`scalar deleting destructor'(v13, v12);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000549c  mov     rax, rsp
0x18000549f  mov     [rax+10h], rbx
0x1800054a3  push    rbp
0x1800054a4  push    rsi
0x1800054a5  push    rdi
0x1800054a6  push    r14
0x1800054a8  push    r15
0x1800054aa  sub     rsp, 40h
0x1800054ae  mov     qword ptr [rax+8], 0
0x1800054b6  mov     r15, r9
0x1800054b9  mov     qword ptr [rax+18h], 0
0x1800054c1  mov     rdi, r8
0x1800054c4  mov     rbp, rdx
0x1800054c7  mov     r14, rcx
0x1800054ca  test    rcx, rcx
0x1800054cd  jz      loc_1800056C4
0x1800054d3  test    rdx, rdx
0x1800054d6  jz      loc_1800056C4
0x1800054dc  test    r8, r8
0x1800054df  jz      loc_1800056C4
0x1800054e5  lea     r8, [rax+8]; struct CIISGenObject **
0x1800054e9  mov     rdx, r9; struct CCredentials *
0x1800054ec  call    ?AllocateGenObject@CIISGenObject@@SAJPEBGAEAVCCredentials@@PEAPEAV1@@Z; CIISGenObject::AllocateGenObject(ushort const *,CCredentials &,CIISGenObject * *)
0x1800054f1  mov     rsi, [rsp+68h+arg_0]
0x1800054f6  mov     ebx, eax
0x1800054f8  test    eax, eax
0x1800054fa  js      short loc_180005578
0x1800054fc  mov     eax, [rsp+68h+arg_20]
0x180005503  mov     r9, rdi; unsigned __int16 *
0x180005506  mov     [rsp+68h+var_38], eax; unsigned int
0x18000550a  mov     r8, rbp; unsigned __int16 *
0x18000550d  lea     rax, CLSID_IISGenObject
0x180005514  mov     rdx, r14; unsigned __int16 *
0x180005517  mov     rcx, rsi; this
0x18000551a  mov     [rsp+68h+var_40], rax; struct _GUID *
0x18000551f  call    ?InitializeCoreObject@CCoreADsObject@@QEAAJPEBG000AEBU_GUID@@K@Z; CCoreADsObject::InitializeCoreObject(ushort const *,ushort const *,ushort const *,ushort const *,_GUID const &,ulong)
0x180005524  mov     ebx, eax
0x180005526  test    eax, eax
0x180005528  js      short loc_180005578
0x18000552a  mov     rcx, rsi; this
0x18000552d  call    ?CacheMetaDataPath@CIISGenObject@@QEAAJXZ; CIISGenObject::CacheMetaDataPath(void)
0x180005532  mov     ebx, eax
0x180005534  test    eax, eax
0x180005536  js      short loc_180005578
0x180005538  mov     rdx, [rsi+88h]; unsigned __int16 *
0x18000553f  mov     r8, r15; struct CCredentials *
0x180005542  mov     rcx, [rsi+98h]; this
0x180005549  call    ?InitializePropertyCache@CPropertyCache@@QEAAJPEBGAEAVCCredentials@@@Z; CPropertyCache::InitializePropertyCache(ushort const *,CCredentials &)
0x18000554e  mov     ebx, eax
0x180005550  test    eax, eax
0x180005552  js      short loc_180005578
0x180005554  cmp     dword ptr [rsi+8], 2
0x180005558  jnz     short loc_180005594
0x18000555a  mov     rdx, [rsi+90h]; unsigned __int16 *
0x180005561  mov     rcx, [rsi+0C8h]; struct IMSAdminBaseW *
0x180005568  call    ?MetaBaseDetectKey@@YAJPEAUIMSAdminBaseW@@PEBG@Z; MetaBaseDetectKey(IMSAdminBaseW *,ushort const *)
0x18000556d  mov     ebx, eax
0x18000556f  test    eax, eax
0x180005571  js      short loc_18000558E
0x180005573  mov     ebx, 800700B7h
0x180005578  test    rsi, rsi
0x18000557b  jz      loc_1800056C9
0x180005581  mov     rcx, rsi; this
0x180005584  call    ??_GCIISGenObject@@QEAAPEAXI@Z; CIISGenObject::`scalar deleting destructor'(uint)
0x180005589  jmp     loc_1800056C9
0x18000558e  cmp     ax, 3
0x180005592  jnz     short loc_180005578
0x180005594  lea     rdx, aIisftpserver; "IIsFtpServer"
0x18000559b  mov     rcx, rdi; String1
0x18000559e  call    cs:__imp__wcsicmp
0x1800055a4  test    eax, eax
0x1800055a6  jz      loc_180005645
0x1800055ac  lea     rdx, aIiswebserver; "IIsWebServer"
0x1800055b3  mov     rcx, rdi; String1
0x1800055b6  call    cs:__imp__wcsicmp
0x1800055bc  test    eax, eax
0x1800055be  jz      loc_180005645
0x1800055c4  lea     rdx, aIisnntpserver; "IIsNntpServer"
0x1800055cb  mov     rcx, rdi; String1
0x1800055ce  call    cs:__imp__wcsicmp
0x1800055d4  test    eax, eax
0x1800055d6  jz      short loc_180005645
0x1800055d8  lea     rdx, aIissmtpserver; "IIsSmtpServer"
0x1800055df  mov     rcx, rdi; String1
0x1800055e2  call    cs:__imp__wcsicmp
0x1800055e8  test    eax, eax
0x1800055ea  jz      short loc_180005645
0x1800055ec  lea     rdx, aIispop3server; "IIsPop3Server"
0x1800055f3  mov     rcx, rdi; String1
0x1800055f6  call    cs:__imp__wcsicmp
0x1800055fc  test    eax, eax
0x1800055fe  jz      short loc_180005645
0x180005600  lea     rdx, aIisimapserver; "IIsImapServer"
0x180005607  mov     rcx, rdi; String1
0x18000560a  call    cs:__imp__wcsicmp
0x180005610  test    eax, eax
0x180005612  jz      short loc_180005645
0x180005614  lea     rdx, aIiswebdirector_1; "IIsWebDirectory"
0x18000561b  mov     rcx, rdi; String1
0x18000561e  call    cs:__imp__wcsicmp
0x180005624  test    eax, eax
0x180005626  jz      short loc_18000563C
0x180005628  lea     rdx, aIiswebvirtuald; "IIsWebVirtualDir"
0x18000562f  mov     rcx, rdi; String1
0x180005632  call    cs:__imp__wcsicmp
0x180005638  test    eax, eax
0x18000563a  jnz     short loc_18000564C
0x18000563c  lea     rdi, aIisapp; "IIsApp"
0x180005643  jmp     short loc_18000564C
0x180005645  lea     rdi, aIisserver; "IIsServer"
0x18000564c  mov     rdx, [rsi+0A0h]; struct CAggregatorDispMgr *
0x180005653  lea     rax, [rsp+68h+arg_10]
0x18000565b  lea     r14, [rsi+40h]
0x18000565f  mov     [rsp+68h+var_48], rax; struct CADsExtMgr **
0x180005664  mov     rcx, r14; pUnkOuter
0x180005667  mov     r9, rdi; unsigned __int16 *
0x18000566a  mov     r8, r15; struct CCredentials *
0x18000566d  call    ?CreateExtMgr@CADsExtMgr@@SAJPEAUIUnknown@@PEAVCAggregatorDispMgr@@AEAVCCredentials@@PEAGPEAPEAV1@@Z; CADsExtMgr::CreateExtMgr(IUnknown *,CAggregatorDispMgr *,CCredentials &,ushort *,CADsExtMgr * *)
0x180005672  mov     ebx, eax
0x180005674  test    eax, eax
0x180005676  js      loc_180005578
0x18000567c  mov     rax, [rsp+68h+arg_10]
0x180005684  mov     rcx, r14
0x180005687  mov     r8, [rsp+68h+arg_30]
0x18000568f  mov     rdx, [rsp+68h+arg_28]
0x180005697  mov     [rsi+0A8h], rax
0x18000569e  mov     rax, [r14]
0x1800056a1  mov     rax, [rax]
0x1800056a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056a9  mov     ebx, eax
0x1800056ab  test    eax, eax
0x1800056ad  js      loc_180005578
0x1800056b3  mov     rax, [r14]
0x1800056b6  mov     rcx, r14
0x1800056b9  mov     rax, [rax+10h]
0x1800056bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c2  jmp     short loc_1800056C9
0x1800056c4  mov     ebx, 80004003h
0x1800056c9  mov     eax, ebx
0x1800056cb  mov     rbx, [rsp+68h+arg_8]
0x1800056d0  add     rsp, 40h
0x1800056d4  pop     r15
0x1800056d6  pop     r14
0x1800056d8  pop     rdi
0x1800056d9  pop     rsi
0x1800056da  pop     rbp
0x1800056db  retn
```
