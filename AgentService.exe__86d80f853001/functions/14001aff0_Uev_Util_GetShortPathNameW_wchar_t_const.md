# Uev::Util::GetShortPathNameW(wchar_t const *)

- ea: `0x14001aff0`
- end: `0x14001b13d`
- name: `?GetShortPathNameW@Util@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z`
- size: `333`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1400125ac`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x140004ab4`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x14000d448`
- `0x140015190`
- `0x14001aff0`
- `0x140023bd8`

## import_xrefs

- `KERNEL32!GetShortPathNameW` at `0x14001b03c`
- `KERNEL32!GetShortPathNameW` at `0x14001b072`
- `KERNEL32!GetShortPathNameW` at `0x14001b03c`
- `KERNEL32!GetShortPathNameW` at `0x14001b072`
- `KERNEL32!GetLastError` at `0x14001b0eb`
- `KERNEL32!GetLastError` at `0x14001b0eb`

## string_xrefs

- `0x14001b0f9`: `::GetShortPathName failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Uev::Util::GetShortPathNameW(_QWORD *a1, const WCHAR *a2)
{
  WCHAR *v4; // rbx
  DWORD ShortPathNameW; // eax
  DWORD v6; // esi
  WCHAR *v7; // rbp
  WCHAR *v8; // r14
  DWORD LastError; // ebx
  __int64 v11; // rcx
  __int64 v12; // rcx
  _QWORD *SystemError; // rax
  WCHAR *v14; // [rsp+20h] [rbp-2C8h]
  _QWORD v15[4]; // [rsp+30h] [rbp-2B8h] BYREF
  _BYTE v16[32]; // [rsp+50h] [rbp-298h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+70h] [rbp-278h] BYREF
  WCHAR szShortPath[264]; // [rsp+B0h] [rbp-238h] BYREF

  v4 = 0;
  v14 = 0;
  ShortPathNameW = GetShortPathNameW(a2, szShortPath, 0x104u);
  v6 = ShortPathNameW;
  if ( ShortPathNameW <= 0x104 )
  {
    v8 = 0;
    v7 = szShortPath;
  }
  else
  {
    v4 = (WCHAR *)operator new[](saturated_mul(ShortPathNameW, 2u));
    v14 = v4;
    v7 = v4;
    v6 = GetShortPathNameW(a2, v4, v6);
    v8 = v4;
  }
  if ( !v6 )
  {
    LastError = GetLastError();
    Uev::Singleton<Uev::Log,Uev::Log>::Instance(v11);
    std::wstring::wstring(v15, L"::GetShortPathName failed");
    SystemError = (_QWORD *)Uev::Log::GetSystemError(v12, v16, v15, LastError, v14);
    Uev::UevException::UevException((__int64)pExceptionObject, SystemError);
    throw (Uev::UevException *)pExceptionObject;
  }
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  std::wstring::_Construct<1,wchar_t *>(a1, v7, v6);
  if ( v8 )
    operator delete(v4);
  return a1;
}

```

## disassembly

```asm
0x14001aff0  mov     [rsp+arg_10], rbx
0x14001aff5  mov     [rsp+arg_18], rbp
0x14001affa  push    rsi
0x14001affb  push    rdi
0x14001affc  push    r14
0x14001affe  sub     rsp, 2D0h
0x14001b005  mov     rax, cs:__security_cookie
0x14001b00c  xor     rax, rsp
0x14001b00f  mov     [rsp+2E8h+var_28], rax
0x14001b017  mov     r14, rdx
0x14001b01a  mov     rdi, rcx
0x14001b01d  mov     [rsp+2E8h+var_2C8], rcx
0x14001b022  xor     ebx, ebx
0x14001b024  mov     [rsp+2E8h+var_2C8], rbx
0x14001b029  mov     ebp, 104h
0x14001b02e  mov     r8d, ebp; cchBuffer
0x14001b031  lea     rdx, [rsp+2E8h+szShortPath]; lpszShortPath
0x14001b039  mov     rcx, r14; lpszLongPath
0x14001b03c  call    cs:__imp_GetShortPathNameW
0x14001b042  mov     esi, eax
0x14001b044  cmp     eax, ebp
0x14001b046  jbe     short loc_14001B07F
0x14001b048  lea     eax, [rbx+2]
0x14001b04b  mul     rsi
0x14001b04e  lea     rcx, [rbx-1]
0x14001b052  cmovb   rax, rcx
0x14001b056  mov     rcx, rax; unsigned __int64
0x14001b059  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14001b05e  mov     rbx, rax
0x14001b061  mov     [rsp+2E8h+var_2C8], rax
0x14001b066  mov     rbp, rax
0x14001b069  mov     r8d, esi; cchBuffer
0x14001b06c  mov     rdx, rax; lpszShortPath
0x14001b06f  mov     rcx, r14; lpszLongPath
0x14001b072  call    cs:__imp_GetShortPathNameW
0x14001b078  mov     esi, eax
0x14001b07a  mov     r14, rbx
0x14001b07d  jmp     short loc_14001B08A
0x14001b07f  xor     r14d, r14d
0x14001b082  lea     rbp, [rsp+2E8h+szShortPath]
0x14001b08a  test    esi, esi
0x14001b08c  jz      short loc_14001B0EB
0x14001b08e  xorps   xmm0, xmm0
0x14001b091  movups  xmmword ptr [rdi], xmm0
0x14001b094  mov     qword ptr [rdi+10h], 0
0x14001b09c  mov     qword ptr [rdi+18h], 0
0x14001b0a4  mov     r8d, esi
0x14001b0a7  mov     rdx, rbp
0x14001b0aa  mov     rcx, rdi
0x14001b0ad  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14001b0b2  nop
0x14001b0b3  test    r14, r14
0x14001b0b6  jz      short loc_14001B0C0
0x14001b0b8  mov     rcx, rbx; Block
0x14001b0bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001b0c0  mov     rax, rdi
0x14001b0c3  mov     rcx, [rsp+2E8h+var_28]
0x14001b0cb  xor     rcx, rsp; StackCookie
0x14001b0ce  call    __security_check_cookie
0x14001b0d3  lea     r11, [rsp+2E8h+var_18]
0x14001b0db  mov     rbx, [r11+30h]
0x14001b0df  mov     rbp, [r11+38h]
0x14001b0e3  mov     rsp, r11
0x14001b0e6  pop     r14
0x14001b0e8  pop     rdi
0x14001b0e9  pop     rsi
0x14001b0ea  retn
0x14001b0eb  call    cs:__imp_GetLastError
0x14001b0f1  nop
0x14001b0f2  mov     ebx, eax
0x14001b0f4  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14001b0f9  lea     rdx, aGetshortpathna; "::GetShortPathName failed"
0x14001b100  lea     rcx, [rsp+2E8h+var_2B8]
0x14001b105  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001b10a  nop
0x14001b10b  mov     r9d, ebx
0x14001b10e  lea     r8, [rsp+2E8h+var_2B8]
0x14001b113  lea     rdx, [rsp+2E8h+var_298]
0x14001b118  call    ?GetSystemError@Log@Uev@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@K@Z; Uev::Log::GetSystemError(std::wstring const &,ulong)
0x14001b11d  nop
0x14001b11e  mov     rdx, rax
0x14001b121  lea     rcx, [rsp+2E8h+pExceptionObject]
0x14001b126  call    ??0UevException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::UevException::UevException(std::wstring const &)
0x14001b12b  lea     rdx, _TI2?AVUevException@Uev@@; pThrowInfo
0x14001b132  lea     rcx, [rsp+2E8h+pExceptionObject]; pExceptionObject
0x14001b137  call    _CxxThrowException_0
```
