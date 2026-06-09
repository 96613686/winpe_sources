# GuestStatePartition::FormatBlockStorage(void)

- ea: `0x1401116e4`
- end: `0x140111aa0`
- name: `?FormatBlockStorage@GuestStatePartition@@AEAAXXZ`
- size: `956`
- prototype: `void __fastcall(GuestStatePartition *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401b9904`

## callees

- `0x14005e7e4`
- `0x1401116e4`
- `0x140111aa8`
- `0x140111b2c`
- `0x140124708`
- `0x140132940`
- `0x1401335fc`
- `0x140177e70`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14011197b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14011197b`
- `RPCRT4!UuidCreate` at `0x140111900`
- `RPCRT4!UuidCreate` at `0x140111945`
- `RPCRT4!UuidCreate` at `0x140111900`
- `RPCRT4!UuidCreate` at `0x140111945`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GuestStatePartition::FormatBlockStorage(GuestStatePartition *this)
{
  __int64 v2; // r14
  size_t v3; // rdx
  size_t v4; // rbx
  char *v5; // rdi
  __int64 v6; // rax
  char v7; // dl
  __int64 v8; // rax
  char v9; // dl
  __int64 v10; // r15
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // r12d
  __int64 v14; // r13
  unsigned __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // r14
  unsigned __int64 v18; // rbx
  char *v19; // rdi
  char *v20; // rax
  size_t v21; // rbx
  char *v22; // rdi
  UUID *v23; // rbx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  __int64 v26; // rcx
  unsigned __int8 v27[2]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v28[6]; // [rsp+42h] [rbp-27h] BYREF
  unsigned __int64 v29; // [rsp+48h] [rbp-21h]
  UUID Uuid; // [rsp+50h] [rbp-19h] BYREF
  void *v31[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v32; // [rsp+70h] [rbp+7h]

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 96LL))(*((_QWORD *)this + 1));
  v3 = *((unsigned int *)this + 8);
  v4 = v2 * v3;
  *(_OWORD *)v31 = 0;
  v32 = 0;
  v27[0] = 0;
  std::vector<enum gsl::byte>::vector<enum gsl::byte>(v31, v3, v27);
  v5 = (char *)v31[0];
  *((_BYTE *)v31[0] + 446) = 0;
  v6 = DiskStructs::Utilities::ChsAddressFromLba(v28, 1, v4);
  v7 = *(_BYTE *)(v6 + 2);
  *(_WORD *)(v5 + 447) = *(_WORD *)v6;
  v5[449] = v7;
  v5[450] = -18;
  *(_DWORD *)(v5 + 454) = 1;
  v8 = DiskStructs::Utilities::ChsAddressFromLba(v28, v2, v4);
  v9 = *(_BYTE *)(v8 + 2);
  *(_WORD *)(v5 + 451) = *(_WORD *)v8;
  v5[453] = v9;
  v10 = v2 - 1;
  v11 = -1;
  if ( (unsigned __int64)(v2 - 1) < 0xFFFFFFFF )
    v11 = v2 - 1;
  *(_DWORD *)(v5 + 458) = v11;
  *((_WORD *)v5 + 255) = -21931;
  (*(void (__fastcall **)(_QWORD, void *, _QWORD, _QWORD, int, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    v31[0],
    *((unsigned int *)this + 8),
    0,
    1,
    0);
  memset_0(v31[0], 0, (char *)v31[1] - (char *)v31[0]);
  v12 = *((_DWORD *)this + 8);
  v13 = -v12 & (v12 + 0x3FFF);
  v14 = v13 / v12;
  v15 = v2 - v14 - 1;
  v16 = (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 112LL))(
          *((_QWORD *)this + 1),
          v13 % v12)
      / v12;
  v17 = ~(v16 - 1) & ((unsigned int)v16 + v14 + 1);
  v29 = v15 - v15 % (unsigned int)v16 - 1;
  v27[0] = 0;
  v18 = v13 + *((_DWORD *)this + 8);
  v19 = (char *)v31[1];
  if ( v18 < (char *)v31[1] - (char *)v31[0] )
  {
    v20 = (char *)v31[0] + v18;
LABEL_9:
    v31[1] = v20;
    goto LABEL_10;
  }
  if ( v18 > (char *)v31[1] - (char *)v31[0] )
  {
    if ( v18 <= v32 - (unsigned __int64)v31[0] )
    {
      v21 = v18 - ((char *)v31[1] - (char *)v31[0]);
      memset_0(v31[1], 0, v21);
      v20 = &v19[v21];
      goto LABEL_9;
    }
    std::vector<unsigned char>::_Resize_reallocate<unsigned char>((__int64)v31, v13 + *((_DWORD *)this + 8), v27);
  }
LABEL_10:
  v22 = (char *)v31[0];
  *(_QWORD *)v31[0] = 0x5452415020494645LL;
  *((_DWORD *)v22 + 2) = 0x10000;
  *((_DWORD *)v22 + 3) = 92;
  *((_QWORD *)v22 + 3) = 1;
  *((_QWORD *)v22 + 4) = v10;
  *((_QWORD *)v22 + 5) = v17;
  *((_QWORD *)v22 + 6) = v29;
  Uuid = 0;
  UuidCreate(&Uuid);
  *(UUID *)(v22 + 56) = Uuid;
  *((_QWORD *)v22 + 9) = 2;
  *((_DWORD *)v22 + 20) = 128;
  *((_DWORD *)v22 + 21) = 128;
  v23 = (UUID *)((char *)v31[0] + *((unsigned int *)this + 8));
  *v23 = GPT_PARTITION_TYPE_GUEST_STATE;
  Uuid = 0;
  UuidCreate(&Uuid);
  v23[1] = Uuid;
  *(_QWORD *)&v23[2].Data1 = v17;
  *(_QWORD *)v23[2].Data4 = v29;
  _o_wcsncpy_s(v23[3].Data4, 36, L"Guest Runtime State Partition", 30);
  *((_DWORD *)v22 + 22) = ComputeCrc32(v24, v23, v13);
  *((_DWORD *)v22 + 4) = ComputeCrc32(v25, v22, 0x5Cu);
  (*(void (__fastcall **)(_QWORD, void *, _QWORD, __int64, _DWORD, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    v31[0],
    v13 + *((_DWORD *)this + 8),
    1,
    v14 + 1,
    0);
  v26 = *((_QWORD *)v22 + 3);
  *((_QWORD *)v22 + 3) = *((_QWORD *)v22 + 4);
  *((_QWORD *)v22 + 4) = v26;
  *((_QWORD *)v22 + 9) = v10 - v14;
  *((_DWORD *)v22 + 4) = ComputeCrc32(v26, v22, 0x5Cu);
  (*(void (__fastcall **)(_QWORD, void *, _QWORD, __int64, int, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    v31[0],
    *((unsigned int *)this + 8),
    v10,
    1,
    0);
  (*(void (__fastcall **)(_QWORD, char *, _QWORD, __int64, _DWORD, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    (char *)v31[0] + *((unsigned int *)this + 8),
    v13,
    v10 - v14,
    v14,
    0);
  *((_QWORD *)this + 2) = v17;
  *((_QWORD *)this + 3) = v29 - v17 + 1;
  std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v31);
}

```

## disassembly

```asm
0x1401116e4  push    rbp
0x1401116e6  push    rbx
0x1401116e7  push    rsi
0x1401116e8  push    rdi
0x1401116e9  push    r12
0x1401116eb  push    r13
0x1401116ed  push    r14
0x1401116ef  push    r15
0x1401116f1  lea     rbp, [rsp-1Fh]
0x1401116f6  sub     rsp, 88h
0x1401116fd  mov     rax, cs:__security_cookie
0x140111704  xor     rax, rsp
0x140111707  mov     [rbp+57h+var_48], rax
0x14011170b  mov     rsi, rcx
0x14011170e  mov     rcx, [rcx+8]
0x140111712  mov     rax, [rcx]
0x140111715  mov     rax, [rax+60h]
0x140111719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011171e  mov     r14, rax
0x140111721  mov     edx, [rsi+20h]
0x140111724  mov     ebx, edx
0x140111726  imul    rbx, rax
0x14011172a  xorps   xmm0, xmm0
0x14011172d  xor     eax, eax
0x14011172f  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x140111733  mov     [rbp+57h+var_50], rax
0x140111737  xor     r12d, r12d
0x14011173a  mov     [rbp+57h+var_80], r12b
0x14011173e  lea     r8, [rbp+57h+var_80]
0x140111742  lea     rcx, [rbp+57h+var_60]
0x140111746  call    ??$?0V?$allocator@W4byte@gsl@@@std@@$0A@@?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBW4byte@gsl@@AEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,gsl::byte const &,std::allocator<gsl::byte> const &)
0x14011174b  nop
0x14011174c  mov     rdi, [rbp+57h+var_60]
0x140111750  mov     [rdi+1BEh], r12b
0x140111757  mov     r8, rbx
0x14011175a  lea     r13d, [r12+1]
0x14011175f  mov     edx, r13d
0x140111762  lea     rcx, [rbp+57h+var_7E]
0x140111766  call    ?ChsAddressFromLba@Utilities@DiskStructs@@YA?AU_CHS_ADDRESS@@_K0@Z; DiskStructs::Utilities::ChsAddressFromLba(unsigned __int64,unsigned __int64)
0x14011176b  movzx   ecx, word ptr [rax]
0x14011176e  mov     dl, [rax+2]
0x140111771  mov     [rdi+1BFh], cx
0x140111778  mov     [rdi+1C1h], dl
0x14011177e  mov     byte ptr [rdi+1C2h], 0EEh
0x140111785  mov     [rdi+1C6h], r13d
0x14011178c  mov     r8, rbx
0x14011178f  mov     rdx, r14
0x140111792  lea     rcx, [rbp+57h+var_7E]
0x140111796  call    ?ChsAddressFromLba@Utilities@DiskStructs@@YA?AU_CHS_ADDRESS@@_K0@Z; DiskStructs::Utilities::ChsAddressFromLba(unsigned __int64,unsigned __int64)
0x14011179b  movzx   ecx, word ptr [rax]
0x14011179e  mov     dl, [rax+2]
0x1401117a1  mov     [rdi+1C3h], cx
0x1401117a8  mov     [rdi+1C5h], dl
0x1401117ae  lea     r15, [r14-1]
0x1401117b2  mov     eax, 0FFFFFFFFh
0x1401117b7  cmp     r15, rax
0x1401117ba  jnb     short loc_1401117BF
0x1401117bc  mov     eax, r15d
0x1401117bf  mov     [rdi+1CAh], eax
0x1401117c5  mov     word ptr [rdi+1FEh], 0AA55h
0x1401117ce  mov     rcx, [rsi+8]
0x1401117d2  mov     rax, [rcx]
0x1401117d5  mov     [rsp+0C0h+var_98], r12
0x1401117da  mov     [rsp+0C0h+var_A0], r13d
0x1401117df  xor     r9d, r9d
0x1401117e2  mov     r8d, [rsi+20h]
0x1401117e6  mov     rdx, [rbp+57h+var_60]
0x1401117ea  mov     rax, [rax+80h]
0x1401117f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401117f6  mov     rcx, [rbp+57h+var_60]; void *
0x1401117fa  mov     r8, [rbp+57h+var_60+8]
0x1401117fe  sub     r8, rcx; Size
0x140111801  xor     edx, edx; Val
0x140111803  call    memset_0
0x140111808  mov     ebx, [rsi+20h]
0x14011180b  lea     r12d, [rbx+3FFFh]
0x140111812  mov     eax, ebx
0x140111814  neg     eax
0x140111816  and     r12d, eax
0x140111819  xor     edx, edx
0x14011181b  mov     eax, r12d
0x14011181e  div     ebx
0x140111820  mov     r13d, eax
0x140111823  sub     r14, r13
0x140111826  lea     rdi, [r14-1]
0x14011182a  mov     rcx, [rsi+8]
0x14011182e  mov     rax, [rcx]
0x140111831  mov     rax, [rax+70h]
0x140111835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011183a  xor     edx, edx
0x14011183c  div     ebx
0x14011183e  mov     ecx, eax
0x140111840  lea     r14, [r13+1]
0x140111844  add     r14, rcx
0x140111847  dec     rax
0x14011184a  not     rax
0x14011184d  and     r14, rax
0x140111850  xor     edx, edx
0x140111852  mov     rax, rdi
0x140111855  div     rcx
0x140111858  sub     rdi, rdx
0x14011185b  lea     rax, [rdi-1]
0x14011185f  mov     [rbp+57h+var_78], rax
0x140111863  mov     [rbp+57h+var_80], 0
0x140111867  mov     ebx, [rsi+20h]
0x14011186a  add     ebx, r12d
0x14011186d  mov     rdx, [rbp+57h+var_60]
0x140111871  mov     rdi, [rbp+57h+var_60+8]
0x140111875  mov     rcx, rdi
0x140111878  sub     rcx, rdx
0x14011187b  cmp     rbx, rcx
0x14011187e  jnb     short loc_140111886
0x140111880  lea     rax, [rbx+rdx]
0x140111884  jmp     short loc_1401118BA
0x140111886  jbe     short loc_1401118BE
0x140111888  mov     rax, [rbp+57h+var_50]
0x14011188c  sub     rax, rdx
0x14011188f  cmp     rbx, rax
0x140111892  jbe     short loc_1401118A6
0x140111894  lea     r8, [rbp+57h+var_80]
0x140111898  mov     rdx, rbx
0x14011189b  lea     rcx, [rbp+57h+var_60]
0x14011189f  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x1401118a4  jmp     short loc_1401118BE
0x1401118a6  sub     rbx, rcx
0x1401118a9  mov     r8, rbx; Size
0x1401118ac  xor     edx, edx; Val
0x1401118ae  mov     rcx, rdi; void *
0x1401118b1  call    memset_0
0x1401118b6  lea     rax, [rbx+rdi]
0x1401118ba  mov     [rbp+57h+var_60+8], rax
0x1401118be  mov     rdi, [rbp+57h+var_60]
0x1401118c2  mov     rax, 5452415020494645h
0x1401118cc  mov     [rdi], rax
0x1401118cf  mov     dword ptr [rdi+8], 10000h
0x1401118d6  mov     dword ptr [rdi+0Ch], 5Ch ; '\'
0x1401118dd  mov     qword ptr [rdi+18h], 1
0x1401118e5  mov     [rdi+20h], r15
0x1401118e9  mov     [rdi+28h], r14
0x1401118ed  mov     rax, [rbp+57h+var_78]
0x1401118f1  mov     [rdi+30h], rax
0x1401118f5  xorps   xmm0, xmm0
0x1401118f8  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1401118fc  lea     rcx, [rbp+57h+Uuid]; Uuid
0x140111900  call    cs:__imp_UuidCreate
0x140111907  nop     dword ptr [rax+rax+00h]
0x14011190c  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x140111910  movdqu  xmmword ptr [rdi+38h], xmm0
0x140111915  mov     qword ptr [rdi+48h], 2
0x14011191d  mov     eax, 80h
0x140111922  mov     [rdi+50h], eax
0x140111925  mov     [rdi+54h], eax
0x140111928  mov     ebx, [rsi+20h]
0x14011192b  add     rbx, [rbp+57h+var_60]
0x14011192f  movups  xmm0, xmmword ptr cs:?GPT_PARTITION_TYPE_GUEST_STATE@@3U_GUID@@B.Data1; _GUID const GPT_PARTITION_TYPE_GUEST_STATE ...
0x140111936  movdqu  xmmword ptr [rbx], xmm0
0x14011193a  xorps   xmm0, xmm0
0x14011193d  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x140111941  lea     rcx, [rbp+57h+Uuid]; Uuid
0x140111945  call    cs:__imp_UuidCreate
0x14011194c  nop     dword ptr [rax+rax+00h]
0x140111951  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x140111955  movdqu  xmmword ptr [rbx+10h], xmm0
0x14011195a  mov     [rbx+20h], r14
0x14011195e  mov     rax, [rbp+57h+var_78]
0x140111962  mov     [rbx+28h], rax
0x140111966  lea     rcx, [rbx+38h]
0x14011196a  mov     r9d, 1Eh
0x140111970  lea     r8, ?GPT_PARTITION_NAME_GUEST_STATE@@3QBGB; "Guest Runtime State Partition"
0x140111977  lea     edx, [r9+6]
0x14011197b  call    cs:__imp__o_wcsncpy_s
0x140111982  nop     dword ptr [rax+rax+00h]
0x140111987  mov     r8d, r12d; unsigned int
0x14011198a  mov     rdx, rbx; void *
0x14011198d  call    ?ComputeCrc32@@YAKKPEBXK@Z; ComputeCrc32(ulong,void const *,ulong)
0x140111992  mov     [rdi+58h], eax
0x140111995  mov     r8d, 5Ch ; '\'; unsigned int
0x14011199b  mov     rdx, rdi; void *
0x14011199e  call    ?ComputeCrc32@@YAKKPEBXK@Z; ComputeCrc32(ulong,void const *,ulong)
0x1401119a3  mov     [rdi+10h], eax
0x1401119a6  mov     rcx, [rsi+8]
0x1401119aa  mov     rdx, [rcx]
0x1401119ad  lea     r9d, [r13+1]
0x1401119b1  mov     r8d, [rsi+20h]
0x1401119b5  add     r8d, r12d
0x1401119b8  mov     rax, [rdx+80h]
0x1401119bf  mov     [rsp+0C0h+var_98], 0
0x1401119c8  mov     [rsp+0C0h+var_A0], r9d
0x1401119cd  mov     r9d, 1
0x1401119d3  mov     rdx, [rbp+57h+var_60]
0x1401119d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401119dc  mov     rbx, r15
0x1401119df  sub     rbx, r13
0x1401119e2  mov     rcx, [rdi+18h]; unsigned int
0x1401119e6  mov     rax, [rdi+20h]
0x1401119ea  mov     [rdi+18h], rax
0x1401119ee  mov     [rdi+20h], rcx
0x1401119f2  mov     [rdi+48h], rbx
0x1401119f6  mov     r8d, 5Ch ; '\'; unsigned int
0x1401119fc  mov     rdx, rdi; void *
0x1401119ff  call    ?ComputeCrc32@@YAKKPEBXK@Z; ComputeCrc32(ulong,void const *,ulong)
0x140111a04  mov     [rdi+10h], eax
0x140111a07  mov     rcx, [rsi+8]
0x140111a0b  mov     rax, [rcx]
0x140111a0e  mov     [rsp+0C0h+var_98], 0
0x140111a17  mov     [rsp+0C0h+var_A0], 1
0x140111a1f  mov     r9, r15
0x140111a22  mov     r8d, [rsi+20h]
0x140111a26  mov     rdx, [rbp+57h+var_60]
0x140111a2a  mov     rax, [rax+80h]
0x140111a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140111a36  mov     rcx, [rsi+8]
0x140111a3a  mov     rax, [rcx]
0x140111a3d  mov     edx, [rsi+20h]
0x140111a40  add     rdx, [rbp+57h+var_60]
0x140111a44  mov     [rsp+0C0h+var_98], 0
0x140111a4d  mov     [rsp+0C0h+var_A0], r13d
0x140111a52  mov     r9, rbx
0x140111a55  mov     r8d, r12d
0x140111a58  mov     rax, [rax+80h]
0x140111a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140111a64  mov     [rsi+10h], r14
0x140111a68  mov     rax, [rbp+57h+var_78]
0x140111a6c  sub     rax, r14
0x140111a6f  inc     rax
0x140111a72  mov     [rsi+18h], rax
0x140111a76  lea     rcx, [rbp+57h+var_60]
0x140111a7a  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140111a7f  mov     rcx, [rbp+57h+var_48]
0x140111a83  xor     rcx, rsp; StackCookie
0x140111a86  call    __security_check_cookie
0x140111a8b  add     rsp, 88h
0x140111a92  pop     r15
0x140111a94  pop     r14
0x140111a96  pop     r13
0x140111a98  pop     r12
0x140111a9a  pop     rdi
0x140111a9b  pop     rsi
0x140111a9c  pop     rbx
0x140111a9d  pop     rbp
0x140111a9e  retn
```
