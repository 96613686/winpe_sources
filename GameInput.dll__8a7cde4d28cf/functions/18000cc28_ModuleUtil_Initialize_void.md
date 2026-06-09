# ModuleUtil::Initialize(void)

- ea: `0x18000cc28`
- end: `0x18000cfe8`
- name: `?Initialize@ModuleUtil@@YAJXZ`
- size: `960`
- prototype: `__int64 __fastcall(ModuleUtil *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d56c`

## callees

- `0x180001304`
- `0x18000c11c`
- `0x18000cc28`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18000cc51`
- `ntdll!NtQuerySystemInformation` at `0x18000cccb`
- `ntdll!NtQuerySystemInformation` at `0x18000cc51`
- `ntdll!NtQuerySystemInformation` at `0x18000cccb`
- `ntdll!RtlAllocateHeap` at `0x18000cc96`
- `ntdll!RtlAllocateHeap` at `0x18000cecc`
- `ntdll!RtlAllocateHeap` at `0x18000cc96`
- `ntdll!RtlAllocateHeap` at `0x18000cecc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ce97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ce97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cf2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cfc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cf2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cfc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cddd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cddd`

## string_xrefs

- `0x18000cd10`: `onecore\xbox\gameinput\common\GameInputModuleUtil.cpp`
- `0x18000cd98`: `onecore\xbox\gameinput\common\GameInputModuleUtil.cpp`
- `0x18000ce30`: `onecore\xbox\gameinput\common\GameInputModuleUtil.cpp`
- `0x18000cf7e`: `onecore\xbox\gameinput\common\GameInputModuleUtil.cpp`

## pseudocode

```c
__int64 __fastcall ModuleUtil::Initialize(ModuleUtil *this)
{
  char *v1; // rbx
  const struct std::nothrow_t *v2; // rdx
  NTSTATUS v3; // edi
  int v4; // r8d
  int v5; // r9d
  ULONG v6; // edi
  const struct std::nothrow_t *v7; // rdx
  char *Heap; // rsi
  int v9; // r8d
  int v10; // r9d
  unsigned int v11; // edi
  DWORD CurrentProcessId; // eax
  int v14; // r8d
  int v15; // r9d
  const struct std::nothrow_t *v16; // rdx
  unsigned __int64 v17; // rdi
  unsigned int v18; // esi
  char *v19; // r14
  int v20; // r15d
  _QWORD *v21; // rax
  int v22; // r8d
  int v23; // r9d
  __int64 *v24; // rdx
  __int64 **v25; // rcx
  const struct std::nothrow_t *v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  ULONG ReturnLength; // [rsp+80h] [rbp+38h] BYREF
  int v29; // [rsp+88h] [rbp+40h] BYREF
  int v30; // [rsp+90h] [rbp+48h] BYREF
  const char *v31; // [rsp+98h] [rbp+50h] BYREF

  v1 = 0;
  ReturnLength = 0;
  v3 = NtQuerySystemInformation(SystemProcessInformation, 0, 0, &ReturnLength);
  if ( v3 == -1073741820 )
  {
    while ( 1 )
    {
      if ( -1 - ReturnLength > 0x2000 )
        v6 = ReturnLength + 0x2000;
      else
        v6 = -1;
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      if ( v1 )
        operator delete(v1, v7);
      if ( !Heap )
        break;
      v1 = Heap;
      v3 = NtQuerySystemInformation(SystemProcessInformation, Heap, v6, &ReturnLength);
      if ( v3 != -1073741820 )
        goto LABEL_9;
    }
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
    {
      v29 = -2147024882;
      v31 = "onecore\\xbox\\gameinput\\common\\GameInputModuleUtil.cpp";
      v30 = 165;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&word_180059DB6,
        v9,
        v10,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
    return 2147942414LL;
  }
LABEL_9:
  if ( v3 >= 0 )
  {
    CurrentProcessId = GetCurrentProcessId();
    v16 = (const struct std::nothrow_t *)ReturnLength;
    v17 = 0;
    if ( ReturnLength )
    {
      while ( *(_DWORD *)&v1[v17 + 80] != CurrentProcessId )
      {
        v17 += *(unsigned int *)&v1[v17];
        if ( v17 >= ReturnLength )
          goto LABEL_24;
      }
      AcquireSRWLockExclusive(&SRWLock);
      v18 = 0;
      v19 = &v1[v17 + 256];
      if ( *(_DWORD *)&v1[v17 + 4] )
      {
        while ( 1 )
        {
          v20 = *((_DWORD *)v19 + 12);
          v21 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u);
          if ( !v21 )
            break;
          *(_OWORD *)v21 = 0;
          v21[2] = 0;
          *((_DWORD *)v21 + 4) = v20;
          v24 = &qword_180069920[3 * (v20 & 7)];
          v25 = (__int64 **)v24[1];
          if ( *v25 != v24 )
            __fastfail(3u);
          *v21 = v24;
          v19 += 80;
          v21[1] = v25;
          ++v18;
          *v25 = v21;
          ++*((_DWORD *)v24 + 4);
          v24[1] = (__int64)v21;
          if ( v18 >= *(_DWORD *)&v1[v17 + 4] )
            goto LABEL_35;
        }
        if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
        {
          v29 = -2147024882;
          v31 = "onecore\\xbox\\gameinput\\common\\GameInputModuleUtil.cpp";
          v30 = 191;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069018,
            (unsigned int)byte_180059F53,
            v22,
            v23,
            (__int64)&v31,
            (__int64)&v30,
            (__int64)&v29);
        }
        ReleaseSRWLockExclusive(&SRWLock);
        if ( v1 )
          operator delete(v1, v27);
        return 2147942414LL;
      }
LABEL_35:
      ReleaseSRWLockExclusive(&SRWLock);
      if ( v1 )
        operator delete(v1, v26);
      return 0;
    }
    else
    {
LABEL_24:
      if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
      {
        v29 = -2147418113;
        v31 = "onecore\\xbox\\gameinput\\common\\GameInputModuleUtil.cpp";
        v30 = 205;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018,
          (unsigned int)byte_180059FA3,
          v14,
          v15,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v29);
      }
      if ( v1 )
        operator delete(v1, v16);
      return 2147549183LL;
    }
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
    {
      v29 = v3;
      v31 = "onecore\\xbox\\gameinput\\common\\GameInputModuleUtil.cpp";
      v30 = 169;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_18005A0E9,
        v4,
        v5,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
    v11 = v3 | 0x10000000;
    if ( v1 )
      operator delete(v1, v2);
    return v11;
  }
}

```

## disassembly

```asm
0x18000cc28  push    rbp
0x18000cc2a  push    rbx
0x18000cc2b  push    rsi
0x18000cc2c  push    rdi
0x18000cc2d  push    r14
0x18000cc2f  push    r15
0x18000cc31  mov     rbp, rsp
0x18000cc34  sub     rsp, 48h
0x18000cc38  xor     ebx, ebx
0x18000cc3a  mov     [rbp+ReturnLength], 0
0x18000cc41  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18000cc45  xor     r8d, r8d; SystemInformationLength
0x18000cc48  xor     edx, edx; SystemInformation
0x18000cc4a  lea     r15d, [rbx+5]
0x18000cc4e  mov     ecx, r15d; SystemInformationClass
0x18000cc51  call    cs:__imp_NtQuerySystemInformation
0x18000cc58  nop     dword ptr [rax+rax+00h]
0x18000cc5d  mov     edi, eax
0x18000cc5f  cmp     eax, 0C0000004h
0x18000cc64  jnz     short loc_18000CCE0
0x18000cc66  or      r14d, 0FFFFFFFFh
0x18000cc6a  mov     edi, [rbp+ReturnLength]
0x18000cc6d  mov     eax, r14d
0x18000cc70  sub     eax, edi
0x18000cc72  cmp     eax, 2000h
0x18000cc77  ja      short loc_18000CC7E
0x18000cc79  mov     edi, r14d
0x18000cc7c  jmp     short loc_18000CC84
0x18000cc7e  add     edi, 2000h
0x18000cc84  mov     rcx, gs:60h
0x18000cc8d  xor     edx, edx; Flags
0x18000cc8f  mov     r8d, edi; Size
0x18000cc92  mov     rcx, [rcx+30h]; HeapHandle
0x18000cc96  call    cs:__imp_RtlAllocateHeap
0x18000cc9d  nop     dword ptr [rax+rax+00h]
0x18000cca2  mov     rsi, rax
0x18000cca5  test    rbx, rbx
0x18000cca8  jz      short loc_18000CCB2
0x18000ccaa  mov     rcx, rbx; P
0x18000ccad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ccb2  test    rsi, rsi
0x18000ccb5  jz      loc_18000CD64
0x18000ccbb  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18000ccbf  mov     r8d, edi; SystemInformationLength
0x18000ccc2  mov     rdx, rsi; SystemInformation
0x18000ccc5  mov     ecx, r15d; SystemInformationClass
0x18000ccc8  mov     rbx, rsi
0x18000cccb  call    cs:__imp_NtQuerySystemInformation
0x18000ccd2  nop     dword ptr [rax+rax+00h]
0x18000ccd7  mov     edi, eax
0x18000ccd9  cmp     eax, 0C0000004h
0x18000ccde  jz      short loc_18000CC6A
0x18000cce0  test    edi, edi
0x18000cce2  jns     loc_18000CDDD
0x18000cce8  mov     eax, cs:dword_180069000
0x18000ccee  cmp     eax, 2
0x18000ccf1  jbe     short loc_18000CD4C
0x18000ccf3  mov     rcx, cs:qword_180069018
0x18000ccfa  mov     rax, cs:qword_180069010
0x18000cd01  test    al, 2
0x18000cd03  jz      short loc_18000CD4C
0x18000cd05  mov     rax, rcx
0x18000cd08  and     eax, 2
0x18000cd0b  cmp     rax, rcx
0x18000cd0e  jnz     short loc_18000CD4C
0x18000cd10  lea     rax, aOnecoreXboxGam_29; "onecore\\xbox\\gameinput\\common\\GameI"...
0x18000cd17  mov     [rbp+arg_8], edi
0x18000cd1a  mov     [rbp+arg_18], rax
0x18000cd1e  lea     rdx, byte_18005A0E9
0x18000cd25  lea     rax, [rbp+arg_8]
0x18000cd29  mov     [rbp+arg_10], 0A9h
0x18000cd30  mov     [rsp+48h+var_18], rax
0x18000cd35  lea     rax, [rbp+arg_10]
0x18000cd39  mov     [rsp+48h+var_20], rax
0x18000cd3e  lea     rax, [rbp+arg_18]
0x18000cd42  mov     [rsp+48h+var_28], rax
0x18000cd47  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000cd4c  bts     edi, 1Ch
0x18000cd50  test    rbx, rbx
0x18000cd53  jz      short loc_18000CD5D
0x18000cd55  mov     rcx, rbx; P
0x18000cd58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cd5d  mov     eax, edi
0x18000cd5f  jmp     loc_18000CE82
0x18000cd64  mov     eax, cs:dword_180069000
0x18000cd6a  cmp     eax, 2
0x18000cd6d  jbe     loc_18000CFDE
0x18000cd73  mov     rcx, cs:qword_180069018
0x18000cd7a  mov     rax, cs:qword_180069010
0x18000cd81  test    al, 2
0x18000cd83  jz      loc_18000CFDE
0x18000cd89  mov     rax, rcx
0x18000cd8c  and     eax, 2
0x18000cd8f  cmp     rax, rcx
0x18000cd92  jnz     loc_18000CFDE
0x18000cd98  lea     rax, aOnecoreXboxGam_29; "onecore\\xbox\\gameinput\\common\\GameI"...
0x18000cd9f  mov     [rbp+arg_8], 8007000Eh
0x18000cda6  mov     [rbp+arg_18], rax
0x18000cdaa  lea     rdx, word_180059DB6
0x18000cdb1  lea     rax, [rbp+arg_8]
0x18000cdb5  mov     [rbp+arg_10], 0A5h
0x18000cdbc  mov     [rsp+48h+var_18], rax
0x18000cdc1  lea     rax, [rbp+arg_10]
0x18000cdc5  mov     [rsp+48h+var_20], rax
0x18000cdca  lea     rax, [rbp+arg_18]
0x18000cdce  mov     [rsp+48h+var_28], rax
0x18000cdd3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000cdd8  jmp     loc_18000CFDE
0x18000cddd  call    cs:__imp_GetCurrentProcessId
0x18000cde4  nop     dword ptr [rax+rax+00h]
0x18000cde9  mov     edx, [rbp+ReturnLength]
0x18000cdec  xor     edi, edi
0x18000cdee  test    rdx, rdx
0x18000cdf1  jz      short loc_18000CE08
0x18000cdf3  cmp     [rdi+rbx+50h], eax
0x18000cdf7  jz      loc_18000CE90
0x18000cdfd  mov     ecx, [rdi+rbx]
0x18000ce00  add     rdi, rcx
0x18000ce03  cmp     rdi, rdx
0x18000ce06  jb      short loc_18000CDF3
0x18000ce08  mov     eax, cs:dword_180069000
0x18000ce0e  cmp     eax, 2
0x18000ce11  jbe     short loc_18000CE70
0x18000ce13  mov     rcx, cs:qword_180069018
0x18000ce1a  mov     rax, cs:qword_180069010
0x18000ce21  test    al, 2
0x18000ce23  jz      short loc_18000CE70
0x18000ce25  mov     rax, rcx
0x18000ce28  and     eax, 2
0x18000ce2b  cmp     rax, rcx
0x18000ce2e  jnz     short loc_18000CE70
0x18000ce30  lea     rax, aOnecoreXboxGam_29; "onecore\\xbox\\gameinput\\common\\GameI"...
0x18000ce37  mov     [rbp+arg_8], 8000FFFFh
0x18000ce3e  mov     [rbp+arg_18], rax
0x18000ce42  lea     rdx, byte_180059FA3
0x18000ce49  lea     rax, [rbp+arg_8]
0x18000ce4d  mov     [rbp+arg_10], 0CDh
0x18000ce54  mov     [rsp+48h+var_18], rax
0x18000ce59  lea     rax, [rbp+arg_10]
0x18000ce5d  mov     [rsp+48h+var_20], rax
0x18000ce62  lea     rax, [rbp+arg_18]
0x18000ce66  mov     [rsp+48h+var_28], rax
0x18000ce6b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ce70  test    rbx, rbx
0x18000ce73  jz      short loc_18000CE7D
0x18000ce75  mov     rcx, rbx; P
0x18000ce78  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ce7d  mov     eax, 8000FFFFh
0x18000ce82  add     rsp, 48h
0x18000ce86  pop     r15
0x18000ce88  pop     r14
0x18000ce8a  pop     rdi
0x18000ce8b  pop     rsi
0x18000ce8c  pop     rbx
0x18000ce8d  pop     rbp
0x18000ce8e  retn
0x18000ce90  lea     rcx, SRWLock; SRWLock
0x18000ce97  call    cs:__imp_AcquireSRWLockExclusive
0x18000ce9e  nop     dword ptr [rax+rax+00h]
0x18000cea3  lea     r14, [rbx+100h]
0x18000ceaa  xor     esi, esi
0x18000ceac  add     r14, rdi
0x18000ceaf  cmp     [rdi+rbx+4], esi
0x18000ceb3  jbe     short loc_18000CF28
0x18000ceb5  mov     rcx, gs:60h
0x18000cebe  xor     edx, edx; Flags
0x18000cec0  mov     r15d, [r14+30h]
0x18000cec4  mov     rcx, [rcx+30h]; HeapHandle
0x18000cec8  lea     r8d, [rdx+18h]; Size
0x18000cecc  call    cs:__imp_RtlAllocateHeap
0x18000ced3  nop     dword ptr [rax+rax+00h]
0x18000ced8  test    rax, rax
0x18000cedb  jz      short loc_18000CF56
0x18000cedd  xor     ecx, ecx
0x18000cedf  lea     rdx, qword_180069920
0x18000cee6  xorps   xmm0, xmm0
0x18000cee9  movups  xmmword ptr [rax], xmm0
0x18000ceec  mov     [rax+10h], rcx
0x18000cef0  mov     ecx, r15d
0x18000cef3  and     ecx, 7
0x18000cef6  mov     [rax+10h], r15d
0x18000cefa  lea     rcx, [rcx+rcx*2]
0x18000cefe  lea     rdx, [rdx+rcx*8]
0x18000cf02  mov     rcx, [rdx+8]
0x18000cf06  cmp     [rcx], rdx
0x18000cf09  jnz     short loc_18000CF4F
0x18000cf0b  mov     [rax], rdx
0x18000cf0e  add     r14, 50h ; 'P'
0x18000cf12  mov     [rax+8], rcx
0x18000cf16  inc     esi
0x18000cf18  mov     [rcx], rax
0x18000cf1b  inc     dword ptr [rdx+10h]
0x18000cf1e  mov     [rdx+8], rax
0x18000cf22  cmp     esi, [rdi+rbx+4]
0x18000cf26  jb      short loc_18000CEB5
0x18000cf28  lea     rcx, SRWLock; SRWLock
0x18000cf2f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cf36  nop     dword ptr [rax+rax+00h]
0x18000cf3b  test    rbx, rbx
0x18000cf3e  jz      short loc_18000CF48
0x18000cf40  mov     rcx, rbx; P
0x18000cf43  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cf48  xor     eax, eax
0x18000cf4a  jmp     loc_18000CE82
0x18000cf4f  mov     ecx, 3
0x18000cf54  int     29h; Win8: RtlFailFast(ecx)
0x18000cf56  mov     eax, cs:dword_180069000
0x18000cf5c  cmp     eax, 2
0x18000cf5f  jbe     short loc_18000CFBE
0x18000cf61  mov     rcx, cs:qword_180069018
0x18000cf68  mov     rax, cs:qword_180069010
0x18000cf6f  test    al, 2
0x18000cf71  jz      short loc_18000CFBE
0x18000cf73  mov     rax, rcx
0x18000cf76  and     eax, 2
0x18000cf79  cmp     rax, rcx
0x18000cf7c  jnz     short loc_18000CFBE
0x18000cf7e  lea     rax, aOnecoreXboxGam_29; "onecore\\xbox\\gameinput\\common\\GameI"...
0x18000cf85  mov     [rbp+arg_8], 8007000Eh
0x18000cf8c  mov     [rbp+arg_18], rax
0x18000cf90  lea     rdx, [rbp+arg_18]
0x18000cf94  lea     rax, [rbp+arg_8]
0x18000cf98  mov     [rbp+arg_10], 0BFh
0x18000cf9f  mov     [rsp+48h+var_18], rax
0x18000cfa4  lea     rax, [rbp+arg_10]
0x18000cfa8  mov     [rsp+48h+var_20], rax
0x18000cfad  mov     [rsp+48h+var_28], rdx
0x18000cfb2  lea     rdx, byte_180059F53
0x18000cfb9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000cfbe  lea     rcx, SRWLock; SRWLock
0x18000cfc5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cfcc  nop     dword ptr [rax+rax+00h]
0x18000cfd1  test    rbx, rbx
0x18000cfd4  jz      short loc_18000CFDE
0x18000cfd6  mov     rcx, rbx; P
0x18000cfd9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cfde  mov     eax, 8007000Eh
0x18000cfe3  jmp     loc_18000CE82
```
