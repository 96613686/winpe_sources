# WerpAddRegisteredDataToReport

- ea: `0x180066fd0`
- end: `0x1800672d1`
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
- `0x180066fd0`
- `0x1800a38e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800671b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab198`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800671b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab198`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006710d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006710d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180067032`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180067032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067208`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800670ae`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006717a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800670ae`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006717a`

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
0x180066fd0  mov     rax, rsp
0x180066fd3  push    rbx
0x180066fd4  push    rsi
0x180066fd5  push    rdi
0x180066fd6  push    r12
0x180066fd8  push    r13
0x180066fda  push    r14
0x180066fdc  push    r15
0x180066fde  sub     rsp, 80h
0x180066fe5  mov     rsi, rdx
0x180066fe8  mov     r12, rcx
0x180066feb  mov     qword ptr [rax+20h], 0
0x180066ff3  test    rcx, rcx
0x180066ff6  jz      loc_18006728B
0x180066ffc  test    rdx, rdx
0x180066fff  jz      loc_18006728B
0x180067005  lea     rdx, [rax+20h]; struct WER_GATHER **
0x180067009  mov     rcx, rsi; void *
0x18006700c  call    ?WerpGetGatherListStart@@YAJPEAXPEAPEAUWER_GATHER@@@Z; WerpGetGatherListStart(void *,WER_GATHER * *)
0x180067011  mov     ebx, eax
0x180067013  test    eax, eax
0x180067015  js      loc_180067287
0x18006701b  mov     rdi, [rsp+0B8h+lpBaseAddress]
0x180067023  test    rdi, rdi
0x180067026  jz      loc_180067287
0x18006702c  xor     r15d, r15d
0x18006702f  mov     rcx, rsi; Process
0x180067032  call    cs:__imp_GetProcessId
0x180067038  mov     [rsp+0B8h+arg_0], eax
0x18006703f  test    eax, eax
0x180067041  jnz     short loc_180067049
0x180067043  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180067048  nop
0x180067049  mov     r14d, 20h ; ' '
0x18006704f  test    rdi, rdi
0x180067052  jz      loc_180067249
0x180067058  mov     eax, r15d
0x18006705b  inc     r15d
0x18006705e  mov     [rsp+0B8h+var_70], r15d
0x180067063  cmp     eax, 200h
0x180067068  jnb     loc_180067249
0x18006706e  mov     [rsp+0B8h+Buffer], 0
0x180067077  xorps   xmm0, xmm0
0x18006707a  xor     eax, eax
0x18006707c  movups  [rsp+0B8h+var_50], xmm0
0x180067081  mov     [rsp+0B8h+var_40], rax
0x180067086  mov     [rsp+0B8h+var_78], ax
0x18006708b  mov     [rsp+0B8h+NumberOfBytesRead], rax
0x180067093  lea     rax, [rsp+0B8h+NumberOfBytesRead]
0x18006709b  mov     [rsp+0B8h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1800670a0  mov     r9d, r14d; nSize
0x1800670a3  lea     r8, [rsp+0B8h+Buffer]; lpBuffer
0x1800670a8  mov     rdx, rdi; lpBaseAddress
0x1800670ab  mov     rcx, rsi; hProcess
0x1800670ae  call    cs:__imp_ReadProcessMemory
0x1800670b4  test    eax, eax
0x1800670b6  jz      loc_180067208
0x1800670bc  cmp     [rsp+0B8h+NumberOfBytesRead], r14
0x1800670c4  jnz     loc_180067208
0x1800670ca  mov     eax, 3FFFh
0x1800670cf  movzx   edx, word ptr [rsp+0B8h+var_50]
0x1800670d4  and     dx, ax
0x1800670d7  mov     [rsp+0B8h+var_78], dx
0x1800670dc  movzx   eax, dx
0x1800670df  sub     ax, r14w
0x1800670e3  mov     ecx, 208h
0x1800670e8  cmp     ax, cx
0x1800670eb  ja      loc_1800671C4
0x1800670f1  mov     [rsp+0B8h+NumberOfBytesRead], 0
0x1800670fd  movzx   r13d, dx
0x180067101  mov     r8d, r13d; dwBytes
0x180067104  xor     edx, edx; dwFlags
0x180067106  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18006710d  call    cs:__imp_HeapAlloc
0x180067113  mov     r14, rax
0x180067116  mov     [rsp+0B8h+var_68], rax
0x18006711b  mov     [rsp+0B8h+var_60], rax
0x180067120  test    rax, rax
0x180067123  jnz     short loc_180067161
0x180067125  lea     rax, WPP_GLOBAL_Control
0x18006712c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067133  cmp     rcx, rax
0x180067136  jz      short loc_180067153
0x180067138  test    byte ptr [rcx+1Ch], 1
0x18006713c  jz      short loc_180067153
0x18006713e  mov     edx, 0ACh
0x180067143  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x18006714a  mov     rcx, [rcx+10h]
0x18006714e  call    WPP_SF_
0x180067153  mov     ebx, 8007000Eh
0x180067158  mov     [rsp+0B8h+var_74], ebx
0x18006715c  jmp     loc_180067249
0x180067161  lea     rax, [rsp+0B8h+NumberOfBytesRead]
0x180067169  mov     [rsp+0B8h+lpNumberOfBytesRead], rax; int (*)(void *, unsigned int, void *, unsigned int, unsigned int)
0x18006716e  mov     r9, r13; nSize
0x180067171  mov     r8, r14; lpBuffer
0x180067174  mov     rdx, rdi; lpBaseAddress
0x180067177  mov     rcx, rsi; hProcess
0x18006717a  call    cs:__imp_ReadProcessMemory
0x180067180  test    eax, eax
0x180067182  jz      short loc_1800671A3
0x180067184  mov     rdi, [r14]
0x180067187  mov     [rsp+0B8h+lpBaseAddress], rdi
0x18006718f  mov     r8, r14; struct WER_GATHER *
0x180067192  mov     edx, [rsp+0B8h+arg_0]; unsigned int
0x180067199  mov     rcx, r12; void *
0x18006719c  call    ?WerpAddGatherBlockToReport@@YAJPEAXKPEAUWER_GATHER@@P6AJ0PEB_WW4_WER_FILE_TYPE@@K22@ZP6AJ0K0KK@Z5K@Z; WerpAddGatherBlockToReport(void *,ulong,WER_GATHER *,long (*)(void *,wchar_t const *,_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *),long (*)(void *,ulong,void *,ulong,ulong),long (*)(void *,ulong,void *,ulong,ulong),ulong)
0x1800671a1  jmp     short loc_1800671AD
0x1800671a3  xor     edi, edi
0x1800671a5  mov     [rsp+0B8h+lpBaseAddress], rdi
0x1800671ad  mov     r8, r14; lpMem
0x1800671b0  xor     edx, edx; dwFlags
0x1800671b2  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800671b9  call    cs:__imp_HeapFree
0x1800671bf  jmp     loc_180067049
0x1800671c4  mov     ecx, 0Dh; unsigned int
0x1800671c9  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800671ce  mov     ebx, eax
0x1800671d0  mov     [rsp+0B8h+var_74], eax
0x1800671d4  lea     rax, WPP_GLOBAL_Control
0x1800671db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800671e2  cmp     rcx, rax
0x1800671e5  jz      short loc_180067249
0x1800671e7  test    byte ptr [rcx+1Ch], 1
0x1800671eb  jz      short loc_180067249
0x1800671ed  movzx   r9d, dx
0x1800671f1  mov     edx, 0ADh
0x1800671f6  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x1800671fd  mov     rcx, [rcx+10h]
0x180067201  call    WPP_SF_d
0x180067206  jmp     short loc_180067249
0x180067208  call    cs:__imp_GetLastError
0x18006720e  mov     ecx, eax; unsigned int
0x180067210  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180067215  mov     ebx, eax
0x180067217  mov     [rsp+0B8h+var_74], eax
0x18006721b  lea     rax, WPP_GLOBAL_Control
0x180067222  mov     rcx, cs:WPP_GLOBAL_Control
0x180067229  cmp     rcx, rax
0x18006722c  jz      short loc_180067249
0x18006722e  test    byte ptr [rcx+1Ch], 1
0x180067232  jz      short loc_180067249
0x180067234  mov     edx, 0ABh
0x180067239  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x180067240  mov     rcx, [rcx+10h]
0x180067244  call    WPP_SF_
0x180067249  jmp     short loc_180067287
0x18006724b  lea     rax, WPP_GLOBAL_Control
0x180067252  mov     rcx, cs:WPP_GLOBAL_Control
0x180067259  cmp     rcx, rax
0x18006725c  jz      short loc_180067279
0x18006725e  test    byte ptr [rcx+1Ch], 1
0x180067262  jz      short loc_180067279
0x180067264  mov     edx, 0AEh
0x180067269  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x180067270  mov     rcx, [rcx+10h]
0x180067274  call    WPP_SF_
0x180067279  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006727e  mov     ebx, 80004005h
0x180067283  mov     [rsp+0B8h+var_74], ebx
0x180067287  mov     eax, ebx
0x180067289  jmp     short loc_1800672BE
0x18006728b  lea     rax, WPP_GLOBAL_Control
0x180067292  mov     rcx, cs:WPP_GLOBAL_Control
0x180067299  cmp     rcx, rax
0x18006729c  jz      short loc_1800672B9
0x18006729e  test    byte ptr [rcx+1Ch], 1
0x1800672a2  jz      short loc_1800672B9
0x1800672a4  mov     edx, 0AAh
0x1800672a9  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x1800672b0  mov     rcx, [rcx+10h]
0x1800672b4  call    WPP_SF_
0x1800672b9  mov     eax, 80070057h
0x1800672be  add     rsp, 80h
0x1800672c5  pop     r15
0x1800672c7  pop     r14
0x1800672c9  pop     r13
0x1800672cb  pop     r12
0x1800672cd  pop     rdi
0x1800672ce  pop     rsi
0x1800672cf  pop     rbx
0x1800672d0  retn
0x1800ab182  push    rbp
0x1800ab184  sub     rsp, 40h
0x1800ab188  mov     rbp, rdx
0x1800ab18b  mov     r8, [rbp+50h]; lpMem
0x1800ab18f  xor     edx, edx; dwFlags
0x1800ab191  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800ab198  call    cs:__imp_HeapFree
0x1800ab19e  nop
0x1800ab19f  add     rsp, 40h
0x1800ab1a3  pop     rbp
0x1800ab1a4  retn
```
