# _lambda_5551ac6b8613a4d1ae9eaae85dc12299_::operator()

- ea: `0x180008a94`
- end: `0x180008c13`
- name: `_lambda_5551ac6b8613a4d1ae9eaae85dc12299_::operator()`
- size: `383`
- prototype: `__int64 __fastcall(AppMon::AppPortEntry **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180007b80`

## callees

- `0x1800026fc`
- `0x180007a04`
- `0x1800087b0`
- `0x18000894c`
- `0x180008990`
- `0x180008a94`
- `0x180009804`
- `0x180009da4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008b81`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008b81`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008bb5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008bb5`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180008bde`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180008bde`
- `SPOOLSS!RevertToPrinterSelf` at `0x180008ac8`
- `SPOOLSS!RevertToPrinterSelf` at `0x180008ac8`

## pseudocode

```c
__int64 __fastcall lambda_5551ac6b8613a4d1ae9eaae85dc12299_::operator()(AppMon::AppPortEntry **a1)
{
  int v2; // eax
  HANDLE v3; // rax
  const char *v4; // r9
  void *v5; // rbp
  _QWORD *v6; // r14
  AppMon::AppPortEntry *v7; // rsi
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // r9
  DWORD dwCreationFlags; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HANDLE Thread; // [rsp+60h] [rbp+8h] BYREF
  HANDLE v15; // [rsp+68h] [rbp+10h] BYREF
  _QWORD *v16; // [rsp+70h] [rbp+18h]

  v2 = AppMon::AppPortEntry::SetJobStatus(*a1);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\appmonitor.cpp",
      (const char *)(unsigned int)v2,
      dwCreationFlags);
  v3 = RevertToPrinterSelf();
  v5 = v3;
  if ( !v3 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xA2,
      (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\appmonitor.cpp",
      v4);
  v15 = v3;
  v6 = operator new(0x38u);
  v16 = v6;
  v7 = *a1;
  *v6 = 0;
  v6[1] = 0;
  v6[2] = 0;
  v6[3] = 0;
  v6[4] = 0;
  v6[5] = 0;
  std::shared_ptr<AppMon::AppPrinterEndPointBase>::operator=(v6, v7);
  std::shared_ptr<AppMon::AppPortEntry>::operator=(v6 + 2, (char *)v7 + 16);
  std::shared_ptr<AppMon::AppPortEntry>::operator=(v6 + 4, (char *)v7 + 32);
  *((_DWORD *)v6 + 12) = *((_DWORD *)v7 + 12);
  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)AppMon::AppPortEntry::AppPrinterThreadFunction, v6, 4u, 0);
  if ( !Thread )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xB1,
      (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\appmonitor.cpp",
      v8);
  if ( !SetThreadToken(&Thread, v5) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xB5,
      (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\appmonitor.cpp",
      v9);
  if ( ResumeThread(Thread) == -1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xB6,
      (unsigned int)"printscan\\print\\spooler\\monitors\\appmon\\lib\\appmonitor.cpp",
      v10);
  return std::unique_ptr_void__lambda_5beab740efbf3494b609d1267351a2ce___::_unique_ptr_void__lambda_5beab740efbf3494b609d1267351a2ce___(&v15);
}

```

## disassembly

```asm
0x180008a94  push    rbx
0x180008a96  push    rbp
0x180008a97  push    rsi
0x180008a98  push    rdi
0x180008a99  push    r14
0x180008a9b  sub     rsp, 30h
0x180008a9f  mov     rsi, rcx
0x180008aa2  mov     rcx, [rcx]; this
0x180008aa5  call    ?SetJobStatus@AppPortEntry@AppMon@@QEAAJK@Z; AppMon::AppPortEntry::SetJobStatus(ulong)
0x180008aaa  mov     rcx, [rsp+58h]; this
0x180008aaf  test    eax, eax
0x180008ab1  jns     short loc_180008AC8
0x180008ab3  mov     r9d, eax; char *
0x180008ab6  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\monitors\\ap"...
0x180008abd  mov     edx, 9Eh; void *
0x180008ac2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180008ac8  call    cs:__imp_RevertToPrinterSelf
0x180008ace  mov     rbp, rax
0x180008ad1  mov     rcx, [rsp+58h]; this
0x180008ad6  test    rax, rax
0x180008ad9  jnz     short loc_180008AED
0x180008adb  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\monitors\\ap"...
0x180008ae2  mov     edx, 0A2h; void *
0x180008ae7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180008aed  mov     [rsp+58h+arg_8], rbp
0x180008af2  mov     ecx, 38h ; '8'; Size
0x180008af7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008afc  mov     r14, rax
0x180008aff  mov     [rsp+58h+arg_10], rax
0x180008b04  mov     rsi, [rsi]
0x180008b07  mov     qword ptr [rax], 0
0x180008b0e  mov     qword ptr [rax+8], 0
0x180008b16  mov     qword ptr [rax+10h], 0
0x180008b1e  mov     qword ptr [rax+18h], 0
0x180008b26  mov     qword ptr [rax+20h], 0
0x180008b2e  mov     qword ptr [rax+28h], 0
0x180008b36  mov     rdx, rsi
0x180008b39  mov     rcx, rax
0x180008b3c  call    ??4?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<AppMon::AppPrinterEndPointBase>::operator=(std::shared_ptr<AppMon::AppPrinterEndPointBase> const &)
0x180008b41  lea     rdx, [rsi+10h]
0x180008b45  lea     rcx, [r14+10h]
0x180008b49  call    ??4?$shared_ptr@VAppPortEntry@AppMon@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<AppMon::AppPortEntry>::operator=(std::shared_ptr<AppMon::AppPortEntry> const &)
0x180008b4e  lea     rdx, [rsi+20h]
0x180008b52  lea     rcx, [r14+20h]
0x180008b56  call    ??4?$shared_ptr@VAppPortEntry@AppMon@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<AppMon::AppPortEntry>::operator=(std::shared_ptr<AppMon::AppPortEntry> const &)
0x180008b5b  mov     eax, [rsi+30h]
0x180008b5e  mov     [r14+30h], eax
0x180008b62  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180008b6b  mov     [rsp+58h+dwCreationFlags], 4; dwCreationFlags
0x180008b73  mov     r9, r14; lpParameter
0x180008b76  lea     r8, ?AppPrinterThreadFunction@AppPortEntry@AppMon@@CAKPEAX@Z; lpStartAddress
0x180008b7d  xor     edx, edx; dwStackSize
0x180008b7f  xor     ecx, ecx; lpThreadAttributes
0x180008b81  call    cs:__imp_CreateThread
0x180008b87  mov     [rsp+58h+Thread], rax
0x180008b8c  mov     rcx, [rsp+58h]; this
0x180008b91  test    rax, rax
0x180008b94  jnz     short loc_180008BA8
0x180008b96  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\monitors\\ap"...
0x180008b9d  mov     edx, 0B1h; void *
0x180008ba2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180008ba8  mov     rbx, [rsp+58h]
0x180008bad  mov     rdx, rbp; Token
0x180008bb0  lea     rcx, [rsp+58h+Thread]; Thread
0x180008bb5  call    cs:__imp_SetThreadToken
0x180008bbb  test    eax, eax
0x180008bbd  jnz     short loc_180008BD4
0x180008bbf  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\monitors\\ap"...
0x180008bc6  mov     edx, 0B5h; void *
0x180008bcb  mov     rcx, rbx; this
0x180008bce  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180008bd4  mov     rbx, [rsp+58h]
0x180008bd9  mov     rcx, [rsp+58h+Thread]; hThread
0x180008bde  call    cs:__imp_ResumeThread
0x180008be4  cmp     eax, 0FFFFFFFFh
0x180008be7  jnz     short loc_180008BFE
0x180008be9  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\monitors\\ap"...
0x180008bf0  mov     edx, 0B6h; void *
0x180008bf5  mov     rcx, rbx; this
0x180008bf8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180008bfe  lea     rcx, [rsp+58h+arg_8]
0x180008c03  call    std__unique_ptr_void__lambda_5beab740efbf3494b609d1267351a2ce______unique_ptr_void__lambda_5beab740efbf3494b609d1267351a2ce___
0x180008c08  add     rsp, 30h
0x180008c0c  pop     r14
0x180008c0e  pop     rdi
0x180008c0f  pop     rsi
0x180008c10  pop     rbp
0x180008c11  pop     rbx
0x180008c12  retn
```
