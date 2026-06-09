# PduRecv_ToIRemoteTextInputClient::On_RDPTXT_RECONVERSION_CANDIDATES_PDU(Gryps::FlexIBuffer *)

- ea: `0x180039ee8`
- end: `0x18003a07c`
- name: `?On_RDPTXT_RECONVERSION_CANDIDATES_PDU@PduRecv_ToIRemoteTextInputClient@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(PduRecv_ToIRemoteTextInputClient *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800399d0`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180038d7c`
- `0x180039678`
- `0x180039ee8`
- `0x18003b8a4`
- `0x180058010`

## import_xrefs

- `CoreMessaging!MsgBlobCreateShared` at `0x180039fe4`
- `CoreMessaging!MsgBlobCreateShared` at `0x180039fe4`
- `CoreMessaging!MsgRelease` at `0x18003a049`
- `CoreMessaging!MsgRelease` at `0x18003a049`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PduRecv_ToIRemoteTextInputClient::On_RDPTXT_RECONVERSION_CANDIDATES_PDU(
        PduRecv_ToIRemoteTextInputClient *this,
        struct Gryps::FlexIBuffer *a2)
{
  __int128 *v4; // rcx
  unsigned int v6; // [rsp+38h] [rbp-19h] BYREF
  unsigned int v7; // [rsp+3Ch] [rbp-15h] BYREF
  unsigned int v8; // [rsp+40h] [rbp-11h] BYREF
  __int64 v9; // [rsp+48h] [rbp-9h] BYREF
  __int64 v10; // [rsp+50h] [rbp-1h] BYREF
  __int128 v11; // [rsp+58h] [rbp+7h] BYREF
  __m128i si128; // [rsp+68h] [rbp+17h]
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+78h] [rbp+27h] BYREF

  v7 = 0;
  v10 = 0;
  v8 = 0;
  v9 = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180082080, (unsigned __int8 *)&dword_180075724, 0, 0, 2u, &v13);
  }
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v7);
  v6 = 0;
  v11 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v11) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v6);
  Gryps::FlexIBuffer::extractString(a2, &v11, v6);
  v4 = &v11;
  if ( si128.m128i_i64[1] > 0xFuLL )
    v4 = (__int128 *)v11;
  MsgBlobCreateShared(v4, v6, &v10);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v8);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v9);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, (char *)&v9 + 4);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), v7);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 3) + 56LL))(
    *((_QWORD *)this + 3),
    v8,
    (unsigned int)v9,
    HIDWORD(v9),
    v10);
  MsgRelease(v10);
  std::string::~string(&v11);
  return 0;
}

```

## disassembly

```asm
0x180039ee8  mov     r11, rsp
0x180039eeb  mov     [r11+18h], rbx
0x180039eef  mov     [r11+20h], rdi
0x180039ef3  push    rbp
0x180039ef4  lea     rbp, [r11-5Fh]
0x180039ef8  sub     rsp, 0A0h
0x180039eff  mov     rax, cs:__security_cookie
0x180039f06  xor     rax, rsp
0x180039f09  mov     [rbp+57h+var_10], rax
0x180039f0d  mov     rbx, rdx
0x180039f10  mov     rdi, rcx
0x180039f13  mov     [rbp+57h+var_6C], 0
0x180039f1a  mov     [rbp+57h+var_58], 0
0x180039f22  mov     [rbp+57h+var_68], 0
0x180039f29  mov     [rbp+57h+var_60], 0
0x180039f31  mov     eax, cs:dword_180082080
0x180039f37  cmp     eax, 5
0x180039f3a  jbe     short loc_180039F88
0x180039f3c  mov     rcx, cs:qword_180082098
0x180039f43  mov     rax, cs:qword_180082090
0x180039f4a  mov     edx, 400000h
0x180039f4f  test    rdx, rax
0x180039f52  jz      short loc_180039F88
0x180039f54  mov     rax, rcx
0x180039f57  and     rax, rdx
0x180039f5a  cmp     rax, rcx
0x180039f5d  jnz     short loc_180039F88
0x180039f5f  lea     rax, [rbp+57h+var_30]
0x180039f63  mov     [r11-80h], rax
0x180039f67  mov     dword ptr [rsp+0A0h+var_80], 2
0x180039f6f  xor     r9d, r9d
0x180039f72  xor     r8d, r8d
0x180039f75  lea     rdx, dword_180075724
0x180039f7c  lea     rcx, dword_180082080
0x180039f83  call    _tlgWriteTransfer_EventWriteTransfer
0x180039f88  lea     rdx, [rbp+57h+var_6C]
0x180039f8c  mov     rcx, rbx
0x180039f8f  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180039f94  mov     [rbp+57h+var_70], 0
0x180039f9b  xorps   xmm0, xmm0
0x180039f9e  movups  [rbp+57h+var_50], xmm0
0x180039fa2  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180039faa  movdqu  [rbp+57h+var_40], xmm1
0x180039faf  mov     byte ptr [rbp+57h+var_50], 0
0x180039fb3  lea     rdx, [rbp+57h+var_70]
0x180039fb7  mov     rcx, rbx
0x180039fba  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180039fbf  mov     r8d, [rbp+57h+var_70]
0x180039fc3  lea     rdx, [rbp+57h+var_50]
0x180039fc7  mov     rcx, rbx
0x180039fca  call    ?extractString@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractString(std::string &,unsigned __int64,bool)
0x180039fcf  lea     rcx, [rbp+57h+var_50]
0x180039fd3  cmp     qword ptr [rbp+57h+var_40+8], 0Fh
0x180039fd8  cmova   rcx, qword ptr [rbp+57h+var_50]
0x180039fdd  lea     r8, [rbp+57h+var_58]
0x180039fe1  mov     edx, [rbp+57h+var_70]
0x180039fe4  call    cs:__imp_MsgBlobCreateShared
0x180039fea  lea     rdx, [rbp+57h+var_68]
0x180039fee  mov     rcx, rbx
0x180039ff1  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180039ff6  lea     rdx, [rbp+57h+var_60]
0x180039ffa  mov     rcx, rbx
0x180039ffd  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a002  lea     rdx, [rbp+57h+var_60+4]
0x18003a006  mov     rcx, rbx
0x18003a009  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003a00e  mov     rcx, [rdi+8]
0x18003a012  mov     rax, [rcx]
0x18003a015  mov     edx, [rbp+57h+var_6C]
0x18003a018  mov     rax, [rax+10h]
0x18003a01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a021  mov     rcx, [rdi+18h]
0x18003a025  mov     rax, [rcx]
0x18003a028  mov     rdx, [rbp+57h+var_58]
0x18003a02c  mov     [rsp+0A0h+var_80], rdx
0x18003a031  mov     r9d, dword ptr [rbp+57h+var_60+4]
0x18003a035  mov     r8d, dword ptr [rbp+57h+var_60]
0x18003a039  mov     edx, [rbp+57h+var_68]
0x18003a03c  mov     rax, [rax+38h]
0x18003a040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a045  mov     rcx, [rbp+57h+var_58]
0x18003a049  call    cs:__imp_MsgRelease
0x18003a04f  nop
0x18003a050  lea     rcx, [rbp+57h+var_50]
0x18003a054  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18003a059  xor     eax, eax
0x18003a05b  mov     rcx, [rbp+57h+var_10]
0x18003a05f  xor     rcx, rsp; StackCookie
0x18003a062  call    __security_check_cookie
0x18003a067  lea     r11, [rsp+0A0h+var_s0]
0x18003a06f  mov     rbx, [r11+20h]
0x18003a073  mov     rdi, [r11+28h]
0x18003a077  mov     rsp, r11
0x18003a07a  pop     rbp
0x18003a07b  retn
```
