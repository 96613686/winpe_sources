# Uev::Log::GetSystemError(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong)

- ea: `0x140023bd8`
- end: `0x140023db3`
- name: `?GetSystemError@Log@Uev@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@K@Z`
- size: `475`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x14001a9c8`
- `0x14001aff0`
- `0x1400329bc`
- `0x14008b730`
- `0x14008c424`
- `0x14008c774`

## callees

- `0x140003e50`
- `0x140004a6c`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000c1cc`
- `0x14000c2b8`
- `0x14000c3a4`
- `0x14000d7b4`
- `0x140023bd8`

## import_xrefs

- `KERNEL32!LocalLock` at `0x140023c8a`
- `KERNEL32!LocalLock` at `0x140023c8a`
- `KERNEL32!FormatMessageW` at `0x140023c76`
- `KERNEL32!FormatMessageW` at `0x140023c76`
- `KERNEL32!LocalFree` at `0x140023d24`
- `KERNEL32!LocalFree` at `0x140023d24`
- `KERNEL32!LocalUnlock` at `0x140023cb9`
- `KERNEL32!LocalUnlock` at `0x140023cb9`

## string_xrefs

- `0x140023cf9`: `<Error accessing system message>`
- `0x140023d10`: `<Error accessing system message>`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Uev::Log::GetSystemError(__int64 a1, _QWORD *a2, __int64 a3, DWORD a4)
{
  DWORD v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r8
  _WORD *v9; // rbx
  _WORD *v10; // rbx
  void **v11; // rdx
  WCHAR Buffer[4]; // [rsp+48h] [rbp-11h] BYREF
  _QWORD *v14; // [rsp+50h] [rbp-9h]
  void *v15[2]; // [rsp+58h] [rbp-1h] BYREF
  unsigned __int64 v16; // [rsp+68h] [rbp+Fh]
  unsigned __int64 v17; // [rsp+70h] [rbp+17h]
  _OWORD v18[2]; // [rsp+78h] [rbp+1Fh] BYREF

  v14 = a2;
  std::wstring::wstring((__int64)a2, a3);
  std::wstring::_Append<wchar_t>(a2, L": ", 2u);
  *(_OWORD *)v15 = 0;
  v16 = 0;
  v17 = 7;
  LOWORD(v15[0]) = 0;
  *(_QWORD *)Buffer = 0;
  v6 = FormatMessageW(0x1100u, 0, a4, 0, Buffer, 0, 0);
  if ( v6 )
  {
    if ( LocalLock(*(HLOCAL *)Buffer) )
    {
      memset(v18, 0, sizeof(v18));
      std::wstring::_Construct<1,wchar_t *>(v18, *(const void **)Buffer, v6);
      LocalUnlock(*(HLOCAL *)Buffer);
      std::wstring::operator=(v15, v18);
      std::wstring::_Tidy_deallocate(v18);
    }
    else if ( v17 < 0x20 )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
        (char **)v15,
        0x20u,
        v8,
        L"<Error accessing system message>");
    }
    else
    {
      v9 = v15[0];
      v16 = 32;
      memmove_0(v15[0], L"<Error accessing system message>", 0x40u);
      v9[32] = 0;
    }
    LocalFree(*(HLOCAL *)Buffer);
  }
  else if ( v17 < 0x33 )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char **)v15,
      0x33u,
      v7,
      L"<The underlying system error could not be obtained>");
  }
  else
  {
    v10 = v15[0];
    v16 = 51;
    memmove_0(v15[0], L"<The underlying system error could not be obtained>", 0x66u);
    v10[51] = 0;
  }
  v11 = v15;
  if ( v17 > 7 )
    v11 = (void **)v15[0];
  std::wstring::_Append<wchar_t>(a2, v11, v16);
  std::wstring::_Tidy_deallocate(v15);
  return a2;
}

```

## disassembly

```asm
0x140023bd8  push    rbp
0x140023bda  push    rbx
0x140023bdb  push    rdi
0x140023bdc  lea     rbp, [rsp-47h]
0x140023be1  sub     rsp, 0A0h
0x140023be8  mov     rax, cs:__security_cookie
0x140023bef  xor     rax, rsp
0x140023bf2  mov     [rbp+57h+var_18], rax
0x140023bf6  mov     ebx, r9d
0x140023bf9  mov     rdi, rdx
0x140023bfc  mov     [rbp+57h+var_60], rdx
0x140023c00  mov     [rbp+57h+var_70], 0
0x140023c07  mov     rdx, r8
0x140023c0a  mov     rcx, rdi
0x140023c0d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140023c12  mov     [rbp+57h+var_70], 1
0x140023c19  mov     r8d, 2
0x140023c1f  lea     rdx, asc_1400A0EA4; ": "
0x140023c26  mov     rcx, rdi; Src
0x140023c29  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140023c2e  nop
0x140023c2f  xorps   xmm0, xmm0
0x140023c32  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x140023c36  mov     [rbp+57h+var_48], 0
0x140023c3e  mov     [rbp+57h+var_40], 7
0x140023c46  xor     eax, eax
0x140023c48  mov     word ptr [rbp+57h+var_58], ax
0x140023c4c  mov     [rbp+57h+var_70], 3
0x140023c53  mov     qword ptr [rbp+57h+Buffer], rax
0x140023c57  mov     [rsp+0B0h+Arguments], rax; Arguments
0x140023c5c  mov     [rsp+0B0h+nSize], eax; nSize
0x140023c60  lea     rax, [rbp+57h+Buffer]
0x140023c64  mov     [rsp+0B0h+lpBuffer], rax; lpBuffer
0x140023c69  xor     r9d, r9d; dwLanguageId
0x140023c6c  mov     r8d, ebx; dwMessageId
0x140023c6f  xor     edx, edx; lpSource
0x140023c71  mov     ecx, 1100h; dwFlags
0x140023c76  call    cs:__imp_FormatMessageW
0x140023c7c  mov     ebx, eax
0x140023c7e  test    eax, eax
0x140023c80  jz      loc_140023D2C
0x140023c86  mov     rcx, qword ptr [rbp+57h+Buffer]; hMem
0x140023c8a  call    cs:__imp_LocalLock
0x140023c90  test    rax, rax
0x140023c93  jz      short loc_140023CD8
0x140023c95  xorps   xmm0, xmm0
0x140023c98  movups  [rbp+57h+var_38], xmm0
0x140023c9c  xorps   xmm1, xmm1
0x140023c9f  movdqu  [rbp+57h+var_28], xmm1
0x140023ca4  mov     r8d, ebx
0x140023ca7  mov     rdx, qword ptr [rbp+57h+Buffer]
0x140023cab  lea     rcx, [rbp+57h+var_38]
0x140023caf  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140023cb4  nop
0x140023cb5  mov     rcx, qword ptr [rbp+57h+Buffer]; hMem
0x140023cb9  call    cs:__imp_LocalUnlock
0x140023cbf  lea     rdx, [rbp+57h+var_38]
0x140023cc3  lea     rcx, [rbp+57h+var_58]
0x140023cc7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140023ccc  nop
0x140023ccd  lea     rcx, [rbp+57h+var_38]
0x140023cd1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140023cd6  jmp     short loc_140023D20
0x140023cd8  mov     edx, 20h ; ' '
0x140023cdd  cmp     [rbp+57h+var_40], rdx
0x140023ce1  jb      short loc_140023D10
0x140023ce3  lea     rbx, [rbp+57h+var_58]
0x140023ce7  cmp     [rbp+57h+var_40], 7
0x140023cec  cmova   rbx, [rbp+57h+var_58]
0x140023cf1  mov     [rbp+57h+var_48], rdx
0x140023cf5  lea     r8d, [rdx+20h]; Size
0x140023cf9  lea     rdx, aErrorAccessing; "<Error accessing system message>"
0x140023d00  mov     rcx, rbx; void *
0x140023d03  call    memmove_0
0x140023d08  xor     eax, eax
0x140023d0a  mov     [rbx+40h], ax
0x140023d0e  jmp     short loc_140023D20
0x140023d10  lea     r9, aErrorAccessing; "<Error accessing system message>"
0x140023d17  lea     rcx, [rbp+57h+var_58]
0x140023d1b  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140023d20  mov     rcx, qword ptr [rbp+57h+Buffer]; hMem
0x140023d24  call    cs:__imp_LocalFree
0x140023d2a  jmp     short loc_140023D74
0x140023d2c  mov     edx, 33h ; '3'
0x140023d31  cmp     [rbp+57h+var_40], rdx
0x140023d35  jb      short loc_140023D64
0x140023d37  lea     rbx, [rbp+57h+var_58]
0x140023d3b  cmp     [rbp+57h+var_40], 7
0x140023d40  cmova   rbx, [rbp+57h+var_58]
0x140023d45  mov     [rbp+57h+var_48], rdx
0x140023d49  lea     r8d, [rdx+33h]; Size
0x140023d4d  lea     rdx, aTheUnderlyingS; "<The underlying system error could not "...
0x140023d54  mov     rcx, rbx; void *
0x140023d57  call    memmove_0
0x140023d5c  xor     eax, eax
0x140023d5e  mov     [rbx+66h], ax
0x140023d62  jmp     short loc_140023D74
0x140023d64  lea     r9, aTheUnderlyingS; "<The underlying system error could not "...
0x140023d6b  lea     rcx, [rbp+57h+var_58]
0x140023d6f  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140023d74  lea     rdx, [rbp+57h+var_58]
0x140023d78  cmp     [rbp+57h+var_40], 7
0x140023d7d  cmova   rdx, [rbp+57h+var_58]
0x140023d82  mov     r8, [rbp+57h+var_48]
0x140023d86  mov     rcx, rdi; Src
0x140023d89  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140023d8e  nop
0x140023d8f  lea     rcx, [rbp+57h+var_58]
0x140023d93  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140023d98  mov     rax, rdi
0x140023d9b  mov     rcx, [rbp+57h+var_18]
0x140023d9f  xor     rcx, rsp; StackCookie
0x140023da2  call    __security_check_cookie
0x140023da7  add     rsp, 0A0h
0x140023dae  pop     rdi
0x140023daf  pop     rbx
0x140023db0  pop     rbp
0x140023db1  retn
```
