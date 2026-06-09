# CFoDWizard::StartCbsInstall(int)

- ea: `0x180028f60`
- end: `0x180029035`
- name: `?StartCbsInstall@CFoDWizard@@QEAAJH@Z`
- size: `213`
- prototype: `__int64 __fastcall(CFoDWizard *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180026c18`
- `0x180026fcc`

## callees

- `0x1800227c8`
- `0x180022e20`
- `0x180027f18`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028f86`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ff2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180028fbb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180028fbb`

## pseudocode

```c
__int64 __fastcall CFoDWizard::StartCbsInstall(CFoDWizard *this, int a2)
{
  _QWORD *v2; // rdi
  void *v4; // rcx
  HANDLE Thread; // rsi
  signed int LastError; // eax
  bool v8; // sf
  signed int v9; // eax
  unsigned int v10; // ebx

  v2 = (_QWORD *)((char *)this + 320);
  v4 = (void *)*((_QWORD *)this + 40);
  if ( v4 )
    WaitForSingleObject(v4, 0xFFFFFFFF);
  *((_DWORD *)this + 71) = a2;
  *((_DWORD *)this + 62) = 1;
  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CFoDWizard::CbsInstallThreadProc, this, 0, 0);
  SH<void *,SH_HANDLE>::Reset(v2);
  if ( Thread )
  {
    v10 = 0;
    *v2 = Thread;
    goto LABEL_14;
  }
  *v2 = 0;
  *((_DWORD *)this + 62) = 0;
  LastError = GetLastError();
  v8 = LastError < 0;
  if ( LastError > 0 )
    v8 = 1;
  if ( !v8 )
  {
    v10 = -2147467259;
LABEL_12:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    goto LABEL_14;
  }
  v9 = GetLastError();
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( (v10 & 0x80000000) != 0 )
    goto LABEL_12;
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
  return v10;
}

```

## disassembly

```asm
0x180028f60  mov     [rsp+arg_0], rbx
0x180028f65  mov     [rsp+arg_8], rsi
0x180028f6a  push    rdi
0x180028f6b  sub     rsp, 30h
0x180028f6f  lea     rdi, [rcx+140h]
0x180028f76  mov     rbx, rcx
0x180028f79  mov     rcx, [rdi]; hHandle
0x180028f7c  mov     esi, edx
0x180028f7e  test    rcx, rcx
0x180028f81  jz      short loc_180028F8C
0x180028f83  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180028f86  call    cs:__imp_WaitForSingleObject
0x180028f8c  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180028f95  lea     r8, ?CbsInstallThreadProc@CFoDWizard@@CAKPEAX@Z; lpStartAddress
0x180028f9c  mov     r9, rbx; lpParameter
0x180028f9f  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180028fa7  xor     edx, edx; dwStackSize
0x180028fa9  mov     [rbx+11Ch], esi
0x180028faf  xor     ecx, ecx; lpThreadAttributes
0x180028fb1  mov     dword ptr [rbx+0F8h], 1
0x180028fbb  call    cs:__imp_CreateThread
0x180028fc1  mov     rcx, rdi
0x180028fc4  mov     rsi, rax
0x180028fc7  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180028fcc  test    rsi, rsi
0x180028fcf  jnz     short loc_180029017
0x180028fd1  mov     [rdi], rsi
0x180028fd4  mov     [rbx+0F8h], esi
0x180028fda  call    cs:__imp_GetLastError
0x180028fe0  mov     edi, 80070000h
0x180028fe5  test    eax, eax
0x180028fe7  jle     short loc_180028FF0
0x180028fe9  movzx   eax, ax
0x180028fec  or      eax, edi
0x180028fee  test    eax, eax
0x180028ff0  jns     short loc_180029009
0x180028ff2  call    cs:__imp_GetLastError
0x180028ff8  mov     ebx, eax
0x180028ffa  test    eax, eax
0x180028ffc  jle     short loc_180029003
0x180028ffe  movzx   ebx, ax
0x180029001  or      ebx, edi
0x180029003  test    ebx, ebx
0x180029005  jns     short loc_18002901C
0x180029007  jmp     short loc_18002900E
0x180029009  mov     ebx, 80004005h
0x18002900e  mov     ecx, ebx
0x180029010  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180029015  jmp     short loc_18002901C
0x180029017  xor     ebx, ebx
0x180029019  mov     [rdi], rsi
0x18002901c  mov     ecx, ebx
0x18002901e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180029023  mov     rsi, [rsp+38h+arg_8]
0x180029028  mov     eax, ebx
0x18002902a  mov     rbx, [rsp+38h+arg_0]
0x18002902f  add     rsp, 30h
0x180029033  pop     rdi
0x180029034  retn
```
