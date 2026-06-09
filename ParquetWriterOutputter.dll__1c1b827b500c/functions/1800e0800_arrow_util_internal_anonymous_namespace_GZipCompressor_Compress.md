# arrow::util::internal::_anonymous_namespace_::GZipCompressor::Compress

- ea: `0x1800e0800`
- end: `0x1800e0982`
- name: `arrow::util::internal::_anonymous_namespace_::GZipCompressor::Compress`
- size: `386`
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
- `0x1800e0800`
- `0x1800e19a0`
- `0x1802a0ad0`
- `0x180358070`

## string_xrefs

- `0x1800e08f2`: `c:\source\src\submodules\apache\arrow\cpp\src\arrow\util\compression_zlib.cc`
- `0x1800e0878`: `zlib compress failed: `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::util::internal::_anonymous_namespace_::GZipCompressor::Compress(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  char v9; // r14
  _QWORD *v10; // rcx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 v15; // rax
  arrow::Status::State *v17[2]; // [rsp+30h] [rbp-28h] BYREF

  v9 = 0;
  v10 = (_QWORD *)(a1 + 8);
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
  v13 = deflate(v10, 0);
  if ( v13 == -2 )
  {
    arrow::util::internal::_anonymous_namespace_::ZlibErrorPrefix(v17, "zlib compress failed: ", *(_QWORD *)(a1 + 40));
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v17);
    if ( v17[1] )
      arrow::Status::State::`scalar deleting destructor'(v17[1], 1u);
  }
  else if ( v13 )
  {
    if ( v13 != -5 )
    {
      v14 = arrow::util::ArrowLog::ArrowLog(
              v17,
              "c:\\source\\src\\submodules\\apache\\arrow\\cpp\\src\\arrow\\util\\compression_zlib.cc",
              218,
              3);
      v9 = 2;
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14) )
      {
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        std::operator<<<std::char_traits<char>>(v15, " Check failed: (ret) == ((-5)) ");
      }
    }
    if ( (v9 & 2) != 0 )
      arrow::util::ArrowLog::~ArrowLog((arrow::util::ArrowLog *)v17);
    *(_QWORD *)(a2 + 8) = 0;
    *(_OWORD *)(a2 + 16) = 0;
  }
  else
  {
    v17[0] = (arrow::Status::State *)(a3 - *(unsigned int *)(a1 + 16));
    v17[1] = (arrow::Status::State *)(a5 - *(unsigned int *)(a1 + 32));
    *(_QWORD *)(a2 + 8) = 0;
    *(_OWORD *)(a2 + 16) = *(_OWORD *)v17;
  }
  return a2;
}

```

## disassembly

```asm
0x1800e0800  mov     r11, rsp
0x1800e0803  push    r14
0x1800e0805  sub     rsp, 50h
0x1800e0809  mov     qword ptr [r11-30h], 0FFFFFFFFFFFFFFFEh
0x1800e0811  mov     [r11+8], rbx
0x1800e0815  mov     [r11+10h], rbp
0x1800e0819  mov     [r11+18h], rsi
0x1800e081d  mov     [r11+20h], rdi
0x1800e0821  mov     rsi, r8
0x1800e0824  mov     rbx, rdx
0x1800e0827  mov     rdi, rcx
0x1800e082a  xor     r14d, r14d
0x1800e082d  mov     [r11-38h], r14d
0x1800e0831  add     rcx, 8
0x1800e0835  mov     [rcx], r9
0x1800e0838  mov     eax, r8d
0x1800e083b  mov     edx, 0FFFFFFFFh
0x1800e0840  cmp     r8, rdx
0x1800e0843  cmovg   eax, edx
0x1800e0846  mov     [rdi+10h], eax
0x1800e0849  mov     rax, [rsp+58h+arg_28]
0x1800e0851  mov     [rdi+18h], rax
0x1800e0855  mov     rbp, [r11+28h]
0x1800e0859  mov     eax, ebp
0x1800e085b  cmp     rbp, rdx
0x1800e085e  cmovg   eax, edx
0x1800e0861  mov     [rdi+20h], eax
0x1800e0864  xor     edx, edx
0x1800e0866  call    deflate
0x1800e086b  movsxd  rcx, eax
0x1800e086e  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x1800e0872  jnz     short loc_1800E08B4
0x1800e0874  mov     r8, [rdi+28h]
0x1800e0878  lea     rdx, aZlibCompressFa; "zlib compress failed: "
0x1800e087f  lea     rcx, [rsp+58h+var_28]
0x1800e0884  call    arrow__util__internal___anonymous_namespace___ZlibErrorPrefix
0x1800e0889  nop
0x1800e088a  lea     rdx, [rsp+58h+var_28]
0x1800e088f  mov     rcx, rbx
0x1800e0892  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e0897  nop
0x1800e0898  mov     rcx, [rsp+58h+var_28+8]; this
0x1800e089d  test    rcx, rcx
0x1800e08a0  jz      loc_1800E0964
0x1800e08a6  lea     edx, [r14+1]; unsigned int
0x1800e08aa  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e08af  jmp     loc_1800E0964
0x1800e08b4  test    eax, eax
0x1800e08b6  jnz     short loc_1800E08E0
0x1800e08b8  mov     eax, [rdi+10h]
0x1800e08bb  sub     rsi, rax
0x1800e08be  mov     [rsp+58h+var_28], rsi
0x1800e08c3  mov     eax, [rdi+20h]
0x1800e08c6  sub     rbp, rax
0x1800e08c9  mov     [rsp+58h+var_28+8], rbp
0x1800e08ce  mov     [rbx+8], r14
0x1800e08d2  movups  xmm0, xmmword ptr [rsp+58h+var_28]
0x1800e08d7  movups  xmmword ptr [rbx+10h], xmm0
0x1800e08db  jmp     loc_1800E0964
0x1800e08e0  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x1800e08e4  jz      short loc_1800E0945
0x1800e08e6  mov     r9d, 3
0x1800e08ec  mov     r8d, 0DAh
0x1800e08f2  lea     rdx, aCSourceSrcSubm_7; "c:\\source\\src\\submodules\\apache\\ar"...
0x1800e08f9  lea     rcx, [rsp+58h+var_28]
0x1800e08fe  call    ??0ArrowLog@util@arrow@@QEAA@PEBDHW4ArrowLogLevel@12@@Z; arrow::util::ArrowLog::ArrowLog(char const *,int,arrow::util::ArrowLogLevel)
0x1800e0903  mov     rdi, rax
0x1800e0906  mov     r14d, 2
0x1800e090c  mov     [rsp+58h+var_38], r14d
0x1800e0911  mov     rcx, [rax]
0x1800e0914  mov     rax, [rcx+8]
0x1800e0918  mov     rcx, rdi
0x1800e091b  call    cs:__guard_dispatch_icall_fptr
0x1800e0921  test    al, al
0x1800e0923  jz      short loc_1800E0945
0x1800e0925  mov     rax, [rdi]
0x1800e0928  mov     rcx, rdi
0x1800e092b  mov     rax, [rax+10h]
0x1800e092f  call    cs:__guard_dispatch_icall_fptr
0x1800e0935  mov     rcx, rax
0x1800e0938  lea     rdx, aCheckFailedRet; " Check failed: (ret) == ((-5)) "
0x1800e093f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800e0944  nop
0x1800e0945  test    r14b, 2
0x1800e0949  jz      short loc_1800E0955
0x1800e094b  lea     rcx, [rsp+58h+var_28]; this
0x1800e0950  call    ??1ArrowLog@util@arrow@@UEAA@XZ; arrow::util::ArrowLog::~ArrowLog(void)
0x1800e0955  xorps   xmm0, xmm0
0x1800e0958  mov     qword ptr [rbx+8], 0
0x1800e0960  movups  xmmword ptr [rbx+10h], xmm0
0x1800e0964  mov     rax, rbx
0x1800e0967  mov     rbx, [rsp+58h+arg_0]
0x1800e096c  mov     rbp, [rsp+58h+arg_8]
0x1800e0971  mov     rsi, [rsp+58h+arg_10]
0x1800e0976  mov     rdi, [rsp+58h+arg_18]
0x1800e097b  add     rsp, 50h
0x1800e097f  pop     r14
0x1800e0981  retn
```
