# CalaisLockReader(ushort const *,void *)

- ea: `0x18000c9a0`
- end: `0x18000cd6e`
- name: `?CalaisLockReader@@YAPEAVCReaderReference@@PEBGPEAX@Z`
- size: `974`
- prototype: `struct CReaderReference *__fastcall(LPCWSTR lpString1, PSID pSid2)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004af8`
- `0x180010dc4`
- `0x180012190`

## callees

- `0x18000c870`
- `0x18000c9a0`
- `0x18000fb50`
- `0x180019bc4`
- `0x18001c330`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000cb11`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000cb11`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000cb9a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000cb9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd17`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ca98`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cac2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ccb0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ca98`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cac2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ccb0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000cc12`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000cc12`
- `KERNEL32!lstrcmpiW` at `0x18000ca1a`
- `KERNEL32!lstrcmpiW` at `0x18000ca1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct CReaderReference *__fastcall CalaisLockReader(LPCWSTR lpString1, PSID pSid2)
{
  struct CCriticalSectionObject *v4; // rdi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r14
  const WCHAR *v8; // rdx
  char *v9; // rax
  const unsigned __int8 *v10; // rcx
  const unsigned __int16 *v11; // r9
  _QWORD *v12; // r15
  __int64 v13; // rbx
  __int64 v14; // rsi
  LPVOID Value; // rbp
  unsigned int v16; // eax
  __int64 v17; // rbp
  __int64 v18; // rsi
  bool v19; // zf
  void *v21; // rax
  __int64 pExceptionObject; // [rsp+90h] [rbp+18h] BYREF
  struct CCriticalSectionObject *v23; // [rsp+98h] [rbp+20h]

  v4 = g_pcsControlLocks;
  v23 = g_pcsControlLocks;
  (**(void (__fastcall ***)(struct CCriticalSectionObject *, _QWORD, _QWORD))g_pcsControlLocks)(g_pcsControlLocks, 0, 0);
  v5 = HIDWORD(qword_18004B0C8);
  v6 = HIDWORD(qword_18004B0C8);
  while ( 1 )
  {
    do
    {
      if ( !v6 )
      {
        LODWORD(pExceptionObject) = -2146435063;
        throw (ulong *)&pExceptionObject;
      }
      --v6;
    }
    while ( v5 <= v6 );
    _mm_lfence();
    v7 = *((_QWORD *)qword_18004B0D0 + (int)v6);
    if ( v7 )
    {
      v8 = *(_DWORD *)(v7 + 28) ? *(const WCHAR **)(v7 + 16) : &Data;
      if ( !lstrcmpiW(lpString1, v8) )
        break;
    }
    v5 = HIDWORD(qword_18004B0C8);
  }
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7) )
  {
    if ( pSid2 )
    {
      v21 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7);
      if ( !EqualSid(v21, pSid2) )
      {
        LODWORD(pExceptionObject) = -2146435063;
        throw (ulong *)&pExceptionObject;
      }
    }
  }
  v9 = (char *)operator new(0x20u);
  v12 = v9;
  if ( v9 )
  {
    *(_OWORD *)(v9 + 8) = 0;
    *((_DWORD *)v9 + 6) = 0;
    v13 = v7 + 56;
    pExceptionObject = v7 + 56;
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))(v7 + 56))(v7 + 56, 0, 0);
    if ( *(LPVOID *)(v7 + 160) == TlsGetValue(dwTlsIndex) )
    {
      ++*(_DWORD *)(v7 + 112);
      CAccessLock::UnsignalNoReaders((CAccessLock *)(v7 + 56));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v7 + 56);
    }
    else
    {
      do
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v7 + 56);
        v14 = *(_QWORD *)(v7 + 144);
        Value = TlsGetValue(dword_18004B240);
        while ( 1 )
        {
          v16 = WaitForAnyObject(0xFFFFFFFF, v14, Value, 0);
          if ( v16 == 1 )
            break;
          if ( v16 == 2 )
          {
            LODWORD(pExceptionObject) = -2146435070;
            throw (ulong *)&pExceptionObject;
          }
        }
        (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v13)(v7 + 56, 0, 0);
      }
      while ( *(_DWORD *)(v7 + 116) && *(LPVOID *)(v7 + 160) != TlsGetValue(dwTlsIndex) );
      ++*(_DWORD *)(v7 + 112);
      if ( !ResetEvent(*(HANDLE *)(v7 + 128)) )
      {
        LODWORD(pExceptionObject) = GetLastError();
        throw (ulong *)&pExceptionObject;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v7 + 56);
    }
    v17 = *(_QWORD *)(v7 + 48);
    if ( !v17 )
    {
      LODWORD(pExceptionObject) = -2146435049;
      throw (ulong *)&pExceptionObject;
    }
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))(v17 + 8))(v17 + 8, 0, 0);
    ++*(_DWORD *)(v17 + 64);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v17 + 8) + 8LL))(v17 + 8);
    v18 = *(_QWORD *)(v7 + 48);
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v7 + 56) )
    {
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v13)(v7 + 56, 0, 0);
      v19 = (*(_DWORD *)(v7 + 112))-- == 1;
      if ( v19 && !SetEvent(*(HANDLE *)(v7 + 128)) )
      {
        LODWORD(pExceptionObject) = GetLastError();
        throw (ulong *)&pExceptionObject;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v7 + 56);
    }
    *v12 = v18;
  }
  else
  {
    v12 = 0;
  }
  if ( !v12 )
  {
    CalaisError(v10, 0xCBu, 0, v11);
    LODWORD(pExceptionObject) = -2146435066;
    throw (ulong *)&pExceptionObject;
  }
  (*(void (__fastcall **)(struct CCriticalSectionObject *))(*(_QWORD *)v4 + 8LL))(v4);
  return (struct CReaderReference *)v12;
}

```

## disassembly

```asm
0x18000c9a0  mov     [rsp+arg_0], rbx
0x18000c9a5  push    rbp
0x18000c9a6  push    rsi
0x18000c9a7  push    rdi
0x18000c9a8  push    r14
0x18000c9aa  push    r15
0x18000c9ac  sub     rsp, 50h
0x18000c9b0  mov     rbp, rdx
0x18000c9b3  mov     rsi, rcx
0x18000c9b6  mov     rdi, cs:?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; CCriticalSectionObject * near * g_pcsControlLocks
0x18000c9bd  mov     [rsp+78h+arg_18], rdi
0x18000c9c5  mov     rax, [rdi]
0x18000c9c8  xor     r8d, r8d
0x18000c9cb  xor     edx, edx
0x18000c9cd  mov     rcx, rdi
0x18000c9d0  mov     rax, [rax]
0x18000c9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9d8  nop
0x18000c9d9  mov     eax, dword ptr cs:qword_18004B0C8+4
0x18000c9df  mov     ebx, eax
0x18000c9e1  test    ebx, ebx
0x18000c9e3  jz      loc_18000CC40
0x18000c9e9  dec     ebx
0x18000c9eb  cmp     eax, ebx
0x18000c9ed  jbe     short loc_18000C9E1
0x18000c9ef  lfence
0x18000c9f2  movsxd  rcx, ebx
0x18000c9f5  mov     rax, cs:qword_18004B0D0
0x18000c9fc  mov     r14, [rax+rcx*8]
0x18000ca00  test    r14, r14
0x18000ca03  jz      short loc_18000CA24
0x18000ca05  cmp     dword ptr [r14+1Ch], 0
0x18000ca0a  ja      loc_18000CBEB
0x18000ca10  lea     rdx, Data; lpString2
0x18000ca17  mov     rcx, rsi; lpString1
0x18000ca1a  call    cs:__imp_lstrcmpiW
0x18000ca20  test    eax, eax
0x18000ca22  jz      short loc_18000CA2C
0x18000ca24  mov     eax, dword ptr cs:qword_18004B0C8+4
0x18000ca2a  jmp     short loc_18000C9E1
0x18000ca2c  mov     rax, [r14]
0x18000ca2f  mov     rcx, r14
0x18000ca32  mov     rax, [rax+38h]
0x18000ca36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca3b  test    rax, rax
0x18000ca3e  jnz     loc_18000CBF4
0x18000ca44  mov     ecx, 20h ; ' '; Size
0x18000ca49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ca4e  mov     r15, rax
0x18000ca51  mov     [rsp+78h+var_48], rax
0x18000ca56  test    rax, rax
0x18000ca59  jz      loc_18000CD39
0x18000ca5f  xorps   xmm0, xmm0
0x18000ca62  movups  xmmword ptr [rax+8], xmm0
0x18000ca66  mov     dword ptr [rax+18h], 0
0x18000ca6d  lea     rbx, [r14+38h]
0x18000ca71  mov     [rsp+78h+var_40], rbx
0x18000ca76  mov     [rsp+78h+pExceptionObject], rbx
0x18000ca7e  mov     rax, [rbx]
0x18000ca81  xor     r8d, r8d
0x18000ca84  xor     edx, edx
0x18000ca86  mov     rcx, rbx
0x18000ca89  mov     rax, [rax]
0x18000ca8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca91  nop
0x18000ca92  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000ca98  call    cs:__imp_TlsGetValue
0x18000ca9e  cmp     [rbx+68h], rax
0x18000caa2  jz      loc_18000CC89
0x18000caa8  mov     rax, [rbx]
0x18000caab  mov     rcx, rbx
0x18000caae  mov     rax, [rax+8]
0x18000cab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cab7  nop
0x18000cab8  mov     rsi, [rbx+58h]
0x18000cabc  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000cac2  call    cs:__imp_TlsGetValue
0x18000cac8  mov     rbp, rax
0x18000cacb  xor     r9d, r9d
0x18000cace  mov     r8, rbp
0x18000cad1  mov     rdx, rsi
0x18000cad4  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000cad9  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000cade  cmp     eax, 1
0x18000cae1  jnz     loc_18000CC60
0x18000cae7  mov     [rsp+78h+var_38], rbx
0x18000caec  mov     rax, [rbx]
0x18000caef  xor     r8d, r8d
0x18000caf2  xor     edx, edx
0x18000caf4  mov     rcx, rbx
0x18000caf7  mov     rax, [rax]
0x18000cafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caff  nop
0x18000cb00  cmp     dword ptr [rbx+3Ch], 0
0x18000cb04  jnz     loc_18000CCAA
0x18000cb0a  inc     dword ptr [rbx+38h]
0x18000cb0d  mov     rcx, [rbx+48h]; hEvent
0x18000cb11  call    cs:__imp_ResetEvent
0x18000cb17  test    eax, eax
0x18000cb19  jz      loc_18000CCD5
0x18000cb1f  mov     rax, [rbx]
0x18000cb22  mov     rcx, rbx
0x18000cb25  mov     rax, [rax+8]
0x18000cb29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb2e  nop
0x18000cb2f  mov     rbp, [r14+30h]
0x18000cb33  test    rbp, rbp
0x18000cb36  jz      loc_18000CCF7
0x18000cb3c  mov     rax, [rbp+8]
0x18000cb40  xor     r8d, r8d
0x18000cb43  xor     edx, edx
0x18000cb45  lea     rcx, [rbp+8]
0x18000cb49  mov     rax, [rax]
0x18000cb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb51  inc     dword ptr [rbp+40h]
0x18000cb54  mov     rax, [rbp+8]
0x18000cb58  lea     rcx, [rbp+8]
0x18000cb5c  mov     rax, [rax+8]
0x18000cb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb65  nop
0x18000cb66  mov     rsi, [r14+30h]
0x18000cb6a  mov     rax, [rbx]
0x18000cb6d  mov     rcx, rbx
0x18000cb70  mov     rax, [rax+10h]
0x18000cb74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb79  test    eax, eax
0x18000cb7b  jnz     short loc_18000CBB8
0x18000cb7d  mov     rax, [rbx]
0x18000cb80  xor     r8d, r8d
0x18000cb83  xor     edx, edx
0x18000cb85  mov     rcx, rbx
0x18000cb88  mov     rax, [rax]
0x18000cb8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb90  add     dword ptr [rbx+38h], 0FFFFFFFFh
0x18000cb94  jnz     short loc_18000CBA8
0x18000cb96  mov     rcx, [rbx+48h]; hEvent
0x18000cb9a  call    cs:__imp_SetEvent
0x18000cba0  test    eax, eax
0x18000cba2  jz      loc_18000CD17
0x18000cba8  mov     rax, [rbx]
0x18000cbab  mov     rcx, rbx
0x18000cbae  mov     rax, [rax+8]
0x18000cbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbb7  nop
0x18000cbb8  mov     [r15], rsi
0x18000cbbb  test    r15, r15
0x18000cbbe  jz      loc_18000CD41
0x18000cbc4  mov     rcx, [rdi]
0x18000cbc7  mov     rax, [rcx+8]
0x18000cbcb  mov     rcx, rdi
0x18000cbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbd3  nop
0x18000cbd4  mov     rax, r15
0x18000cbd7  mov     rbx, [rsp+78h+arg_0]
0x18000cbdf  add     rsp, 50h
0x18000cbe3  pop     r15
0x18000cbe5  pop     r14
0x18000cbe7  pop     rdi
0x18000cbe8  pop     rsi
0x18000cbe9  pop     rbp
0x18000cbea  retn
0x18000cbeb  mov     rdx, [r14+10h]
0x18000cbef  jmp     loc_18000CA17
0x18000cbf4  test    rbp, rbp
0x18000cbf7  jz      loc_18000CA44
0x18000cbfd  mov     rax, [r14]
0x18000cc00  mov     rcx, r14
0x18000cc03  mov     rax, [rax+38h]
0x18000cc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc0c  mov     rcx, rax; pSid1
0x18000cc0f  mov     rdx, rbp; pSid2
0x18000cc12  call    cs:__imp_EqualSid
0x18000cc18  test    eax, eax
0x18000cc1a  jnz     loc_18000CA44
0x18000cc20  mov     dword ptr [rsp+78h+pExceptionObject], 80100009h
0x18000cc2b  lea     rdx, _TI1K; pThrowInfo
0x18000cc32  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000cc3a  call    _CxxThrowException_0
0x18000cc40  mov     dword ptr [rsp+78h+pExceptionObject], 80100009h
0x18000cc4b  lea     rdx, _TI1K; pThrowInfo
0x18000cc52  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000cc5a  call    _CxxThrowException_0
0x18000cc60  cmp     eax, 2
0x18000cc63  jnz     loc_18000CACB
0x18000cc69  mov     dword ptr [rsp+78h+pExceptionObject], 80100002h
0x18000cc74  lea     rdx, _TI1K; pThrowInfo
0x18000cc7b  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000cc83  call    _CxxThrowException_0
0x18000cc89  inc     dword ptr [rbx+38h]
0x18000cc8c  mov     rcx, rbx; this
0x18000cc8f  call    ?UnsignalNoReaders@CAccessLock@@IEAAXXZ; CAccessLock::UnsignalNoReaders(void)
0x18000cc94  nop
0x18000cc95  mov     rax, [rbx]
0x18000cc98  mov     rcx, rbx
0x18000cc9b  mov     rax, [rax+8]
0x18000cc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca4  nop
0x18000cca5  jmp     loc_18000CB2F
0x18000ccaa  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000ccb0  call    cs:__imp_TlsGetValue
0x18000ccb6  cmp     [rbx+68h], rax
0x18000ccba  jz      loc_18000CB0A
0x18000ccc0  mov     rax, [rbx]
0x18000ccc3  mov     rcx, rbx
0x18000ccc6  mov     rax, [rax+8]
0x18000ccca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cccf  nop
0x18000ccd0  jmp     loc_18000CAB8
0x18000ccd5  call    cs:__imp_GetLastError
0x18000ccdb  mov     dword ptr [rsp+78h+pExceptionObject], eax
0x18000cce2  lea     rdx, _TI1K; pThrowInfo
0x18000cce9  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000ccf1  call    _CxxThrowException_0
0x18000ccf7  mov     dword ptr [rsp+78h+pExceptionObject], 80100017h
0x18000cd02  lea     rdx, _TI1K; pThrowInfo
0x18000cd09  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000cd11  call    _CxxThrowException_0
0x18000cd17  call    cs:__imp_GetLastError
0x18000cd1d  mov     dword ptr [rsp+78h+pExceptionObject], eax
0x18000cd24  lea     rdx, _TI1K; pThrowInfo
0x18000cd2b  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000cd33  call    _CxxThrowException_0
0x18000cd39  xor     r15d, r15d
0x18000cd3c  jmp     loc_18000CBBB
0x18000cd41  xor     r8d, r8d; unsigned __int16 *
0x18000cd44  mov     edx, 0CBh; unsigned int
0x18000cd49  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18000cd4e  mov     dword ptr [rsp+78h+pExceptionObject], 80100006h
0x18000cd59  lea     rdx, _TI1K; pThrowInfo
0x18000cd60  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000cd68  call    _CxxThrowException_0
```
