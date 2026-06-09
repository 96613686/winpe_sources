# PduRecv_ToRemoteTextAppIntegration::On_RDPTXT_FOREGROUND_HOST_INFO_UPDATED_PDU(Gryps::FlexIBuffer *)

- ea: `0x180050318`
- end: `0x18005043e`
- name: `?On_RDPTXT_FOREGROUND_HOST_INFO_UPDATED_PDU@PduRecv_ToRemoteTextAppIntegration@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(PduRecv_ToRemoteTextAppIntegration *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18004f430`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180038d7c`
- `0x1800396e0`
- `0x18003b984`
- `0x180050318`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800503f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800503f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PduRecv_ToRemoteTextAppIntegration::On_RDPTXT_FOREGROUND_HOST_INFO_UPDATED_PDU(
        PduRecv_ToRemoteTextAppIntegration *this,
        struct Gryps::FlexIBuffer *a2)
{
  const WCHAR *v4; // rcx
  UINT32 length; // [rsp+38h] [rbp-9h] BYREF
  HSTRING string; // [rsp+40h] [rbp-1h] BYREF
  PCNZWCH sourceString[2]; // [rsp+48h] [rbp+7h] BYREF
  __m128i si128; // [rsp+58h] [rbp+17h]
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+68h] [rbp+27h] BYREF

  string = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180082080, (unsigned __int8 *)byte_18007850B, 0, 0, 2u, &v10);
  }
  length = 0;
  *(_OWORD *)sourceString = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(sourceString[0]) = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>(a2, &length);
  Gryps::FlexIBuffer::extractUTF16String(a2, sourceString, length);
  v4 = (const WCHAR *)sourceString;
  if ( si128.m128i_i64[1] > 7uLL )
    v4 = sourceString[0];
  WindowsCreateString(v4, length, &string);
  (*(void (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)this + 1) + 736LL))(*((_QWORD *)this + 1), string);
  std::wstring::~wstring(sourceString);
  return 0;
}

```

## disassembly

```asm
0x180050318  mov     r11, rsp
0x18005031b  mov     [r11+18h], rbx
0x18005031f  mov     [r11+20h], rdi
0x180050323  push    rbp
0x180050324  lea     rbp, [r11-5Fh]
0x180050328  sub     rsp, 90h
0x18005032f  mov     rax, cs:__security_cookie
0x180050336  xor     rax, rsp
0x180050339  mov     [rbp+57h+var_10], rax
0x18005033d  mov     rbx, rdx
0x180050340  mov     rdi, rcx
0x180050343  mov     [rbp+57h+string], 0
0x18005034b  mov     eax, cs:dword_180082080
0x180050351  cmp     eax, 5
0x180050354  jbe     short loc_1800503A2
0x180050356  mov     rdx, cs:qword_180082098
0x18005035d  mov     rax, cs:qword_180082090
0x180050364  mov     ecx, 400000h
0x180050369  test    rcx, rax
0x18005036c  jz      short loc_1800503A2
0x18005036e  mov     rax, rdx
0x180050371  and     rax, rcx
0x180050374  cmp     rax, rdx
0x180050377  jnz     short loc_1800503A2
0x180050379  lea     rax, [rbp+57h+var_30]
0x18005037d  mov     [r11-70h], rax
0x180050381  mov     [rsp+90h+var_70], 2
0x180050389  xor     r9d, r9d
0x18005038c  xor     r8d, r8d
0x18005038f  lea     rdx, byte_18007850B
0x180050396  lea     rcx, dword_180082080
0x18005039d  call    _tlgWriteTransfer_EventWriteTransfer
0x1800503a2  mov     [rbp+57h+length], 0
0x1800503a9  xorps   xmm0, xmm0
0x1800503ac  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x1800503b0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800503b8  movdqu  [rbp+57h+var_40], xmm1
0x1800503bd  xor     eax, eax
0x1800503bf  mov     word ptr [rbp+57h+sourceString], ax
0x1800503c3  lea     rdx, [rbp+57h+length]
0x1800503c7  mov     rcx, rbx
0x1800503ca  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x1800503cf  mov     r8d, [rbp+57h+length]
0x1800503d3  lea     rdx, [rbp+57h+sourceString]
0x1800503d7  mov     rcx, rbx
0x1800503da  call    ?extractUTF16String@FlexIBuffer@Gryps@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; Gryps::FlexIBuffer::extractUTF16String(std::wstring &,unsigned __int64,bool)
0x1800503df  lea     rcx, [rbp+57h+sourceString]
0x1800503e3  cmp     qword ptr [rbp+57h+var_40+8], 7
0x1800503e8  cmova   rcx, [rbp+57h+sourceString]; sourceString
0x1800503ed  lea     r8, [rbp+57h+string]; string
0x1800503f1  mov     edx, [rbp+57h+length]; length
0x1800503f4  call    cs:__imp_WindowsCreateString
0x1800503fa  mov     rcx, [rdi+8]
0x1800503fe  mov     rax, [rcx]
0x180050401  mov     rdx, [rbp+57h+string]
0x180050405  mov     rax, [rax+2E0h]
0x18005040c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050411  nop
0x180050412  lea     rcx, [rbp+57h+sourceString]
0x180050416  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005041b  xor     eax, eax
0x18005041d  mov     rcx, [rbp+57h+var_10]
0x180050421  xor     rcx, rsp; StackCookie
0x180050424  call    __security_check_cookie
0x180050429  lea     r11, [rsp+90h+var_s0]
0x180050431  mov     rbx, [r11+20h]
0x180050435  mov     rdi, [r11+28h]
0x180050439  mov     rsp, r11
0x18005043c  pop     rbp
0x18005043d  retn
```
