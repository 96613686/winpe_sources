# arrow::util::internal::_anonymous_namespace_::GZipDecompressor::Decompress

- ea: `0x1800e0c20`
- end: `0x1800e0dfb`
- name: `arrow::util::internal::_anonymous_namespace_::GZipDecompressor::Decompress`
- size: `475`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18001b360`
- `0x18001f8c0`
- `0x180059010`
- `0x1800dc8f0`
- `0x1800dca00`
- `0x1800e0c20`
- `0x1800e19a0`
- `0x1802a2560`
- `0x180358070`

## string_xrefs

- `0x1800e0d08`: `c:\source\src\submodules\apache\arrow\cpp\src\arrow\util\compression_zlib.cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall arrow::util::internal::_anonymous_namespace_::GZipDecompressor::Decompress(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int8 *a4,
        __int64 a5,
        __int64 a6)
{
  char v9; // r15
  unsigned __int8 **v10; // rcx
  int v11; // eax
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rsi
  __int64 v15; // rax
  arrow::Status::State *v17[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v18; // [rsp+40h] [rbp-28h]

  v9 = 0;
  v10 = (unsigned __int8 **)(a1 + 8);
  *v10 = a4;
  v11 = a3;
  if ( a3 > 0xFFFFFFFFLL )
    v11 = -1;
  *(_DWORD *)(a1 + 16) = v11;
  *(_QWORD *)(a1 + 24) = a6;
  v12 = a5;
  if ( a5 > 0xFFFFFFFFLL )
    v12 = -1;
  *(_DWORD *)(a1 + 32) = v12;
  v13 = inflate(v10, 2);
  if ( v13 + 4 <= 2 )
  {
    arrow::util::internal::_anonymous_namespace_::ZlibErrorPrefix(v17, "zlib inflate failed: ", *(_QWORD *)(a1 + 40));
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v17);
LABEL_17:
    if ( v17[1] )
      arrow::Status::State::`scalar deleting destructor'(v17[1], 1u);
    return a2;
  }
  if ( v13 == 2 )
  {
    arrow::util::internal::_anonymous_namespace_::ZlibErrorPrefix(
      v17,
      "zlib inflate failed (need preset dictionary): ",
      *(_QWORD *)(a1 + 40));
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v17);
    goto LABEL_17;
  }
  *(_BYTE *)(a1 + 101) = v13 == 1;
  if ( v13 == -5 )
  {
    LOBYTE(v18) = 1;
    *(_QWORD *)(a2 + 8) = 0;
    *(_OWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 32) = v18;
  }
  else
  {
    if ( v13 > 1 )
    {
      v14 = arrow::util::ArrowLog::ArrowLog(
              v17,
              "c:\\source\\src\\submodules\\apache\\arrow\\cpp\\src\\arrow\\util\\compression_zlib.cc",
              145,
              3);
      v9 = 2;
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14) )
      {
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        std::operator<<<std::char_traits<char>>(v15, " Check failed: ret == Z_OK || ret == Z_STREAM_END ");
      }
    }
    if ( (v9 & 2) != 0 )
      arrow::util::ArrowLog::~ArrowLog((arrow::util::ArrowLog *)v17);
    v17[0] = (arrow::Status::State *)(a3 - *(unsigned int *)(a1 + 16));
    v17[1] = (arrow::Status::State *)(a5 - *(unsigned int *)(a1 + 32));
    LOBYTE(v18) = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_OWORD *)(a2 + 16) = *(_OWORD *)v17;
    *(_QWORD *)(a2 + 32) = v18;
  }
  return a2;
}

```

## disassembly

```asm
0x1800e0c20  mov     r11, rsp
0x1800e0c23  push    rdi
0x1800e0c24  push    r14
0x1800e0c26  push    r15
0x1800e0c28  sub     rsp, 50h
0x1800e0c2c  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x1800e0c34  mov     [r11+8], rbx
0x1800e0c38  mov     [r11+10h], rbp
0x1800e0c3c  mov     [r11+18h], rsi
0x1800e0c40  mov     rbp, r8
0x1800e0c43  mov     rbx, rdx
0x1800e0c46  mov     rdi, rcx
0x1800e0c49  xor     r15d, r15d
0x1800e0c4c  mov     [r11-48h], r15d
0x1800e0c50  add     rcx, 8
0x1800e0c54  mov     [rcx], r9
0x1800e0c57  mov     eax, r8d
0x1800e0c5a  mov     edx, 0FFFFFFFFh
0x1800e0c5f  cmp     r8, rdx
0x1800e0c62  cmovg   eax, edx
0x1800e0c65  mov     [rdi+10h], eax
0x1800e0c68  mov     rax, [rsp+68h+arg_28]
0x1800e0c70  mov     [rdi+18h], rax
0x1800e0c74  mov     r14, [r11+28h]
0x1800e0c78  mov     eax, r14d
0x1800e0c7b  cmp     r14, rdx
0x1800e0c7e  cmovg   eax, edx
0x1800e0c81  mov     [rdi+20h], eax
0x1800e0c84  lea     edx, [r15+2]
0x1800e0c88  call    inflate
0x1800e0c8d  mov     edx, eax
0x1800e0c8f  lea     ecx, [rax+4]
0x1800e0c92  cmp     ecx, 2
0x1800e0c95  jbe     loc_1800E0DA4
0x1800e0c9b  cmp     eax, 2
0x1800e0c9e  jnz     short loc_1800E0CC9
0x1800e0ca0  mov     r8, [rdi+28h]
0x1800e0ca4  lea     rdx, aZlibInflateFai; "zlib inflate failed (need preset dictio"...
0x1800e0cab  lea     rcx, [rsp+68h+var_38]
0x1800e0cb0  call    arrow__util__internal___anonymous_namespace___ZlibErrorPrefix
0x1800e0cb5  nop
0x1800e0cb6  lea     rdx, [rsp+68h+var_38]
0x1800e0cbb  mov     rcx, rbx
0x1800e0cbe  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e0cc3  nop
0x1800e0cc4  jmp     loc_1800E0DC8
0x1800e0cc9  cmp     edx, 1
0x1800e0ccc  setz    al
0x1800e0ccf  mov     [rdi+65h], al
0x1800e0cd2  cmp     edx, 0FFFFFFFBh
0x1800e0cd5  jnz     short loc_1800E0CF7
0x1800e0cd7  xorps   xmm0, xmm0
0x1800e0cda  mov     byte ptr [rsp+68h+var_28], 1
0x1800e0cdf  mov     [rbx+8], r15
0x1800e0ce3  movups  xmmword ptr [rbx+10h], xmm0
0x1800e0ce7  movsd   xmm0, [rsp+68h+var_28]
0x1800e0ced  movsd   qword ptr [rbx+20h], xmm0
0x1800e0cf2  jmp     loc_1800E0DDC
0x1800e0cf7  cmp     edx, 1
0x1800e0cfa  jbe     short loc_1800E0D5B
0x1800e0cfc  mov     r9d, 3
0x1800e0d02  mov     r8d, 91h
0x1800e0d08  lea     rdx, aCSourceSrcSubm_7; "c:\\source\\src\\submodules\\apache\\ar"...
0x1800e0d0f  lea     rcx, [rsp+68h+var_38]
0x1800e0d14  call    ??0ArrowLog@util@arrow@@QEAA@PEBDHW4ArrowLogLevel@12@@Z; arrow::util::ArrowLog::ArrowLog(char const *,int,arrow::util::ArrowLogLevel)
0x1800e0d19  mov     rsi, rax
0x1800e0d1c  mov     r15d, 2
0x1800e0d22  mov     [rsp+68h+var_48], r15d
0x1800e0d27  mov     rcx, [rax]
0x1800e0d2a  mov     rax, [rcx+8]
0x1800e0d2e  mov     rcx, rsi
0x1800e0d31  call    cs:__guard_dispatch_icall_fptr
0x1800e0d37  test    al, al
0x1800e0d39  jz      short loc_1800E0D5B
0x1800e0d3b  mov     rax, [rsi]
0x1800e0d3e  mov     rcx, rsi
0x1800e0d41  mov     rax, [rax+10h]
0x1800e0d45  call    cs:__guard_dispatch_icall_fptr
0x1800e0d4b  mov     rcx, rax
0x1800e0d4e  lea     rdx, aCheckFailedRet_0; " Check failed: ret == Z_OK || ret == Z_"...
0x1800e0d55  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800e0d5a  nop
0x1800e0d5b  test    r15b, 2
0x1800e0d5f  jz      short loc_1800E0D6B
0x1800e0d61  lea     rcx, [rsp+68h+var_38]; this
0x1800e0d66  call    ??1ArrowLog@util@arrow@@UEAA@XZ; arrow::util::ArrowLog::~ArrowLog(void)
0x1800e0d6b  mov     eax, [rdi+10h]
0x1800e0d6e  sub     rbp, rax
0x1800e0d71  mov     [rsp+68h+var_38], rbp
0x1800e0d76  mov     eax, [rdi+20h]
0x1800e0d79  sub     r14, rax
0x1800e0d7c  mov     [rsp+68h+var_38+8], r14
0x1800e0d81  mov     byte ptr [rsp+68h+var_28], 0
0x1800e0d86  mov     qword ptr [rbx+8], 0
0x1800e0d8e  movups  xmm0, xmmword ptr [rsp+68h+var_38]
0x1800e0d93  movups  xmmword ptr [rbx+10h], xmm0
0x1800e0d97  movsd   xmm1, [rsp+68h+var_28]
0x1800e0d9d  movsd   qword ptr [rbx+20h], xmm1
0x1800e0da2  jmp     short loc_1800E0DDC
0x1800e0da4  mov     r8, [rdi+28h]
0x1800e0da8  lea     rdx, aZlibInflateFai_0; "zlib inflate failed: "
0x1800e0daf  lea     rcx, [rsp+68h+var_38]
0x1800e0db4  call    arrow__util__internal___anonymous_namespace___ZlibErrorPrefix
0x1800e0db9  nop
0x1800e0dba  lea     rdx, [rsp+68h+var_38]
0x1800e0dbf  mov     rcx, rbx
0x1800e0dc2  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e0dc7  nop
0x1800e0dc8  mov     rcx, [rsp+68h+var_38+8]; this
0x1800e0dcd  test    rcx, rcx
0x1800e0dd0  jz      short loc_1800E0DDC
0x1800e0dd2  mov     edx, 1; unsigned int
0x1800e0dd7  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e0ddc  mov     rax, rbx
0x1800e0ddf  mov     rbx, [rsp+68h+arg_0]
0x1800e0de4  mov     rbp, [rsp+68h+arg_8]
0x1800e0de9  mov     rsi, [rsp+68h+arg_10]
0x1800e0df1  add     rsp, 50h
0x1800e0df5  pop     r15
0x1800e0df7  pop     r14
0x1800e0df9  pop     rdi
0x1800e0dfa  retn
```
