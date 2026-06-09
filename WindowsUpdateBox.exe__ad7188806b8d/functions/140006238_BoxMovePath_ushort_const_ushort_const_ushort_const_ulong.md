# BoxMovePath(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x140006238`
- end: `0x140006531`
- name: `?BoxMovePath@@YAJPEBG00K@Z`
- size: `761`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14000bccc`

## callees

- `0x140006238`
- `0x1400076c8`
- `0x140007cb0`
- `0x14000a7d0`
- `0x1400135b8`
- `0x140016bb4`
- `0x14001d4ac`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400064ae`
- `KERNEL32!CloseHandle` at `0x1400064ae`
- `KERNEL32!MoveFileW` at `0x14000644f`
- `KERNEL32!MoveFileW` at `0x14000644f`
- `KERNEL32!HeapFree` at `0x14000636d`
- `KERNEL32!HeapFree` at `0x1400063a0`
- `KERNEL32!HeapFree` at `0x1400064d5`
- `KERNEL32!HeapFree` at `0x140006503`
- `KERNEL32!HeapFree` at `0x14000636d`
- `KERNEL32!HeapFree` at `0x1400063a0`
- `KERNEL32!HeapFree` at `0x1400064d5`
- `KERNEL32!HeapFree` at `0x140006503`
- `KERNEL32!GetProcessHeap` at `0x140006358`
- `KERNEL32!GetProcessHeap` at `0x14000638b`
- `KERNEL32!GetProcessHeap` at `0x1400064c0`
- `KERNEL32!GetProcessHeap` at `0x1400064ee`
- `KERNEL32!GetProcessHeap` at `0x140006358`
- `KERNEL32!GetProcessHeap` at `0x14000638b`
- `KERNEL32!GetProcessHeap` at `0x1400064c0`
- `KERNEL32!GetProcessHeap` at `0x1400064ee`
- `KERNEL32!GetLastError` at `0x14000645f`
- `KERNEL32!GetLastError` at `0x14000645f`
- `KERNEL32!GetFileAttributesW` at `0x1400062f3`
- `KERNEL32!GetFileAttributesW` at `0x1400062f3`

## string_xrefs

- `0x140006347`: `BoxMovePath: Target path exists [%s].`
- `0x1400063d4`: `BoxMovePath: Using target path [%s].`
- `0x1400063fa`: `BoxMovePath: No target path found!`
- `0x140006436`: `BoxMovePath: Moving [%s] -> [%s]...`

## pseudocode

```c
__int64 __fastcall BoxMovePath(LPCWSTR lpExistingFileName, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  const WCHAR *v5; // rsi
  unsigned __int16 *v6; // r14
  __int64 v7; // rcx
  unsigned int v8; // edi
  int PathWithVerification; // eax
  unsigned int v10; // r15d
  int v11; // eax
  int v12; // eax
  DWORD FileAttributesW; // ebx
  BOOL v14; // ebx
  HANDLE v15; // rcx
  char *v16; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v18; // rax
  HANDLE v19; // rcx
  HANDLE v20; // rcx
  signed int LastError; // eax
  HANDLE v22; // rax
  HANDLE v23; // rax
  HANDLE hObject[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v26; // [rsp+80h] [rbp+40h] BYREF
  LPCWSTR lpFileName; // [rsp+90h] [rbp+50h]

  hObject[1] = (HANDLE)-2LL;
  v5 = 0;
  lpFileName = 0;
  v6 = 0;
  v26 = 0;
  hObject[0] = 0;
  if ( !lpExistingFileName || !a2 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_38;
  }
  PathWithVerification = CreatePathWithVerification(a2, 1, 0, hObject);
  v8 = PathWithVerification;
  if ( PathWithVerification < 0 )
  {
    v7 = (unsigned int)PathWithVerification;
    goto LABEL_3;
  }
  v10 = 0;
  while ( 1 )
  {
    v11 = STRAPI_Format(&v26, L"%4.4d.~BT", v10);
    v8 = v11;
    if ( v11 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v11);
      v6 = v26;
      goto LABEL_38;
    }
    v6 = v26;
    v12 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)a2, (__int64)v26, 0);
    v8 = v12;
    if ( v12 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
      v5 = lpFileName;
      goto LABEL_38;
    }
    v5 = lpFileName;
    FileAttributesW = GetFileAttributesW(lpFileName);
    v14 = FileAttributesW != -1 && (FileAttributesW >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v8 = 0;
    v15 = 0;
    v16 = (char *)g_shLogFile - 1;
    if ( !v14 )
      break;
    if ( (unsigned __int64)v16 <= 0xFFFFFFFFFFFFFFFDuLL )
      v15 = g_shLogFile;
    OutputMsg(v15, g_shLogEvent, L"BoxMovePath: Target path exists [%s].", v5);
    if ( v5 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v5 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v5 = 0;
      lpFileName = 0;
    }
    if ( v6 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v6 - 2);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v6 = 0;
      v26 = 0;
    }
    if ( ++v10 >= 0x2710 )
      goto LABEL_25;
  }
  if ( (unsigned __int64)v16 <= 0xFFFFFFFFFFFFFFFDuLL )
    v15 = g_shLogFile;
  OutputMsg(v15, g_shLogEvent, L"BoxMovePath: Using target path [%s].", v5);
  if ( !v5 )
  {
LABEL_25:
    v19 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v19 = g_shLogFile;
    OutputMsg(v19, g_shLogEvent, L"BoxMovePath: No target path found!");
    v8 = -2147024893;
LABEL_28:
    v7 = v8;
    goto LABEL_3;
  }
  v20 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v20 = g_shLogFile;
  OutputMsg(v20, g_shLogEvent, L"BoxMovePath: Moving [%s] -> [%s]...", lpExistingFileName, v5);
  if ( !MoveFileW(lpExistingFileName, v5) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    goto LABEL_28;
  }
LABEL_38:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  if ( v6 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v6 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v8;
}

```

## disassembly

```asm
0x140006238  mov     rax, rsp
0x14000623b  mov     [rax+18h], r8
0x14000623f  push    rbp
0x140006240  push    rsi
0x140006241  push    rdi
0x140006242  push    r12
0x140006244  push    r13
0x140006246  push    r14
0x140006248  push    r15
0x14000624a  mov     rbp, rsp
0x14000624d  sub     rsp, 40h
0x140006251  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x140006259  mov     [rax+10h], rbx
0x14000625d  mov     r12, rdx
0x140006260  mov     r13, rcx
0x140006263  xor     esi, esi
0x140006265  mov     [rbp+lpFileName], rsi
0x140006269  xor     r14d, r14d
0x14000626c  mov     [rbp+arg_0], r14
0x140006270  mov     [rbp+hObject], r14
0x140006274  test    rcx, rcx
0x140006277  jnz     short loc_14000628A
0x140006279  mov     ecx, 80070057h
0x14000627e  mov     edi, ecx
0x140006280  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140006285  jmp     loc_14000649D
0x14000628a  test    r12, r12
0x14000628d  jz      short loc_140006279
0x14000628f  lea     r9, [rbp+hObject]; void **
0x140006293  xor     r8d, r8d; void **
0x140006296  lea     edx, [r8+1]; int
0x14000629a  mov     rcx, r12; unsigned __int16 *
0x14000629d  call    ?CreatePathWithVerification@@YAJPEBGHPEAPEAX1@Z; CreatePathWithVerification(ushort const *,int,void * *,void * *)
0x1400062a2  mov     edi, eax
0x1400062a4  test    eax, eax
0x1400062a6  jns     short loc_1400062AC
0x1400062a8  mov     ecx, eax
0x1400062aa  jmp     short loc_140006280
0x1400062ac  xor     r15d, r15d
0x1400062af  mov     r8d, r15d
0x1400062b2  lea     rdx, a44dBt; "%4.4d.~BT"
0x1400062b9  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x1400062bd  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x1400062c2  mov     edi, eax
0x1400062c4  test    eax, eax
0x1400062c6  js      loc_140006492
0x1400062cc  mov     r14, [rbp+arg_0]
0x1400062d0  lea     r9, [rbp+lpFileName]
0x1400062d4  xor     r8d, r8d
0x1400062d7  mov     rdx, r14
0x1400062da  mov     rcx, r12
0x1400062dd  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1400062e2  mov     edi, eax
0x1400062e4  test    eax, eax
0x1400062e6  js      loc_140006485
0x1400062ec  mov     rsi, [rbp+lpFileName]
0x1400062f0  mov     rcx, rsi; lpFileName
0x1400062f3  call    cs:__imp_GetFileAttributesW
0x1400062fa  nop     dword ptr [rax+rax+00h]
0x1400062ff  mov     ebx, eax
0x140006301  cmp     eax, 0FFFFFFFFh
0x140006304  jz      short loc_14000630E
0x140006306  shr     ebx, 4
0x140006309  and     ebx, 1
0x14000630c  jmp     short loc_140006310
0x14000630e  xor     ebx, ebx
0x140006310  xor     ecx, ecx
0x140006312  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140006317  xor     ecx, ecx
0x140006319  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000631e  xor     edi, edi
0x140006320  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140006327  xor     ecx, ecx
0x140006329  mov     r9, rsi
0x14000632c  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140006333  lea     rax, [r8-1]
0x140006337  test    ebx, ebx
0x140006339  jz      loc_1400063CC
0x14000633f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140006343  cmovbe  rcx, r8; hFile
0x140006347  lea     r8, aBoxmovepathTar; "BoxMovePath: Target path exists [%s]."
0x14000634e  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140006353  test    rsi, rsi
0x140006356  jz      short loc_140006386
0x140006358  call    cs:__imp_GetProcessHeap
0x14000635f  nop     dword ptr [rax+rax+00h]
0x140006364  mov     rcx, rax; hHeap
0x140006367  lea     r8, [rsi-4]; lpMem
0x14000636b  xor     edx, edx; dwFlags
0x14000636d  call    cs:__imp_HeapFree
0x140006374  nop     dword ptr [rax+rax+00h]
0x140006379  xor     ecx, ecx
0x14000637b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140006380  xor     esi, esi
0x140006382  mov     [rbp+lpFileName], rsi
0x140006386  test    r14, r14
0x140006389  jz      short loc_1400063BA
0x14000638b  call    cs:__imp_GetProcessHeap
0x140006392  nop     dword ptr [rax+rax+00h]
0x140006397  mov     rcx, rax; hHeap
0x14000639a  lea     r8, [r14-4]; lpMem
0x14000639e  xor     edx, edx; dwFlags
0x1400063a0  call    cs:__imp_HeapFree
0x1400063a7  nop     dword ptr [rax+rax+00h]
0x1400063ac  xor     ecx, ecx
0x1400063ae  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400063b3  xor     r14d, r14d
0x1400063b6  mov     [rbp+arg_0], r14
0x1400063ba  inc     r15d
0x1400063bd  cmp     r15d, 2710h
0x1400063c4  jb      loc_1400062AF
0x1400063ca  jmp     short loc_1400063E5
0x1400063cc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400063d0  cmovbe  rcx, r8; hFile
0x1400063d4  lea     r8, aBoxmovepathUsi; "BoxMovePath: Using target path [%s]."
0x1400063db  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x1400063e0  test    rsi, rsi
0x1400063e3  jnz     short loc_140006419
0x1400063e5  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x1400063ec  lea     rax, [r8-1]
0x1400063f0  xor     ecx, ecx
0x1400063f2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400063f6  cmovbe  rcx, r8; hFile
0x1400063fa  lea     r8, aBoxmovepathNoT; "BoxMovePath: No target path found!"
0x140006401  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140006408  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14000640d  mov     edi, 80070003h
0x140006412  mov     ecx, edi
0x140006414  jmp     loc_140006280
0x140006419  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140006420  lea     rax, [r8-1]
0x140006424  xor     ecx, ecx
0x140006426  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000642a  cmovbe  rcx, r8; hFile
0x14000642e  mov     [rsp+40h+var_20], rsi
0x140006433  mov     r9, r13
0x140006436  lea     r8, aBoxmovepathMov; "BoxMovePath: Moving [%s] -> [%s]..."
0x14000643d  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x140006444  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x140006449  mov     rdx, rsi; lpNewFileName
0x14000644c  mov     rcx, r13; lpExistingFileName
0x14000644f  call    cs:__imp_MoveFileW
0x140006456  nop     dword ptr [rax+rax+00h]
0x14000645b  test    eax, eax
0x14000645d  jnz     short loc_14000649D
0x14000645f  call    cs:__imp_GetLastError
0x140006466  nop     dword ptr [rax+rax+00h]
0x14000646b  mov     edi, eax
0x14000646d  test    eax, eax
0x14000646f  jnz     short loc_140006478
0x140006471  mov     edi, 80004005h
0x140006476  jmp     short loc_140006412
0x140006478  jle     short loc_140006412
0x14000647a  movzx   edi, ax
0x14000647d  or      edi, 80070000h
0x140006483  jmp     short loc_140006412
0x140006485  mov     ecx, eax
0x140006487  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000648c  mov     rsi, [rbp+lpFileName]
0x140006490  jmp     short loc_14000649D
0x140006492  mov     ecx, eax
0x140006494  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140006499  mov     r14, [rbp+arg_0]
0x14000649d  mov     ecx, edi
0x14000649f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400064a4  nop
0x1400064a5  mov     rcx, [rbp+hObject]; hObject
0x1400064a9  test    rcx, rcx
0x1400064ac  jz      short loc_1400064BB
0x1400064ae  call    cs:__imp_CloseHandle
0x1400064b5  nop     dword ptr [rax+rax+00h]
0x1400064ba  nop
0x1400064bb  test    r14, r14
0x1400064be  jz      short loc_1400064E9
0x1400064c0  call    cs:__imp_GetProcessHeap
0x1400064c7  nop     dword ptr [rax+rax+00h]
0x1400064cc  mov     rcx, rax; hHeap
0x1400064cf  lea     r8, [r14-4]; lpMem
0x1400064d3  xor     edx, edx; dwFlags
0x1400064d5  call    cs:__imp_HeapFree
0x1400064dc  nop     dword ptr [rax+rax+00h]
0x1400064e1  xor     ecx, ecx
0x1400064e3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400064e8  nop
0x1400064e9  test    rsi, rsi
0x1400064ec  jz      short loc_140006516
0x1400064ee  call    cs:__imp_GetProcessHeap
0x1400064f5  nop     dword ptr [rax+rax+00h]
0x1400064fa  mov     rcx, rax; hHeap
0x1400064fd  lea     r8, [rsi-4]; lpMem
0x140006501  xor     edx, edx; dwFlags
0x140006503  call    cs:__imp_HeapFree
0x14000650a  nop     dword ptr [rax+rax+00h]
0x14000650f  xor     ecx, ecx
0x140006511  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140006516  mov     eax, edi
0x140006518  mov     rbx, [rsp+40h+arg_8]
0x140006520  add     rsp, 40h
0x140006524  pop     r15
0x140006526  pop     r14
0x140006528  pop     r13
0x14000652a  pop     r12
0x14000652c  pop     rdi
0x14000652d  pop     rsi
0x14000652e  pop     rbp
0x14000652f  retn
```
