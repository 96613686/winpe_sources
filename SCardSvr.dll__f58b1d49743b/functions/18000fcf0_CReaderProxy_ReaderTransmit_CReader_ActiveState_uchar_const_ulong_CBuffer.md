# CReaderProxy::ReaderTransmit(CReader::ActiveState *,uchar const *,ulong,CBuffer &)

- ea: `0x18000fcf0`
- end: `0x18001003b`
- name: `?ReaderTransmit@CReaderProxy@@QEAAXPEAUActiveState@CReader@@PEBEKAEAVCBuffer@@@Z`
- size: `843`
- prototype: `void __fastcall(CReaderProxy *this, struct CReader::ActiveState *, const unsigned __int8 *, unsigned int, const WCHAR **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180015790`

## callees

- `0x180006700`
- `0x180006ad0`
- `0x18000c640`
- `0x18000d9c0`
- `0x18000f800`
- `0x18000fb50`
- `0x18000fcf0`
- `0x180010670`
- `0x180010af0`
- `0x180012380`
- `0x180023168`
- `0x180023174`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fdaa`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fdaa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000feee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000feee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010019`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fd58`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ff77`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000fd58`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ff77`

## pseudocode

```c
void __fastcall CReaderProxy::ReaderTransmit(
        CReaderProxy *this,
        struct CReader::ActiveState *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        const WCHAR **a5)
{
  __int64 v9; // rbx
  _DWORD *v10; // rdi
  struct CBuffer *v11; // rsi
  const WCHAR *v12; // rax
  int v13; // eax
  int v14; // ebp
  void *v15; // r14
  void *v16; // rcx
  CReader *v17; // rdi
  _QWORD v19[2]; // [rsp+40h] [rbp-58h] BYREF
  CReader *v20; // [rsp+50h] [rbp-48h] BYREF
  char v21; // [rsp+5Ch] [rbp-3Ch]
  __int64 pExceptionObject; // [rsp+A0h] [rbp+8h] BYREF

  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 1))((char *)this + 8, 0, 0);
  if ( !*(_QWORD *)this )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
    LODWORD(pExceptionObject) = -2146435049;
    throw (ulong *)&pExceptionObject;
  }
  v9 = *(_QWORD *)this + 512LL;
  v19[1] = v9;
  pExceptionObject = v9;
  (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v9)(v9, 0, 0);
  if ( *(LPVOID *)(v9 + 104) == TlsGetValue(dwTlsIndex) )
  {
    ++*(_DWORD *)(v9 + 56);
    CAccessLock::UnsignalNoReaders((CAccessLock *)v9);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    while ( 1 )
    {
      CAccessLock::WaitOnWriters((CAccessLock *)v9);
      v19[0] = v9;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v9)(v9, 0, 0);
      if ( !*(_DWORD *)(v9 + 60) || *(LPVOID *)(v9 + 104) == TlsGetValue(dwTlsIndex) )
        break;
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)v19);
    }
    ++*(_DWORD *)(v9 + 56);
    if ( !ResetEvent(*(HANDLE *)(v9 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1) + 8LL))((char *)this + 8);
  v10 = *(_DWORD **)this;
  CLatchReader::CLatchReader((CLatchReader *)&v20, *(struct CReader **)this, a2);
  v11 = (struct CBuffer *)a5;
  LODWORD(pExceptionObject) = *((_DWORD *)a5 + 5);
  if ( (_DWORD)pExceptionObject )
    v12 = a5[1];
  else
    v12 = &Data;
  v13 = (*(__int64 (__fastcall **)(_DWORD *, __int64, const unsigned __int8 *, _QWORD, const WCHAR *, __int64 *, int))(*(_QWORD *)v10 + 64LL))(
          v10,
          3211284,
          a3,
          a4,
          v12,
          &pExceptionObject,
          1);
  if ( v13 )
  {
    LODWORD(v19[0]) = v13;
    throw (ulong *)v19;
  }
  v14 = pExceptionObject;
  if ( *((_DWORD *)v11 + 5) < (unsigned int)pExceptionObject )
  {
    v15 = operator new[]((unsigned int)pExceptionObject);
    if ( !v15 )
    {
      LODWORD(v19[0]) = 14;
      throw (ulong *)v19;
    }
    v16 = (void *)*((_QWORD *)v11 + 1);
    if ( v16 )
      operator delete[](v16);
    *((_QWORD *)v11 + 1) = v15;
    *((_DWORD *)v11 + 5) = v14;
  }
  *((_DWORD *)v11 + 4) = v14;
  ++v10[52];
  v17 = v20;
  if ( v20 )
  {
    if ( !(unsigned int)CReader::InitFailed(v20) )
    {
      CMutex::Share((CReader *)((char *)v17 + 328));
      CMutex::Share((CReader *)((char *)v17 + 240));
      if ( v21 )
      {
        if ( (unsigned int)CMutex::IsGrabbed((CReader *)((char *)v17 + 240)) )
          CReader::TransactionTimeoutStart(v17);
        else
          CReader::TransactionTimeoutStop(v17);
      }
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9) )
  {
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v9)(v9, 0, 0);
    if ( (*(_DWORD *)(v9 + 56))-- == 1 && !SetEvent(*(HANDLE *)(v9 + 72)) )
    {
      LODWORD(pExceptionObject) = GetLastError();
      throw (ulong *)&pExceptionObject;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  }
}

```

## disassembly

```asm
0x18000fcf0  push    rbx
0x18000fcf2  push    rbp
0x18000fcf3  push    rsi
0x18000fcf4  push    rdi
0x18000fcf5  push    r14
0x18000fcf7  push    r15
0x18000fcf9  sub     rsp, 68h
0x18000fcfd  mov     r14d, r9d
0x18000fd00  mov     r15, r8
0x18000fd03  mov     rbp, rdx
0x18000fd06  mov     rsi, rcx
0x18000fd09  mov     rax, [rcx+8]
0x18000fd0d  xor     r8d, r8d
0x18000fd10  xor     edx, edx
0x18000fd12  add     rcx, 8
0x18000fd16  mov     rax, [rax]
0x18000fd19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd1e  mov     rbx, [rsi]
0x18000fd21  test    rbx, rbx
0x18000fd24  jz      loc_18000FF96
0x18000fd2a  add     rbx, 200h
0x18000fd31  mov     [rsp+98h+var_50], rbx
0x18000fd36  mov     [rsp+98h+pExceptionObject], rbx
0x18000fd3e  mov     rax, [rbx]
0x18000fd41  xor     r8d, r8d
0x18000fd44  xor     edx, edx
0x18000fd46  mov     rcx, rbx
0x18000fd49  mov     rax, [rax]
0x18000fd4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd51  nop
0x18000fd52  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000fd58  call    cs:__imp_TlsGetValue
0x18000fd5e  cmp     [rbx+68h], rax
0x18000fd62  jz      loc_18000FF46
0x18000fd68  mov     rax, [rbx]
0x18000fd6b  mov     rcx, rbx
0x18000fd6e  mov     rax, [rax+8]
0x18000fd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd77  nop
0x18000fd78  mov     rcx, rbx; this
0x18000fd7b  call    ?WaitOnWriters@CAccessLock@@IEAAXXZ; CAccessLock::WaitOnWriters(void)
0x18000fd80  mov     [rsp+98h+var_58], rbx
0x18000fd85  mov     rax, [rbx]
0x18000fd88  xor     r8d, r8d
0x18000fd8b  xor     edx, edx
0x18000fd8d  mov     rcx, rbx
0x18000fd90  mov     rax, [rax]
0x18000fd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd98  nop
0x18000fd99  cmp     dword ptr [rbx+3Ch], 0
0x18000fd9d  jnz     loc_18000FF71
0x18000fda3  inc     dword ptr [rbx+38h]
0x18000fda6  mov     rcx, [rbx+48h]; hEvent
0x18000fdaa  call    cs:__imp_ResetEvent
0x18000fdb0  test    eax, eax
0x18000fdb2  jz      loc_18000FFC7
0x18000fdb8  mov     rax, [rbx]
0x18000fdbb  mov     rcx, rbx
0x18000fdbe  mov     rax, [rax+8]
0x18000fdc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdc7  nop
0x18000fdc8  mov     rax, [rsi+8]
0x18000fdcc  lea     rcx, [rsi+8]
0x18000fdd0  mov     rax, [rax+8]
0x18000fdd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd9  mov     rdi, [rsi]
0x18000fddc  mov     r8, rbp; struct CReader::ActiveState *
0x18000fddf  mov     rdx, rdi; struct CReader *
0x18000fde2  lea     rcx, [rsp+98h+var_48]; this
0x18000fde7  call    ??0CLatchReader@@QEAA@PEAVCReader@@PEBUActiveState@1@@Z; CLatchReader::CLatchReader(CReader *,CReader::ActiveState const *)
0x18000fdec  nop
0x18000fded  mov     rsi, [rsp+98h+arg_20]
0x18000fdf5  mov     ecx, [rsi+14h]
0x18000fdf8  mov     dword ptr [rsp+98h+pExceptionObject], ecx
0x18000fdff  mov     rax, [rdi]
0x18000fe02  mov     r10, [rax+40h]
0x18000fe06  test    ecx, ecx
0x18000fe08  jnz     loc_18000FF19
0x18000fe0e  lea     rax, Data
0x18000fe15  mov     [rsp+98h+var_68], 1
0x18000fe1d  lea     rcx, [rsp+98h+pExceptionObject]
0x18000fe25  mov     [rsp+98h+var_70], rcx
0x18000fe2a  mov     [rsp+98h+var_78], rax
0x18000fe2f  mov     r9d, r14d
0x18000fe32  mov     r8, r15
0x18000fe35  mov     edx, 310014h
0x18000fe3a  mov     rcx, rdi
0x18000fe3d  mov     rax, r10
0x18000fe40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe45  test    eax, eax
0x18000fe47  jnz     loc_18000FFE9
0x18000fe4d  mov     ebp, dword ptr [rsp+98h+pExceptionObject]
0x18000fe54  cmp     [rsi+14h], ebp
0x18000fe57  jnb     short loc_18000FE80
0x18000fe59  mov     ecx, ebp; unsigned __int64
0x18000fe5b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000fe60  mov     r14, rax
0x18000fe63  test    rax, rax
0x18000fe66  jz      loc_18000FFFF
0x18000fe6c  mov     rcx, [rsi+8]; Block
0x18000fe70  test    rcx, rcx
0x18000fe73  jnz     loc_18000FF67
0x18000fe79  mov     [rsi+8], r14
0x18000fe7d  mov     [rsi+14h], ebp
0x18000fe80  mov     [rsi+10h], ebp
0x18000fe83  inc     dword ptr [rdi+0D0h]
0x18000fe89  mov     rdi, [rsp+98h+var_48]
0x18000fe8e  test    rdi, rdi
0x18000fe91  jz      short loc_18000FEBE
0x18000fe93  mov     rcx, rdi; this
0x18000fe96  call    ?InitFailed@CReader@@QEAAHXZ; CReader::InitFailed(void)
0x18000fe9b  test    eax, eax
0x18000fe9d  jnz     short loc_18000FEBE
0x18000fe9f  lea     rcx, [rdi+148h]; this
0x18000fea6  call    ?Share@CMutex@@QEAAHXZ; CMutex::Share(void)
0x18000feab  lea     rcx, [rdi+0F0h]; this
0x18000feb2  call    ?Share@CMutex@@QEAAHXZ; CMutex::Share(void)
0x18000feb7  cmp     [rsp+98h+var_3C], 0
0x18000febc  jnz     short loc_18000FF22
0x18000febe  mov     rax, [rbx]
0x18000fec1  mov     rcx, rbx
0x18000fec4  mov     rax, [rax+10h]
0x18000fec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fecd  test    eax, eax
0x18000fecf  jnz     short loc_18000FF0C
0x18000fed1  mov     rax, [rbx]
0x18000fed4  xor     r8d, r8d
0x18000fed7  xor     edx, edx
0x18000fed9  mov     rcx, rbx
0x18000fedc  mov     rax, [rax]
0x18000fedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fee4  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x18000fee8  jnz     short loc_18000FEFC
0x18000feea  mov     rcx, [rbx+48h]; hEvent
0x18000feee  call    cs:__imp_SetEvent
0x18000fef4  test    eax, eax
0x18000fef6  jz      loc_180010019
0x18000fefc  mov     rax, [rbx]
0x18000feff  mov     rcx, rbx
0x18000ff02  mov     rax, [rax+8]
0x18000ff06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff0b  nop
0x18000ff0c  add     rsp, 68h
0x18000ff10  pop     r15
0x18000ff12  pop     r14
0x18000ff14  pop     rdi
0x18000ff15  pop     rsi
0x18000ff16  pop     rbp
0x18000ff17  pop     rbx
0x18000ff18  retn
0x18000ff19  mov     rax, [rsi+8]
0x18000ff1d  jmp     loc_18000FE15
0x18000ff22  lea     rcx, [rdi+0F0h]; this
0x18000ff29  call    ?IsGrabbed@CMutex@@QEAAHXZ; CMutex::IsGrabbed(void)
0x18000ff2e  mov     rcx, rdi; this
0x18000ff31  test    eax, eax
0x18000ff33  jnz     short loc_18000FF3C
0x18000ff35  call    ?TransactionTimeoutStop@CReader@@IEAAXXZ; CReader::TransactionTimeoutStop(void)
0x18000ff3a  jmp     short loc_18000FEBE
0x18000ff3c  call    ?TransactionTimeoutStart@CReader@@IEAAXXZ; CReader::TransactionTimeoutStart(void)
0x18000ff41  jmp     loc_18000FEBE
0x18000ff46  inc     dword ptr [rbx+38h]
0x18000ff49  mov     rcx, rbx; this
0x18000ff4c  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000ff51  nop
0x18000ff52  mov     rax, [rbx]
0x18000ff55  mov     rcx, rbx
0x18000ff58  mov     rax, [rax+8]
0x18000ff5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff61  nop
0x18000ff62  jmp     loc_18000FDC8
0x18000ff67  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ff6c  jmp     loc_18000FE79
0x18000ff71  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000ff77  call    cs:__imp_TlsGetValue
0x18000ff7d  cmp     [rbx+68h], rax
0x18000ff81  jz      loc_18000FDA3
0x18000ff87  lea     rcx, [rsp+98h+var_58]; this
0x18000ff8c  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18000ff91  jmp     loc_18000FD78
0x18000ff96  mov     rax, [rsi+8]
0x18000ff9a  lea     rcx, [rsi+8]
0x18000ff9e  mov     rax, [rax+8]
0x18000ffa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffa7  mov     dword ptr [rsp+98h+pExceptionObject], 80100017h
0x18000ffb2  lea     rdx, _TI1K; pThrowInfo
0x18000ffb9  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000ffc1  call    _CxxThrowException_0
0x18000ffc7  call    cs:__imp_GetLastError
0x18000ffcd  mov     dword ptr [rsp+98h+pExceptionObject], eax
0x18000ffd4  lea     rdx, _TI1K; pThrowInfo
0x18000ffdb  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000ffe3  call    _CxxThrowException_0
0x18000ffe9  mov     dword ptr [rsp+98h+var_58], eax
0x18000ffed  lea     rdx, _TI1K; pThrowInfo
0x18000fff4  lea     rcx, [rsp+98h+var_58]; pExceptionObject
0x18000fff9  call    _CxxThrowException_0
0x18000ffff  mov     dword ptr [rsp+98h+var_58], 0Eh
0x180010007  lea     rdx, _TI1K; pThrowInfo
0x18001000e  lea     rcx, [rsp+98h+var_58]; pExceptionObject
0x180010013  call    _CxxThrowException_0
0x180010019  call    cs:__imp_GetLastError
0x18001001f  mov     dword ptr [rsp+98h+pExceptionObject], eax
0x180010026  lea     rdx, _TI1K; pThrowInfo
0x18001002d  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180010035  call    _CxxThrowException_0
```
