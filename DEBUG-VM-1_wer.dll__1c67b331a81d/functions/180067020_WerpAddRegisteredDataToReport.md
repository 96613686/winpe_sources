# WerpAddRegisteredDataToReport

- ea: `0x180067020`
- end: `0x180067321`
- name: `WerpAddRegisteredDataToReport`
- size: `769`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e4b8`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001fe24`
- `0x18003bf14`
- `0x180040c34`
- `0x180067020`
- `0x1800a3930`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067209`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab1e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067209`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab1e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006715d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006715d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180067082`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180067082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067258`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800670fe`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800671ca`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800670fe`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800671ca`

## pseudocode

```c
__int64 __fastcall WerpAddRegisteredDataToReport(void *a1, void *a2)
{
  unsigned int GatherListStart; // ebx
  LPCVOID v5; // rdi
  unsigned int v6; // r15d
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // eax
  unsigned __int16 v11; // dx
  SIZE_T v12; // r13
  LPCVOID *v13; // r14
  int (*v14)(void *, const wchar_t *, enum _WER_FILE_TYPE, unsigned int, const wchar_t *, const wchar_t *); // r9
  unsigned __int16 v15; // dx
  DWORD LastError; // eax
  int (*lpNumberOfBytesRead)(void *, unsigned int, void *, unsigned int, unsigned int); // [rsp+20h] [rbp-98h]
  int (*v19)(void *, unsigned int, void *, unsigned int, unsigned int); // [rsp+28h] [rbp-90h]
  unsigned int v20; // [rsp+30h] [rbp-88h]
  __int64 Buffer; // [rsp+60h] [rbp-58h] BYREF
  __int128 v22; // [rsp+68h] [rbp-50h]
  __int64 v23; // [rsp+78h] [rbp-40h]
  DWORD ProcessId; // [rsp+C0h] [rbp+8h]
  SIZE_T NumberOfBytesRead; // [rsp+D0h] [rbp+18h] BYREF
  LPCVOID lpBaseAddress; // [rsp+D8h] [rbp+20h] BYREF

  lpBaseAddress = 0;
  if ( a1 && a2 )
  {
    GatherListStart = WerpGetGatherListStart(a2, (struct WER_GATHER **)&lpBaseAddress);
    if ( (GatherListStart & 0x80000000) == 0 )
    {
      v5 = lpBaseAddress;
      if ( lpBaseAddress )
      {
        v6 = 0;
        ProcessId = GetProcessId(a2);
        if ( !ProcessId )
          MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7, v9);
        while ( v5 )
        {
          v10 = v6++;
          if ( v10 >= 0x200 )
            break;
          Buffer = 0;
          v22 = 0;
          v23 = 0;
          NumberOfBytesRead = 0;
          if ( !ReadProcessMemory(a2, v5, &Buffer, 0x20u, &NumberOfBytesRead) || NumberOfBytesRead != 32 )
          {
            LastError = GetLastError();
            GatherListStart = ERROR_HR_FROM_WIN32(LastError);
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
            return GatherListStart;
          }
          v11 = v22 & 0x3FFF;
          if ( (unsigned __int16)((v22 & 0x3FFF) - 32) > 0x208u )
          {
            GatherListStart = ERROR_HR_FROM_WIN32(0xDu);
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids, v15);
            return GatherListStart;
          }
          NumberOfBytesRead = 0;
          v12 = v11;
          v13 = (LPCVOID *)HeapAlloc(g_hWerheap, 0, v11);
          if ( !v13 )
          {
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
            return (unsigned int)-2147024882;
          }
          if ( ReadProcessMemory(a2, v5, v13, v12, &NumberOfBytesRead) )
          {
            v5 = *v13;
            lpBaseAddress = *v13;
            WerpAddGatherBlockToReport(a1, ProcessId, (struct WER_GATHER *)v13, v14, lpNumberOfBytesRead, v19, v20);
          }
          else
          {
            v5 = 0;
            lpBaseAddress = 0;
          }
          HeapFree(g_hWerheap, 0, v13);
        }
      }
    }
    return GatherListStart;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180067020  mov     rax, rsp
0x180067023  push    rbx
0x180067024  push    rsi
0x180067025  push    rdi
0x180067026  push    r12
0x180067028  push    r13
0x18006702a  push    r14
0x18006702c  push    r15
0x18006702e  sub     rsp, 80h
0x180067035  mov     rsi, rdx
0x180067038  mov     r12, rcx
0x18006703b  mov     qword ptr [rax+20h], 0
0x180067043  test    rcx, rcx
0x180067046  jz      loc_1800672DB
0x18006704c  test    rdx, rdx
0x18006704f  jz      loc_1800672DB
0x180067055  lea     rdx, [rax+20h]; struct WER_GATHER **
0x180067059  mov     rcx, rsi; void *
0x18006705c  call    ?WerpGetGatherListStart@@YAJPEAXPEAPEAUWER_GATHER@@@Z; WerpGetGatherListStart(void *,WER_GATHER * *)
0x180067061  mov     ebx, eax
0x180067063  test    eax, eax
0x180067065  js      loc_1800672D7
0x18006706b  mov     rdi, [rsp+0B8h+lpBaseAddress]
0x180067073  test    rdi, rdi
0x180067076  jz      loc_1800672D7
0x18006707c  xor     r15d, r15d
0x18006707f  mov     rcx, rsi; Process
0x180067082  call    cs:__imp_GetProcessId
0x180067088  mov     [rsp+0B8h+arg_0], eax
0x18006708f  test    eax, eax
0x180067091  jnz     short loc_180067099
0x180067093  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180067098  nop
0x180067099  mov     r14d, 20h ; ' '
0x18006709f  test    rdi, rdi
0x1800670a2  jz      loc_180067299
0x1800670a8  mov     eax, r15d
0x1800670ab  inc     r15d
0x1800670ae  mov     [rsp+0B8h+var_70], r15d
0x1800670b3  cmp     eax, 200h
0x1800670b8  jnb     loc_180067299
0x1800670be  mov     [rsp+0B8h+Buffer], 0
0x1800670c7  xorps   xmm0, xmm0
0x1800670ca  xor     eax, eax
0x1800670cc  movups  [rsp+0B8h+var_50], xmm0
0x1800670d1  mov     [rsp+0B8h+var_40], rax
0x1800670d6  mov     [rsp+0B8h+var_78], ax
0x1800670db  mov     [rsp+0B8h+NumberOfBytesRead], rax
0x1800670e3  lea     rax, [rsp+0B8h+NumberOfBytesRead]
0x1800670eb  mov     [rsp+0B8h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1800670f0  mov     r9d, r14d; nSize
0x1800670f3  lea     r8, [rsp+0B8h+Buffer]; lpBuffer
0x1800670f8  mov     rdx, rdi; lpBaseAddress
0x1800670fb  mov     rcx, rsi; hProcess
0x1800670fe  call    cs:__imp_ReadProcessMemory
0x180067104  test    eax, eax
0x180067106  jz      loc_180067258
0x18006710c  cmp     [rsp+0B8h+NumberOfBytesRead], r14
0x180067114  jnz     loc_180067258
0x18006711a  mov     eax, 3FFFh
0x18006711f  movzx   edx, word ptr [rsp+0B8h+var_50]
0x180067124  and     dx, ax
0x180067127  mov     [rsp+0B8h+var_78], dx
0x18006712c  movzx   eax, dx
0x18006712f  sub     ax, r14w
0x180067133  mov     ecx, 208h
0x180067138  cmp     ax, cx
0x18006713b  ja      loc_180067214
0x180067141  mov     [rsp+0B8h+NumberOfBytesRead], 0
0x18006714d  movzx   r13d, dx
0x180067151  mov     r8d, r13d; dwBytes
0x180067154  xor     edx, edx; dwFlags
0x180067156  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18006715d  call    cs:__imp_HeapAlloc
0x180067163  mov     r14, rax
0x180067166  mov     [rsp+0B8h+var_68], rax
0x18006716b  mov     [rsp+0B8h+var_60], rax
0x180067170  test    rax, rax
0x180067173  jnz     short loc_1800671B1
0x180067175  lea     rax, WPP_GLOBAL_Control
0x18006717c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067183  cmp     rcx, rax
0x180067186  jz      short loc_1800671A3
0x180067188  test    byte ptr [rcx+1Ch], 1
0x18006718c  jz      short loc_1800671A3
0x18006718e  mov     edx, 0ACh
0x180067193  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x18006719a  mov     rcx, [rcx+10h]
0x18006719e  call    WPP_SF_
0x1800671a3  mov     ebx, 8007000Eh
0x1800671a8  mov     [rsp+0B8h+var_74], ebx
0x1800671ac  jmp     loc_180067299
0x1800671b1  lea     rax, [rsp+0B8h+NumberOfBytesRead]
0x1800671b9  mov     [rsp+0B8h+lpNumberOfBytesRead], rax; int (*)(void *, unsigned int, void *, unsigned int, unsigned int)
0x1800671be  mov     r9, r13; nSize
0x1800671c1  mov     r8, r14; lpBuffer
0x1800671c4  mov     rdx, rdi; lpBaseAddress
0x1800671c7  mov     rcx, rsi; hProcess
0x1800671ca  call    cs:__imp_ReadProcessMemory
0x1800671d0  test    eax, eax
0x1800671d2  jz      short loc_1800671F3
0x1800671d4  mov     rdi, [r14]
0x1800671d7  mov     [rsp+0B8h+lpBaseAddress], rdi
0x1800671df  mov     r8, r14; struct WER_GATHER *
0x1800671e2  mov     edx, [rsp+0B8h+arg_0]; unsigned int
0x1800671e9  mov     rcx, r12; void *
0x1800671ec  call    ?WerpAddGatherBlockToReport@@YAJPEAXKPEAUWER_GATHER@@P6AJ0PEB_WW4_WER_FILE_TYPE@@K22@ZP6AJ0K0KK@Z5K@Z; WerpAddGatherBlockToReport(void *,ulong,WER_GATHER *,long (*)(void *,wchar_t const *,_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *),long (*)(void *,ulong,void *,ulong,ulong),long (*)(void *,ulong,void *,ulong,ulong),ulong)
0x1800671f1  jmp     short loc_1800671FD
0x1800671f3  xor     edi, edi
0x1800671f5  mov     [rsp+0B8h+lpBaseAddress], rdi
0x1800671fd  mov     r8, r14; lpMem
0x180067200  xor     edx, edx; dwFlags
0x180067202  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180067209  call    cs:__imp_HeapFree
0x18006720f  jmp     loc_180067099
0x180067214  mov     ecx, 0Dh; unsigned int
0x180067219  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006721e  mov     ebx, eax
0x180067220  mov     [rsp+0B8h+var_74], eax
0x180067224  lea     rax, WPP_GLOBAL_Control
0x18006722b  mov     rcx, cs:WPP_GLOBAL_Control
0x180067232  cmp     rcx, rax
0x180067235  jz      short loc_180067299
0x180067237  test    byte ptr [rcx+1Ch], 1
0x18006723b  jz      short loc_180067299
0x18006723d  movzx   r9d, dx
0x180067241  mov     edx, 0ADh
0x180067246  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x18006724d  mov     rcx, [rcx+10h]
0x180067251  call    WPP_SF_d
0x180067256  jmp     short loc_180067299
0x180067258  call    cs:__imp_GetLastError
0x18006725e  mov     ecx, eax; unsigned int
0x180067260  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180067265  mov     ebx, eax
0x180067267  mov     [rsp+0B8h+var_74], eax
0x18006726b  lea     rax, WPP_GLOBAL_Control
0x180067272  mov     rcx, cs:WPP_GLOBAL_Control
0x180067279  cmp     rcx, rax
0x18006727c  jz      short loc_180067299
0x18006727e  test    byte ptr [rcx+1Ch], 1
0x180067282  jz      short loc_180067299
0x180067284  mov     edx, 0ABh
0x180067289  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x180067290  mov     rcx, [rcx+10h]
0x180067294  call    WPP_SF_
0x180067299  jmp     short loc_1800672D7
0x18006729b  lea     rax, WPP_GLOBAL_Control
0x1800672a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800672a9  cmp     rcx, rax
0x1800672ac  jz      short loc_1800672C9
0x1800672ae  test    byte ptr [rcx+1Ch], 1
0x1800672b2  jz      short loc_1800672C9
0x1800672b4  mov     edx, 0AEh
0x1800672b9  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x1800672c0  mov     rcx, [rcx+10h]
0x1800672c4  call    WPP_SF_
0x1800672c9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800672ce  mov     ebx, 80004005h
0x1800672d3  mov     [rsp+0B8h+var_74], ebx
0x1800672d7  mov     eax, ebx
0x1800672d9  jmp     short loc_18006730E
0x1800672db  lea     rax, WPP_GLOBAL_Control
0x1800672e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800672e9  cmp     rcx, rax
0x1800672ec  jz      short loc_180067309
0x1800672ee  test    byte ptr [rcx+1Ch], 1
0x1800672f2  jz      short loc_180067309
0x1800672f4  mov     edx, 0AAh
0x1800672f9  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x180067300  mov     rcx, [rcx+10h]
0x180067304  call    WPP_SF_
0x180067309  mov     eax, 80070057h
0x18006730e  add     rsp, 80h
0x180067315  pop     r15
0x180067317  pop     r14
0x180067319  pop     r13
0x18006731b  pop     r12
0x18006731d  pop     rdi
0x18006731e  pop     rsi
0x18006731f  pop     rbx
0x180067320  retn
0x1800ab1d2  push    rbp
0x1800ab1d4  sub     rsp, 40h
0x1800ab1d8  mov     rbp, rdx
0x1800ab1db  mov     r8, [rbp+50h]; lpMem
0x1800ab1df  xor     edx, edx; dwFlags
0x1800ab1e1  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800ab1e8  call    cs:__imp_HeapFree
0x1800ab1ee  nop
0x1800ab1ef  add     rsp, 40h
0x1800ab1f3  pop     rbp
0x1800ab1f4  retn
```
