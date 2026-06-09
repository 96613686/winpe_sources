# Streaming::staging_operations::stage_directory(wchar_t const *,wchar_t const *,void * const,_GUID const &)

- ea: `0x140011478`
- end: `0x1400115c6`
- name: `?stage_directory@staging_operations@Streaming@@YAJPEB_W0QEAXAEBU_GUID@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(Streaming::staging_operations *this, const wchar_t *, const wchar_t *, _OWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a310`

## callees

- `0x140010130`
- `0x140011478`
- `0x140014364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001159f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001159f`
- `ntoskrnl!ExAllocatePool2` at `0x1400114e4`
- `ntoskrnl!ExAllocatePool2` at `0x1400114e4`

## pseudocode

```c
__int64 __fastcall Streaming::staging_operations::stage_directory(
        Streaming::staging_operations *this,
        const wchar_t *a2,
        const wchar_t *a3,
        _OWORD *a4)
{
  __int64 v8; // rbx
  __int64 v9; // rdi
  unsigned __int16 v10; // di
  unsigned __int16 v11; // bx
  ULONG v12; // r15d
  __int64 Pool2; // rax
  unsigned __int16 *v14; // rsi
  unsigned int v15; // ebx
  _BYTE v17[4]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-54h] BYREF
  _QWORD v19[10]; // [rsp+38h] [rbp-50h] BYREF
  char v20; // [rsp+90h] [rbp+8h] BYREF

  if ( !this )
    return 3221225485LL;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)this + v9) );
  v10 = 2 * v9;
  if ( a2 )
  {
    do
      ++v8;
    while ( a2[v8] );
    v11 = 2 * v8;
  }
  else
  {
    v11 = 0;
  }
  v12 = v10 + 36 + v11;
  Pool2 = ExAllocatePool2(256, v12, 1852663411);
  v14 = (unsigned __int16 *)Pool2;
  if ( !Pool2 )
    return 3221225485LL;
  *(_DWORD *)Pool2 = 68;
  v19[0] = Pool2 + 36;
  *(_DWORD *)(Pool2 + 4) = v12;
  *(_WORD *)(Pool2 + 32) = v10;
  *(_OWORD *)(Pool2 + 8) = *a4;
  *(_WORD *)(Pool2 + 34) = v11;
  *(_QWORD *)(Pool2 + 24) = a3;
  messages::write<wchar_t const *>(v19, Pool2, v17, this, v10);
  messages::write<wchar_t const *>(v19, v14, v17, a2, v14[17]);
  v18 = 1;
  v20 = 0;
  v15 = Streaming::Messaging::UserCommunication::SendMessage(
          *((Streaming::Messaging::UserCommunication **)Streaming::gStrmFltData + 4),
          v14,
          v12,
          &v20,
          &v18);
  ExFreePoolWithTag(v14, 0);
  return v15;
}

```

## disassembly

```asm
0x140011478  push    rbx
0x14001147a  push    rbp
0x14001147b  push    rsi
0x14001147c  push    rdi
0x14001147d  push    r12
0x14001147f  push    r13
0x140011481  push    r14
0x140011483  push    r15
0x140011485  sub     rsp, 48h
0x140011489  xor     eax, eax
0x14001148b  mov     r12, r9
0x14001148e  mov     r13, r8
0x140011491  mov     r14, rdx
0x140011494  mov     rbp, rcx
0x140011497  test    rcx, rcx
0x14001149a  jz      loc_1400115AF
0x1400114a0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400114a4  mov     rdi, rbx
0x1400114a7  inc     rdi
0x1400114aa  cmp     [rcx+rdi*2], ax
0x1400114ae  jnz     short loc_1400114A7
0x1400114b0  add     di, di
0x1400114b3  test    r14, r14
0x1400114b6  jz      short loc_1400114C6
0x1400114b8  inc     rbx
0x1400114bb  cmp     [rdx+rbx*2], ax
0x1400114bf  jnz     short loc_1400114B8
0x1400114c1  add     bx, bx
0x1400114c4  jmp     short loc_1400114C9
0x1400114c6  movzx   ebx, ax
0x1400114c9  movzx   ecx, di
0x1400114cc  mov     r8d, 6E6D6673h
0x1400114d2  add     ecx, 24h ; '$'
0x1400114d5  movzx   r15d, bx
0x1400114d9  add     r15d, ecx
0x1400114dc  mov     ecx, 100h
0x1400114e1  mov     edx, r15d
0x1400114e4  call    cs:__imp_ExAllocatePool2
0x1400114eb  nop     dword ptr [rax+rax+00h]
0x1400114f0  mov     rsi, rax
0x1400114f3  test    rax, rax
0x1400114f6  jz      loc_1400115AF
0x1400114fc  lea     rcx, [rax+24h]
0x140011500  mov     dword ptr [rax], 44h ; 'D'
0x140011506  mov     [rsp+88h+var_50], rcx
0x14001150b  lea     r8, [rsp+88h+var_58]
0x140011510  mov     [rax+4], r15d
0x140011514  mov     r9, rbp
0x140011517  mov     [rax+20h], di
0x14001151b  mov     rdx, rax
0x14001151e  movups  xmm0, xmmword ptr [r12]
0x140011523  movzx   ecx, di
0x140011526  mov     [rsp+88h+var_68], rcx
0x14001152b  lea     rcx, [rsp+88h+var_50]
0x140011530  movdqu  xmmword ptr [rax+8], xmm0
0x140011535  mov     [rax+22h], bx
0x140011539  mov     [rax+18h], r13
0x14001153d  call    ??$write@PEB_W@messages@@YAXAEAPEAEPEBEAEAKQEB_W_K@Z; messages::write<wchar_t const *>(uchar * &,uchar const *,ulong &,wchar_t const * const,unsigned __int64)
0x140011542  movzx   eax, word ptr [rsi+22h]
0x140011546  lea     r8, [rsp+88h+var_58]
0x14001154b  mov     r9, r14
0x14001154e  mov     [rsp+88h+var_68], rax
0x140011553  mov     rdx, rsi
0x140011556  lea     rcx, [rsp+88h+var_50]
0x14001155b  call    ??$write@PEB_W@messages@@YAXAEAPEAEPEBEAEAKQEB_W_K@Z; messages::write<wchar_t const *>(uchar * &,uchar const *,ulong &,wchar_t const * const,unsigned __int64)
0x140011560  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140011567  lea     rax, [rsp+88h+var_54]
0x14001156c  mov     [rsp+88h+var_54], 1
0x140011574  lea     r9, [rsp+88h+arg_0]; void *
0x14001157c  mov     [rsp+88h+arg_0], 0
0x140011584  mov     r8d, r15d; unsigned int
0x140011587  mov     rdx, rsi; void *
0x14001158a  mov     [rsp+88h+var_68], rax; unsigned int *
0x14001158f  mov     rcx, [rcx+20h]; this
0x140011593  call    ?SendMessage@UserCommunication@Messaging@Streaming@@QEAAJPEAXK0AEAK@Z; Streaming::Messaging::UserCommunication::SendMessage(void *,ulong,void *,ulong &)
0x140011598  xor     edx, edx; Tag
0x14001159a  mov     rcx, rsi; P
0x14001159d  mov     ebx, eax
0x14001159f  call    cs:__imp_ExFreePoolWithTag
0x1400115a6  nop     dword ptr [rax+rax+00h]
0x1400115ab  mov     eax, ebx
0x1400115ad  jmp     short loc_1400115B4
0x1400115af  mov     eax, 0C000000Dh
0x1400115b4  add     rsp, 48h
0x1400115b8  pop     r15
0x1400115ba  pop     r14
0x1400115bc  pop     r13
0x1400115be  pop     r12
0x1400115c0  pop     rdi
0x1400115c1  pop     rsi
0x1400115c2  pop     rbp
0x1400115c3  pop     rbx
0x1400115c4  retn
```
