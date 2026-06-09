# CopyFileIfNewer(ushort const *,ushort const *)

- ea: `0x140001e5c`
- end: `0x1400021eb`
- name: `?CopyFileIfNewer@@YAJPEBG0@Z`
- size: `911`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x140002ac0`

## callees

- `0x140001008`
- `0x140001e5c`
- `0x140002798`
- `0x140004c20`
- `0x140006b48`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140001f66`
- `ntdll!RtlAllocateHeap` at `0x140001f66`
- `ntdll!swprintf_s` at `0x140002006`
- `ntdll!swprintf_s` at `0x140002006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002077`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140001f14`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x14000206d`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140001f14`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x14000206d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000200f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14000200f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000205e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14000205e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x14000201b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x14000201b`

## pseudocode

```c
__int64 __fastcall CopyFileIfNewer(LPCWSTR lpExistingFileName, LPCWSTR lpFileName)
{
  DWORD LastError; // ebx
  int v5; // r9d
  int v6; // r8d
  _QWORD *v7; // rcx
  int *v8; // rdx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rax
  size_t v13; // r15
  SIZE_T v14; // rax
  unsigned __int64 v15; // kr00_8
  wchar_t *Heap; // r14
  unsigned __int16 v17; // bx
  int v18; // r8d
  int v19; // r9d
  bool v20; // cc
  __int64 v21; // [rsp+20h] [rbp-30h]
  _QWORD v22[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD v23; // [rsp+A0h] [rbp+50h] BYREF
  int v24; // [rsp+A8h] [rbp+58h] BYREF

  LastError = IsFileNewerThan(lpExistingFileName, lpFileName);
  if ( (LastError & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_14000E000 <= 2 )
      return LastError;
    v6 = qword_14000E018;
    LODWORD(v7) = qword_14000E010;
    if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
      return LastError;
    v24 = 82;
    v8 = &dword_14000A74C;
    goto LABEL_6;
  }
  if ( LastError == 1 )
    return 1;
  if ( !CopyFileW(lpExistingFileName, lpFileName, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 32 )
    {
      v12 = -1;
      do
        ++v12;
      while ( lpFileName[v12] );
      v13 = v12 + 6;
      v15 = v12 + 6;
      v14 = 2 * (v12 + 6);
      if ( !is_mul_ok(v15, 2u) )
        v14 = -1;
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
      if ( !Heap )
      {
        LastError = -2147024882;
        if ( (unsigned int)dword_14000E000 <= 2
          || (qword_14000E010 & 0x800) == 0
          || (qword_14000E018 & 0x800) != qword_14000E018 )
        {
          return LastError;
        }
        v24 = 95;
        v22[0] = "onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
        v8 = &dword_14000A6FC;
        v7 = v22;
        goto LABEL_7;
      }
      v17 = 0;
      while ( 1 )
      {
        LODWORD(v21) = v17;
        swprintf_s(Heap, v13, L"%ws.%x", lpFileName, v21);
        DeleteFileW(Heap);
        if ( MoveFileW(lpFileName, Heap) )
          break;
        if ( ++v17 == 0xFFFF )
          goto LABEL_25;
      }
      MoveFileExW(Heap, 0, 4u);
      if ( CopyFileW(lpExistingFileName, lpFileName, 0) )
      {
LABEL_25:
        operator delete[](Heap);
        return 0;
      }
      LastError = GetLastError();
      if ( (unsigned int)dword_14000E000 > 2
        && (qword_14000E010 & 0x800) != 0
        && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v23 = LastError;
        v22[0] = "onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
        v24 = 105;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14000E018,
          (unsigned int)&dword_14000A6BC,
          v18,
          v19,
          (__int64)v22,
          (__int64)&v24,
          (__int64)&v23);
      }
      v20 = (int)LastError <= 0;
      if ( !LastError )
        return (DWORD)-2147418113;
LABEL_34:
      if ( !v20 )
        return (unsigned __int16)LastError | 0x80070000;
      return LastError;
    }
    if ( LastError != 5 )
    {
      if ( !LastError )
        return LastError;
      if ( (unsigned int)dword_14000E000 > 2
        && (qword_14000E010 & 0x800) != 0
        && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v23 = LastError;
        v22[0] = "onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
        v24 = 118;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14000E018,
          (unsigned int)&byte_14000A63F,
          v10,
          v11,
          (__int64)v22,
          (__int64)&v24,
          (__int64)&v23);
      }
      v20 = (int)LastError <= 0;
      goto LABEL_34;
    }
    LastError = ModifySystemFile(lpExistingFileName, lpFileName);
    if ( (LastError & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_14000E000 <= 2 )
        return LastError;
      v6 = qword_14000E018;
      LODWORD(v7) = qword_14000E010;
      if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
        return LastError;
      v24 = 114;
      v8 = (int *)&byte_14000A67F;
LABEL_6:
      v22[0] = "onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
LABEL_7:
      v23 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v7,
        (_DWORD)v8,
        v6,
        v5,
        (__int64)v22,
        (__int64)&v24,
        (__int64)&v23);
      return LastError;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140001e5c  mov     [rsp-38h+arg_0], rbx
0x140001e61  push    rbp
0x140001e62  push    rsi
0x140001e63  push    rdi
0x140001e64  push    r12
0x140001e66  push    r13
0x140001e68  push    r14
0x140001e6a  push    r15
0x140001e6c  mov     rbp, rsp
0x140001e6f  sub     rsp, 50h
0x140001e73  mov     rdi, rdx
0x140001e76  mov     rsi, rcx
0x140001e79  call    ?IsFileNewerThan@@YAJPEBG0@Z; IsFileNewerThan(ushort const *,ushort const *)
0x140001e7e  xor     r12d, r12d
0x140001e81  mov     ebx, eax
0x140001e83  test    eax, eax
0x140001e85  jns     short loc_140001EF8
0x140001e87  mov     ecx, cs:dword_14000E000
0x140001e8d  cmp     ecx, 2
0x140001e90  jbe     short loc_140001EF1
0x140001e92  mov     r8, cs:qword_14000E018
0x140001e99  mov     edx, 800h
0x140001e9e  mov     rcx, cs:qword_14000E010
0x140001ea5  test    rdx, rcx
0x140001ea8  jz      short loc_140001EF1
0x140001eaa  mov     rax, r8
0x140001ead  and     rax, rdx
0x140001eb0  cmp     rax, r8
0x140001eb3  jnz     short loc_140001EF1
0x140001eb5  mov     [rbp+arg_18], 52h ; 'R'
0x140001ebc  lea     rdx, dword_14000A74C
0x140001ec3  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x140001eca  mov     [rbp+var_10], rax
0x140001ece  lea     rax, [rbp+arg_10]
0x140001ed2  mov     [rsp+50h+var_20], rax
0x140001ed7  lea     rax, [rbp+arg_18]
0x140001edb  mov     [rsp+50h+var_28], rax
0x140001ee0  lea     rax, [rbp+var_10]
0x140001ee4  mov     [rsp+50h+var_30], rax
0x140001ee9  mov     [rbp+arg_10], ebx
0x140001eec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140001ef1  mov     eax, ebx
0x140001ef3  jmp     loc_14000203D
0x140001ef8  mov     r13d, 1
0x140001efe  cmp     ebx, r13d
0x140001f01  jnz     short loc_140001F0B
0x140001f03  mov     eax, r13d
0x140001f06  jmp     loc_14000203D
0x140001f0b  xor     r8d, r8d; bFailIfExists
0x140001f0e  mov     rdx, rdi; lpNewFileName
0x140001f11  mov     rcx, rsi; lpExistingFileName
0x140001f14  call    cs:__imp_CopyFileW
0x140001f1a  test    eax, eax
0x140001f1c  jnz     loc_14000203B
0x140001f22  call    cs:__imp_GetLastError
0x140001f28  mov     ebx, eax
0x140001f2a  cmp     eax, 20h ; ' '
0x140001f2d  jnz     loc_14000210B
0x140001f33  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001f37  mov     rax, rcx
0x140001f3a  inc     rax
0x140001f3d  cmp     [rdi+rax*2], r12w
0x140001f42  jnz     short loc_140001F3A
0x140001f44  lea     r15, [rax+6]
0x140001f48  mov     eax, 2
0x140001f4d  mul     r15
0x140001f50  cmovb   rax, rcx
0x140001f54  mov     rcx, gs:60h
0x140001f5d  mov     r8, rax; Size
0x140001f60  xor     edx, edx; Flags
0x140001f62  mov     rcx, [rcx+30h]; HeapHandle
0x140001f66  call    cs:__imp_RtlAllocateHeap
0x140001f6c  mov     r14, rax
0x140001f6f  test    rax, rax
0x140001f72  jnz     short loc_140001FEC
0x140001f74  mov     eax, cs:dword_14000E000
0x140001f7a  mov     ebx, 8007000Eh
0x140001f7f  cmp     eax, 2
0x140001f82  jbe     loc_140001EF1
0x140001f88  mov     rcx, cs:qword_14000E018
0x140001f8f  mov     edx, 800h
0x140001f94  mov     rax, cs:qword_14000E010
0x140001f9b  test    rdx, rax
0x140001f9e  jz      loc_140001EF1
0x140001fa4  mov     rax, rcx
0x140001fa7  and     rax, rdx
0x140001faa  cmp     rax, rcx
0x140001fad  jnz     loc_140001EF1
0x140001fb3  lea     rcx, [rbp+arg_10]
0x140001fb7  mov     [rbp+arg_18], 5Fh ; '_'
0x140001fbe  mov     [rsp+50h+var_20], rcx
0x140001fc3  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x140001fca  lea     rcx, [rbp+arg_18]
0x140001fce  mov     [rbp+var_10], rax
0x140001fd2  mov     [rsp+50h+var_28], rcx
0x140001fd7  lea     rdx, dword_14000A6FC
0x140001fde  lea     rcx, [rbp+var_10]
0x140001fe2  mov     [rsp+50h+var_30], rcx
0x140001fe7  jmp     loc_140001EE9
0x140001fec  mov     ebx, r12d
0x140001fef  movzx   eax, bx
0x140001ff2  lea     r8, aWsX; "%ws.%x"
0x140001ff9  mov     r9, rdi
0x140001ffc  mov     dword ptr [rsp+50h+var_30], eax
0x140002000  mov     rdx, r15; BufferCount
0x140002003  mov     rcx, r14; Buffer
0x140002006  call    cs:__imp_swprintf_s
0x14000200c  mov     rcx, r14; lpFileName
0x14000200f  call    cs:__imp_DeleteFileW
0x140002015  mov     rdx, r14; lpNewFileName
0x140002018  mov     rcx, rdi; lpExistingFileName
0x14000201b  call    cs:__imp_MoveFileW
0x140002021  test    eax, eax
0x140002023  jnz     short loc_140002055
0x140002025  add     bx, r13w
0x140002029  mov     eax, 0FFFFh
0x14000202e  cmp     bx, ax
0x140002031  jb      short loc_140001FEF
0x140002033  mov     rcx, r14; P
0x140002036  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x14000203b  xor     eax, eax
0x14000203d  mov     rbx, [rsp+50h+arg_0]
0x140002045  add     rsp, 50h
0x140002049  pop     r15
0x14000204b  pop     r14
0x14000204d  pop     r13
0x14000204f  pop     r12
0x140002051  pop     rdi
0x140002052  pop     rsi
0x140002053  pop     rbp
0x140002054  retn
0x140002055  xor     edx, edx; lpNewFileName
0x140002057  mov     rcx, r14; lpExistingFileName
0x14000205a  lea     r8d, [rdx+4]; dwFlags
0x14000205e  call    cs:__imp_MoveFileExW
0x140002064  xor     r8d, r8d; bFailIfExists
0x140002067  mov     rdx, rdi; lpNewFileName
0x14000206a  mov     rcx, rsi; lpExistingFileName
0x14000206d  call    cs:__imp_CopyFileW
0x140002073  test    eax, eax
0x140002075  jnz     short loc_140002033
0x140002077  call    cs:__imp_GetLastError
0x14000207d  mov     ebx, eax
0x14000207f  mov     eax, cs:dword_14000E000
0x140002085  cmp     eax, 2
0x140002088  jbe     short loc_1400020E9
0x14000208a  mov     rcx, cs:qword_14000E018
0x140002091  mov     edx, 800h
0x140002096  mov     rax, cs:qword_14000E010
0x14000209d  test    rdx, rax
0x1400020a0  jz      short loc_1400020E9
0x1400020a2  mov     rax, rcx
0x1400020a5  and     rax, rdx
0x1400020a8  cmp     rax, rcx
0x1400020ab  jnz     short loc_1400020E9
0x1400020ad  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x1400020b4  mov     [rbp+arg_10], ebx
0x1400020b7  mov     [rbp+var_10], rax
0x1400020bb  lea     rdx, dword_14000A6BC
0x1400020c2  lea     rax, [rbp+arg_10]
0x1400020c6  mov     [rbp+arg_18], 69h ; 'i'
0x1400020cd  mov     [rsp+50h+var_20], rax
0x1400020d2  lea     rax, [rbp+arg_18]
0x1400020d6  mov     [rsp+50h+var_28], rax
0x1400020db  lea     rax, [rbp+var_10]
0x1400020df  mov     [rsp+50h+var_30], rax
0x1400020e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400020e9  test    ebx, ebx
0x1400020eb  jnz     short loc_1400020F7
0x1400020ed  mov     ebx, 8000FFFFh
0x1400020f2  jmp     loc_140001EF1
0x1400020f7  jle     loc_140001EF1
0x1400020fd  movzx   ebx, bx
0x140002100  or      ebx, 80070000h
0x140002106  jmp     loc_140001EF1
0x14000210b  cmp     ebx, 5
0x14000210e  jnz     short loc_140002172
0x140002110  mov     rdx, rdi; lpFileName
0x140002113  mov     rcx, rsi; lpExistingFileName
0x140002116  call    ?ModifySystemFile@@YAJPEBG0@Z; ModifySystemFile(ushort const *,ushort const *)
0x14000211b  mov     ebx, eax
0x14000211d  test    eax, eax
0x14000211f  jns     loc_14000203B
0x140002125  mov     ecx, cs:dword_14000E000
0x14000212b  cmp     ecx, 2
0x14000212e  jbe     loc_140001EF1
0x140002134  mov     r8, cs:qword_14000E018
0x14000213b  mov     edx, 800h
0x140002140  mov     rcx, cs:qword_14000E010
0x140002147  test    rdx, rcx
0x14000214a  jz      loc_140001EF1
0x140002150  mov     rax, r8
0x140002153  and     rax, rdx
0x140002156  cmp     rax, r8
0x140002159  jnz     loc_140001EF1
0x14000215f  mov     [rbp+arg_18], 72h ; 'r'
0x140002166  lea     rdx, byte_14000A67F
0x14000216d  jmp     loc_140001EC3
0x140002172  test    ebx, ebx
0x140002174  jz      loc_140001EF1
0x14000217a  mov     eax, cs:dword_14000E000
0x140002180  cmp     eax, 2
0x140002183  jbe     short loc_1400021E4
0x140002185  mov     rcx, cs:qword_14000E018
0x14000218c  mov     edx, 800h
0x140002191  mov     rax, cs:qword_14000E010
0x140002198  test    rdx, rax
0x14000219b  jz      short loc_1400021E4
0x14000219d  mov     rax, rcx
0x1400021a0  and     rax, rdx
0x1400021a3  cmp     rax, rcx
0x1400021a6  jnz     short loc_1400021E4
0x1400021a8  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x1400021af  mov     [rbp+arg_10], ebx
0x1400021b2  mov     [rbp+var_10], rax
0x1400021b6  lea     rdx, byte_14000A63F
0x1400021bd  lea     rax, [rbp+arg_10]
0x1400021c1  mov     [rbp+arg_18], 76h ; 'v'
0x1400021c8  mov     [rsp+50h+var_20], rax
0x1400021cd  lea     rax, [rbp+arg_18]
0x1400021d1  mov     [rsp+50h+var_28], rax
0x1400021d6  lea     rax, [rbp+var_10]
0x1400021da  mov     [rsp+50h+var_30], rax
0x1400021df  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400021e4  test    ebx, ebx
0x1400021e6  jmp     loc_1400020F7
```
