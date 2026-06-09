# ModularWindowPrivate::GetDesktopWallpaperPath

- ea: `0x18003b5dc`
- end: `0x18003b6dd`
- name: `ModularWindowPrivate::GetDesktopWallpaperPath`
- size: `257`
- prototype: `__int64 __fastcall(Base::Path *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006f588`
- `0x18006f5f4`

## callees

- `0x1800037d8`
- `0x1800041a4`
- `0x180004908`
- `0x180025f90`
- `0x18003b5dc`
- `0x18003b6e4`
- `0x18005ea5c`
- `0x18006ea88`

## import_xrefs

- `SHELL32!SHGetSpecialFolderPathW` at `0x18003b623`
- `SHELL32!SHGetSpecialFolderPathW` at `0x18003b623`
- `SHLWAPI!PathRenameExtensionW` at `0x18003b6ad`
- `SHLWAPI!PathRenameExtensionW` at `0x18003b6ad`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b6bc`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003b6bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ModularWindowPrivate::GetDesktopWallpaperPath(LPWSTR *this)
{
  int v2; // edx
  BOOL v3; // ebx
  struct _SECURITY_ATTRIBUTES *v4; // rdx
  LPCWSTR *v5; // rax
  __int64 v6; // r8
  int v7; // edx
  char v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_DWORD *)*this - 3) - 260;
  if ( (v2 | (1 - *((_DWORD *)*this - 2))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(this, 260, v2 | (unsigned int)(1 - *((_DWORD *)*this - 2)));
  v3 = SHGetSpecialFolderPathW(0, *this, 26, 1);
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(this, 0xFFFFFFFFLL);
  if ( v3 )
  {
    Base::Path::Append((Base::Path *)this, L"\\Microsoft\\Windows Photo Viewer");
    if ( !Base::Path::FileExists((Base::Path *)this) )
      Base::Directory::CreateTree(*this, v4);
  }
  v5 = (LPCWSTR *)Base::ResourceString::ResourceString((Base::ResourceString *)&v9, 0x1B58u);
  Base::Path::Append((Base::Path *)this, *v5);
  Base::String::~String((Base::String *)&v9);
  if ( ((*((_DWORD *)*this - 3) - 260) | (1 - *((_DWORD *)*this - 2))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(this, 260, v6);
  if ( !PathRenameExtensionW(*this, L".jpg") )
  {
    Base::Throw((Base *)0x800700CELL, v7);
    __debugbreak();
  }
  return ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(this, 0xFFFFFFFFLL);
}

```

## disassembly

```asm
0x18003b5dc  mov     [rsp+arg_8], rbx
0x18003b5e1  mov     [rsp+arg_10], rsi
0x18003b5e6  push    rdi
0x18003b5e7  sub     rsp, 20h
0x18003b5eb  mov     rdi, rcx
0x18003b5ee  mov     rax, [rcx]
0x18003b5f1  mov     esi, 1
0x18003b5f6  mov     r8d, esi
0x18003b5f9  sub     r8d, [rax-8]
0x18003b5fd  mov     edx, [rax-0Ch]
0x18003b600  sub     edx, 104h
0x18003b606  or      r8d, edx
0x18003b609  jge     short loc_18003B615
0x18003b60b  mov     edx, 104h
0x18003b610  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18003b615  mov     r9d, esi; fCreate
0x18003b618  mov     r8d, 1Ah; csidl
0x18003b61e  mov     rdx, [rdi]; pszPath
0x18003b621  xor     ecx, ecx; hwnd
0x18003b623  call    cs:__imp_SHGetSpecialFolderPathW
0x18003b629  mov     ebx, eax
0x18003b62b  or      edx, 0FFFFFFFFh
0x18003b62e  mov     rcx, rdi
0x18003b631  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18003b636  test    ebx, ebx
0x18003b638  jz      short loc_18003B65D
0x18003b63a  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows Photo Viewer"
0x18003b641  mov     rcx, rdi; this
0x18003b644  call    ?Append@Path@Base@@QEAAAEAV12@PEBG@Z; Base::Path::Append(ushort const *)
0x18003b649  mov     rcx, rdi; this
0x18003b64c  call    ?FileExists@Path@Base@@QEBA_NXZ; Base::Path::FileExists(void)
0x18003b651  test    al, al
0x18003b653  jnz     short loc_18003B65D
0x18003b655  mov     rcx, [rdi]; unsigned __int16 *
0x18003b658  call    ?CreateTree@Directory@Base@@SAXPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; Base::Directory::CreateTree(ushort const *,_SECURITY_ATTRIBUTES *)
0x18003b65d  mov     edx, 1B58h; unsigned int
0x18003b662  lea     rcx, [rsp+28h+arg_0]; this
0x18003b667  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x18003b66c  nop
0x18003b66d  mov     rdx, [rax]; pszMore
0x18003b670  mov     rcx, rdi; this
0x18003b673  call    ?Append@Path@Base@@QEAAAEAV12@PEBG@Z; Base::Path::Append(ushort const *)
0x18003b678  nop
0x18003b679  lea     rcx, [rsp+28h+arg_0]; this
0x18003b67e  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18003b683  mov     rax, [rdi]
0x18003b686  sub     esi, [rax-8]
0x18003b689  mov     ecx, [rax-0Ch]
0x18003b68c  sub     ecx, 104h
0x18003b692  or      esi, ecx
0x18003b694  jge     short loc_18003B6A3
0x18003b696  mov     edx, 104h
0x18003b69b  mov     rcx, rdi
0x18003b69e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18003b6a3  lea     rdx, pszExt; ".jpg"
0x18003b6aa  mov     rcx, [rdi]; pszPath
0x18003b6ad  call    cs:__imp_PathRenameExtensionW
0x18003b6b3  test    eax, eax
0x18003b6b5  jnz     short loc_18003B6C3
0x18003b6b7  mov     ecx, 800700CEh
0x18003b6bc  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003b6c2  int     3; Trap to Debugger
0x18003b6c3  or      edx, 0FFFFFFFFh
0x18003b6c6  mov     rcx, rdi
0x18003b6c9  mov     rbx, [rsp+28h+arg_8]
0x18003b6ce  mov     rsi, [rsp+28h+arg_10]
0x18003b6d3  add     rsp, 20h
0x18003b6d7  pop     rdi
0x18003b6d8  jmp     ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
```
