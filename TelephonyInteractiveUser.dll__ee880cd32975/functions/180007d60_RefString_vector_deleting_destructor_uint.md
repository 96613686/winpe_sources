# RefString::`vector deleting destructor'(uint)

- ea: `0x180007d60`
- end: `0x180007da3`
- name: `??_ERefString@@UEAAPEAXI@Z`
- size: `67`
- prototype: `void *__fastcall(RefString *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001984`
- `0x180007d60`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007d73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007d73`

## pseudocode

```c
HSTRING *__fastcall RefString::`vector deleting destructor'(HSTRING *this, char a2)
{
  WindowsDeleteString(this[2]);
  this[2] = 0;
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007d60  mov     [rsp+arg_0], rbx
0x180007d65  push    rdi
0x180007d66  sub     rsp, 20h
0x180007d6a  mov     rdi, rcx
0x180007d6d  mov     ebx, edx
0x180007d6f  mov     rcx, [rcx+10h]; string
0x180007d73  call    cs:__imp_WindowsDeleteString
0x180007d79  mov     qword ptr [rdi+10h], 0
0x180007d81  mov     dword ptr [rdi+0Ch], 0C0000001h
0x180007d88  test    bl, 1
0x180007d8b  jz      short loc_180007D95
0x180007d8d  mov     rcx, rdi; Block
0x180007d90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007d95  mov     rbx, [rsp+28h+arg_0]
0x180007d9a  mov     rax, rdi
0x180007d9d  add     rsp, 20h
0x180007da1  pop     rdi
0x180007da2  retn
```
