# GameInputDispatcher::StartThread(void)

- ea: `0x18000b700`
- end: `0x18000b836`
- name: `?StartThread@GameInputDispatcher@@AEAAJXZ`
- size: `310`
- prototype: `__int64 __fastcall(GameInputDispatcher *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180007ec0`
- `0x18000a5a0`

## callees

- `0x180001304`
- `0x18000b700`
- `0x18000d68c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b73e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b73e`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000b7f7`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000b7f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b811`

## pseudocode

```c
__int64 __fastcall GameInputDispatcher::StartThread(GameInputDispatcher *this)
{
  signed int v2; // ebx
  int v3; // r8d
  int v4; // r9d
  signed int LastError; // eax
  signed int v7; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+58h] [rbp+10h] BYREF
  const char *v9; // [rsp+60h] [rbp+18h] BYREF

  if ( *((_QWORD *)this + 7) )
    return 0;
  *((_QWORD *)this + 8) = -1;
  _mm_mfence();
  *((_QWORD *)this + 7) = CreateThread(0, 0, GameInputDispatcher::ThreadProcThunk, this, 4u, 0);
  _mm_mfence();
  if ( *((_QWORD *)this + 7) )
  {
    if ( ResumeThread(*((HANDLE *)this + 7)) == -1 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      GameInputFailFast((unsigned int)LastError, 281);
      JUMPOUT(0x18000B835LL);
    }
    return 0;
  }
  v2 = GetLastError();
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
  {
    v7 = v2;
    v9 = "onecore\\xbox\\gameinput\\client\\GameInputDispatcher.cpp";
    v8 = 280;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)&byte_180059867,
      v3,
      v4,
      (__int64)&v9,
      (__int64)&v8,
      (__int64)&v7);
  }
  if ( v2 )
  {
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000b700  push    rbx
0x18000b702  sub     rsp, 40h
0x18000b706  mov     rax, [rcx+38h]
0x18000b70a  mov     rbx, rcx
0x18000b70d  nop
0x18000b70e  test    rax, rax
0x18000b711  jnz     loc_18000B808
0x18000b717  nop
0x18000b718  mov     qword ptr [rcx+40h], 0FFFFFFFFFFFFFFFFh
0x18000b720  mfence
0x18000b723  mov     r9, rcx; lpParameter
0x18000b726  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18000b72b  xor     ecx, ecx; lpThreadAttributes
0x18000b72d  mov     [rsp+48h+dwCreationFlags], 4; dwCreationFlags
0x18000b735  lea     r8, ?ThreadProcThunk@GameInputDispatcher@@CAKPEAX@Z; lpStartAddress
0x18000b73c  xor     edx, edx; dwStackSize
0x18000b73e  call    cs:__imp_CreateThread
0x18000b745  nop     dword ptr [rax+rax+00h]
0x18000b74a  nop
0x18000b74b  mov     [rbx+38h], rax
0x18000b74f  mfence
0x18000b752  mov     rax, [rbx+38h]
0x18000b756  nop
0x18000b757  test    rax, rax
0x18000b75a  jnz     loc_18000B7F2
0x18000b760  call    cs:__imp_GetLastError
0x18000b767  nop     dword ptr [rax+rax+00h]
0x18000b76c  mov     ebx, eax
0x18000b76e  mov     eax, cs:dword_180069000
0x18000b774  cmp     eax, 2
0x18000b777  jbe     short loc_18000B7D8
0x18000b779  mov     rcx, cs:qword_180069018
0x18000b780  mov     rax, cs:qword_180069010
0x18000b787  test    al, 1
0x18000b789  jz      short loc_18000B7D8
0x18000b78b  mov     rax, rcx
0x18000b78e  and     eax, 1
0x18000b791  cmp     rax, rcx
0x18000b794  jnz     short loc_18000B7D8
0x18000b796  lea     rax, aOnecoreXboxGam_9; "onecore\\xbox\\gameinput\\client\\GameI"...
0x18000b79d  mov     [rsp+48h+arg_0], ebx
0x18000b7a1  mov     [rsp+48h+arg_10], rax
0x18000b7a6  lea     rdx, byte_180059867
0x18000b7ad  lea     rax, [rsp+48h+arg_0]
0x18000b7b2  mov     [rsp+48h+arg_8], 118h
0x18000b7ba  mov     [rsp+48h+var_18], rax
0x18000b7bf  lea     rax, [rsp+48h+arg_8]
0x18000b7c4  mov     [rsp+48h+lpThreadId], rax
0x18000b7c9  lea     rax, [rsp+48h+arg_10]
0x18000b7ce  mov     qword ptr [rsp+48h+dwCreationFlags], rax
0x18000b7d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000b7d8  test    ebx, ebx
0x18000b7da  jnz     short loc_18000B7E3
0x18000b7dc  mov     ebx, 8000FFFFh
0x18000b7e1  jmp     short loc_18000B7EE
0x18000b7e3  jle     short loc_18000B7EE
0x18000b7e5  movzx   ebx, bx
0x18000b7e8  or      ebx, 80070000h
0x18000b7ee  mov     eax, ebx
0x18000b7f0  jmp     short loc_18000B80A
0x18000b7f2  mov     rcx, [rbx+38h]; hThread
0x18000b7f6  nop
0x18000b7f7  call    cs:__imp_ResumeThread
0x18000b7fe  nop     dword ptr [rax+rax+00h]
0x18000b803  cmp     eax, 0FFFFFFFFh
0x18000b806  jz      short loc_18000B811
0x18000b808  xor     eax, eax
0x18000b80a  add     rsp, 40h
0x18000b80e  pop     rbx
0x18000b80f  retn
0x18000b811  call    cs:__imp_GetLastError
0x18000b818  nop     dword ptr [rax+rax+00h]
0x18000b81d  test    eax, eax
0x18000b81f  jle     short loc_18000B829
0x18000b821  movzx   eax, ax
0x18000b824  or      eax, 80070000h
0x18000b829  mov     edx, 119h
0x18000b82e  mov     ecx, eax
0x18000b830  call    GameInputFailFast
```
