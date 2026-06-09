# RfbShellFolderBase::CreateExtractIconObjectFromIconId(int,_GUID const &,void * *)

- ea: `0x180014ec4`
- end: `0x180014f95`
- name: `?CreateExtractIconObjectFromIconId@RfbShellFolderBase@@IEAAXHAEBU_GUID@@PEAPEAX@Z`
- size: `209`
- prototype: `void __fastcall(RfbShellFolderBase *this, unsigned int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006800`
- `0x180016c30`

## callees

- `0x180007150`
- `0x180014ec4`
- `0x180019010`

## import_xrefs

- `SHELL32!SHCreateDefaultExtractIcon` at `0x180014ef3`
- `SHELL32!SHCreateDefaultExtractIcon` at `0x180014ef3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall RfbShellFolderBase::CreateExtractIconObjectFromIconId(
        RfbShellFolderBase *this,
        unsigned int a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT v7; // eax
  void *v8; // rcx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v11; // [rsp+30h] [rbp+8h] BYREF

  v11 = 0;
  v7 = SHCreateDefaultExtractIcon(&GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58, &v11);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v11 + 24LL))(v11, 4);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, 0, a2);
      if ( v7 >= 0 )
        v7 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v11)(v11, a3, a4);
    }
  }
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x595,
      (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
      (const char *)(unsigned int)v7,
      v9);
  v8 = v11;
  if ( v11 )
  {
    v11 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
  }
}

```

## disassembly

```asm
0x180014ec4  mov     rax, rsp
0x180014ec7  mov     [rax+10h], rbx
0x180014ecb  mov     [rax+18h], rsi
0x180014ecf  mov     [rax+8], rcx
0x180014ed3  push    rdi; int
0x180014ed4  sub     rsp, 20h
0x180014ed8  mov     rdi, r9
0x180014edb  mov     rsi, r8
0x180014ede  mov     ebx, edx
0x180014ee0  mov     qword ptr [rax+8], 0
0x180014ee8  lea     rdx, [rax+8]; ppv
0x180014eec  lea     rcx, _GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58; riid
0x180014ef3  call    cs:__imp_SHCreateDefaultExtractIcon
0x180014ef9  test    eax, eax
0x180014efb  js      short loc_180014F47
0x180014efd  mov     rcx, [rsp+28h+arg_0]
0x180014f02  mov     rax, [rcx]
0x180014f05  mov     edx, 4
0x180014f0a  mov     rax, [rax+18h]
0x180014f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f13  test    eax, eax
0x180014f15  js      short loc_180014F47
0x180014f17  mov     rcx, [rsp+28h+arg_0]
0x180014f1c  mov     rax, [rcx]
0x180014f1f  mov     r8d, ebx
0x180014f22  xor     edx, edx
0x180014f24  mov     rax, [rax+28h]
0x180014f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f2d  test    eax, eax
0x180014f2f  js      short loc_180014F47
0x180014f31  mov     rcx, [rsp+28h+arg_0]
0x180014f36  mov     rax, [rcx]
0x180014f39  mov     r8, rdi
0x180014f3c  mov     rdx, rsi
0x180014f3f  mov     rax, [rax]
0x180014f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f47  mov     rcx, [rsp+28h]; this
0x180014f4c  test    eax, eax
0x180014f4e  js      short loc_180014F80
0x180014f50  mov     rcx, [rsp+28h+arg_0]
0x180014f55  test    rcx, rcx
0x180014f58  jz      short loc_180014F70
0x180014f5a  mov     [rsp+28h+arg_0], 0
0x180014f63  mov     rax, [rcx]
0x180014f66  mov     rax, [rax+10h]
0x180014f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f6f  nop
0x180014f70  mov     rbx, [rsp+28h+arg_8]
0x180014f75  mov     rsi, [rsp+28h+arg_10]
0x180014f7a  add     rsp, 20h
0x180014f7e  pop     rdi
0x180014f7f  retn
0x180014f80  mov     r9d, eax; char *
0x180014f83  lea     r8, aVmUxUiRemotefi_1; "vm\\ux\\ui\\remotefilebrowse\\rfbshellf"...
0x180014f8a  mov     edx, 595h; void *
0x180014f8f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
