# EnsureSessionStarted(ulong)

- ea: `0x140003c5c`
- end: `0x140003e4b`
- name: `?EnsureSessionStarted@@YAJK@Z`
- size: `495`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400028f8`
- `0x1400038b0`

## callees

- `0x140001008`
- `0x1400039a8`
- `0x140003c5c`
- `0x140003e54`
- `0x140007735`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140003cc0`
- `ntdll!RtlAllocateHeap` at `0x140003cc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003d49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003da2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003d49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003da2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003c84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003c84`

## pseudocode

```c
__int64 __fastcall EnsureSessionStarted(unsigned int a1)
{
  __int64 i; // rax
  _QWORD *Heap; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // ebx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // r9
  const char *v11; // [rsp+40h] [rbp-20h] BYREF
  _QWORD **v12; // [rsp+48h] [rbp-18h] BYREF
  char v13; // [rsp+50h] [rbp-10h]
  int v14; // [rsp+88h] [rbp+28h] BYREF
  int v15; // [rsp+90h] [rbp+30h] BYREF
  _QWORD *v16; // [rsp+98h] [rbp+38h] BYREF

  v16 = 0;
  v13 = 1;
  v12 = &v16;
  EnterCriticalSection(&CriticalSection);
  for ( i = qword_14000E6F0; ; i = *(_QWORD *)i )
  {
    if ( (__int64 *)i == &qword_14000E6F0 )
      goto LABEL_5;
    if ( *(_DWORD *)(i + 16) == a1 )
      break;
  }
  if ( i )
  {
    v6 = 0;
LABEL_10:
    LeaveCriticalSection(&CriticalSection);
LABEL_20:
    utl::scope_exit__EnsureSessionStarted_::_2_::_lambda_1___::_scope_exit__EnsureSessionStarted_::_2_::_lambda_1___(&v12);
    return (unsigned int)v6;
  }
LABEL_5:
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x98u);
  v16 = Heap;
  if ( !Heap )
  {
    v6 = -2147024882;
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v14 = -2147024882;
      v11 = "onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
      v15 = 360;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (int)&unk_14000AE10,
        v4,
        v5,
        (__int64 **)&v11,
        (__int64)&v15,
        (__int64)&v14);
    }
    goto LABEL_10;
  }
  memset_0(Heap, 0, 0x98u);
  v7 = qword_14000E6F0;
  if ( *(__int64 **)(qword_14000E6F0 + 8) != &qword_14000E6F0 )
    __fastfail(3u);
  v8 = v16;
  *v16 = qword_14000E6F0;
  v8[1] = &qword_14000E6F0;
  *(_QWORD *)(v7 + 8) = v8;
  qword_14000E6F0 = (__int64)v8;
  LeaveCriticalSection(&CriticalSection);
  v6 = InitializeSession((HINSTANCE)a1, v16);
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v14 = v6;
      v11 = "onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
      v15 = 366;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E010,
        (int)byte_14000ADD3,
        qword_14000E018,
        v9,
        (__int64 **)&v11,
        (__int64)&v15,
        (__int64)&v14);
    }
    goto LABEL_20;
  }
  v16 = 0;
  utl::scope_exit__EnsureSessionStarted_::_2_::_lambda_1___::_scope_exit__EnsureSessionStarted_::_2_::_lambda_1___(&v12);
  return 0;
}

```

## disassembly

```asm
0x140003c5c  push    rbp
0x140003c5e  push    rbx
0x140003c5f  push    rdi
0x140003c60  mov     rbp, rsp
0x140003c63  sub     rsp, 60h
0x140003c67  mov     ebx, ecx
0x140003c69  mov     [rbp+arg_18], 0
0x140003c71  lea     rax, [rbp+arg_18]
0x140003c75  mov     [rbp+var_10], 1
0x140003c79  lea     rcx, CriticalSection; lpCriticalSection
0x140003c80  mov     [rbp+var_18], rax
0x140003c84  call    cs:__imp_EnterCriticalSection
0x140003c8a  mov     rax, cs:qword_14000E6F0
0x140003c91  lea     rdi, qword_14000E6F0
0x140003c98  jmp     short loc_140003CA6
0x140003c9a  cmp     [rax+10h], ebx
0x140003c9d  jz      loc_140003D54
0x140003ca3  mov     rax, [rax]
0x140003ca6  cmp     rax, rdi
0x140003ca9  jnz     short loc_140003C9A
0x140003cab  mov     rcx, gs:60h
0x140003cb4  xor     edx, edx; Flags
0x140003cb6  mov     r8d, 98h; Size
0x140003cbc  mov     rcx, [rcx+30h]; HeapHandle
0x140003cc0  call    cs:__imp_RtlAllocateHeap
0x140003cc6  mov     [rbp+arg_18], rax
0x140003cca  test    rax, rax
0x140003ccd  jnz     loc_140003D61
0x140003cd3  mov     eax, cs:dword_14000E000
0x140003cd9  mov     ebx, 8007000Eh
0x140003cde  cmp     eax, 2
0x140003ce1  jbe     short loc_140003D42
0x140003ce3  mov     rcx, cs:qword_14000E018
0x140003cea  mov     edx, 800h
0x140003cef  mov     rax, cs:qword_14000E010
0x140003cf6  test    rdx, rax
0x140003cf9  jz      short loc_140003D42
0x140003cfb  mov     rax, rcx
0x140003cfe  and     rax, rdx
0x140003d01  cmp     rax, rcx
0x140003d04  jnz     short loc_140003D42
0x140003d06  lea     rax, aOnecoreXboxGam_3; "onecore\\xbox\\gameinput\\published\\sv"...
0x140003d0d  mov     [rbp+arg_8], ebx
0x140003d10  mov     [rbp+var_20], rax
0x140003d14  lea     rdx, unk_14000AE10
0x140003d1b  lea     rax, [rbp+arg_8]
0x140003d1f  mov     [rbp+arg_10], 168h
0x140003d26  mov     [rsp+60h+var_30], rax
0x140003d2b  lea     rax, [rbp+arg_10]
0x140003d2f  mov     [rsp+60h+var_38], rax
0x140003d34  lea     rax, [rbp+var_20]
0x140003d38  mov     [rsp+60h+var_40], rax
0x140003d3d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140003d42  lea     rcx, CriticalSection; lpCriticalSection
0x140003d49  call    cs:__imp_LeaveCriticalSection
0x140003d4f  jmp     loc_140003E23
0x140003d54  test    rax, rax
0x140003d57  jz      loc_140003CAB
0x140003d5d  xor     ebx, ebx
0x140003d5f  jmp     short loc_140003D42
0x140003d61  xor     edx, edx; Val
0x140003d63  mov     r8d, 98h; Size
0x140003d69  mov     rcx, rax; void *
0x140003d6c  call    memset_0
0x140003d71  mov     rcx, cs:qword_14000E6F0
0x140003d78  cmp     [rcx+8], rdi
0x140003d7c  jz      short loc_140003D85
0x140003d7e  mov     ecx, 3
0x140003d83  int     29h; Win8: RtlFailFast(ecx)
0x140003d85  mov     rax, [rbp+arg_18]
0x140003d89  mov     [rax], rcx
0x140003d8c  mov     [rax+8], rdi
0x140003d90  mov     [rcx+8], rax
0x140003d94  lea     rcx, CriticalSection; lpCriticalSection
0x140003d9b  mov     cs:qword_14000E6F0, rax
0x140003da2  call    cs:__imp_LeaveCriticalSection
0x140003da8  mov     rdx, [rbp+arg_18]
0x140003dac  mov     ecx, ebx
0x140003dae  call    InitializeSession
0x140003db3  mov     ebx, eax
0x140003db5  test    eax, eax
0x140003db7  jns     short loc_140003E30
0x140003db9  mov     ecx, cs:dword_14000E000
0x140003dbf  cmp     ecx, 2
0x140003dc2  jbe     short loc_140003E23
0x140003dc4  mov     r8, cs:qword_14000E018
0x140003dcb  mov     edx, 800h
0x140003dd0  mov     rcx, cs:qword_14000E010
0x140003dd7  test    rdx, rcx
0x140003dda  jz      short loc_140003E23
0x140003ddc  mov     rax, r8
0x140003ddf  and     rax, rdx
0x140003de2  cmp     rax, r8
0x140003de5  jnz     short loc_140003E23
0x140003de7  lea     rax, aOnecoreXboxGam_3; "onecore\\xbox\\gameinput\\published\\sv"...
0x140003dee  mov     [rbp+arg_8], ebx
0x140003df1  mov     [rbp+var_20], rax
0x140003df5  lea     rdx, byte_14000ADD3
0x140003dfc  lea     rax, [rbp+arg_8]
0x140003e00  mov     [rbp+arg_10], 16Eh
0x140003e07  mov     [rsp+60h+var_30], rax
0x140003e0c  lea     rax, [rbp+arg_10]
0x140003e10  mov     [rsp+60h+var_38], rax
0x140003e15  lea     rax, [rbp+var_20]
0x140003e19  mov     [rsp+60h+var_40], rax
0x140003e1e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140003e23  lea     rcx, [rbp+var_18]
0x140003e27  call    utl__scope_exit__EnsureSessionStarted____2____lambda_1______scope_exit__EnsureSessionStarted____2____lambda_1___
0x140003e2c  mov     eax, ebx
0x140003e2e  jmp     short loc_140003E43
0x140003e30  lea     rcx, [rbp+var_18]
0x140003e34  mov     [rbp+arg_18], 0
0x140003e3c  call    utl__scope_exit__EnsureSessionStarted____2____lambda_1______scope_exit__EnsureSessionStarted____2____lambda_1___
0x140003e41  xor     eax, eax
0x140003e43  add     rsp, 60h
0x140003e47  pop     rdi
0x140003e48  pop     rbx
0x140003e49  pop     rbp
0x140003e4a  retn
```
