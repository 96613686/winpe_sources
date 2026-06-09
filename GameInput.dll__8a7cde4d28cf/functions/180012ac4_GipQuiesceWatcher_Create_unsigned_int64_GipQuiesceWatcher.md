# GipQuiesceWatcher::Create(unsigned __int64,GipQuiesceWatcher * *)

- ea: `0x180012ac4`
- end: `0x180012d68`
- name: `?Create@GipQuiesceWatcher@@SAJ_KPEAPEAV1@@Z`
- size: `676`
- prototype: `__int64 __fastcall(unsigned __int64, struct GipQuiesceWatcher **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180014f18`

## callees

- `0x180001304`
- `0x1800023a4`
- `0x18000c11c`
- `0x18000ff40`
- `0x180012ac4`
- `0x18001a2bc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180012b69`
- `ntdll!RtlAllocateHeap` at `0x180012b69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012c66`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012c66`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012bce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012be2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012be2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c7b`

## pseudocode

```c
__int64 __fastcall GipQuiesceWatcher::Create(__int64 a1, struct GipQuiesceWatcher **a2, __int64 a3, int a4)
{
  GipQuiesceWatcher *Heap; // rax
  int v7; // r8d
  int v8; // r9d
  GipQuiesceWatcher *v9; // rdi
  HANDLE FileW; // rax
  signed int LastError; // ebx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rcx
  __int16 *v15; // rdx
  HANDLE EventW; // rax
  const struct std::nothrow_t *v17; // rdx
  const char *v19; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+88h] [rbp+38h] BYREF
  __int64 v21; // [rsp+90h] [rbp+40h] BYREF
  const char *v22; // [rsp+98h] [rbp+48h] BYREF

  *a2 = 0;
  if ( (unsigned int)dword_180069000 > 5 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v21 = a1;
    v22 = "Creating GIP quiesce watcher";
    v20 = 41;
    v19 = "onecore\\xbox\\gameinput\\feedback\\GipQuiesceWatcher.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      a1,
      (unsigned int)&word_18005A6D6,
      qword_180069018,
      a4,
      (__int64)&v19,
      (__int64)&v20,
      (__int64)&v22,
      (__int64)&v21);
  }
  Heap = (GipQuiesceWatcher *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x40u);
  v9 = Heap;
  if ( !Heap )
  {
    LastError = -2147024882;
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v20 = -2147024882;
      LODWORD(v21) = 44;
      v22 = "onecore\\xbox\\gameinput\\feedback\\GipQuiesceWatcher.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&v22,
        (unsigned int)&dword_18005C724,
        v7,
        v8,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v20);
    }
    return (unsigned int)LastError;
  }
  *(_QWORD *)Heap = 0;
  *((_QWORD *)Heap + 1) = 0;
  *((_OWORD *)Heap + 1) = 0;
  *((_OWORD *)Heap + 2) = 0;
  *((_QWORD *)Heap + 6) = a1;
  *((_BYTE *)Heap + 56) = 0;
  FileW = CreateFileW(L"\\\\.\\XboxGIP_Admin", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  *(_QWORD *)v9 = FileW;
  if ( !FileW )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_12;
    if ( (qword_180069010 & 8) == 0 )
      goto LABEL_12;
    v14 = qword_180069018 & 8;
    if ( v14 != qword_180069018 )
      goto LABEL_12;
    LODWORD(v21) = 55;
    v15 = &word_18005DDCE;
    goto LABEL_11;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v9 + 1) = EventW;
  if ( EventW )
  {
    LastError = GipQuiesceWatcher::RequestQuiesceNotification(v9);
    if ( LastError >= 0 )
    {
      *a2 = v9;
      return 0;
    }
    goto LABEL_22;
  }
  LastError = GetLastError();
  if ( (unsigned int)dword_180069000 > 2 )
  {
    LODWORD(v14) = qword_180069018;
    if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      LODWORD(v21) = 63;
      v15 = (__int16 *)byte_18005D3C3;
LABEL_11:
      v22 = "onecore\\xbox\\gameinput\\feedback\\GipQuiesceWatcher.cpp";
      v20 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (_DWORD)v15,
        v12,
        v13,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v20);
    }
  }
LABEL_12:
  if ( LastError )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    LastError = -2147418113;
  }
LABEL_22:
  GipQuiesceWatcher::~GipQuiesceWatcher(v9);
  operator delete(v9, v17);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180012ac4  mov     r11, rsp
0x180012ac7  push    rbp
0x180012ac8  push    rbx
0x180012ac9  push    rsi
0x180012aca  push    rdi
0x180012acb  push    r15
0x180012acd  mov     rbp, rsp
0x180012ad0  sub     rsp, 50h
0x180012ad4  mov     qword ptr [rdx], 0
0x180012adb  lea     r15, aOnecoreXboxGam_15; "onecore\\xbox\\gameinput\\feedback\\Gip"...
0x180012ae2  mov     eax, cs:dword_180069000
0x180012ae8  mov     rsi, rdx
0x180012aeb  mov     rbx, rcx
0x180012aee  cmp     eax, 5
0x180012af1  jbe     short loc_180012B56
0x180012af3  mov     r8, cs:qword_180069018
0x180012afa  mov     rax, cs:qword_180069010
0x180012b01  test    al, 8
0x180012b03  jz      short loc_180012B56
0x180012b05  mov     rax, r8
0x180012b08  and     eax, 8
0x180012b0b  cmp     rax, r8
0x180012b0e  jnz     short loc_180012B56
0x180012b10  lea     rax, aCreatingGipQui; "Creating GIP quiesce watcher"
0x180012b17  mov     [rbp+arg_10], rcx
0x180012b1b  mov     [rbp+arg_18], rax
0x180012b1f  lea     rdx, word_18005A6D6
0x180012b26  lea     rax, [rbp+arg_10]
0x180012b2a  mov     [rbp+arg_8], 29h ; ')'
0x180012b31  mov     [r11-40h], rax
0x180012b35  lea     rax, [rbp+arg_18]
0x180012b39  mov     [r11-48h], rax
0x180012b3d  lea     rax, [rbp+arg_8]
0x180012b41  mov     [r11-50h], rax
0x180012b45  lea     rax, [rbp+var_10]
0x180012b49  mov     [r11-58h], rax
0x180012b4d  mov     [rbp+var_10], r15
0x180012b51  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180012b56  mov     rcx, gs:60h
0x180012b5f  xor     edx, edx; Flags
0x180012b61  mov     rcx, [rcx+30h]; HeapHandle
0x180012b65  lea     r8d, [rdx+40h]; Size
0x180012b69  call    cs:__imp_RtlAllocateHeap
0x180012b70  nop     dword ptr [rax+rax+00h]
0x180012b75  mov     rdi, rax
0x180012b78  test    rax, rax
0x180012b7b  jz      loc_180012CF8
0x180012b81  xorps   xmm0, xmm0
0x180012b84  mov     qword ptr [rax], 0
0x180012b8b  mov     qword ptr [rax+8], 0
0x180012b93  lea     rcx, aXboxgipAdmin; "\\\\.\\XboxGIP_Admin"
0x180012b9a  movups  xmmword ptr [rax+10h], xmm0
0x180012b9e  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x180012ba7  mov     r8d, 3; dwShareMode
0x180012bad  movups  xmmword ptr [rax+20h], xmm0
0x180012bb1  mov     [rsp+50h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180012bb9  xor     r9d, r9d; lpSecurityAttributes
0x180012bbc  mov     edx, 0C0000000h; dwDesiredAccess
0x180012bc1  mov     [rax+30h], rbx
0x180012bc5  mov     byte ptr [rax+38h], 0
0x180012bc9  mov     [rsp+50h+dwCreationDisposition], r8d; dwCreationDisposition
0x180012bce  call    cs:__imp_CreateFileW
0x180012bd5  nop     dword ptr [rax+rax+00h]
0x180012bda  mov     [rdi], rax
0x180012bdd  test    rax, rax
0x180012be0  jnz     short loc_180012C5C
0x180012be2  call    cs:__imp_GetLastError
0x180012be9  nop     dword ptr [rax+rax+00h]
0x180012bee  mov     ecx, cs:dword_180069000
0x180012bf4  mov     ebx, eax
0x180012bf6  cmp     ecx, 2
0x180012bf9  jbe     short loc_180012C4E
0x180012bfb  mov     rax, cs:qword_180069018
0x180012c02  mov     rcx, cs:qword_180069010
0x180012c09  test    cl, 8
0x180012c0c  jz      short loc_180012C4E
0x180012c0e  mov     rcx, rax
0x180012c11  and     ecx, 8
0x180012c14  cmp     rcx, rax
0x180012c17  jnz     short loc_180012C4E
0x180012c19  mov     dword ptr [rbp+arg_10], 37h ; '7'
0x180012c20  lea     rdx, word_18005DDCE
0x180012c27  lea     rax, [rbp+arg_8]
0x180012c2b  mov     [rbp+arg_18], r15
0x180012c2f  mov     [rsp+50h+hTemplateFile], rax
0x180012c34  lea     rax, [rbp+arg_10]
0x180012c38  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], rax
0x180012c3d  lea     rax, [rbp+arg_18]
0x180012c41  mov     qword ptr [rsp+50h+dwCreationDisposition], rax
0x180012c46  mov     [rbp+arg_8], ebx
0x180012c49  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180012c4e  test    ebx, ebx
0x180012c50  jnz     short loc_180012CC4
0x180012c52  mov     ebx, 8000FFFFh
0x180012c57  jmp     loc_180012CDF
0x180012c5c  xor     r9d, r9d; lpName
0x180012c5f  xor     r8d, r8d; bInitialState
0x180012c62  xor     edx, edx; bManualReset
0x180012c64  xor     ecx, ecx; lpEventAttributes
0x180012c66  call    cs:__imp_CreateEventW
0x180012c6d  nop     dword ptr [rax+rax+00h]
0x180012c72  mov     [rdi+8], rax
0x180012c76  test    rax, rax
0x180012c79  jnz     short loc_180012CD1
0x180012c7b  call    cs:__imp_GetLastError
0x180012c82  nop     dword ptr [rax+rax+00h]
0x180012c87  mov     ebx, eax
0x180012c89  mov     eax, cs:dword_180069000
0x180012c8f  cmp     eax, 2
0x180012c92  jbe     short loc_180012C4E
0x180012c94  mov     rcx, cs:qword_180069018
0x180012c9b  mov     rax, cs:qword_180069010
0x180012ca2  test    al, 8
0x180012ca4  jz      short loc_180012C4E
0x180012ca6  mov     rax, rcx
0x180012ca9  and     eax, 8
0x180012cac  cmp     rax, rcx
0x180012caf  jnz     short loc_180012C4E
0x180012cb1  mov     dword ptr [rbp+arg_10], 3Fh ; '?'
0x180012cb8  lea     rdx, byte_18005D3C3
0x180012cbf  jmp     loc_180012C27
0x180012cc4  jle     short loc_180012CDF
0x180012cc6  movzx   ebx, bx
0x180012cc9  or      ebx, 80070000h
0x180012ccf  jmp     short loc_180012CDF
0x180012cd1  mov     rcx, rdi; this
0x180012cd4  call    ?RequestQuiesceNotification@GipQuiesceWatcher@@AEAAJXZ; GipQuiesceWatcher::RequestQuiesceNotification(void)
0x180012cd9  mov     ebx, eax
0x180012cdb  test    eax, eax
0x180012cdd  jns     short loc_180012CF1
0x180012cdf  mov     rcx, rdi; this
0x180012ce2  call    ??1GipQuiesceWatcher@@QEAA@XZ; GipQuiesceWatcher::~GipQuiesceWatcher(void)
0x180012ce7  mov     rcx, rdi; P
0x180012cea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012cef  jmp     short loc_180012D5A
0x180012cf1  mov     [rsi], rdi
0x180012cf4  xor     eax, eax
0x180012cf6  jmp     short loc_180012D5C
0x180012cf8  mov     eax, cs:dword_180069000
0x180012cfe  mov     ebx, 8007000Eh
0x180012d03  cmp     eax, 2
0x180012d06  jbe     short loc_180012D5A
0x180012d08  mov     rcx, cs:qword_180069018
0x180012d0f  mov     rax, cs:qword_180069010
0x180012d16  test    al, 8
0x180012d18  jz      short loc_180012D5A
0x180012d1a  mov     rax, rcx
0x180012d1d  and     eax, 8
0x180012d20  cmp     rax, rcx
0x180012d23  jnz     short loc_180012D5A
0x180012d25  lea     rcx, [rbp+arg_8]
0x180012d29  mov     [rbp+arg_8], ebx
0x180012d2c  mov     [rsp+50h+hTemplateFile], rcx
0x180012d31  lea     rdx, dword_18005C724
0x180012d38  lea     rcx, [rbp+arg_10]
0x180012d3c  mov     dword ptr [rbp+arg_10], 2Ch ; ','
0x180012d43  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], rcx
0x180012d48  lea     rcx, [rbp+arg_18]
0x180012d4c  mov     qword ptr [rsp+50h+dwCreationDisposition], rcx
0x180012d51  mov     [rbp+arg_18], r15
0x180012d55  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180012d5a  mov     eax, ebx
0x180012d5c  add     rsp, 50h
0x180012d60  pop     r15
0x180012d62  pop     rdi
0x180012d63  pop     rsi
0x180012d64  pop     rbx
0x180012d65  pop     rbp
0x180012d66  retn
```
