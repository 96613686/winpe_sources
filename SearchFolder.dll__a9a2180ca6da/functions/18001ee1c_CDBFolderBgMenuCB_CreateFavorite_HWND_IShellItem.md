# CDBFolderBgMenuCB::_CreateFavorite(HWND__ *,IShellItem *)

- ea: `0x18001ee1c`
- end: `0x18001eef8`
- name: `?_CreateFavorite@CDBFolderBgMenuCB@@AEAAJPEAUHWND__@@PEAUIShellItem@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(CDBFolderBgMenuCB *__hidden this, HWND, struct IShellItem *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180020cf4`

## callees

- `0x18001ee1c`
- `0x180051010`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x18001ee4b`
- `SHELL32!SHGetKnownFolderPath` at `0x18001ee4b`
- `SHELL32!__imp_SHCreateLinksEx` at `0x18001eec6`
- `SHELL32!__imp_SHCreateLinksEx` at `0x18001eec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eee7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eee7`

## pseudocode

```c
__int64 __fastcall CDBFolderBgMenuCB::_CreateFavorite(CDBFolderBgMenuCB *this, HWND a2, struct IShellItem *a3)
{
  HRESULT v6; // ebx
  struct IShellItemVtbl *lpVtbl; // rax
  PWSTR ppszPath; // [rsp+40h] [rbp-38h] BYREF
  __int64 v10; // [rsp+98h] [rbp+20h] BYREF

  ppszPath = 0;
  v6 = SHGetKnownFolderPath(&FOLDERID_Links, 0x8000u, 0, &ppszPath);
  if ( v6 >= 0 )
  {
    lpVtbl = a3->lpVtbl;
    v10 = 0;
    v6 = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, __int64 *))lpVtbl->BindToHandler)(
           a3,
           0,
           &BHID_DataObject,
           &GUID_0000010e_0000_0000_c000_000000000046,
           &v10);
    if ( v6 >= 0 )
    {
      v6 = SHCreateLinksEx(a2, *((_QWORD *)this + 2), ppszPath, v10, 0, 0, 0);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    CoTaskMemFree(ppszPath);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ee1c  push    rbx
0x18001ee1e  push    rbp
0x18001ee1f  push    rsi
0x18001ee20  push    rdi
0x18001ee21  sub     rsp, 58h
0x18001ee25  mov     rdi, r8
0x18001ee28  mov     [rsp+78h+ppszPath], 0
0x18001ee31  mov     rsi, rdx
0x18001ee34  lea     r9, [rsp+78h+ppszPath]; ppszPath
0x18001ee39  mov     rbp, rcx
0x18001ee3c  xor     r8d, r8d; hToken
0x18001ee3f  mov     edx, 8000h; dwFlags
0x18001ee44  lea     rcx, FOLDERID_Links; rfid
0x18001ee4b  call    cs:__imp_SHGetKnownFolderPath
0x18001ee51  mov     ebx, eax
0x18001ee53  test    eax, eax
0x18001ee55  js      loc_18001EEED
0x18001ee5b  mov     rax, [rdi]
0x18001ee5e  lea     rcx, [rsp+78h+arg_18]
0x18001ee66  mov     [rsp+78h+var_58], rcx
0x18001ee6b  lea     r9, _GUID_0000010e_0000_0000_c000_000000000046
0x18001ee72  lea     r8, BHID_DataObject
0x18001ee79  mov     [rsp+78h+arg_18], 0
0x18001ee85  xor     edx, edx
0x18001ee87  mov     rcx, rdi
0x18001ee8a  mov     rax, [rax+18h]
0x18001ee8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee93  mov     ebx, eax
0x18001ee95  test    eax, eax
0x18001ee97  js      short loc_18001EEE2
0x18001ee99  mov     r9, [rsp+78h+arg_18]
0x18001eea1  mov     rcx, rsi
0x18001eea4  mov     r8, [rsp+78h+ppszPath]
0x18001eea9  mov     rdx, [rbp+10h]
0x18001eead  mov     [rsp+78h+var_48], 0
0x18001eeb5  mov     [rsp+78h+var_50], 0
0x18001eebe  mov     dword ptr [rsp+78h+var_58], 0
0x18001eec6  call    cs:__imp_SHCreateLinksEx
0x18001eecc  mov     rcx, [rsp+78h+arg_18]
0x18001eed4  mov     ebx, eax
0x18001eed6  mov     rax, [rcx]
0x18001eed9  mov     rax, [rax+10h]
0x18001eedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eee2  mov     rcx, [rsp+78h+ppszPath]; pv
0x18001eee7  call    cs:__imp_CoTaskMemFree
0x18001eeed  mov     eax, ebx
0x18001eeef  add     rsp, 58h
0x18001eef3  pop     rdi
0x18001eef4  pop     rsi
0x18001eef5  pop     rbp
0x18001eef6  pop     rbx
0x18001eef7  retn
```
