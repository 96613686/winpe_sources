# PduRecv_ToIRemoteCoreInputView::On_RDPTXT_OCCLUDING_VIEWS_PDU(Gryps::FlexIBuffer *)

- ea: `0x18003c168`
- end: `0x18003c2ab`
- name: `?On_RDPTXT_OCCLUDING_VIEWS_PDU@PduRecv_ToIRemoteCoreInputView@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(PduRecv_ToIRemoteCoreInputView *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003c0d0`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180038c0c`
- `0x180038d7c`
- `0x180039678`
- `0x18003b8a4`
- `0x18003c168`
- `0x180058010`

## import_xrefs

- `CoreMessaging!MsgBlobCreateShared` at `0x18003c242`
- `CoreMessaging!MsgBlobCreateShared` at `0x18003c242`
- `CoreMessaging!MsgRelease` at `0x18003c278`
- `CoreMessaging!MsgRelease` at `0x18003c278`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PduRecv_ToIRemoteCoreInputView::On_RDPTXT_OCCLUDING_VIEWS_PDU(
        PduRecv_ToIRemoteCoreInputView *this,
        struct Gryps::FlexIBuffer *a2)
{
  __int128 *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  _BYTE v10[4]; // [rsp+38h] [rbp-9h] BYREF
  unsigned int v11; // [rsp+3Ch] [rbp-5h] BYREF
  __int64 v12; // [rsp+40h] [rbp-1h] BYREF
  __int128 v13; // [rsp+48h] [rbp+7h] BYREF
  __m128i si128; // [rsp+58h] [rbp+17h]
  _BYTE v15[32]; // [rsp+68h] [rbp+27h] BYREF

  v12 = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_180082080, &unk_180075AF1, 0, 0, 2, v15);
  }
  v11 = 0;
  v13 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v13) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v11);
  Gryps::FlexIBuffer::extractString((__int64)a2, &v13, v11);
  v4 = &v13;
  if ( si128.m128i_i64[1] > 0xFuLL )
    v4 = (__int128 *)v13;
  MsgBlobCreateShared(v4, v11, &v12);
  v10[0] = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, v10);
  LOBYTE(v5) = v10[0] != 0;
  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3), v12, v5);
  MsgRelease(v12, v6, v7, v8);
  std::string::~string(&v13);
  return 0;
}

```

## disassembly

```asm
0x18003c168  mov     r11, rsp
0x18003c16b  mov     [r11+18h], rbx
0x18003c16f  mov     [r11+20h], rdi
0x18003c173  push    rbp
0x18003c174  lea     rbp, [r11-5Fh]
0x18003c178  sub     rsp, 90h
0x18003c17f  mov     rax, cs:__security_cookie
0x18003c186  xor     rax, rsp
0x18003c189  mov     [rbp+57h+var_10], rax
0x18003c18d  mov     rbx, rdx
0x18003c190  mov     rdi, rcx
0x18003c193  mov     [rbp+57h+var_58], 0
0x18003c19b  mov     eax, cs:dword_180082080
0x18003c1a1  cmp     eax, 5
0x18003c1a4  jbe     short loc_18003C1F2
0x18003c1a6  mov     rdx, cs:qword_180082098
0x18003c1ad  mov     rax, cs:qword_180082090
0x18003c1b4  mov     ecx, 400000h
0x18003c1b9  test    rcx, rax
0x18003c1bc  jz      short loc_18003C1F2
0x18003c1be  mov     rax, rdx
0x18003c1c1  and     rax, rcx
0x18003c1c4  cmp     rax, rdx
0x18003c1c7  jnz     short loc_18003C1F2
0x18003c1c9  lea     rax, [rbp+57h+var_30]
0x18003c1cd  mov     [r11-70h], rax
0x18003c1d1  mov     [rsp+90h+var_70], 2
0x18003c1d9  xor     r9d, r9d
0x18003c1dc  xor     r8d, r8d
0x18003c1df  lea     rdx, unk_180075AF1
0x18003c1e6  lea     rcx, dword_180082080
0x18003c1ed  call    _tlgWriteTransfer_EventWriteTransfer
0x18003c1f2  mov     [rbp+57h+var_5C], 0
0x18003c1f9  xorps   xmm0, xmm0
0x18003c1fc  movups  [rbp+57h+var_50], xmm0
0x18003c200  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18003c208  movdqu  [rbp+57h+var_40], xmm1
0x18003c20d  mov     byte ptr [rbp+57h+var_50], 0
0x18003c211  lea     rdx, [rbp+57h+var_5C]
0x18003c215  mov     rcx, rbx
0x18003c218  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003c21d  mov     r8d, [rbp+57h+var_5C]
0x18003c221  lea     rdx, [rbp+57h+var_50]
0x18003c225  mov     rcx, rbx
0x18003c228  call    ?extractString@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractString(std::string &,unsigned __int64,bool)
0x18003c22d  lea     rcx, [rbp+57h+var_50]
0x18003c231  cmp     qword ptr [rbp+57h+var_40+8], 0Fh
0x18003c236  cmova   rcx, qword ptr [rbp+57h+var_50]
0x18003c23b  lea     r8, [rbp+57h+var_58]
0x18003c23f  mov     edx, [rbp+57h+var_5C]
0x18003c242  call    cs:__imp_MsgBlobCreateShared
0x18003c248  mov     [rbp+57h+var_60], 0
0x18003c24c  lea     rdx, [rbp+57h+var_60]
0x18003c250  mov     rcx, rbx
0x18003c253  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003c258  cmp     [rbp+57h+var_60], 0
0x18003c25c  setnz   r8b
0x18003c260  mov     rcx, [rdi+18h]
0x18003c264  mov     rax, [rcx]
0x18003c267  mov     rdx, [rbp+57h+var_58]
0x18003c26b  mov     rax, [rax+30h]
0x18003c26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c274  mov     rcx, [rbp+57h+var_58]
0x18003c278  call    cs:__imp_MsgRelease
0x18003c27e  nop
0x18003c27f  lea     rcx, [rbp+57h+var_50]
0x18003c283  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003c288  xor     eax, eax
0x18003c28a  mov     rcx, [rbp+57h+var_10]
0x18003c28e  xor     rcx, rsp; StackCookie
0x18003c291  call    __security_check_cookie
0x18003c296  lea     r11, [rsp+90h+var_s0]
0x18003c29e  mov     rbx, [r11+20h]
0x18003c2a2  mov     rdi, [r11+28h]
0x18003c2a6  mov     rsp, r11
0x18003c2a9  pop     rbp
0x18003c2aa  retn
```
