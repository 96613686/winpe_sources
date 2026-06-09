# BoxDeletePath(ushort const *)

- ea: `0x140005f7c`
- end: `0x140006109`
- name: `?BoxDeletePath@@YAJPEBG@Z`
- size: `397`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400076e8`
- `0x14000bccc`
- `0x140013894`
- `0x14001ac60`

## callees

- `0x140005f7c`
- `0x1400076c8`
- `0x1400135b8`
- `0x140016bb4`
- `0x140026104`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400060de`
- `KERNEL32!HeapFree` at `0x1400060de`
- `KERNEL32!GetProcessHeap` at `0x1400060c9`
- `KERNEL32!GetProcessHeap` at `0x1400060c9`
- `KERNEL32!GetLastError` at `0x140005fea`
- `KERNEL32!GetLastError` at `0x140005fea`

## string_xrefs

- `0x140006051`: `BoxDeletePath: Error deleting path [%s]!  Error = 0x%X`
- `0x140006090`: `BoxDeletePath: Last file path: [%s]`
- `0x1400060ab`: `BoxDeletePath: No last path available.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall BoxDeletePath(const unsigned __int16 *a1)
{
  unsigned int v2; // edi
  signed int LastError; // eax
  HANDLE v4; // rcx
  HANDLE v5; // rcx

  v2 = 0;
  if ( a1 )
  {
    if ( !(unsigned int)DeletePathEx(a1) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v2 = -2147467259;
      }
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v2);
      if ( (v2 & 0x80000000) != 0 )
      {
        v4 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v4 = g_shLogFile;
        OutputMsg(v4, g_shLogEvent, L"BoxDeletePath: Error deleting path [%s]!  Error = 0x%X", a1, v2);
        v5 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v5 = g_shLogFile;
        OutputMsg(v5, g_shLogEvent, L"BoxDeletePath: No last path available.");
      }
    }
  }
  else
  {
    v2 = -2147024809;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v2);
  return v2;
}

```

## disassembly

```asm
0x140005f7c  mov     r11, rsp
0x140005f7f  push    rdi
0x140005f80  sub     rsp, 50h
0x140005f84  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x140005f8c  mov     [r11+8], rbx
0x140005f90  mov     [r11+10h], rbp
0x140005f94  mov     [r11+18h], rsi
0x140005f98  mov     rsi, rcx
0x140005f9b  xor     eax, eax
0x140005f9d  mov     [r11-20h], rax
0x140005fa1  xor     ebp, ebp
0x140005fa3  mov     [r11-18h], rbp
0x140005fa7  mov     [r11-10h], rax
0x140005fab  mov     edi, ebp
0x140005fad  test    rcx, rcx
0x140005fb0  jnz     short loc_140005FC3
0x140005fb2  mov     edi, 80070057h
0x140005fb7  mov     ecx, edi
0x140005fb9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140005fbe  jmp     loc_1400060B7
0x140005fc3  mov     [rsp+58h+var_20], rsi
0x140005fc8  mov     [rsp+58h+var_10], ebp
0x140005fcc  lea     r9, [rsp+58h+var_20]
0x140005fd1  lea     r8, BoxDeletePathCallback
0x140005fd8  mov     edx, 12h
0x140005fdd  call    DeletePathEx
0x140005fe2  test    eax, eax
0x140005fe4  jnz     loc_1400060B7
0x140005fea  call    cs:__imp_GetLastError
0x140005ff1  nop     dword ptr [rax+rax+00h]
0x140005ff6  mov     edi, eax
0x140005ff8  test    eax, eax
0x140005ffa  jnz     short loc_140006003
0x140005ffc  mov     edi, 80004005h
0x140006001  jmp     short loc_14000600E
0x140006003  jle     short loc_14000600E
0x140006005  movzx   edi, ax
0x140006008  or      edi, 80070000h
0x14000600e  mov     ecx, edi
0x140006010  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140006015  cmp     edi, 800704C7h
0x14000601b  jnz     short loc_140006027
0x14000601d  mov     eax, [rsp+58h+var_10]
0x140006021  test    eax, eax
0x140006023  jns     short loc_14000602F
0x140006025  mov     edi, eax
0x140006027  test    edi, edi
0x140006029  jns     loc_1400060B7
0x14000602f  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140006036  lea     rax, [r8-1]
0x14000603a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000603e  setnbe  al
0x140006041  mov     rcx, rbp
0x140006044  test    al, al
0x140006046  cmovz   rcx, r8; hFile
0x14000604a  mov     [rsp+58h+var_38], edi
0x14000604e  mov     r9, rsi
0x140006051  lea     r8, aBoxdeletepathE; "BoxDeletePath: Error deleting path [%s]"...
0x140006058  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14000605f  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140006064  mov     r9, [rsp+58h+var_18]
0x140006069  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140006070  mov     rcx, rbp
0x140006073  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14000607a  lea     rax, [r8-1]
0x14000607e  test    r9, r9
0x140006081  jz      short loc_14000609E
0x140006083  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140006087  setnbe  al
0x14000608a  test    al, al
0x14000608c  cmovz   rcx, r8; hFile
0x140006090  lea     r8, aBoxdeletepathL; "BoxDeletePath: Last file path: [%s]"
0x140006097  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14000609c  jmp     short loc_1400060B7
0x14000609e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400060a2  setnbe  al
0x1400060a5  test    al, al
0x1400060a7  cmovz   rcx, r8; hFile
0x1400060ab  lea     r8, aBoxdeletepathN; "BoxDeletePath: No last path available."
0x1400060b2  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x1400060b7  mov     ecx, edi
0x1400060b9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400060be  nop
0x1400060bf  mov     rbx, [rsp+58h+var_18]
0x1400060c4  test    rbx, rbx
0x1400060c7  jz      short loc_1400060F1
0x1400060c9  call    cs:__imp_GetProcessHeap
0x1400060d0  nop     dword ptr [rax+rax+00h]
0x1400060d5  mov     rcx, rax; hHeap
0x1400060d8  lea     r8, [rbx-4]; lpMem
0x1400060dc  xor     edx, edx; dwFlags
0x1400060de  call    cs:__imp_HeapFree
0x1400060e5  nop     dword ptr [rax+rax+00h]
0x1400060ea  xor     ecx, ecx
0x1400060ec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400060f1  mov     eax, edi
0x1400060f3  mov     rbx, [rsp+58h+arg_0]
0x1400060f8  mov     rbp, [rsp+58h+arg_8]
0x1400060fd  mov     rsi, [rsp+58h+arg_10]
0x140006102  add     rsp, 50h
0x140006106  pop     rdi
0x140006107  retn
```
