# PCLmWriter::ByteStreamFlateEncoder::Initialize(void)

- ea: `0x18001a7d0`
- end: `0x18001a84b`
- name: `?Initialize@ByteStreamFlateEncoder@PCLmWriter@@UEAAXXZ`
- size: `123`
- prototype: `void __fastcall(PCLmWriter::ByteStreamFlateEncoder *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015f0`
- `0x180002154`
- `0x180012c90`
- `0x180018334`
- `0x18001a7d0`
- `0x18001a854`

## pseudocode

```c
void __fastcall PCLmWriter::ByteStreamFlateEncoder::Initialize(PCLmWriter::ByteStreamFlateEncoder *this)
{
  char *v2; // [rsp+20h] [rbp-68h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-58h] BYREF

  if ( !*((_BYTE *)this + 32) )
  {
    if ( !PCLmWriter::ByteStreamFlateEncoder::_EncodeData(this) )
    {
      v2 = "Data could not be encoded";
      PCLmWriter::ByteStreamException::ByteStreamException(
        (PCLmWriter::ByteStreamException *)pExceptionObject,
        (const char *const *)&v2,
        0x80048603);
      throw (PCLmWriter::ByteStreamException *)pExceptionObject;
    }
    PCLmWriter::MemoryByteStream::Initialize(this);
  }
}

```

## disassembly

```asm
0x18001a7d0  push    rbx
0x18001a7d2  sub     rsp, 80h
0x18001a7d9  mov     rax, cs:__security_cookie
0x18001a7e0  xor     rax, rsp
0x18001a7e3  mov     [rsp+88h+var_18], rax
0x18001a7e8  cmp     byte ptr [rcx+20h], 0
0x18001a7ec  mov     rbx, rcx
0x18001a7ef  jnz     short loc_18001A835
0x18001a7f1  call    ?_EncodeData@ByteStreamFlateEncoder@PCLmWriter@@AEAA_NXZ; PCLmWriter::ByteStreamFlateEncoder::_EncodeData(void)
0x18001a7f6  test    al, al
0x18001a7f8  jnz     short loc_18001A82D
0x18001a7fa  lea     rax, aDataCouldNotBe; "Data could not be encoded"
0x18001a801  mov     r8d, 80048603h; int
0x18001a807  lea     rdx, [rsp+88h+var_68]; char **
0x18001a80c  mov     [rsp+88h+var_68], rax
0x18001a811  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18001a816  call    ??0ByteStreamException@PCLmWriter@@QEAA@AEBQEBDJ@Z; PCLmWriter::ByteStreamException::ByteStreamException(char const * const &,long)
0x18001a81b  lea     rdx, _TI3?AVByteStreamException@PCLmWriter@@; pThrowInfo
0x18001a822  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001a827  call    _CxxThrowException_0
0x18001a82d  mov     rcx, rbx; this
0x18001a830  call    ?Initialize@MemoryByteStream@PCLmWriter@@UEAAXXZ; PCLmWriter::MemoryByteStream::Initialize(void)
0x18001a835  mov     rcx, [rsp+88h+var_18]
0x18001a83a  xor     rcx, rsp; StackCookie
0x18001a83d  call    __security_check_cookie
0x18001a842  add     rsp, 80h
0x18001a849  pop     rbx
0x18001a84a  retn
```
