# apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TMemoryBuffer>::readMessageBegin(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,apache::thrift::protocol::TMessageType &,int &)

- ea: `0x18003e4a0`
- end: `0x18003e5ba`
- name: `?readMessageBegin@?$TCompactProtocolT@VTMemoryBuffer@transport@thrift@apache@@@protocol@thrift@apache@@QEAAIAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAW4TMessageType@234@AEAH@Z`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003e6e0`

## callees

- `0x180035cd0`
- `0x180036df0`
- `0x18003d910`
- `0x18003da90`
- `0x18003e4a0`
- `0x18003e820`
- `0x18030c3f0`
- `0x18032b080`

## string_xrefs

- `0x18003e582`: `Bad protocol identifier`
- `0x18003e54a`: `Bad protocol version`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TMemoryBuffer>::readMessageBegin(
        __int64 a1,
        __int64 a2,
        int *a3,
        __int64 a4)
{
  int Byte; // ebx
  int v9; // ebx
  int v10; // ebx
  _BYTE v12[8]; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v13; // [rsp+28h] [rbp-A0h]
  _BYTE v14[32]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-78h] BYREF

  v13 = -2;
  Byte = apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TMemoryBuffer>::readByte(a1, v12);
  if ( v12[0] != 0x82 )
  {
    std::string::string(v14, "Bad protocol identifier");
    apache::thrift::protocol::TProtocolException::TProtocolException(pExceptionObject, 4, v14);
    throw (apache::thrift::protocol::TProtocolException *)pExceptionObject;
  }
  v9 = apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TMemoryBuffer>::readByte(a1, v12) + Byte;
  if ( (v12[0] & 0x1F) != 1 )
  {
    std::string::string(v14, "Bad protocol version");
    apache::thrift::protocol::TProtocolException::TProtocolException(pExceptionObject, 4, v14);
    throw (apache::thrift::protocol::TProtocolException *)pExceptionObject;
  }
  *a3 = v12[0] >> 5;
  v10 = apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TMemoryBuffer>::readVarint32(a1, a4) + v9;
  return v10
       + (unsigned int)apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TMemoryBuffer>::readString(
                         a1,
                         a2);
}

```

## disassembly

```asm
0x18003e4a0  push    rbx
0x18003e4a2  push    rbp
0x18003e4a3  push    rsi
0x18003e4a4  push    rdi
0x18003e4a5  push    r14
0x18003e4a7  sub     rsp, 0A0h
0x18003e4ae  mov     [rsp+0C8h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18003e4b7  mov     rax, cs:__security_cookie
0x18003e4be  xor     rax, rsp
0x18003e4c1  mov     [rsp+0C8h+var_38], rax
0x18003e4c9  mov     rbp, r9
0x18003e4cc  mov     r14, r8
0x18003e4cf  mov     rsi, rdx
0x18003e4d2  mov     rdi, rcx
0x18003e4d5  lea     rdx, [rsp+0C8h+var_A8]
0x18003e4da  call    ?readByte@?$TCompactProtocolT@VTMemoryBuffer@transport@thrift@apache@@@protocol@thrift@apache@@QEAAIAEAC@Z; apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TMemoryBuffer>::readByte(signed char &)
0x18003e4df  mov     ebx, eax
0x18003e4e1  cmp     [rsp+0C8h+var_A8], 82h
0x18003e4e6  jnz     loc_18003E582
0x18003e4ec  lea     rdx, [rsp+0C8h+var_A8]
0x18003e4f1  mov     rcx, rdi
0x18003e4f4  call    ?readByte@?$TCompactProtocolT@VTMemoryBuffer@transport@thrift@apache@@@protocol@thrift@apache@@QEAAIAEAC@Z; apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TMemoryBuffer>::readByte(signed char &)
0x18003e4f9  add     ebx, eax
0x18003e4fb  movzx   ecx, [rsp+0C8h+var_A8]
0x18003e500  movzx   eax, cl
0x18003e503  and     al, 1Fh
0x18003e505  cmp     al, 1
0x18003e507  jnz     short loc_18003E54A
0x18003e509  movzx   eax, cl
0x18003e50c  shr     eax, 5
0x18003e50f  mov     [r14], eax
0x18003e512  mov     rdx, rbp
0x18003e515  mov     rcx, rdi
0x18003e518  call    ?readVarint32@?$TCompactProtocolT@VTMemoryBuffer@transport@thrift@apache@@@protocol@thrift@apache@@IEAAIAEAH@Z; apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TMemoryBuffer>::readVarint32(int &)
0x18003e51d  add     ebx, eax
0x18003e51f  mov     rdx, rsi
0x18003e522  mov     rcx, rdi
0x18003e525  call    ?readString@?$TCompactProtocolT@VTMemoryBuffer@transport@thrift@apache@@@protocol@thrift@apache@@QEAAIAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; apache::thrift::protocol::TCompactProtocolT<apache::thrift::transport::TMemoryBuffer>::readString(std::string &)
0x18003e52a  add     eax, ebx
0x18003e52c  mov     rcx, [rsp+0C8h+var_38]
0x18003e534  xor     rcx, rsp; StackCookie
0x18003e537  call    __security_check_cookie
0x18003e53c  add     rsp, 0A0h
0x18003e543  pop     r14
0x18003e545  pop     rdi
0x18003e546  pop     rsi
0x18003e547  pop     rbp
0x18003e548  pop     rbx
0x18003e549  retn
0x18003e54a  lea     rdx, aBadProtocolVer; "Bad protocol version"
0x18003e551  lea     rcx, [rsp+0C8h+var_98]
0x18003e556  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003e55b  nop
0x18003e55c  lea     r8, [rsp+0C8h+var_98]
0x18003e561  mov     edx, 4
0x18003e566  lea     rcx, [rsp+0C8h+pExceptionObject]
0x18003e56b  call    ??0TProtocolException@protocol@thrift@apache@@QEAA@W4TProtocolExceptionType@0123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; apache::thrift::protocol::TProtocolException::TProtocolException(apache::thrift::protocol::TProtocolException::TProtocolExceptionType,std::string const &)
0x18003e570  lea     rdx, _TI3?AVTProtocolException@protocol@thrift@apache@@; pThrowInfo
0x18003e577  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18003e57c  call    _CxxThrowException
0x18003e582  lea     rdx, aBadProtocolIde; "Bad protocol identifier"
0x18003e589  lea     rcx, [rsp+0C8h+var_98]
0x18003e58e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003e593  nop
0x18003e594  lea     r8, [rsp+0C8h+var_98]
0x18003e599  mov     edx, 4
0x18003e59e  lea     rcx, [rsp+0C8h+pExceptionObject]
0x18003e5a3  call    ??0TProtocolException@protocol@thrift@apache@@QEAA@W4TProtocolExceptionType@0123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; apache::thrift::protocol::TProtocolException::TProtocolException(apache::thrift::protocol::TProtocolException::TProtocolExceptionType,std::string const &)
0x18003e5a8  lea     rdx, _TI3?AVTProtocolException@protocol@thrift@apache@@; pThrowInfo
0x18003e5af  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18003e5b4  call    _CxxThrowException
```
