# CReader::VerifyState(void)

- ea: `0x18000ecb0`
- end: `0x18000f1b0`
- name: `?VerifyState@CReader@@QEAAXXZ`
- size: `1280`
- prototype: `void __fastcall(CReader *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800067a0`
- `0x180018d4c`

## callees

- `0x18000366c`
- `0x180003ff0`
- `0x18000c870`
- `0x18000cd80`
- `0x18000d7a0`
- `0x18000ecb0`
- `0x18000f1c0`
- `0x18000fb50`
- `0x180012380`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ed85`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ed85`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000edd9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ee40`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000edd9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ee40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f15d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f15d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ed0c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ed36`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000eeb9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ed0c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ed36`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000eeb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CReader::VerifyState(CReader *this)
{
  char *v2; // rbx
  __int64 v3; // rsi
  LPVOID Value; // rbp
  unsigned int v5; // eax
  int v6; // esi
  int ReaderState; // eax
  __int64 v8; // rbx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  bool v15; // zf
  int v16; // eax
  bool v17; // zf
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  char *pExceptionObject; // [rsp+58h] [rbp+10h] BYREF
  char *v32; // [rsp+60h] [rbp+18h] BYREF
  __int64 v33; // [rsp+68h] [rbp+20h] BYREF

  if ( (unsigned int)CReader::AvailabilityStatus((__int64)this) != 8 )
  {
    v2 = (char *)this + 56;
    CLockWrite::CLockWrite((CLockWrite *)&v33, (CReader *)((char *)this + 56));
    while ( 1 )
    {
      pExceptionObject = (char *)this + 56;
      (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v2)((char *)this + 56, 0, 0);
      if ( *((LPVOID *)this + 20) == TlsGetValue(dwTlsIndex) )
      {
        ++*((_DWORD *)this + 28);
        CAccessLock::UnsignalNoReaders((HANDLE *)this + 7);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 56);
      }
      else
      {
        (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 56);
        while ( 1 )
        {
          v3 = *((_QWORD *)this + 18);
          Value = TlsGetValue(dword_18004B240);
          while ( 1 )
          {
            v5 = WaitForAnyObject(0xFFFFFFFF, v3, Value, 0);
            if ( v5 == 1 )
              break;
            if ( v5 == 2 )
            {
              LODWORD(pExceptionObject) = -2146435070;
              throw (ulong *)&pExceptionObject;
            }
          }
          v32 = (char *)this + 56;
          (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v2)((char *)this + 56, 0, 0);
          if ( !*((_DWORD *)this + 29) || *((LPVOID *)this + 20) == TlsGetValue(dwTlsIndex) )
            break;
          COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v32);
        }
        ++*((_DWORD *)this + 28);
        if ( !ResetEvent(*((HANDLE *)this + 16)) )
        {
          LODWORD(pExceptionObject) = GetLastError();
          throw (ulong *)&pExceptionObject;
        }
        (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 56);
      }
      v6 = *((_DWORD *)this + 59);
      if ( !(*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))((char *)this + 56) )
      {
        (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v2)((char *)this + 56, 0, 0);
        v15 = (*((_DWORD *)this + 28))-- == 1;
        if ( v15 && !SetEvent(*((HANDLE *)this + 16)) )
        {
          LODWORD(pExceptionObject) = GetLastError();
          throw (ulong *)&pExceptionObject;
        }
        (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 56);
      }
      ReaderState = CReader::GetReaderState(this);
      if ( v6 == ReaderState )
        break;
      switch ( v6 )
      {
        case 0:
          switch ( ReaderState )
          {
            case 1:
              *((_DWORD *)this + 57) = 0;
              *((_DWORD *)this + 46) = 0;
              ++*((_DWORD *)this + 50);
              if ( *((int *)this + 48) < 8 )
                CReader::SetAvailabilityStatus(this, 1);
              break;
            case 2:
            case 3:
            case 4:
            case 5:
            case 6:
              *((_DWORD *)this + 57) = 0;
              *((_DWORD *)this + 46) = 0;
              ++*((_DWORD *)this + 49);
              if ( *((int *)this + 48) < 8 )
                CReader::PowerUp(this);
              break;
            default:
              continue;
          }
          continue;
        case 1:
          v9 = ReaderState - 2;
          if ( v9 && (v10 = v9 - 1) != 0 && (v11 = v10 - 1) != 0 && (v12 = v11 - 1) != 0 )
          {
            if ( v12 != 1 )
              continue;
          }
          else
          {
            *((_DWORD *)this + 57) = 0;
          }
          ++*((_DWORD *)this + 49);
          if ( *((int *)this + 48) < 8 )
            goto LABEL_67;
          continue;
        case 2:
          v13 = ReaderState - 1;
          if ( !v13 )
            goto LABEL_52;
          v14 = v13 - 2;
          if ( !v14 )
            goto LABEL_49;
          v16 = v14 - 1;
          v15 = v16 == 0;
          goto LABEL_44;
        case 3:
          v19 = ReaderState - 1;
          if ( !v19 )
            goto LABEL_52;
          v20 = v19 - 1;
          if ( !v20 )
            goto LABEL_55;
          v16 = v20 - 2;
          v15 = v16 == 0;
LABEL_44:
          if ( v15 )
            goto LABEL_49;
          v18 = v16 - 1;
          v17 = v18 == 0;
          goto LABEL_46;
        case 4:
          v21 = ReaderState - 1;
          if ( !v21 )
          {
LABEL_52:
            *((_DWORD *)this + 57) = 0;
            *((_DWORD *)this + 46) = 0;
            ++*((_DWORD *)this + 50);
            continue;
          }
          v22 = v21 - 1;
          if ( v22 )
          {
            v23 = v22 - 1;
            if ( v23 )
            {
              v18 = v23 - 2;
              v17 = v18 == 0;
LABEL_46:
              if ( v17 )
              {
LABEL_49:
                *((_DWORD *)this + 57) = 0;
              }
              else if ( v18 != 1 )
              {
                continue;
              }
              if ( *((int *)this + 48) < 8 )
              {
LABEL_67:
                *((_DWORD *)this + 57) = 0;
                *((_DWORD *)this + 46) = 0;
                CReader::PowerUp(this);
              }
              continue;
            }
          }
LABEL_55:
          *((_DWORD *)this + 57) = 0;
          ++*((_DWORD *)this + 51);
          if ( *((int *)this + 48) >= 8 )
            continue;
          goto LABEL_56;
        case 5:
          v24 = ReaderState - 1;
          if ( !v24 )
            goto LABEL_74;
          v25 = v24 - 1;
          if ( !v25 )
            goto LABEL_55;
          v26 = v25 - 1;
          if ( !v26 )
            goto LABEL_55;
          v27 = v26 - 1;
          if ( !v27 )
            goto LABEL_55;
          if ( v27 == 2 && *((int *)this + 48) < 8 )
            goto LABEL_67;
          continue;
        case 6:
          v28 = ReaderState - 1;
          if ( v28 )
          {
            v29 = v28 - 1;
            if ( !v29 || (v30 = v29 - 1) == 0 || (unsigned int)(v30 - 1) <= 1 )
            {
              ++*((_DWORD *)this + 51);
              *((_DWORD *)this + 57) = 0;
              if ( *((int *)this + 48) < 8 )
              {
LABEL_56:
                *((_DWORD *)this + 46) = 0;
                CReader::PowerUp(this);
              }
            }
          }
          else
          {
LABEL_74:
            ++*((_DWORD *)this + 50);
            *((_DWORD *)this + 57) = 0;
            *((_DWORD *)this + 46) = 0;
          }
          break;
        default:
          continue;
      }
    }
    v8 = v33;
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33) )
    {
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v8)(v8, 0, 0);
      v15 = (*(_DWORD *)(v8 + 60))-- == 1;
      if ( v15 )
      {
        *(_QWORD *)(v8 + 104) = 0;
        if ( !SetEvent(*(HANDLE *)(v8 + 88)) )
        {
          LODWORD(pExceptionObject) = GetLastError();
          throw (ulong *)&pExceptionObject;
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
}

```

## disassembly

```asm
0x18000ecb0  mov     [rsp+arg_0], rbx
0x18000ecb5  push    rbp
0x18000ecb6  push    rsi
0x18000ecb7  push    rdi
0x18000ecb8  push    r14
0x18000ecba  push    r15
0x18000ecbc  sub     rsp, 20h
0x18000ecc0  mov     rdi, rcx
0x18000ecc3  call    ?AvailabilityStatus@CReader@@QEAA?AW4AvailableState@1@XZ; CReader::AvailabilityStatus(void)
0x18000ecc8  cmp     eax, 8
0x18000eccb  jz      loc_18000EE5E
0x18000ecd1  lea     rbx, [rdi+38h]
0x18000ecd5  mov     rdx, rbx; struct CAccessLock *
0x18000ecd8  lea     rcx, [rsp+48h+arg_18]; this
0x18000ecdd  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18000ece2  nop
0x18000ece3  lea     r15, cs:180000000h
0x18000ecea  xor     r14d, r14d
0x18000eced  mov     [rsp+48h+pExceptionObject], rbx; jumptable 000000018000EEEC default case
0x18000ecf2  mov     rax, [rbx]
0x18000ecf5  xor     r8d, r8d
0x18000ecf8  xor     edx, edx
0x18000ecfa  mov     rcx, rbx
0x18000ecfd  mov     rax, [rax]
0x18000ed00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed05  nop
0x18000ed06  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000ed0c  call    cs:__imp_TlsGetValue
0x18000ed12  cmp     [rbx+68h], rax
0x18000ed16  jz      loc_18000EE92
0x18000ed1c  mov     rax, [rbx]
0x18000ed1f  mov     rcx, rbx
0x18000ed22  mov     rax, [rax+8]
0x18000ed26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed2b  nop
0x18000ed2c  mov     rsi, [rbx+58h]
0x18000ed30  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000ed36  call    cs:__imp_TlsGetValue
0x18000ed3c  mov     rbp, rax
0x18000ed3f  xor     r9d, r9d
0x18000ed42  mov     r8, rbp
0x18000ed45  mov     rdx, rsi
0x18000ed48  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000ed4d  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000ed52  cmp     eax, 1
0x18000ed55  jnz     loc_18000EE6F
0x18000ed5b  mov     [rsp+48h+arg_10], rbx
0x18000ed60  mov     rax, [rbx]
0x18000ed63  xor     r8d, r8d
0x18000ed66  xor     edx, edx
0x18000ed68  mov     rcx, rbx
0x18000ed6b  mov     rax, [rax]
0x18000ed6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed73  nop
0x18000ed74  cmp     dword ptr [rbx+3Ch], 0
0x18000ed78  jnz     loc_18000EEB3
0x18000ed7e  inc     dword ptr [rbx+38h]
0x18000ed81  mov     rcx, [rbx+48h]; hEvent
0x18000ed85  call    cs:__imp_ResetEvent
0x18000ed8b  test    eax, eax
0x18000ed8d  jz      loc_18000F15D
0x18000ed93  mov     rax, [rbx]
0x18000ed96  mov     rcx, rbx
0x18000ed99  mov     rax, [rax+8]
0x18000ed9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eda2  nop
0x18000eda3  mov     esi, [rdi+0ECh]
0x18000eda9  mov     rax, [rbx]
0x18000edac  mov     rcx, rbx
0x18000edaf  mov     rax, [rax+10h]
0x18000edb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edb8  test    eax, eax
0x18000edba  jnz     short loc_18000EDF7
0x18000edbc  mov     rax, [rbx]
0x18000edbf  xor     r8d, r8d
0x18000edc2  xor     edx, edx
0x18000edc4  mov     rcx, rbx
0x18000edc7  mov     rax, [rax]
0x18000edca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edcf  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x18000edd3  jnz     short loc_18000EDE7
0x18000edd5  mov     rcx, [rbx+48h]; hEvent
0x18000edd9  call    cs:__imp_SetEvent
0x18000eddf  test    eax, eax
0x18000ede1  jz      loc_18000F125
0x18000ede7  mov     rax, [rbx]
0x18000edea  mov     rcx, rbx
0x18000eded  mov     rax, [rax+8]
0x18000edf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edf6  nop
0x18000edf7  mov     rcx, rdi; this
0x18000edfa  call    ?GetReaderState@CReader@@QEAAKXZ; CReader::GetReaderState(void)
0x18000edff  cmp     esi, eax
0x18000ee01  jnz     loc_18000EED8
0x18000ee07  mov     rbx, [rsp+48h+arg_18]
0x18000ee0c  mov     rax, [rbx]
0x18000ee0f  mov     rcx, rbx
0x18000ee12  mov     rax, [rax+10h]
0x18000ee16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee1b  test    eax, eax
0x18000ee1d  jnz     short loc_18000EE5E
0x18000ee1f  mov     rax, [rbx]
0x18000ee22  xor     r8d, r8d
0x18000ee25  xor     edx, edx
0x18000ee27  mov     rcx, rbx
0x18000ee2a  mov     rax, [rax]
0x18000ee2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee32  add     dword ptr [rbx+3Ch], 0FFFFFFFFh
0x18000ee36  jnz     short loc_18000EE4E
0x18000ee38  mov     [rbx+68h], r14
0x18000ee3c  mov     rcx, [rbx+58h]; hEvent
0x18000ee40  call    cs:__imp_SetEvent
0x18000ee46  test    eax, eax
0x18000ee48  jz      loc_18000F141
0x18000ee4e  mov     rax, [rbx]
0x18000ee51  mov     rcx, rbx
0x18000ee54  mov     rax, [rax+8]
0x18000ee58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee5d  nop
0x18000ee5e  mov     rbx, [rsp+48h+arg_0]
0x18000ee63  add     rsp, 20h
0x18000ee67  pop     r15
0x18000ee69  pop     r14
0x18000ee6b  pop     rdi
0x18000ee6c  pop     rsi
0x18000ee6d  pop     rbp
0x18000ee6e  retn
0x18000ee6f  cmp     eax, 2
0x18000ee72  jnz     loc_18000ED3F
0x18000ee78  mov     dword ptr [rsp+48h+pExceptionObject], 80100002h
0x18000ee80  lea     rdx, _TI1K; pThrowInfo
0x18000ee87  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000ee8c  call    _CxxThrowException_0
0x18000ee92  inc     dword ptr [rbx+38h]
0x18000ee95  mov     rcx, rbx; this
0x18000ee98  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000ee9d  nop
0x18000ee9e  mov     rax, [rbx]
0x18000eea1  mov     rcx, rbx
0x18000eea4  mov     rax, [rax+8]
0x18000eea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eead  nop
0x18000eeae  jmp     loc_18000EDA3
0x18000eeb3  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000eeb9  call    cs:__imp_TlsGetValue
0x18000eebf  cmp     [rbx+68h], rax
0x18000eec3  jz      loc_18000ED7E
0x18000eec9  lea     rcx, [rsp+48h+arg_10]; this
0x18000eece  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18000eed3  jmp     loc_18000ED2C
0x18000eed8  cmp     esi, 6; switch 7 cases
0x18000eedb  ja      def_18000EEEC; jumptable 000000018000EEEC default case
0x18000eee1  mov     ecx, ds:(jpt_18000EEEC - 180000000h)[r15+rsi*4]
0x18000eee9  add     rcx, r15
0x18000eeec  jmp     rcx; switch jump
0x18000eeee  dec     eax; jumptable 000000018000EEEC case 0
0x18000eef0  cmp     eax, 5
0x18000eef3  ja      def_18000EEEC; jumptable 000000018000EEEC default case
0x18000eef9  mov     eax, ds:(jpt_18000EF04 - 180000000h)[r15+rax*4]
0x18000ef01  add     rax, r15
0x18000ef04  jmp     rax; switch jump
0x18000ef06  mov     [rdi+0E4h], r14d; jumptable 000000018000EF04 case 1
0x18000ef0d  mov     [rdi+0B8h], r14d
0x18000ef14  inc     dword ptr [rdi+0C8h]
0x18000ef1a  cmp     dword ptr [rdi+0C0h], 8
0x18000ef21  jge     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000ef27  mov     edx, 1
0x18000ef2c  mov     rcx, rdi
0x18000ef2f  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x18000ef34  jmp     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000ef39  mov     [rdi+0E4h], r14d; jumptable 000000018000EF04 cases 2-6
0x18000ef40  mov     [rdi+0B8h], r14d
0x18000ef47  inc     dword ptr [rdi+0C4h]
0x18000ef4d  cmp     dword ptr [rdi+0C0h], 8
0x18000ef54  jge     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000ef5a  mov     rcx, rdi; this
0x18000ef5d  call    ?PowerUp@CReader@@IEAAXXZ; CReader::PowerUp(void)
0x18000ef62  jmp     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000ef67  sub     eax, 2; jumptable 000000018000EEEC case 1
0x18000ef6a  jz      short loc_18000EF86
0x18000ef6c  sub     eax, 1
0x18000ef6f  jz      short loc_18000EF86
0x18000ef71  sub     eax, 1
0x18000ef74  jz      short loc_18000EF86
0x18000ef76  sub     eax, 1
0x18000ef79  jz      short loc_18000EF86
0x18000ef7b  cmp     eax, 1
0x18000ef7e  jnz     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000ef84  jmp     short loc_18000EF8D
0x18000ef86  mov     [rdi+0E4h], r14d
0x18000ef8d  inc     dword ptr [rdi+0C4h]
0x18000ef93  cmp     dword ptr [rdi+0C0h], 8
0x18000ef9a  jge     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000efa0  mov     [rdi+0E4h], r14d
0x18000efa7  mov     [rdi+0B8h], r14d
0x18000efae  mov     rcx, rdi; this
0x18000efb1  call    ?PowerUp@CReader@@IEAAXXZ; CReader::PowerUp(void)
0x18000efb6  jmp     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000efbb  sub     eax, 1; jumptable 000000018000EEEC case 2
0x18000efbe  jz      short loc_18000F013
0x18000efc0  sub     eax, 2
0x18000efc3  jz      short loc_18000EFE4
0x18000efc5  sub     eax, 1
0x18000efc8  jmp     short loc_18000EFCD
0x18000efca  sub     eax, 2
0x18000efcd  jz      short loc_18000EFE4
0x18000efcf  sub     eax, 1
0x18000efd2  jmp     short loc_18000EFD7
0x18000efd4  sub     eax, 2
0x18000efd7  jz      short loc_18000EFE4
0x18000efd9  cmp     eax, 1
0x18000efdc  jnz     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000efe2  jmp     short loc_18000EFEB
0x18000efe4  mov     [rdi+0E4h], r14d
0x18000efeb  cmp     dword ptr [rdi+0C0h], 8
0x18000eff2  jge     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000eff8  mov     [rdi+0E4h], r14d
0x18000efff  mov     [rdi+0B8h], r14d
0x18000f006  mov     rcx, rdi; this
0x18000f009  call    ?PowerUp@CReader@@IEAAXXZ; CReader::PowerUp(void)
0x18000f00e  jmp     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000f013  mov     [rdi+0E4h], r14d
0x18000f01a  mov     [rdi+0B8h], r14d
0x18000f021  inc     dword ptr [rdi+0C8h]
0x18000f027  jmp     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000f02c  sub     eax, 1; jumptable 000000018000EEEC case 3
0x18000f02f  jz      short loc_18000F013
0x18000f031  sub     eax, 1
0x18000f034  jnz     short loc_18000EFCA
0x18000f036  mov     [rdi+0E4h], r14d
0x18000f03d  inc     dword ptr [rdi+0CCh]
0x18000f043  cmp     dword ptr [rdi+0C0h], 8
0x18000f04a  jge     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000f050  mov     [rdi+0B8h], r14d
0x18000f057  mov     rcx, rdi; this
0x18000f05a  call    ?PowerUp@CReader@@IEAAXXZ; CReader::PowerUp(void)
0x18000f05f  jmp     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000f064  sub     eax, 1; jumptable 000000018000EEEC case 4
0x18000f067  jz      short loc_18000F013
0x18000f069  sub     eax, 1
0x18000f06c  jz      short loc_18000F036
0x18000f06e  sub     eax, 1
0x18000f071  jz      short loc_18000F036
0x18000f073  jmp     loc_18000EFD4
0x18000f078  sub     eax, 1; jumptable 000000018000EEEC case 5
0x18000f07b  jz      loc_18000F10C
0x18000f081  sub     eax, 1
0x18000f084  jz      short loc_18000F036
0x18000f086  sub     eax, 1
0x18000f089  jz      short loc_18000F036
0x18000f08b  sub     eax, 1
0x18000f08e  jz      short loc_18000F036
0x18000f090  cmp     eax, 2
0x18000f093  jnz     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000f099  cmp     dword ptr [rdi+0C0h], 8
0x18000f0a0  jge     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000f0a6  mov     [rdi+0E4h], r14d
0x18000f0ad  mov     [rdi+0B8h], r14d
0x18000f0b4  mov     rcx, rdi; this
0x18000f0b7  call    ?PowerUp@CReader@@IEAAXXZ; CReader::PowerUp(void)
0x18000f0bc  jmp     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000f0c1  sub     eax, 1; jumptable 000000018000EEEC case 6
0x18000f0c4  jz      short loc_18000F10C
0x18000f0c6  sub     eax, 1
0x18000f0c9  jz      short loc_18000F0DE
0x18000f0cb  sub     eax, 1
0x18000f0ce  jz      short loc_18000F0DE
0x18000f0d0  sub     eax, 1
0x18000f0d3  jz      short loc_18000F0DE
0x18000f0d5  cmp     eax, 1
0x18000f0d8  jnz     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000f0de  inc     dword ptr [rdi+0CCh]
0x18000f0e4  mov     [rdi+0E4h], r14d
0x18000f0eb  cmp     dword ptr [rdi+0C0h], 8
0x18000f0f2  jge     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000f0f8  mov     [rdi+0B8h], r14d
0x18000f0ff  mov     rcx, rdi; this
0x18000f102  call    ?PowerUp@CReader@@IEAAXXZ; CReader::PowerUp(void)
0x18000f107  jmp     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000f10c  inc     dword ptr [rdi+0C8h]
0x18000f112  mov     [rdi+0E4h], r14d
0x18000f119  mov     [rdi+0B8h], r14d
0x18000f120  jmp     def_18000EEEC; jumptable 000000018000EEEC default case
0x18000f125  call    cs:__imp_GetLastError
0x18000f12b  mov     dword ptr [rsp+48h+pExceptionObject], eax
0x18000f12f  lea     rdx, _TI1K; pThrowInfo
0x18000f136  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f13b  call    _CxxThrowException_0
0x18000f141  call    cs:__imp_GetLastError
0x18000f147  mov     dword ptr [rsp+48h+pExceptionObject], eax
0x18000f14b  lea     rdx, _TI1K; pThrowInfo
0x18000f152  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f157  call    _CxxThrowException_0
0x18000f15d  call    cs:__imp_GetLastError
0x18000f163  mov     dword ptr [rsp+48h+pExceptionObject], eax
0x18000f167  lea     rdx, _TI1K; pThrowInfo
0x18000f16e  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000f173  call    _CxxThrowException_0
```
