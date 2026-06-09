# CSharedReaderWriterLock::LockWrite(void)

- ea: `0x1400051e0`
- end: `0x14000531d`
- name: `?LockWrite@CSharedReaderWriterLock@@QEAAXXZ`
- size: `317`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x140004730`
- `0x14000fb90`
- `0x140027f40`
- `0x140043370`
- `0x14004c234`
- `0x14007cea0`
- `0x14007cef0`
- `0x14007cf40`
- `0x14007cf90`

## callees

- `0x1400051e0`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000520a`
- `KERNEL32!GetCurrentThreadId` at `0x1400052e5`
- `KERNEL32!GetCurrentThreadId` at `0x14000520a`
- `KERNEL32!GetCurrentThreadId` at `0x1400052e5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140005244`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140005244`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x1400051ed`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x1400051ed`
- `KERNEL32!IsDebuggerPresent` at `0x140005287`
- `KERNEL32!IsDebuggerPresent` at `0x140005287`

## string_xrefs

- `0x140005235`: `CSharedReaderWriterLock::LockWrite - Waiting for SRW write lock %s, owner = 0x%X (contention count = %d).\n`
- `0x14000526a`: `m_tidWriteLockOwner == 0`
- `0x14000525e`: `CSharedReaderWriterLock::LockWrite`
- `0x140005307`: `CSharedReaderWriterLock::LockWrite - SRW write lock %s acquired (contention count = %d)\n`
- `0x14000527b`: `termsrv\wms\Src\inc\SrcSharedReaderWriterLock.h`
- `0x14000529d`: `termsrv\wms\Src\inc\SrcSharedReaderWriterLock.h`
- `0x1400052c7`: `termsrv\wms\Src\inc\SrcSharedReaderWriterLock.h`

## pseudocode

```c
void __fastcall CSharedReaderWriterLock::LockWrite(PSRWLOCK SRWLock)
{
  int Ptr; // ebx
  const unsigned __int16 *v3; // r9
  DWORD CurrentThreadId; // eax
  int Ptr_high; // r8d

  if ( !TryAcquireSRWLockExclusive(SRWLock) )
  {
    if ( !LODWORD(SRWLock[33].Ptr) || (Ptr = (int)SRWLock[33].Ptr, Ptr != GetCurrentThreadId()) )
    {
      DEBUGMSG(
        L"CSharedReaderWriterLock::LockWrite - Waiting for SRW write lock %s, owner = 0x%X (contention count = %d).\n",
        &SRWLock[1],
        LODWORD(SRWLock[33].Ptr),
        (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&SRWLock[33].Ptr + 1));
      AcquireSRWLockExclusive(SRWLock);
      _InterlockedDecrement((volatile signed __int32 *)&SRWLock[33].Ptr + 1);
      if ( LODWORD(SRWLock[33].Ptr) )
      {
        LOGASSERT(
          L"termsrv\\wms\\Src\\inc\\SrcSharedReaderWriterLock.h",
          0x3Au,
          L"CSharedReaderWriterLock::LockWrite",
          v3,
          L"m_tidWriteLockOwner == 0");
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
            L"termsrv\\wms\\Src\\inc\\SrcSharedReaderWriterLock.h",
            58,
            L"CSharedReaderWriterLock::LockWrite",
            L"ASSERT",
            L"m_tidWriteLockOwner == 0");
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
            L"termsrv\\wms\\Src\\inc\\SrcSharedReaderWriterLock.h",
            58,
            L"CSharedReaderWriterLock::LockWrite",
            L"ASSERT",
            L"m_tidWriteLockOwner == 0");
      }
    }
  }
  CurrentThreadId = GetCurrentThreadId();
  ++LODWORD(SRWLock[34].Ptr);
  Ptr_high = HIDWORD(SRWLock[33].Ptr);
  LODWORD(SRWLock[33].Ptr) = CurrentThreadId;
  if ( Ptr_high )
    DEBUGMSG(L"CSharedReaderWriterLock::LockWrite - SRW write lock %s acquired (contention count = %d)\n", &SRWLock[1]);
}

```

## disassembly

```asm
0x1400051e0  push    rbx
0x1400051e2  push    rbp
0x1400051e3  push    rdi
0x1400051e4  push    r14
0x1400051e6  sub     rsp, 48h
0x1400051ea  mov     rdi, rcx
0x1400051ed  call    cs:__imp_TryAcquireSRWLockExclusive
0x1400051f3  test    al, al
0x1400051f5  jnz     loc_1400052E5
0x1400051fb  cmp     dword ptr [rdi+108h], 0
0x140005202  jz      short loc_140005218
0x140005204  mov     ebx, [rdi+108h]
0x14000520a  call    cs:__imp_GetCurrentThreadId
0x140005210  cmp     ebx, eax
0x140005212  jz      loc_1400052E5
0x140005218  mov     r9d, 1
0x14000521e  lock xadd [rdi+10Ch], r9d
0x140005227  mov     r8d, [rdi+108h]
0x14000522e  lea     rdx, [rdi+8]
0x140005232  inc     r9d
0x140005235  lea     rcx, aCsharedreaderw_3; "CSharedReaderWriterLock::LockWrite - Wa"...
0x14000523c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140005241  mov     rcx, rdi; SRWLock
0x140005244  call    cs:__imp_AcquireSRWLockExclusive
0x14000524a  lock dec dword ptr [rdi+10Ch]
0x140005251  cmp     dword ptr [rdi+108h], 0
0x140005258  jz      loc_1400052E5
0x14000525e  lea     rbp, aCsharedreaderw; "CSharedReaderWriterLock::LockWrite"
0x140005265  mov     ebx, 3Ah ; ':'
0x14000526a  lea     r14, aMTidwritelocko; "m_tidWriteLockOwner == 0"
0x140005271  mov     r8, rbp; unsigned __int16 *
0x140005274  mov     edx, ebx; unsigned int
0x140005276  mov     [rsp+68h+var_48], r14; unsigned __int16 *
0x14000527b  lea     rcx, aTermsrvWmsSrcI; "termsrv\\wms\\Src\\inc\\SrcSharedReader"...
0x140005282  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140005287  call    cs:__imp_IsDebuggerPresent
0x14000528d  test    eax, eax
0x14000528f  lea     rax, aAssert; "ASSERT"
0x140005296  jz      short loc_1400052C2
0x140005298  mov     [rsp+68h+var_38], r14
0x14000529d  lea     r8, aTermsrvWmsSrcI; "termsrv\\wms\\Src\\inc\\SrcSharedReader"...
0x1400052a4  mov     [rsp+68h+var_40], rax
0x1400052a9  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400052b0  mov     r9d, ebx
0x1400052b3  mov     [rsp+68h+var_48], rbp
0x1400052b8  lea     ecx, [rbx-38h]; unsigned __int8
0x1400052bb  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400052c0  jmp     short loc_1400052E5
0x1400052c2  mov     [rsp+68h+var_40], r14
0x1400052c7  lea     rdx, aTermsrvWmsSrcI; "termsrv\\wms\\Src\\inc\\SrcSharedReader"...
0x1400052ce  mov     r9, rbp
0x1400052d1  mov     [rsp+68h+var_48], rax
0x1400052d6  mov     r8d, ebx
0x1400052d9  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400052e0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400052e5  call    cs:__imp_GetCurrentThreadId
0x1400052eb  inc     dword ptr [rdi+110h]
0x1400052f1  mov     r8d, [rdi+10Ch]
0x1400052f8  mov     [rdi+108h], eax
0x1400052fe  test    r8d, r8d
0x140005301  jz      short loc_140005313
0x140005303  lea     rdx, [rdi+8]
0x140005307  lea     rcx, aCsharedreaderw_1; "CSharedReaderWriterLock::LockWrite - SR"...
0x14000530e  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140005313  add     rsp, 48h
0x140005317  pop     r14
0x140005319  pop     rdi
0x14000531a  pop     rbp
0x14000531b  pop     rbx
0x14000531c  retn
```
