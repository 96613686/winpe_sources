# arrow::util::internal::_anonymous_namespace_::GZipCompressor::Flush

- ea: `0x1800e0f30`
- end: `0x1800e1080`
- name: `arrow::util::internal::_anonymous_namespace_::GZipCompressor::Flush`
- size: `336`
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
- `0x1800e0f30`
- `0x1800e19a0`
- `0x1802a0ad0`
- `0x180358070`

## string_xrefs

- `0x1800e0fe7`: `c:\source\src\submodules\apache\arrow\cpp\src\arrow\util\compression_zlib.cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::util::internal::_anonymous_namespace_::GZipCompressor::Flush(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char v7; // bp
  int v8; // eax
  int v9; // eax
  arrow::Status::State *v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rax
  arrow::Status::State *v14[2]; // [rsp+30h] [rbp-28h] BYREF

  v7 = 0;
  *(_DWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = a4;
  v8 = a3;
  if ( a3 > 0xFFFFFFFFLL )
    v8 = -1;
  *(_DWORD *)(a1 + 32) = v8;
  v9 = deflate(a1 + 8, 2);
  if ( v9 == -2 )
  {
    arrow::util::internal::_anonymous_namespace_::ZlibErrorPrefix(v14, "zlib flush failed: ", *(_QWORD *)(a1 + 40));
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v14);
    if ( v14[1] )
      arrow::Status::State::`scalar deleting destructor'(v14[1], 1u);
  }
  else
  {
    if ( v9 )
    {
      if ( v9 != -5 )
      {
        v11 = arrow::util::ArrowLog::ArrowLog(
                v14,
                "c:\\source\\src\\submodules\\apache\\arrow\\cpp\\src\\arrow\\util\\compression_zlib.cc",
                242,
                3);
        v7 = 2;
        if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11) )
        {
          v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
          std::operator<<<std::char_traits<char>>(v12, " Check failed: (ret) == ((-5)) ");
        }
      }
      if ( (v7 & 2) != 0 )
        arrow::util::ArrowLog::~ArrowLog((arrow::util::ArrowLog *)v14);
      v10 = 0;
    }
    else
    {
      v10 = (arrow::Status::State *)(a3 - *(unsigned int *)(a1 + 32));
    }
    v14[0] = v10;
    LOBYTE(v14[1]) = v10 == 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_OWORD *)(a2 + 16) = *(_OWORD *)v14;
  }
  return a2;
}

```

## disassembly

```asm
0x1800e0f30  push    rdi
0x1800e0f32  sub     rsp, 50h
0x1800e0f36  mov     [rsp+58h+var_30], 0FFFFFFFFFFFFFFFEh
0x1800e0f3f  mov     [rsp+58h+arg_0], rbx
0x1800e0f44  mov     [rsp+58h+arg_8], rbp
0x1800e0f49  mov     [rsp+58h+arg_10], rsi
0x1800e0f4e  mov     rbx, r8
0x1800e0f51  mov     rdi, rdx
0x1800e0f54  mov     rsi, rcx
0x1800e0f57  xor     ebp, ebp
0x1800e0f59  mov     [rsp+58h+var_38], ebp
0x1800e0f5d  mov     [rcx+10h], ebp
0x1800e0f60  mov     [rcx+18h], r9
0x1800e0f64  mov     eax, r8d
0x1800e0f67  mov     ecx, 0FFFFFFFFh
0x1800e0f6c  cmp     r8, rcx
0x1800e0f6f  cmovg   eax, ecx
0x1800e0f72  mov     [rsi+20h], eax
0x1800e0f75  lea     rcx, [rsi+8]
0x1800e0f79  lea     edx, [rbp+2]
0x1800e0f7c  call    deflate
0x1800e0f81  movsxd  rcx, eax
0x1800e0f84  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x1800e0f88  jnz     short loc_1800E0FC9
0x1800e0f8a  mov     r8, [rsi+28h]
0x1800e0f8e  lea     rdx, aZlibFlushFaile; "zlib flush failed: "
0x1800e0f95  lea     rcx, [rsp+58h+var_28]
0x1800e0f9a  call    arrow__util__internal___anonymous_namespace___ZlibErrorPrefix
0x1800e0f9f  nop
0x1800e0fa0  lea     rdx, [rsp+58h+var_28]
0x1800e0fa5  mov     rcx, rdi
0x1800e0fa8  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e0fad  nop
0x1800e0fae  mov     rcx, [rsp+58h+var_28+8]; this
0x1800e0fb3  test    rcx, rcx
0x1800e0fb6  jz      loc_1800E1068
0x1800e0fbc  lea     edx, [rbp+1]; unsigned int
0x1800e0fbf  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e0fc4  jmp     loc_1800E1068
0x1800e0fc9  test    eax, eax
0x1800e0fcb  jnz     short loc_1800E0FD5
0x1800e0fcd  mov     eax, [rsi+20h]
0x1800e0fd0  sub     rbx, rax
0x1800e0fd3  jmp     short loc_1800E104A
0x1800e0fd5  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x1800e0fd9  jz      short loc_1800E1038
0x1800e0fdb  mov     r9d, 3
0x1800e0fe1  mov     r8d, 0F2h
0x1800e0fe7  lea     rdx, aCSourceSrcSubm_7; "c:\\source\\src\\submodules\\apache\\ar"...
0x1800e0fee  lea     rcx, [rsp+58h+var_28]
0x1800e0ff3  call    ??0ArrowLog@util@arrow@@QEAA@PEBDHW4ArrowLogLevel@12@@Z; arrow::util::ArrowLog::ArrowLog(char const *,int,arrow::util::ArrowLogLevel)
0x1800e0ff8  mov     rbx, rax
0x1800e0ffb  mov     ebp, 2
0x1800e1000  mov     [rsp+58h+var_38], ebp
0x1800e1004  mov     rcx, [rax]
0x1800e1007  mov     rax, [rcx+8]
0x1800e100b  mov     rcx, rbx
0x1800e100e  call    cs:__guard_dispatch_icall_fptr
0x1800e1014  test    al, al
0x1800e1016  jz      short loc_1800E1038
0x1800e1018  mov     rax, [rbx]
0x1800e101b  mov     rcx, rbx
0x1800e101e  mov     rax, [rax+10h]
0x1800e1022  call    cs:__guard_dispatch_icall_fptr
0x1800e1028  mov     rcx, rax
0x1800e102b  lea     rdx, aCheckFailedRet; " Check failed: (ret) == ((-5)) "
0x1800e1032  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800e1037  nop
0x1800e1038  test    bpl, 2
0x1800e103c  jz      short loc_1800E1048
0x1800e103e  lea     rcx, [rsp+58h+var_28]; this
0x1800e1043  call    ??1ArrowLog@util@arrow@@UEAA@XZ; arrow::util::ArrowLog::~ArrowLog(void)
0x1800e1048  xor     ebx, ebx
0x1800e104a  mov     [rsp+58h+var_28], rbx
0x1800e104f  test    rbx, rbx
0x1800e1052  setz    byte ptr [rsp+58h+var_28+8]
0x1800e1057  mov     qword ptr [rdi+8], 0
0x1800e105f  movups  xmm0, xmmword ptr [rsp+58h+var_28]
0x1800e1064  movups  xmmword ptr [rdi+10h], xmm0
0x1800e1068  mov     rax, rdi
0x1800e106b  mov     rbx, [rsp+58h+arg_0]
0x1800e1070  mov     rbp, [rsp+58h+arg_8]
0x1800e1075  mov     rsi, [rsp+58h+arg_10]
0x1800e107a  add     rsp, 50h
0x1800e107e  pop     rdi
0x1800e107f  retn
```
