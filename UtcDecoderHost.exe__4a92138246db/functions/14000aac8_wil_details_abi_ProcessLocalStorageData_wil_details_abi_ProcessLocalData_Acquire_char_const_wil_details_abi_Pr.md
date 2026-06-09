# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000aac8`
- end: `0x14000ae9c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14000ba50`

## callees

- `0x140008660`
- `0x1400090ec`
- `0x14000aac8`
- `0x14000aea4`
- `0x14000b194`
- `0x14000b7e8`
- `0x14000bfc8`
- `0x14000c434`
- `0x14000ce24`
- `0x14000cefc`
- `0x14000d2dc`
- `0x14000d2ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000abf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ad35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ada5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000abf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ad35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ada5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000ab61`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000ab61`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000ab40`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000ab40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ad0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ad0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000acfe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000acfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000ab01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000ab01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ac08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000acd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000acf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ad46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000adbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ac08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000acd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000acf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ad46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000adbb`

## string_xrefs

- `0x14000ae06`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  __int64 v15; // r8
  const char *v16; // r9
  __int64 v17; // r8
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v23 = (_QWORD *)v20;
  if ( v20 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v20 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
    v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v22,
            v20 >> 2);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v35 = *(_OWORD *)hObject;
      *(_DWORD *)v23 = 1;
      v23[1] = v6;
      *((_OWORD *)v23 + 1) = v35;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v23;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v24, v42);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  return v24;
}

```

## disassembly

```asm
0x14000aac8  mov     [rsp-8+arg_10], rbx
0x14000aacd  push    rbp
0x14000aace  push    rsi
0x14000aacf  push    rdi
0x14000aad0  push    r14
0x14000aad2  push    r15
0x14000aad4  lea     rbp, [rsp-160h]
0x14000aadc  sub     rsp, 260h
0x14000aae3  mov     rax, cs:__security_cookie
0x14000aaea  xor     rax, rsp
0x14000aaed  mov     [rbp+180h+var_30], rax
0x14000aaf4  mov     r15, rdx
0x14000aaf7  mov     qword ptr [rdx], 0
0x14000aafe  mov     rbx, rcx
0x14000ab01  call    cs:__imp_GetCurrentProcessId
0x14000ab07  mov     r14d, 78h ; 'x'
0x14000ab0d  mov     [rsp+280h+var_258], rbx
0x14000ab12  mov     r9d, eax
0x14000ab15  mov     [rsp+280h+var_260], r14d; int
0x14000ab1a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000ab21  mov     edx, 104h; unsigned __int64
0x14000ab26  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000ab2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000ab30  mov     r9d, 1F0001h; dwDesiredAccess
0x14000ab36  lea     rdx, [rsp+280h+Name]; lpName
0x14000ab3b  xor     r8d, r8d; dwFlags
0x14000ab3e  xor     ecx, ecx; lpMutexAttributes
0x14000ab40  call    cs:__imp_CreateMutexExW
0x14000ab46  mov     rbx, rax
0x14000ab49  test    rax, rax
0x14000ab4c  jnz     short loc_14000AB58
0x14000ab4e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000ab53  jmp     loc_14000ADC7
0x14000ab58  xor     r8d, r8d; bAlertable
0x14000ab5b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000ab5e  mov     rcx, rbx; hHandle
0x14000ab61  call    cs:__imp_WaitForSingleObjectEx
0x14000ab67  cmp     eax, 102h
0x14000ab6c  jz      short loc_14000AB7E
0x14000ab6e  test    eax, 0FFFFFF7Fh
0x14000ab73  jnz     loc_14000ADFF
0x14000ab79  mov     rdi, rbx
0x14000ab7c  jmp     short loc_14000AB80
0x14000ab7e  xor     edi, edi
0x14000ab80  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14000ab85  mov     [rsp+280h+hObject], 0
0x14000ab8e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000ab93  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000ab98  mov     esi, eax
0x14000ab9a  test    eax, eax
0x14000ab9c  jns     short loc_14000AC1D
0x14000ab9e  mov     rcx, [rbp+188h]; this
0x14000aba5  lea     r8, aWil; "wil"
0x14000abac  mov     r9d, eax; char *
0x14000abaf  mov     edx, 66h ; 'f'; void *
0x14000abb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000abb9  mov     rcx, [rbp+188h]; this
0x14000abc0  lea     r8, aWil; "wil"
0x14000abc7  mov     r9d, esi; char *
0x14000abca  mov     edx, 6Fh ; 'o'; void *
0x14000abcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000abd4  mov     rcx, [rbp+188h]; this
0x14000abdb  lea     r8, aWil; "wil"
0x14000abe2  mov     r9d, esi; char *
0x14000abe5  mov     edx, 12Eh; void *
0x14000abea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000abef  test    rdi, rdi
0x14000abf2  jz      short loc_14000AC05
0x14000abf4  mov     rcx, rdi; hMutex
0x14000abf7  call    cs:__imp_ReleaseMutex
0x14000abfd  test    eax, eax
0x14000abff  jz      loc_14000AE18
0x14000ac05  mov     rcx, rbx; hObject
0x14000ac08  call    cs:__imp_CloseHandle
0x14000ac0e  test    eax, eax
0x14000ac10  jz      loc_14000AE2A
0x14000ac16  mov     eax, esi
0x14000ac18  jmp     loc_14000ADC7
0x14000ac1d  mov     rax, [rsp+280h+hObject]
0x14000ac22  lea     rcx, ds:0[rax*4]
0x14000ac2a  test    rcx, rcx
0x14000ac2d  jz      short loc_14000AC3D
0x14000ac2f  mov     [r15], rcx
0x14000ac32  mov     eax, [rcx]
0x14000ac34  inc     eax
0x14000ac36  mov     [rcx], eax
0x14000ac38  jmp     loc_14000AD9D
0x14000ac3d  mov     rdx, r14; dwBytes
0x14000ac40  mov     qword ptr [r15], 0
0x14000ac47  mov     ecx, 8; dwFlags
0x14000ac4c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000ac51  mov     rsi, rax
0x14000ac54  test    rax, rax
0x14000ac57  jnz     short loc_14000AC7F
0x14000ac59  mov     rcx, [rbp+188h]; this
0x14000ac60  lea     r8, aWil; "wil"
0x14000ac67  mov     r14d, 8007000Eh
0x14000ac6d  mov     edx, 14Bh; void *
0x14000ac72  mov     r9d, r14d; char *
0x14000ac75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ac7a  jmp     loc_14000AD12
0x14000ac7f  xorps   xmm0, xmm0
0x14000ac82  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000ac88  test    sil, 3
0x14000ac8c  jnz     loc_14000AE3C
0x14000ac92  mov     r9, rsi
0x14000ac95  lea     rdx, [rsp+280h+Name]; wchar_t *
0x14000ac9a  shr     r9, 2; unsigned __int64
0x14000ac9e  lea     rcx, [rsp+280h+hObject]; this
0x14000aca3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x14000aca8  mov     r14d, eax
0x14000acab  test    eax, eax
0x14000acad  jns     loc_14000AD59
0x14000acb3  mov     rcx, [rbp+188h]; this
0x14000acba  lea     r8, aWil; "wil"
0x14000acc1  mov     r9d, eax; char *
0x14000acc4  mov     edx, 14Eh; void *
0x14000acc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000acce  mov     rcx, [rsp+280h+hObject+8]; hObject
0x14000acd3  test    rcx, rcx
0x14000acd6  jz      short loc_14000ACE6
0x14000acd8  call    cs:__imp_CloseHandle
0x14000acde  test    eax, eax
0x14000ace0  jz      loc_14000AE42
0x14000ace6  mov     rcx, [rsp+280h+hObject]; hObject
0x14000aceb  test    rcx, rcx
0x14000acee  jz      short loc_14000ACFE
0x14000acf0  call    cs:__imp_CloseHandle
0x14000acf6  test    eax, eax
0x14000acf8  jz      loc_14000AE54
0x14000acfe  call    cs:__imp_GetProcessHeap
0x14000ad04  mov     r8, rsi; lpMem
0x14000ad07  xor     edx, edx; dwFlags
0x14000ad09  mov     rcx, rax; hHeap
0x14000ad0c  call    cs:__imp_HeapFree
0x14000ad12  mov     rcx, [rbp+188h]; this
0x14000ad19  lea     r8, aWil; "wil"
0x14000ad20  mov     r9d, r14d; char *
0x14000ad23  mov     edx, 137h; void *
0x14000ad28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ad2d  test    rdi, rdi
0x14000ad30  jz      short loc_14000AD43
0x14000ad32  mov     rcx, rdi; hMutex
0x14000ad35  call    cs:__imp_ReleaseMutex
0x14000ad3b  test    eax, eax
0x14000ad3d  jz      loc_14000AE66
0x14000ad43  mov     rcx, rbx; hObject
0x14000ad46  call    cs:__imp_CloseHandle
0x14000ad4c  test    eax, eax
0x14000ad4e  jz      loc_14000AE78
0x14000ad54  mov     eax, r14d
0x14000ad57  jmp     short loc_14000ADC7
0x14000ad59  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000ad5e  xor     edx, edx; Val
0x14000ad60  mov     dword ptr [rsi], 1
0x14000ad66  lea     rcx, [rsi+22h]; void *
0x14000ad6a  mov     [rsi+8], rbx
0x14000ad6e  movdqu  xmmword ptr [rsi+10h], xmm0
0x14000ad73  lea     r8d, [rdx+56h]; Size
0x14000ad77  call    memset_0
0x14000ad7c  xor     edx, edx; Val
0x14000ad7e  mov     word ptr [rsi+20h], 58h ; 'X'
0x14000ad84  lea     rcx, [rsi+28h]; void *
0x14000ad88  mov     dword ptr [rsi+24h], 1
0x14000ad8f  lea     r8d, [rdx+50h]; Size
0x14000ad93  call    memset_0
0x14000ad98  xor     ebx, ebx
0x14000ad9a  mov     [r15], rsi
0x14000ad9d  test    rdi, rdi
0x14000ada0  jz      short loc_14000ADB3
0x14000ada2  mov     rcx, rdi; hMutex
0x14000ada5  call    cs:__imp_ReleaseMutex
0x14000adab  test    eax, eax
0x14000adad  jz      loc_14000AE8A
0x14000adb3  test    rbx, rbx
0x14000adb6  jz      short loc_14000ADC5
0x14000adb8  mov     rcx, rbx; hObject
0x14000adbb  call    cs:__imp_CloseHandle
0x14000adc1  test    eax, eax
0x14000adc3  jz      short loc_14000ADED
0x14000adc5  xor     eax, eax
0x14000adc7  mov     rcx, [rbp+180h+var_30]
0x14000adce  xor     rcx, rsp; StackCookie
0x14000add1  call    __security_check_cookie
0x14000add6  mov     rbx, [rsp+280h+arg_10]
0x14000adde  add     rsp, 260h
0x14000ade5  pop     r15
0x14000ade7  pop     r14
0x14000ade9  pop     rdi
0x14000adea  pop     rsi
0x14000adeb  pop     rbp
0x14000adec  retn
0x14000aded  mov     rcx, [rbp+188h]; this
0x14000adf4  mov     edx, 0A0Bh; void *
0x14000adf9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000adff  mov     rcx, [rbp+188h]; this
0x14000ae06  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000ae0d  mov     edx, 0E01h; void *
0x14000ae12  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000ae18  mov     rcx, [rbp+188h]; this
0x14000ae1f  mov     edx, 0A15h; void *
0x14000ae24  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ae2a  mov     rcx, [rbp+188h]; this
0x14000ae31  mov     edx, 0A0Bh; void *
0x14000ae36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ae3c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000ae42  mov     rcx, [rbp+188h]; this
0x14000ae49  mov     edx, 0A0Bh; void *
0x14000ae4e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ae54  mov     rcx, [rbp+188h]; this
0x14000ae5b  mov     edx, 0A0Bh; void *
0x14000ae60  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ae66  mov     rcx, [rbp+188h]; this
0x14000ae6d  mov     edx, 0A15h; void *
0x14000ae72  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ae78  mov     rcx, [rbp+188h]; this
0x14000ae7f  mov     edx, 0A0Bh; void *
0x14000ae84  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ae8a  mov     rcx, [rbp+188h]; this
0x14000ae91  mov     edx, 0A15h; void *
0x14000ae96  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
