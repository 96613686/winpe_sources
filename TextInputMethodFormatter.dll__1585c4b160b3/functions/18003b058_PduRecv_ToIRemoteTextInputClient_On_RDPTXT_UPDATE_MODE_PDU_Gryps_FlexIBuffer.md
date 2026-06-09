# PduRecv_ToIRemoteTextInputClient::On_RDPTXT_UPDATE_MODE_PDU(Gryps::FlexIBuffer *)

- ea: `0x18003b058`
- end: `0x18003b2e6`
- name: `?On_RDPTXT_UPDATE_MODE_PDU@PduRecv_ToIRemoteTextInputClient@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `654`
- prototype: `__int64 __fastcall(PduRecv_ToIRemoteTextInputClient *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1800399d0`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180038c0c`
- `0x180038d7c`
- `0x1800396e0`
- `0x18003b058`
- `0x18003b984`
- `0x180058010`

## import_xrefs

- `CoreMessaging!MsgStringCreateShared` at `0x18003b1c8`
- `CoreMessaging!MsgStringCreateShared` at `0x18003b1c8`
- `CoreMessaging!MsgRelease` at `0x18003b2b1`
- `CoreMessaging!MsgRelease` at `0x18003b2b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PduRecv_ToIRemoteTextInputClient::On_RDPTXT_UPDATE_MODE_PDU(
        PduRecv_ToIRemoteTextInputClient *this,
        struct Gryps::FlexIBuffer *a2)
{
  unsigned int v4; // edi
  bool v5; // r14
  __int64 v6; // rbx
  __int128 *v7; // rcx
  __int64 v8; // rdx
  __int64 *v9; // rcx
  __int64 v10; // rax
  void (__fastcall *v11)(__int64 *, struct _EVENT_DATA_DESCRIPTOR *, _QWORD, _QWORD, int, __int64); // rax
  int v13; // [rsp+20h] [rbp-99h]
  __int64 v14; // [rsp+28h] [rbp-91h]
  _BYTE v15[4]; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v16; // [rsp+44h] [rbp-75h] BYREF
  unsigned int v17; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v18; // [rsp+4Ch] [rbp-6Dh] BYREF
  unsigned int v19; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v20; // [rsp+54h] [rbp-65h] BYREF
  __int64 v21; // [rsp+58h] [rbp-61h] BYREF
  __int64 v22; // [rsp+60h] [rbp-59h] BYREF
  __int128 v23; // [rsp+68h] [rbp-51h] BYREF
  __m128i si128; // [rsp+78h] [rbp-41h]
  _OWORD v25[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-11h]
  struct _EVENT_DATA_DESCRIPTOR v27[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v28; // [rsp+D0h] [rbp+17h]

  v19 = 0;
  v20 = 0;
  v17 = 0;
  v21 = 0;
  v22 = 0;
  v18 = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180082080, (unsigned __int8 *)byte_180075653, 0, 0, 2u, v27);
  }
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v19);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v20);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v17);
  v16 = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v16);
  v4 = v16;
  v15[0] = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, v15);
  v5 = v15[0] != 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v21);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, (char *)&v21 + 4);
  v6 = v21;
  v16 = 0;
  v23 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v23) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v16);
  Gryps::FlexIBuffer::extractUTF16String(a2, &v23, v16);
  v7 = &v23;
  if ( si128.m128i_i64[1] > 7uLL )
    v7 = (__int128 *)v23;
  MsgStringCreateShared(v7, v16, &v22);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v18);
  (*(void (__fastcall **)(_QWORD, _OWORD *, _QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1), v25, v19);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), v20);
  v9 = (__int64 *)*((_QWORD *)this + 3);
  if ( (v4 & 0x10) == v4 )
  {
    v14 = v6;
    LOBYTE(v13) = v5;
    v11 = *(void (__fastcall **)(__int64 *, struct _EVENT_DATA_DESCRIPTOR *, _QWORD, _QWORD, int, __int64))(*v9 + 96);
    goto LABEL_14;
  }
  if ( (v4 & 1) == v4 )
  {
    LOBYTE(v8) = v5;
    (*(void (__fastcall **)(__int64 *, __int64, __int64))(*v9 + 208))(v9, v8, v22);
    goto LABEL_15;
  }
  v10 = *v9;
  if ( (v4 & 2) != v4 )
  {
    LOBYTE(v14) = (v4 & 8) != 0;
    LOBYTE(v13) = (v4 & 4) != 0;
    v11 = *(void (__fastcall **)(__int64 *, struct _EVENT_DATA_DESCRIPTOR *, _QWORD, _QWORD, int, __int64))(v10 + 104);
LABEL_14:
    v27[0] = (struct _EVENT_DATA_DESCRIPTOR)v25[0];
    v27[1] = (struct _EVENT_DATA_DESCRIPTOR)v25[1];
    v28 = v26;
    v11(v9, v27, v18, v17, v13, v14);
    goto LABEL_15;
  }
  (*(void (__fastcall **)(__int64 *, _QWORD))(v10 + 192))(v9, (unsigned int)v5 + 1);
LABEL_15:
  MsgRelease(v22);
  std::wstring::~wstring(&v23);
  return 0;
}

```

## disassembly

```asm
0x18003b058  mov     [rsp-8+arg_10], rbx
0x18003b05d  push    rbp
0x18003b05e  push    rsi
0x18003b05f  push    rdi
0x18003b060  push    r14
0x18003b062  push    r15
0x18003b064  lea     rbp, [rsp-37h]
0x18003b069  sub     rsp, 0F0h
0x18003b070  mov     rax, cs:__security_cookie
0x18003b077  xor     rax, rsp
0x18003b07a  mov     [rbp+57h+var_30], rax
0x18003b07e  mov     r15, rdx
0x18003b081  mov     rsi, rcx
0x18003b084  mov     [rbp+57h+var_C0], 0
0x18003b08b  mov     [rbp+57h+var_BC], 0
0x18003b092  mov     [rbp+57h+var_C8], 0
0x18003b099  mov     [rbp+57h+var_B8], 0
0x18003b0a1  mov     [rbp+57h+var_B0], 0
0x18003b0a9  mov     [rbp+57h+var_C4], 0
0x18003b0b0  mov     eax, cs:dword_180082080
0x18003b0b6  cmp     eax, 5
0x18003b0b9  jbe     short loc_18003B108
0x18003b0bb  mov     rcx, cs:qword_180082098
0x18003b0c2  mov     rax, cs:qword_180082090
0x18003b0c9  mov     edx, 400000h
0x18003b0ce  test    rdx, rax
0x18003b0d1  jz      short loc_18003B108
0x18003b0d3  mov     rax, rcx
0x18003b0d6  and     rax, rdx
0x18003b0d9  cmp     rax, rcx
0x18003b0dc  jnz     short loc_18003B108
0x18003b0de  lea     rax, [rbp+57h+var_60]
0x18003b0e2  mov     [rsp+110h+var_E8], rax
0x18003b0e7  mov     [rsp+110h+var_F0], 2
0x18003b0ef  xor     r9d, r9d
0x18003b0f2  xor     r8d, r8d
0x18003b0f5  lea     rdx, byte_180075653
0x18003b0fc  lea     rcx, dword_180082080
0x18003b103  call    _tlgWriteTransfer_EventWriteTransfer
0x18003b108  lea     rdx, [rbp+57h+var_C0]
0x18003b10c  mov     rcx, r15
0x18003b10f  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b114  lea     rdx, [rbp+57h+var_BC]
0x18003b118  mov     rcx, r15
0x18003b11b  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b120  lea     rdx, [rbp+57h+var_C8]
0x18003b124  mov     rcx, r15
0x18003b127  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b12c  mov     [rbp+57h+var_CC], 0
0x18003b133  lea     rdx, [rbp+57h+var_CC]
0x18003b137  mov     rcx, r15
0x18003b13a  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b13f  mov     edi, [rbp+57h+var_CC]
0x18003b142  mov     [rbp+57h+var_D0], 0
0x18003b146  lea     rdx, [rbp+57h+var_D0]
0x18003b14a  mov     rcx, r15
0x18003b14d  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003b152  cmp     [rbp+57h+var_D0], 0
0x18003b156  setnz   r14b
0x18003b15a  lea     rdx, [rbp+57h+var_B8]
0x18003b15e  mov     rcx, r15
0x18003b161  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b166  lea     rdx, [rbp+57h+var_B8+4]
0x18003b16a  mov     rcx, r15
0x18003b16d  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b172  mov     rbx, [rbp+57h+var_B8]
0x18003b176  mov     [rbp+57h+var_CC], 0
0x18003b17d  xorps   xmm0, xmm0
0x18003b180  movups  [rbp+57h+var_A8], xmm0
0x18003b184  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003b18c  movdqu  [rbp+57h+var_98], xmm1
0x18003b191  xor     eax, eax
0x18003b193  mov     word ptr [rbp+57h+var_A8], ax
0x18003b197  lea     rdx, [rbp+57h+var_CC]
0x18003b19b  mov     rcx, r15
0x18003b19e  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b1a3  mov     r8d, [rbp+57h+var_CC]
0x18003b1a7  lea     rdx, [rbp+57h+var_A8]
0x18003b1ab  mov     rcx, r15
0x18003b1ae  call    ?extractUTF16String@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractUTF16String(std::wstring &,unsigned __int64,bool)
0x18003b1b3  lea     rcx, [rbp+57h+var_A8]
0x18003b1b7  cmp     qword ptr [rbp+57h+var_98+8], 7
0x18003b1bc  cmova   rcx, qword ptr [rbp+57h+var_A8]
0x18003b1c1  lea     r8, [rbp+57h+var_B0]
0x18003b1c5  mov     edx, [rbp+57h+var_CC]
0x18003b1c8  call    cs:__imp_MsgStringCreateShared
0x18003b1ce  lea     rdx, [rbp+57h+var_C4]
0x18003b1d2  mov     rcx, r15
0x18003b1d5  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b1da  mov     rcx, [rsi+8]
0x18003b1de  mov     rax, [rcx]
0x18003b1e1  mov     r8d, [rbp+57h+var_C0]
0x18003b1e5  lea     rdx, [rbp+57h+var_88]
0x18003b1e9  mov     rax, [rax+38h]
0x18003b1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1f2  mov     rcx, [rsi+8]
0x18003b1f6  mov     rax, [rcx]
0x18003b1f9  mov     edx, [rbp+57h+var_BC]
0x18003b1fc  mov     rax, [rax+10h]
0x18003b200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b205  mov     eax, edi
0x18003b207  and     eax, 10h
0x18003b20a  mov     rcx, [rsi+18h]
0x18003b20e  cmp     eax, edi
0x18003b210  jz      short loc_18003B271
0x18003b212  mov     eax, edi
0x18003b214  and     eax, 1
0x18003b217  cmp     eax, edi
0x18003b219  jz      short loc_18003B259
0x18003b21b  mov     eax, edi
0x18003b21d  and     eax, 2
0x18003b220  cmp     eax, edi
0x18003b222  mov     rax, [rcx]
0x18003b225  jnz     short loc_18003B23B
0x18003b227  movzx   edx, r14b
0x18003b22b  inc     edx
0x18003b22d  mov     rax, [rax+0C0h]
0x18003b234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b239  jmp     short loc_18003B2AD
0x18003b23b  mov     edx, edi
0x18003b23d  shr     edx, 2
0x18003b240  and     dl, 1
0x18003b243  shr     edi, 3
0x18003b246  and     dil, 1
0x18003b24a  mov     byte ptr [rsp+110h+var_E8], dil
0x18003b24f  mov     byte ptr [rsp+110h+var_F0], dl
0x18003b253  mov     rax, [rax+68h]
0x18003b257  jmp     short loc_18003B282
0x18003b259  mov     rax, [rcx]
0x18003b25c  mov     r8, [rbp+57h+var_B0]
0x18003b260  mov     dl, r14b
0x18003b263  mov     rax, [rax+0D0h]
0x18003b26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b26f  jmp     short loc_18003B2AD
0x18003b271  mov     rax, [rcx]
0x18003b274  mov     [rsp+110h+var_E8], rbx
0x18003b279  mov     byte ptr [rsp+110h+var_F0], r14b
0x18003b27e  mov     rax, [rax+60h]
0x18003b282  movups  xmm0, [rbp+57h+var_88]
0x18003b286  movaps  [rbp+57h+var_60], xmm0
0x18003b28a  movups  xmm1, [rbp+57h+var_78]
0x18003b28e  movsd   xmm0, [rbp+57h+var_68]
0x18003b293  movaps  [rbp+57h+var_50], xmm1
0x18003b297  movsd   [rbp+57h+var_40], xmm0
0x18003b29c  mov     r9d, [rbp+57h+var_C8]
0x18003b2a0  mov     r8d, [rbp+57h+var_C4]
0x18003b2a4  lea     rdx, [rbp+57h+var_60]
0x18003b2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2ad  mov     rcx, [rbp+57h+var_B0]
0x18003b2b1  call    cs:__imp_MsgRelease
0x18003b2b7  nop
0x18003b2b8  lea     rcx, [rbp+57h+var_A8]
0x18003b2bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b2c1  xor     eax, eax
0x18003b2c3  mov     rcx, [rbp+57h+var_30]
0x18003b2c7  xor     rcx, rsp; StackCookie
0x18003b2ca  call    __security_check_cookie
0x18003b2cf  mov     rbx, [rsp+110h+arg_10]
0x18003b2d7  add     rsp, 0F0h
0x18003b2de  pop     r15
0x18003b2e0  pop     r14
0x18003b2e2  pop     rdi
0x18003b2e3  pop     rsi
0x18003b2e4  pop     rbp
0x18003b2e5  retn
```
