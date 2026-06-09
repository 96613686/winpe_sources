# CReader::VerifyActive(CReader::ActiveState const *)

- ea: `0x180010390`
- end: `0x180010668`
- name: `?VerifyActive@CReader@@QEAAXPEBUActiveState@1@@Z`
- size: `728`
- prototype: `void __fastcall(CReader *__hidden this, const struct CReader::ActiveState *)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x1800067a0`
- `0x180010044`
- `0x180010994`
- `0x180017118`
- `0x180018d4c`
- `0x18002dcc4`
- `0x18002f890`

## callees

- `0x18000c870`
- `0x18000fb50`
- `0x180010390`
- `0x180012380`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001044a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001044a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800104d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800104d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001061f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001061f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103fb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010562`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800103fb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010562`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CReader::VerifyActive(CReader *this, const struct CReader::ActiveState *a2)
{
  char *v4; // rbx
  __int64 v5; // rbp
  LPVOID Value; // r14
  unsigned int v7; // eax
  int v8; // eax
  char *pExceptionObject; // [rsp+58h] [rbp+10h] BYREF
  char *v11; // [rsp+60h] [rbp+18h] BYREF
  char *v12; // [rsp+68h] [rbp+20h]

  if ( a2 )
  {
    v4 = (char *)this + 56;
    v12 = (char *)this + 56;
    pExceptionObject = (char *)this + 56;
    (**((void (__fastcall ***)(char *, _QWORD, _QWORD))this + 7))((char *)this + 56, 0, 0);
    if ( *((LPVOID *)v4 + 13) == TlsGetValue(dwTlsIndex) )
    {
      ++*((_DWORD *)v4 + 14);
      CAccessLock::UnsignalNoReaders((HANDLE *)v4);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    }
    else
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
      while ( 1 )
      {
        v5 = *((_QWORD *)v4 + 11);
        Value = TlsGetValue(dword_18004B240);
        while ( 1 )
        {
          v7 = WaitForAnyObject(0xFFFFFFFF, v5, Value, 0);
          if ( v7 == 1 )
            break;
          if ( v7 == 2 )
          {
            LODWORD(pExceptionObject) = -2146435070;
            throw (ulong *)&pExceptionObject;
          }
        }
        v11 = v4;
        (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v4)(v4, 0, 0);
        if ( !*((_DWORD *)v4 + 15) || *((LPVOID *)v4 + 13) == TlsGetValue(dwTlsIndex) )
          break;
        COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v11);
      }
      ++*((_DWORD *)v4 + 14);
      if ( !ResetEvent(*((HANDLE *)v4 + 9)) )
      {
        LODWORD(pExceptionObject) = GetLastError();
        throw (ulong *)&pExceptionObject;
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    }
    v8 = *((_DWORD *)this + 48);
    if ( v8 != 7 )
    {
      switch ( v8 )
      {
        case 1:
        case 2:
        case 3:
        case 4:
        case 5:
        case 6:
          break;
        case 8:
          goto LABEL_13;
        case 9:
        case 10:
        case 11:
          LODWORD(pExceptionObject) = -2146435049;
          throw (ulong *)&pExceptionObject;
        default:
          LODWORD(pExceptionObject) = -2146435071;
          throw (ulong *)&pExceptionObject;
      }
    }
    if ( *(_DWORD *)a2 != *((_DWORD *)this + 49) )
    {
      LODWORD(pExceptionObject) = -2146434967;
      throw (ulong *)&pExceptionObject;
    }
    if ( *((_DWORD *)a2 + 1) != *((_DWORD *)this + 50) )
    {
      LODWORD(pExceptionObject) = -2146434967;
      throw (ulong *)&pExceptionObject;
    }
    if ( *((_DWORD *)a2 + 2) != *((_DWORD *)this + 51) )
    {
      LODWORD(pExceptionObject) = -2146434968;
      throw (ulong *)&pExceptionObject;
    }
LABEL_13:
    if ( !(*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4) )
    {
      (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v4)(v4, 0, 0);
      if ( (*((_DWORD *)v4 + 14))-- == 1 && !SetEvent(*((HANDLE *)v4 + 9)) )
      {
        LODWORD(pExceptionObject) = GetLastError();
        throw (ulong *)&pExceptionObject;
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
}

```

## disassembly

```asm
0x180010390  test    rdx, rdx
0x180010393  jz      locret_1800104FB
0x180010399  push    rbx
0x18001039a  push    rbp
0x18001039b  push    rsi
0x18001039c  push    rdi
0x18001039d  push    r14
0x18001039f  sub     rsp, 20h
0x1800103a3  mov     rsi, rdx
0x1800103a6  mov     rdi, rcx
0x1800103a9  lea     rbx, [rcx+38h]
0x1800103ad  mov     [rsp+48h+arg_18], rbx
0x1800103b2  mov     [rsp+48h+pExceptionObject], rbx
0x1800103b7  mov     rax, [rbx]
0x1800103ba  xor     r8d, r8d
0x1800103bd  xor     edx, edx
0x1800103bf  mov     rcx, rbx
0x1800103c2  mov     rax, [rax]
0x1800103c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103ca  nop
0x1800103cb  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800103d1  call    cs:__imp_TlsGetValue
0x1800103d7  cmp     [rbx+68h], rax
0x1800103db  jz      loc_18001051F
0x1800103e1  mov     rax, [rbx]
0x1800103e4  mov     rcx, rbx
0x1800103e7  mov     rax, [rax+8]
0x1800103eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103f0  nop
0x1800103f1  mov     rbp, [rbx+58h]
0x1800103f5  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x1800103fb  call    cs:__imp_TlsGetValue
0x180010401  mov     r14, rax
0x180010404  xor     r9d, r9d
0x180010407  mov     r8, r14
0x18001040a  mov     rdx, rbp
0x18001040d  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x180010412  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x180010417  cmp     eax, 1
0x18001041a  jnz     loc_1800104FC
0x180010420  mov     [rsp+48h+arg_10], rbx
0x180010425  mov     rax, [rbx]
0x180010428  xor     r8d, r8d
0x18001042b  xor     edx, edx
0x18001042d  mov     rcx, rbx
0x180010430  mov     rax, [rax]
0x180010433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010438  nop
0x180010439  cmp     dword ptr [rbx+3Ch], 0
0x18001043d  jnz     loc_18001055C
0x180010443  inc     dword ptr [rbx+38h]
0x180010446  mov     rcx, [rbx+48h]; hEvent
0x18001044a  call    cs:__imp_ResetEvent
0x180010450  test    eax, eax
0x180010452  jz      loc_180010581
0x180010458  mov     rax, [rbx]
0x18001045b  mov     rcx, rbx
0x18001045e  mov     rax, [rax+8]
0x180010462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010467  nop
0x180010468  mov     eax, [rdi+0C0h]
0x18001046e  cmp     eax, 7
0x180010471  jnz     loc_180010540
0x180010477  mov     eax, [rdi+0C4h]; jumptable 000000018001055A cases 1-6
0x18001047d  cmp     [rsi], eax
0x18001047f  jnz     loc_1800105D1
0x180010485  mov     eax, [rdi+0C8h]
0x18001048b  cmp     [rsi+4], eax
0x18001048e  jnz     loc_1800105EB
0x180010494  mov     eax, [rdi+0CCh]
0x18001049a  cmp     [rsi+8], eax
0x18001049d  jnz     loc_180010605
0x1800104a3  mov     rax, [rbx]; jumptable 000000018001055A case 8
0x1800104a6  mov     rcx, rbx
0x1800104a9  mov     rax, [rax+10h]
0x1800104ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104b2  test    eax, eax
0x1800104b4  jnz     short loc_1800104F1
0x1800104b6  mov     rax, [rbx]
0x1800104b9  xor     r8d, r8d
0x1800104bc  xor     edx, edx
0x1800104be  mov     rcx, rbx
0x1800104c1  mov     rax, [rax]
0x1800104c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104c9  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x1800104cd  jnz     short loc_1800104E1
0x1800104cf  mov     rcx, [rbx+48h]; hEvent
0x1800104d3  call    cs:__imp_SetEvent
0x1800104d9  test    eax, eax
0x1800104db  jz      loc_18001061F
0x1800104e1  mov     rax, [rbx]
0x1800104e4  mov     rcx, rbx
0x1800104e7  mov     rax, [rax+8]
0x1800104eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104f0  nop
0x1800104f1  add     rsp, 20h
0x1800104f5  pop     r14
0x1800104f7  pop     rdi
0x1800104f8  pop     rsi
0x1800104f9  pop     rbp
0x1800104fa  pop     rbx
0x1800104fb  retn
0x1800104fc  cmp     eax, 2
0x1800104ff  jnz     loc_180010404
0x180010505  mov     dword ptr [rsp+48h+pExceptionObject], 80100002h
0x18001050d  lea     rdx, _TI1K; pThrowInfo
0x180010514  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180010519  call    _CxxThrowException_0
0x18001051f  inc     dword ptr [rbx+38h]
0x180010522  mov     rcx, rbx; this
0x180010525  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18001052a  nop
0x18001052b  mov     rax, [rbx]
0x18001052e  mov     rcx, rbx
0x180010531  mov     rax, [rax+8]
0x180010535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001053a  nop
0x18001053b  jmp     loc_180010468
0x180010540  dec     eax; switch 11 cases
0x180010542  cmp     eax, 0Ah
0x180010545  ja      short def_18001055A; jumptable 000000018001055A default case, case 7
0x180010547  cdqe
0x180010549  lea     rdx, cs:180000000h
0x180010550  mov     ecx, ds:(jpt_18001055A - 180000000h)[rdx+rax*4]
0x180010557  add     rcx, rdx
0x18001055a  jmp     rcx; switch jump
0x18001055c  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180010562  call    cs:__imp_TlsGetValue
0x180010568  cmp     [rbx+68h], rax
0x18001056c  jz      loc_180010443
0x180010572  lea     rcx, [rsp+48h+arg_10]; this
0x180010577  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18001057c  jmp     loc_1800103F1
0x180010581  call    cs:__imp_GetLastError
0x180010587  mov     dword ptr [rsp+48h+pExceptionObject], eax
0x18001058b  lea     rdx, _TI1K; pThrowInfo
0x180010592  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180010597  call    _CxxThrowException_0
0x18001059d  mov     dword ptr [rsp+48h+pExceptionObject], 80100017h; jumptable 000000018001055A cases 9-11
0x1800105a5  lea     rdx, _TI1K; pThrowInfo
0x1800105ac  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800105b1  call    _CxxThrowException_0
0x1800105b7  mov     dword ptr [rsp+48h+pExceptionObject], 80100001h; jumptable 000000018001055A default case, case 7
0x1800105bf  lea     rdx, _TI1K; pThrowInfo
0x1800105c6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800105cb  call    _CxxThrowException_0
0x1800105d1  mov     dword ptr [rsp+48h+pExceptionObject], 80100069h
0x1800105d9  lea     rdx, _TI1K; pThrowInfo
0x1800105e0  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800105e5  call    _CxxThrowException_0
0x1800105eb  mov     dword ptr [rsp+48h+pExceptionObject], 80100069h
0x1800105f3  lea     rdx, _TI1K; pThrowInfo
0x1800105fa  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800105ff  call    _CxxThrowException_0
0x180010605  mov     dword ptr [rsp+48h+pExceptionObject], 80100068h
0x18001060d  lea     rdx, _TI1K; pThrowInfo
0x180010614  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180010619  call    _CxxThrowException_0
0x18001061f  call    cs:__imp_GetLastError
0x180010625  mov     dword ptr [rsp+48h+pExceptionObject], eax
0x180010629  lea     rdx, _TI1K; pThrowInfo
0x180010630  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180010635  call    _CxxThrowException_0
```
