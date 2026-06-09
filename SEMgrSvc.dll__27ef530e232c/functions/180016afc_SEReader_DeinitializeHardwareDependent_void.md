# SEReader::DeinitializeHardwareDependent(void)

- ea: `0x180016afc`
- end: `0x180016c5f`
- name: `?DeinitializeHardwareDependent@SEReader@@AEAAJXZ`
- size: `355`
- prototype: `__int64 __fastcall(SEReader *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180017094`
- `0x18001752c`
- `0x180017a60`

## callees

- `0x1800049c4`
- `0x180016afc`
- `0x180016c68`
- `0x180017be4`
- `0x18001b844`
- `0x18001fb2c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016c47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016c47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016b2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016b2f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016b75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016bbc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016b75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016bbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SEReader::DeinitializeHardwareDependent(struct _RTL_CRITICAL_SECTION *this)
{
  RfFieldEventHandler *LockSemaphore; // rcx
  RfFieldEventHandler *v3; // rdi
  RfFieldEventHandler *SpinCount; // rcx
  RfFieldEventHandler *v5; // rdi
  NFCConnector *v6; // rcx
  volatile signed __int32 *OwningThread; // rdi

  SEReader::UnregisterFromWNFEvents((SEReader *)this);
  if ( LODWORD(this[5].DebugInfo) )
  {
    EnterCriticalSection(this + 4);
    SEReader::DeinitializeSecureElements((SEReader *)this);
    LockSemaphore = (RfFieldEventHandler *)this[3].LockSemaphore;
    if ( LockSemaphore )
    {
      RfFieldEventHandler::Uninitialize(LockSemaphore);
      v3 = (RfFieldEventHandler *)this[3].LockSemaphore;
      this[3].LockSemaphore = 0;
      if ( v3 )
      {
        RfFieldEventHandler::Uninitialize(v3);
        DeleteCriticalSection((LPCRITICAL_SECTION)v3);
        operator delete(v3);
      }
    }
    SpinCount = (RfFieldEventHandler *)this[3].SpinCount;
    if ( SpinCount )
    {
      RfFieldEventHandler::Uninitialize(SpinCount);
      v5 = (RfFieldEventHandler *)this[3].SpinCount;
      this[3].SpinCount = 0;
      if ( v5 )
      {
        RfFieldEventHandler::Uninitialize(v5);
        DeleteCriticalSection((LPCRITICAL_SECTION)v5);
        operator delete(v5);
      }
    }
    v6 = *(NFCConnector **)&this[5].LockCount;
    if ( v6 )
    {
      NFCConnector::Uninitialize(v6);
      *(_QWORD *)&this[5].LockCount = 0;
      OwningThread = (volatile signed __int32 *)this[5].OwningThread;
      this[5].OwningThread = 0;
      if ( OwningThread )
      {
        if ( _InterlockedExchangeAdd(OwningThread + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))OwningThread)(OwningThread);
          if ( _InterlockedExchangeAdd(OwningThread + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)OwningThread + 8LL))(OwningThread);
        }
      }
    }
    LODWORD(this[5].DebugInfo) = 0;
    LeaveCriticalSection(this + 4);
  }
  return 0;
}

```

## disassembly

```asm
0x180016afc  mov     [rsp+arg_0], rbx
0x180016b01  mov     [rsp+arg_8], rsi
0x180016b06  push    rdi
0x180016b07  sub     rsp, 30h
0x180016b0b  mov     rbx, rcx
0x180016b0e  call    ?UnregisterFromWNFEvents@SEReader@@AEAAJXZ; SEReader::UnregisterFromWNFEvents(void)
0x180016b13  cmp     dword ptr [rbx+0C8h], 0
0x180016b1a  jz      loc_180016C4D
0x180016b20  lea     rsi, [rbx+0A0h]
0x180016b27  mov     [rsp+38h+var_18], rsi
0x180016b2c  mov     rcx, rsi; lpCriticalSection
0x180016b2f  call    cs:__imp_EnterCriticalSection
0x180016b35  mov     [rsp+38h+var_10], 1
0x180016b3a  mov     rcx, rbx; this
0x180016b3d  call    ?DeinitializeSecureElements@SEReader@@AEAAJXZ; SEReader::DeinitializeSecureElements(void)
0x180016b42  mov     rcx, [rbx+90h]; this
0x180016b49  test    rcx, rcx
0x180016b4c  jz      short loc_180016B89
0x180016b4e  call    ?Uninitialize@RfFieldEventHandler@@QEAAXXZ; RfFieldEventHandler::Uninitialize(void)
0x180016b53  mov     rdi, [rbx+90h]
0x180016b5a  mov     qword ptr [rbx+90h], 0
0x180016b65  test    rdi, rdi
0x180016b68  jz      short loc_180016B89
0x180016b6a  mov     rcx, rdi; this
0x180016b6d  call    ?Uninitialize@RfFieldEventHandler@@QEAAXXZ; RfFieldEventHandler::Uninitialize(void)
0x180016b72  mov     rcx, rdi; lpCriticalSection
0x180016b75  call    cs:__imp_DeleteCriticalSection
0x180016b7b  nop
0x180016b7c  mov     edx, 70h ; 'p'
0x180016b81  mov     rcx, rdi; Block
0x180016b84  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016b89  mov     rcx, [rbx+98h]; this
0x180016b90  test    rcx, rcx
0x180016b93  jz      short loc_180016BD0
0x180016b95  call    ?Uninitialize@RfFieldEventHandler@@QEAAXXZ; RfFieldEventHandler::Uninitialize(void)
0x180016b9a  mov     rdi, [rbx+98h]
0x180016ba1  mov     qword ptr [rbx+98h], 0
0x180016bac  test    rdi, rdi
0x180016baf  jz      short loc_180016BD0
0x180016bb1  mov     rcx, rdi; this
0x180016bb4  call    ?Uninitialize@RfFieldEventHandler@@QEAAXXZ; RfFieldEventHandler::Uninitialize(void)
0x180016bb9  mov     rcx, rdi; lpCriticalSection
0x180016bbc  call    cs:__imp_DeleteCriticalSection
0x180016bc2  nop
0x180016bc3  mov     edx, 70h ; 'p'
0x180016bc8  mov     rcx, rdi; Block
0x180016bcb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016bd0  mov     rcx, [rbx+0D0h]; this
0x180016bd7  test    rcx, rcx
0x180016bda  jz      short loc_180016C3A
0x180016bdc  call    ?Uninitialize@NFCConnector@@QEAAJXZ; NFCConnector::Uninitialize(void)
0x180016be1  mov     qword ptr [rbx+0D0h], 0
0x180016bec  mov     rdi, [rbx+0D8h]
0x180016bf3  mov     qword ptr [rbx+0D8h], 0
0x180016bfe  test    rdi, rdi
0x180016c01  jz      short loc_180016C3A
0x180016c03  or      eax, 0FFFFFFFFh
0x180016c06  lock xadd [rdi+8], eax
0x180016c0b  cmp     eax, 1
0x180016c0e  jnz     short loc_180016C3A
0x180016c10  mov     rax, [rdi]
0x180016c13  mov     rcx, rdi
0x180016c16  mov     rax, [rax]
0x180016c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c1e  or      eax, 0FFFFFFFFh
0x180016c21  lock xadd [rdi+0Ch], eax
0x180016c26  cmp     eax, 1
0x180016c29  jnz     short loc_180016C3A
0x180016c2b  mov     rax, [rdi]
0x180016c2e  mov     rcx, rdi
0x180016c31  mov     rax, [rax+8]
0x180016c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c3a  mov     dword ptr [rbx+0C8h], 0
0x180016c44  mov     rcx, rsi; lpCriticalSection
0x180016c47  call    cs:__imp_LeaveCriticalSection
0x180016c4d  xor     eax, eax
0x180016c4f  mov     rbx, [rsp+38h+arg_0]
0x180016c54  mov     rsi, [rsp+38h+arg_8]
0x180016c59  add     rsp, 30h
0x180016c5d  pop     rdi
0x180016c5e  retn
```
