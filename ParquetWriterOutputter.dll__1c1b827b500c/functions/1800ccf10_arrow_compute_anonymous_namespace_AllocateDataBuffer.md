# arrow::compute::_anonymous_namespace_::AllocateDataBuffer

- ea: `0x1800ccf10`
- end: `0x1800cd1a2`
- name: `arrow::compute::_anonymous_namespace_::AllocateDataBuffer`
- size: `658`
- prototype: `__int64 __fastcall(arrow::Status *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800d0c70`

## callees

- `0x18001b360`
- `0x18001f8c0`
- `0x18009a530`
- `0x1800ccf10`
- `0x1800dc8f0`
- `0x1800dca00`
- `0x180127580`
- `0x180127670`
- `0x18030c3f0`
- `0x180358070`

## string_xrefs

- `0x1800cd029`: `c:\source\src\submodules\apache\arrow\cpp\src\arrow\compute\exec.cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
arrow::Status *__fastcall arrow::compute::_anonymous_namespace_::AllocateDataBuffer(
        arrow::Status *this,
        __int64 a2,
        __int64 a3,
        int a4)
{
  __int64 v4; // rbp
  char v8; // si
  const struct arrow::Status *Bitmap; // rax
  const struct arrow::Status *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  arrow::Status::State *v13; // rcx
  volatile signed __int32 *v14; // rsi
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rax
  const struct arrow::Status *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  volatile signed __int32 *v21; // rsi
  _BYTE v23[24]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v24[8]; // [rsp+50h] [rbp-88h] BYREF
  arrow::Status::State *v25; // [rsp+58h] [rbp-80h]
  volatile signed __int32 *v26; // [rsp+68h] [rbp-70h]
  _BYTE v27[8]; // [rsp+70h] [rbp-68h] BYREF
  arrow::Status::State *v28; // [rsp+78h] [rbp-60h]
  volatile signed __int32 *v29; // [rsp+88h] [rbp-50h]

  v4 = a4;
  v8 = 0;
  if ( a4 != 1 )
  {
    if ( a4 % 8 )
    {
      v15 = arrow::util::ArrowLog::ArrowLog(
              v23,
              "c:\\source\\src\\submodules\\apache\\arrow\\cpp\\src\\arrow\\compute\\exec.cc",
              65,
              3);
      v8 = 2;
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15) )
      {
        v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        std::operator<<<std::char_traits<char>>(v16, " Check failed: (bit_width % 8) == (0) ");
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15) )
      {
        v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        std::operator<<<std::char_traits<char>>(v17, "Only bit widths with multiple of 8 are currently supported");
      }
    }
    if ( (v8 & 2) != 0 )
      arrow::util::ArrowLog::~ArrowLog((arrow::util::ArrowLog *)v23);
    v18 = (const struct arrow::Status *)arrow::compute::KernelContext::Allocate(a2, v27, a3 * v4 / 8);
    *((_QWORD *)this + 1) = 0;
    if ( *((_QWORD *)v18 + 1) )
    {
      arrow::Status::CopyFrom(this, v18);
    }
    else
    {
      *((_QWORD *)this + 1) = 0;
      *((_QWORD *)v18 + 1) = 0;
      v19 = *((_QWORD *)v18 + 2);
      v20 = *((_QWORD *)v18 + 3);
      *((_QWORD *)v18 + 2) = 0;
      *((_QWORD *)v18 + 3) = 0;
      *((_QWORD *)this + 2) = v19;
      *((_QWORD *)this + 3) = v20;
    }
    v13 = v28;
    if ( v28 )
      goto LABEL_28;
    v21 = v29;
    if ( !v29 )
      return this;
    if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
    v13 = v28;
    goto LABEL_27;
  }
  Bitmap = (const struct arrow::Status *)arrow::compute::KernelContext::AllocateBitmap(a2, v24);
  v10 = Bitmap;
  *((_QWORD *)this + 1) = 0;
  if ( *((_QWORD *)Bitmap + 1) )
  {
    arrow::Status::CopyFrom(this, Bitmap);
  }
  else
  {
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)Bitmap + 1) = 0;
    v11 = *((_QWORD *)Bitmap + 2);
    v12 = *((_QWORD *)Bitmap + 3);
    *((_QWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 3) = 0;
    *((_QWORD *)this + 2) = v11;
    *((_QWORD *)this + 3) = v12;
  }
  v13 = v25;
  if ( v25 )
    goto LABEL_28;
  v14 = v26;
  if ( v26 )
  {
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
    v13 = v25;
LABEL_27:
    if ( v13 )
LABEL_28:
      arrow::Status::State::`scalar deleting destructor'(v13, 1u);
  }
  return this;
}

```

## disassembly

```asm
0x1800ccf10  push    rbx
0x1800ccf12  push    rbp
0x1800ccf13  push    rsi
0x1800ccf14  push    rdi
0x1800ccf15  push    r12
0x1800ccf17  push    r14
0x1800ccf19  push    r15
0x1800ccf1b  sub     rsp, 0A0h
0x1800ccf22  mov     [rsp+0D8h+var_B0], 0FFFFFFFFFFFFFFFEh
0x1800ccf2b  mov     rax, cs:__security_cookie
0x1800ccf32  xor     rax, rsp
0x1800ccf35  mov     [rsp+0D8h+var_48], rax
0x1800ccf3d  movsxd  rbp, r9d
0x1800ccf40  mov     r15, r8
0x1800ccf43  mov     r14, rdx
0x1800ccf46  mov     rbx, rcx
0x1800ccf49  mov     [rsp+0D8h+var_A8], rcx
0x1800ccf4e  xor     r12d, r12d
0x1800ccf51  mov     esi, r12d
0x1800ccf54  mov     [rsp+0D8h+var_B8], r12d
0x1800ccf59  cmp     ebp, 1
0x1800ccf5c  jnz     loc_1800CD007
0x1800ccf62  lea     rdx, [rsp+0D8h+var_88]
0x1800ccf67  mov     rcx, r14
0x1800ccf6a  call    ?AllocateBitmap@KernelContext@compute@arrow@@QEAA?AV?$Result@V?$shared_ptr@VResizableBuffer@arrow@@@std@@@3@_J@Z; arrow::compute::KernelContext::AllocateBitmap(__int64)
0x1800ccf6f  mov     rdx, rax; struct arrow::Status *
0x1800ccf72  mov     [rbx+8], r12
0x1800ccf76  cmp     [rax+8], r12
0x1800ccf7a  jnz     short loc_1800CCF9E
0x1800ccf7c  mov     [rbx+8], r12
0x1800ccf80  mov     [rax+8], r12
0x1800ccf84  mov     rcx, [rax+10h]
0x1800ccf88  mov     rax, [rax+18h]
0x1800ccf8c  mov     [rdx+10h], r12
0x1800ccf90  mov     [rdx+18h], r12
0x1800ccf94  mov     [rbx+10h], rcx
0x1800ccf98  mov     [rbx+18h], rax
0x1800ccf9c  jmp     short loc_1800CCFA7
0x1800ccf9e  mov     rcx, rbx; this
0x1800ccfa1  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x1800ccfa6  nop
0x1800ccfa7  mov     rcx, [rsp+0D8h+var_80]
0x1800ccfac  test    rcx, rcx
0x1800ccfaf  jnz     loc_1800CD173
0x1800ccfb5  mov     rsi, [rsp+0D8h+var_70]
0x1800ccfba  test    rsi, rsi
0x1800ccfbd  jz      loc_1800CD17D
0x1800ccfc3  mov     edi, 0FFFFFFFFh
0x1800ccfc8  mov     eax, edi
0x1800ccfca  lock xadd [rsi+8], eax
0x1800ccfcf  cmp     eax, 1
0x1800ccfd2  jnz     short loc_1800CCFFD
0x1800ccfd4  mov     rax, [rsi]
0x1800ccfd7  mov     rcx, rsi
0x1800ccfda  mov     rax, [rax]
0x1800ccfdd  call    cs:__guard_dispatch_icall_fptr
0x1800ccfe3  lock xadd [rsi+0Ch], edi
0x1800ccfe8  cmp     edi, 1
0x1800ccfeb  jnz     short loc_1800CCFFD
0x1800ccfed  mov     rax, [rsi]
0x1800ccff0  mov     rcx, rsi
0x1800ccff3  mov     rax, [rax+8]
0x1800ccff7  call    cs:__guard_dispatch_icall_fptr
0x1800ccffd  mov     rcx, [rsp+0D8h+var_80]
0x1800cd002  jmp     loc_1800CD16E
0x1800cd007  mov     eax, ebp
0x1800cd009  and     eax, 80000007h
0x1800cd00e  jge     short loc_1800CD017
0x1800cd010  dec     eax
0x1800cd012  or      eax, 0FFFFFFF8h
0x1800cd015  inc     eax
0x1800cd017  test    eax, eax
0x1800cd019  jz      loc_1800CD0AD
0x1800cd01f  mov     r9d, 3
0x1800cd025  lea     r8d, [r9+3Eh]
0x1800cd029  lea     rdx, aCSourceSrcSubm_13; "c:\\source\\src\\submodules\\apache\\ar"...
0x1800cd030  lea     rcx, [rsp+0D8h+var_A0]
0x1800cd035  call    ??0ArrowLog@util@arrow@@QEAA@PEBDHW4ArrowLogLevel@12@@Z; arrow::util::ArrowLog::ArrowLog(char const *,int,arrow::util::ArrowLogLevel)
0x1800cd03a  mov     rdi, rax
0x1800cd03d  mov     esi, 2
0x1800cd042  mov     [rsp+0D8h+var_B8], esi
0x1800cd046  mov     rcx, [rax]
0x1800cd049  mov     rax, [rcx+8]
0x1800cd04d  mov     rcx, rdi
0x1800cd050  call    cs:__guard_dispatch_icall_fptr
0x1800cd056  test    al, al
0x1800cd058  jz      short loc_1800CD079
0x1800cd05a  mov     rax, [rdi]
0x1800cd05d  mov     rcx, rdi
0x1800cd060  mov     rax, [rax+10h]
0x1800cd064  call    cs:__guard_dispatch_icall_fptr
0x1800cd06a  mov     rcx, rax
0x1800cd06d  lea     rdx, aCheckFailedBit; " Check failed: (bit_width % 8) == (0) "
0x1800cd074  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800cd079  mov     rax, [rdi]
0x1800cd07c  mov     rcx, rdi
0x1800cd07f  mov     rax, [rax+8]
0x1800cd083  call    cs:__guard_dispatch_icall_fptr
0x1800cd089  test    al, al
0x1800cd08b  jz      short loc_1800CD0AD
0x1800cd08d  mov     rax, [rdi]
0x1800cd090  mov     rcx, rdi
0x1800cd093  mov     rax, [rax+10h]
0x1800cd097  call    cs:__guard_dispatch_icall_fptr
0x1800cd09d  mov     rcx, rax
0x1800cd0a0  lea     rdx, aOnlyBitWidthsW; "Only bit widths with multiple of 8 are "...
0x1800cd0a7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800cd0ac  nop
0x1800cd0ad  test    sil, 2
0x1800cd0b1  jz      short loc_1800CD0BD
0x1800cd0b3  lea     rcx, [rsp+0D8h+var_A0]; this
0x1800cd0b8  call    ??1ArrowLog@util@arrow@@UEAA@XZ; arrow::util::ArrowLog::~ArrowLog(void)
0x1800cd0bd  mov     rax, rbp
0x1800cd0c0  imul    rax, r15
0x1800cd0c4  cqo
0x1800cd0c6  and     edx, 7
0x1800cd0c9  lea     r8, [rdx+rax]
0x1800cd0cd  sar     r8, 3
0x1800cd0d1  lea     rdx, [rsp+0D8h+var_68]
0x1800cd0d6  mov     rcx, r14
0x1800cd0d9  call    ?Allocate@KernelContext@compute@arrow@@QEAA?AV?$Result@V?$shared_ptr@VResizableBuffer@arrow@@@std@@@3@_J@Z; arrow::compute::KernelContext::Allocate(__int64)
0x1800cd0de  nop
0x1800cd0df  mov     [rbx+8], r12
0x1800cd0e3  cmp     qword ptr [rax+8], 0
0x1800cd0e8  jnz     short loc_1800CD10C
0x1800cd0ea  mov     [rbx+8], r12
0x1800cd0ee  mov     [rax+8], r12
0x1800cd0f2  mov     rdx, [rax+10h]
0x1800cd0f6  mov     rcx, [rax+18h]
0x1800cd0fa  mov     [rax+10h], r12
0x1800cd0fe  mov     [rax+18h], r12
0x1800cd102  mov     [rbx+10h], rdx
0x1800cd106  mov     [rbx+18h], rcx
0x1800cd10a  jmp     short loc_1800CD118
0x1800cd10c  mov     rdx, rax; struct arrow::Status *
0x1800cd10f  mov     rcx, rbx; this
0x1800cd112  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x1800cd117  nop
0x1800cd118  mov     rcx, [rsp+0D8h+var_60]
0x1800cd11d  test    rcx, rcx
0x1800cd120  jnz     short loc_1800CD173
0x1800cd122  mov     rsi, [rsp+0D8h+var_50]
0x1800cd12a  test    rsi, rsi
0x1800cd12d  jz      short loc_1800CD17D
0x1800cd12f  mov     edi, 0FFFFFFFFh
0x1800cd134  mov     eax, edi
0x1800cd136  lock xadd [rsi+8], eax
0x1800cd13b  cmp     eax, 1
0x1800cd13e  jnz     short loc_1800CD169
0x1800cd140  mov     rax, [rsi]
0x1800cd143  mov     rcx, rsi
0x1800cd146  mov     rax, [rax]
0x1800cd149  call    cs:__guard_dispatch_icall_fptr
0x1800cd14f  lock xadd [rsi+0Ch], edi
0x1800cd154  cmp     edi, 1
0x1800cd157  jnz     short loc_1800CD169
0x1800cd159  mov     rax, [rsi]
0x1800cd15c  mov     rcx, rsi
0x1800cd15f  mov     rax, [rax+8]
0x1800cd163  call    cs:__guard_dispatch_icall_fptr
0x1800cd169  mov     rcx, [rsp+0D8h+var_60]; this
0x1800cd16e  test    rcx, rcx
0x1800cd171  jz      short loc_1800CD17D
0x1800cd173  mov     edx, 1; unsigned int
0x1800cd178  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800cd17d  mov     rax, rbx
0x1800cd180  mov     rcx, [rsp+0D8h+var_48]
0x1800cd188  xor     rcx, rsp; StackCookie
0x1800cd18b  call    __security_check_cookie
0x1800cd190  add     rsp, 0A0h
0x1800cd197  pop     r15
0x1800cd199  pop     r14
0x1800cd19b  pop     r12
0x1800cd19d  pop     rdi
0x1800cd19e  pop     rsi
0x1800cd19f  pop     rbp
0x1800cd1a0  pop     rbx
0x1800cd1a1  retn
```
