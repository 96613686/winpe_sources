# CFavoritesEnumerator_CreateInstance(IEdgeFavoritesEnumerator * *)

- ea: `0x18001ae5c`
- end: `0x18001af04`
- name: `?CFavoritesEnumerator_CreateInstance@@YAJPEAPEAUIEdgeFavoritesEnumerator@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(struct IEdgeFavoritesEnumerator **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001aaf4`

## callees

- `0x180002d3c`
- `0x18000ebb8`
- `0x18002d010`

## import_xrefs

- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x18001aec9`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x18001aec9`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetSpecialFolderLocation` at `0x18001aebb`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetSpecialFolderLocation` at `0x18001aebb`

## pseudocode

```c
__int64 __fastcall CFavoritesEnumerator_CreateInstance(struct IEdgeFavoritesEnumerator **a1)
{
  unsigned int v2; // ebx
  void *v4; // [rsp+50h] [rbp+8h]

  *a1 = 0;
  v4 = operator new(0x238u);
  *(_QWORD *)v4 = &TUnknownSTBaseFRE<char>::`vftable';
  *((_DWORD *)v4 + 2) = 1;
  TUnknownMT_IncrementDllComponentCount();
  *(_QWORD *)v4 = &CFavoritesEnumerator::`vftable'{for `TUnknownSTBaseFRE<char>'};
  *((_QWORD *)v4 + 2) = &CFavoritesEnumerator::`vftable'{for `IEdgeFavoritesEnumerator'};
  SHGetSpecialFolderLocation(0, 6, (LPITEMIDLIST *)v4 + 4);
  SHGetPathFromIDListW(*((LPCITEMIDLIST *)v4 + 4), (LPWSTR)v4 + 20);
  v2 = (**((__int64 (__fastcall ***)(__int64, GUID *, struct IEdgeFavoritesEnumerator **))v4 + 2))(
         (__int64)v4 + 16,
         &GUID_5f89caa4_98d6_4f4c_afcd_53e93eeff09f,
         a1);
  (*(void (__fastcall **)(__int64))(*((_QWORD *)v4 + 2) + 16LL))((__int64)v4 + 16);
  return v2;
}

```

## disassembly

```asm
0x18001ae5c  push    rbx
0x18001ae5e  push    rsi
0x18001ae5f  push    rdi
0x18001ae60  push    r14
0x18001ae62  sub     rsp, 28h
0x18001ae66  mov     r14, rcx
0x18001ae69  mov     qword ptr [rcx], 0
0x18001ae70  mov     ecx, 238h; Size
0x18001ae75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ae7a  mov     rdi, rax
0x18001ae7d  mov     [rsp+48h+arg_0], rax
0x18001ae82  lea     rax, ??_7?$TUnknownSTBaseFRE@D@@6B@; const TUnknownSTBaseFRE<char>::`vftable'
0x18001ae89  mov     [rdi], rax
0x18001ae8c  mov     dword ptr [rdi+8], 1
0x18001ae93  call    TUnknownMT_IncrementDllComponentCount
0x18001ae98  lea     rax, ??_7CFavoritesEnumerator@@6B?$TUnknownSTBaseFRE@D@@@; const CFavoritesEnumerator::`vftable'{for `TUnknownSTBaseFRE<char>'}
0x18001ae9f  mov     edx, 6; csidl
0x18001aea4  mov     [rdi], rax
0x18001aea7  lea     rsi, [rdi+10h]
0x18001aeab  lea     rax, ??_7CFavoritesEnumerator@@6BIEdgeFavoritesEnumerator@@@; const CFavoritesEnumerator::`vftable'{for `IEdgeFavoritesEnumerator'}
0x18001aeb2  xor     ecx, ecx; hwnd
0x18001aeb4  lea     r8, [rdi+20h]; ppidl
0x18001aeb8  mov     [rsi], rax
0x18001aebb  call    cs:__imp_SHGetSpecialFolderLocation
0x18001aec1  mov     rcx, [rdi+20h]; pidl
0x18001aec5  lea     rdx, [rdi+28h]; pszPath
0x18001aec9  call    cs:__imp_SHGetPathFromIDListW
0x18001aecf  mov     rax, [rsi]
0x18001aed2  lea     rdx, _GUID_5f89caa4_98d6_4f4c_afcd_53e93eeff09f
0x18001aed9  mov     r8, r14
0x18001aedc  mov     rcx, rsi
0x18001aedf  mov     rax, [rax]
0x18001aee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aee7  mov     rdx, [rsi]
0x18001aeea  mov     ebx, eax
0x18001aeec  mov     rcx, rsi
0x18001aeef  mov     rax, [rdx+10h]
0x18001aef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aef8  mov     eax, ebx
0x18001aefa  add     rsp, 28h
0x18001aefe  pop     r14
0x18001af00  pop     rdi
0x18001af01  pop     rsi
0x18001af02  pop     rbx
0x18001af03  retn
```
