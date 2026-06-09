# PAL_System_ThreadGetDeathCondition(ulong,void * *)

- ea: `0x18001c27c`
- end: `0x18001c361`
- name: `?PAL_System_ThreadGetDeathCondition@@YAJKPEAPEAX@Z`
- size: `229`
- prototype: `__int64 __fastcall(DWORD dwThreadId, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012b10`

## callees

- `0x1800015c0`
- `0x18001c27c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18001c2a8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18001c2a8`

## string_xrefs

- `0x18001c2e9`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001c2de`: `PAL_System_ThreadGetDeathCondition`
- `0x18001c2f4`: `Failed to open thread %#x. GetLastError: 0x%x`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadGetDeathCondition(DWORD dwThreadId, void **a2)
{
  unsigned int v4; // ebx
  HANDLE v5; // rax
  DWORD LastError; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int v11; // [rsp+60h] [rbp-20h] BYREF
  const char *v12; // [rsp+68h] [rbp-18h] BYREF
  const char *v13; // [rsp+70h] [rbp-10h] BYREF
  const char *v14; // [rsp+78h] [rbp-8h] BYREF
  DWORD v15; // [rsp+A8h] [rbp+28h] BYREF
  DWORD v16; // [rsp+B0h] [rbp+30h] BYREF
  int v17; // [rsp+B8h] [rbp+38h] BYREF

  if ( a2 )
  {
    v5 = OpenThread(0x100000u, 0, dwThreadId);
    if ( v5 )
    {
      *a2 = v5;
      return 0;
    }
    else
    {
      v4 = -2147467259;
      if ( (unsigned int)dword_1800EB958 > 2 )
      {
        LastError = GetLastError();
        v16 = dwThreadId;
        v15 = LastError;
        v12 = "PAL_System_ThreadGetDeathCondition";
        v13 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
        v14 = "Failed to open thread %#x. GetLastError: 0x%x";
        v17 = 1522;
        v11 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v7,
          (unsigned int)&word_1800CD61E,
          v8,
          v9,
          (__int64)&v14,
          (__int64)&v11,
          (__int64)&v13,
          (__int64)&v17,
          (__int64)&v12,
          (__int64)&v16,
          (__int64)&v15);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18001c27c  push    rbp
0x18001c27e  push    rbx
0x18001c27f  push    rdi
0x18001c280  mov     rbp, rsp
0x18001c283  sub     rsp, 80h
0x18001c28a  mov     rbx, rdx
0x18001c28d  mov     edi, ecx
0x18001c28f  test    rdx, rdx
0x18001c292  jnz     short loc_18001C29E
0x18001c294  mov     ebx, 80070057h
0x18001c299  jmp     loc_18001C354
0x18001c29e  mov     r8d, edi; dwThreadId
0x18001c2a1  xor     edx, edx; bInheritHandle
0x18001c2a3  mov     ecx, 100000h; dwDesiredAccess
0x18001c2a8  call    cs:__imp_OpenThread
0x18001c2ae  test    rax, rax
0x18001c2b1  jnz     loc_18001C34F
0x18001c2b7  mov     eax, cs:dword_1800EB958
0x18001c2bd  mov     ebx, 80004005h
0x18001c2c2  cmp     eax, 2
0x18001c2c5  jbe     loc_18001C354
0x18001c2cb  call    cs:__imp_GetLastError
0x18001c2d1  lea     rdx, word_1800CD61E
0x18001c2d8  mov     [rbp+arg_10], edi
0x18001c2db  mov     [rbp+arg_8], eax
0x18001c2de  lea     rax, aPalSystemThrea_5; "PAL_System_ThreadGetDeathCondition"
0x18001c2e5  mov     [rbp+var_18], rax
0x18001c2e9  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001c2f0  mov     [rbp+var_10], rax
0x18001c2f4  lea     rax, aFailedToOpenTh; "Failed to open thread %#x. GetLastError"...
0x18001c2fb  mov     [rbp+var_8], rax
0x18001c2ff  lea     rax, [rbp+arg_8]
0x18001c303  mov     [rsp+80h+var_30], rax
0x18001c308  lea     rax, [rbp+arg_10]
0x18001c30c  mov     [rsp+80h+var_38], rax
0x18001c311  lea     rax, [rbp+var_18]
0x18001c315  mov     [rsp+80h+var_40], rax
0x18001c31a  lea     rax, [rbp+arg_18]
0x18001c31e  mov     [rsp+80h+var_48], rax
0x18001c323  lea     rax, [rbp+var_10]
0x18001c327  mov     [rsp+80h+var_50], rax
0x18001c32c  lea     rax, [rbp+var_20]
0x18001c330  mov     [rsp+80h+var_58], rax
0x18001c335  lea     rax, [rbp+var_8]
0x18001c339  mov     [rsp+80h+var_60], rax
0x18001c33e  mov     [rbp+arg_18], 5F2h
0x18001c345  mov     [rbp+var_20], ebx
0x18001c348  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c34d  jmp     short loc_18001C354
0x18001c34f  mov     [rbx], rax
0x18001c352  xor     ebx, ebx
0x18001c354  mov     eax, ebx
0x18001c356  add     rsp, 80h
0x18001c35d  pop     rdi
0x18001c35e  pop     rbx
0x18001c35f  pop     rbp
0x18001c360  retn
```
