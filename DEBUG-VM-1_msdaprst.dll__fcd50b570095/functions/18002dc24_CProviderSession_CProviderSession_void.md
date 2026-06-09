# CProviderSession::~CProviderSession(void)

- ea: `0x18002dc24`
- end: `0x18002dc9f`
- name: `??1CProviderSession@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(CProviderSession *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180020c38`
- `0x18002f08a`

## callees

- `0x18002dc24`
- `0x180030010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18002dc89`
- `MSDART!MPDeleteCriticalSection` at `0x18002dc89`
- `MSDART!MPDeleteCriticalSection` at `0x18002dc98`

## pseudocode

```c
void __fastcall CProviderSession::~CProviderSession(CProviderSession *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CProviderDSO::`vftable'{for `IPersist'};
  *((_QWORD *)this + 1) = &CProviderSession::`vftable'{for `IGetDataSource'};
  *((_QWORD *)this + 2) = &IUpdateInfo::`vftable';
  *((_QWORD *)this + 3) = &CProviderDSO::`vftable'{for `ISupportErrorInfo'};
  v2 = *((_QWORD *)this + 9);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
    *((_QWORD *)this + 9) = 0;
  }
  MPDeleteCriticalSection((char *)this + 48);
  MPDeleteCriticalSection((char *)this + 40);
}

```

## disassembly

```asm
0x18002dc24  push    rbx
0x18002dc26  sub     rsp, 20h
0x18002dc2a  mov     rbx, rcx
0x18002dc2d  lea     rax, ??_7CProviderDSO@@6BIPersist@@@; const CProviderDSO::`vftable'{for `IPersist'}
0x18002dc34  mov     [rcx], rax
0x18002dc37  lea     rax, ??_7CProviderSession@@6BIGetDataSource@@@; const CProviderSession::`vftable'{for `IGetDataSource'}
0x18002dc3e  mov     [rcx+8], rax
0x18002dc42  lea     rax, ??_7IUpdateInfo@@6B@; const IUpdateInfo::`vftable'
0x18002dc49  mov     [rcx+10h], rax
0x18002dc4d  lea     rax, ??_7CProviderDSO@@6BISupportErrorInfo@@@; const CProviderDSO::`vftable'{for `ISupportErrorInfo'}
0x18002dc54  mov     [rcx+18h], rax
0x18002dc58  mov     rcx, [rcx+48h]
0x18002dc5c  test    rcx, rcx
0x18002dc5f  jz      short loc_18002DC85
0x18002dc61  mov     rax, [rcx]
0x18002dc64  mov     rax, [rax+18h]
0x18002dc68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc6d  mov     rcx, [rbx+48h]
0x18002dc71  mov     rax, [rcx]
0x18002dc74  mov     rax, [rax+10h]
0x18002dc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc7d  mov     qword ptr [rbx+48h], 0
0x18002dc85  lea     rcx, [rbx+30h]
0x18002dc89  call    cs:__imp_MPDeleteCriticalSection
0x18002dc8f  lea     rcx, [rbx+28h]
0x18002dc93  add     rsp, 20h
0x18002dc97  pop     rbx
0x18002dc98  jmp     cs:__imp_MPDeleteCriticalSection
```
