# I_ReaderMonitorStatusChangeWorker

- ea: `0x18001b660`
- end: `0x18001b8b2`
- name: `I_ReaderMonitorStatusChangeWorker`
- size: `594`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, LPSCARD_READERSTATEW *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x18001b660`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b863`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b72a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b7a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b72a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b7a1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b6f0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b6f0`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x18001b6dc`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x18001b6dc`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18001b6c9`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18001b6c9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001b773`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001b773`
- `WinSCard!SCardGetStatusChangeW` at `0x18001b766`
- `WinSCard!SCardGetStatusChangeW` at `0x18001b766`

## pseudocode

```c
void __fastcall I_ReaderMonitorStatusChangeWorker(
        PTP_CALLBACK_INSTANCE Instance,
        LPSCARD_READERSTATEW *Context,
        PTP_WORK Work)
{
  PVOID v5; // rcx
  LPSCARD_READERSTATEW v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rbx
  char v9; // al
  __int64 v10; // rcx
  LONG v11; // ebp
  __int64 v12; // rbx
  char LastError; // al
  PVOID v14; // rcx

  WppTraceIndent(Instance, 0);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( Context && *Context )
  {
    CallbackMayRunLong(Instance);
    v6 = *Context;
    SetEventWhenCallbackReturns(Instance, *(HANDLE *)&(*Context)[5].rgbAtr[12]);
    if ( !LODWORD(v6->szReader) || SetThreadToken(0, *(HANDLE *)&v6[3].rgbAtr[28]) )
    {
      v11 = SCardGetStatusChangeW(*(_QWORD *)&v6[3].rgbAtr[12], 0xFFFFFFFF, Context[1], *((_DWORD *)Context + 4));
      if ( LODWORD(v6->szReader) )
      {
        if ( !RevertToSelf() )
        {
          WppTraceIndent(v10, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            LastError = GetLastError();
            WPP_SF_sd(
              v12,
              221,
              (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
              WPP_pszIndent,
              LastError);
          }
        }
      }
      if ( v11 )
      {
        WppTraceIndent(v10, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            222,
            (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent,
            v11);
        }
      }
      *(_DWORD *)&v6[5].rgbAtr[32] = v11;
    }
    else
    {
      WppTraceIndent(v7, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v9 = GetLastError();
        WPP_SF_sd(v8, 220, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, v9);
      }
    }
LABEL_30:
    HeapFree(hHeap, 0, Context);
    goto LABEL_31;
  }
  WppTraceIndent(v5, 2);
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( Context )
    goto LABEL_30;
LABEL_31:
  WppTraceIndent(v14, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
}

```

## disassembly

```asm
0x18001b660  push    rbx
0x18001b662  push    rbp
0x18001b663  push    rsi
0x18001b664  push    rdi
0x18001b665  push    r13
0x18001b667  sub     rsp, 30h
0x18001b66b  mov     rdi, rdx
0x18001b66e  mov     rbx, rcx
0x18001b671  xor     edx, edx
0x18001b673  call    WppTraceIndent
0x18001b678  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b67f  lea     r13, WPP_GLOBAL_Control
0x18001b686  cmp     rcx, r13
0x18001b689  jz      short loc_18001B6B3
0x18001b68b  test    byte ptr [rcx+1Ch], 2
0x18001b68f  jz      short loc_18001B6B3
0x18001b691  cmp     byte ptr [rcx+19h], 5
0x18001b695  jb      short loc_18001B6B3
0x18001b697  mov     r9, cs:WPP_pszIndent
0x18001b69e  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b6a5  mov     rcx, [rcx+10h]
0x18001b6a9  mov     edx, 0DAh
0x18001b6ae  call    WPP_SF_s
0x18001b6b3  test    rdi, rdi
0x18001b6b6  jz      loc_18001B814
0x18001b6bc  cmp     qword ptr [rdi], 0
0x18001b6c0  jz      loc_18001B814
0x18001b6c6  mov     rcx, rbx; pci
0x18001b6c9  call    cs:__imp_CallbackMayRunLong
0x18001b6cf  mov     rsi, [rdi]
0x18001b6d2  mov     rcx, rbx; pci
0x18001b6d5  mov     rdx, [rsi+168h]; evt
0x18001b6dc  call    cs:__imp_SetEventWhenCallbackReturns
0x18001b6e2  cmp     dword ptr [rsi], 0
0x18001b6e5  jz      short loc_18001B754
0x18001b6e7  mov     rdx, [rsi+0F8h]; Token
0x18001b6ee  xor     ecx, ecx; Thread
0x18001b6f0  call    cs:__imp_SetThreadToken
0x18001b6f6  test    eax, eax
0x18001b6f8  jnz     short loc_18001B754
0x18001b6fa  lea     edx, [rax+2]
0x18001b6fd  call    WppTraceIndent
0x18001b702  mov     rbx, cs:WPP_GLOBAL_Control
0x18001b709  cmp     rbx, r13
0x18001b70c  jz      loc_18001B857
0x18001b712  test    byte ptr [rbx+1Ch], 1
0x18001b716  jz      loc_18001B857
0x18001b71c  cmp     byte ptr [rbx+19h], 3
0x18001b720  jb      loc_18001B857
0x18001b726  mov     rbx, [rbx+10h]
0x18001b72a  call    cs:__imp_GetLastError
0x18001b730  mov     r9, cs:WPP_pszIndent
0x18001b737  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b73e  mov     edx, 0DCh
0x18001b743  mov     [rsp+58h+var_38], eax
0x18001b747  mov     rcx, rbx
0x18001b74a  call    WPP_SF_sd
0x18001b74f  jmp     loc_18001B857
0x18001b754  mov     r9d, [rdi+10h]; cReaders
0x18001b758  or      edx, 0FFFFFFFFh; dwTimeout
0x18001b75b  mov     r8, [rdi+8]; rgReaderStates
0x18001b75f  mov     rcx, [rsi+0E8h]; hContext
0x18001b766  call    cs:__imp_SCardGetStatusChangeW
0x18001b76c  cmp     dword ptr [rsi], 0
0x18001b76f  mov     ebp, eax
0x18001b771  jz      short loc_18001B7C6
0x18001b773  call    cs:__imp_RevertToSelf
0x18001b779  test    eax, eax
0x18001b77b  jnz     short loc_18001B7C6
0x18001b77d  lea     edx, [rax+2]
0x18001b780  call    WppTraceIndent
0x18001b785  mov     rbx, cs:WPP_GLOBAL_Control
0x18001b78c  cmp     rbx, r13
0x18001b78f  jz      short loc_18001B7C6
0x18001b791  test    byte ptr [rbx+1Ch], 1
0x18001b795  jz      short loc_18001B7C6
0x18001b797  cmp     byte ptr [rbx+19h], 3
0x18001b79b  jb      short loc_18001B7C6
0x18001b79d  mov     rbx, [rbx+10h]
0x18001b7a1  call    cs:__imp_GetLastError
0x18001b7a7  mov     r9, cs:WPP_pszIndent
0x18001b7ae  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b7b5  mov     edx, 0DDh
0x18001b7ba  mov     [rsp+58h+var_38], eax
0x18001b7be  mov     rcx, rbx
0x18001b7c1  call    WPP_SF_sd
0x18001b7c6  test    ebp, ebp
0x18001b7c8  jz      short loc_18001B80C
0x18001b7ca  mov     edx, 2
0x18001b7cf  call    WppTraceIndent
0x18001b7d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7db  cmp     rcx, r13
0x18001b7de  jz      short loc_18001B80C
0x18001b7e0  test    byte ptr [rcx+1Ch], 1
0x18001b7e4  jz      short loc_18001B80C
0x18001b7e6  cmp     byte ptr [rcx+19h], 3
0x18001b7ea  jb      short loc_18001B80C
0x18001b7ec  mov     r9, cs:WPP_pszIndent
0x18001b7f3  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b7fa  mov     rcx, [rcx+10h]
0x18001b7fe  mov     edx, 0DEh
0x18001b803  mov     [rsp+58h+var_38], ebp
0x18001b807  call    WPP_SF_sd
0x18001b80c  mov     [rsi+17Ch], ebp
0x18001b812  jmp     short loc_18001B857
0x18001b814  mov     edx, 2
0x18001b819  call    WppTraceIndent
0x18001b81e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b825  cmp     rcx, r13
0x18001b828  jz      short loc_18001B852
0x18001b82a  test    byte ptr [rcx+1Ch], 1
0x18001b82e  jz      short loc_18001B852
0x18001b830  cmp     byte ptr [rcx+19h], 3
0x18001b834  jb      short loc_18001B852
0x18001b836  mov     r9, cs:WPP_pszIndent
0x18001b83d  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b844  mov     rcx, [rcx+10h]
0x18001b848  mov     edx, 0DBh
0x18001b84d  call    WPP_SF_s
0x18001b852  test    rdi, rdi
0x18001b855  jz      short loc_18001B869
0x18001b857  mov     rcx, cs:hHeap; hHeap
0x18001b85e  mov     r8, rdi; lpMem
0x18001b861  xor     edx, edx; dwFlags
0x18001b863  call    cs:__imp_HeapFree
0x18001b869  mov     edx, 1
0x18001b86e  call    WppTraceIndent
0x18001b873  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b87a  cmp     rcx, r13
0x18001b87d  jz      short loc_18001B8A7
0x18001b87f  test    byte ptr [rcx+1Ch], 2
0x18001b883  jz      short loc_18001B8A7
0x18001b885  cmp     byte ptr [rcx+19h], 5
0x18001b889  jb      short loc_18001B8A7
0x18001b88b  mov     r9, cs:WPP_pszIndent
0x18001b892  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b899  mov     rcx, [rcx+10h]
0x18001b89d  mov     edx, 0DFh
0x18001b8a2  call    WPP_SF_s
0x18001b8a7  add     rsp, 30h
0x18001b8ab  pop     r13
0x18001b8ad  pop     rdi
0x18001b8ae  pop     rsi
0x18001b8af  pop     rbp
0x18001b8b0  pop     rbx
0x18001b8b1  retn
```
