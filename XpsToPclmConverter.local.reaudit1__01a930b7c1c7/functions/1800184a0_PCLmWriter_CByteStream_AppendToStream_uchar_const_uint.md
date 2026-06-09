# PCLmWriter::CByteStream::AppendToStream(uchar const *,uint)

- ea: `0x1800184a0`
- end: `0x1800184e9`
- name: `?AppendToStream@CByteStream@PCLmWriter@@MEAAXPEBEI@Z`
- size: `73`
- prototype: `void __fastcall __noreturn(PCLmWriter::CByteStream *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002154`
- `0x180018334`

## string_xrefs

- `0x1800184b6`: `Stream is read only`

## pseudocode

```c
void __fastcall __noreturn PCLmWriter::CByteStream::AppendToStream(
        PCLmWriter::CByteStream *this,
        const unsigned __int8 *a2)
{
  char *v2; // [rsp+20h] [rbp-68h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-58h] BYREF

  v2 = "Stream is read only";
  PCLmWriter::ByteStreamException::ByteStreamException(
    (PCLmWriter::ByteStreamException *)pExceptionObject,
    (const char *const *)&v2,
    -2147187195);
  throw (PCLmWriter::ByteStreamException *)pExceptionObject;
}

```

## disassembly

```asm
0x1800184a0  sub     rsp, 88h
0x1800184a7  mov     rax, cs:__security_cookie
0x1800184ae  xor     rax, rsp
0x1800184b1  mov     [rsp+88h+var_18], rax
0x1800184b6  lea     rax, aStreamIsReadOn; "Stream is read only"
0x1800184bd  mov     r8d, 80048605h; int
0x1800184c3  lea     rdx, [rsp+88h+var_68]; char **
0x1800184c8  mov     [rsp+88h+var_68], rax
0x1800184cd  lea     rcx, [rsp+88h+pExceptionObject]; this
0x1800184d2  call    ??0ByteStreamException@PCLmWriter@@QEAA@AEBQEBDJ@Z; PCLmWriter::ByteStreamException::ByteStreamException(char const * const &,long)
0x1800184d7  lea     rdx, _TI3?AVByteStreamException@PCLmWriter@@; pThrowInfo
0x1800184de  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800184e3  call    _CxxThrowException_0
```
