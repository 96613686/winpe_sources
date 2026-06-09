# D3DApiWrapper::`scalar deleting destructor'(uint)

- ea: `0x180074fd0`
- end: `0x180075022`
- name: `??_GD3DApiWrapper@@EEAAPEAXI@Z`
- size: `82`
- prototype: `void *__fastcall(D3DApiWrapper *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180006994`
- `0x180074fd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180074ff6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180074ff6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075000`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075000`

## pseudocode

```c
D3DApiWrapper *__fastcall D3DApiWrapper::`scalar deleting destructor'(D3DApiWrapper *this, char a2)
{
  *(_QWORD *)this = &DesktopApiWrapper::`vftable';
  if ( *((_QWORD *)this + 1) )
    FreeLibrary(*((HMODULE *)this + 1));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180074fd0  mov     [rsp+arg_0], rbx
0x180074fd5  push    rdi
0x180074fd6  sub     rsp, 20h
0x180074fda  lea     rax, ??_7DesktopApiWrapper@@6B@; const DesktopApiWrapper::`vftable'
0x180074fe1  mov     edi, edx
0x180074fe3  mov     [rcx], rax
0x180074fe6  mov     rbx, rcx
0x180074fe9  mov     rax, [rcx+8]
0x180074fed  test    rax, rax
0x180074ff0  jz      short loc_180074FFC
0x180074ff2  mov     rcx, [rcx+8]; hLibModule
0x180074ff6  call    cs:__imp_FreeLibrary
0x180074ffc  lea     rcx, [rbx+10h]; lpCriticalSection
0x180075000  call    cs:__imp_DeleteCriticalSection
0x180075006  test    dil, 1
0x18007500a  jz      short loc_180075014
0x18007500c  mov     rcx, rbx; Block
0x18007500f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180075014  mov     rax, rbx
0x180075017  mov     rbx, [rsp+28h+arg_0]
0x18007501c  add     rsp, 20h
0x180075020  pop     rdi
0x180075021  retn
```
