# DiskFolder::CreateSubFolder(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180005e70`
- end: `0x180005eee`
- name: `?CreateSubFolder@DiskFolder@@MEAA?AV?$ComPtr@UIShellFolder@@@WRL@Microsoft@@PEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `126`
- prototype: `__int64 *__fastcall(__int64, __int64 *, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004608`
- `0x180005e70`
- `0x180007150`
- `0x180015d70`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall DiskFolder::CreateSubFolder(__int64 a1, __int64 *a2, const struct _ITEMIDLIST_ABSOLUTE *a3)
{
  __int64 v5; // rbx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  Microsoft::WRL::Details::Make<FileFolder,std::shared_ptr<RfbServerRegistrar> &>(&v10, a1 + 128);
  v5 = v10;
  if ( a3 )
  {
    v6 = RfbShellFolderBase::Initialize((RfbShellFolderBase *)(v10 + 16), a3);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\diskfolder.cpp",
        (const char *)(unsigned int)v6,
        v8);
  }
  *a2 = (v5 + 24) & -(__int64)(v5 != 0);
  return a2;
}

```

## disassembly

```asm
0x180005e70  mov     [rsp+arg_8], rbx
0x180005e75  mov     [rsp+arg_10], rsi
0x180005e7a  push    rdi
0x180005e7b  sub     rsp, 30h
0x180005e7f  mov     rsi, r8
0x180005e82  mov     rdi, rdx
0x180005e85  lea     rdx, [rcx+80h]
0x180005e8c  lea     rcx, [rsp+38h+arg_0]
0x180005e91  call    ??$Make@VFileFolder@@AEAV?$shared_ptr@VRfbServerRegistrar@@@std@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VFileFolder@@@12@AEAV?$shared_ptr@VRfbServerRegistrar@@@std@@@Z; Microsoft::WRL::Details::Make<FileFolder,std::shared_ptr<RfbServerRegistrar> &>(std::shared_ptr<RfbServerRegistrar> &)
0x180005e96  nop
0x180005e97  mov     rbx, [rsp+38h+arg_0]
0x180005e9c  test    rsi, rsi
0x180005e9f  jz      short loc_180005EB6
0x180005ea1  lea     rcx, [rbx+10h]; this
0x180005ea5  mov     rdx, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x180005ea8  call    ?Initialize@RfbShellFolderBase@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; RfbShellFolderBase::Initialize(_ITEMIDLIST_ABSOLUTE const *)
0x180005ead  mov     rcx, [rsp+38h]; this
0x180005eb2  test    eax, eax
0x180005eb4  js      short loc_180005ED9
0x180005eb6  lea     rcx, [rbx+18h]
0x180005eba  neg     rbx
0x180005ebd  sbb     rax, rax
0x180005ec0  and     rax, rcx
0x180005ec3  mov     [rdi], rax
0x180005ec6  mov     rax, rdi
0x180005ec9  mov     rbx, [rsp+38h+arg_8]
0x180005ece  mov     rsi, [rsp+38h+arg_10]
0x180005ed3  add     rsp, 30h
0x180005ed7  pop     rdi
0x180005ed8  retn
0x180005ed9  mov     r9d, eax; char *
0x180005edc  lea     r8, aVmUxUiRemotefi_7; "vm\\ux\\ui\\remotefilebrowse\\diskfolde"...
0x180005ee3  mov     edx, 93h; void *
0x180005ee8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
