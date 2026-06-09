# TextFile::RefreshBuffer(void)

- ea: `0x18009e148`
- end: `0x18009e1b6`
- name: `?RefreshBuffer@TextFile@@AEAAXXZ`
- size: `110`
- prototype: `void __fastcall(TextFile *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18009ddf4`
- `0x18009dfcc`

## callees

- `0x18009e148`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009e182`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18009e182`

## pseudocode

```c
void __fastcall TextFile::RefreshBuffer(TextFile *this)
{
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesRead = 0;
  *((_QWORD *)this + 514) = (char *)this + 16;
  *((_QWORD *)this + 515) = (char *)this + 16;
  if ( ReadFile(*(HANDLE *)this, (char *)this + 16, 0x1000u, &NumberOfBytesRead, 0) )
  {
    if ( NumberOfBytesRead )
      *((_QWORD *)this + 515) = *((_QWORD *)this + 514) + NumberOfBytesRead;
    else
      *((_BYTE *)this + 13) = 1;
  }
  else
  {
    *(_WORD *)((char *)this + 13) = 257;
  }
}

```

## disassembly

```asm
0x18009e148  push    rbx
0x18009e14a  sub     rsp, 30h
0x18009e14e  lea     rdx, [rcx+10h]; lpBuffer
0x18009e152  mov     [rsp+38h+NumberOfBytesRead], 0
0x18009e15a  mov     [rcx+1010h], rdx
0x18009e161  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009e166  mov     [rcx+1018h], rdx
0x18009e16d  mov     rbx, rcx
0x18009e170  mov     rcx, [rcx]; hFile
0x18009e173  mov     r8d, 1000h; nNumberOfBytesToRead
0x18009e179  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18009e182  call    cs:__imp_ReadFile
0x18009e188  test    eax, eax
0x18009e18a  jnz     short loc_18009E194
0x18009e18c  mov     word ptr [rbx+0Dh], 101h
0x18009e192  jmp     short loc_18009E1B0
0x18009e194  mov     eax, [rsp+38h+NumberOfBytesRead]
0x18009e198  test    eax, eax
0x18009e19a  jnz     short loc_18009E1A2
0x18009e19c  mov     byte ptr [rbx+0Dh], 1
0x18009e1a0  jmp     short loc_18009E1B0
0x18009e1a2  add     rax, [rbx+1010h]
0x18009e1a9  mov     [rbx+1018h], rax
0x18009e1b0  add     rsp, 30h
0x18009e1b4  pop     rbx
0x18009e1b5  retn
```
