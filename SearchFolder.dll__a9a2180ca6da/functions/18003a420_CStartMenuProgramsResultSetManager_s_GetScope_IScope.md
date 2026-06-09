# CStartMenuProgramsResultSetManager::s_GetScope(IScope * *)

- ea: `0x18003a420`
- end: `0x18003a4db`
- name: `?s_GetScope@CStartMenuProgramsResultSetManager@@SAJPEAPEAUIScope@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(struct IScope **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033838`
- `0x180039b1c`
- `0x18003bc20`

## callees

- `0x1800054b0`
- `0x180005c74`
- `0x180005c88`
- `0x1800289c8`
- `0x18003a420`

## import_xrefs

- `SHELL32!__imp_SHRestricted` at `0x18003a475`
- `SHELL32!__imp_SHRestricted` at `0x18003a475`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18003a44d`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18003a44d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStartMenuProgramsResultSetManager::s_GetScope(struct IScope **a1)
{
  int v2; // ebx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v4);
  v2 = SHCreateScope(0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, &v4);
  if ( v2 >= 0 )
  {
    AddKnownFolderToScope(v4, &FOLDERID_UserPinned, 5);
    if ( SHRestricted(REST_NOCOMMONGROUPS) || (v2 = AddKnownFolderToScope(v4, &FOLDERID_CommonStartMenu, 5), v2 >= 0) )
    {
      v2 = AddKnownFolderToScope(v4, &FOLDERID_StartMenu, 5);
      if ( v2 >= 0 )
        *a1 = (struct IScope *)ATL::CComPtrBase<IScope>::Detach(&v4);
    }
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003a420  mov     [rsp+arg_8], rbx
0x18003a425  push    rdi
0x18003a426  sub     rsp, 20h
0x18003a42a  mov     rdi, rcx
0x18003a42d  mov     qword ptr [rcx], 0
0x18003a434  lea     rcx, [rsp+28h+arg_0]; void *
0x18003a439  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003a43e  nop
0x18003a43f  lea     r8, [rsp+28h+arg_0]
0x18003a444  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x18003a44b  xor     ecx, ecx
0x18003a44d  call    cs:__imp_SHCreateScope
0x18003a453  mov     ebx, eax
0x18003a455  test    eax, eax
0x18003a457  js      short loc_18003A4C4
0x18003a459  mov     r8d, 5
0x18003a45f  lea     rdx, FOLDERID_UserPinned
0x18003a466  mov     rcx, [rsp+28h+arg_0]
0x18003a46b  call    ?AddKnownFolderToScope@@YAJPEAUIScope@@AEBU_GUID@@W4SCOPE_ITEM_FLAGS@@@Z; AddKnownFolderToScope(IScope *,_GUID const &,SCOPE_ITEM_FLAGS)
0x18003a470  mov     ecx, 400000h; rest
0x18003a475  call    cs:__imp_SHRestricted
0x18003a47b  test    eax, eax
0x18003a47d  jnz     short loc_18003A49A
0x18003a47f  lea     r8d, [rax+5]
0x18003a483  lea     rdx, FOLDERID_CommonStartMenu
0x18003a48a  mov     rcx, [rsp+28h+arg_0]
0x18003a48f  call    ?AddKnownFolderToScope@@YAJPEAUIScope@@AEBU_GUID@@W4SCOPE_ITEM_FLAGS@@@Z; AddKnownFolderToScope(IScope *,_GUID const &,SCOPE_ITEM_FLAGS)
0x18003a494  mov     ebx, eax
0x18003a496  test    eax, eax
0x18003a498  js      short loc_18003A4C4
0x18003a49a  mov     r8d, 5
0x18003a4a0  lea     rdx, FOLDERID_StartMenu
0x18003a4a7  mov     rcx, [rsp+28h+arg_0]
0x18003a4ac  call    ?AddKnownFolderToScope@@YAJPEAUIScope@@AEBU_GUID@@W4SCOPE_ITEM_FLAGS@@@Z; AddKnownFolderToScope(IScope *,_GUID const &,SCOPE_ITEM_FLAGS)
0x18003a4b1  mov     ebx, eax
0x18003a4b3  test    eax, eax
0x18003a4b5  js      short loc_18003A4C4
0x18003a4b7  lea     rcx, [rsp+28h+arg_0]
0x18003a4bc  call    ?Detach@?$CComPtrBase@UIScope@@@ATL@@QEAAPEAUIScope@@XZ; ATL::CComPtrBase<IScope>::Detach(void)
0x18003a4c1  mov     [rdi], rax
0x18003a4c4  lea     rcx, [rsp+28h+arg_0]
0x18003a4c9  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003a4ce  mov     eax, ebx
0x18003a4d0  mov     rbx, [rsp+28h+arg_8]
0x18003a4d5  add     rsp, 20h
0x18003a4d9  pop     rdi
0x18003a4da  retn
```
