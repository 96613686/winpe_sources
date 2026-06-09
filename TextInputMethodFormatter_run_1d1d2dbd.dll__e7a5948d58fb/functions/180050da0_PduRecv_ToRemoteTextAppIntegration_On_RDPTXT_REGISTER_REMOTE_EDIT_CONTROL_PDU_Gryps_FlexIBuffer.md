# PduRecv_ToRemoteTextAppIntegration::On_RDPTXT_REGISTER_REMOTE_EDIT_CONTROL_PDU(Gryps::FlexIBuffer *)

- ea: `0x180050da0`
- end: `0x180050f0e`
- name: `?On_RDPTXT_REGISTER_REMOTE_EDIT_CONTROL_PDU@PduRecv_ToRemoteTextAppIntegration@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(PduRecv_ToRemoteTextAppIntegration *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004f430`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180038d7c`
- `0x1800396e0`
- `0x18003b984`
- `0x180050da0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180050e91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180050e91`

## pseudocode

```c
__int64 __fastcall PduRecv_ToRemoteTextAppIntegration::On_RDPTXT_REGISTER_REMOTE_EDIT_CONTROL_PDU(
        PduRecv_ToRemoteTextAppIntegration *this,
        struct Gryps::FlexIBuffer *a2)
{
  const WCHAR *v4; // rcx
  UINT32 length; // [rsp+38h] [rbp-9h] BYREF
  int v7; // [rsp+3Ch] [rbp-5h] BYREF
  unsigned int v8; // [rsp+40h] [rbp-1h] BYREF
  unsigned int v9; // [rsp+44h] [rbp+3h] BYREF
  HSTRING string; // [rsp+48h] [rbp+7h] BYREF
  PCNZWCH sourceString[2]; // [rsp+50h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+60h] [rbp+1Fh]
  _BYTE v13[32]; // [rsp+70h] [rbp+2Fh] BYREF

  string = 0;
  v9 = 0;
  v8 = 0;
  v7 = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_180082080, &unk_180078C30, 0, 0, 2, v13);
  }
  length = 0;
  *(_OWORD *)sourceString = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(sourceString[0]) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &length);
  Gryps::FlexIBuffer::extractUTF16String((__int64)a2, (char ***)sourceString, length);
  v4 = (const WCHAR *)sourceString;
  if ( si128.m128i_i64[1] > 7uLL )
    v4 = sourceString[0];
  WindowsCreateString(v4, length, &string);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v9);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v8);
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v7);
  (*(void (__fastcall **)(_QWORD, HSTRING, _QWORD, _QWORD, int))(**((_QWORD **)this + 1) + 608LL))(
    *((_QWORD *)this + 1),
    string,
    v9,
    v8,
    v7);
  std::wstring::~wstring(sourceString);
  return 0;
}

```

## disassembly

```asm
0x180050da0  mov     r11, rsp
0x180050da3  mov     [r11+18h], rbx
0x180050da7  mov     [r11+20h], rdi
0x180050dab  push    rbp
0x180050dac  lea     rbp, [r11-5Fh]
0x180050db0  sub     rsp, 90h
0x180050db7  mov     rax, cs:__security_cookie
0x180050dbe  xor     rax, rsp
0x180050dc1  mov     [rbp+57h+var_8], rax
0x180050dc5  mov     rbx, rdx
0x180050dc8  mov     rdi, rcx
0x180050dcb  mov     [rbp+57h+string], 0
0x180050dd3  mov     [rbp+57h+var_54], 0
0x180050dda  mov     [rbp+57h+var_58], 0
0x180050de1  mov     [rbp+57h+var_5C], 0
0x180050de8  mov     eax, cs:dword_180082080
0x180050dee  cmp     eax, 5
0x180050df1  jbe     short loc_180050E3F
0x180050df3  mov     rcx, cs:qword_180082098
0x180050dfa  mov     rax, cs:qword_180082090
0x180050e01  mov     edx, 400000h
0x180050e06  test    rdx, rax
0x180050e09  jz      short loc_180050E3F
0x180050e0b  mov     rax, rcx
0x180050e0e  and     rax, rdx
0x180050e11  cmp     rax, rcx
0x180050e14  jnz     short loc_180050E3F
0x180050e16  lea     rax, [rbp+57h+var_28]
0x180050e1a  mov     [r11-70h], rax
0x180050e1e  mov     [rsp+90h+var_70], 2
0x180050e26  xor     r9d, r9d
0x180050e29  xor     r8d, r8d
0x180050e2c  lea     rdx, unk_180078C30
0x180050e33  lea     rcx, dword_180082080
0x180050e3a  call    _tlgWriteTransfer_EventWriteTransfer
0x180050e3f  mov     [rbp+57h+length], 0
0x180050e46  xorps   xmm0, xmm0
0x180050e49  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180050e4d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180050e55  movdqu  [rbp+57h+var_38], xmm1
0x180050e5a  xor     eax, eax
0x180050e5c  mov     word ptr [rbp+57h+sourceString], ax
0x180050e60  lea     rdx, [rbp+57h+length]
0x180050e64  mov     rcx, rbx
0x180050e67  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180050e6c  mov     r8d, [rbp+57h+length]
0x180050e70  lea     rdx, [rbp+57h+sourceString]
0x180050e74  mov     rcx, rbx
0x180050e77  call    ?extractUTF16String@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractUTF16String(std::wstring &,unsigned __int64,bool)
0x180050e7c  lea     rcx, [rbp+57h+sourceString]
0x180050e80  cmp     qword ptr [rbp+57h+var_38+8], 7
0x180050e85  cmova   rcx, [rbp+57h+sourceString]; sourceString
0x180050e8a  lea     r8, [rbp+57h+string]; string
0x180050e8e  mov     edx, [rbp+57h+length]; length
0x180050e91  call    cs:__imp_WindowsCreateString
0x180050e97  lea     rdx, [rbp+57h+var_54]
0x180050e9b  mov     rcx, rbx
0x180050e9e  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180050ea3  lea     rdx, [rbp+57h+var_58]
0x180050ea7  mov     rcx, rbx
0x180050eaa  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180050eaf  lea     rdx, [rbp+57h+var_5C]
0x180050eb3  mov     rcx, rbx
0x180050eb6  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x180050ebb  mov     rcx, [rdi+8]
0x180050ebf  mov     rax, [rcx]
0x180050ec2  mov     edx, [rbp+57h+var_5C]
0x180050ec5  mov     [rsp+90h+var_70], edx
0x180050ec9  mov     r9d, [rbp+57h+var_58]
0x180050ecd  mov     r8d, [rbp+57h+var_54]
0x180050ed1  mov     rdx, [rbp+57h+string]
0x180050ed5  mov     rax, [rax+260h]
0x180050edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ee1  nop
0x180050ee2  lea     rcx, [rbp+57h+sourceString]
0x180050ee6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050eeb  xor     eax, eax
0x180050eed  mov     rcx, [rbp+57h+var_8]
0x180050ef1  xor     rcx, rsp; StackCookie
0x180050ef4  call    __security_check_cookie
0x180050ef9  lea     r11, [rsp+90h+var_s0]
0x180050f01  mov     rbx, [r11+20h]
0x180050f05  mov     rdi, [r11+28h]
0x180050f09  mov     rsp, r11
0x180050f0c  pop     rbp
0x180050f0d  retn
```
