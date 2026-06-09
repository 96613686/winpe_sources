# SafeThreadCreateEx(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,int,ulong *,void * *)

- ea: `0x1800166e8`
- end: `0x1800168bc`
- name: `?SafeThreadCreateEx@@YAJPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KHPEAKPEAPEAX@Z`
- size: `468`
- prototype: `__int64 __fastcall(struct _SECURITY_ATTRIBUTES *, __int64, unsigned int (*)(void *), void *, unsigned int, int, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800170b0`

## callees

- `0x180001e90`
- `0x180001ed8`
- `0x1800090dc`
- `0x180009480`
- `0x180014a1c`
- `0x1800166e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016790`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016808`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001687f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016790`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016808`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001687f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001681d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001681d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800167de`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800167de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800168a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800168a0`

## pseudocode

```c
__int64 __fastcall SafeThreadCreateEx(
        struct _SECURITY_ATTRIBUTES *a1,
        __int64 a2,
        unsigned int (*a3)(void *),
        void *a4,
        unsigned int a5,
        int a6,
        unsigned int *a7,
        void **a8)
{
  char *v9; // r14
  unsigned int (*v10)(void *); // rdx
  int v11; // eax
  signed int v12; // edi
  void *v13; // rsi
  _QWORD *v14; // rbx
  HMODULE v15; // rcx
  void *v16; // rbx
  HANDLE v17; // rcx
  HMODULE v18; // rcx
  signed int LastError; // eax
  HMODULE v20; // rcx
  DWORD ThreadId; // [rsp+58h] [rbp+10h] BYREF

  ThreadId = 0;
  v9 = (char *)operator new(0x28u);
  *(_QWORD *)(v9 + 4) = 0;
  *(_QWORD *)(v9 + 12) = 0;
  *((_DWORD *)v9 + 5) = 0;
  *((_QWORD *)v9 + 4) = 0;
  *(_DWORD *)v9 = 1;
  *((_QWORD *)v9 + 3) = 0;
  v11 = CSafeThreadsInfo::Initialize((CSafeThreadsInfo *)v9, v10, a4);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v14 = 0;
    v13 = v9;
  }
  else
  {
    v13 = 0;
    v14 = v9;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( v14 && _InterlockedExchangeAdd((volatile signed __int32 *)v14, 0xFFFFFFFF) == 1 )
  {
    v15 = (HMODULE)v14[3];
    if ( v15 )
    {
      FreeLibrary(v15);
      v14[3] = 0;
    }
    operator delete(v14);
  }
  if ( v12 < 0 )
  {
    v16 = 0;
LABEL_11:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
    goto LABEL_25;
  }
  _InterlockedIncrement((volatile signed __int32 *)v13);
  v17 = CreateThread(0, 0, CSafeThreadsInfo::ThreadProc, v13, 0, &ThreadId);
  if ( !v17 )
  {
    v16 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF) == 1 && v13 )
    {
      v18 = (HMODULE)*((_QWORD *)v13 + 3);
      if ( v18 )
      {
        FreeLibrary(v18);
        *((_QWORD *)v13 + 3) = 0;
      }
      operator delete(v13);
    }
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v12 = -2147467259;
    }
    goto LABEL_11;
  }
  if ( a8 )
  {
    v16 = 0;
    *a8 = v17;
  }
  else
  {
    v16 = v17;
  }
LABEL_25:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( v13 && _InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF) == 1 )
  {
    v20 = (HMODULE)*((_QWORD *)v13 + 3);
    if ( v20 )
    {
      FreeLibrary(v20);
      *((_QWORD *)v13 + 3) = 0;
    }
    operator delete(v13);
  }
  if ( v16 )
    CloseHandle(v16);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800166e8  mov     rax, rsp
0x1800166eb  mov     [rax+8], rbx
0x1800166ef  mov     [rax+18h], rsi
0x1800166f3  mov     [rax+10h], edx
0x1800166f6  push    rdi
0x1800166f7  push    r14
0x1800166f9  push    r15
0x1800166fb  sub     rsp, 30h
0x1800166ff  mov     r15d, 28h ; '('
0x180016705  mov     dword ptr [rax+10h], 0
0x18001670c  mov     ecx, r15d; Size
0x18001670f  mov     rbx, r9
0x180016712  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016717  mov     r8, rbx; void *
0x18001671a  mov     rcx, rax; this
0x18001671d  mov     r14, rax
0x180016720  mov     qword ptr [rax+4], 0
0x180016728  mov     qword ptr [rax+0Ch], 0
0x180016730  mov     dword ptr [rax+14h], 0
0x180016737  mov     qword ptr [rax+20h], 0
0x18001673f  mov     dword ptr [rax], 1
0x180016745  mov     qword ptr [rax+18h], 0
0x18001674d  call    ?Initialize@CSafeThreadsInfo@@AEAAJP6AKPEAX@Z0H@Z; CSafeThreadsInfo::Initialize(ulong (*)(void *),void *,int)
0x180016752  mov     edi, eax
0x180016754  test    eax, eax
0x180016756  jns     short loc_180016766
0x180016758  xor     esi, esi
0x18001675a  mov     ecx, eax
0x18001675c  mov     rbx, r14
0x18001675f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180016764  jmp     short loc_18001676B
0x180016766  xor     ebx, ebx
0x180016768  mov     rsi, r14
0x18001676b  mov     ecx, edi
0x18001676d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016772  or      r14d, 0FFFFFFFFh
0x180016776  test    rbx, rbx
0x180016779  jz      short loc_1800167A9
0x18001677b  mov     eax, r14d
0x18001677e  lock xadd [rbx], eax
0x180016782  add     eax, r14d
0x180016785  jnz     short loc_1800167A9
0x180016787  mov     rcx, [rbx+18h]; hLibModule
0x18001678b  test    rcx, rcx
0x18001678e  jz      short loc_18001679E
0x180016790  call    cs:__imp_FreeLibrary
0x180016796  mov     qword ptr [rbx+18h], 0
0x18001679e  mov     rdx, r15; unsigned __int64
0x1800167a1  mov     rcx, rbx; void *
0x1800167a4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800167a9  test    edi, edi
0x1800167ab  jns     short loc_1800167BB
0x1800167ad  xor     ebx, ebx
0x1800167af  mov     ecx, edi
0x1800167b1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800167b6  jmp     loc_18001685E
0x1800167bb  lock inc dword ptr [rsi]
0x1800167be  lea     rax, [rsp+48h+ThreadId]
0x1800167c3  mov     r9, rsi; lpParameter
0x1800167c6  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800167cb  lea     r8, ?ThreadProc@CSafeThreadsInfo@@SAKPEAX@Z; lpStartAddress
0x1800167d2  xor     edx, edx; dwStackSize
0x1800167d4  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800167dc  xor     ecx, ecx; lpThreadAttributes
0x1800167de  call    cs:__imp_CreateThread
0x1800167e4  mov     rcx, rax
0x1800167e7  test    rax, rax
0x1800167ea  jnz     short loc_180016847
0x1800167ec  xor     ebx, ebx
0x1800167ee  mov     eax, r14d
0x1800167f1  lock xadd [rsi], eax
0x1800167f5  add     eax, r14d
0x1800167f8  jnz     short loc_18001681D
0x1800167fa  test    rsi, rsi
0x1800167fd  jz      short loc_18001681D
0x1800167ff  mov     rcx, [rsi+18h]; hLibModule
0x180016803  test    rcx, rcx
0x180016806  jz      short loc_180016812
0x180016808  call    cs:__imp_FreeLibrary
0x18001680e  mov     [rsi+18h], rbx
0x180016812  mov     rdx, r15; unsigned __int64
0x180016815  mov     rcx, rsi; void *
0x180016818  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001681d  call    cs:__imp_GetLastError
0x180016823  mov     edi, eax
0x180016825  test    eax, eax
0x180016827  jnz     short loc_180016833
0x180016829  mov     edi, 80004005h
0x18001682e  jmp     loc_1800167AF
0x180016833  jle     loc_1800167AF
0x180016839  movzx   edi, ax
0x18001683c  or      edi, 80070000h
0x180016842  jmp     loc_1800167AF
0x180016847  mov     rax, [rsp+48h+arg_38]
0x18001684f  test    rax, rax
0x180016852  jz      short loc_18001685B
0x180016854  xor     ebx, ebx
0x180016856  mov     [rax], rcx
0x180016859  jmp     short loc_18001685E
0x18001685b  mov     rbx, rcx
0x18001685e  mov     ecx, edi
0x180016860  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180016865  test    rsi, rsi
0x180016868  jz      short loc_180016898
0x18001686a  mov     eax, r14d
0x18001686d  lock xadd [rsi], eax
0x180016871  add     eax, r14d
0x180016874  jnz     short loc_180016898
0x180016876  mov     rcx, [rsi+18h]; hLibModule
0x18001687a  test    rcx, rcx
0x18001687d  jz      short loc_18001688D
0x18001687f  call    cs:__imp_FreeLibrary
0x180016885  mov     qword ptr [rsi+18h], 0
0x18001688d  mov     rdx, r15; unsigned __int64
0x180016890  mov     rcx, rsi; void *
0x180016893  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016898  test    rbx, rbx
0x18001689b  jz      short loc_1800168A6
0x18001689d  mov     rcx, rbx; hObject
0x1800168a0  call    cs:__imp_CloseHandle
0x1800168a6  mov     rbx, [rsp+48h+arg_0]
0x1800168ab  mov     eax, edi
0x1800168ad  mov     rsi, [rsp+48h+arg_10]
0x1800168b2  add     rsp, 30h
0x1800168b6  pop     r15
0x1800168b8  pop     r14
0x1800168ba  pop     rdi
0x1800168bb  retn
```
