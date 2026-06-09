# PAL_System_ThreadFree(void *)

- ea: `0x18001c018`
- end: `0x18001c143`
- name: `?PAL_System_ThreadFree@@YAJPEAX@Z`
- size: `299`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800150c0`
- `0x18001bd9c`

## callees

- `0x180001180`
- `0x1800013f4`
- `0x18001c018`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c0a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c0a2`

## string_xrefs

- `0x18001c04d`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001c0e2`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001c034`: `PAL_System_ThreadFree`
- `0x18001c0d7`: `PAL_System_ThreadFree`
- `0x18001c0ed`: `Failed to CloseHandle on thread. GetLastError: 0x%x`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadFree(void *a1, __int64 a2, int a3, int a4)
{
  unsigned int v4; // ebx
  DWORD LastError; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  const char *v10; // [rsp+50h] [rbp-18h] BYREF
  const char *v11; // [rsp+58h] [rbp-10h] BYREF
  int v12; // [rsp+80h] [rbp+18h] BYREF
  int v13; // [rsp+88h] [rbp+20h] BYREF
  const char *v14; // [rsp+90h] [rbp+28h] BYREF
  const char *v15; // [rsp+98h] [rbp+30h] BYREF

  if ( a1 )
  {
    if ( CloseHandle(a1) )
    {
      return 0;
    }
    else
    {
      v4 = -2147467259;
      if ( (unsigned int)dword_1800EB958 > 2 )
      {
        LastError = GetLastError();
        v13 = 1570;
        v12 = LastError;
        v15 = "PAL_System_ThreadFree";
        v10 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
        v11 = "Failed to CloseHandle on thread. GetLastError: 0x%x";
        LODWORD(v14) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v6,
          (unsigned int)&dword_1800CD584,
          v7,
          v8,
          (__int64)&v11,
          (__int64)&v14,
          (__int64)&v10,
          (__int64)&v13,
          (__int64)&v15,
          (__int64)&v12);
      }
    }
  }
  else
  {
    if ( (unsigned int)dword_1800EB958 > 2 )
    {
      v12 = 1563;
      v14 = "PAL_System_ThreadFree";
      v15 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v10 = "NULL parameter passed";
      v13 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (unsigned int)byte_1800CD5D9,
        a3,
        a4,
        (__int64)&v10,
        (__int64)&v13,
        (__int64)&v15,
        (__int64)&v12,
        (__int64)&v14);
    }
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18001c018  mov     r11, rsp
0x18001c01b  push    rbp
0x18001c01c  push    rbx
0x18001c01d  mov     rbp, rsp
0x18001c020  sub     rsp, 68h
0x18001c024  test    rcx, rcx
0x18001c027  jnz     short loc_18001C0A2
0x18001c029  mov     eax, cs:dword_1800EB958
0x18001c02f  cmp     eax, 2
0x18001c032  jbe     short loc_18001C098
0x18001c034  lea     rax, aPalSystemThrea_2; "PAL_System_ThreadFree"
0x18001c03b  mov     [rbp+arg_0], 61Bh
0x18001c042  mov     [rbp+arg_10], rax
0x18001c046  lea     rdx, byte_1800CD5D9
0x18001c04d  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001c054  mov     ebx, 80004005h
0x18001c059  mov     [rbp+arg_18], rax
0x18001c05d  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001c064  mov     [rbp+var_18], rax
0x18001c068  lea     rax, [rbp+arg_10]
0x18001c06c  mov     [r11-38h], rax
0x18001c070  lea     rax, [rbp+arg_0]
0x18001c074  mov     [r11-40h], rax
0x18001c078  lea     rax, [rbp+arg_18]
0x18001c07c  mov     [r11-48h], rax
0x18001c080  lea     rax, [rbp+arg_8]
0x18001c084  mov     [r11-50h], rax
0x18001c088  lea     rax, [rbp+var_18]
0x18001c08c  mov     [r11-58h], rax
0x18001c090  mov     [rbp+arg_8], ebx
0x18001c093  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001c098  mov     ebx, 80070057h
0x18001c09d  jmp     loc_18001C13A
0x18001c0a2  call    cs:__imp_CloseHandle
0x18001c0a8  test    eax, eax
0x18001c0aa  jnz     loc_18001C138
0x18001c0b0  mov     eax, cs:dword_1800EB958
0x18001c0b6  mov     ebx, 80004005h
0x18001c0bb  cmp     eax, 2
0x18001c0be  jbe     short loc_18001C13A
0x18001c0c0  call    cs:__imp_GetLastError
0x18001c0c6  lea     rdx, dword_1800CD584
0x18001c0cd  mov     [rbp+arg_8], 622h
0x18001c0d4  mov     [rbp+arg_0], eax
0x18001c0d7  lea     rax, aPalSystemThrea_2; "PAL_System_ThreadFree"
0x18001c0de  mov     [rbp+arg_18], rax
0x18001c0e2  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001c0e9  mov     [rbp+var_18], rax
0x18001c0ed  lea     rax, aFailedToCloseh; "Failed to CloseHandle on thread. GetLas"...
0x18001c0f4  mov     [rbp+var_10], rax
0x18001c0f8  lea     rax, [rbp+arg_0]
0x18001c0fc  mov     [rsp+68h+var_20], rax
0x18001c101  lea     rax, [rbp+arg_18]
0x18001c105  mov     [rsp+68h+var_28], rax
0x18001c10a  lea     rax, [rbp+arg_8]
0x18001c10e  mov     [rsp+68h+var_30], rax
0x18001c113  lea     rax, [rbp+var_18]
0x18001c117  mov     [rsp+68h+var_38], rax
0x18001c11c  lea     rax, [rbp+arg_10]
0x18001c120  mov     [rsp+68h+var_40], rax
0x18001c125  lea     rax, [rbp+var_10]
0x18001c129  mov     [rsp+68h+var_48], rax
0x18001c12e  mov     dword ptr [rbp+arg_10], ebx
0x18001c131  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001c136  jmp     short loc_18001C13A
0x18001c138  xor     ebx, ebx
0x18001c13a  mov     eax, ebx
0x18001c13c  add     rsp, 68h
0x18001c140  pop     rbx
0x18001c141  pop     rbp
0x18001c142  retn
```
