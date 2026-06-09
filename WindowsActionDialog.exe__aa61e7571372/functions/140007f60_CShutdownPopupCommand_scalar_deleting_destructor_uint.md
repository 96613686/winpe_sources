# CShutdownPopupCommand::`scalar deleting destructor'(uint)

- ea: `0x140007f60`
- end: `0x140007fa6`
- name: `??_GCShutdownPopupCommand@@UEAAPEAXI@Z`
- size: `70`
- prototype: `void *__fastcall(CShutdownPopupCommand *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000175c`
- `0x140007f60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007f78`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007f78`

## pseudocode

```c
CShutdownPopupCommand *__fastcall CShutdownPopupCommand::`scalar deleting destructor'(
        CShutdownPopupCommand *this,
        char a2)
{
  HMODULE v4; // rcx

  v4 = (HMODULE)*((_QWORD *)this + 2);
  if ( v4 )
    FreeLibrary(v4);
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140007f60  mov     [rsp+arg_0], rbx
0x140007f65  push    rdi
0x140007f66  sub     rsp, 20h
0x140007f6a  mov     rbx, rcx
0x140007f6d  mov     edi, edx
0x140007f6f  mov     rcx, [rcx+10h]; hLibModule
0x140007f73  test    rcx, rcx
0x140007f76  jz      short loc_140007F7E
0x140007f78  call    cs:__imp_FreeLibrary
0x140007f7e  mov     dword ptr [rbx+0Ch], 0C0000001h
0x140007f85  test    dil, 1
0x140007f89  jz      short loc_140007F98
0x140007f8b  mov     edx, 30h ; '0'
0x140007f90  mov     rcx, rbx; Block
0x140007f93  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007f98  mov     rax, rbx
0x140007f9b  mov     rbx, [rsp+28h+arg_0]
0x140007fa0  add     rsp, 20h
0x140007fa4  pop     rdi
0x140007fa5  retn
```
