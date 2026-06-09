# FileFolder::CreateSubFolder(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180007d40`
- end: `0x180007dbe`
- name: `?CreateSubFolder@FileFolder@@MEAA?AV?$ComPtr@UIShellFolder@@@WRL@Microsoft@@PEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `126`
- prototype: `__int64 *__fastcall(__int64, __int64 *, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004608`
- `0x180007150`
- `0x180007d40`
- `0x180015d70`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall FileFolder::CreateSubFolder(__int64 a1, __int64 *a2, const struct _ITEMIDLIST_ABSOLUTE *a3)
{
  __int64 v5; // rbx
  int v6; // eax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  Microsoft::WRL::Details::Make<FileFolder,std::shared_ptr<RfbServerRegistrar> &>(&v10, a1 + 160);
  v5 = v10;
  if ( a3 )
  {
    v6 = RfbShellFolderBase::Initialize((RfbShellFolderBase *)(v10 + 16), a3);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\filefolder.cpp",
        (const char *)(unsigned int)v6,
        v8);
  }
  *a2 = (v5 + 24) & -(__int64)(v5 != 0);
  return a2;
}

```

## disassembly

```asm
0x180007d40  mov     [rsp+arg_8], rbx
0x180007d45  mov     [rsp+arg_10], rsi
0x180007d4a  push    rdi
0x180007d4b  sub     rsp, 30h
0x180007d4f  mov     rsi, r8
0x180007d52  mov     rdi, rdx
0x180007d55  lea     rdx, [rcx+0A0h]
0x180007d5c  lea     rcx, [rsp+38h+arg_0]
0x180007d61  call    ??$Make@VFileFolder@@AEAV?$shared_ptr@VRfbServerRegistrar@@@std@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VFileFolder@@@12@AEAV?$shared_ptr@VRfbServerRegistrar@@@std@@@Z; Microsoft::WRL::Details::Make<FileFolder,std::shared_ptr<RfbServerRegistrar> &>(std::shared_ptr<RfbServerRegistrar> &)
0x180007d66  nop
0x180007d67  mov     rbx, [rsp+38h+arg_0]
0x180007d6c  test    rsi, rsi
0x180007d6f  jz      short loc_180007D86
0x180007d71  lea     rcx, [rbx+10h]; this
0x180007d75  mov     rdx, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x180007d78  call    ?Initialize@RfbShellFolderBase@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; RfbShellFolderBase::Initialize(_ITEMIDLIST_ABSOLUTE const *)
0x180007d7d  mov     rcx, [rsp+38h]; this
0x180007d82  test    eax, eax
0x180007d84  js      short loc_180007DA9
0x180007d86  lea     rcx, [rbx+18h]
0x180007d8a  neg     rbx
0x180007d8d  sbb     rax, rax
0x180007d90  and     rax, rcx
0x180007d93  mov     [rdi], rax
0x180007d96  mov     rax, rdi
0x180007d99  mov     rbx, [rsp+38h+arg_8]
0x180007d9e  mov     rsi, [rsp+38h+arg_10]
0x180007da3  add     rsp, 30h
0x180007da7  pop     rdi
0x180007da8  retn
0x180007da9  mov     r9d, eax; char *
0x180007dac  lea     r8, aVmUxUiRemotefi_8; "vm\\ux\\ui\\remotefilebrowse\\filefolde"...
0x180007db3  mov     edx, 168h; void *
0x180007db8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
