# Streaming::WriteFault::ProcessFault(void)

- ea: `0x140014dcc`
- end: `0x140014fea`
- name: `?ProcessFault@WriteFault@Streaming@@QEAA?AW4_FLT_PREOP_CALLBACK_STATUS@@XZ`
- size: `542`
- prototype: `__int64 __fastcall(Streaming::WriteFault *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000de2c`
- `0x14000ebd0`

## callees

- `0x140010130`
- `0x140014364`
- `0x140014b00`
- `0x140014dcc`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140014fc7`
- `ntoskrnl!DbgPrint` at `0x140014fc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014f38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014f38`
- `ntoskrnl!ExAllocatePool2` at `0x140014e81`
- `ntoskrnl!ExAllocatePool2` at `0x140014e81`

## string_xrefs

- `0x140014fb0`: `complete write file %wZ \n`

## pseudocode

```c
__int64 __fastcall Streaming::WriteFault::ProcessFault(Streaming::WriteFault *this)
{
  __int64 v1; // rax
  unsigned int v3; // ecx
  __int16 v4; // dx
  __int16 v5; // ax
  __int64 v6; // r15
  __int64 v7; // r12
  __int64 v8; // rsi
  unsigned __int16 v9; // si
  __int64 v10; // rbx
  unsigned __int16 v11; // bx
  ULONG v12; // r13d
  __int64 Pool2; // rax
  unsigned __int16 *v14; // r14
  __int128 v15; // xmm0
  int v16; // esi
  volatile signed __int32 *v17; // rbx
  __int64 v18; // rcx
  __int64 result; // rax
  __int128 v20; // xmm1
  _OWORD v21[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v23; // [rsp+A8h] [rbp+50h] BYREF
  int v24; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+60h] BYREF

  v1 = *((_QWORD *)this + 8);
  v3 = *((_DWORD *)this + 8) >> 1;
  v22 = v1;
  if ( v3 > 0xFFFF )
    v4 = -1;
  else
    v4 = v3;
  v5 = 0;
  v6 = 0;
  if ( v3 <= 0xFFFF )
    v5 = v4;
  if ( v5 )
    v6 = *((_QWORD *)this + 5);
  v7 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v21, *(_QWORD *)this + 32LL);
  if ( !v7 )
    goto LABEL_18;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(v7 + 2 * v8) );
  v9 = 2 * v8;
  if ( v6 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(v6 + 2 * v10) );
    v11 = 2 * v10;
  }
  else
  {
    v11 = 0;
  }
  v12 = v9 + 36 + v11;
  Pool2 = ExAllocatePool2(256, v12, 1835820659);
  v14 = (unsigned __int16 *)Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 64;
    *(_DWORD *)(Pool2 + 4) = v12;
    *(_WORD *)(Pool2 + 32) = v9;
    v15 = *((_OWORD *)this + 1);
    v25 = Pool2 + 36;
    *(_OWORD *)(Pool2 + 8) = v15;
    *(_QWORD *)(Pool2 + 24) = v22;
    *(_WORD *)(Pool2 + 34) = v11;
    messages::write<wchar_t const *>(&v25, Pool2, &v22, v7, v9);
    messages::write<wchar_t const *>(&v25, v14, &v22, v6, v14[17]);
    v24 = 0;
    v23 = 4;
    v16 = Streaming::Messaging::UserCommunication::SendMessage(
            *((Streaming::Messaging::UserCommunication **)Streaming::gStrmFltData + 4),
            v14,
            v12,
            &v24,
            &v23);
    ExFreePoolWithTag(v14, 0);
  }
  else
  {
LABEL_18:
    v16 = -1073741811;
  }
  v17 = (volatile signed __int32 *)*((_QWORD *)&v21[0] + 1);
  if ( *((_QWORD *)&v21[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  if ( v16 >= 0 )
  {
    v20 = *(_OWORD *)(*(_QWORD *)this + 64LL);
    v21[0] = *(_OWORD *)(*(_QWORD *)this + 48LL);
    v21[1] = v20;
    DbgPrint("complete write file %wZ \n", v21);
    return 1;
  }
  else
  {
    v18 = *((_QWORD *)this + 1);
    result = 4;
    *(_DWORD *)(v18 + 24) = -1073741818;
    *(_QWORD *)(v18 + 32) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140014dcc  push    rbp
0x140014dce  push    rbx
0x140014dcf  push    rsi
0x140014dd0  push    rdi
0x140014dd1  push    r12
0x140014dd3  push    r13
0x140014dd5  push    r14
0x140014dd7  push    r15
0x140014dd9  mov     rbp, rsp
0x140014ddc  sub     rsp, 58h
0x140014de0  mov     rax, [rcx+40h]
0x140014de4  mov     rdi, rcx
0x140014de7  mov     ecx, [rcx+20h]
0x140014dea  mov     r8d, 0FFFFh
0x140014df0  shr     ecx, 1
0x140014df2  mov     [rbp+arg_0], rax
0x140014df6  cmp     ecx, r8d
0x140014df9  ja      short loc_140014E00
0x140014dfb  movzx   edx, cx
0x140014dfe  jmp     short loc_140014E03
0x140014e00  mov     edx, r8d
0x140014e03  xor     r13d, r13d
0x140014e06  cmp     ecx, r8d
0x140014e09  mov     eax, r13d
0x140014e0c  mov     r15d, r13d
0x140014e0f  cmovbe  ax, dx
0x140014e13  test    ax, ax
0x140014e16  jz      short loc_140014E1C
0x140014e18  mov     r15, [rdi+28h]
0x140014e1c  mov     rdx, [rdi]
0x140014e1f  lea     rcx, [rbp+var_28]
0x140014e23  add     rdx, 20h ; ' '
0x140014e27  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140014e2c  mov     r12, [rax]
0x140014e2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140014e33  test    r12, r12
0x140014e36  jz      loc_140014F49
0x140014e3c  mov     rsi, rax
0x140014e3f  inc     rsi
0x140014e42  cmp     [r12+rsi*2], r13w
0x140014e47  jnz     short loc_140014E3F
0x140014e49  add     si, si
0x140014e4c  test    r15, r15
0x140014e4f  jz      short loc_140014E63
0x140014e51  mov     rbx, rax
0x140014e54  inc     rbx
0x140014e57  cmp     [r15+rbx*2], r13w
0x140014e5c  jnz     short loc_140014E54
0x140014e5e  add     bx, bx
0x140014e61  jmp     short loc_140014E66
0x140014e63  mov     ebx, r13d
0x140014e66  movzx   ecx, si
0x140014e69  mov     r8d, 6D6C6673h
0x140014e6f  add     ecx, 24h ; '$'
0x140014e72  movzx   r13d, bx
0x140014e76  add     r13d, ecx
0x140014e79  mov     ecx, 100h
0x140014e7e  mov     edx, r13d
0x140014e81  call    cs:__imp_ExAllocatePool2
0x140014e88  nop     dword ptr [rax+rax+00h]
0x140014e8d  mov     r14, rax
0x140014e90  test    rax, rax
0x140014e93  jz      loc_140014F46
0x140014e99  mov     dword ptr [rax], 40h ; '@'
0x140014e9f  lea     rcx, [r14+24h]
0x140014ea3  mov     [rax+4], r13d
0x140014ea7  lea     r8, [rbp+arg_0]
0x140014eab  mov     [rax+20h], si
0x140014eaf  mov     r9, r12
0x140014eb2  movups  xmm0, xmmword ptr [rdi+10h]
0x140014eb6  mov     [rbp+arg_18], rcx
0x140014eba  mov     rdx, r14
0x140014ebd  movzx   ecx, si
0x140014ec0  movdqu  xmmword ptr [rax+8], xmm0
0x140014ec5  mov     rax, [rbp+arg_0]
0x140014ec9  mov     [rsp+58h+var_38], rcx
0x140014ece  lea     rcx, [rbp+arg_18]
0x140014ed2  mov     [r14+18h], rax
0x140014ed6  mov     [r14+22h], bx
0x140014edb  call    ??$write@PEB_W@messages@@YAXAEAPEAEPEBEAEAKQEB_W_K@Z; messages::write<wchar_t const *>(uchar * &,uchar const *,ulong &,wchar_t const * const,unsigned __int64)
0x140014ee0  movzx   eax, word ptr [r14+22h]
0x140014ee5  lea     r8, [rbp+arg_0]
0x140014ee9  mov     r9, r15
0x140014eec  mov     [rsp+58h+var_38], rax
0x140014ef1  mov     rdx, r14
0x140014ef4  lea     rcx, [rbp+arg_18]
0x140014ef8  call    ??$write@PEB_W@messages@@YAXAEAPEAEPEBEAEAKQEB_W_K@Z; messages::write<wchar_t const *>(uchar * &,uchar const *,ulong &,wchar_t const * const,unsigned __int64)
0x140014efd  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140014f04  lea     rax, [rbp+arg_8]
0x140014f08  mov     [rbp+arg_10], 0
0x140014f0f  lea     r9, [rbp+arg_10]; void *
0x140014f13  mov     [rbp+arg_8], 4
0x140014f1a  mov     r8d, r13d; unsigned int
0x140014f1d  mov     rdx, r14; void *
0x140014f20  mov     [rsp+58h+var_38], rax; unsigned int *
0x140014f25  mov     rcx, [rcx+20h]; this
0x140014f29  call    ?SendMessage@UserCommunication@Messaging@Streaming@@QEAAJPEAXK0AEAK@Z; Streaming::Messaging::UserCommunication::SendMessage(void *,ulong,void *,ulong &)
0x140014f2e  xor     edx, edx; Tag
0x140014f30  mov     rcx, r14; P
0x140014f33  xor     r13d, r13d
0x140014f36  mov     esi, eax
0x140014f38  call    cs:__imp_ExFreePoolWithTag
0x140014f3f  nop     dword ptr [rax+rax+00h]
0x140014f44  jmp     short loc_140014F4E
0x140014f46  xor     r13d, r13d
0x140014f49  mov     esi, 0C000000Dh
0x140014f4e  mov     rbx, qword ptr [rbp+var_28+8]
0x140014f52  test    rbx, rbx
0x140014f55  jz      short loc_140014F8F
0x140014f57  or      eax, 0FFFFFFFFh
0x140014f5a  lock xadd [rbx+8], eax
0x140014f5f  cmp     eax, 1
0x140014f62  jnz     short loc_140014F8F
0x140014f64  mov     rax, [rbx]
0x140014f67  mov     rcx, rbx
0x140014f6a  mov     rax, [rax+8]
0x140014f6e  call    _guard_dispatch_icall
0x140014f73  or      eax, 0FFFFFFFFh
0x140014f76  lock xadd [rbx+0Ch], eax
0x140014f7b  cmp     eax, 1
0x140014f7e  jnz     short loc_140014F8F
0x140014f80  mov     rdx, [rbx]
0x140014f83  mov     rcx, rbx
0x140014f86  mov     rax, [rdx+10h]
0x140014f8a  call    _guard_dispatch_icall
0x140014f8f  test    esi, esi
0x140014f91  jns     short loc_140014FA9
0x140014f93  mov     rcx, [rdi+8]
0x140014f97  mov     eax, 4
0x140014f9c  mov     dword ptr [rcx+18h], 0C0000006h
0x140014fa3  mov     [rcx+20h], r13
0x140014fa7  jmp     short loc_140014FD8
0x140014fa9  mov     rax, [rdi]
0x140014fac  lea     rdx, [rbp+var_28]
0x140014fb0  lea     rcx, aCompleteWriteF; "complete write file %wZ \n"
0x140014fb7  movups  xmm0, xmmword ptr [rax+30h]
0x140014fbb  movups  xmm1, xmmword ptr [rax+40h]
0x140014fbf  movaps  [rbp+var_28], xmm0
0x140014fc3  movaps  [rbp+var_18], xmm1
0x140014fc7  call    cs:__imp_DbgPrint
0x140014fce  nop     dword ptr [rax+rax+00h]
0x140014fd3  mov     eax, 1
0x140014fd8  add     rsp, 58h
0x140014fdc  pop     r15
0x140014fde  pop     r14
0x140014fe0  pop     r13
0x140014fe2  pop     r12
0x140014fe4  pop     rdi
0x140014fe5  pop     rsi
0x140014fe6  pop     rbx
0x140014fe7  pop     rbp
0x140014fe8  retn
```
