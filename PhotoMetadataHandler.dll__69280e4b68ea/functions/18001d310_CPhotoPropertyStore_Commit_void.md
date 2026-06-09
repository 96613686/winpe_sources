# CPhotoPropertyStore::Commit(void)

- ea: `0x18001d310`
- end: `0x18001d3cf`
- name: `?Commit@CPhotoPropertyStore@@UEAAJXZ`
- size: `191`
- prototype: `__int64 __fastcall(CPhotoPropertyStore *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002540`
- `0x180005440`
- `0x18001186c`
- `0x18001b2f8`
- `0x18001d310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d3b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d3b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d326`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d326`

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
0x18001d310  mov     [rsp+arg_0], rbx
0x18001d315  mov     [rsp+arg_8], rsi
0x18001d31a  push    rdi
0x18001d31b  sub     rsp, 20h
0x18001d31f  mov     rdi, rcx
0x18001d322  add     rcx, 50h ; 'P'; lpCriticalSection
0x18001d326  call    cs:__imp_EnterCriticalSection
0x18001d32d  nop     dword ptr [rax+rax+00h]
0x18001d332  mov     rax, cs:WPP_GLOBAL_Control
0x18001d339  mov     r8, [rax+38h]; unsigned __int64
0x18001d33d  test    r8, r8
0x18001d340  jz      short loc_18001D34F
0x18001d342  mov     r9b, 1; unsigned __int8
0x18001d345  mov     edx, 8; unsigned int
0x18001d34a  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001d34f  lea     rcx, [rdi-10h]; this
0x18001d353  call    ?_RealInitialize@CPhotoPropertyStore@@AEAAJXZ; CPhotoPropertyStore::_RealInitialize(void)
0x18001d358  mov     ebx, eax
0x18001d35a  test    eax, eax
0x18001d35c  js      short loc_18001D38F
0x18001d35e  test    byte ptr [rdi+88h], 3
0x18001d365  jz      short loc_18001D38A
0x18001d367  lea     rcx, [rdi+0B8h]; this
0x18001d36e  call    ?Commit@CMetadataContainer@@QEAAJXZ; CMetadataContainer::Commit(void)
0x18001d373  lea     rcx, [rdi+78h]
0x18001d377  mov     dword ptr [rdi+0A4h], 1
0x18001d381  mov     ebx, eax
0x18001d383  call    ?Release@?$CComPtrBase@UIStream@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IStream>::Release(void)
0x18001d388  jmp     short loc_18001D38F
0x18001d38a  mov     ebx, 80030005h
0x18001d38f  mov     rax, cs:WPP_GLOBAL_Control
0x18001d396  mov     r8, [rax+38h]; unsigned __int64
0x18001d39a  test    r8, r8
0x18001d39d  jz      short loc_18001D3AC
0x18001d39f  mov     r9b, 2; unsigned __int8
0x18001d3a2  mov     edx, 8; unsigned int
0x18001d3a7  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18001d3ac  lea     rcx, [rdi+50h]; lpCriticalSection
0x18001d3b0  call    cs:__imp_LeaveCriticalSection
0x18001d3b7  nop     dword ptr [rax+rax+00h]
0x18001d3bc  mov     rsi, [rsp+28h+arg_8]
0x18001d3c1  mov     eax, ebx
0x18001d3c3  mov     rbx, [rsp+28h+arg_0]
0x18001d3c8  add     rsp, 20h
0x18001d3cc  pop     rdi
0x18001d3cd  retn
```
