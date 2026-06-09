# PCLmWriter::FlateEncoderWrapper::FlateEncoderWrapper(void)

- ea: `0x18001ab14`
- end: `0x18001abb2`
- name: `??0FlateEncoderWrapper@PCLmWriter@@QEAA@XZ`
- size: `158`
- prototype: `__int64 __fastcall(PCLmWriter::FlateEncoderWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001a854`

## callees

- `0x1800015f0`
- `0x180002154`
- `0x180004110`
- `0x18000f3e0`
- `0x180011600`
- `0x18001ab14`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PCLmWriter::FlateEncoderWrapper *__fastcall PCLmWriter::FlateEncoderWrapper::FlateEncoderWrapper(
        PCLmWriter::FlateEncoderWrapper *this)
{
  __int64 v2; // rcx
  PCLmWriter::FlateEncoderWrapper *v3; // rax
  _BYTE v5[32]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+40h] [rbp-58h] BYREF

  v2 = 88;
  v3 = this;
  do
  {
    *(_BYTE *)v3 = 0;
    v3 = (PCLmWriter::FlateEncoderWrapper *)((char *)v3 + 1);
    --v2;
  }
  while ( v2 );
  if ( (unsigned int)deflateInit_(this, 0xFFFFFFFFLL, "1.3.1") )
  {
    std::string::string(v5, "Error zlib::deflateInit failed!");
    PCLmWriter::Exception::Exception((std::exception *)pExceptionObject, (__int64)v5, 0);
    throw (PCLmWriter::Exception *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18001ab14  push    rbx
0x18001ab16  sub     rsp, 90h
0x18001ab1d  mov     rax, cs:__security_cookie
0x18001ab24  xor     rax, rsp
0x18001ab27  mov     [rsp+98h+var_18], rax
0x18001ab2f  mov     rbx, rcx
0x18001ab32  mov     r9d, 58h ; 'X'
0x18001ab38  mov     ecx, r9d
0x18001ab3b  mov     rax, rbx
0x18001ab3e  mov     byte ptr [rax], 0
0x18001ab41  inc     rax
0x18001ab44  sub     rcx, 1
0x18001ab48  jnz     short loc_18001AB3E
0x18001ab4a  lea     r8, a131; "1.3.1"
0x18001ab51  or      edx, 0FFFFFFFFh
0x18001ab54  mov     rcx, rbx
0x18001ab57  call    deflateInit_
0x18001ab5c  test    eax, eax
0x18001ab5e  jnz     short loc_18001AB7C
0x18001ab60  mov     rax, rbx
0x18001ab63  mov     rcx, [rsp+98h+var_18]
0x18001ab6b  xor     rcx, rsp; StackCookie
0x18001ab6e  call    __security_check_cookie
0x18001ab73  add     rsp, 90h
0x18001ab7a  pop     rbx
0x18001ab7b  retn
0x18001ab7c  lea     rdx, aErrorZlibDefla; "Error zlib::deflateInit failed!"
0x18001ab83  lea     rcx, [rsp+98h+var_78]
0x18001ab88  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001ab8d  nop
0x18001ab8e  xor     r8d, r8d
0x18001ab91  lea     rdx, [rsp+98h+var_78]
0x18001ab96  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18001ab9b  call    ??0Exception@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z; PCLmWriter::Exception::Exception(std::string const &,long)
0x18001aba0  lea     rdx, _TI2?AVException@PCLmWriter@@; pThrowInfo
0x18001aba7  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18001abac  call    _CxxThrowException_0
```
