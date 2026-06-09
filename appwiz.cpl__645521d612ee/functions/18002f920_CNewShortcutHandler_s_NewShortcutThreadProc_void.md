# CNewShortcutHandler::s_NewShortcutThreadProc(void *)

- ea: `0x18002f920`
- end: `0x18002fb4a`
- name: `?s_NewShortcutThreadProc@CNewShortcutHandler@@CAKPEAX@Z`
- size: `554`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000791c`
- `0x180008b98`
- `0x18000eac4`
- `0x180017128`
- `0x18002f508`
- `0x18002f62c`
- `0x18002f920`
- `0x180044bd8`
- `0x180052dd0`
- `0x1800582a2`
- `0x1800582e0`
- `0x1800583a0`
- `0x180059010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x18002fa42`
- `SHELL32!SHCreateItemFromIDList` at `0x18002fa42`
- `SHELL32!__imp_ILFree` at `0x18002faf3`
- `SHELL32!__imp_ILFree` at `0x18002faf3`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18002f9d1`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18002f9d1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fa77`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fa77`

## string_xrefs

- `0x18002f954`: `NewLinkWizard`

## pseudocode

```c
__int64 __fastcall CNewShortcutHandler::s_NewShortcutThreadProc(__int64 *Parameter)
{
  int v2; // ebx
  unsigned int v3; // r9d
  const ITEMIDLIST *v4; // rcx
  LPVOID v6; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v8; // [rsp+40h] [rbp-C0h] BYREF
  int v9; // [rsp+48h] [rbp-B8h]
  WCHAR *v10; // [rsp+A80h] [rbp+980h]
  unsigned __int16 *v11; // [rsp+D20h] [rbp+C20h]
  _QWORD v12[42]; // [rsp+F50h] [rbp+E50h] BYREF
  unsigned __int16 v13[264]; // [rsp+10A0h] [rbp+FA0h] BYREF
  WCHAR pszPath[264]; // [rsp+12B0h] [rbp+11B0h] BYREF

  v2 = -1;
  wil::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v12,
    "NewLinkWizard");
  v12[0] = &AppWizLoggingTelemetry::NewLinkWizard::`vftable';
  AppWizLoggingTelemetry::NewLinkWizard::StartActivity((AppWizLoggingTelemetry::NewLinkWizard *)v12);
  if ( (int)SHGetNameAndFlagsW((LPCITEMIDLIST)Parameter[1], 0x8000u, v13, v3, 0) >= 0
    && StringCchCopyW(pszPath, 0x104u, v13) >= 0 )
  {
    PathRemoveFileSpecW(pszPath);
    memset_0(&v8, 0, 0xF08u);
    v8 = *Parameter;
    v11 = v13;
    v10 = pszPath;
    v9 = 32;
    v2 = LinkWizard((struct _WIZDATA *)&v8);
    if ( !v2 )
    {
      v4 = (const ITEMIDLIST *)Parameter[1];
      ppv = 0;
      if ( SHCreateItemFromIDList(v4, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv) >= 0 )
      {
        v6 = 0;
        if ( CoCreateInstance(&CLSID_FileOperation, 0, v2 + 1, &GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8, &v6) >= 0 )
        {
          if ( (*(int (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v6 + 40LL))(v6, (unsigned int)(v2 + 20)) >= 0
            && (*(int (__fastcall **)(LPVOID, void *, _QWORD))(*(_QWORD *)v6 + 144LL))(v6, ppv, 0) >= 0 )
          {
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 168LL))(v6);
          }
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
  }
  ILFree((LPITEMIDLIST)Parameter[1]);
  operator delete(Parameter);
  wil::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v12,
    (v2 >> 31) & 0x80004005);
  AppWizLoggingTelemetry::NewLinkWizard::~NewLinkWizard((AppWizLoggingTelemetry::NewLinkWizard *)v12);
  return 0;
}

```

## disassembly

```asm
0x18002f920  mov     [rsp-8+arg_8], rbx
0x18002f925  mov     [rsp-8+arg_10], rdi
0x18002f92a  push    rbp
0x18002f92b  lea     rbp, [rsp-13D0h]
0x18002f933  mov     eax, 14D0h
0x18002f938  call    _alloca_probe
0x18002f93d  sub     rsp, rax
0x18002f940  mov     rax, cs:__security_cookie
0x18002f947  xor     rax, rsp
0x18002f94a  mov     [rbp+13D0h+var_10], rax
0x18002f951  mov     rdi, rcx
0x18002f954  lea     rdx, aNewlinkwizard; "NewLinkWizard"
0x18002f95b  lea     rcx, [rbp+13D0h+var_580]
0x18002f962  or      ebx, 0FFFFFFFFh
0x18002f965  call    ??0?$ActivityBase@VAppWizLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002f96a  lea     rax, ??_7NewLinkWizard@AppWizLoggingTelemetry@@6B@; const AppWizLoggingTelemetry::NewLinkWizard::`vftable'
0x18002f971  lea     rcx, [rbp+13D0h+var_580]; this
0x18002f978  mov     [rbp+13D0h+var_580], rax
0x18002f97f  call    ?StartActivity@NewLinkWizard@AppWizLoggingTelemetry@@QEAAXXZ; AppWizLoggingTelemetry::NewLinkWizard::StartActivity(void)
0x18002f984  mov     rcx, [rdi+8]; pidl
0x18002f988  lea     r8, [rbp+13D0h+var_430]; unsigned __int16 *
0x18002f98f  mov     edx, 8000h; unsigned int
0x18002f994  mov     [rsp+14D0h+var_14B0], 0; unsigned int *
0x18002f99d  call    ?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)
0x18002f9a2  test    eax, eax
0x18002f9a4  js      loc_18002FAEF
0x18002f9aa  lea     r8, [rbp+13D0h+var_430]; unsigned __int16 *
0x18002f9b1  mov     edx, 104h; unsigned __int64
0x18002f9b6  lea     rcx, [rbp+13D0h+pszPath]; unsigned __int16 *
0x18002f9bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002f9c2  test    eax, eax
0x18002f9c4  js      loc_18002FAEF
0x18002f9ca  lea     rcx, [rbp+13D0h+pszPath]; pszPath
0x18002f9d1  call    cs:__imp_PathRemoveFileSpecW
0x18002f9d7  xor     edx, edx; Val
0x18002f9d9  lea     rcx, [rsp+14D0h+var_1490]; void *
0x18002f9de  mov     r8d, 0F08h; Size
0x18002f9e4  call    memset_0
0x18002f9e9  mov     rax, [rdi]
0x18002f9ec  lea     rcx, [rsp+14D0h+var_1490]; struct _WIZDATA *
0x18002f9f1  mov     [rsp+14D0h+var_1490], rax
0x18002f9f6  lea     rax, [rbp+13D0h+var_430]
0x18002f9fd  mov     [rbp+13D0h+var_7B0], rax
0x18002fa04  lea     rax, [rbp+13D0h+pszPath]
0x18002fa0b  mov     [rbp+13D0h+var_A50], rax
0x18002fa12  mov     [rsp+14D0h+var_1488], 20h ; ' '
0x18002fa1a  call    LinkWizard
0x18002fa1f  mov     ebx, eax
0x18002fa21  test    eax, eax
0x18002fa23  jnz     loc_18002FAEF
0x18002fa29  mov     rcx, [rdi+8]; pidl
0x18002fa2d  lea     r8, [rsp+14D0h+ppv]; ppv
0x18002fa32  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18002fa39  mov     [rsp+14D0h+ppv], 0
0x18002fa42  call    cs:__imp_SHCreateItemFromIDList
0x18002fa48  test    eax, eax
0x18002fa4a  js      loc_18002FAEF
0x18002fa50  lea     rax, [rsp+14D0h+var_14A0]
0x18002fa55  mov     [rsp+14D0h+var_14A0], 0
0x18002fa5e  lea     r9, _GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8; riid
0x18002fa65  mov     [rsp+14D0h+var_14B0], rax; ppv
0x18002fa6a  xor     edx, edx; pUnkOuter
0x18002fa6c  lea     r8d, [rbx+1]; dwClsContext
0x18002fa70  lea     rcx, CLSID_FileOperation; rclsid
0x18002fa77  call    cs:__imp_CoCreateInstance
0x18002fa7d  test    eax, eax
0x18002fa7f  js      short loc_18002FADE
0x18002fa81  mov     rcx, [rsp+14D0h+var_14A0]
0x18002fa86  lea     edx, [rbx+14h]
0x18002fa89  mov     rax, [rcx]
0x18002fa8c  mov     rax, [rax+28h]
0x18002fa90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa95  test    eax, eax
0x18002fa97  js      short loc_18002FACD
0x18002fa99  mov     rcx, [rsp+14D0h+var_14A0]
0x18002fa9e  xor     r8d, r8d
0x18002faa1  mov     rdx, [rsp+14D0h+ppv]
0x18002faa6  mov     rax, [rcx]
0x18002faa9  mov     rax, [rax+90h]
0x18002fab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fab5  test    eax, eax
0x18002fab7  js      short loc_18002FACD
0x18002fab9  mov     rcx, [rsp+14D0h+var_14A0]
0x18002fabe  mov     rax, [rcx]
0x18002fac1  mov     rax, [rax+0A8h]
0x18002fac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002facd  mov     rcx, [rsp+14D0h+var_14A0]
0x18002fad2  mov     rax, [rcx]
0x18002fad5  mov     rax, [rax+10h]
0x18002fad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fade  mov     rcx, [rsp+14D0h+ppv]
0x18002fae3  mov     rax, [rcx]
0x18002fae6  mov     rax, [rax+10h]
0x18002faea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002faef  mov     rcx, [rdi+8]; pidl
0x18002faf3  call    cs:__imp_ILFree
0x18002faf9  mov     rcx, rdi; lpMem
0x18002fafc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002fb01  sar     ebx, 1Fh
0x18002fb04  lea     rcx, [rbp+13D0h+var_580]
0x18002fb0b  and     ebx, 80004005h
0x18002fb11  mov     edx, ebx
0x18002fb13  call    ?Stop@?$ActivityBase@VAppWizLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AppWizLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002fb18  lea     rcx, [rbp+13D0h+var_580]; this
0x18002fb1f  call    ??1NewLinkWizard@AppWizLoggingTelemetry@@QEAA@XZ; AppWizLoggingTelemetry::NewLinkWizard::~NewLinkWizard(void)
0x18002fb24  xor     eax, eax
0x18002fb26  mov     rcx, [rbp+13D0h+var_10]
0x18002fb2d  xor     rcx, rsp; StackCookie
0x18002fb30  call    __security_check_cookie
0x18002fb35  lea     r11, [rsp+14D0h+var_s0]
0x18002fb3d  mov     rbx, [r11+18h]
0x18002fb41  mov     rdi, [r11+20h]
0x18002fb45  mov     rsp, r11
0x18002fb48  pop     rbp
0x18002fb49  retn
```
