# PduRecv_ToIRemoteTextInputClient::On_RDPTXT_UPDATE_COMPOSITION_PDU(Gryps::FlexIBuffer *)

- ea: `0x18003a550`
- end: `0x18003a7d3`
- name: `?On_RDPTXT_UPDATE_COMPOSITION_PDU@PduRecv_ToIRemoteTextInputClient@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(PduRecv_ToIRemoteTextInputClient *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800399d0`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180038c0c`
- `0x180038d7c`
- `0x180039678`
- `0x18003a550`
- `0x18003b8a4`
- `0x180058010`

## import_xrefs

- `CoreMessaging!MsgBlobCreateShared` at `0x18003a6c7`
- `CoreMessaging!MsgBlobCreateShared` at `0x18003a6c7`
- `CoreMessaging!MsgRelease` at `0x18003a799`
- `CoreMessaging!MsgRelease` at `0x18003a799`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PduRecv_ToIRemoteTextInputClient::On_RDPTXT_UPDATE_COMPOSITION_PDU(
        PduRecv_ToIRemoteTextInputClient *this,
        struct Gryps::FlexIBuffer *a2)
{
  unsigned int v4; // esi
  int v5; // r13d
  __int64 v6; // r12
  unsigned int v7; // r14d
  __int128 *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v12; // [rsp+20h] [rbp-99h]
  _BYTE v13[4]; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v14; // [rsp+44h] [rbp-75h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v16; // [rsp+4Ch] [rbp-6Dh] BYREF
  unsigned int v17; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v18; // [rsp+54h] [rbp-65h] BYREF
  unsigned int v19; // [rsp+58h] [rbp-61h] BYREF
  __int64 v20; // [rsp+60h] [rbp-59h] BYREF
  __int128 v21; // [rsp+68h] [rbp-51h] BYREF
  __m128i si128; // [rsp+78h] [rbp-41h]
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+88h] [rbp-31h] BYREF
  __int128 v24; // [rsp+98h] [rbp-21h]
  __int64 v25; // [rsp+A8h] [rbp-11h]
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v27; // [rsp+C0h] [rbp+7h]
  __int64 v28; // [rsp+D0h] [rbp+17h]

  v4 = 0;
  v19 = 0;
  v15 = 0;
  v18 = 0;
  v16 = 0;
  v20 = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180082080, (unsigned __int8 *)byte_18007586D, 0, 0, 2u, &v26);
  }
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v19);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v15);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v18);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v16);
  v13[0] = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, v13);
  v5 = v13[0];
  v6 = *((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1);
  v7 = 4;
  v14 = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v14);
  if ( v14 )
  {
    do
    {
      v17 = 0;
      Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v17);
      v7 += 2 * v17 + 12;
      *((_QWORD *)a2 + 2) += v17 + 8LL;
      ++v4;
    }
    while ( v4 < v14 );
  }
  *((_QWORD *)a2 + 2) = v6 + *((_QWORD *)a2 + 1);
  v21 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v21) = 0;
  Gryps::FlexIBuffer::extractString(a2, &v21, v7);
  v8 = &v21;
  if ( si128.m128i_i64[1] > 0xFuLL )
    v8 = (__int128 *)v21;
  MsgBlobCreateShared(v8, v7, &v20);
  (*(void (__fastcall **)(_QWORD, struct _EVENT_DATA_DESCRIPTOR *, _QWORD))(**((_QWORD **)this + 1) + 56LL))(
    *((_QWORD *)this + 1),
    &v23,
    v18);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), v19);
  if ( v5 == 1 || v5 == 2 )
  {
    v10 = *((_QWORD *)this + 3);
    v26 = v23;
    v27 = v24;
    v28 = v25;
    LOBYTE(v12) = v5 == 1;
    (*(void (__fastcall **)(__int64, struct _EVENT_DATA_DESCRIPTOR *, _QWORD, _QWORD, int, __int64))(*(_QWORD *)v10 + 88LL))(
      v10,
      &v26,
      v16,
      v15,
      v12,
      v20);
  }
  else
  {
    v9 = *((_QWORD *)this + 3);
    v26 = v23;
    v27 = v24;
    v28 = v25;
    (*(void (__fastcall **)(__int64, struct _EVENT_DATA_DESCRIPTOR *, _QWORD, _QWORD, __int64))(*(_QWORD *)v9 + 248LL))(
      v9,
      &v26,
      v16,
      v15,
      v20);
  }
  MsgRelease(v20);
  std::string::~string(&v21);
  return 0;
}

```

## disassembly

```asm
0x18003a550  mov     [rsp-8+arg_10], rbx
0x18003a555  mov     [rsp-8+arg_18], rsi
0x18003a55a  push    rbp
0x18003a55b  push    rdi
0x18003a55c  push    r12
0x18003a55e  push    r13
0x18003a560  push    r14
0x18003a562  lea     rbp, [rsp-37h]
0x18003a567  sub     rsp, 0F0h
0x18003a56e  mov     rax, cs:__security_cookie
0x18003a575  xor     rax, rsp
0x18003a578  mov     [rbp+57h+var_30], rax
0x18003a57c  mov     rbx, rdx
0x18003a57f  mov     rdi, rcx
0x18003a582  xor     esi, esi
0x18003a584  mov     [rbp+57h+var_B8], esi
0x18003a587  mov     [rbp+57h+var_C8], esi
0x18003a58a  mov     [rbp+57h+var_BC], esi
0x18003a58d  mov     [rbp+57h+var_C4], esi
0x18003a590  mov     [rbp+57h+var_B0], rsi
0x18003a594  mov     eax, cs:dword_180082080
0x18003a59a  cmp     eax, 5
0x18003a59d  jbe     short loc_18003A5EC
0x18003a59f  mov     rcx, cs:qword_180082098
0x18003a5a6  mov     rax, cs:qword_180082090
0x18003a5ad  mov     edx, 400000h
0x18003a5b2  test    rdx, rax
0x18003a5b5  jz      short loc_18003A5EC
0x18003a5b7  mov     rax, rcx
0x18003a5ba  and     rax, rdx
0x18003a5bd  cmp     rax, rcx
0x18003a5c0  jnz     short loc_18003A5EC
0x18003a5c2  lea     rax, [rbp+57h+var_60]
0x18003a5c6  mov     [rsp+110h+var_E8], rax
0x18003a5cb  mov     dword ptr [rsp+110h+var_F0], 2
0x18003a5d3  xor     r9d, r9d
0x18003a5d6  xor     r8d, r8d
0x18003a5d9  lea     rdx, byte_18007586D
0x18003a5e0  lea     rcx, dword_180082080
0x18003a5e7  call    _tlgWriteTransfer_EventWriteTransfer
0x18003a5ec  lea     rdx, [rbp+57h+var_B8]
0x18003a5f0  mov     rcx, rbx
0x18003a5f3  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a5f8  lea     rdx, [rbp+57h+var_C8]
0x18003a5fc  mov     rcx, rbx
0x18003a5ff  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a604  lea     rdx, [rbp+57h+var_BC]
0x18003a608  mov     rcx, rbx
0x18003a60b  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a610  lea     rdx, [rbp+57h+var_C4]
0x18003a614  mov     rcx, rbx
0x18003a617  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a61c  mov     [rbp+57h+var_D0], sil
0x18003a620  lea     rdx, [rbp+57h+var_D0]
0x18003a624  mov     rcx, rbx
0x18003a627  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003a62c  movzx   r13d, [rbp+57h+var_D0]
0x18003a631  mov     r12, [rbx+10h]
0x18003a635  sub     r12, [rbx+8]
0x18003a639  mov     r14d, 4
0x18003a63f  mov     [rbp+57h+var_CC], esi
0x18003a642  lea     rdx, [rbp+57h+var_CC]
0x18003a646  mov     rcx, rbx
0x18003a649  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a64e  cmp     [rbp+57h+var_CC], esi
0x18003a651  jbe     short loc_18003A680
0x18003a653  mov     [rbp+57h+var_C0], 0
0x18003a65a  lea     rdx, [rbp+57h+var_C0]
0x18003a65e  mov     rcx, rbx
0x18003a661  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a666  mov     eax, [rbp+57h+var_C0]
0x18003a669  lea     r14d, [r14+rax*2]
0x18003a66d  add     r14d, 0Ch
0x18003a671  lea     rcx, [rax+8]
0x18003a675  add     [rbx+10h], rcx
0x18003a679  inc     esi
0x18003a67b  cmp     esi, [rbp+57h+var_CC]
0x18003a67e  jb      short loc_18003A653
0x18003a680  mov     rdx, [rbx+8]
0x18003a684  add     rdx, r12
0x18003a687  mov     [rbx+10h], rdx
0x18003a68b  xorps   xmm0, xmm0
0x18003a68e  movups  [rbp+57h+var_A8], xmm0
0x18003a692  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18003a69a  movdqu  [rbp+57h+var_98], xmm1
0x18003a69f  mov     byte ptr [rbp+57h+var_A8], 0
0x18003a6a3  mov     r8d, r14d
0x18003a6a6  lea     rdx, [rbp+57h+var_A8]
0x18003a6aa  mov     rcx, rbx
0x18003a6ad  call    ?extractString@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractString(std::string &,unsigned __int64,bool)
0x18003a6b2  lea     rcx, [rbp+57h+var_A8]
0x18003a6b6  cmp     qword ptr [rbp+57h+var_98+8], 0Fh
0x18003a6bb  cmova   rcx, qword ptr [rbp+57h+var_A8]
0x18003a6c0  lea     r8, [rbp+57h+var_B0]
0x18003a6c4  mov     edx, r14d
0x18003a6c7  call    cs:__imp_MsgBlobCreateShared
0x18003a6cd  mov     rcx, [rdi+8]
0x18003a6d1  mov     rax, [rcx]
0x18003a6d4  mov     r8d, [rbp+57h+var_BC]
0x18003a6d8  lea     rdx, [rbp+57h+var_88]
0x18003a6dc  mov     rax, [rax+38h]
0x18003a6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6e5  mov     rcx, [rdi+8]
0x18003a6e9  mov     rax, [rcx]
0x18003a6ec  mov     edx, [rbp+57h+var_B8]
0x18003a6ef  mov     rax, [rax+10h]
0x18003a6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6f8  mov     ecx, r13d
0x18003a6fb  sub     ecx, 1
0x18003a6fe  jz      short loc_18003A749
0x18003a700  cmp     ecx, 1
0x18003a703  jz      short loc_18003A749
0x18003a705  mov     rcx, [rdi+18h]
0x18003a709  movups  xmm0, [rbp+57h+var_88]
0x18003a70d  movaps  [rbp+57h+var_60], xmm0
0x18003a711  movups  xmm1, [rbp+57h+var_78]
0x18003a715  movaps  [rbp+57h+var_50], xmm1
0x18003a719  movsd   xmm0, [rbp+57h+var_68]
0x18003a71e  movsd   [rbp+57h+var_40], xmm0
0x18003a723  mov     rax, [rcx]
0x18003a726  mov     rdx, [rbp+57h+var_B0]
0x18003a72a  mov     [rsp+110h+var_F0], rdx
0x18003a72f  mov     r9d, [rbp+57h+var_C8]
0x18003a733  mov     r8d, [rbp+57h+var_C4]
0x18003a737  lea     rdx, [rbp+57h+var_60]
0x18003a73b  mov     rax, [rax+0F8h]
0x18003a742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a747  jmp     short loc_18003A795
0x18003a749  mov     rcx, [rdi+18h]
0x18003a74d  movups  xmm0, [rbp+57h+var_88]
0x18003a751  movaps  [rbp+57h+var_60], xmm0
0x18003a755  movups  xmm1, [rbp+57h+var_78]
0x18003a759  movaps  [rbp+57h+var_50], xmm1
0x18003a75d  movsd   xmm0, [rbp+57h+var_68]
0x18003a762  movsd   [rbp+57h+var_40], xmm0
0x18003a767  mov     rax, [rcx]
0x18003a76a  cmp     r13d, 1
0x18003a76e  setz    r8b
0x18003a772  mov     rdx, [rbp+57h+var_B0]
0x18003a776  mov     [rsp+110h+var_E8], rdx
0x18003a77b  mov     byte ptr [rsp+110h+var_F0], r8b
0x18003a780  mov     r9d, [rbp+57h+var_C8]
0x18003a784  mov     r8d, [rbp+57h+var_C4]
0x18003a788  lea     rdx, [rbp+57h+var_60]
0x18003a78c  mov     rax, [rax+58h]
0x18003a790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a795  mov     rcx, [rbp+57h+var_B0]
0x18003a799  call    cs:__imp_MsgRelease
0x18003a79f  nop
0x18003a7a0  lea     rcx, [rbp+57h+var_A8]
0x18003a7a4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003a7a9  xor     eax, eax
0x18003a7ab  mov     rcx, [rbp+57h+var_30]
0x18003a7af  xor     rcx, rsp; StackCookie
0x18003a7b2  call    __security_check_cookie
0x18003a7b7  lea     r11, [rsp+110h+var_20]
0x18003a7bf  mov     rbx, [r11+40h]
0x18003a7c3  mov     rsi, [r11+48h]
0x18003a7c7  mov     rsp, r11
0x18003a7ca  pop     r14
0x18003a7cc  pop     r13
0x18003a7ce  pop     r12
0x18003a7d0  pop     rdi
0x18003a7d1  pop     rbp
0x18003a7d2  retn
```
