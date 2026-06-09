# Record_InternalError_w

- ea: `0x14003f8e0`
- end: `0x14003fa86`
- name: `Record_InternalError_w`
- size: `422`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `10`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d0a0`
- `0x140010258`
- `0x1400117f4`
- `0x14001c9e4`
- `0x140040448`
- `0x140041b40`
- `0x14004258c`
- `0x1400427e4`
- `0x140043900`
- `0x140043fd0`

## callees

- `0x140001abc`
- `0x14001a420`
- `0x14003dda0`
- `0x14003de10`
- `0x14003e7c4`
- `0x14003f8e0`
- `0x140113220`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x14003fa2e`
- `ADVAPI32!EventEnabled` at `0x14003fa2e`
- `KERNEL32!EnterCriticalSection` at `0x14003f969`
- `KERNEL32!EnterCriticalSection` at `0x14003f969`
- `KERNEL32!LeaveCriticalSection` at `0x14003fa1a`
- `KERNEL32!LeaveCriticalSection` at `0x14003fa1a`
- `KERNEL32!GetCurrentThreadId` at `0x14003f997`
- `KERNEL32!GetCurrentThreadId` at `0x14003f997`
- `msvcrt!_vsnwprintf_s` at `0x14003f93f`
- `msvcrt!_vsnwprintf_s` at `0x14003f93f`

## pseudocode

```c
BOOLEAN Record_InternalError_w(char *a1, int a2, const wchar_t *a3, ...)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rsi
  unsigned __int64 v8; // r8
  BOOLEAN result; // al
  __int64 v10; // [rsp+30h] [rbp-858h]
  wchar_t Buffer[1024]; // [rsp+40h] [rbp-848h] BYREF
  va_list va; // [rsp+8A8h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( !a3 || !*a3 )
  {
    Buffer[0] = 0;
    v5 = 0;
    goto LABEL_6;
  }
  v5 = _vsnwprintf_s(Buffer, 0x400u, 0xFFFFFFFFFFFFFFFFuLL, a3, va);
  v10 = v5;
  if ( v5 == -1 )
  {
    v5 = 1023;
LABEL_6:
    LODWORD(v10) = v5;
  }
  EnterCriticalSection(&CriticalSection);
  try
  {
    try
    {
      std::vector<ErrorRecord>::resize(v6, ((qword_1401C65E0 - (__int64)qword_1401C65D8) >> 6) + 1);
      v7 = qword_1401C65E0;
      *(_DWORD *)(v7 - 64) = GetCurrentThreadId();
      *(_BYTE *)(v7 - 60) = 1;
      *(_DWORD *)(v7 - 56) = -1;
      *(_DWORD *)(v7 - 52) = -2147467259;
      *(_DWORD *)(v7 - 40) = a2;
      ErrorRecord::MakeDeepStringCopy((char **)(v7 - 48), a1, v8);
      ErrorRecord::MakeDeepStringCopy((unsigned __int16 **)(v7 - 32), Buffer, 0xFFFFFFFFFFFFFFFFuLL);
      operator delete(*(void **)(v7 - 24));
      *(_QWORD *)(v7 - 24) = 0;
      operator delete(*(void **)(v7 - 16));
      *(_QWORD *)(v7 - 16) = 0;
      operator delete(*(void **)(v7 - 8));
      *(_QWORD *)(v7 - 8) = 0;
    }
    catch ( std::bad_alloc )
    {
      Log_Text_F((__int64)"base\\winsat\\exe\\logging.cpp", 1482, "ERROR: cannot allocate memory for error record");
      v5 = v10;
    }
  }
  catch ( ... )
  {
    Log_Text_F((__int64)"base\\winsat\\exe\\logging.cpp", 1486, "ERROR: unhandled general exception");
    v5 = v10;
  }
  LeaveCriticalSection(&CriticalSection);
  result = EventEnabled(WINSAT_ETW_PROVIDER_Context, &InternalErrorEv);
  if ( result && v5 <= 0xFFFF && (Microsoft_Windows_WindowsSystemAssessmentToolEnableBits & 2) != 0 )
    return McTemplateU0hzr0_EventWriteTransfer(&WINSAT_ETW_PROVIDER_Context, &InternalErrorEv, v5 + 1, Buffer);
  return result;
}

```

## disassembly

```asm
0x14003f8e0  mov     r11, rsp
0x14003f8e3  mov     [r11+18h], r8
0x14003f8e7  mov     [r11+20h], r9
0x14003f8eb  push    rbx
0x14003f8ec  push    rsi
0x14003f8ed  push    rdi
0x14003f8ee  push    r12
0x14003f8f0  push    r14
0x14003f8f2  push    r15
0x14003f8f4  sub     rsp, 858h
0x14003f8fb  mov     rax, cs:__security_cookie
0x14003f902  xor     rax, rsp
0x14003f905  mov     [rsp+888h+var_48], rax
0x14003f90d  mov     r15d, edx
0x14003f910  mov     r12, rcx
0x14003f913  xor     edi, edi
0x14003f915  test    r8, r8
0x14003f918  jz      short loc_14003F957
0x14003f91a  cmp     [r8], di
0x14003f91e  jz      short loc_14003F957
0x14003f920  mov     [rsp+888h+var_858], rdi
0x14003f925  lea     rax, [r11+20h]
0x14003f929  mov     [rsp+888h+ArgList], rax; ArgList
0x14003f92e  mov     r9, r8; Format
0x14003f931  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003f935  mov     edx, 400h; BufferCount
0x14003f93a  lea     rcx, [rsp+888h+Buffer]; Buffer
0x14003f93f  call    cs:__imp__vsnwprintf_s
0x14003f945  mov     ebx, eax
0x14003f947  mov     dword ptr [rsp+888h+var_858], eax
0x14003f94b  cmp     eax, 0FFFFFFFFh
0x14003f94e  jnz     short loc_14003F962
0x14003f950  mov     ebx, 3FFh
0x14003f955  jmp     short loc_14003F95E
0x14003f957  mov     [rsp+888h+Buffer], di
0x14003f95c  mov     ebx, edi
0x14003f95e  mov     dword ptr [rsp+888h+var_858], ebx
0x14003f962  lea     rcx, CriticalSection; lpCriticalSection
0x14003f969  call    cs:__imp_EnterCriticalSection
0x14003f96f  nop
0x14003f970  mov     rdx, cs:qword_1401C65E0
0x14003f977  sub     rdx, cs:qword_1401C65D8
0x14003f97e  sar     rdx, 6
0x14003f982  mov     r14d, 1
0x14003f988  add     rdx, r14
0x14003f98b  call    ?resize@?$vector@VErrorRecord@@V?$allocator@VErrorRecord@@@std@@@std@@QEAAX_K@Z; std::vector<ErrorRecord>::resize(unsigned __int64)
0x14003f990  mov     rsi, cs:qword_1401C65E0
0x14003f997  call    cs:__imp_GetCurrentThreadId
0x14003f99d  mov     [rsi-40h], eax
0x14003f9a0  mov     [rsi-3Ch], r14b
0x14003f9a4  mov     dword ptr [rsi-38h], 0FFFFFFFFh
0x14003f9ab  mov     dword ptr [rsi-34h], 80004005h
0x14003f9b2  mov     [rsi-28h], r15d
0x14003f9b6  lea     rcx, [rsi-30h]; char **
0x14003f9ba  mov     rdx, r12; char *
0x14003f9bd  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEADPEBD_K@Z; ErrorRecord::MakeDeepStringCopy(char * &,char const *,unsigned __int64)
0x14003f9c2  lea     rcx, [rsi-20h]; unsigned __int16 **
0x14003f9c6  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x14003f9ca  lea     rdx, [rsp+888h+Buffer]; unsigned __int16 *
0x14003f9cf  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEAGPEBG_K@Z; ErrorRecord::MakeDeepStringCopy(ushort * &,ushort const *,unsigned __int64)
0x14003f9d4  mov     rcx, [rsi-18h]; Block
0x14003f9d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003f9dd  mov     [rsi-18h], rdi
0x14003f9e1  mov     rcx, [rsi-10h]; Block
0x14003f9e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003f9ea  mov     [rsi-10h], rdi
0x14003f9ee  mov     rcx, [rsi-8]; Block
0x14003f9f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003f9f7  mov     [rsi-8], rdi
0x14003f9fb  jmp     short loc_14003FA07
0x14003f9fd  mov     r14d, 1
0x14003fa03  mov     ebx, dword ptr [rsp+888h+var_858]
0x14003fa07  jmp     short loc_14003FA13
0x14003fa09  mov     r14d, 1
0x14003fa0f  mov     ebx, dword ptr [rsp+888h+var_858]
0x14003fa13  lea     rcx, CriticalSection; lpCriticalSection
0x14003fa1a  call    cs:__imp_LeaveCriticalSection
0x14003fa20  lea     rdx, InternalErrorEv; EventDescriptor
0x14003fa27  mov     rcx, cs:WINSAT_ETW_PROVIDER_Context; RegHandle
0x14003fa2e  call    cs:__imp_EventEnabled
0x14003fa34  test    al, al
0x14003fa36  jz      short loc_14003FA65
0x14003fa38  cmp     ebx, 0FFFFh
0x14003fa3e  ja      short loc_14003FA65
0x14003fa40  test    cs:Microsoft_Windows_WindowsSystemAssessmentToolEnableBits, 2
0x14003fa47  jz      short loc_14003FA65
0x14003fa49  lea     r8d, [r14+rbx]
0x14003fa4d  lea     r9, [rsp+888h+Buffer]
0x14003fa52  lea     rdx, InternalErrorEv
0x14003fa59  lea     rcx, WINSAT_ETW_PROVIDER_Context
0x14003fa60  call    McTemplateU0hzr0_EventWriteTransfer
0x14003fa65  mov     rcx, [rsp+888h+var_48]
0x14003fa6d  xor     rcx, rsp; StackCookie
0x14003fa70  call    __security_check_cookie
0x14003fa75  add     rsp, 858h
0x14003fa7c  pop     r15
0x14003fa7e  pop     r14
0x14003fa80  pop     r12
0x14003fa82  pop     rdi
0x14003fa83  pop     rsi
0x14003fa84  pop     rbx
0x14003fa85  retn
```
