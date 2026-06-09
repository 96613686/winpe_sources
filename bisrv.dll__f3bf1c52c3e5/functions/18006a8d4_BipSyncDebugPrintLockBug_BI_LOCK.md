# BipSyncDebugPrintLockBug(_BI_LOCK *)

- ea: `0x18006a8d4`
- end: `0x18006aba5`
- name: `?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z`
- size: `721`
- prototype: `void __fastcall(struct _BI_LOCK *)`
- caller_count: `50`
- callee_count: `3`
- tags: ``

## callers

- `0x180004c3c`
- `0x180006300`
- `0x18000638c`
- `0x1800064cc`
- `0x180006808`
- `0x1800075f8`
- `0x1800076f4`
- `0x180007938`
- `0x18000cd10`
- `0x18000d7c0`
- `0x18000da50`
- `0x18000db40`
- `0x18000e360`
- `0x18000e470`
- `0x1800101a4`
- `0x18001027c`
- `0x180010c70`
- `0x180011e98`
- `0x180012034`
- `0x180012584`
- `0x180012960`
- `0x180013c70`
- `0x1800144f4`
- `0x180014ea0`
- `0x1800154b0`
- `0x180015930`
- `0x180015b38`
- `0x18001614c`
- `0x180023b00`
- `0x18002b100`
- `0x18002c4e0`
- `0x18002d0b0`
- `0x18002dbb0`
- `0x18002e2d8`
- `0x18002eb64`
- `0x180032fc8`
- `0x180035d28`
- `0x180035e2c`
- `0x1800366a8`
- `0x180036740`
- `0x180037500`
- `0x18003a024`
- `0x18003a35c`
- `0x180041a9c`
- `0x180053db0`
- `0x180058b20`
- `0x180059ad0`
- `0x18005d730`
- `0x18005db80`
- `0x1800617d0`

## callees

- `0x18003f778`
- `0x18006a8d4`
- `0x1800946a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006aa01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006aa01`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006a9fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006aa2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006ab78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006a9fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006aa2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006ab78`

## string_xrefs

- `0x18006aa07`: `The current thread (%u) is already holding the following lock types:\n`

## pseudocode

```c
void __fastcall BipSyncDebugPrintLockBug(struct _BI_LOCK *a1)
{
  int v1; // edx
  const wchar_t *v2; // r9
  DWORD CurrentThreadId; // eax
  int v4; // ebx
  _QWORD *ThreadLocalStoragePointer; // rax
  _DWORD *v6; // rsi
  _DWORD *v7; // rdi
  const wchar_t *v8; // rdx
  const wchar_t *v9; // rax
  WCHAR OutputString[128]; // [rsp+30h] [rbp-138h] BYREF

  v1 = *((_DWORD *)a1 + 2);
  if ( v1 > 8 )
  {
    switch ( v1 )
    {
      case 9:
        v2 = L"BiCoalesceLock";
        goto LABEL_31;
      case 10:
        v2 = L"BiEnergyQuotaMgrLock";
        goto LABEL_31;
      case 11:
        v2 = L"BiEnergyBudgetLock";
        goto LABEL_31;
      case 12:
        v2 = L"BiEnergyQuotaQueueLock";
        goto LABEL_31;
      case 13:
        v2 = L"BiExecutionMgrLock";
        goto LABEL_31;
      case 14:
        v2 = L"BiCleanLock";
        goto LABEL_31;
    }
    goto LABEL_24;
  }
  switch ( v1 )
  {
    case 8:
      v2 = L"BiPackageLock";
      goto LABEL_31;
    case 1:
      v2 = L"BiGlobalLock";
      goto LABEL_31;
    case 2:
      v2 = L"BiSessionLock";
      goto LABEL_31;
    case 3:
      v2 = L"BiEventTableLock";
      goto LABEL_31;
    case 4:
      v2 = L"BiWorkItemTableLock";
      goto LABEL_31;
    case 5:
      v2 = L"BiPackageTableLock";
      goto LABEL_31;
    case 6:
      v2 = L"BiSystemStateLock";
      goto LABEL_31;
  }
  if ( v1 != 7 )
  {
LABEL_24:
    v2 = L"Unknown";
    goto LABEL_31;
  }
  v2 = L"BiWorkItemLock";
LABEL_31:
  if ( (int)RtlStringCchPrintfW(
              OutputString,
              0x80u,
              L"!!!!! BISYNC: Cannot acquire lock with type: %ws (level: %u) !!!!!\n",
              v2,
              *((_DWORD *)a1 + 2)) >= 0 )
  {
    OutputDebugStringW(OutputString);
    CurrentThreadId = GetCurrentThreadId();
    if ( (int)RtlStringCchPrintfW(
                OutputString,
                0x80u,
                L"The current thread (%u) is already holding the following lock types:\n",
                CurrentThreadId) >= 0 )
    {
      OutputDebugStringW(OutputString);
      v4 = 0;
      ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
      v6 = (_DWORD *)(ThreadLocalStoragePointer[(unsigned int)tls_index] + 8LL);
      v7 = (_DWORD *)(ThreadLocalStoragePointer[(unsigned int)tls_index] + 4LL);
      do
      {
        if ( ((1 << v4) & *v7) != 0 )
        {
          v8 = L"EXCLUSIVE";
          if ( ((1 << v4) & *v6) == 0 )
            v8 = L"SHARED";
          if ( v4 > 8 )
          {
            switch ( v4 )
            {
              case 9:
                v9 = L"BiCoalesceLock";
                break;
              case 10:
                v9 = L"BiEnergyQuotaMgrLock";
                break;
              case 11:
                v9 = L"BiEnergyBudgetLock";
                break;
              case 12:
                v9 = L"BiEnergyQuotaQueueLock";
                break;
              case 13:
                v9 = L"BiExecutionMgrLock";
                break;
              default:
                v9 = L"BiCleanLock";
                break;
            }
          }
          else
          {
            switch ( v4 )
            {
              case 8:
                v9 = L"BiPackageLock";
                break;
              case 1:
                v9 = L"BiGlobalLock";
                break;
              case 2:
                v9 = L"BiSessionLock";
                break;
              case 3:
                v9 = L"BiEventTableLock";
                break;
              case 4:
                v9 = L"BiWorkItemTableLock";
                break;
              case 5:
                v9 = L"BiPackageTableLock";
                break;
              case 6:
                v9 = L"BiSystemStateLock";
                break;
              case 7:
                v9 = L"BiWorkItemLock";
                break;
              default:
                v9 = L"Unknown";
                break;
            }
          }
          if ( (int)RtlStringCchPrintfW(OutputString, 0x80u, L"\t%u: %ws\t\t(%ws)\n", (unsigned int)v4, v9, v8) < 0 )
            return;
          OutputDebugStringW(OutputString);
        }
        ++v4;
      }
      while ( (unsigned int)v4 < 0xF );
    }
  }
}

```

## disassembly

```asm
0x18006a8d4  push    rbx
0x18006a8d6  push    rbp
0x18006a8d7  push    rsi
0x18006a8d8  push    rdi
0x18006a8d9  sub     rsp, 148h
0x18006a8e0  mov     rax, cs:__security_cookie
0x18006a8e7  xor     rax, rsp
0x18006a8ea  mov     [rsp+168h+var_38], rax
0x18006a8f2  mov     edx, [rcx+8]
0x18006a8f5  cmp     edx, 8
0x18006a8f8  jg      short loc_18006A975
0x18006a8fa  jz      short loc_18006A96C
0x18006a8fc  mov     ecx, edx
0x18006a8fe  sub     ecx, 1
0x18006a901  jz      short loc_18006A963
0x18006a903  sub     ecx, 1
0x18006a906  jz      short loc_18006A95A
0x18006a908  sub     ecx, 1
0x18006a90b  jz      short loc_18006A951
0x18006a90d  sub     ecx, 1
0x18006a910  jz      short loc_18006A945
0x18006a912  sub     ecx, 1
0x18006a915  jz      short loc_18006A939
0x18006a917  sub     ecx, 1
0x18006a91a  jz      short loc_18006A92D
0x18006a91c  cmp     ecx, 1
0x18006a91f  jnz     short loc_18006A995
0x18006a921  lea     r9, aBiworkitemlock; "BiWorkItemLock"
0x18006a928  jmp     loc_18006A9D2
0x18006a92d  lea     r9, aBisystemstatel; "BiSystemStateLock"
0x18006a934  jmp     loc_18006A9D2
0x18006a939  lea     r9, aBipackagetable; "BiPackageTableLock"
0x18006a940  jmp     loc_18006A9D2
0x18006a945  lea     r9, aBiworkitemtabl; "BiWorkItemTableLock"
0x18006a94c  jmp     loc_18006A9D2
0x18006a951  lea     r9, aBieventtablelo; "BiEventTableLock"
0x18006a958  jmp     short loc_18006A9D2
0x18006a95a  lea     r9, aBisessionlock; "BiSessionLock"
0x18006a961  jmp     short loc_18006A9D2
0x18006a963  lea     r9, aBigloballock; "BiGlobalLock"
0x18006a96a  jmp     short loc_18006A9D2
0x18006a96c  lea     r9, aBipackagelock; "BiPackageLock"
0x18006a973  jmp     short loc_18006A9D2
0x18006a975  mov     ecx, edx
0x18006a977  sub     ecx, 9
0x18006a97a  jz      short loc_18006A9CB
0x18006a97c  sub     ecx, 1
0x18006a97f  jz      short loc_18006A9C2
0x18006a981  sub     ecx, 1
0x18006a984  jz      short loc_18006A9B9
0x18006a986  sub     ecx, 1
0x18006a989  jz      short loc_18006A9B0
0x18006a98b  sub     ecx, 1
0x18006a98e  jz      short loc_18006A9A7
0x18006a990  cmp     ecx, 1
0x18006a993  jz      short loc_18006A99E
0x18006a995  lea     r9, aUnknown; "Unknown"
0x18006a99c  jmp     short loc_18006A9D2
0x18006a99e  lea     r9, aBicleanlock; "BiCleanLock"
0x18006a9a5  jmp     short loc_18006A9D2
0x18006a9a7  lea     r9, aBiexecutionmgr; "BiExecutionMgrLock"
0x18006a9ae  jmp     short loc_18006A9D2
0x18006a9b0  lea     r9, aBienergyquotaq; "BiEnergyQuotaQueueLock"
0x18006a9b7  jmp     short loc_18006A9D2
0x18006a9b9  lea     r9, aBienergybudget; "BiEnergyBudgetLock"
0x18006a9c0  jmp     short loc_18006A9D2
0x18006a9c2  lea     r9, aBienergyquotam; "BiEnergyQuotaMgrLock"
0x18006a9c9  jmp     short loc_18006A9D2
0x18006a9cb  lea     r9, aBicoalescelock; "BiCoalesceLock"
0x18006a9d2  mov     dword ptr [rsp+168h+var_148], edx
0x18006a9d6  lea     r8, aBisyncCannotAc; "!!!!! BISYNC: Cannot acquire lock with "...
0x18006a9dd  mov     ebp, 80h
0x18006a9e2  lea     rcx, [rsp+168h+OutputString]; unsigned __int16 *
0x18006a9e7  mov     edx, ebp; unsigned __int64
0x18006a9e9  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006a9ee  test    eax, eax
0x18006a9f0  js      loc_18006AB89
0x18006a9f6  lea     rcx, [rsp+168h+OutputString]; lpOutputString
0x18006a9fb  call    cs:__imp_OutputDebugStringW
0x18006aa01  call    cs:__imp_GetCurrentThreadId
0x18006aa07  lea     r8, aTheCurrentThre; "The current thread (%u) is already hold"...
0x18006aa0e  mov     edx, ebp; unsigned __int64
0x18006aa10  mov     r9d, eax
0x18006aa13  lea     rcx, [rsp+168h+OutputString]; unsigned __int16 *
0x18006aa18  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006aa1d  test    eax, eax
0x18006aa1f  js      loc_18006AB89
0x18006aa25  lea     rcx, [rsp+168h+OutputString]; lpOutputString
0x18006aa2a  call    cs:__imp_OutputDebugStringW
0x18006aa30  mov     ecx, cs:_tls_index
0x18006aa36  xor     ebx, ebx
0x18006aa38  mov     rax, gs:58h
0x18006aa41  mov     esi, 8
0x18006aa46  mov     edi, 4
0x18006aa4b  add     rsi, [rax+rcx*8]
0x18006aa4f  add     rdi, [rax+rcx*8]
0x18006aa53  mov     ecx, ebx
0x18006aa55  mov     eax, 1
0x18006aa5a  shl     eax, cl
0x18006aa5c  test    [rdi], eax
0x18006aa5e  jz      loc_18006AB7E
0x18006aa64  test    [rsi], eax
0x18006aa66  lea     rdx, aExclusive; "EXCLUSIVE"
0x18006aa6d  lea     rax, aShared; "SHARED"
0x18006aa74  cmovz   rdx, rax
0x18006aa78  cmp     ebx, 8
0x18006aa7b  jg      short loc_18006AAF3
0x18006aa7d  jz      short loc_18006AAEA
0x18006aa7f  sub     ecx, 1
0x18006aa82  jz      short loc_18006AAE1
0x18006aa84  sub     ecx, 1
0x18006aa87  jz      short loc_18006AAD8
0x18006aa89  sub     ecx, 1
0x18006aa8c  jz      short loc_18006AACF
0x18006aa8e  sub     ecx, 1
0x18006aa91  jz      short loc_18006AAC6
0x18006aa93  sub     ecx, 1
0x18006aa96  jz      short loc_18006AABA
0x18006aa98  sub     ecx, 1
0x18006aa9b  jz      short loc_18006AAAE
0x18006aa9d  cmp     ecx, 1
0x18006aaa0  jnz     short loc_18006AB11
0x18006aaa2  lea     rax, aBiworkitemlock; "BiWorkItemLock"
0x18006aaa9  jmp     loc_18006AB4E
0x18006aaae  lea     rax, aBisystemstatel; "BiSystemStateLock"
0x18006aab5  jmp     loc_18006AB4E
0x18006aaba  lea     rax, aBipackagetable; "BiPackageTableLock"
0x18006aac1  jmp     loc_18006AB4E
0x18006aac6  lea     rax, aBiworkitemtabl; "BiWorkItemTableLock"
0x18006aacd  jmp     short loc_18006AB4E
0x18006aacf  lea     rax, aBieventtablelo; "BiEventTableLock"
0x18006aad6  jmp     short loc_18006AB4E
0x18006aad8  lea     rax, aBisessionlock; "BiSessionLock"
0x18006aadf  jmp     short loc_18006AB4E
0x18006aae1  lea     rax, aBigloballock; "BiGlobalLock"
0x18006aae8  jmp     short loc_18006AB4E
0x18006aaea  lea     rax, aBipackagelock; "BiPackageLock"
0x18006aaf1  jmp     short loc_18006AB4E
0x18006aaf3  sub     ecx, 9
0x18006aaf6  jz      short loc_18006AB47
0x18006aaf8  sub     ecx, 1
0x18006aafb  jz      short loc_18006AB3E
0x18006aafd  sub     ecx, 1
0x18006ab00  jz      short loc_18006AB35
0x18006ab02  sub     ecx, 1
0x18006ab05  jz      short loc_18006AB2C
0x18006ab07  sub     ecx, 1
0x18006ab0a  jz      short loc_18006AB23
0x18006ab0c  cmp     ecx, 1
0x18006ab0f  jz      short loc_18006AB1A
0x18006ab11  lea     rax, aUnknown; "Unknown"
0x18006ab18  jmp     short loc_18006AB4E
0x18006ab1a  lea     rax, aBicleanlock; "BiCleanLock"
0x18006ab21  jmp     short loc_18006AB4E
0x18006ab23  lea     rax, aBiexecutionmgr; "BiExecutionMgrLock"
0x18006ab2a  jmp     short loc_18006AB4E
0x18006ab2c  lea     rax, aBienergyquotaq; "BiEnergyQuotaQueueLock"
0x18006ab33  jmp     short loc_18006AB4E
0x18006ab35  lea     rax, aBienergybudget; "BiEnergyBudgetLock"
0x18006ab3c  jmp     short loc_18006AB4E
0x18006ab3e  lea     rax, aBienergyquotam; "BiEnergyQuotaMgrLock"
0x18006ab45  jmp     short loc_18006AB4E
0x18006ab47  lea     rax, aBicoalescelock; "BiCoalesceLock"
0x18006ab4e  mov     [rsp+168h+var_140], rdx
0x18006ab53  lea     r8, aUWsWs_0; "\t%u: %ws\t\t(%ws)\n"
0x18006ab5a  mov     rdx, rbp; unsigned __int64
0x18006ab5d  mov     [rsp+168h+var_148], rax
0x18006ab62  mov     r9d, ebx
0x18006ab65  lea     rcx, [rsp+168h+OutputString]; unsigned __int16 *
0x18006ab6a  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006ab6f  test    eax, eax
0x18006ab71  js      short loc_18006AB89
0x18006ab73  lea     rcx, [rsp+168h+OutputString]; lpOutputString
0x18006ab78  call    cs:__imp_OutputDebugStringW
0x18006ab7e  inc     ebx
0x18006ab80  cmp     ebx, 0Fh
0x18006ab83  jb      loc_18006AA53
0x18006ab89  mov     rcx, [rsp+168h+var_38]
0x18006ab91  xor     rcx, rsp; StackCookie
0x18006ab94  call    __security_check_cookie
0x18006ab99  add     rsp, 148h
0x18006aba0  pop     rdi
0x18006aba1  pop     rsi
0x18006aba2  pop     rbp
0x18006aba3  pop     rbx
0x18006aba4  retn
```
