# CommonUtil::CFlatEnumFiles::`scalar deleting destructor'(uint)

- ea: `0x140011d80`
- end: `0x140011dfb`
- name: `??_GCFlatEnumFiles@CommonUtil@@UEAAPEAXI@Z`
- size: `123`
- prototype: `CommonUtil::CFlatEnumFiles *__fastcall(CommonUtil::CFlatEnumFiles *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400015f4`
- `0x140011d80`

## import_xrefs

- `KERNEL32!FindClose` at `0x140011dca`
- `KERNEL32!FindClose` at `0x140011dca`

## pseudocode

```c
CommonUtil::CFlatEnumFiles *__fastcall CommonUtil::CFlatEnumFiles::`scalar deleting destructor'(
        CommonUtil::CFlatEnumFiles *this,
        char a2)
{
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  char *v7; // rcx

  v4 = (void *)*((_QWORD *)this + 79);
  if ( v4 )
    operator delete(v4);
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
    operator delete(v5);
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
    operator delete(v6);
  v7 = (char *)*((_QWORD *)this + 2);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(v7);
  *(_QWORD *)this = &CommonUtil::IRefObject::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140011d80  mov     [rsp+arg_0], rbx
0x140011d85  push    rdi
0x140011d86  sub     rsp, 20h
0x140011d8a  mov     rbx, rcx
0x140011d8d  mov     edi, edx
0x140011d8f  mov     rcx, [rcx+278h]; void *
0x140011d96  test    rcx, rcx
0x140011d99  jz      short loc_140011DA0
0x140011d9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011da0  mov     rcx, [rbx+20h]; void *
0x140011da4  test    rcx, rcx
0x140011da7  jz      short loc_140011DAE
0x140011da9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011dae  mov     rcx, [rbx+18h]; void *
0x140011db2  test    rcx, rcx
0x140011db5  jz      short loc_140011DBC
0x140011db7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011dbc  mov     rcx, [rbx+10h]; hFindFile
0x140011dc0  lea     rax, [rcx-1]
0x140011dc4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140011dc8  ja      short loc_140011DD0
0x140011dca  call    cs:__imp_FindClose
0x140011dd0  lea     rax, ??_7IRefObject@CommonUtil@@6B@; const CommonUtil::IRefObject::`vftable'
0x140011dd7  mov     [rbx], rax
0x140011dda  test    dil, 1
0x140011dde  jz      short loc_140011DED
0x140011de0  mov     edx, 288h; unsigned __int64
0x140011de5  mov     rcx, rbx; void *
0x140011de8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011ded  mov     rax, rbx
0x140011df0  mov     rbx, [rsp+28h+arg_0]
0x140011df5  add     rsp, 20h
0x140011df9  pop     rdi
0x140011dfa  retn
```
