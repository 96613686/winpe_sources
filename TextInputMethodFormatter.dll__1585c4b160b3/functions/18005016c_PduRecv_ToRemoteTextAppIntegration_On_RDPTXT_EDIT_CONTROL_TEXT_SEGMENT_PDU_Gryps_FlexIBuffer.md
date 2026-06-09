# PduRecv_ToRemoteTextAppIntegration::On_RDPTXT_EDIT_CONTROL_TEXT_SEGMENT_PDU(Gryps::FlexIBuffer *)

- ea: `0x18005016c`
- end: `0x18005030f`
- name: `?On_RDPTXT_EDIT_CONTROL_TEXT_SEGMENT_PDU@PduRecv_ToRemoteTextAppIntegration@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(PduRecv_ToRemoteTextAppIntegration *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18004f430`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180038c0c`
- `0x180038d7c`
- `0x1800396e0`
- `0x18003b984`
- `0x18005016c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800502aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800502aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PduRecv_ToRemoteTextAppIntegration::On_RDPTXT_EDIT_CONTROL_TEXT_SEGMENT_PDU(
        PduRecv_ToRemoteTextAppIntegration *this,
        struct Gryps::FlexIBuffer *a2)
{
  BOOL v4; // ebx
  const WCHAR *v5; // rcx
  _BYTE v7[4]; // [rsp+40h] [rbp-29h] BYREF
  UINT32 length; // [rsp+44h] [rbp-25h] BYREF
  int v9; // [rsp+48h] [rbp-21h] BYREF
  int v10; // [rsp+4Ch] [rbp-1Dh] BYREF
  unsigned int v11; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v12; // [rsp+54h] [rbp-15h] BYREF
  HSTRING string; // [rsp+58h] [rbp-11h] BYREF
  PCNZWCH sourceString[2]; // [rsp+60h] [rbp-9h] BYREF
  __m128i si128; // [rsp+70h] [rbp+7h]
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+80h] [rbp+17h] BYREF

  v12 = 0;
  v11 = 0;
  v10 = 0;
  v9 = 0;
  string = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180082080, (unsigned __int8 *)word_180077F4A, 0, 0, 2u, &v16);
  }
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v12);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v11);
  v7[0] = 0;
  Gryps::FlexIBuffer::extractLE<unsigned char>(a2, v7);
  v4 = v7[0] != 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v10);
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &v9);
  length = 0;
  *(_OWORD *)sourceString = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(sourceString[0]) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &length);
  Gryps::FlexIBuffer::extractUTF16String(a2, sourceString, length);
  v5 = (const WCHAR *)sourceString;
  if ( si128.m128i_i64[1] > 7uLL )
    v5 = sourceString[0];
  WindowsCreateString(v5, length, &string);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, BOOL, int, int, HSTRING))(**((_QWORD **)this + 1) + 840LL))(
    *((_QWORD *)this + 1),
    v12,
    v11,
    v4,
    v10,
    v9,
    string);
  std::wstring::~wstring(sourceString);
  return 0;
}

```

## disassembly

```asm
0x18005016c  mov     [rsp-8+arg_10], rbx
0x180050171  push    rbp
0x180050172  push    rsi
0x180050173  push    rdi
0x180050174  lea     rbp, [rsp-47h]
0x180050179  sub     rsp, 0B0h
0x180050180  mov     rax, cs:__security_cookie
0x180050187  xor     rax, rsp
0x18005018a  mov     [rbp+57h+var_20], rax
0x18005018e  mov     rdi, rdx
0x180050191  mov     rsi, rcx
0x180050194  mov     [rbp+57h+var_6C], 0
0x18005019b  mov     [rbp+57h+var_70], 0
0x1800501a2  mov     [rbp+57h+var_74], 0
0x1800501a9  mov     [rbp+57h+var_78], 0
0x1800501b0  mov     [rbp+57h+string], 0
0x1800501b8  mov     eax, cs:dword_180082080
0x1800501be  cmp     eax, 5
0x1800501c1  jbe     short loc_180050210
0x1800501c3  mov     rcx, cs:qword_180082098
0x1800501ca  mov     rax, cs:qword_180082090
0x1800501d1  mov     edx, 400000h
0x1800501d6  test    rdx, rax
0x1800501d9  jz      short loc_180050210
0x1800501db  mov     rax, rcx
0x1800501de  and     rax, rdx
0x1800501e1  cmp     rax, rcx
0x1800501e4  jnz     short loc_180050210
0x1800501e6  lea     rax, [rbp+57h+var_40]
0x1800501ea  mov     [rsp+0C0h+var_98], rax
0x1800501ef  mov     [rsp+0C0h+var_A0], 2
0x1800501f7  xor     r9d, r9d
0x1800501fa  xor     r8d, r8d
0x1800501fd  lea     rdx, word_180077F4A
0x180050204  lea     rcx, dword_180082080
0x18005020b  call    _tlgWriteTransfer_EventWriteTransfer
0x180050210  lea     rdx, [rbp+57h+var_6C]
0x180050214  mov     rcx, rdi
0x180050217  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18005021c  lea     rdx, [rbp+57h+var_70]
0x180050220  mov     rcx, rdi
0x180050223  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180050228  mov     [rbp+57h+var_80], 0
0x18005022c  lea     rdx, [rbp+57h+var_80]
0x180050230  mov     rcx, rdi
0x180050233  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x180050238  xor     ebx, ebx
0x18005023a  cmp     [rbp+57h+var_80], bl
0x18005023d  setnz   bl
0x180050240  lea     rdx, [rbp+57h+var_74]
0x180050244  mov     rcx, rdi
0x180050247  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18005024c  lea     rdx, [rbp+57h+var_78]
0x180050250  mov     rcx, rdi
0x180050253  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180050258  mov     [rbp+57h+length], 0
0x18005025f  xorps   xmm0, xmm0
0x180050262  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180050266  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005026e  movdqu  [rbp+57h+var_50], xmm1
0x180050273  xor     eax, eax
0x180050275  mov     word ptr [rbp+57h+sourceString], ax
0x180050279  lea     rdx, [rbp+57h+length]
0x18005027d  mov     rcx, rdi
0x180050280  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180050285  mov     r8d, [rbp+57h+length]
0x180050289  lea     rdx, [rbp+57h+sourceString]
0x18005028d  mov     rcx, rdi
0x180050290  call    ?extractUTF16String@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractUTF16String(std::wstring &,unsigned __int64,bool)
0x180050295  lea     rcx, [rbp+57h+sourceString]
0x180050299  cmp     qword ptr [rbp+57h+var_50+8], 7
0x18005029e  cmova   rcx, [rbp+57h+sourceString]; sourceString
0x1800502a3  lea     r8, [rbp+57h+string]; string
0x1800502a7  mov     edx, [rbp+57h+length]; length
0x1800502aa  call    cs:__imp_WindowsCreateString
0x1800502b0  mov     rcx, [rsi+8]
0x1800502b4  mov     rax, [rcx]
0x1800502b7  mov     rdx, [rbp+57h+string]
0x1800502bb  mov     [rsp+0C0h+var_90], rdx
0x1800502c0  mov     edx, [rbp+57h+var_78]
0x1800502c3  mov     dword ptr [rsp+0C0h+var_98], edx
0x1800502c7  mov     edx, [rbp+57h+var_74]
0x1800502ca  mov     [rsp+0C0h+var_A0], edx
0x1800502ce  mov     r9d, ebx
0x1800502d1  mov     r8d, [rbp+57h+var_70]
0x1800502d5  mov     edx, [rbp+57h+var_6C]
0x1800502d8  mov     rax, [rax+348h]
0x1800502df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502e4  nop
0x1800502e5  lea     rcx, [rbp+57h+sourceString]
0x1800502e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800502ee  xor     eax, eax
0x1800502f0  mov     rcx, [rbp+57h+var_20]
0x1800502f4  xor     rcx, rsp; StackCookie
0x1800502f7  call    __security_check_cookie
0x1800502fc  mov     rbx, [rsp+0C0h+arg_10]
0x180050304  add     rsp, 0B0h
0x18005030b  pop     rdi
0x18005030c  pop     rsi
0x18005030d  pop     rbp
0x18005030e  retn
```
