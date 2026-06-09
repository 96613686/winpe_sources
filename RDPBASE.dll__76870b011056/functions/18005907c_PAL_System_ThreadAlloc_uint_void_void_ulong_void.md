# PAL_System_ThreadAlloc(uint (*)(void *),void *,ulong *,void * *)

- ea: `0x18005907c`
- end: `0x180059290`
- name: `?PAL_System_ThreadAlloc@@YAJP6AIPEAX@Z0PEAKPEAPEAX@Z`
- size: `532`
- prototype: `__int64 __fastcall(unsigned int (*)(void *), void *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180059298`

## callees

- `0x1800018a4`
- `0x180004970`
- `0x18005907c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800591d0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800591d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800590f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800590f8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800591b9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800591b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005911a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005911a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800590c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800590c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800591e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800591e6`

## string_xrefs

- `0x18005913c`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x180059221`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x180059131`: `PAL_System_ThreadAlloc`
- `0x180059208`: `PAL_System_ThreadAlloc`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadAlloc(unsigned int (*a1)(void *), void *a2, unsigned int *a3, void **a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  unsigned int v9; // ebx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  HANDLE v13; // rcx
  DWORD LastError; // [rsp+50h] [rbp-30h] BYREF
  int v16; // [rsp+54h] [rbp-2Ch] BYREF
  int v17; // [rsp+58h] [rbp-28h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-20h] BYREF
  const char *v19; // [rsp+68h] [rbp-18h] BYREF
  const char *v20; // [rsp+70h] [rbp-10h] BYREF
  const char *v21; // [rsp+78h] [rbp-8h] BYREF
  DWORD ThreadId; // [rsp+A0h] [rbp+20h] BYREF
  int v23; // [rsp+A4h] [rbp+24h]

  v23 = HIDWORD(a1);
  ThreadId = 0;
  phModule = 0;
  if ( a3 )
  {
    v7 = LocalAlloc(0x40u, 0x18u);
    v8 = v7;
    if ( v7 )
    {
      v7[1] = a2;
      *v7 = CTSThread::TSStaticThreadEntry;
      if ( GetModuleHandleExW(4u, &g_TsSystemPalDllModule, &phModule) )
      {
        v8[2] = phModule;
        v13 = CreateThread(0, 0, PAL_System_Win32_ThreadProcWrapper, v8, 0, &ThreadId);
        if ( v13 )
        {
          *a3 = ThreadId;
          v9 = 0;
          *a4 = v13;
          return v9;
        }
        if ( phModule )
        {
          FreeLibrary(phModule);
          phModule = 0;
        }
        v9 = -2147467259;
      }
      else
      {
        v9 = -2147467259;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v16 = 1295;
          LastError = GetLastError();
          v19 = "PAL_System_ThreadAlloc";
          v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
          v21 = "Failed GetModuleHandleEx.  GetLastError: 0x%x";
          v17 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)byte_1801B8B1D,
            v11,
            v12,
            (__int64)&v21,
            (__int64)&v17,
            (__int64)&v20,
            (__int64)&v16,
            (__int64)&v19,
            (__int64)&LastError);
        }
      }
      LocalFree(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v17 = 1268;
      v21 = "PAL_System_ThreadAlloc";
      v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v19 = "NULL parameter passed";
      v16 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)byte_1801B8FA5,
        0,
        (_DWORD)a4,
        (__int64)&v19,
        (__int64)&v16,
        (__int64)&v20,
        (__int64)&v17,
        (__int64)&v21);
    }
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x18005907c  mov     [rsp-18h+arg_8], rbx
0x180059081  mov     [rsp-18h+arg_10], rsi
0x180059086  mov     qword ptr [rsp-18h+ThreadId], rcx
0x18005908b  push    rbp
0x18005908c  push    rdi
0x18005908d  push    r14
0x18005908f  mov     rbp, rsp
0x180059092  sub     rsp, 80h
0x180059099  mov     [rbp+ThreadId], 0
0x1800590a0  mov     rsi, r9
0x1800590a3  mov     [rbp+phModule], 0
0x1800590ab  mov     rbx, r8
0x1800590ae  mov     r14, rdx
0x1800590b1  test    r8, r8
0x1800590b4  jz      loc_1800591FD
0x1800590ba  mov     edx, 18h; uBytes
0x1800590bf  lea     ecx, [rdx+28h]; uFlags
0x1800590c2  call    cs:__imp_LocalAlloc
0x1800590c8  mov     rdi, rax
0x1800590cb  test    rax, rax
0x1800590ce  jnz     short loc_1800590DA
0x1800590d0  mov     ebx, 8007000Eh
0x1800590d5  jmp     loc_180059276
0x1800590da  mov     [rax+8], r14
0x1800590de  lea     r8, [rbp+phModule]; phModule
0x1800590e2  lea     rax, ?TSStaticThreadEntry@CTSThread@@CAIPEAX@Z; CTSThread::TSStaticThreadEntry(void *)
0x1800590e9  mov     ecx, 4; dwFlags
0x1800590ee  lea     rdx, ?g_TsSystemPalDllModule@@3HA; lpModuleName
0x1800590f5  mov     [rdi], rax
0x1800590f8  call    cs:__imp_GetModuleHandleExW
0x1800590fe  test    eax, eax
0x180059100  jnz     loc_180059192
0x180059106  mov     eax, cs:CallbackContext
0x18005910c  mov     ebx, 80004005h
0x180059111  cmp     eax, 2
0x180059114  jbe     loc_1800591E3
0x18005911a  call    cs:__imp_GetLastError
0x180059120  lea     rdx, byte_1801B8B1D
0x180059127  mov     [rbp+var_2C], 50Fh
0x18005912e  mov     [rbp+var_30], eax
0x180059131  lea     rax, aPalSystemThrea_5; "PAL_System_ThreadAlloc"
0x180059138  mov     [rbp+var_18], rax
0x18005913c  lea     rax, aOnecoreTermsrv_12; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180059143  mov     [rbp+var_10], rax
0x180059147  lea     rax, aFailedGetmodul; "Failed GetModuleHandleEx.  GetLastError"...
0x18005914e  mov     [rbp+var_8], rax
0x180059152  lea     rax, [rbp+var_30]
0x180059156  mov     [rsp+80h+var_38], rax
0x18005915b  lea     rax, [rbp+var_18]
0x18005915f  mov     [rsp+80h+var_40], rax
0x180059164  lea     rax, [rbp+var_2C]
0x180059168  mov     [rsp+80h+var_48], rax
0x18005916d  lea     rax, [rbp+var_10]
0x180059171  mov     [rsp+80h+var_50], rax
0x180059176  lea     rax, [rbp+var_28]
0x18005917a  mov     [rsp+80h+lpThreadId], rax
0x18005917f  lea     rax, [rbp+var_8]
0x180059183  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x180059188  mov     [rbp+var_28], ebx
0x18005918b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180059190  jmp     short loc_1800591E3
0x180059192  mov     rax, [rbp+phModule]
0x180059196  lea     r8, ?PAL_System_Win32_ThreadProcWrapper@@YAKPEAX@Z; lpStartAddress
0x18005919d  mov     [rdi+10h], rax
0x1800591a1  mov     r9, rdi; lpParameter
0x1800591a4  lea     rax, [rbp+ThreadId]
0x1800591a8  xor     edx, edx; dwStackSize
0x1800591aa  mov     [rsp+80h+lpThreadId], rax; lpThreadId
0x1800591af  xor     ecx, ecx; lpThreadAttributes
0x1800591b1  mov     [rsp+80h+dwCreationFlags], 0; dwCreationFlags
0x1800591b9  call    cs:__imp_CreateThread
0x1800591bf  mov     rcx, rax
0x1800591c2  test    rax, rax
0x1800591c5  jnz     short loc_1800591F1
0x1800591c7  mov     rcx, [rbp+phModule]; hLibModule
0x1800591cb  test    rcx, rcx
0x1800591ce  jz      short loc_1800591DE
0x1800591d0  call    cs:__imp_FreeLibrary
0x1800591d6  mov     [rbp+phModule], 0
0x1800591de  mov     ebx, 80004005h
0x1800591e3  mov     rcx, rdi; hMem
0x1800591e6  call    cs:__imp_LocalFree
0x1800591ec  jmp     loc_180059276
0x1800591f1  mov     eax, [rbp+ThreadId]
0x1800591f4  mov     [rbx], eax
0x1800591f6  xor     ebx, ebx
0x1800591f8  mov     [rsi], rcx
0x1800591fb  jmp     short loc_180059276
0x1800591fd  mov     eax, cs:CallbackContext
0x180059203  cmp     eax, 2
0x180059206  jbe     short loc_180059271
0x180059208  lea     rax, aPalSystemThrea_5; "PAL_System_ThreadAlloc"
0x18005920f  mov     [rbp+var_28], 4F4h
0x180059216  mov     [rbp+var_8], rax
0x18005921a  lea     rdx, byte_1801B8FA5
0x180059221  lea     rax, aOnecoreTermsrv_12; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180059228  mov     ebx, 80004005h
0x18005922d  mov     [rbp+var_10], rax
0x180059231  lea     rax, aNullParameterP; "NULL parameter passed"
0x180059238  mov     [rbp+var_18], rax
0x18005923c  lea     rax, [rbp+var_8]
0x180059240  mov     [rsp+80h+var_40], rax
0x180059245  lea     rax, [rbp+var_28]
0x180059249  mov     [rsp+80h+var_48], rax
0x18005924e  lea     rax, [rbp+var_10]
0x180059252  mov     [rsp+80h+var_50], rax
0x180059257  lea     rax, [rbp+var_2C]
0x18005925b  mov     [rsp+80h+lpThreadId], rax
0x180059260  lea     rax, [rbp+var_18]
0x180059264  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x180059269  mov     [rbp+var_2C], ebx
0x18005926c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180059271  mov     ebx, 80070057h
0x180059276  lea     r11, [rsp+80h+var_s0]
0x18005927e  mov     eax, ebx
0x180059280  mov     rbx, [r11+28h]
0x180059284  mov     rsi, [r11+30h]
0x180059288  mov     rsp, r11
0x18005928b  pop     r14
0x18005928d  pop     rdi
0x18005928e  pop     rbp
0x18005928f  retn
```
