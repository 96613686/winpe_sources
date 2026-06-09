# Record_FailingHresult_w

- ea: `0x14003f698`
- end: `0x14003f8d9`
- name: `Record_FailingHresult_w`
- size: `577`
- prototype: ``
- caller_count: `20`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14004211c`
- `0x14007e498`
- `0x14007eab8`
- `0x14007ee8c`
- `0x14007f198`
- `0x14007f5ec`
- `0x14007fef4`
- `0x14008088c`
- `0x140080e58`
- `0x140080f04`
- `0x140082280`
- `0x140082a40`
- `0x140082ea8`
- `0x140084410`
- `0x1400848f0`
- `0x140084ed0`
- `0x140085624`
- `0x140086f00`
- `0x140087420`
- `0x140087c40`

## callees

- `0x140001abc`
- `0x14003dda0`
- `0x14003de10`
- `0x14003e7c4`
- `0x14003ec14`
- `0x14003f030`
- `0x14003f698`
- `0x140113220`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x14003f810`
- `ADVAPI32!EventEnabled` at `0x14003f810`
- `KERNEL32!EnterCriticalSection` at `0x14003f723`
- `KERNEL32!EnterCriticalSection` at `0x14003f723`
- `KERNEL32!LeaveCriticalSection` at `0x14003f7fc`
- `KERNEL32!LeaveCriticalSection` at `0x14003f7fc`
- `KERNEL32!GetCurrentThreadId` at `0x14003f74f`
- `KERNEL32!GetCurrentThreadId` at `0x14003f74f`
- `msvcrt!_vsnwprintf_s` at `0x14003f706`
- `msvcrt!_vsnwprintf_s` at `0x14003f706`

## pseudocode

```c
__int64 Record_FailingHresult_w(const char *a1, int a2, int a3, const unsigned __int16 *a4, const wchar_t *a5, ...)
{
  const unsigned __int16 *v5; // r12
  unsigned int v6; // r15d
  __int64 v7; // rdi
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // r14
  unsigned __int64 v11; // r8
  int v12; // edx
  wchar_t Buffer[1024]; // [rsp+70h] [rbp-848h] BYREF
  va_list va; // [rsp+8E8h] [rbp+30h] BYREF

  va_start(va, a5);
  v5 = a4;
  v6 = a3;
  if ( a3 < 0 )
  {
    v7 = -1;
    v8 = _vsnwprintf_s(Buffer, 0x400u, 0xFFFFFFFFFFFFFFFFuLL, a5, va);
    if ( v8 == -1 )
      v8 = 1023;
    EnterCriticalSection(&CriticalSection);
    try
    {
      try
      {
        std::vector<ErrorRecord>::resize(v9, ((qword_1401C65E0 - (__int64)qword_1401C65D8) >> 6) + 1);
        v10 = qword_1401C65E0;
        *(_DWORD *)(v10 - 64) = GetCurrentThreadId();
        *(_BYTE *)(v10 - 60) = 0;
        *(_DWORD *)(v10 - 56) = 0;
        *(_DWORD *)(v10 - 52) = v6;
        *(_DWORD *)(v10 - 40) = a2;
        ErrorRecord::MakeDeepStringCopy((char **)(v10 - 48), a1, v11);
        ErrorRecord::MakeDeepStringCopy((unsigned __int16 **)(v10 - 32), v5, 0xFFFFFFFFFFFFFFFFuLL);
        ErrorRecord::MakeDeepStringCopy((unsigned __int16 **)(v10 - 24), Buffer, v8);
        operator delete(*(void **)(v10 - 16));
        *(_QWORD *)(v10 - 16) = 0;
        operator delete(*(void **)(v10 - 8));
        *(_QWORD *)(v10 - 8) = 0;
      }
      catch ( std::bad_alloc )
      {
        Log_Text_F((__int64)"base\\winsat\\exe\\logging.cpp", 1550, "ERROR: cannot allocate memory for error record");
        v7 = -1;
        v6 = a3;
        v5 = a4;
      }
    }
    catch ( ... )
    {
      Log_Text_F((__int64)"base\\winsat\\exe\\logging.cpp", 1554, "ERROR: unhandled general exception");
      v7 = -1;
      v6 = a3;
      v5 = a4;
    }
    LeaveCriticalSection(&CriticalSection);
    if ( EventEnabled(WINSAT_ETW_PROVIDER_Context, &FailingHresultErrorEv) )
    {
      do
        ++v7;
      while ( v5[v7] );
      if ( (unsigned __int16)v7 >= 0x400u )
      {
        Log_Text_F((__int64)"base\\winsat\\exe\\logging.cpp", 1571, "error message is too large");
      }
      else if ( (unsigned int)v8 <= 0x3FF )
      {
        if ( (Microsoft_Windows_WindowsSystemAssessmentToolEnableBits & 2) != 0 )
          McTemplateU0dhzr1hzr3_EventWriteTransfer(
            (unsigned int)&WINSAT_ETW_PROVIDER_Context,
            v12,
            v6,
            v7 + 1,
            (__int64)v5,
            v8 + 1,
            (__int64)Buffer);
        return v6;
      }
      if ( v8 < 1024 )
      {
        if ( v8 < 0 )
          Log_Text_F((__int64)"base\\winsat\\exe\\logging.cpp", 1577, "can't message size is invalid");
      }
      else
      {
        Log_Text_F((__int64)"base\\winsat\\exe\\logging.cpp", 1574, "can't message is too large");
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14003f698  mov     r11, rsp
0x14003f69b  push    rbx
0x14003f69c  push    rsi
0x14003f69d  push    rdi
0x14003f69e  push    r12
0x14003f6a0  push    r13
0x14003f6a2  push    r14
0x14003f6a4  push    r15
0x14003f6a6  sub     rsp, 880h
0x14003f6ad  mov     rax, cs:__security_cookie
0x14003f6b4  xor     rax, rsp
0x14003f6b7  mov     [rsp+8B8h+var_48], rax
0x14003f6bf  mov     r12, r9
0x14003f6c2  mov     r15d, r8d
0x14003f6c5  mov     [rsp+8B8h+var_868], edx
0x14003f6c9  mov     [rsp+8B8h+var_858], rcx
0x14003f6ce  mov     [rsp+8B8h+var_878], r8d
0x14003f6d3  mov     [rsp+8B8h+var_860], r9
0x14003f6d8  xor     esi, esi
0x14003f6da  test    r8d, r8d
0x14003f6dd  jns     loc_14003F8B3
0x14003f6e3  mov     [rsp+8B8h+var_870], rsi
0x14003f6e8  lea     rax, [r11+30h]
0x14003f6ec  mov     [rsp+8B8h+ArgList], rax; ArgList
0x14003f6f1  mov     r9, [r11+28h]; Format
0x14003f6f5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003f6f9  mov     r8, rdi; MaxCount
0x14003f6fc  mov     edx, 400h; BufferCount
0x14003f701  lea     rcx, [rsp+8B8h+Buffer]; Buffer
0x14003f706  call    cs:__imp__vsnwprintf_s
0x14003f70c  mov     ebx, eax
0x14003f70e  mov     eax, 3FFh
0x14003f713  cmp     ebx, edi
0x14003f715  cmovz   ebx, eax
0x14003f718  mov     dword ptr [rsp+8B8h+var_870], ebx
0x14003f71c  lea     rcx, CriticalSection; lpCriticalSection
0x14003f723  call    cs:__imp_EnterCriticalSection
0x14003f729  nop
0x14003f72a  mov     rdx, cs:qword_1401C65E0
0x14003f731  sub     rdx, cs:qword_1401C65D8
0x14003f738  sar     rdx, 6
0x14003f73c  lea     r13d, [rsi+1]
0x14003f740  add     rdx, r13
0x14003f743  call    ?resize@?$vector@VErrorRecord@@V?$allocator@VErrorRecord@@@std@@@std@@QEAAX_K@Z; std::vector<ErrorRecord>::resize(unsigned __int64)
0x14003f748  mov     r14, cs:qword_1401C65E0
0x14003f74f  call    cs:__imp_GetCurrentThreadId
0x14003f755  mov     [r14-40h], eax
0x14003f759  mov     [r14-3Ch], sil
0x14003f75d  mov     [r14-38h], esi
0x14003f761  mov     [r14-34h], r15d
0x14003f765  mov     eax, [rsp+8B8h+var_868]
0x14003f769  mov     [r14-28h], eax
0x14003f76d  lea     rcx, [r14-30h]; char **
0x14003f771  mov     rdx, [rsp+8B8h+var_858]; char *
0x14003f776  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEADPEBD_K@Z; ErrorRecord::MakeDeepStringCopy(char * &,char const *,unsigned __int64)
0x14003f77b  lea     rcx, [r14-20h]; unsigned __int16 **
0x14003f77f  mov     r8, rdi; unsigned __int64
0x14003f782  mov     rdx, r12; unsigned __int16 *
0x14003f785  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEAGPEBG_K@Z; ErrorRecord::MakeDeepStringCopy(ushort * &,ushort const *,unsigned __int64)
0x14003f78a  movsxd  r8, ebx; unsigned __int64
0x14003f78d  lea     rcx, [r14-18h]; unsigned __int16 **
0x14003f791  lea     rdx, [rsp+8B8h+Buffer]; unsigned __int16 *
0x14003f796  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEAGPEBG_K@Z; ErrorRecord::MakeDeepStringCopy(ushort * &,ushort const *,unsigned __int64)
0x14003f79b  mov     rcx, [r14-10h]; Block
0x14003f79f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003f7a4  mov     [r14-10h], rsi
0x14003f7a8  mov     rcx, [r14-8]; Block
0x14003f7ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003f7b1  mov     [r14-8], rsi
0x14003f7b5  jmp     short loc_14003F7CF
0x14003f7b7  xor     esi, esi
0x14003f7b9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003f7bd  lea     r13d, [rsi+1]
0x14003f7c1  mov     ebx, dword ptr [rsp+8B8h+var_870]
0x14003f7c5  mov     r15d, [rsp+8B8h+var_878]
0x14003f7ca  mov     r12, [rsp+8B8h+var_860]
0x14003f7cf  mov     r14d, 400h
0x14003f7d5  jmp     short loc_14003F7F5
0x14003f7d7  xor     esi, esi
0x14003f7d9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003f7dd  mov     r14d, 400h
0x14003f7e3  lea     r13d, [rsi+1]
0x14003f7e7  mov     ebx, dword ptr [rsp+8B8h+var_870]
0x14003f7eb  mov     r15d, [rsp+8B8h+var_878]
0x14003f7f0  mov     r12, [rsp+8B8h+var_860]
0x14003f7f5  lea     rcx, CriticalSection; lpCriticalSection
0x14003f7fc  call    cs:__imp_LeaveCriticalSection
0x14003f802  lea     rdx, FailingHresultErrorEv; EventDescriptor
0x14003f809  mov     rcx, cs:WINSAT_ETW_PROVIDER_Context; RegHandle
0x14003f810  call    cs:__imp_EventEnabled
0x14003f816  test    al, al
0x14003f818  jz      loc_14003F8B3
0x14003f81e  inc     rdi
0x14003f821  cmp     [r12+rdi*2], si
0x14003f826  jnz     short loc_14003F81E
0x14003f828  cmp     di, r14w
0x14003f82c  jnb     short loc_14003F86C
0x14003f82e  cmp     ebx, 3FFh
0x14003f834  ja      short loc_14003F884
0x14003f836  test    cs:Microsoft_Windows_WindowsSystemAssessmentToolEnableBits, 2
0x14003f83d  jz      short loc_14003F8B3
0x14003f83f  add     bx, r13w
0x14003f843  lea     r9d, [rdi+r13]
0x14003f847  lea     rax, [rsp+8B8h+Buffer]
0x14003f84c  mov     [rsp+8B8h+var_888], rax
0x14003f851  mov     [rsp+8B8h+var_890], bx
0x14003f856  mov     [rsp+8B8h+ArgList], r12
0x14003f85b  mov     r8d, r15d
0x14003f85e  lea     rcx, WINSAT_ETW_PROVIDER_Context
0x14003f865  call    McTemplateU0dhzr1hzr3_EventWriteTransfer
0x14003f86a  jmp     short loc_14003F8B3
0x14003f86c  lea     r8, aErrorMessageIs; "error message is too large"
0x14003f873  mov     edx, 623h
0x14003f878  lea     rcx, aBaseWinsatExeL; "base\\winsat\\exe\\logging.cpp"
0x14003f87f  call    Log_Text_F
0x14003f884  cmp     ebx, r14d
0x14003f887  jl      short loc_14003F897
0x14003f889  lea     r8, aCanTMessageIsT; "can't message is too large"
0x14003f890  mov     edx, 626h
0x14003f895  jmp     short loc_14003F8A7
0x14003f897  test    ebx, ebx
0x14003f899  jns     short loc_14003F8B3
0x14003f89b  lea     r8, aCanTMessageSiz; "can't message size is invalid"
0x14003f8a2  mov     edx, 629h
0x14003f8a7  lea     rcx, aBaseWinsatExeL; "base\\winsat\\exe\\logging.cpp"
0x14003f8ae  call    Log_Text_F
0x14003f8b3  mov     eax, r15d
0x14003f8b6  mov     rcx, [rsp+8B8h+var_48]
0x14003f8be  xor     rcx, rsp; StackCookie
0x14003f8c1  call    __security_check_cookie
0x14003f8c6  add     rsp, 880h
0x14003f8cd  pop     r15
0x14003f8cf  pop     r14
0x14003f8d1  pop     r13
0x14003f8d3  pop     r12
0x14003f8d5  pop     rdi
0x14003f8d6  pop     rsi
0x14003f8d7  pop     rbx
0x14003f8d8  retn
```
