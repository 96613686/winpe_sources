# DllRegisterServer

- ea: `0x180009e20`
- end: `0x180009f1b`
- name: `DllRegisterServer`
- size: `251`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180008c84`
- `0x1800093f8`
- `0x1800098c0`
- `0x180009e20`
- `0x180012010`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x180009e36`
- `KERNEL32!SetThreadLocale` at `0x180009f0a`
- `KERNEL32!SetThreadLocale` at `0x180009e36`
- `KERNEL32!SetThreadLocale` at `0x180009f0a`
- `KERNEL32!GetThreadLocale` at `0x180009e29`
- `KERNEL32!GetThreadLocale` at `0x180009e29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  unsigned int v1; // edx
  ATL::CAtlModule *v2; // rcx
  const unsigned __int16 *v3; // rdx
  HRESULT updated; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rdi
  __int64 *v6; // rax
  __int64 v7; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v8; // rax
  _QWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v11; // [rsp+30h] [rbp-38h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v10[0] = L"APPID";
  v10[1] = L"{71962dd6-5a51-4c62-99aa-65f9ee09ae2c}";
  v11 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v10);
  if ( updated >= 0 )
  {
    v5 = off_18001B110;
    v6 = (__int64 *)off_18001B118;
    if ( off_18001B110 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_18001B118 )
    {
      do
      {
        v7 = *(_QWORD *)v5;
        if ( *(_QWORD *)v5 )
        {
          updated = (*(__int64 (__fastcall **)(__int64))(v7 + 8))(1);
          if ( updated < 0 )
            goto LABEL_9;
          v8 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v7 + 56))();
          updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v7, v8, 1);
          if ( updated < 0 )
            goto LABEL_9;
          v6 = (__int64 *)off_18001B118;
        }
        v5 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v5 + 8);
      }
      while ( v5 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v6 );
    }
    updated = ATL::AtlRegisterTypeLib(off_18001B108, v3);
LABEL_9:
    if ( updated >= 0 && ATL::_pPerfRegFunc )
      updated = ATL::_pPerfRegFunc(hInstance);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180009e20  push    rbx
0x180009e22  push    rbp
0x180009e23  push    rsi
0x180009e24  push    rdi
0x180009e25  sub     rsp, 48h
0x180009e29  call    cs:__imp_GetThreadLocale
0x180009e2f  mov     ebp, eax
0x180009e31  mov     ecx, 800h; Locale
0x180009e36  call    cs:__imp_SetThreadLocale
0x180009e3c  lea     rax, aAppid; "APPID"
0x180009e43  mov     [rsp+68h+var_48], rax
0x180009e48  lea     rax, a71962dd65a514c; "{71962dd6-5a51-4c62-99aa-65f9ee09ae2c}"
0x180009e4f  mov     [rsp+68h+var_40], rax
0x180009e54  xorps   xmm0, xmm0
0x180009e57  movdqu  [rsp+68h+var_38], xmm0
0x180009e5d  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x180009e62  mov     r8d, 1; int
0x180009e68  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180009e6d  mov     ebx, eax
0x180009e6f  test    eax, eax
0x180009e71  js      loc_180009F08
0x180009e77  xor     ebx, ebx
0x180009e79  mov     rdi, cs:off_18001B110
0x180009e80  mov     rax, cs:off_18001B118
0x180009e87  cmp     rdi, rax
0x180009e8a  jnb     short loc_180009EDC
0x180009e8c  mov     rsi, [rdi]
0x180009e8f  test    rsi, rsi
0x180009e92  jz      short loc_180009ECF
0x180009e94  mov     ecx, 1
0x180009e99  mov     rax, [rsi+8]
0x180009e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ea2  mov     ebx, eax
0x180009ea4  test    eax, eax
0x180009ea6  js      short loc_180009EEA
0x180009ea8  mov     rax, [rsi+38h]
0x180009eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eb1  mov     r8d, 1; int
0x180009eb7  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180009eba  mov     rcx, [rsi]; rguid
0x180009ebd  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180009ec2  mov     ebx, eax
0x180009ec4  test    eax, eax
0x180009ec6  js      short loc_180009EEA
0x180009ec8  mov     rax, cs:off_18001B118
0x180009ecf  add     rdi, 8
0x180009ed3  cmp     rdi, rax
0x180009ed6  jb      short loc_180009E8C
0x180009ed8  test    ebx, ebx
0x180009eda  js      short loc_180009F08
0x180009edc  mov     rcx, cs:off_18001B108; HINSTANCE
0x180009ee3  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x180009ee8  mov     ebx, eax
0x180009eea  test    ebx, ebx
0x180009eec  js      short loc_180009F08
0x180009eee  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180009ef5  test    rax, rax
0x180009ef8  jz      short loc_180009F08
0x180009efa  mov     rcx, cs:hInstance
0x180009f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f06  mov     ebx, eax
0x180009f08  mov     ecx, ebp; Locale
0x180009f0a  call    cs:__imp_SetThreadLocale
0x180009f10  mov     eax, ebx
0x180009f12  add     rsp, 48h
0x180009f16  pop     rdi
0x180009f17  pop     rsi
0x180009f18  pop     rbp
0x180009f19  pop     rbx
0x180009f1a  retn
```
