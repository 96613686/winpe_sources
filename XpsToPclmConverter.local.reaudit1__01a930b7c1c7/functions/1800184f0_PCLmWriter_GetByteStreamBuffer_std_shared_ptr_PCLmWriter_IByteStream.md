# PCLmWriter::GetByteStreamBuffer(std::shared_ptr<PCLmWriter::IByteStream>)

- ea: `0x1800184f0`
- end: `0x1800185a7`
- name: `?GetByteStreamBuffer@PCLmWriter@@YAPEAEV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800199e0`
- `0x18001a854`

## callees

- `0x1800101cc`
- `0x1800184f0`
- `0x18001cc44`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PCLmWriter::GetByteStreamBuffer(_QWORD *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  std::_Ref_count_base *v4; // rdi
  __int64 v5; // rsi
  std::_Ref_count_base *v6; // rcx

  v2 = _RTDynamicCast_0(
         *a1,
         0,
         &PCLmWriter::IByteStream `RTTI Type Descriptor',
         &PCLmWriter::IStreamBufferProvider `RTTI Type Descriptor',
         0);
  if ( v2 )
  {
    v3 = a1[1];
    if ( v3 )
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
    v4 = (std::_Ref_count_base *)a1[1];
  }
  else
  {
    v4 = (std::_Ref_count_base *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v2 = 0;
  }
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  v6 = (std::_Ref_count_base *)a1[1];
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  return v5;
}

```

## disassembly

```asm
0x1800184f0  mov     rax, rsp
0x1800184f3  mov     [rax+10h], rbx
0x1800184f7  mov     [rax+18h], rsi
0x1800184fb  mov     [rax+8], rcx
0x1800184ff  push    rdi
0x180018500  sub     rsp, 40h
0x180018504  mov     rbx, rcx
0x180018507  mov     dword ptr [rax-28h], 0
0x18001850e  lea     r9, ??_R0?AVIStreamBufferProvider@PCLmWriter@@@8; PCLmWriter::IStreamBufferProvider `RTTI Type Descriptor'
0x180018515  lea     r8, ??_R0?AVIByteStream@PCLmWriter@@@8; PCLmWriter::IByteStream `RTTI Type Descriptor'
0x18001851c  xor     edx, edx
0x18001851e  mov     rcx, [rcx]
0x180018521  call    __RTDynamicCast_0
0x180018526  mov     rdx, rax
0x180018529  test    rax, rax
0x18001852c  jz      short loc_18001854B
0x18001852e  mov     rcx, [rbx+8]
0x180018532  test    rcx, rcx
0x180018535  jz      short loc_18001853B
0x180018537  lock inc dword ptr [rcx+8]
0x18001853b  mov     qword ptr [rsp+48h+var_18], rax
0x180018540  mov     rdi, [rbx+8]
0x180018544  mov     qword ptr [rsp+48h+var_18+8], rdi
0x180018549  jmp     short loc_180018566
0x18001854b  xorps   xmm0, xmm0
0x18001854e  xorps   xmm1, xmm1
0x180018551  movdqu  [rsp+48h+var_18], xmm1
0x180018557  psrldq  xmm0, 8
0x18001855c  movq    rdi, xmm0
0x180018561  movq    rdx, xmm1
0x180018566  mov     rax, [rdx]
0x180018569  mov     rcx, rdx
0x18001856c  mov     rax, [rax+8]
0x180018570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018575  mov     rsi, rax
0x180018578  test    rdi, rdi
0x18001857b  jz      short loc_180018586
0x18001857d  mov     rcx, rdi; this
0x180018580  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018585  nop
0x180018586  mov     rcx, [rbx+8]; this
0x18001858a  test    rcx, rcx
0x18001858d  jz      short loc_180018594
0x18001858f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018594  mov     rax, rsi
0x180018597  mov     rbx, [rsp+48h+arg_8]
0x18001859c  mov     rsi, [rsp+48h+arg_10]
0x1800185a1  add     rsp, 40h
0x1800185a5  pop     rdi
0x1800185a6  retn
```
