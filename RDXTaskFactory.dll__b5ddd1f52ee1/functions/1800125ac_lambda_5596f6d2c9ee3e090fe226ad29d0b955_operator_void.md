# _lambda_5596f6d2c9ee3e090fe226ad29d0b955_::operator()(void)

- ea: `0x1800125ac`
- end: `0x180012873`
- name: `??R_lambda_5596f6d2c9ee3e090fe226ad29d0b955_@@QEAA@XZ`
- size: `711`
- prototype: `__int64 __fastcall(CMarshaledInterface *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180013050`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x18001094c`
- `0x1800125ac`
- `0x180012c48`
- `0x180013298`
- `0x18002e174`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800125f9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001263f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800125f9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001263f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012686`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012686`
- `ext-ms-win-shell-shell32-l1-2-0!SHCreateItemInKnownFolder` at `0x1800126ec`
- `ext-ms-win-shell-shell32-l1-2-0!SHCreateItemInKnownFolder` at `0x1800126ec`

## string_xrefs

- `0x180012631`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1800127c5`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x18001280f`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012823`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012838`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x18001284c`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012860`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x1800125eb`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _lambda_5596f6d2c9ee3e090fe226ad29d0b955_::operator()(CMarshaledInterface *this)
{
  CMarshaledInterface *v1; // rsi
  unsigned int v2; // edi
  RetailDemoUtil *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r8
  HRESULT v6; // eax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  wil *v18; // rcx
  __int64 v19; // r8
  const struct _GUID *v20; // rdx
  bool v21; // r9
  int v22; // eax
  unsigned int v23; // esi
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  const char *pvData; // [rsp+28h] [rbp-30h]
  int pdwType; // [rsp+20h] [rbp-38h]
  int pdwTypea; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID pcbData; // [rsp+68h] [rbp+10h] BYREF
  void *ppv; // [rsp+70h] [rbp+18h] BYREF
  void *v36; // [rsp+78h] [rbp+20h] BYREF

  v1 = this;
  v2 = 0;
  LODWORD(ppv) = 0;
  LODWORD(pcbData) = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
         L"Enabled",
         0x10010u,
         0,
         &ppv,
         (LPDWORD)&pcbData) )
  {
    LODWORD(pcbData) = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
      L"Enabled",
      0x20010010u,
      0,
      &ppv,
      (LPDWORD)&pcbData);
  }
  try
  {
    if ( !(_DWORD)ppv )
    {
      RemoveRetailDemoOfflineContentTask::RemoveRetailDemoOptionalComponents();
      pcbData = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pcbData, v4, v5);
      v6 = CoCreateInstance(&CLSID_FileOperation, 0, 3u, &GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8, &pcbData);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
          (const char *)(unsigned int)v6,
          pdwTypea);
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)pcbData + 40LL))(pcbData, 9748);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x27,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
          (const char *)(unsigned int)v7,
          pdwTypea);
      ppv = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v8, v9);
      v2 = SHCreateItemInKnownFolder(&FOLDERID_RetailDemo, 0, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      if ( (int)(v2 + 0x80000000) >= 0 && v2 != -2147467259 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2D,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
          (const char *)v2,
          pdwType);
      if ( (v2 & 0x80000000) == 0 )
      {
        v13 = (*(__int64 (__fastcall **)(LPVOID, void *, _QWORD))(*(_QWORD *)pcbData + 144LL))(pcbData, ppv, 0);
        if ( v13 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x30,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
            (const char *)(unsigned int)v13,
            pdwType);
        v14 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)pcbData + 168LL))(pcbData);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x31,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
            (const char *)(unsigned int)v14,
            pdwType);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v10, v11);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pcbData, v15, v16);
    }
    RetailDemoUtil::DeleteScheduledTaskToRemoveRetailDemoFolders(v3);
  }
  catch ( ... )
  {
    LODWORD(pcbData) = wil::ResultFromCaughtException(v18);
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x3B,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
      (const char *)(unsigned int)pcbData,
      (int)"RetailDemo Maintenance task failed to cleanup offline files",
      pvData);
    v1 = this;
    v2 = (unsigned int)pcbData;
  }
  *(_BYTE *)(*((_QWORD *)v1 + 1) + 16LL) = 1;
  v36 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36, v17, v19);
  v22 = CMarshaledInterface::_Unmarshal(v1, v20, &v36, v21);
  v23 = v22;
  if ( v22 >= 0 )
  {
    (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v36 + 32LL))(v36, v2);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36, v27, v28);
    return v2;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
      (const char *)(unsigned int)v22,
      pdwType);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36, v24, v25);
    return v23;
  }
}

```

## disassembly

```asm
0x1800125ac  mov     r11, rsp
0x1800125af  mov     [r11+8], rcx
0x1800125b3  push    rsi
0x1800125b4  push    rdi
0x1800125b5  sub     rsp, 48h
0x1800125b9  mov     rsi, rcx
0x1800125bc  xor     edi, edi
0x1800125be  mov     dword ptr [rsp+58h+ppv], edi
0x1800125c2  mov     dword ptr [rsp+58h+arg_8], 4
0x1800125ca  lea     rax, [r11+10h]
0x1800125ce  mov     [r11-28h], rax
0x1800125d2  lea     rax, [r11+18h]
0x1800125d6  mov     [r11-30h], rax
0x1800125da  mov     [r11-38h], rdi
0x1800125de  mov     r9d, 10010h; dwFlags
0x1800125e4  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1800125eb  lea     rdx, SubKey; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x1800125f2  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800125f9  call    cs:__imp_RegGetValueW
0x1800125ff  test    eax, eax
0x180012601  jz      short loc_180012645
0x180012603  mov     dword ptr [rsp+58h+arg_8], 4
0x18001260b  lea     rax, [rsp+58h+arg_8]
0x180012610  mov     [rsp+58h+pcbData], rax; pcbData
0x180012615  lea     rax, [rsp+58h+ppv]
0x18001261a  mov     [rsp+58h+pvData], rax; pvData
0x18001261f  mov     [rsp+58h+pdwType], rdi; pdwType
0x180012624  mov     r9d, 20010010h; dwFlags
0x18001262a  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x180012631  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180012638  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001263f  call    cs:__imp_RegGetValueW
0x180012645  cmp     dword ptr [rsp+58h+ppv], 0
0x18001264a  jnz     loc_18001277E
0x180012650  call    ?RemoveRetailDemoOptionalComponents@RemoveRetailDemoOfflineContentTask@@CAXXZ; RemoveRetailDemoOfflineContentTask::RemoveRetailDemoOptionalComponents(void)
0x180012655  mov     [rsp+58h+arg_8], 0
0x18001265e  lea     rcx, [rsp+58h+arg_8]
0x180012663  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012668  lea     rax, [rsp+58h+arg_8]
0x18001266d  mov     [rsp+58h+pdwType], rax; int
0x180012672  lea     r9, _GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8; riid
0x180012679  xor     edx, edx; pUnkOuter
0x18001267b  lea     r8d, [rdx+3]; dwClsContext
0x18001267f  lea     rcx, CLSID_FileOperation; rclsid
0x180012686  call    cs:__imp_CoCreateInstance
0x18001268c  mov     rcx, [rsp+58h]; this
0x180012691  test    eax, eax
0x180012693  js      loc_18001280C
0x180012699  mov     rcx, [rsp+58h+arg_8]
0x18001269e  mov     rax, [rcx]
0x1800126a1  mov     edx, 2614h
0x1800126a6  mov     rax, [rax+28h]
0x1800126aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126af  mov     rcx, [rsp+58h]; this
0x1800126b4  test    eax, eax
0x1800126b6  js      loc_180012820
0x1800126bc  mov     [rsp+58h+ppv], 0
0x1800126c5  lea     rcx, [rsp+58h+ppv]
0x1800126ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800126cf  lea     rax, [rsp+58h+ppv]
0x1800126d4  mov     [rsp+58h+pdwType], rax; int
0x1800126d9  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800126e0  xor     r8d, r8d; pszItem
0x1800126e3  xor     edx, edx; dwKFFlags
0x1800126e5  lea     rcx, FOLDERID_RetailDemo; kfid
0x1800126ec  call    cs:__imp_SHCreateItemInKnownFolder
0x1800126f2  mov     edi, eax
0x1800126f4  mov     eax, 80000000h
0x1800126f9  lea     ecx, [rdi+rax]
0x1800126fc  test    eax, ecx
0x1800126fe  jnz     short loc_18001270C
0x180012700  cmp     edi, 80004005h
0x180012706  jz      short loc_18001270C
0x180012708  mov     al, 1
0x18001270a  jmp     short loc_18001270E
0x18001270c  xor     al, al
0x18001270e  mov     rcx, [rsp+58h]; this
0x180012713  test    al, al
0x180012715  jnz     loc_180012835
0x18001271b  test    edi, edi
0x18001271d  js      short loc_180012769
0x18001271f  mov     rcx, [rsp+58h+arg_8]
0x180012724  mov     rax, [rcx]
0x180012727  xor     r8d, r8d
0x18001272a  mov     rdx, [rsp+58h+ppv]
0x18001272f  mov     rax, [rax+90h]
0x180012736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001273b  mov     rcx, [rsp+58h]; this
0x180012740  test    eax, eax
0x180012742  js      loc_180012849
0x180012748  mov     rcx, [rsp+58h+arg_8]
0x18001274d  mov     rax, [rcx]
0x180012750  mov     rax, [rax+0A8h]
0x180012757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001275c  mov     rcx, [rsp+58h]; this
0x180012761  test    eax, eax
0x180012763  js      loc_18001285D
0x180012769  lea     rcx, [rsp+58h+ppv]
0x18001276e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012773  nop
0x180012774  lea     rcx, [rsp+58h+arg_8]
0x180012779  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001277e  call    ?DeleteScheduledTaskToRemoveRetailDemoFolders@RetailDemoUtil@@YAXXZ; RetailDemoUtil::DeleteScheduledTaskToRemoveRetailDemoFolders(void)
0x180012783  nop
0x180012784  jmp     short loc_18001278F
0x180012786  mov     rsi, [rsp+58h+arg_0]
0x18001278b  mov     edi, dword ptr [rsp+58h+arg_8]
0x18001278f  mov     rax, [rsi+8]
0x180012793  mov     byte ptr [rax+10h], 1
0x180012797  mov     [rsp+58h+arg_18], 0
0x1800127a0  lea     rcx, [rsp+58h+arg_18]
0x1800127a5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800127aa  lea     r8, [rsp+58h+arg_18]; void **
0x1800127af  mov     rcx, rsi; this
0x1800127b2  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x1800127b7  mov     esi, eax
0x1800127b9  test    eax, eax
0x1800127bb  jns     short loc_1800127E5
0x1800127bd  mov     rcx, [rsp+58h]; this
0x1800127c2  mov     r9d, eax; char *
0x1800127c5  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800127cc  mov     edx, 40h ; '@'; void *
0x1800127d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800127d6  nop
0x1800127d7  lea     rcx, [rsp+58h+arg_18]
0x1800127dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800127e1  mov     eax, esi
0x1800127e3  jmp     short loc_180012805
0x1800127e5  mov     rcx, [rsp+58h+arg_18]
0x1800127ea  mov     rax, [rcx]
0x1800127ed  mov     edx, edi
0x1800127ef  mov     rax, [rax+20h]
0x1800127f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127f8  nop
0x1800127f9  lea     rcx, [rsp+58h+arg_18]
0x1800127fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012803  mov     eax, edi
0x180012805  add     rsp, 48h
0x180012809  pop     rdi
0x18001280a  pop     rsi
0x18001280b  retn
0x18001280c  mov     r9d, eax; char *
0x18001280f  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012816  mov     edx, 26h ; '&'; void *
0x18001281b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012820  mov     r9d, eax; char *
0x180012823  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001282a  mov     edx, 27h ; '''; void *
0x18001282f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012835  mov     r9d, edi; char *
0x180012838  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001283f  mov     edx, 2Dh ; '-'; void *
0x180012844  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012849  mov     r9d, eax; char *
0x18001284c  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012853  mov     edx, 30h ; '0'; void *
0x180012858  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001285d  mov     r9d, eax; char *
0x180012860  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012867  mov     edx, 31h ; '1'; void *
0x18001286c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
