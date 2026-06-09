# Base::File::OpenImpl(ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18005f6c0`
- end: `0x18005f71a`
- name: `?OpenImpl@File@Base@@MEAAXKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `90`
- prototype: `void __fastcall(Base::File *__hidden this, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, DWORD, DWORD, HANDLE)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180079e30`

## callees

- `0x18005f6c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18005f6fd`
- `KERNEL32!CreateFileW` at `0x18005f6fd`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f6d5`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f6d5`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18005f70d`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18005f70d`

## pseudocode

```c
void __fastcall Base::File::OpenImpl(
        Base::File *this,
        DWORD a2,
        DWORD a3,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile)
{
  HANDLE FileW; // rax
  Base *v9; // rcx

  if ( *((_QWORD *)this + 1) != -1 )
  {
    Base::Throw((Base *)0x20, a2);
    __debugbreak();
  }
  FileW = CreateFileW(*((LPCWSTR *)this + 2), a2, a3, a4, dwCreationDisposition, dwFlagsAndAttributes, hTemplateFile);
  *((_QWORD *)this + 1) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    Base::ThrowLastError(v9);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x18005f6c0  push    rbx
0x18005f6c2  sub     rsp, 40h
0x18005f6c6  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x18005f6cb  mov     rbx, rcx
0x18005f6ce  jz      short loc_18005F6DC
0x18005f6d0  mov     ecx, 20h ; ' '
0x18005f6d5  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005f6db  int     3; Trap to Debugger
0x18005f6dc  mov     rax, [rsp+48h+arg_30]
0x18005f6e4  mov     rcx, [rcx+10h]; lpFileName
0x18005f6e8  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x18005f6ed  mov     eax, [rsp+48h+arg_28]
0x18005f6f1  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18005f6f5  mov     eax, [rsp+48h+arg_20]
0x18005f6f9  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x18005f6fd  call    cs:__imp_CreateFileW
0x18005f703  mov     [rbx+8], rax
0x18005f707  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005f70b  jnz     short loc_18005F714
0x18005f70d  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18005f713  int     3; Trap to Debugger
0x18005f714  add     rsp, 40h
0x18005f718  pop     rbx
0x18005f719  retn
```
