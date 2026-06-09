# TEMPFILEINFO::_OpenDeleteHandle(void)

- ea: `0x18000a374`
- end: `0x18000a40d`
- name: `?_OpenDeleteHandle@TEMPFILEINFO@@AEAAJXZ`
- size: `153`
- prototype: `__int64 __fastcall(TEMPFILEINFO *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009834`
- `0x18000a0fc`

## callees

- `0x180001c80`
- `0x18000a374`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000a3e6`
- `KERNEL32!CreateFileW` at `0x18000a3e6`

## pseudocode

```c
__int64 __fastcall TEMPFILEINFO::_OpenDeleteHandle(TEMPFILEINFO *this)
{
  int v1; // eax
  unsigned int v3; // edi
  const WCHAR *v4; // rcx
  HANDLE FileW; // rax
  const WCHAR *v6; // rcx

  v1 = *((_DWORD *)this + 132);
  v3 = 0;
  if ( *((_DWORD *)this + 140) )
  {
    if ( v1 )
      v4 = (const WCHAR *)*((_QWORD *)this + 67);
    else
      v4 = &ExistingFileName;
    FileW = CreateFileW(v4, 0, 7u, 0, 3u, 0x6000000u, 0);
  }
  else
  {
    if ( v1 )
      v6 = (const WCHAR *)*((_QWORD *)this + 67);
    else
      v6 = &ExistingFileName;
    FileW = CreateFileW(v6, 0, 7u, 0, 3u, 0x4000100u, 0);
  }
  *((_QWORD *)this + 71) = FileW;
  if ( FileW == (HANDLE)-1LL )
    return (unsigned int)HrGetLastError();
  return v3;
}

```

## disassembly

```asm
0x18000a374  mov     [rsp+arg_0], rbx
0x18000a379  push    rdi
0x18000a37a  sub     rsp, 40h
0x18000a37e  mov     eax, [rcx+210h]
0x18000a384  xor     edx, edx; dwDesiredAccess
0x18000a386  mov     rbx, rcx
0x18000a389  mov     edi, edx
0x18000a38b  cmp     [rcx+230h], edx
0x18000a391  jz      short loc_18000A3B6
0x18000a393  test    eax, eax
0x18000a395  jnz     short loc_18000A3A0
0x18000a397  lea     rcx, ExistingFileName
0x18000a39e  jmp     short loc_18000A3A7
0x18000a3a0  mov     rcx, [rcx+218h]
0x18000a3a7  mov     [rsp+48h+hTemplateFile], rdx
0x18000a3ac  mov     [rsp+48h+dwFlagsAndAttributes], 6000000h
0x18000a3b4  jmp     short loc_18000A3D7
0x18000a3b6  test    eax, eax
0x18000a3b8  jnz     short loc_18000A3C3
0x18000a3ba  lea     rcx, ExistingFileName
0x18000a3c1  jmp     short loc_18000A3CA
0x18000a3c3  mov     rcx, [rcx+218h]; lpFileName
0x18000a3ca  mov     [rsp+48h+hTemplateFile], rdx; hTemplateFile
0x18000a3cf  mov     [rsp+48h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x18000a3d7  xor     r9d, r9d; lpSecurityAttributes
0x18000a3da  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a3e2  lea     r8d, [r9+7]; dwShareMode
0x18000a3e6  call    cs:__imp_CreateFileW
0x18000a3ec  mov     [rbx+238h], rax
0x18000a3f3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a3f7  jnz     short loc_18000A400
0x18000a3f9  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18000a3fe  mov     edi, eax
0x18000a400  mov     rbx, [rsp+48h+arg_0]
0x18000a405  mov     eax, edi
0x18000a407  add     rsp, 40h
0x18000a40b  pop     rdi
0x18000a40c  retn
```
