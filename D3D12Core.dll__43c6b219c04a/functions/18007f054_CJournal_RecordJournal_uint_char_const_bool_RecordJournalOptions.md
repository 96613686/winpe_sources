# CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)

- ea: `0x18007f054`
- end: `0x18007f23a`
- name: `?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z`
- size: `486`
- prototype: ``
- caller_count: `167`
- callee_count: `5`
- tags: ``

## callers

- `0x180003810`
- `0x1800041e8`
- `0x180004240`
- `0x180004460`
- `0x1800046f0`
- `0x180004a38`
- `0x180004c38`
- `0x1800059a0`
- `0x180005d54`
- `0x180005f0c`
- `0x180005f5c`
- `0x180006390`
- `0x1800064a4`
- `0x180006508`
- `0x1800066a0`
- `0x180006944`
- `0x1800070d0`
- `0x180007314`
- `0x1800074c4`
- `0x1800077e0`
- `0x1800078c0`
- `0x180007910`
- `0x1800079f0`
- `0x180007d84`
- `0x1800082e0`
- `0x180008330`
- `0x180008380`
- `0x180008400`
- `0x180008464`
- `0x1800084b4`
- `0x1800295a0`
- `0x18002ef50`
- `0x180048770`
- `0x1800487c0`
- `0x180049e40`
- `0x18004a070`
- `0x180050b94`
- `0x1800529b4`
- `0x180052a3c`
- `0x180053830`
- `0x180053aa4`
- `0x180055294`
- `0x180056e30`
- `0x1800584fc`
- `0x18005c5d0`
- `0x18005df74`
- `0x18005eeb4`
- `0x18005fc0c`
- `0x18006028c`
- `0x180062b24`

## callees

- `0x18007f054`
- `0x1800bb480`
- `0x1800bc094`
- `0x18017a608`
- `0x18017a694`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f0a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f174`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f1f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f0a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f174`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007f1f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007f0b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007f16c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007f0b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007f16c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18007f17a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18007f136`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18007f136`

## pseudocode

```c
USHORT __fastcall CJournal::RecordJournal(__int64 a1, int a2, __int64 a3, __int64 a4, char a5)
{
  __int64 v7; // r12
  __int64 v8; // rdi
  _BYTE *v9; // r8
  __int64 v10; // rdx
  struct SJournalEntry near **v11; // rcx
  __int64 v12; // rax
  struct SJournalEntry near **v13; // rax
  USHORT result; // ax
  unsigned int v15; // ebp
  struct SJournalEntry *v16; // rsi
  DWORD TickCount; // ebx
  DWORD CurrentThreadId; // eax
  unsigned __int64 v19; // r10
  unsigned __int64 v20; // r11
  __int64 v21; // rcx
  __int64 v22; // rdx
  struct SJournalEntry *v23; // r8
  struct SJournalEntry *v24; // r9
  char v25; // al
  int v26; // edx
  int v27; // ecx
  PVOID BackTrace[50]; // [rsp+30h] [rbp-1C8h] BYREF

  v7 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&JournalCounter, 0xFFFFFFFF) - 1) & 0x3F;
  v8 = 120 * v7;
  *((_DWORD *)&Journal + 30 * v7) = a2;
  *(_DWORD *)((char *)&Journal + v8 + 4) = GetCurrentThreadId();
  *(_DWORD *)((char *)&Journal + v8 + 8) = GetTickCount();
  *(_OWORD *)((char *)&Journal + v8 + 16) = 0;
  *(struct SJournalEntry near **)((char *)&Journal + v8 + 32) = 0;
  v9 = (_BYTE *)a3;
  *(struct SJournalEntry near **)((char *)&Journal + v8 + 40) = 0;
  v10 = 64;
  *(struct SJournalEntry near **)((char *)&Journal + v8 + 48) = 0;
  v11 = &Journal + 15 * v7 + 7;
  v12 = 2147483646;
  do
  {
    if ( !v12 )
      break;
    if ( !*v9 )
      break;
    *(_BYTE *)v11 = *v9++;
    v11 = (struct SJournalEntry near **)((char *)v11 + 1);
    --v12;
    --v10;
  }
  while ( v10 );
  v13 = (struct SJournalEntry near **)((char *)v11 - 1);
  if ( v10 )
    v13 = v11;
  *(_BYTE *)v13 = 0;
  memset_0(BackTrace, 0, sizeof(BackTrace));
  result = RtlCaptureStackBackTrace(1u, 0x32u, BackTrace, 0);
  v15 = result;
  if ( result >= 3u )
  {
    v16 = (struct SJournalEntry *)BackTrace[0];
    *(struct SJournalEntry near **)((char *)&Journal + v8 + 24) = (struct SJournalEntry near *)BackTrace[1];
    *(struct SJournalEntry near **)((char *)&Journal + v8 + 32) = (struct SJournalEntry near *)BackTrace[2];
    *(struct SJournalEntry near **)((char *)&Journal + v8 + 16) = v16;
    if ( (a5 & 1) != 0 )
    {
      TickCount = GetTickCount();
      CurrentThreadId = GetCurrentThreadId();
      result = D3DOutputMessage((_DWORD)OutputDebugStringA, a2, CurrentThreadId, TickCount, (__int64)v16, a3);
    }
  }
  v19 = qword_18033B158;
  v20 = g_Journal;
  v21 = 0;
  do
  {
    v22 = (unsigned int)(v21 + 1);
    if ( (unsigned int)v22 >= v15 )
      break;
    v23 = (struct SJournalEntry *)BackTrace[v21];
    if ( (unsigned __int64)v23 <= v19 && (unsigned __int64)v23 >= v20 )
    {
      v24 = (struct SJournalEntry *)BackTrace[v22];
      if ( (unsigned __int64)v24 < v20 || (unsigned __int64)v24 > v19 )
      {
        *(struct SJournalEntry near **)((char *)&Journal + v8 + 40) = v23;
        LODWORD(v21) = v21 + 1;
        *(struct SJournalEntry near **)((char *)&Journal + v8 + 48) = v24;
      }
    }
    v21 = (unsigned int)(v21 + 1);
    result = v21 + 1;
  }
  while ( (unsigned int)(v21 + 1) < 0x32 );
  if ( (byte_180333481 & 2) != 0 )
  {
    v25 = GetCurrentThreadId();
    return McTemplateU0qdqs_EventWriteTransfer(v27, v26, v7, a2, v25, a3);
  }
  return result;
}

```

## disassembly

```asm
0x18007f054  mov     [rsp+arg_0], rbx
0x18007f059  mov     [rsp+arg_18], rbp
0x18007f05e  push    rsi
0x18007f05f  push    rdi
0x18007f060  push    r12
0x18007f062  push    r14
0x18007f064  push    r15
0x18007f066  sub     rsp, 1D0h
0x18007f06d  mov     rax, cs:__security_cookie
0x18007f074  xor     rax, rsp
0x18007f077  mov     [rsp+1F8h+var_38], rax
0x18007f07f  mov     r15, r8
0x18007f082  mov     r14d, edx
0x18007f085  or      r12d, 0FFFFFFFFh
0x18007f089  lock xadd cs:?JournalCounter@@3IC, r12d; uint volatile JournalCounter
0x18007f092  dec     r12d
0x18007f095  lea     rbx, ?Journal@@3PAUSJournalEntry@@A; SJournalEntry near * Journal
0x18007f09c  and     r12d, 3Fh
0x18007f0a0  imul    rdi, r12, 78h ; 'x'
0x18007f0a4  mov     [rdi+rbx], edx
0x18007f0a7  call    cs:__imp_GetCurrentThreadId
0x18007f0ad  mov     [rdi+rbx+4], eax
0x18007f0b1  call    cs:__imp_GetTickCount
0x18007f0b7  mov     [rdi+rbx+8], eax
0x18007f0bb  xorps   xmm0, xmm0
0x18007f0be  xor     eax, eax
0x18007f0c0  lea     rcx, [rbx+38h]
0x18007f0c4  movups  xmmword ptr [rdi+rbx+10h], xmm0
0x18007f0c9  mov     [rdi+rbx+20h], rax
0x18007f0ce  mov     r8, r15
0x18007f0d1  mov     [rdi+rbx+28h], rax
0x18007f0d6  mov     edx, 40h ; '@'
0x18007f0db  mov     [rdi+rbx+30h], rax
0x18007f0e0  add     rcx, rdi
0x18007f0e3  mov     eax, 7FFFFFFEh
0x18007f0e8  test    rax, rax
0x18007f0eb  jz      short loc_18007F107
0x18007f0ed  mov     r9b, [r8]
0x18007f0f0  test    r9b, r9b
0x18007f0f3  jz      short loc_18007F107
0x18007f0f5  mov     [rcx], r9b
0x18007f0f8  inc     r8
0x18007f0fb  inc     rcx
0x18007f0fe  dec     rax
0x18007f101  sub     rdx, 1
0x18007f105  jnz     short loc_18007F0E8
0x18007f107  test    rdx, rdx
0x18007f10a  lea     rax, [rcx-1]
0x18007f10e  mov     r8d, 190h; Size
0x18007f114  cmovnz  rax, rcx
0x18007f118  xor     edx, edx; Val
0x18007f11a  lea     rcx, [rsp+1F8h+BackTrace]; void *
0x18007f11f  mov     byte ptr [rax], 0
0x18007f122  call    memset_0
0x18007f127  xor     r9d, r9d; BackTraceHash
0x18007f12a  lea     r8, [rsp+1F8h+BackTrace]; BackTrace
0x18007f12f  lea     edx, [r9+32h]; FramesToCapture
0x18007f133  lea     ecx, [rdx-31h]; FramesToSkip
0x18007f136  call    cs:__imp_RtlCaptureStackBackTrace
0x18007f13c  movzx   ebp, ax
0x18007f13f  cmp     ebp, 3
0x18007f142  jb      short loc_18007F199
0x18007f144  test    [rsp+1F8h+arg_20], 1
0x18007f14c  mov     rcx, [rsp+1F8h+var_1C0]
0x18007f151  mov     rsi, [rsp+1F8h+BackTrace]
0x18007f156  mov     [rdi+rbx+18h], rcx
0x18007f15b  mov     rcx, [rsp+1F8h+var_1B8]
0x18007f160  mov     [rdi+rbx+20h], rcx
0x18007f165  mov     [rdi+rbx+10h], rsi
0x18007f16a  jz      short loc_18007F199
0x18007f16c  call    cs:__imp_GetTickCount
0x18007f172  mov     ebx, eax
0x18007f174  call    cs:__imp_GetCurrentThreadId
0x18007f17a  mov     rcx, cs:__imp_OutputDebugStringA
0x18007f181  mov     r9d, ebx
0x18007f184  mov     r8d, eax
0x18007f187  mov     [rsp+1F8h+var_1D0], r15
0x18007f18c  mov     edx, r14d
0x18007f18f  mov     [rsp+1F8h+var_1D8], rsi
0x18007f194  call    D3DOutputMessage
0x18007f199  mov     r10, cs:qword_18033B158
0x18007f1a0  lea     rsi, ?Journal@@3PAUSJournalEntry@@A; SJournalEntry near * Journal
0x18007f1a7  mov     r11, cs:?g_Journal@@3VCJournal@@A; CJournal g_Journal
0x18007f1ae  xor     ecx, ecx
0x18007f1b0  lea     edx, [rcx+1]
0x18007f1b3  cmp     edx, ebp
0x18007f1b5  jnb     short loc_18007F1EB
0x18007f1b7  mov     r8, [rsp+rcx*8+1F8h+BackTrace]
0x18007f1bc  cmp     r8, r10
0x18007f1bf  ja      short loc_18007F1E1
0x18007f1c1  cmp     r8, r11
0x18007f1c4  jb      short loc_18007F1E1
0x18007f1c6  mov     r9, [rsp+rdx*8+1F8h+BackTrace]
0x18007f1cb  cmp     r9, r11
0x18007f1ce  jb      short loc_18007F1D5
0x18007f1d0  cmp     r9, r10
0x18007f1d3  jbe     short loc_18007F1E1
0x18007f1d5  mov     [rdi+rsi+28h], r8
0x18007f1da  mov     ecx, edx
0x18007f1dc  mov     [rdi+rsi+30h], r9
0x18007f1e1  inc     ecx
0x18007f1e3  lea     eax, [rcx+1]
0x18007f1e6  cmp     eax, 32h ; '2'
0x18007f1e9  jb      short loc_18007F1B0
0x18007f1eb  test    cs:byte_180333481, 2
0x18007f1f2  jz      short loc_18007F20E
0x18007f1f4  call    cs:__imp_GetCurrentThreadId
0x18007f1fa  mov     r9d, r14d
0x18007f1fd  mov     [rsp+1F8h+var_1D0], r15
0x18007f202  mov     r8d, r12d
0x18007f205  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x18007f209  call    McTemplateU0qdqs_EventWriteTransfer
0x18007f20e  mov     rcx, [rsp+1F8h+var_38]
0x18007f216  xor     rcx, rsp; StackCookie
0x18007f219  call    __security_check_cookie
0x18007f21e  lea     r11, [rsp+1F8h+var_28]
0x18007f226  mov     rbx, [r11+30h]
0x18007f22a  mov     rbp, [r11+48h]
0x18007f22e  mov     rsp, r11
0x18007f231  pop     r15
0x18007f233  pop     r14
0x18007f235  pop     r12
0x18007f237  pop     rdi
0x18007f238  pop     rsi
0x18007f239  retn
```
