# ResourceLoader6::SimpleResourceLoader::FileReadStream::FileReadStream(ushort const *)

- ea: `0x18003c0b0`
- end: `0x18003c16b`
- name: `??0FileReadStream@SimpleResourceLoader@ResourceLoader6@@QEAA@PEBG@Z`
- size: `187`
- prototype: `ResourceLoader6::SimpleResourceLoader::FileReadStream *__fastcall(ResourceLoader6::SimpleResourceLoader::FileReadStream *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18004ce50`

## callees

- `0x180014ebc`
- `0x180035640`
- `0x18003c0b0`
- `0x18003ed6c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c11e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003c11e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ResourceLoader6::SimpleResourceLoader::FileReadStream *__fastcall ResourceLoader6::SimpleResourceLoader::FileReadStream::FileReadStream(
        ResourceLoader6::SimpleResourceLoader::FileReadStream *this,
        const unsigned __int16 *a2)
{
  char *v3; // rdi
  HANDLE FileW; // rax
  _BYTE pExceptionObject[80]; // [rsp+48h] [rbp-50h] BYREF
  const void *retaddr; // [rsp+98h] [rbp+0h]

  *(_QWORD *)this = &ResourceLoader6::SimpleResourceLoader::FileReadStream::`vftable';
  *((_DWORD *)this + 2) = 1;
  v3 = (char *)this + 16;
  std::wstring::wstring((char *)this + 16, a2);
  if ( *((_QWORD *)v3 + 3) >= 8u )
    v3 = *(char **)v3;
  FileW = CreateFileW((LPCWSTR)v3, 0x20081u, 1u, 0, 3u, 0x80u, 0);
  *((_QWORD *)this + 6) = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18003c0b0  mov     rax, rsp
0x18003c0b3  mov     [rax+8], rcx
0x18003c0b7  push    rdi
0x18003c0b8  sub     rsp, 90h
0x18003c0bf  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x18003c0c7  mov     [rax+10h], rbx
0x18003c0cb  mov     rbx, rcx
0x18003c0ce  lea     rax, ??_7FileReadStream@SimpleResourceLoader@ResourceLoader6@@6B@; const ResourceLoader6::SimpleResourceLoader::FileReadStream::`vftable'
0x18003c0d5  mov     [rcx], rax
0x18003c0d8  mov     dword ptr [rcx+8], 1
0x18003c0df  lea     rdi, [rcx+10h]
0x18003c0e3  mov     rcx, rdi
0x18003c0e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18003c0eb  nop
0x18003c0ec  cmp     qword ptr [rdi+18h], 8
0x18003c0f1  jb      short loc_18003C0F6
0x18003c0f3  mov     rdi, [rdi]
0x18003c0f6  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x18003c0ff  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003c107  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18003c10f  xor     r9d, r9d; lpSecurityAttributes
0x18003c112  mov     edx, 20081h; dwDesiredAccess
0x18003c117  lea     r8d, [r9+1]; dwShareMode
0x18003c11b  mov     rcx, rdi; lpFileName
0x18003c11e  call    cs:__imp_CreateFileW
0x18003c124  mov     [rbx+30h], rax
0x18003c128  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c12c  jz      short loc_18003C157
0x18003c12e  mov     r8, [rsp+98h]; void *
0x18003c136  mov     edx, 80004005h; int
0x18003c13b  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18003c140  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18003c145  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18003c14c  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18003c151  call    _CxxThrowException_0
0x18003c157  mov     rax, rbx
0x18003c15a  mov     rbx, [rsp+98h+arg_8]
0x18003c162  add     rsp, 90h
0x18003c169  pop     rdi
0x18003c16a  retn
```
