# PCLmWriter::IStreamByteStream::AppendToStream(uchar const *,uint)

- ea: `0x18001a2b0`
- end: `0x18001a38e`
- name: `?AppendToStream@IStreamByteStream@PCLmWriter@@UEAAXPEBEI@Z`
- size: `222`
- prototype: `void __fastcall(PCLmWriter::IStreamByteStream *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015f0`
- `0x180002154`
- `0x180010050`
- `0x180018334`
- `0x18001a2b0`
- `0x18001f010`

## pseudocode

```c
void __fastcall PCLmWriter::IStreamByteStream::AppendToStream(
        PCLmWriter::IStreamByteStream *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  __int64 v3; // rbx
  unsigned int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // [rsp+20h] [rbp-88h]
  int v11; // [rsp+30h] [rbp-78h] BYREF
  char *v12; // [rsp+38h] [rbp-70h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-68h] BYREF

  v3 = *(_QWORD *)this;
  v7 = (*(__int64 (__fastcall **)(PCLmWriter::IStreamByteStream *))(*(_QWORD *)this + 16LL))(this);
  (*(void (__fastcall **)(PCLmWriter::IStreamByteStream *, _QWORD))(v3 + 32))(this, v7);
  v8 = *((_QWORD *)this + 9);
  v11 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int8 *, _QWORD, int *))(*(_QWORD *)v8 + 32LL))(
         v8,
         a2,
         a3,
         &v11);
  PrintCore::ThrowIfError(
    (PrintCore *)v9,
    (int)"Failure appending data to stream.",
    "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pclm\\lib\\istreambytestream.cpp",
    (const char *)0x39,
    v10);
  if ( a3 != v11 )
  {
    v12 = "Failure appending specified no of bytes.";
    PCLmWriter::ByteStreamException::ByteStreamException(
      (PCLmWriter::ByteStreamException *)pExceptionObject,
      (const char *const *)&v12,
      0x80048604);
    throw (PCLmWriter::ByteStreamException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18001a2b0  mov     [rsp+arg_18], rbx
0x18001a2b5  push    rbp
0x18001a2b6  push    rsi
0x18001a2b7  push    rdi
0x18001a2b8  sub     rsp, 90h
0x18001a2bf  mov     rax, cs:__security_cookie
0x18001a2c6  xor     rax, rsp
0x18001a2c9  mov     [rsp+0A8h+var_28], rax
0x18001a2d1  mov     rbx, [rcx]
0x18001a2d4  mov     ebp, r8d
0x18001a2d7  mov     rsi, rdx
0x18001a2da  mov     rdi, rcx
0x18001a2dd  mov     rax, [rbx+10h]
0x18001a2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2e6  mov     edx, eax
0x18001a2e8  mov     rcx, rdi
0x18001a2eb  mov     rax, [rbx+20h]
0x18001a2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2f4  mov     rcx, [rdi+48h]
0x18001a2f8  lea     r9, [rsp+0A8h+var_78]
0x18001a2fd  mov     [rsp+0A8h+var_78], 0
0x18001a305  mov     r8d, ebp
0x18001a308  mov     rdx, rsi
0x18001a30b  mov     rax, [rcx]
0x18001a30e  mov     rax, [rax+20h]
0x18001a312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a317  mov     r9d, 39h ; '9'; char *
0x18001a31d  lea     r8, aOnecoreuapPrin_2; "onecoreuap\\printscan\\print\\drivers\\"...
0x18001a324  lea     rdx, aFailureAppendi_0; "Failure appending data to stream."
0x18001a32b  mov     ecx, eax; this
0x18001a32d  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18001a332  cmp     ebp, [rsp+0A8h+var_78]
0x18001a336  jz      short loc_18001A36B
0x18001a338  lea     rax, aFailureAppendi; "Failure appending specified no of bytes"...
0x18001a33f  mov     r8d, 80048604h; int
0x18001a345  lea     rdx, [rsp+0A8h+var_70]; char **
0x18001a34a  mov     [rsp+0A8h+var_70], rax
0x18001a34f  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x18001a354  call    ??0ByteStreamException@PCLmWriter@@QEAA@AEBQEBDJ@Z; PCLmWriter::ByteStreamException::ByteStreamException(char const * const &,long)
0x18001a359  lea     rdx, _TI3?AVByteStreamException@PCLmWriter@@; pThrowInfo
0x18001a360  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18001a365  call    _CxxThrowException_0
0x18001a36b  mov     rcx, [rsp+0A8h+var_28]
0x18001a373  xor     rcx, rsp; StackCookie
0x18001a376  call    __security_check_cookie
0x18001a37b  mov     rbx, [rsp+0A8h+arg_18]
0x18001a383  add     rsp, 90h
0x18001a38a  pop     rdi
0x18001a38b  pop     rsi
0x18001a38c  pop     rbp
0x18001a38d  retn
```
