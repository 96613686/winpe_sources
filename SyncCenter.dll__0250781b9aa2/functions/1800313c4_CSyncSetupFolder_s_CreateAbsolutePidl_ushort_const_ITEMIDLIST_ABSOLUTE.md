# CSyncSetupFolder::s_CreateAbsolutePidl(ushort const *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x1800313c4`
- end: `0x180031467`
- name: `?s_CreateAbsolutePidl@CSyncSetupFolder@@SAJPEBGPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004de00`
- `0x18004e0d0`

## callees

- `0x1800304e4`
- `0x1800313c4`

## import_xrefs

- `SHELL32!SHGetKnownFolderIDList` at `0x1800313f9`
- `SHELL32!SHGetKnownFolderIDList` at `0x1800313f9`
- `SHELL32!__imp_ILCombine` at `0x18003142b`
- `SHELL32!__imp_ILCombine` at `0x18003142b`
- `SHELL32!__imp_ILFree` at `0x180031444`
- `SHELL32!__imp_ILFree` at `0x18003144f`
- `SHELL32!__imp_ILFree` at `0x180031444`
- `SHELL32!__imp_ILFree` at `0x18003144f`

## pseudocode

```c
__int64 __fastcall CSyncSetupFolder::s_CreateAbsolutePidl(const unsigned __int16 *a1, struct _ITEMIDLIST_ABSOLUTE **a2)
{
  HRESULT ChildPidl; // ebx
  struct _ITEMIDLIST_ABSOLUTE *v5; // rax
  LPCITEMIDLIST pidl2; // [rsp+38h] [rbp+10h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  pidl1 = 0;
  ChildPidl = SHGetKnownFolderIDList(&FOLDERID_SyncSetupFolder, 0, 0, (LPITEMIDLIST *)&pidl1);
  if ( ChildPidl >= 0 )
  {
    pidl2 = 0;
    ChildPidl = CSyncSetupFolder::s_CreateChildPidl(a1, (struct _ITEMID_CHILD **)&pidl2);
    if ( ChildPidl >= 0 )
    {
      v5 = (struct _ITEMIDLIST_ABSOLUTE *)ILCombine(pidl1, pidl2);
      *a2 = v5;
      if ( !v5 )
        ChildPidl = -2147024882;
      ILFree((LPITEMIDLIST)pidl2);
    }
    ILFree((LPITEMIDLIST)pidl1);
  }
  return (unsigned int)ChildPidl;
}

```

## disassembly

```asm
0x1800313c4  mov     rax, rsp
0x1800313c7  mov     [rax+8], rbx
0x1800313cb  mov     [rax+20h], rsi
0x1800313cf  push    rdi
0x1800313d0  sub     rsp, 20h
0x1800313d4  mov     rsi, rdx
0x1800313d7  mov     qword ptr [rdx], 0
0x1800313de  mov     rdi, rcx
0x1800313e1  mov     qword ptr [rax+18h], 0
0x1800313e9  xor     edx, edx; dwFlags
0x1800313eb  lea     rcx, FOLDERID_SyncSetupFolder; rfid
0x1800313f2  lea     r9, [rax+18h]; ppidl
0x1800313f6  xor     r8d, r8d; hToken
0x1800313f9  call    cs:__imp_SHGetKnownFolderIDList
0x1800313ff  mov     ebx, eax
0x180031401  test    eax, eax
0x180031403  js      short loc_180031455
0x180031405  lea     rdx, [rsp+28h+pidl2]; struct _ITEMID_CHILD **
0x18003140a  mov     [rsp+28h+pidl2], 0
0x180031413  mov     rcx, rdi; unsigned __int16 *
0x180031416  call    ?s_CreateChildPidl@CSyncSetupFolder@@SAJPEBGPEAPEAU_ITEMID_CHILD@@@Z; CSyncSetupFolder::s_CreateChildPidl(ushort const *,_ITEMID_CHILD * *)
0x18003141b  mov     ebx, eax
0x18003141d  test    eax, eax
0x18003141f  js      short loc_18003144A
0x180031421  mov     rdx, [rsp+28h+pidl2]; pidl2
0x180031426  mov     rcx, [rsp+28h+pidl1]; pidl1
0x18003142b  call    cs:__imp_ILCombine
0x180031431  test    rax, rax
0x180031434  mov     [rsi], rax
0x180031437  mov     ecx, 8007000Eh
0x18003143c  cmovz   ebx, ecx
0x18003143f  mov     rcx, [rsp+28h+pidl2]; pidl
0x180031444  call    cs:__imp_ILFree
0x18003144a  mov     rcx, [rsp+28h+pidl1]; pidl
0x18003144f  call    cs:__imp_ILFree
0x180031455  mov     rsi, [rsp+28h+arg_18]
0x18003145a  mov     eax, ebx
0x18003145c  mov     rbx, [rsp+28h+arg_0]
0x180031461  add     rsp, 20h
0x180031465  pop     rdi
0x180031466  retn
```
