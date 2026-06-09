# CGrepQuery::_AddSystemFoldersToExcludeTree(void)

- ea: `0x1800433c0`
- end: `0x180043510`
- name: `?_AddSystemFoldersToExcludeTree@CGrepQuery@@AEAAJXZ`
- size: `336`
- prototype: `__int64 __fastcall(CGrepQuery *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043254`

## callees

- `0x1800433c0`
- `0x180043518`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!__imp_GUIDFromStringW` at `0x180043479`
- `SHCORE!__imp_GUIDFromStringW` at `0x180043479`
- `Windows.Storage!ILFree` at `0x1800434bb`
- `Windows.Storage!ILFree` at `0x1800434bb`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x18004349b`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x18004349b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800434c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800434c5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_QuerySourceCreateFromKey` at `0x180043411`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_QuerySourceCreateFromKey` at `0x180043411`

## pseudocode

```c
__int64 __fastcall CGrepQuery::_AddSystemFoldersToExcludeTree(CGrepQuery *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-38h] BYREF
  __int64 v7; // [rsp+40h] [rbp-30h] BYREF
  __int64 v8; // [rsp+48h] [rbp-28h] BYREF
  KNOWNFOLDERID rfid; // [rsp+50h] [rbp-20h] BYREF

  v8 = 0;
  v2 = 1;
  if ( (int)QuerySourceCreateFromKey(
              -2147483646,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Search\\Preferences\\ExcludeSystemFolders",
              0,
              &GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac,
              &v8) >= 0 )
  {
    v7 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 24LL))(v8, &v7) >= 0 )
    {
      for ( pv = 0;
            !(*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v7 + 24LL))(v7, 1, &pv);
            CoTaskMemFree(pv) )
      {
        rfid = 0;
        if ( (unsigned int)GUIDFromStringW(pv, &rfid) )
        {
          ppidl = 0;
          if ( SHGetKnownFolderIDList(&rfid, 0x4000u, 0, &ppidl) >= 0 )
          {
            v2 = CIDLTree::AddData(*((_QWORD *)this + 18), v3, ppidl);
            ILFree(ppidl);
          }
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return v2;
}

```

## disassembly

```asm
0x1800433c0  mov     [rsp-8+arg_8], rbx
0x1800433c5  mov     [rsp-8+arg_10], rdi
0x1800433ca  push    rbp
0x1800433cb  mov     rbp, rsp
0x1800433ce  sub     rsp, 70h
0x1800433d2  mov     rax, cs:__security_cookie
0x1800433d9  xor     rax, rsp
0x1800433dc  mov     [rbp+var_10], rax
0x1800433e0  mov     rdi, rcx
0x1800433e3  mov     [rbp+var_28], 0
0x1800433eb  lea     rax, [rbp+var_28]
0x1800433ef  mov     rcx, 0FFFFFFFF80000002h
0x1800433f6  lea     r9, _GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac
0x1800433fd  mov     [rsp+70h+var_50], rax
0x180043402  xor     r8d, r8d
0x180043405  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004340c  mov     ebx, 1
0x180043411  call    cs:__imp_QuerySourceCreateFromKey
0x180043417  test    eax, eax
0x180043419  js      loc_1800434F0
0x18004341f  mov     rcx, [rbp+var_28]
0x180043423  lea     rdx, [rbp+var_30]
0x180043427  mov     [rbp+var_30], 0
0x18004342f  mov     rax, [rcx]
0x180043432  mov     rax, [rax+18h]
0x180043436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004343b  test    eax, eax
0x18004343d  js      loc_1800434E0
0x180043443  mov     [rbp+pv], 0
0x18004344b  mov     rcx, [rbp+var_30]
0x18004344f  lea     r8, [rbp+pv]
0x180043453  xor     r9d, r9d
0x180043456  mov     rax, [rcx]
0x180043459  lea     edx, [r9+1]
0x18004345d  mov     rax, [rax+18h]
0x180043461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043466  test    eax, eax
0x180043468  jnz     short loc_1800434D0
0x18004346a  mov     rcx, [rbp+pv]
0x18004346e  lea     rdx, [rbp+rfid]
0x180043472  xorps   xmm0, xmm0
0x180043475  movups  xmmword ptr [rbp+rfid.Data1], xmm0
0x180043479  call    cs:__imp_GUIDFromStringW
0x18004347f  test    eax, eax
0x180043481  jz      short loc_1800434C1
0x180043483  lea     r9, [rbp+ppidl]; ppidl
0x180043487  mov     [rbp+ppidl], 0
0x18004348f  xor     r8d, r8d; hToken
0x180043492  lea     rcx, [rbp+rfid]; rfid
0x180043496  mov     edx, 4000h; dwFlags
0x18004349b  call    cs:__imp_SHGetKnownFolderIDList
0x1800434a1  test    eax, eax
0x1800434a3  js      short loc_1800434C1
0x1800434a5  mov     r8, [rbp+ppidl]
0x1800434a9  mov     rcx, [rdi+90h]
0x1800434b0  call    ?AddData@CIDLTree@@QEAAJW4IDLDATAF@@PEBU_ITEMIDLIST_ABSOLUTE@@_JPEAPEAVCIDLNode@@@Z; CIDLTree::AddData(IDLDATAF,_ITEMIDLIST_ABSOLUTE const *,__int64,CIDLNode * *)
0x1800434b5  mov     rcx, [rbp+ppidl]; pidl
0x1800434b9  mov     ebx, eax
0x1800434bb  call    cs:__imp_ILFree
0x1800434c1  mov     rcx, [rbp+pv]; pv
0x1800434c5  call    cs:__imp_CoTaskMemFree
0x1800434cb  jmp     loc_18004344B
0x1800434d0  mov     rcx, [rbp+var_30]
0x1800434d4  mov     rax, [rcx]
0x1800434d7  mov     rax, [rax+10h]
0x1800434db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434e0  mov     rcx, [rbp+var_28]
0x1800434e4  mov     rax, [rcx]
0x1800434e7  mov     rax, [rax+10h]
0x1800434eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434f0  mov     eax, ebx
0x1800434f2  mov     rcx, [rbp+var_10]
0x1800434f6  xor     rcx, rsp; StackCookie
0x1800434f9  call    __security_check_cookie
0x1800434fe  lea     r11, [rsp+70h+var_s0]
0x180043503  mov     rbx, [r11+18h]
0x180043507  mov     rdi, [r11+20h]
0x18004350b  mov     rsp, r11
0x18004350e  pop     rbp
0x18004350f  retn
```
