# CReader::LatchReader(CReader::ActiveState const *,bool *)

- ea: `0x1800067a0`
- end: `0x180006ac8`
- name: `?LatchReader@CReader@@QEAAXPEBUActiveState@1@PEA_N@Z`
- size: `808`
- prototype: `void __fastcall(CReader *__hidden this, const struct CReader::ActiveState *, bool *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180001950`
- `0x180006700`

## callees

- `0x1800067a0`
- `0x18000c640`
- `0x18000d190`
- `0x18000ecb0`
- `0x18000fb50`
- `0x180010390`
- `0x180012380`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180006841`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180006841`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800068ca`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800068ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a7f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800067ef`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800068ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800069c2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800067ef`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800068ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800069c2`

## pseudocode

```c
void __fastcall CReader::LatchReader(CReader *this, const struct CReader::ActiveState *a2, bool *a3)
{
  char *v6; // rbx
  int v7; // eax
  bool v8; // zf
  LPVOID Value; // r14
  LPVOID v10; // r15
  ulong pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  ulong v12; // [rsp+24h] [rbp-44h] BYREF
  ulong v13; // [rsp+28h] [rbp-40h] BYREF
  ulong v14; // [rsp+2Ch] [rbp-3Ch] BYREF
  ulong v15; // [rsp+30h] [rbp-38h] BYREF
  ulong v16; // [rsp+34h] [rbp-34h] BYREF
  ulong LastError; // [rsp+38h] [rbp-30h] BYREF
  char *v18; // [rsp+78h] [rbp+10h] BYREF
  char *v19; // [rsp+88h] [rbp+20h]

  if ( a2 )
  {
    v6 = (char *)this + 56;
    v19 = (char *)this + 56;
    v18 = (char *)this + 56;
    (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 7))((char *)this + 56, 0, 0);
    if ( *((LPVOID *)v6 + 13) == TlsGetValue(dwTlsIndex) )
    {
      ++*((_DWORD *)v6 + 14);
      CAccessLock::UnsignalNoReaders((CAccessLock *)v6);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
    }
    else
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
      while ( 1 )
      {
        CAccessLock::WaitOnWriters((CAccessLock *)v6);
        v18 = v6;
        (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v6)(v6, 0, 0);
        if ( !*((_DWORD *)v6 + 15) || *((LPVOID *)v6 + 13) == TlsGetValue(dwTlsIndex) )
          break;
        COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v18);
      }
      ++*((_DWORD *)v6 + 14);
      if ( !ResetEvent(*((HANDLE *)v6 + 9)) )
      {
        pExceptionObject = GetLastError();
        throw &pExceptionObject;
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
    }
    v7 = *((_DWORD *)this + 48);
    if ( v7 != 7 )
    {
      switch ( v7 )
      {
        case 1:
        case 2:
        case 3:
        case 4:
        case 5:
        case 6:
          break;
        case 8:
          goto LABEL_11;
        case 9:
        case 10:
        case 11:
          v12 = -2146435049;
          throw &v12;
        default:
          v13 = -2146435071;
          throw &v13;
      }
    }
    if ( *(_DWORD *)a2 != *((_DWORD *)this + 49) )
    {
      v14 = -2146434967;
      throw &v14;
    }
    if ( *((_DWORD *)a2 + 1) != *((_DWORD *)this + 50) )
    {
      v15 = -2146434967;
      throw &v15;
    }
    if ( *((_DWORD *)a2 + 2) != *((_DWORD *)this + 51) )
    {
      v16 = -2146434968;
      throw &v16;
    }
LABEL_11:
    if ( !(*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) )
    {
      (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v6)(v6, 0, 0);
      v8 = (*((_DWORD *)v6 + 14))-- == 1;
      if ( v8 && !SetEvent(*((HANDLE *)v6 + 9)) )
      {
        LastError = GetLastError();
        throw &LastError;
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  CMutex::Grab((CReader *)((char *)this + 328));
  if ( a3 )
  {
    Value = TlsGetValue(dwTlsIndex);
    (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 30))((char *)this + 240, 0, 0);
    v10 = (LPVOID)*((_QWORD *)this + 37);
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 30) + 8LL))((char *)this + 240);
    *a3 = v10 == Value;
    if ( a2 )
    {
      if ( v10 == Value )
      {
        CReader::VerifyState(this);
        CReader::VerifyActive(this, a2);
      }
    }
  }
}

```

## disassembly

```asm
0x1800067a0  mov     rax, rsp
0x1800067a3  mov     [rax+18h], rbx
0x1800067a7  mov     [rax+8], rcx
0x1800067ab  push    rsi
0x1800067ac  push    rdi
0x1800067ad  push    r12
0x1800067af  push    r14
0x1800067b1  push    r15
0x1800067b3  sub     rsp, 40h
0x1800067b7  mov     r12, r8
0x1800067ba  mov     rsi, rdx
0x1800067bd  mov     rdi, rcx
0x1800067c0  test    rdx, rdx
0x1800067c3  jz      loc_1800068E8
0x1800067c9  lea     rbx, [rcx+38h]
0x1800067cd  mov     [rax+20h], rbx
0x1800067d1  mov     [rax+10h], rbx
0x1800067d5  mov     rax, [rbx]
0x1800067d8  xor     r8d, r8d
0x1800067db  xor     edx, edx
0x1800067dd  mov     rcx, rbx
0x1800067e0  mov     rax, [rax]
0x1800067e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067e8  nop
0x1800067e9  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800067ef  call    cs:__imp_TlsGetValue
0x1800067f5  cmp     [rbx+68h], rax
0x1800067f9  jz      loc_18000697F
0x1800067ff  mov     rax, [rbx]
0x180006802  mov     rcx, rbx
0x180006805  mov     rax, [rax+8]
0x180006809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000680e  nop
0x18000680f  mov     rcx, rbx; this
0x180006812  call    ?WaitOnWriters@CAccessLock@@IEAAXXZ; CAccessLock::WaitOnWriters(void)
0x180006817  mov     [rsp+68h+arg_8], rbx
0x18000681c  mov     rax, [rbx]
0x18000681f  xor     r8d, r8d
0x180006822  xor     edx, edx
0x180006824  mov     rcx, rbx
0x180006827  mov     rax, [rax]
0x18000682a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000682f  nop
0x180006830  cmp     dword ptr [rbx+3Ch], 0
0x180006834  jnz     loc_1800069BC
0x18000683a  inc     dword ptr [rbx+38h]
0x18000683d  mov     rcx, [rbx+48h]; hEvent
0x180006841  call    cs:__imp_ResetEvent
0x180006847  test    eax, eax
0x180006849  jz      loc_1800069E1
0x18000684f  mov     rax, [rbx]
0x180006852  mov     rcx, rbx
0x180006855  mov     rax, [rax+8]
0x180006859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000685e  nop
0x18000685f  mov     eax, [rdi+0C0h]
0x180006865  cmp     eax, 7
0x180006868  jnz     loc_1800069A0
0x18000686e  mov     eax, [rdi+0C4h]; jumptable 00000001800069BA cases 1-6
0x180006874  cmp     [rsi], eax
0x180006876  jnz     loc_180006A31
0x18000687c  mov     eax, [rdi+0C8h]
0x180006882  cmp     [rsi+4], eax
0x180006885  jnz     loc_180006A4B
0x18000688b  mov     eax, [rdi+0CCh]
0x180006891  cmp     [rsi+8], eax
0x180006894  jnz     loc_180006A65
0x18000689a  mov     rax, [rbx]; jumptable 00000001800069BA case 8
0x18000689d  mov     rcx, rbx
0x1800068a0  mov     rax, [rax+10h]
0x1800068a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068a9  test    eax, eax
0x1800068ab  jnz     short loc_1800068E8
0x1800068ad  mov     rax, [rbx]
0x1800068b0  xor     r8d, r8d
0x1800068b3  xor     edx, edx
0x1800068b5  mov     rcx, rbx
0x1800068b8  mov     rax, [rax]
0x1800068bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068c0  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x1800068c4  jnz     short loc_1800068D8
0x1800068c6  mov     rcx, [rbx+48h]; hEvent
0x1800068ca  call    cs:__imp_SetEvent
0x1800068d0  test    eax, eax
0x1800068d2  jz      loc_180006A7F
0x1800068d8  mov     rax, [rbx]
0x1800068db  mov     rcx, rbx
0x1800068de  mov     rax, [rax+8]
0x1800068e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068e7  nop
0x1800068e8  lea     rcx, [rdi+148h]; this
0x1800068ef  call    ?Grab@CMutex@@QEAAXXZ; CMutex::Grab(void)
0x1800068f4  test    r12, r12
0x1800068f7  jz      short loc_18000696A
0x1800068f9  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800068ff  call    cs:__imp_TlsGetValue
0x180006905  mov     r14, rax
0x180006908  mov     rdx, [rdi+0F0h]
0x18000690f  mov     rax, [rdx]
0x180006912  xor     r8d, r8d
0x180006915  xor     edx, edx
0x180006917  lea     rcx, [rdi+0F0h]
0x18000691e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006923  mov     r15, [rdi+128h]
0x18000692a  mov     rdx, [rdi+0F0h]
0x180006931  lea     rcx, [rdi+0F0h]
0x180006938  mov     rax, [rdx+8]
0x18000693c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006941  nop
0x180006942  cmp     r15, r14
0x180006945  setz    al
0x180006948  mov     [r12], al
0x18000694c  test    rsi, rsi
0x18000694f  jz      short loc_18000696A
0x180006951  cmp     r15, r14
0x180006954  jnz     short loc_18000696A
0x180006956  mov     rcx, rdi; this
0x180006959  call    ?VerifyState@CReader@@QEAAXXZ; CReader::VerifyState(void)
0x18000695e  mov     rdx, rsi; struct CReader::ActiveState *
0x180006961  mov     rcx, rdi; this
0x180006964  call    ?VerifyActive@CReader@@QEAAXPEBUActiveState@1@@Z; CReader::VerifyActive(CReader::ActiveState const *)
0x180006969  nop
0x18000696a  mov     rbx, [rsp+68h+arg_10]
0x180006972  add     rsp, 40h
0x180006976  pop     r15
0x180006978  pop     r14
0x18000697a  pop     r12
0x18000697c  pop     rdi
0x18000697d  pop     rsi
0x18000697e  retn
0x18000697f  inc     dword ptr [rbx+38h]
0x180006982  mov     rcx, rbx; this
0x180006985  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000698a  nop
0x18000698b  mov     rax, [rbx]
0x18000698e  mov     rcx, rbx
0x180006991  mov     rax, [rax+8]
0x180006995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699a  nop
0x18000699b  jmp     loc_18000685F
0x1800069a0  dec     eax; switch 11 cases
0x1800069a2  cmp     eax, 0Ah
0x1800069a5  ja      short def_1800069BA; jumptable 00000001800069BA default case, case 7
0x1800069a7  cdqe
0x1800069a9  lea     rdx, cs:180000000h
0x1800069b0  mov     ecx, ds:(jpt_1800069BA - 180000000h)[rdx+rax*4]
0x1800069b7  add     rcx, rdx
0x1800069ba  jmp     rcx; switch jump
0x1800069bc  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800069c2  call    cs:__imp_TlsGetValue
0x1800069c8  cmp     [rbx+68h], rax
0x1800069cc  jz      loc_18000683A
0x1800069d2  lea     rcx, [rsp+68h+arg_8]; this
0x1800069d7  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x1800069dc  jmp     loc_18000680F
0x1800069e1  call    cs:__imp_GetLastError
0x1800069e7  mov     [rsp+68h+pExceptionObject], eax
0x1800069eb  lea     rdx, _TI1K; pThrowInfo
0x1800069f2  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800069f7  call    _CxxThrowException_0
0x1800069fd  mov     [rsp+68h+var_44], 80100017h; jumptable 00000001800069BA cases 9-11
0x180006a05  lea     rdx, _TI1K; pThrowInfo
0x180006a0c  lea     rcx, [rsp+68h+var_44]; pExceptionObject
0x180006a11  call    _CxxThrowException_0
0x180006a17  mov     [rsp+68h+var_40], 80100001h; jumptable 00000001800069BA default case, case 7
0x180006a1f  lea     rdx, _TI1K; pThrowInfo
0x180006a26  lea     rcx, [rsp+68h+var_40]; pExceptionObject
0x180006a2b  call    _CxxThrowException_0
0x180006a31  mov     [rsp+68h+var_3C], 80100069h
0x180006a39  lea     rdx, _TI1K; pThrowInfo
0x180006a40  lea     rcx, [rsp+68h+var_3C]; pExceptionObject
0x180006a45  call    _CxxThrowException_0
0x180006a4b  mov     [rsp+68h+var_38], 80100069h
0x180006a53  lea     rdx, _TI1K; pThrowInfo
0x180006a5a  lea     rcx, [rsp+68h+var_38]; pExceptionObject
0x180006a5f  call    _CxxThrowException_0
0x180006a65  mov     [rsp+68h+var_34], 80100068h
0x180006a6d  lea     rdx, _TI1K; pThrowInfo
0x180006a74  lea     rcx, [rsp+68h+var_34]; pExceptionObject
0x180006a79  call    _CxxThrowException_0
0x180006a7f  call    cs:__imp_GetLastError
0x180006a85  mov     [rsp+68h+var_30], eax
0x180006a89  lea     rdx, _TI1K; pThrowInfo
0x180006a90  lea     rcx, [rsp+68h+var_30]; pExceptionObject
0x180006a95  call    _CxxThrowException_0
```
