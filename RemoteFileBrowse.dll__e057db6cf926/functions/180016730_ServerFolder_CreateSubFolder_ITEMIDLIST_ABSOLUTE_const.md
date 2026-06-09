# ServerFolder::CreateSubFolder(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180016730`
- end: `0x1800167d1`
- name: `?CreateSubFolder@ServerFolder@@MEAA?AV?$ComPtr@UIShellFolder@@@WRL@Microsoft@@PEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `161`
- prototype: `__int64 *__fastcall(__int64, __int64 *, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800020d0`
- `0x1800056ec`
- `0x180007150`
- `0x180015d70`
- `0x180016730`

## pseudocode

```c
__int64 *__fastcall ServerFolder::CreateSubFolder(__int64 a1, __int64 *a2, const struct _ITEMIDLIST_ABSOLUTE *a3)
{
  void *v6; // rax
  __int64 v7; // rbx
  int v8; // eax
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v6 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
  if ( v6 )
    v7 = DiskFolder::DiskFolder(v6, a1 + 96);
  else
    v7 = 0;
  if ( a3 )
  {
    v8 = RfbShellFolderBase::Initialize((RfbShellFolderBase *)(v7 + 16), a3);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\serverfolder.cpp",
        (const char *)(unsigned int)v8,
        v10);
  }
  *a2 = (v7 + 24) & -(__int64)(v7 != 0);
  return a2;
}

```

## disassembly

```asm
0x180016730  mov     [rsp+arg_0], rbx
0x180016735  mov     [rsp+arg_8], rsi
0x18001673a  push    rdi
0x18001673b  sub     rsp, 30h
0x18001673f  mov     rsi, r8
0x180016742  mov     rdi, rdx
0x180016745  mov     rbx, rcx
0x180016748  mov     [rsp+38h+arg_10], 0
0x180016751  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016758  mov     ecx, 0A0h; unsigned __int64
0x18001675d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016762  test    rax, rax
0x180016765  jz      short loc_18001677D
0x180016767  lea     rdx, [rbx+60h]
0x18001676b  mov     rcx, rax
0x18001676e  call    ??0DiskFolder@@QEAA@AEBV?$shared_ptr@VRfbServerRegistrar@@@std@@@Z; DiskFolder::DiskFolder(std::shared_ptr<RfbServerRegistrar> const &)
0x180016773  mov     rbx, rax
0x180016776  mov     [rsp+38h+arg_10], rax
0x18001677b  jmp     short loc_18001677F
0x18001677d  xor     ebx, ebx
0x18001677f  test    rsi, rsi
0x180016782  jz      short loc_180016799
0x180016784  lea     rcx, [rbx+10h]; this
0x180016788  mov     rdx, rsi; struct _ITEMIDLIST_ABSOLUTE *
0x18001678b  call    ?Initialize@RfbShellFolderBase@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z; RfbShellFolderBase::Initialize(_ITEMIDLIST_ABSOLUTE const *)
0x180016790  mov     rcx, [rsp+38h]; this
0x180016795  test    eax, eax
0x180016797  js      short loc_1800167BC
0x180016799  lea     rcx, [rbx+18h]
0x18001679d  neg     rbx
0x1800167a0  sbb     rax, rax
0x1800167a3  and     rax, rcx
0x1800167a6  mov     [rdi], rax
0x1800167a9  mov     rax, rdi
0x1800167ac  mov     rbx, [rsp+38h+arg_0]
0x1800167b1  mov     rsi, [rsp+38h+arg_8]
0x1800167b6  add     rsp, 30h
0x1800167ba  pop     rdi
0x1800167bb  retn
0x1800167bc  mov     r9d, eax; char *
0x1800167bf  lea     r8, aVmUxUiRemotefi_6; "vm\\ux\\ui\\remotefilebrowse\\serverfol"...
0x1800167c6  mov     edx, 77h ; 'w'; void *
0x1800167cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
