# PduRecv_ToIRemoteTextInputClient::On_RDPTXT_SET_COMPOSITION_INFO_PDU(Gryps::FlexIBuffer *)

- ea: `0x18003a084`
- end: `0x18003a28b`
- name: `?On_RDPTXT_SET_COMPOSITION_INFO_PDU@PduRecv_ToIRemoteTextInputClient@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `519`
- prototype: `__int64 __fastcall(PduRecv_ToIRemoteTextInputClient *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800399d0`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180038d7c`
- `0x1800396e0`
- `0x18003a084`
- `0x18003b984`
- `0x180058010`

## import_xrefs

- `CoreMessaging!MsgStringCreateShared` at `0x18003a1d6`
- `CoreMessaging!MsgStringCreateShared` at `0x18003a1d6`
- `CoreMessaging!MsgRelease` at `0x18003a255`
- `CoreMessaging!MsgRelease` at `0x18003a255`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PduRecv_ToIRemoteTextInputClient::On_RDPTXT_SET_COMPOSITION_INFO_PDU(
        PduRecv_ToIRemoteTextInputClient *this,
        struct Gryps::FlexIBuffer *a2)
{
  int v4; // edi
  int v5; // ebx
  __int128 *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v12; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v13; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v14; // [rsp+4Ch] [rbp-5Dh] BYREF
  unsigned int v15; // [rsp+50h] [rbp-59h] BYREF
  unsigned int v16; // [rsp+54h] [rbp-55h] BYREF
  __int64 v17; // [rsp+58h] [rbp-51h] BYREF
  __int128 v18; // [rsp+60h] [rbp-49h] BYREF
  __m128i si128; // [rsp+70h] [rbp-39h]
  _OWORD v20[2]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-9h]
  struct _EVENT_DATA_DESCRIPTOR v22[2]; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v23; // [rsp+D0h] [rbp+27h]

  v14 = 0;
  v15 = 0;
  v13 = 0;
  v16 = 0;
  v12 = 0;
  v17 = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180082080, byte_180075800, 0, 0, 2u, v22);
  }
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v14);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v15);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v13);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v16);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v12);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, (_DWORD *)&v12 + 1);
  v4 = v12;
  v5 = HIDWORD(v12);
  LODWORD(v12) = 0;
  v18 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v18) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v12);
  Gryps::FlexIBuffer::extractUTF16String((__int64)a2, (char ***)&v18, (unsigned int)v12);
  v6 = &v18;
  if ( si128.m128i_i64[1] > 7uLL )
    v6 = (__int128 *)v18;
  MsgStringCreateShared(v6, (unsigned int)v12, &v17);
  (*(void (__fastcall **)(_QWORD, _OWORD *, _QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1), v20, v13);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), v14);
  v7 = *((_QWORD *)this + 3);
  v22[0] = (struct _EVENT_DATA_DESCRIPTOR)v20[0];
  v22[1] = (struct _EVENT_DATA_DESCRIPTOR)v20[1];
  v23 = v21;
  (*(void (__fastcall **)(__int64, struct _EVENT_DATA_DESCRIPTOR *, _QWORD, _QWORD, int, int, __int64))(*(_QWORD *)v7 + 216LL))(
    v7,
    v22,
    v16,
    v15,
    v4,
    v5,
    v17);
  MsgRelease(v17, v8, v9, v10);
  std::wstring::~wstring(&v18);
  return 0;
}

```

## disassembly

```asm
0x18003a084  mov     [rsp-8+arg_10], rbx
0x18003a089  mov     [rsp-8+arg_18], rsi
0x18003a08e  push    rbp
0x18003a08f  push    rdi
0x18003a090  push    r14
0x18003a092  lea     rbp, [rsp-47h]
0x18003a097  sub     rsp, 0F0h
0x18003a09e  mov     rax, cs:__security_cookie
0x18003a0a5  xor     rax, rsp
0x18003a0a8  mov     [rbp+57h+var_20], rax
0x18003a0ac  mov     rsi, rdx
0x18003a0af  mov     r14, rcx
0x18003a0b2  mov     [rbp+57h+var_B4], 0
0x18003a0b9  mov     [rbp+57h+var_B0], 0
0x18003a0c0  mov     [rbp+57h+var_B8], 0
0x18003a0c7  mov     [rbp+57h+var_AC], 0
0x18003a0ce  mov     [rbp+57h+var_C0], 0
0x18003a0d6  mov     [rbp+57h+var_A8], 0
0x18003a0de  mov     eax, cs:dword_180082080
0x18003a0e4  cmp     eax, 5
0x18003a0e7  jbe     short loc_18003A136
0x18003a0e9  mov     rcx, cs:qword_180082098
0x18003a0f0  mov     rax, cs:qword_180082090
0x18003a0f7  mov     edx, 400000h
0x18003a0fc  test    rdx, rax
0x18003a0ff  jz      short loc_18003A136
0x18003a101  mov     rax, rcx
0x18003a104  and     rax, rdx
0x18003a107  cmp     rax, rcx
0x18003a10a  jnz     short loc_18003A136
0x18003a10c  lea     rax, [rbp+57h+var_50]
0x18003a110  mov     [rsp+100h+var_D8], rax
0x18003a115  mov     [rsp+100h+var_E0], 2
0x18003a11d  xor     r9d, r9d
0x18003a120  xor     r8d, r8d
0x18003a123  lea     rdx, byte_180075800
0x18003a12a  lea     rcx, dword_180082080
0x18003a131  call    _tlgWriteTransfer_EventWriteTransfer
0x18003a136  lea     rdx, [rbp+57h+var_B4]
0x18003a13a  mov     rcx, rsi
0x18003a13d  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a142  lea     rdx, [rbp+57h+var_B0]
0x18003a146  mov     rcx, rsi
0x18003a149  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a14e  lea     rdx, [rbp+57h+var_B8]
0x18003a152  mov     rcx, rsi
0x18003a155  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a15a  lea     rdx, [rbp+57h+var_AC]
0x18003a15e  mov     rcx, rsi
0x18003a161  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a166  lea     rdx, [rbp+57h+var_C0]
0x18003a16a  mov     rcx, rsi
0x18003a16d  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a172  lea     rdx, [rbp+57h+var_C0+4]
0x18003a176  mov     rcx, rsi
0x18003a179  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a17e  mov     edi, dword ptr [rbp+57h+var_C0]
0x18003a181  mov     ebx, dword ptr [rbp+57h+var_C0+4]
0x18003a184  mov     dword ptr [rbp+57h+var_C0], 0
0x18003a18b  xorps   xmm0, xmm0
0x18003a18e  movups  [rbp+57h+var_A0], xmm0
0x18003a192  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003a19a  movdqu  [rbp+57h+var_90], xmm1
0x18003a19f  xor     eax, eax
0x18003a1a1  mov     word ptr [rbp+57h+var_A0], ax
0x18003a1a5  lea     rdx, [rbp+57h+var_C0]
0x18003a1a9  mov     rcx, rsi
0x18003a1ac  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a1b1  mov     r8d, dword ptr [rbp+57h+var_C0]
0x18003a1b5  lea     rdx, [rbp+57h+var_A0]
0x18003a1b9  mov     rcx, rsi
0x18003a1bc  call    ?extractUTF16String@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractUTF16String(std::wstring &,unsigned __int64,bool)
0x18003a1c1  lea     rcx, [rbp+57h+var_A0]
0x18003a1c5  cmp     qword ptr [rbp+57h+var_90+8], 7
0x18003a1ca  cmova   rcx, qword ptr [rbp+57h+var_A0]
0x18003a1cf  lea     r8, [rbp+57h+var_A8]
0x18003a1d3  mov     edx, dword ptr [rbp+57h+var_C0]
0x18003a1d6  call    cs:__imp_MsgStringCreateShared
0x18003a1dc  mov     rcx, [r14+8]
0x18003a1e0  mov     rax, [rcx]
0x18003a1e3  mov     r8d, [rbp+57h+var_B8]
0x18003a1e7  lea     rdx, [rbp+57h+var_80]
0x18003a1eb  mov     rax, [rax+38h]
0x18003a1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1f4  mov     rcx, [r14+8]
0x18003a1f8  mov     rax, [rcx]
0x18003a1fb  mov     edx, [rbp+57h+var_B4]
0x18003a1fe  mov     rax, [rax+10h]
0x18003a202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a207  mov     rcx, [r14+18h]
0x18003a20b  movups  xmm0, [rbp+57h+var_80]
0x18003a20f  movaps  [rbp+57h+var_50], xmm0
0x18003a213  movups  xmm1, [rbp+57h+var_70]
0x18003a217  movaps  [rbp+57h+var_40], xmm1
0x18003a21b  movsd   xmm0, [rbp+57h+var_60]
0x18003a220  movsd   [rbp+57h+var_30], xmm0
0x18003a225  mov     rax, [rcx]
0x18003a228  mov     rdx, [rbp+57h+var_A8]
0x18003a22c  mov     [rsp+100h+var_D0], rdx
0x18003a231  mov     dword ptr [rsp+100h+var_D8], ebx
0x18003a235  mov     [rsp+100h+var_E0], edi
0x18003a239  mov     r9d, [rbp+57h+var_B0]
0x18003a23d  mov     r8d, [rbp+57h+var_AC]
0x18003a241  lea     rdx, [rbp+57h+var_50]
0x18003a245  mov     rax, [rax+0D8h]
0x18003a24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a251  mov     rcx, [rbp+57h+var_A8]
0x18003a255  call    cs:__imp_MsgRelease
0x18003a25b  nop
0x18003a25c  lea     rcx, [rbp+57h+var_A0]
0x18003a260  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a265  xor     eax, eax
0x18003a267  mov     rcx, [rbp+57h+var_20]
0x18003a26b  xor     rcx, rsp; StackCookie
0x18003a26e  call    __security_check_cookie
0x18003a273  lea     r11, [rsp+100h+var_10]
0x18003a27b  mov     rbx, [r11+30h]
0x18003a27f  mov     rsi, [r11+38h]
0x18003a283  mov     rsp, r11
0x18003a286  pop     r14
0x18003a288  pop     rdi
0x18003a289  pop     rbp
0x18003a28a  retn
```
