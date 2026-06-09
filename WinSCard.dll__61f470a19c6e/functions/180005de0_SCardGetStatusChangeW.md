# SCardGetStatusChangeW

- ea: `0x180005de0`
- end: `0x180006054`
- name: `SCardGetStatusChangeW`
- size: `628`
- prototype: `LONG __stdcall(SCARDCONTEXT hContext, DWORD dwTimeout, LPSCARD_READERSTATEW rgReaderStates, DWORD cReaders)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180002e84`
- `0x180024b4c`
- `0x180026fb0`

## callees

- `0x1800040d0`
- `0x1800051b0`
- `0x180005de0`
- `0x180006400`
- `0x180007bc0`
- `0x1800108f0`
- `0x18001991c`
- `0x18001b9b8`
- `0x1800239b8`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005e39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005e39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005eb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005eb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LONG __stdcall SCardGetStatusChangeW(
        SCARDCONTEXT hContext,
        DWORD dwTimeout,
        LPSCARD_READERSTATEW rgReaderStates,
        DWORD cReaders)
{
  LONG v7; // r14d
  CHandleList *v8; // rdi
  struct _RTL_CRITICAL_SECTION *v9; // r15
  SCARDCONTEXT v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rsi
  struct _REDIRECTION_CONTEXT *v13; // rbx
  __int64 *v14; // rcx
  unsigned __int16 *v15; // rdi
  DWORD i; // ebx
  const unsigned __int16 *v17; // rdx
  __int64 v18; // rcx
  int v19; // r9d
  ulong v21; // [rsp+30h] [rbp-68h]
  ulong v22; // [rsp+38h] [rbp-60h] BYREF
  ulong pExceptionObject; // [rsp+3Ch] [rbp-5Ch] BYREF
  const int *v24; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-50h]
  int v26; // [rsp+50h] [rbp-48h]
  int v27; // [rsp+54h] [rbp-44h]
  struct _REDIRECTION_CONTEXT *v28; // [rsp+58h] [rbp-40h]
  ulong v29; // [rsp+60h] [rbp-38h] BYREF
  char *v30; // [rsp+68h] [rbp-30h]

  v7 = 0;
  v28 = 0;
  WppTraceIndent(hContext, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_29cff01745ae393421dd9a83e7cfc696_Traceguids);
  }
  try
  {
    v8 = g_phlContexts;
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)g_phlContexts + 32);
    v30 = (char *)g_phlContexts + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_phlContexts + 32));
    if ( HIBYTE(hContext) != *((_BYTE *)v8 + 8)
      || *((_DWORD *)v8 + 4) <= (hContext & 0x7FFFFFFF)
      || (v10 = 16 * (hContext & 0x7FFFFFFF),
          v11 = *((_QWORD *)v8 + 3),
          ((*(_DWORD *)(v10 + v11 + 8) ^ HIDWORD(hContext)) & 0xFFFFFF) != 0) )
    {
      pExceptionObject = 6;
      throw &pExceptionObject;
    }
    v12 = *(_QWORD *)(v10 + v11);
    LeaveCriticalSection(v9);
    if ( *(_DWORD *)(v12 + 16) )
    {
      v22 = -2146435042;
      throw &v22;
    }
    v13 = *(struct _REDIRECTION_CONTEXT **)(v12 + 136);
    v28 = v13;
    v14 = *(__int64 **)(v12 + 128);
    if ( v14 )
    {
      v7 = RedirectedSCardGetStatusChangeW(v14, dwTimeout, rgReaderStates, cReaders);
      if ( v7 == -2146435054 )
        SetStartedEventWhenSCardSubsytemIsStarted(v13);
    }
    else
    {
      v24 = &CBuffer::`vftable';
      v15 = 0;
      v25 = 0;
      v26 = 0;
      v27 = 0;
      for ( i = 0; i < cReaders; ++i )
      {
        MStrAdd((struct CBuffer *)&v24, rgReaderStates[(unsigned __int64)i].szReader);
        v15 = v25;
      }
      v17 = &WideCharStr;
      if ( v27 )
        v17 = v15;
      CSCardUserContext::GetStatusChange((CSCardUserContext *)v12, v17, rgReaderStates, cReaders, dwTimeout);
      v24 = &CBuffer::`vftable';
      if ( v15 )
        operator delete(v15);
      v25 = 0;
      v26 = 0;
      v27 = 0;
    }
  }
  catch ( ulong v29 )
  {
    v21 = v29;
    if ( v29 == -2146435054 )
    {
      v18 = (__int64)v28;
      if ( v28 )
        ResetEvent(*((HANDLE *)v28 + 16));
    }
    v7 = v21;
  }
  catch ( ... )
  {
    v7 = -2146435068;
  }
  WppTraceIndent(v18, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_29cff01745ae393421dd9a83e7cfc696_Traceguids,
      v19,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x180005de0  mov     [rsp+arg_0], rbx
0x180005de5  mov     [rsp+arg_10], rsi
0x180005dea  mov     [rsp+arg_8], edx
0x180005dee  push    rdi
0x180005def  push    r12
0x180005df1  push    r13
0x180005df3  push    r14
0x180005df5  push    r15
0x180005df7  sub     rsp, 70h
0x180005dfb  mov     r12d, r9d
0x180005dfe  mov     r13, r8
0x180005e01  mov     rbx, rcx
0x180005e04  xor     r14d, r14d
0x180005e07  mov     [rsp+98h+var_40], r14
0x180005e0c  xor     edx, edx
0x180005e0e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180005e13  lea     rax, WPP_GLOBAL_Control
0x180005e1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e21  cmp     rcx, rax
0x180005e24  jnz     short loc_180005E8B
0x180005e26  mov     rdi, cs:?g_phlContexts@@3PEAVCHandleList@@EA; CHandleList * g_phlContexts
0x180005e2d  lea     r15, [rdi+20h]
0x180005e31  mov     [rsp+98h+var_30], r15
0x180005e36  mov     rcx, r15; lpCriticalSection
0x180005e39  call    cs:__imp_EnterCriticalSection
0x180005e3f  nop
0x180005e40  mov     rax, rbx
0x180005e43  shr     rax, 38h
0x180005e47  cmp     al, [rdi+8]
0x180005e4a  jnz     short loc_180005E71
0x180005e4c  mov     eax, ebx
0x180005e4e  btr     eax, 1Fh
0x180005e52  cmp     [rdi+10h], eax
0x180005e55  jbe     short loc_180005E71
0x180005e57  mov     edx, eax
0x180005e59  shl     rdx, 4
0x180005e5d  mov     rax, [rdi+18h]
0x180005e61  shr     rbx, 20h
0x180005e65  xor     ebx, [rdx+rax+8]
0x180005e69  test    ebx, 0FFFFFFh
0x180005e6f  jz      short loc_180005EB1
0x180005e71  mov     [rsp+98h+pExceptionObject], 6
0x180005e79  lea     rdx, _TI1K; pThrowInfo
0x180005e80  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180005e85  call    _CxxThrowException_0
0x180005e8b  test    byte ptr [rcx+1Ch], 2
0x180005e8f  jz      short loc_180005E26
0x180005e91  cmp     byte ptr [rcx+19h], 5
0x180005e95  jb      short loc_180005E26
0x180005e97  mov     edx, 0Ah
0x180005e9c  lea     r8, WPP_29cff01745ae393421dd9a83e7cfc696_Traceguids
0x180005ea3  mov     rcx, [rcx+10h]
0x180005ea7  call    WPP_SF_s
0x180005eac  jmp     loc_180005E26
0x180005eb1  mov     rsi, [rdx+rax]
0x180005eb5  mov     rcx, r15; lpCriticalSection
0x180005eb8  call    cs:__imp_LeaveCriticalSection
0x180005ebe  cmp     dword ptr [rsi+10h], 0
0x180005ec2  jnz     loc_180006005
0x180005ec8  mov     rbx, [rsi+88h]
0x180005ecf  mov     [rsp+98h+var_40], rbx
0x180005ed4  mov     rcx, [rsi+80h]; unsigned __int64
0x180005edb  test    rcx, rcx
0x180005ede  jnz     loc_180005FD4
0x180005ee4  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180005eeb  mov     [rsp+98h+var_58], rax
0x180005ef0  xor     r15d, r15d
0x180005ef3  mov     edi, r15d
0x180005ef6  mov     [rsp+98h+var_50], r15
0x180005efb  mov     [rsp+98h+var_48], r15d
0x180005f00  mov     [rsp+98h+var_44], r15d
0x180005f05  mov     [rsp+98h+var_64], r15d
0x180005f0a  mov     ebx, r15d
0x180005f0d  mov     [rsp+98h+var_64], ebx
0x180005f11  cmp     ebx, r12d
0x180005f14  jb      loc_180005FB0
0x180005f1a  lea     rdx, WideCharStr
0x180005f21  cmp     [rsp+98h+var_44], 0
0x180005f26  cmova   rdx, rdi; unsigned __int16 *
0x180005f2a  mov     eax, [rsp+98h+arg_8]
0x180005f31  mov     [rsp+98h+var_78], eax; unsigned int
0x180005f35  mov     r9d, r12d; unsigned int
0x180005f38  mov     r8, r13; struct SCARD_READERSTATEW *
0x180005f3b  mov     rcx, rsi; this
0x180005f3e  call    ?GetStatusChange@CSCardUserContext@@QEAAXPEBGPEAUSCARD_READERSTATEW@@KK@Z; CSCardUserContext::GetStatusChange(ushort const *,SCARD_READERSTATEW *,ulong,ulong)
0x180005f43  nop
0x180005f44  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180005f4b  mov     [rsp+98h+var_58], rax
0x180005f50  test    rdi, rdi
0x180005f53  jz      short loc_180005F5D
0x180005f55  mov     rcx, rdi; void *
0x180005f58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005f5d  mov     [rsp+98h+var_50], r15
0x180005f62  mov     [rsp+98h+var_48], r15d
0x180005f67  mov     [rsp+98h+var_44], r15d
0x180005f6c  lea     rbx, WPP_GLOBAL_Control
0x180005f73  mov     edx, 1
0x180005f78  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180005f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f84  cmp     rcx, rbx
0x180005f87  jz      short loc_180005F93
0x180005f89  test    byte ptr [rcx+1Ch], 2
0x180005f8d  jnz     loc_18000602B
0x180005f93  mov     eax, r14d
0x180005f96  lea     r11, [rsp+98h+var_28]
0x180005f9b  mov     rbx, [r11+30h]
0x180005f9f  mov     rsi, [r11+40h]
0x180005fa3  mov     rsp, r11
0x180005fa6  pop     r15
0x180005fa8  pop     r14
0x180005faa  pop     r13
0x180005fac  pop     r12
0x180005fae  pop     rdi
0x180005faf  retn
0x180005fb0  mov     edx, ebx
0x180005fb2  shl     rdx, 6
0x180005fb6  mov     rdx, [rdx+r13]; unsigned __int16 *
0x180005fba  lea     rcx, [rsp+98h+var_58]; struct CBuffer *
0x180005fbf  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x180005fc4  inc     ebx
0x180005fc6  mov     [rsp+98h+var_64], ebx
0x180005fca  mov     rdi, [rsp+98h+var_50]
0x180005fcf  jmp     loc_180005F11
0x180005fd4  mov     r9d, r12d; unsigned int
0x180005fd7  mov     r8, r13; struct SCARD_READERSTATEW *
0x180005fda  mov     edx, [rsp+98h+arg_8]; unsigned int
0x180005fe1  call    ?RedirectedSCardGetStatusChangeW@@YAJ_KKPEAUSCARD_READERSTATEW@@K@Z; RedirectedSCardGetStatusChangeW(unsigned __int64,ulong,SCARD_READERSTATEW *,ulong)
0x180005fe6  mov     r14d, eax
0x180005fe9  mov     [rsp+98h+var_68], eax
0x180005fed  cmp     eax, 80100012h
0x180005ff2  jnz     loc_180005F6C
0x180005ff8  mov     rcx, rbx; struct _REDIRECTION_CONTEXT *
0x180005ffb  call    ?SetStartedEventWhenSCardSubsytemIsStarted@@YAHPEAU_REDIRECTION_CONTEXT@@@Z; SetStartedEventWhenSCardSubsytemIsStarted(_REDIRECTION_CONTEXT *)
0x180006000  jmp     loc_180005F6C
0x180006005  mov     [rsp+98h+var_60], 8010001Eh
0x18000600d  lea     rdx, _TI1K; pThrowInfo
0x180006014  lea     rcx, [rsp+98h+var_60]; pExceptionObject
0x180006019  call    _CxxThrowException_0
0x18000601f  jmp     short $+2
0x180006021  mov     r14d, [rsp+98h+var_68]
0x180006026  jmp     loc_180005F6C
0x18000602b  cmp     byte ptr [rcx+19h], 5
0x18000602f  jb      loc_180005F93
0x180006035  mov     edx, 0Bh
0x18000603a  mov     [rsp+98h+var_78], r14d
0x18000603f  lea     r8, WPP_29cff01745ae393421dd9a83e7cfc696_Traceguids
0x180006046  mov     rcx, [rcx+10h]
0x18000604a  call    WPP_SF_sd
0x18000604f  jmp     loc_180005F93
```
