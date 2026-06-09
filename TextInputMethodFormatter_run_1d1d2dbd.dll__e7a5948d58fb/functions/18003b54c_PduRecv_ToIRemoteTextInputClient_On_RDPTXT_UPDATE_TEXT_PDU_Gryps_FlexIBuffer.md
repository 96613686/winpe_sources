# PduRecv_ToIRemoteTextInputClient::On_RDPTXT_UPDATE_TEXT_PDU(Gryps::FlexIBuffer *)

- ea: `0x18003b54c`
- end: `0x18003b750`
- name: `?On_RDPTXT_UPDATE_TEXT_PDU@PduRecv_ToIRemoteTextInputClient@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(PduRecv_ToIRemoteTextInputClient *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800399d0`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180038d7c`
- `0x1800396e0`
- `0x18003b54c`
- `0x18003b984`
- `0x180058010`

## import_xrefs

- `CoreMessaging!MsgStringCreateShared` at `0x18003b69b`
- `CoreMessaging!MsgStringCreateShared` at `0x18003b69b`
- `CoreMessaging!MsgRelease` at `0x18003b71d`
- `CoreMessaging!MsgRelease` at `0x18003b71d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PduRecv_ToIRemoteTextInputClient::On_RDPTXT_UPDATE_TEXT_PDU(
        PduRecv_ToIRemoteTextInputClient *this,
        struct Gryps::FlexIBuffer *a2)
{
  __int128 *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v10; // [rsp+40h] [rbp-59h] BYREF
  unsigned int v11; // [rsp+44h] [rbp-55h] BYREF
  unsigned int v12; // [rsp+48h] [rbp-51h] BYREF
  int v13; // [rsp+4Ch] [rbp-4Dh] BYREF
  int v14; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v15; // [rsp+54h] [rbp-45h] BYREF
  unsigned int v16; // [rsp+58h] [rbp-41h] BYREF
  __int64 v17; // [rsp+60h] [rbp-39h] BYREF
  __int128 v18; // [rsp+68h] [rbp-31h] BYREF
  __m128i si128; // [rsp+78h] [rbp-21h]
  _OWORD v20[2]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v21; // [rsp+A8h] [rbp+Fh]
  struct _EVENT_DATA_DESCRIPTOR v22[2]; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v23; // [rsp+D0h] [rbp+37h]

  v12 = 0;
  v15 = 0;
  v11 = 0;
  v16 = 0;
  v14 = 0;
  v13 = 0;
  v17 = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180082080, byte_180075A16, 0, 0, 2u, v22);
  }
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v12);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v15);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v11);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v16);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v14);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v13);
  v10 = 0;
  v18 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v18) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v10);
  Gryps::FlexIBuffer::extractUTF16String((__int64)a2, (char ***)&v18, v10);
  v4 = &v18;
  if ( si128.m128i_i64[1] > 7uLL )
    v4 = (__int128 *)v18;
  MsgStringCreateShared(v4, v10, &v17);
  (*(void (__fastcall **)(_QWORD, _OWORD *, _QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1), v20, v11);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), v12);
  v5 = *((_QWORD *)this + 3);
  v22[0] = (struct _EVENT_DATA_DESCRIPTOR)v20[0];
  v22[1] = (struct _EVENT_DATA_DESCRIPTOR)v20[1];
  v23 = v21;
  (*(void (__fastcall **)(__int64, struct _EVENT_DATA_DESCRIPTOR *, _QWORD, _QWORD, int, int, __int64))(*(_QWORD *)v5 + 40LL))(
    v5,
    v22,
    v16,
    v15,
    v14,
    v13,
    v17);
  MsgRelease(v17, v6, v7, v8);
  std::wstring::~wstring(&v18);
  return 0;
}

```

## disassembly

```asm
0x18003b54c  mov     [rsp-8+arg_10], rbx
0x18003b551  mov     [rsp-8+arg_18], rdi
0x18003b556  push    rbp
0x18003b557  lea     rbp, [rsp-57h]
0x18003b55c  sub     rsp, 0F0h
0x18003b563  mov     rax, cs:__security_cookie
0x18003b56a  xor     rax, rsp
0x18003b56d  mov     [rbp+57h+var_10], rax
0x18003b571  mov     rbx, rdx
0x18003b574  mov     rdi, rcx
0x18003b577  mov     [rbp+57h+var_A8], 0
0x18003b57e  mov     [rbp+57h+var_9C], 0
0x18003b585  mov     [rbp+57h+var_AC], 0
0x18003b58c  mov     [rbp+57h+var_98], 0
0x18003b593  mov     [rbp+57h+var_A0], 0
0x18003b59a  mov     [rbp+57h+var_A4], 0
0x18003b5a1  mov     [rbp+57h+var_90], 0
0x18003b5a9  mov     eax, cs:dword_180082080
0x18003b5af  cmp     eax, 5
0x18003b5b2  jbe     short loc_18003B601
0x18003b5b4  mov     rcx, cs:qword_180082098
0x18003b5bb  mov     rax, cs:qword_180082090
0x18003b5c2  mov     edx, 400000h
0x18003b5c7  test    rdx, rax
0x18003b5ca  jz      short loc_18003B601
0x18003b5cc  mov     rax, rcx
0x18003b5cf  and     rax, rdx
0x18003b5d2  cmp     rax, rcx
0x18003b5d5  jnz     short loc_18003B601
0x18003b5d7  lea     rax, [rbp+57h+var_40]
0x18003b5db  mov     [rsp+0F0h+var_C8], rax
0x18003b5e0  mov     [rsp+0F0h+var_D0], 2
0x18003b5e8  xor     r9d, r9d
0x18003b5eb  xor     r8d, r8d
0x18003b5ee  lea     rdx, byte_180075A16
0x18003b5f5  lea     rcx, dword_180082080
0x18003b5fc  call    _tlgWriteTransfer_EventWriteTransfer
0x18003b601  lea     rdx, [rbp+57h+var_A8]
0x18003b605  mov     rcx, rbx
0x18003b608  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b60d  lea     rdx, [rbp+57h+var_9C]
0x18003b611  mov     rcx, rbx
0x18003b614  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b619  lea     rdx, [rbp+57h+var_AC]
0x18003b61d  mov     rcx, rbx
0x18003b620  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b625  lea     rdx, [rbp+57h+var_98]
0x18003b629  mov     rcx, rbx
0x18003b62c  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b631  lea     rdx, [rbp+57h+var_A0]
0x18003b635  mov     rcx, rbx
0x18003b638  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b63d  lea     rdx, [rbp+57h+var_A4]
0x18003b641  mov     rcx, rbx
0x18003b644  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b649  mov     [rbp+57h+var_B0], 0
0x18003b650  xorps   xmm0, xmm0
0x18003b653  movups  [rbp+57h+var_88], xmm0
0x18003b657  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003b65f  movdqu  [rbp+57h+var_78], xmm1
0x18003b664  xor     eax, eax
0x18003b666  mov     word ptr [rbp+57h+var_88], ax
0x18003b66a  lea     rdx, [rbp+57h+var_B0]
0x18003b66e  mov     rcx, rbx
0x18003b671  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b676  mov     r8d, [rbp+57h+var_B0]
0x18003b67a  lea     rdx, [rbp+57h+var_88]
0x18003b67e  mov     rcx, rbx
0x18003b681  call    ?extractUTF16String@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractUTF16String(std::wstring &,unsigned __int64,bool)
0x18003b686  lea     rcx, [rbp+57h+var_88]
0x18003b68a  cmp     qword ptr [rbp+57h+var_78+8], 7
0x18003b68f  cmova   rcx, qword ptr [rbp+57h+var_88]
0x18003b694  lea     r8, [rbp+57h+var_90]
0x18003b698  mov     edx, [rbp+57h+var_B0]
0x18003b69b  call    cs:__imp_MsgStringCreateShared
0x18003b6a1  mov     rcx, [rdi+8]
0x18003b6a5  mov     rax, [rcx]
0x18003b6a8  mov     r8d, [rbp+57h+var_AC]
0x18003b6ac  lea     rdx, [rbp+57h+var_68]
0x18003b6b0  mov     rax, [rax+38h]
0x18003b6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6b9  mov     rcx, [rdi+8]
0x18003b6bd  mov     rax, [rcx]
0x18003b6c0  mov     edx, [rbp+57h+var_A8]
0x18003b6c3  mov     rax, [rax+10h]
0x18003b6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6cc  mov     rcx, [rdi+18h]
0x18003b6d0  movups  xmm0, [rbp+57h+var_68]
0x18003b6d4  movaps  [rbp+57h+var_40], xmm0
0x18003b6d8  movups  xmm1, [rbp+57h+var_58]
0x18003b6dc  movaps  [rbp+57h+var_30], xmm1
0x18003b6e0  movsd   xmm0, [rbp+57h+var_48]
0x18003b6e5  movsd   [rbp+57h+var_20], xmm0
0x18003b6ea  mov     rax, [rcx]
0x18003b6ed  mov     rdx, [rbp+57h+var_90]
0x18003b6f1  mov     [rsp+0F0h+var_C0], rdx
0x18003b6f6  mov     edx, [rbp+57h+var_A4]
0x18003b6f9  mov     dword ptr [rsp+0F0h+var_C8], edx
0x18003b6fd  mov     edx, [rbp+57h+var_A0]
0x18003b700  mov     [rsp+0F0h+var_D0], edx
0x18003b704  mov     r9d, [rbp+57h+var_9C]
0x18003b708  mov     r8d, [rbp+57h+var_98]
0x18003b70c  lea     rdx, [rbp+57h+var_40]
0x18003b710  mov     rax, [rax+28h]
0x18003b714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b719  mov     rcx, [rbp+57h+var_90]
0x18003b71d  call    cs:__imp_MsgRelease
0x18003b723  nop
0x18003b724  lea     rcx, [rbp+57h+var_88]
0x18003b728  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b72d  xor     eax, eax
0x18003b72f  mov     rcx, [rbp+57h+var_10]
0x18003b733  xor     rcx, rsp; StackCookie
0x18003b736  call    __security_check_cookie
0x18003b73b  lea     r11, [rsp+0F0h+var_s0]
0x18003b743  mov     rbx, [r11+20h]
0x18003b747  mov     rdi, [r11+28h]
0x18003b74b  mov     rsp, r11
0x18003b74e  pop     rbp
0x18003b74f  retn
```
