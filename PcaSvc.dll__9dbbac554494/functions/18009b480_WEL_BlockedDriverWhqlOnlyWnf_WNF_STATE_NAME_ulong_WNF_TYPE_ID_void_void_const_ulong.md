# WEL_BlockedDriverWhqlOnlyWnf(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x18009b480`
- end: `0x18009b6a0`
- name: `?WEL_BlockedDriverWhqlOnlyWnf@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `544`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18009c110`

## callees

- `0x180025bf8`
- `0x18004f8a0`
- `0x180056256`
- `0x18009b480`
- `0x18009beac`
- `0x18009bfdc`
- `0x1800f1f10`
- `0x1800f1fd0`
- `0x1800f7010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18009b512`
- `msvcrt!wcsrchr` at `0x18009b512`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009b56d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009b56d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009b5af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009b5af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b67b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b67b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b53b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009b53b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b57d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b57d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b591`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009b641`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009b641`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18009b618`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18009b618`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009b52b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009b52b`

## string_xrefs

- `0x18009b566`: `wldp.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WEL_BlockedDriverWhqlOnlyWnf(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        void *a4,
        const unsigned __int16 *Src,
        size_t Size)
{
  __int64 result; // rax
  unsigned int v7; // eax
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  ULONGLONG TickCount64; // rsi
  signed int LastError; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  unsigned int v14; // ecx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  HMODULE v16; // [rsp+28h] [rbp-D8h] BYREF
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Str[2040]; // [rsp+40h] [rbp-C0h] BYREF

  if ( (unsigned int)Size < 0x18 )
    return 3221225485LL;
  v7 = Src[10];
  if ( v7 >= (int)Size - 22 )
    v7 = Size - 22;
  LODWORD(result) = StringCchCopyNW(Str, 0x7F6u, Src + 11, (unsigned __int64)v7 >> 1);
  if ( (int)result >= 0 )
  {
    v8 = wcsrchr(Str, 0x5Cu);
    if ( v8 )
      v9 = v8 + 1;
    else
      v9 = Str;
    TickCount64 = GetTickCount64();
    EnterCriticalSection(&g_WELpLock);
    if ( WhqlOnlyIsItTimeToSendToast(Str, TickCount64) )
    {
      Library = LoadLibraryExW(L"wldp.dll", 0, 0x800u);
      v16 = Library;
      if ( Library && (ProcAddress = GetProcAddress(Library, "WldpSendWhqlOnlyBlockToast")) != 0 )
      {
        LastError = ((__int64 (__fastcall *)(wchar_t *))ProcAddress)(v9);
        if ( LastError == -2147221164 )
        {
          if ( !dword_18015AC50 )
          {
            v14 = 4096;
            if ( (unsigned int)Size <= 0x1000 )
              v14 = Size;
            dword_18015AC50 = v14;
            memcpy_0(&dword_18015AC54, Src, v14);
            ThreadpoolTimer = qword_180159928;
            if ( qword_180159928
              || (ThreadpoolTimer = CreateThreadpoolTimer(WhqlOnlyTimerCallback, &dword_18015AC50, 0),
                  (qword_180159928 = ThreadpoolTimer) != 0) )
            {
              pftDueTime = (struct _FILETIME)-1200000000LL;
              SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
            }
          }
        }
        else if ( LastError >= 0 )
        {
          WhqlOnlySetLastToastTickCount(Str, TickCount64);
        }
        LastError = (unsigned __int16)LastError;
        if ( (_WORD)LastError )
          LastError = (unsigned __int16)LastError | 0xC0070000;
      }
      else if ( (int)GetLastError() > 0 )
      {
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      }
      else
      {
        LastError = GetLastError();
      }
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v16);
    }
    else
    {
      LastError = 0;
    }
    LeaveCriticalSection(&g_WELpLock);
    return (unsigned int)LastError;
  }
  else
  {
    result = (unsigned __int16)result;
    if ( (_WORD)result )
      return (unsigned __int16)result | 0xC0070000;
  }
  return result;
}

```

## disassembly

```asm
0x18009b480  push    rbp
0x18009b482  push    rbx
0x18009b483  push    rsi
0x18009b484  push    rdi
0x18009b485  push    r14
0x18009b487  lea     rbp, [rsp-0F40h]
0x18009b48f  mov     eax, 1040h
0x18009b494  call    _alloca_probe
0x18009b499  sub     rsp, rax
0x18009b49c  mov     rax, cs:__security_cookie
0x18009b4a3  xor     rax, rsp
0x18009b4a6  mov     [rbp+0F60h+var_30], rax
0x18009b4ad  mov     r14, [rbp+0F60h+Src]
0x18009b4b4  mov     edi, dword ptr [rbp+0F60h+Size]
0x18009b4ba  cmp     edi, 18h
0x18009b4bd  jnb     short loc_18009B4C9
0x18009b4bf  mov     eax, 0C000000Dh
0x18009b4c4  jmp     loc_18009B683
0x18009b4c9  lea     ecx, [rdi-16h]
0x18009b4cc  movzx   eax, word ptr [r14+14h]
0x18009b4d1  cmp     eax, ecx
0x18009b4d3  cmovnb  eax, ecx
0x18009b4d6  mov     r9d, eax
0x18009b4d9  shr     r9, 1; unsigned __int64
0x18009b4dc  lea     r8, [r14+16h]; unsigned __int16 *
0x18009b4e0  mov     edx, 7F6h; unsigned __int64
0x18009b4e5  lea     rcx, [rsp+1060h+Str]; unsigned __int16 *
0x18009b4ea  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18009b4ef  test    eax, eax
0x18009b4f1  jns     short loc_18009B508
0x18009b4f3  movzx   eax, ax
0x18009b4f6  mov     ecx, eax
0x18009b4f8  or      ecx, 0C0070000h
0x18009b4fe  test    eax, eax
0x18009b500  cmovnz  eax, ecx
0x18009b503  jmp     loc_18009B683
0x18009b508  mov     edx, 5Ch ; '\'; Ch
0x18009b50d  lea     rcx, [rsp+1060h+Str]; Str
0x18009b512  call    cs:__imp_wcsrchr
0x18009b518  mov     rbx, rax
0x18009b51b  test    rax, rax
0x18009b51e  jnz     short loc_18009B527
0x18009b520  lea     rbx, [rsp+1060h+Str]
0x18009b525  jmp     short loc_18009B52B
0x18009b527  add     rbx, 2
0x18009b52b  call    cs:__imp_GetTickCount64
0x18009b531  mov     rsi, rax
0x18009b534  lea     rcx, ?g_WELpLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009b53b  call    cs:__imp_EnterCriticalSection
0x18009b541  mov     [rsp+1060h+var_103F], 1
0x18009b546  mov     rdx, rsi; unsigned __int64
0x18009b549  lea     rcx, [rsp+1060h+Str]; unsigned __int16 *
0x18009b54e  call    ?WhqlOnlyIsItTimeToSendToast@@YAEPEBG_K@Z; WhqlOnlyIsItTimeToSendToast(ushort const *,unsigned __int64)
0x18009b553  test    al, al
0x18009b555  jnz     short loc_18009B55E
0x18009b557  xor     ebx, ebx
0x18009b559  jmp     loc_18009B674
0x18009b55e  xor     edx, edx; hFile
0x18009b560  mov     r8d, 800h; dwFlags
0x18009b566  lea     rcx, aWldpDll; "wldp.dll"
0x18009b56d  call    cs:__imp_LoadLibraryExW
0x18009b573  mov     [rsp+1060h+var_1038], rax
0x18009b578  test    rax, rax
0x18009b57b  jnz     short loc_18009B5A5
0x18009b57d  call    cs:__imp_GetLastError
0x18009b583  test    eax, eax
0x18009b585  jg      short loc_18009B591
0x18009b587  call    cs:__imp_GetLastError
0x18009b58d  mov     ebx, eax
0x18009b58f  jmp     short loc_18009B5A0
0x18009b591  call    cs:__imp_GetLastError
0x18009b597  movzx   ebx, ax
0x18009b59a  or      ebx, 0C0070000h
0x18009b5a0  jmp     loc_18009B669
0x18009b5a5  lea     rdx, aWldpsendwhqlon; "WldpSendWhqlOnlyBlockToast"
0x18009b5ac  mov     rcx, rax; hModule
0x18009b5af  call    cs:__imp_GetProcAddress
0x18009b5b5  test    rax, rax
0x18009b5b8  jz      short loc_18009B57D
0x18009b5ba  mov     rcx, rbx
0x18009b5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b5c2  mov     ebx, eax
0x18009b5c4  cmp     eax, 80040154h
0x18009b5c9  jnz     short loc_18009B649
0x18009b5cb  cmp     cs:dword_18015AC50, 0
0x18009b5d2  jnz     loc_18009B65A
0x18009b5d8  mov     ecx, 1000h
0x18009b5dd  cmp     edi, ecx
0x18009b5df  cmovbe  ecx, edi
0x18009b5e2  mov     r8d, ecx; Size
0x18009b5e5  mov     cs:dword_18015AC50, r8d
0x18009b5ec  mov     rdx, r14; Src
0x18009b5ef  lea     rcx, dword_18015AC54; void *
0x18009b5f6  call    memcpy_0
0x18009b5fb  mov     rax, cs:qword_180159928
0x18009b602  test    rax, rax
0x18009b605  jnz     short loc_18009B62A
0x18009b607  xor     r8d, r8d; pcbe
0x18009b60a  lea     rdx, dword_18015AC50; pv
0x18009b611  lea     rcx, ?WhqlOnlyTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18009b618  call    cs:__imp_CreateThreadpoolTimer
0x18009b61e  mov     cs:qword_180159928, rax
0x18009b625  test    rax, rax
0x18009b628  jz      short loc_18009B65A
0x18009b62a  mov     qword ptr [rsp+1060h+pftDueTime.dwLowDateTime], 0FFFFFFFFB8797400h
0x18009b633  xor     r9d, r9d; msWindowLength
0x18009b636  xor     r8d, r8d; msPeriod
0x18009b639  lea     rdx, [rsp+1060h+pftDueTime]; pftDueTime
0x18009b63e  mov     rcx, rax; pti
0x18009b641  call    cs:__imp_SetThreadpoolTimer
0x18009b647  jmp     short loc_18009B65A
0x18009b649  test    ebx, ebx
0x18009b64b  js      short loc_18009B65A
0x18009b64d  mov     rdx, rsi; unsigned __int64
0x18009b650  lea     rcx, [rsp+1060h+Str]; unsigned __int16 *
0x18009b655  call    ?WhqlOnlySetLastToastTickCount@@YAXPEBG_K@Z; WhqlOnlySetLastToastTickCount(ushort const *,unsigned __int64)
0x18009b65a  movzx   ebx, bx
0x18009b65d  mov     eax, ebx
0x18009b65f  or      eax, 0C0070000h
0x18009b664  test    ebx, ebx
0x18009b666  cmovnz  ebx, eax
0x18009b669  lea     rcx, [rsp+1060h+var_1038]
0x18009b66e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18009b673  nop
0x18009b674  lea     rcx, ?g_WELpLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009b67b  call    cs:__imp_LeaveCriticalSection
0x18009b681  mov     eax, ebx
0x18009b683  mov     rcx, [rbp+0F60h+var_30]
0x18009b68a  xor     rcx, rsp; StackCookie
0x18009b68d  call    __security_check_cookie
0x18009b692  add     rsp, 1040h
0x18009b699  pop     r14
0x18009b69b  pop     rdi
0x18009b69c  pop     rsi
0x18009b69d  pop     rbx
0x18009b69e  pop     rbp
0x18009b69f  retn
```
