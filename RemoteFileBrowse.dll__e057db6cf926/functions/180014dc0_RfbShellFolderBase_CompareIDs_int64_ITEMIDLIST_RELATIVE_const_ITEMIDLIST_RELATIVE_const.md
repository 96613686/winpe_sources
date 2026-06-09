# RfbShellFolderBase::CompareIDs(__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x180014dc0`
- end: `0x180014ebd`
- name: `?CompareIDs@RfbShellFolderBase@@UEAAJ_JPEFBU_ITEMIDLIST_RELATIVE@@1@Z`
- size: `253`
- prototype: `__int64 __fastcall(RfbShellFolderBase *this, __int64, const ITEMIDLIST *, const ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014dc0`
- `0x180019010`

## import_xrefs

- `SHELL32!__imp_ILGetNext` at `0x180014e01`
- `SHELL32!__imp_ILGetNext` at `0x180014e0d`
- `SHELL32!__imp_ILGetNext` at `0x180014e01`
- `SHELL32!__imp_ILGetNext` at `0x180014e0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RfbShellFolderBase::CompareIDs(
        RfbShellFolderBase *this,
        __int64 a2,
        const ITEMIDLIST *a3,
        const ITEMIDLIST *a4)
{
  unsigned int v7; // ebx
  char *v8; // r14
  unsigned int v9; // eax
  const char *v10; // r9
  LPITEMIDLIST v11; // rsi
  LPITEMIDLIST v12; // rax
  LPITEMIDLIST v13; // rdi
  int v14; // ecx
  int v15; // edx
  __int64 v16; // rcx
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  v7 = 0;
  v8 = (char *)this - 8;
  try
  {
    v9 = (*(__int64 (**)(void))(*((_QWORD *)this - 1) + 96LL))();
    if ( v9 )
    {
      v7 = v9;
    }
    else
    {
      v11 = ILGetNext(a3);
      v12 = ILGetNext(a4);
      v13 = v12;
      if ( v11 && v11->mkid.cb )
      {
        v14 = 1;
        v15 = 1;
      }
      else
      {
        v15 = 0;
        v14 = 1;
      }
      if ( !v12 || !v12->mkid.cb )
        v14 = 0;
      if ( v15 && v14 )
      {
        (*(void (__fastcall **)(char *, __int64 *, _QWORD))(*(_QWORD *)v8 + 64LL))(v8, &v19, 0);
        v16 = v19;
        if ( v19 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, __int64, LPITEMIDLIST, LPITEMIDLIST))(*(_QWORD *)v19 + 56LL))(
                 v19,
                 a2,
                 v11,
                 v13);
          v16 = v19;
        }
        if ( v16 )
        {
          v19 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
      else
      {
        v7 = v15 - v14;
      }
    }
    result = v7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x259,
                           (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbshellfolderbase.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180014dc0  push    rbx
0x180014dc2  push    rsi
0x180014dc3  push    rdi
0x180014dc4  push    r12
0x180014dc6  push    r14
0x180014dc8  push    r15
0x180014dca  sub     rsp, 38h
0x180014dce  mov     rdi, r9
0x180014dd1  mov     rsi, r8
0x180014dd4  mov     r15, rdx
0x180014dd7  xor     r12d, r12d
0x180014dda  mov     ebx, r12d
0x180014ddd  lea     r14, [rcx-8]
0x180014de1  mov     rax, [r14]
0x180014de4  mov     r8, r9
0x180014de7  mov     rdx, rsi
0x180014dea  mov     rcx, r14
0x180014ded  mov     rax, [rax+60h]
0x180014df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014df6  test    eax, eax
0x180014df8  jnz     loc_180014EA5
0x180014dfe  mov     rcx, rsi; pidl
0x180014e01  call    cs:__imp_ILGetNext
0x180014e07  mov     rsi, rax
0x180014e0a  mov     rcx, rdi; pidl
0x180014e0d  call    cs:__imp_ILGetNext
0x180014e13  mov     rdi, rax
0x180014e16  test    rsi, rsi
0x180014e19  jz      short loc_180014E2A
0x180014e1b  cmp     [rsi], r12w
0x180014e1f  jz      short loc_180014E2A
0x180014e21  lea     ecx, [r12+1]
0x180014e26  mov     edx, ecx
0x180014e28  jmp     short loc_180014E32
0x180014e2a  mov     edx, r12d
0x180014e2d  mov     ecx, 1
0x180014e32  test    rdi, rdi
0x180014e35  jz      short loc_180014E3D
0x180014e37  cmp     [rax], r12w
0x180014e3b  jnz     short loc_180014E40
0x180014e3d  mov     ecx, r12d
0x180014e40  test    edx, edx
0x180014e42  jz      short loc_180014E9F
0x180014e44  test    ecx, ecx
0x180014e46  jz      short loc_180014E9F
0x180014e48  mov     rax, [r14]
0x180014e4b  xor     r8d, r8d
0x180014e4e  lea     rdx, [rsp+68h+arg_0]
0x180014e53  mov     rcx, r14
0x180014e56  mov     rax, [rax+40h]
0x180014e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e5f  nop
0x180014e60  mov     rcx, [rsp+68h+arg_0]
0x180014e65  test    rcx, rcx
0x180014e68  jz      short loc_180014E86
0x180014e6a  mov     rax, [rcx]
0x180014e6d  mov     r9, rdi
0x180014e70  mov     r8, rsi
0x180014e73  mov     rdx, r15
0x180014e76  mov     rax, [rax+38h]
0x180014e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e7f  mov     ebx, eax
0x180014e81  mov     rcx, [rsp+68h+arg_0]
0x180014e86  test    rcx, rcx
0x180014e89  jz      short loc_180014E9D
0x180014e8b  mov     [rsp+68h+arg_0], r12
0x180014e90  mov     rax, [rcx]
0x180014e93  mov     rax, [rax+10h]
0x180014e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e9c  nop
0x180014e9d  jmp     short loc_180014EA7
0x180014e9f  mov     ebx, edx
0x180014ea1  sub     ebx, ecx
0x180014ea3  jmp     short loc_180014EA7
0x180014ea5  mov     ebx, eax
0x180014ea7  mov     eax, ebx
0x180014ea9  jmp     short loc_180014EAF
0x180014eab  mov     eax, dword ptr [rsp+68h+arg_0]
0x180014eaf  add     rsp, 38h
0x180014eb3  pop     r15
0x180014eb5  pop     r14
0x180014eb7  pop     r12
0x180014eb9  pop     rdi
0x180014eba  pop     rsi
0x180014ebb  pop     rbx
0x180014ebc  retn
```
