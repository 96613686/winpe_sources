# CDlpLogT<CEmptyType>::DlpLogString(WINDLP_LOGLEVEL,ushort const *)

- ea: `0x140034bf4`
- end: `0x140034d7e`
- name: `?DlpLogString@?$CDlpLogT@VCEmptyType@@@@SAJW4WINDLP_LOGLEVEL@@PEBG@Z`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140034ab4`

## callees

- `0x1400076c8`
- `0x14000e494`
- `0x1400135b8`
- `0x14001d4ac`
- `0x140034bf4`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140034c1b`
- `KERNEL32!IsDebuggerPresent` at `0x140034c1b`
- `KERNEL32!HeapFree` at `0x140034d2c`
- `KERNEL32!HeapFree` at `0x140034d5a`
- `KERNEL32!HeapFree` at `0x140034d2c`
- `KERNEL32!HeapFree` at `0x140034d5a`
- `KERNEL32!GetProcessHeap` at `0x140034d17`
- `KERNEL32!GetProcessHeap` at `0x140034d45`
- `KERNEL32!GetProcessHeap` at `0x140034d17`
- `KERNEL32!GetProcessHeap` at `0x140034d45`
- `KERNEL32!OutputDebugStringW` at `0x140034cfe`
- `KERNEL32!OutputDebugStringW` at `0x140034cfe`
- `KERNEL32!GetCurrentThreadId` at `0x140034c8b`
- `KERNEL32!GetCurrentThreadId` at `0x140034ccc`
- `KERNEL32!GetCurrentThreadId` at `0x140034c8b`
- `KERNEL32!GetCurrentThreadId` at `0x140034ccc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpLogT<CEmptyType>::DlpLogString(int a1, __int64 a2)
{
  unsigned __int16 *v4; // rbp
  LPCWSTR v5; // rdi
  unsigned int v6; // esi
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  const wchar_t *v10; // rbx
  int v11; // eax
  DWORD v12; // eax
  int v13; // eax
  DWORD CurrentThreadId; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  LPCWSTR lpOutputString; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int16 *v19; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  v19 = 0;
  v5 = 0;
  lpOutputString = 0;
  if ( IsDebuggerPresent() )
  {
    v7 = a1 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          if ( v9 == 1 )
            v10 = L"ERROR";
          else
            v10 = L"UNKNOWN";
        }
        else
        {
          v10 = L"WARNING";
        }
      }
      else
      {
        v10 = L"INFO";
      }
    }
    else
    {
      v10 = L"DEBUG";
    }
    v11 = CDlpHelpersT<CEmptyType>::FormatSystemTime(&v19);
    v4 = v19;
    if ( v11 < 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = STRAPI_Format(
              (unsigned __int16 **)&lpOutputString,
              L"DLPLOG: [0x%X] [%s] [%s]\n\r",
              CurrentThreadId,
              v10,
              a2);
    }
    else
    {
      v12 = GetCurrentThreadId();
      v13 = STRAPI_Format(
              (unsigned __int16 **)&lpOutputString,
              L"%s, DLPLOG: [0x%X] [%s] [%s]\n\r",
              v4,
              v12,
              v10,
              a2,
              -2);
    }
    v6 = v13;
    if ( v13 >= 0 )
    {
      v5 = lpOutputString;
      OutputDebugStringW(lpOutputString);
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
      v5 = lpOutputString;
    }
  }
  else
  {
    v6 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(0);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v4 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v6;
}

```

## disassembly

```asm
0x140034bf4  mov     rax, rsp
0x140034bf7  push    rbp
0x140034bf8  push    rsi
0x140034bf9  push    rdi
0x140034bfa  sub     rsp, 40h
0x140034bfe  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x140034c06  mov     [rax+8], rbx
0x140034c0a  mov     rsi, rdx
0x140034c0d  mov     ebx, ecx
0x140034c0f  xor     ebp, ebp
0x140034c11  mov     [rax+20h], rbp
0x140034c15  xor     edi, edi
0x140034c17  mov     [rax+18h], rdi
0x140034c1b  call    cs:__imp_IsDebuggerPresent
0x140034c22  nop     dword ptr [rax+rax+00h]
0x140034c27  test    eax, eax
0x140034c29  jnz     short loc_140034C39
0x140034c2b  xor     esi, esi
0x140034c2d  xor     ecx, ecx
0x140034c2f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140034c34  jmp     loc_140034D0A
0x140034c39  sub     ebx, 1
0x140034c3c  jz      short loc_140034C71
0x140034c3e  sub     ebx, 1
0x140034c41  jz      short loc_140034C68
0x140034c43  sub     ebx, 1
0x140034c46  jz      short loc_140034C5F
0x140034c48  cmp     ebx, 1
0x140034c4b  jz      short loc_140034C56
0x140034c4d  lea     rbx, aUnknown; "UNKNOWN"
0x140034c54  jmp     short loc_140034C78
0x140034c56  lea     rbx, aError_0; "ERROR"
0x140034c5d  jmp     short loc_140034C78
0x140034c5f  lea     rbx, aWarning; "WARNING"
0x140034c66  jmp     short loc_140034C78
0x140034c68  lea     rbx, aInfo_0; "INFO"
0x140034c6f  jmp     short loc_140034C78
0x140034c71  lea     rbx, aDebug; "DEBUG"
0x140034c78  lea     rcx, [rsp+58h+arg_18]; unsigned __int16 **
0x140034c7d  call    ?FormatSystemTime@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CDlpHelpersT<CEmptyType>::FormatSystemTime(ushort * *)
0x140034c82  mov     rbp, [rsp+58h+arg_18]
0x140034c87  test    eax, eax
0x140034c89  js      short loc_140034CCC
0x140034c8b  call    cs:__imp_GetCurrentThreadId
0x140034c92  nop     dword ptr [rax+rax+00h]
0x140034c97  mov     [rsp+58h+var_30], rsi
0x140034c9c  mov     [rsp+58h+var_38], rbx
0x140034ca1  mov     r9d, eax
0x140034ca4  mov     r8, rbp
0x140034ca7  lea     rdx, aSDlplog0xXSS; "%s, DLPLOG: [0x%X] [%s] [%s]\n\r"
0x140034cae  lea     rcx, [rsp+58h+lpOutputString]; unsigned __int16 **
0x140034cb3  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x140034cb8  mov     esi, eax
0x140034cba  test    eax, eax
0x140034cbc  jns     short loc_140034CF6
0x140034cbe  mov     ecx, eax
0x140034cc0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140034cc5  mov     rdi, [rsp+58h+lpOutputString]
0x140034cca  jmp     short loc_140034D0A
0x140034ccc  call    cs:__imp_GetCurrentThreadId
0x140034cd3  nop     dword ptr [rax+rax+00h]
0x140034cd8  mov     [rsp+58h+var_38], rsi
0x140034cdd  mov     r9, rbx
0x140034ce0  mov     r8d, eax
0x140034ce3  lea     rdx, aDlplog0xXSS; "DLPLOG: [0x%X] [%s] [%s]\n\r"
0x140034cea  lea     rcx, [rsp+58h+lpOutputString]; unsigned __int16 **
0x140034cef  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x140034cf4  jmp     short loc_140034CB8
0x140034cf6  mov     rdi, [rsp+58h+lpOutputString]
0x140034cfb  mov     rcx, rdi; lpOutputString
0x140034cfe  call    cs:__imp_OutputDebugStringW
0x140034d05  nop     dword ptr [rax+rax+00h]
0x140034d0a  mov     ecx, esi
0x140034d0c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140034d11  nop
0x140034d12  test    rdi, rdi
0x140034d15  jz      short loc_140034D40
0x140034d17  call    cs:__imp_GetProcessHeap
0x140034d1e  nop     dword ptr [rax+rax+00h]
0x140034d23  mov     rcx, rax; hHeap
0x140034d26  lea     r8, [rdi-4]; lpMem
0x140034d2a  xor     edx, edx; dwFlags
0x140034d2c  call    cs:__imp_HeapFree
0x140034d33  nop     dword ptr [rax+rax+00h]
0x140034d38  xor     ecx, ecx
0x140034d3a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140034d3f  nop
0x140034d40  test    rbp, rbp
0x140034d43  jz      short loc_140034D6E
0x140034d45  call    cs:__imp_GetProcessHeap
0x140034d4c  nop     dword ptr [rax+rax+00h]
0x140034d51  mov     rcx, rax; hHeap
0x140034d54  lea     r8, [rbp-4]; lpMem
0x140034d58  xor     edx, edx; dwFlags
0x140034d5a  call    cs:__imp_HeapFree
0x140034d61  nop     dword ptr [rax+rax+00h]
0x140034d66  xor     ecx, ecx
0x140034d68  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140034d6d  nop
0x140034d6e  mov     eax, esi
0x140034d70  mov     rbx, [rsp+58h+arg_0]
0x140034d75  add     rsp, 40h
0x140034d79  pop     rdi
0x140034d7a  pop     rsi
0x140034d7b  pop     rbp
0x140034d7c  retn
```
