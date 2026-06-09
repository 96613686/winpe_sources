# CPhotoPropertyStore::Commit(void)

- ea: `0x18001c5d0`
- end: `0x18001c682`
- name: `?Commit@CPhotoPropertyStore@@UEAAJXZ`
- size: `178`
- prototype: `__int64 __fastcall(CPhotoPropertyStore *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002470`
- `0x180005328`
- `0x1800110b8`
- `0x18001a658`
- `0x18001c5d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c66a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c66a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c5e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c5e6`

## pseudocode

```c
__int64 __fastcall CPhotoPropertyStore::Commit(struct _RTL_CRITICAL_SECTION *this)
{
  const struct _GUID *v2; // rcx
  unsigned __int64 v3; // r8
  const struct _GUID *v4; // rcx
  int v5; // ebx
  int v6; // eax
  unsigned __int64 v7; // r8

  EnterCriticalSection(this + 2);
  v3 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v3 )
    ShellPrivateTraceEvent(v2, 8u, v3, 1u);
  v5 = CPhotoPropertyStore::_RealInitialize((CPhotoPropertyStore *)&this[-1].LockSemaphore);
  if ( v5 >= 0 )
  {
    if ( ((__int64)this[3].OwningThread & 3) != 0 )
    {
      v6 = CMetadataContainer::Commit((CMetadataContainer *)&this[4].LockSemaphore);
      HIDWORD(this[4].DebugInfo) = 1;
      v5 = v6;
      ATL::CComPtrBase<IStream>::Release(&this[3].DebugInfo);
    }
    else
    {
      v5 = -2147287035;
    }
  }
  v7 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v7 )
    ShellPrivateTraceEvent(v4, 8u, v7, 2u);
  LeaveCriticalSection(this + 2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001c5d0  mov     [rsp+arg_0], rbx
0x18001c5d5  mov     [rsp+arg_8], rsi
0x18001c5da  push    rdi
0x18001c5db  sub     rsp, 20h
0x18001c5df  mov     rdi, rcx
0x18001c5e2  add     rcx, 50h ; 'P'; lpCriticalSection
0x18001c5e6  call    cs:__imp_EnterCriticalSection
0x18001c5ec  mov     rax, cs:WPP_GLOBAL_Control
0x18001c5f3  mov     r8, [rax+38h]; unsigned __int64
0x18001c5f7  test    r8, r8
0x18001c5fa  jz      short loc_18001C609
0x18001c5fc  mov     r9b, 1; unsigned __int8
0x18001c5ff  mov     edx, 8; unsigned int
0x18001c604  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001c609  lea     rcx, [rdi-10h]; this
0x18001c60d  call    ?_RealInitialize@CPhotoPropertyStore@@AEAAJXZ; CPhotoPropertyStore::_RealInitialize(void)
0x18001c612  mov     ebx, eax
0x18001c614  test    eax, eax
0x18001c616  js      short loc_18001C649
0x18001c618  test    byte ptr [rdi+88h], 3
0x18001c61f  jz      short loc_18001C644
0x18001c621  lea     rcx, [rdi+0B8h]; this
0x18001c628  call    ?Commit@CMetadataContainer@@QEAAJXZ; CMetadataContainer::Commit(void)
0x18001c62d  lea     rcx, [rdi+78h]
0x18001c631  mov     dword ptr [rdi+0A4h], 1
0x18001c63b  mov     ebx, eax
0x18001c63d  call    ?Release@?$CComPtrBase@UIStream@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IStream>::Release(void)
0x18001c642  jmp     short loc_18001C649
0x18001c644  mov     ebx, 80030005h
0x18001c649  mov     rax, cs:WPP_GLOBAL_Control
0x18001c650  mov     r8, [rax+38h]; unsigned __int64
0x18001c654  test    r8, r8
0x18001c657  jz      short loc_18001C666
0x18001c659  mov     r9b, 2; unsigned __int8
0x18001c65c  mov     edx, 8; unsigned int
0x18001c661  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001c666  lea     rcx, [rdi+50h]; lpCriticalSection
0x18001c66a  call    cs:__imp_LeaveCriticalSection
0x18001c670  mov     rsi, [rsp+28h+arg_8]
0x18001c675  mov     eax, ebx
0x18001c677  mov     rbx, [rsp+28h+arg_0]
0x18001c67c  add     rsp, 20h
0x18001c680  pop     rdi
0x18001c681  retn
```
