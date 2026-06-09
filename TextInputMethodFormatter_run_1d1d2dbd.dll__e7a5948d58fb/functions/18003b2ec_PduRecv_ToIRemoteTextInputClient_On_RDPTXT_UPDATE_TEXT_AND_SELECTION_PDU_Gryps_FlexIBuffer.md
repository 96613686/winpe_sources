# PduRecv_ToIRemoteTextInputClient::On_RDPTXT_UPDATE_TEXT_AND_SELECTION_PDU(Gryps::FlexIBuffer *)

- ea: `0x18003b2ec`
- end: `0x18003b544`
- name: `?On_RDPTXT_UPDATE_TEXT_AND_SELECTION_PDU@PduRecv_ToIRemoteTextInputClient@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `600`
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
- `0x18003b2ec`
- `0x18003b984`
- `0x180058010`

## import_xrefs

- `CoreMessaging!MsgStringCreateShared` at `0x18003b45d`
- `CoreMessaging!MsgStringCreateShared` at `0x18003b45d`
- `CoreMessaging!MsgRelease` at `0x18003b511`
- `CoreMessaging!MsgRelease` at `0x18003b511`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PduRecv_ToIRemoteTextInputClient::On_RDPTXT_UPDATE_TEXT_AND_SELECTION_PDU(
        PduRecv_ToIRemoteTextInputClient *this,
        struct Gryps::FlexIBuffer *a2)
{
  __int128 *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v10; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v11; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v12; // [rsp+58h] [rbp-A8h] BYREF
  int v13; // [rsp+5Ch] [rbp-A4h] BYREF
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+64h] [rbp-9Ch] BYREF
  int v16; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v17; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v18; // [rsp+70h] [rbp-90h] BYREF
  __int64 v19; // [rsp+78h] [rbp-88h] BYREF
  __int128 v20; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  _OWORD v22[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+C0h] [rbp-40h]
  struct _EVENT_DATA_DESCRIPTOR v24[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-10h]

  v12 = 0;
  v17 = 0;
  v11 = 0;
  v18 = 0;
  v16 = 0;
  v15 = 0;
  v19 = 0;
  v14 = 0;
  v13 = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180082080, byte_1800759A4, 0, 0, 2u, v24);
  }
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v12);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v17);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v11);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v18);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v16);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v15);
  v10 = 0;
  v20 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v20) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v10);
  Gryps::FlexIBuffer::extractUTF16String((__int64)a2, (char ***)&v20, v10);
  v4 = &v20;
  if ( si128.m128i_i64[1] > 7uLL )
    v4 = (__int128 *)v20;
  MsgStringCreateShared(v4, v10, &v19);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v14);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v13);
  (*(void (__fastcall **)(_QWORD, _OWORD *, _QWORD))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1), v22, v11);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), v12);
  v5 = *((_QWORD *)this + 3);
  v24[0] = (struct _EVENT_DATA_DESCRIPTOR)v22[0];
  v24[1] = (struct _EVENT_DATA_DESCRIPTOR)v22[1];
  v25 = v23;
  (*(void (__fastcall **)(__int64, struct _EVENT_DATA_DESCRIPTOR *, _QWORD, _QWORD, int, int, __int64, int, int))(*(_QWORD *)v5 + 48LL))(
    v5,
    v24,
    v18,
    v17,
    v16,
    v15,
    v19,
    v14,
    v13);
  MsgRelease(v19, v6, v7, v8);
  std::wstring::~wstring(&v20);
  return 0;
}

```

## disassembly

```asm
0x18003b2ec  mov     [rsp-8+arg_10], rbx
0x18003b2f1  mov     [rsp-8+arg_18], rdi
0x18003b2f6  push    rbp
0x18003b2f7  lea     rbp, [rsp-10h]
0x18003b2fc  sub     rsp, 110h
0x18003b303  mov     rax, cs:__security_cookie
0x18003b30a  xor     rax, rsp
0x18003b30d  mov     [rbp+10h+var_10], rax
0x18003b311  mov     rbx, rdx
0x18003b314  mov     rdi, rcx
0x18003b317  mov     [rsp+110h+var_B8], 0
0x18003b31f  mov     [rsp+110h+var_A4], 0
0x18003b327  mov     [rsp+110h+var_BC], 0
0x18003b32f  mov     [rsp+110h+var_A0], 0
0x18003b337  mov     [rsp+110h+var_A8], 0
0x18003b33f  mov     [rsp+110h+var_AC], 0
0x18003b347  mov     [rsp+110h+var_98], 0
0x18003b350  mov     [rsp+110h+var_B0], 0
0x18003b358  mov     [rsp+110h+var_B4], 0
0x18003b360  mov     eax, cs:dword_180082080
0x18003b366  cmp     eax, 5
0x18003b369  jbe     short loc_18003B3B8
0x18003b36b  mov     rcx, cs:qword_180082098
0x18003b372  mov     rax, cs:qword_180082090
0x18003b379  mov     edx, 400000h
0x18003b37e  test    rdx, rax
0x18003b381  jz      short loc_18003B3B8
0x18003b383  mov     rax, rcx
0x18003b386  and     rax, rdx
0x18003b389  cmp     rax, rcx
0x18003b38c  jnz     short loc_18003B3B8
0x18003b38e  lea     rax, [rbp+10h+var_40]
0x18003b392  mov     [rsp+110h+var_E8], rax
0x18003b397  mov     [rsp+110h+var_F0], 2
0x18003b39f  xor     r9d, r9d
0x18003b3a2  xor     r8d, r8d
0x18003b3a5  lea     rdx, byte_1800759A4
0x18003b3ac  lea     rcx, dword_180082080
0x18003b3b3  call    _tlgWriteTransfer_EventWriteTransfer
0x18003b3b8  lea     rdx, [rsp+110h+var_B8]
0x18003b3bd  mov     rcx, rbx
0x18003b3c0  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b3c5  lea     rdx, [rsp+110h+var_A4]
0x18003b3ca  mov     rcx, rbx
0x18003b3cd  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b3d2  lea     rdx, [rsp+110h+var_BC]
0x18003b3d7  mov     rcx, rbx
0x18003b3da  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b3df  lea     rdx, [rsp+110h+var_A0]
0x18003b3e4  mov     rcx, rbx
0x18003b3e7  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b3ec  lea     rdx, [rsp+110h+var_A8]
0x18003b3f1  mov     rcx, rbx
0x18003b3f4  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b3f9  lea     rdx, [rsp+110h+var_AC]
0x18003b3fe  mov     rcx, rbx
0x18003b401  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b406  mov     [rsp+110h+var_C0], 0
0x18003b40e  xorps   xmm0, xmm0
0x18003b411  movups  [rbp+10h+var_90], xmm0
0x18003b415  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003b41d  movdqu  [rbp+10h+var_80], xmm1
0x18003b422  xor     eax, eax
0x18003b424  mov     word ptr [rbp+10h+var_90], ax
0x18003b428  lea     rdx, [rsp+110h+var_C0]
0x18003b42d  mov     rcx, rbx
0x18003b430  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b435  mov     r8d, [rsp+110h+var_C0]
0x18003b43a  lea     rdx, [rbp+10h+var_90]
0x18003b43e  mov     rcx, rbx
0x18003b441  call    ?extractUTF16String@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractUTF16String(std::wstring &,unsigned __int64,bool)
0x18003b446  lea     rcx, [rbp+10h+var_90]
0x18003b44a  cmp     qword ptr [rbp+10h+var_80+8], 7
0x18003b44f  cmova   rcx, qword ptr [rbp+10h+var_90]
0x18003b454  lea     r8, [rsp+110h+var_98]
0x18003b459  mov     edx, [rsp+110h+var_C0]
0x18003b45d  call    cs:__imp_MsgStringCreateShared
0x18003b463  lea     rdx, [rsp+110h+var_B0]
0x18003b468  mov     rcx, rbx
0x18003b46b  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b470  lea     rdx, [rsp+110h+var_B4]
0x18003b475  mov     rcx, rbx
0x18003b478  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003b47d  mov     rcx, [rdi+8]
0x18003b481  mov     rax, [rcx]
0x18003b484  mov     r8d, [rsp+110h+var_BC]
0x18003b489  lea     rdx, [rbp+10h+var_70]
0x18003b48d  mov     rax, [rax+38h]
0x18003b491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b496  mov     rcx, [rdi+8]
0x18003b49a  mov     rax, [rcx]
0x18003b49d  mov     edx, [rsp+110h+var_B8]
0x18003b4a1  mov     rax, [rax+10h]
0x18003b4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4aa  mov     rcx, [rdi+18h]
0x18003b4ae  movups  xmm0, [rbp+10h+var_70]
0x18003b4b2  movaps  [rbp+10h+var_40], xmm0
0x18003b4b6  movups  xmm1, [rbp+10h+var_60]
0x18003b4ba  movaps  [rbp+10h+var_30], xmm1
0x18003b4be  movsd   xmm0, [rbp+10h+var_50]
0x18003b4c3  movsd   [rbp+10h+var_20], xmm0
0x18003b4c8  mov     rax, [rcx]
0x18003b4cb  mov     edx, [rsp+110h+var_B4]
0x18003b4cf  mov     [rsp+110h+var_D0], edx
0x18003b4d3  mov     edx, [rsp+110h+var_B0]
0x18003b4d7  mov     [rsp+110h+var_D8], edx
0x18003b4db  mov     rdx, [rsp+110h+var_98]
0x18003b4e0  mov     [rsp+110h+var_E0], rdx
0x18003b4e5  mov     edx, [rsp+110h+var_AC]
0x18003b4e9  mov     dword ptr [rsp+110h+var_E8], edx
0x18003b4ed  mov     edx, [rsp+110h+var_A8]
0x18003b4f1  mov     [rsp+110h+var_F0], edx
0x18003b4f5  mov     r9d, [rsp+110h+var_A4]
0x18003b4fa  mov     r8d, [rsp+110h+var_A0]
0x18003b4ff  lea     rdx, [rbp+10h+var_40]
0x18003b503  mov     rax, [rax+30h]
0x18003b507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b50c  mov     rcx, [rsp+110h+var_98]
0x18003b511  call    cs:__imp_MsgRelease
0x18003b517  nop
0x18003b518  lea     rcx, [rbp+10h+var_90]
0x18003b51c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b521  xor     eax, eax
0x18003b523  mov     rcx, [rbp+10h+var_10]
0x18003b527  xor     rcx, rsp; StackCookie
0x18003b52a  call    __security_check_cookie
0x18003b52f  lea     r11, [rsp+110h+var_s0]
0x18003b537  mov     rbx, [r11+20h]
0x18003b53b  mov     rdi, [r11+28h]
0x18003b53f  mov     rsp, r11
0x18003b542  pop     rbp
0x18003b543  retn
```
