# Uev::SystemException::RenderMessage(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong)

- ea: `0x14000de80`
- end: `0x14000e090`
- name: `?RenderMessage@SystemException@Uev@@CA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@K@Z`
- size: `528`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000d2d8`

## callees

- `0x140003e50`
- `0x140004a6c`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000c1cc`
- `0x14000c2b8`
- `0x14000c3a4`
- `0x14000d7b4`
- `0x14000de80`

## import_xrefs

- `KERNEL32!LocalLock` at `0x14000df39`
- `KERNEL32!LocalLock` at `0x14000df39`
- `KERNEL32!FormatMessageW` at `0x14000df24`
- `KERNEL32!FormatMessageW` at `0x14000df24`
- `KERNEL32!LocalFree` at `0x14000dfe5`
- `KERNEL32!LocalFree` at `0x14000dfe5`
- `KERNEL32!LocalUnlock` at `0x14000df70`
- `KERNEL32!LocalUnlock` at `0x14000df70`

## string_xrefs

- `0x14000dfb8`: `<Error accessing system message>`
- `0x14000dfcf`: `<Error accessing system message>`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Uev::SystemException::RenderMessage(_QWORD *Src, __int64 a2, DWORD a3)
{
  DWORD v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r8
  void **v8; // rdx
  _QWORD *result; // rax
  void *v10[2]; // [rsp+48h] [rbp-60h] BYREF
  unsigned __int64 v11; // [rsp+58h] [rbp-50h]
  unsigned __int64 v12; // [rsp+60h] [rbp-48h]
  _QWORD *v13; // [rsp+68h] [rbp-40h]
  WCHAR Buffer[4]; // [rsp+70h] [rbp-38h] BYREF
  _OWORD v15[2]; // [rsp+78h] [rbp-30h] BYREF

  v13 = Src;
  std::wstring::wstring((__int64)Src, a2);
  try
  {
    std::wstring::_Append<wchar_t>(Src, L": ", 2u);
    *(_OWORD *)v10 = 0;
    v11 = 0;
    v12 = 7;
    LOWORD(v10[0]) = 0;
    *(_QWORD *)Buffer = 0;
    v5 = FormatMessageW(0x1100u, 0, a3, 0, Buffer, 0, 0);
    if ( v5 )
    {
      if ( LocalLock(*(HLOCAL *)Buffer) )
      {
        memset(v15, 0, sizeof(v15));
        std::wstring::_Construct<1,wchar_t *>(v15, *(const void **)Buffer, v5);
        LocalUnlock(*(HLOCAL *)Buffer);
        std::wstring::operator=(v10, v15);
        std::wstring::_Tidy_deallocate(v15);
      }
      else
      {
        std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
          (char **)v10,
          0x20u,
          v7,
          L"<Error accessing system message>");
      }
      LocalFree(*(HLOCAL *)Buffer);
    }
    else
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
        (char **)v10,
        0x33u,
        v6,
        L"<The underlying system error could not be obtained>");
    }
    v8 = v10;
    if ( v12 > 7 )
      v8 = (void **)v10[0];
    std::wstring::_Append<wchar_t>(Src, v8, v11);
    std::wstring::_Tidy_deallocate(v10);
    result = Src;
  }
  catch ( ... )
  {
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x14000de80  mov     [rsp+arg_18], rbx
0x14000de85  push    rdi
0x14000de86  sub     rsp, 0A0h
0x14000de8d  mov     rax, cs:__security_cookie
0x14000de94  xor     rax, rsp
0x14000de97  mov     [rsp+0A8h+var_10], rax
0x14000de9f  mov     ebx, r8d
0x14000dea2  mov     rdi, rcx
0x14000dea5  mov     [rsp+0A8h+var_40], rcx
0x14000deaa  mov     [rsp+0A8h+var_68], 1
0x14000deb2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000deb7  nop
0x14000deb8  mov     [rsp+0A8h+var_68], 1
0x14000dec0  mov     r8d, 2
0x14000dec6  lea     rdx, asc_1400A0EA4; ": "
0x14000decd  mov     rcx, rdi; Src
0x14000ded0  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14000ded5  nop
0x14000ded6  xorps   xmm0, xmm0
0x14000ded9  movups  xmmword ptr [rsp+0A8h+var_60], xmm0
0x14000dede  mov     [rsp+0A8h+var_50], 0
0x14000dee7  mov     [rsp+0A8h+var_48], 7
0x14000def0  xor     eax, eax
0x14000def2  mov     word ptr [rsp+0A8h+var_60], ax
0x14000def7  mov     [rsp+0A8h+var_68], 3
0x14000deff  mov     qword ptr [rsp+0A8h+Buffer], rax
0x14000df04  mov     [rsp+0A8h+Arguments], rax; Arguments
0x14000df09  mov     [rsp+0A8h+nSize], eax; nSize
0x14000df0d  lea     rax, [rsp+0A8h+Buffer]
0x14000df12  mov     [rsp+0A8h+lpBuffer], rax; lpBuffer
0x14000df17  xor     r9d, r9d; dwLanguageId
0x14000df1a  mov     r8d, ebx; dwMessageId
0x14000df1d  xor     edx, edx; lpSource
0x14000df1f  mov     ecx, 1100h; dwFlags
0x14000df24  call    cs:__imp_FormatMessageW
0x14000df2a  mov     ebx, eax
0x14000df2c  test    eax, eax
0x14000df2e  jz      loc_14000DFED
0x14000df34  mov     rcx, qword ptr [rsp+0A8h+Buffer]; hMem
0x14000df39  call    cs:__imp_LocalLock
0x14000df3f  test    rax, rax
0x14000df42  jz      short loc_14000DF92
0x14000df44  xorps   xmm0, xmm0
0x14000df47  movups  [rsp+0A8h+var_30], xmm0
0x14000df4c  xorps   xmm1, xmm1
0x14000df4f  movdqu  [rsp+0A8h+var_20], xmm1
0x14000df58  mov     r8d, ebx
0x14000df5b  mov     rdx, qword ptr [rsp+0A8h+Buffer]
0x14000df60  lea     rcx, [rsp+0A8h+var_30]
0x14000df65  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14000df6a  nop
0x14000df6b  mov     rcx, qword ptr [rsp+0A8h+Buffer]; hMem
0x14000df70  call    cs:__imp_LocalUnlock
0x14000df76  lea     rdx, [rsp+0A8h+var_30]
0x14000df7b  lea     rcx, [rsp+0A8h+var_60]
0x14000df80  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000df85  nop
0x14000df86  lea     rcx, [rsp+0A8h+var_30]
0x14000df8b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000df90  jmp     short loc_14000DFE0
0x14000df92  mov     edx, 20h ; ' '
0x14000df97  cmp     [rsp+0A8h+var_48], rdx
0x14000df9c  jb      short loc_14000DFCF
0x14000df9e  lea     rbx, [rsp+0A8h+var_60]
0x14000dfa3  cmp     [rsp+0A8h+var_48], 7
0x14000dfa9  cmova   rbx, [rsp+0A8h+var_60]
0x14000dfaf  mov     [rsp+0A8h+var_50], rdx
0x14000dfb4  lea     r8d, [rdx+20h]; Size
0x14000dfb8  lea     rdx, aErrorAccessing; "<Error accessing system message>"
0x14000dfbf  mov     rcx, rbx; void *
0x14000dfc2  call    memmove_0
0x14000dfc7  xor     eax, eax
0x14000dfc9  mov     [rbx+40h], ax
0x14000dfcd  jmp     short loc_14000DFE0
0x14000dfcf  lea     r9, aErrorAccessing; "<Error accessing system message>"
0x14000dfd6  lea     rcx, [rsp+0A8h+var_60]
0x14000dfdb  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x14000dfe0  mov     rcx, qword ptr [rsp+0A8h+Buffer]; hMem
0x14000dfe5  call    cs:__imp_LocalFree
0x14000dfeb  jmp     short loc_14000E03B
0x14000dfed  mov     edx, 33h ; '3'
0x14000dff2  cmp     [rsp+0A8h+var_48], rdx
0x14000dff7  jb      short loc_14000E02A
0x14000dff9  lea     rbx, [rsp+0A8h+var_60]
0x14000dffe  cmp     [rsp+0A8h+var_48], 7
0x14000e004  cmova   rbx, [rsp+0A8h+var_60]
0x14000e00a  mov     [rsp+0A8h+var_50], rdx
0x14000e00f  lea     r8d, [rdx+33h]; Size
0x14000e013  lea     rdx, aTheUnderlyingS; "<The underlying system error could not "...
0x14000e01a  mov     rcx, rbx; void *
0x14000e01d  call    memmove_0
0x14000e022  xor     eax, eax
0x14000e024  mov     [rbx+66h], ax
0x14000e028  jmp     short loc_14000E03B
0x14000e02a  lea     r9, aTheUnderlyingS; "<The underlying system error could not "...
0x14000e031  lea     rcx, [rsp+0A8h+var_60]
0x14000e036  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x14000e03b  lea     rdx, [rsp+0A8h+var_60]
0x14000e040  cmp     [rsp+0A8h+var_48], 7
0x14000e046  cmova   rdx, [rsp+0A8h+var_60]
0x14000e04c  mov     r8, [rsp+0A8h+var_50]
0x14000e051  mov     rcx, rdi; Src
0x14000e054  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14000e059  nop
0x14000e05a  lea     rcx, [rsp+0A8h+var_60]
0x14000e05f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000e064  nop
0x14000e065  mov     rax, rdi
0x14000e068  jmp     short loc_14000E06F
0x14000e06a  mov     rax, [rsp+0A8h+var_40]
0x14000e06f  mov     rcx, [rsp+0A8h+var_10]
0x14000e077  xor     rcx, rsp; StackCookie
0x14000e07a  call    __security_check_cookie
0x14000e07f  mov     rbx, [rsp+0A8h+arg_18]
0x14000e087  add     rsp, 0A0h
0x14000e08e  pop     rdi
0x14000e08f  retn
```
