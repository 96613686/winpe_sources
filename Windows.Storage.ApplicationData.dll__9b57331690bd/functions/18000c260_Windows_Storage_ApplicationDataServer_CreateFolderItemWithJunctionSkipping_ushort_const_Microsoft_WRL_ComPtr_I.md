# Windows::Storage::ApplicationDataServer::CreateFolderItemWithJunctionSkipping(ushort const *,Microsoft::WRL::ComPtr<IShellItem> &)

- ea: `0x18000c260`
- end: `0x18000c3bb`
- name: `?CreateFolderItemWithJunctionSkipping@ApplicationDataServer@Storage@Windows@@CAJPEBGAEAV?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(const wchar_t *folderPath, Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *shellItem)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18003592c`
- `0x1800360f4`
- `0x1800366f4`

## callees

- `0x180003820`
- `0x18000c260`
- `0x18000c3c4`
- `0x18000c478`
- `0x18000cfc8`
- `0x180021efc`
- `0x1800415ee`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18000c34c`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18000c34c`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18000c2ae`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x18000c2ae`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataServer::CreateFolderItemWithJunctionSkipping(
        const wchar_t *folderPath,
        Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *shellItem)
{
  int v4; // eax
  Windows::ApplicationModel::Core::ICoreApplicationPrivate *ptr; // rdi
  int v6; // ebx
  HRESULT v7; // eax
  HRESULT v9; // r9d
  unsigned int v10; // edx
  wil::ShellBindContextHelper bindCtx; // [rsp+20h] [rbp-E0h] BYREF
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> v12; // [rsp+28h] [rbp-D8h] BYREF
  _WIN32_FIND_DATAW fd; // [rsp+30h] [rbp-D0h] BYREF
  void *retaddr; // [rsp+2A8h] [rbp+1A8h]

  bindCtx.m_bindCtx.ptr_ = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&bindCtx);
  CreateBindCtx(0, &bindCtx.m_bindCtx.ptr_);
  fd.dwFileAttributes = 16;
  memset_0(&fd.ftCreationTime, 0, 0x24Cu);
  v12.ptr_ = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
  v4 = Microsoft::WRL::Details::MakeAndInitialize<wil::FileSystemBindData,IFileSystemBindData2,_WIN32_FIND_DATAW const &>(
         (IFileSystemBindData2 **)&v12,
         &fd);
  ptr = v12.ptr_;
  v6 = v4;
  if ( v4 >= 0 )
    v6 = wil::ShellBindContextHelper::SetFileSystemBindData(&bindCtx, (IFileSystemBindData2 *)v12.ptr_);
  if ( ptr )
    ptr->Release(ptr);
  if ( v6 < 0 )
  {
    v9 = v6;
    v10 = 1970;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v10,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      v9);
    goto LABEL_9;
  }
  v7 = wil::ShellBindContextHelper::SetSkipAllJunctions(&bindCtx);
  v6 = v7;
  if ( v7 < 0 )
  {
    v10 = 1973;
LABEL_14:
    v9 = v7;
    goto LABEL_11;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(shellItem);
  v7 = SHCreateItemFromParsingName(
         folderPath,
         bindCtx.m_bindCtx.ptr_,
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         (void **)&shellItem->ptr_);
  v6 = v7;
  if ( v7 < 0 )
  {
    v10 = 1975;
    goto LABEL_14;
  }
  v6 = 0;
LABEL_9:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&bindCtx);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c260  mov     [rsp-8+arg_10], rbx
0x18000c265  mov     [rsp-8+arg_18], rsi
0x18000c26a  push    rbp
0x18000c26b  push    rdi
0x18000c26c  push    r14
0x18000c26e  lea     rbp, [rsp-190h]
0x18000c276  sub     rsp, 290h
0x18000c27d  mov     rax, cs:__security_cookie
0x18000c284  xor     rax, rsp
0x18000c287  mov     [rbp+1A0h+var_20], rax
0x18000c28e  mov     r14, folderPath
0x18000c291  mov     [rsp+2A0h+bindCtx.m_bindCtx.ptr_], 0
0x18000c29a  lea     folderPath, [rsp+2A0h+bindCtx]; this
0x18000c29f  mov     rsi, shellItem
0x18000c2a2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c2a7  lea     shellItem, [rsp+2A0h+bindCtx]; ppbc
0x18000c2ac  xor     ecx, ecx; reserved
0x18000c2ae  call    cs:__imp_CreateBindCtx
0x18000c2b4  xor     edx, edx; Val
0x18000c2b6  mov     [rsp+2A0h+fd.dwFileAttributes], 10h
0x18000c2be  mov     r8d, 24Ch; Size
0x18000c2c4  lea     folderPath, [rsp+2A0h+fd.ftCreationTime]; void *
0x18000c2c9  call    memset_0
0x18000c2ce  lea     folderPath, [rsp+2A0h+var_278]; this
0x18000c2d3  mov     [rsp+2A0h+var_278.ptr_], 0
0x18000c2dc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c2e1  lea     shellItem, [rsp+2A0h+fd]; <args_0>
0x18000c2e6  lea     folderPath, [rsp+2A0h+var_278]; result
0x18000c2eb  call    ??$MakeAndInitialize@VFileSystemBindData@wil@@UIFileSystemBindData2@@AEBU_WIN32_FIND_DATAW@@@Details@WRL@Microsoft@@YAJPEAPEAUIFileSystemBindData2@@AEBU_WIN32_FIND_DATAW@@@Z; Microsoft::WRL::Details::MakeAndInitialize<wil::FileSystemBindData,IFileSystemBindData2,_WIN32_FIND_DATAW const &>(IFileSystemBindData2 * *,_WIN32_FIND_DATAW const &)
0x18000c2f0  mov     rdi, [rsp+2A0h+var_278.ptr_]
0x18000c2f5  mov     ebx, eax
0x18000c2f7  test    eax, eax
0x18000c2f9  js      short loc_18000C30A
0x18000c2fb  mov     shellItem, rdi; value
0x18000c2fe  lea     folderPath, [rsp+2A0h+bindCtx]; this
0x18000c303  call    ?SetFileSystemBindData@ShellBindContextHelper@wil@@QEAAJPEAUIFileSystemBindData2@@@Z; wil::ShellBindContextHelper::SetFileSystemBindData(IFileSystemBindData2 *)
0x18000c308  mov     ebx, eax
0x18000c30a  test    rdi, rdi
0x18000c30d  jz      short loc_18000C31E
0x18000c30f  mov     rax, [rdi]
0x18000c312  mov     folderPath, rdi
0x18000c315  mov     rax, [rax+10h]
0x18000c319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c31e  test    ebx, ebx
0x18000c320  js      short loc_18000C38D
0x18000c322  lea     folderPath, [rsp+2A0h+bindCtx]; this
0x18000c327  call    ?SetSkipAllJunctions@ShellBindContextHelper@wil@@QEAAJXZ; wil::ShellBindContextHelper::SetSkipAllJunctions(void)
0x18000c32c  mov     ebx, eax
0x18000c32e  test    eax, eax
0x18000c330  js      short loc_18000C3AA
0x18000c332  mov     folderPath, rsi; this
0x18000c335  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c33a  mov     shellItem, [rsp+2A0h+bindCtx.m_bindCtx.ptr_]; pbc
0x18000c33f  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000c346  mov     r9, rsi; ppv
0x18000c349  mov     folderPath, r14; pszPath
0x18000c34c  call    cs:__imp_SHCreateItemFromParsingName
0x18000c352  mov     ebx, eax
0x18000c354  test    eax, eax
0x18000c356  js      short loc_18000C3B1
0x18000c358  xor     ebx, ebx
0x18000c35a  lea     folderPath, [rsp+2A0h+bindCtx]; this
0x18000c35f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000c364  mov     eax, ebx
0x18000c366  mov     folderPath, [rbp+1A0h+var_20]
0x18000c36d  xor     folderPath, rsp; StackCookie
0x18000c370  call    __security_check_cookie
0x18000c375  lea     r11, [rsp+2A0h+var_10]
0x18000c37d  mov     rbx, [r11+30h]
0x18000c381  mov     rsi, [r11+38h]
0x18000c385  mov     rsp, r11
0x18000c388  pop     r14
0x18000c38a  pop     rdi
0x18000c38b  pop     rbp
0x18000c38c  retn
0x18000c38d  mov     r9d, ebx; hr
0x18000c390  mov     edx, 7B2h; lineNumber
0x18000c395  mov     folderPath, [rbp+1A8h]; callerReturnAddress
0x18000c39c  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000c3a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c3a8  jmp     short loc_18000C35A
0x18000c3aa  mov     edx, 7B5h
0x18000c3af  jmp     short loc_18000C3B6
0x18000c3b1  mov     edx, 7B7h
0x18000c3b6  mov     r9d, eax
0x18000c3b9  jmp     short loc_18000C395
```
