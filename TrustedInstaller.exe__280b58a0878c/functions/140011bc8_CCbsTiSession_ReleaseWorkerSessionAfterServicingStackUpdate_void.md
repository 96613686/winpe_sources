# CCbsTiSession::ReleaseWorkerSessionAfterServicingStackUpdate(void)

- ea: `0x140011bc8`
- end: `0x140011c16`
- name: `?ReleaseWorkerSessionAfterServicingStackUpdate@CCbsTiSession@@QEAAXXZ`
- size: `78`
- prototype: `void __fastcall(CCbsTiSession *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000fbc4`
- `0x1400128e4`

## callees

- `0x140006778`
- `0x14000e2ac`
- `0x140011bc8`
- `0x14002b010`

## pseudocode

```c
void __fastcall CCbsTiSession::ReleaseWorkerSessionAfterServicingStackUpdate(CCbsTiSession *this)
{
  __int64 v2; // rcx
  _BYTE v3[40]; // [rsp+20h] [rbp-28h] BYREF

  CritSecLocker::CritSecLocker((CritSecLocker *)v3, (CCbsTiSession *)((char *)this + 48), 1);
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 5) = 0;
  }
  *((_DWORD *)this + 29) = 0;
  CritSecLocker::~CritSecLocker((CritSecLocker *)v3);
}

```

## disassembly

```asm
0x140011bc8  push    rbx
0x140011bca  sub     rsp, 40h
0x140011bce  mov     rbx, rcx
0x140011bd1  lea     rdx, [rcx+30h]; struct AutoCritSec *
0x140011bd5  lea     rcx, [rsp+48h+var_28]; this
0x140011bda  mov     r8b, 1; bool
0x140011bdd  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x140011be2  mov     rcx, [rbx+28h]
0x140011be6  test    rcx, rcx
0x140011be9  jz      short loc_140011BFF
0x140011beb  mov     rax, [rcx]
0x140011bee  mov     rax, [rax+10h]
0x140011bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011bf7  mov     qword ptr [rbx+28h], 0
0x140011bff  lea     rcx, [rsp+48h+var_28]; this
0x140011c04  mov     dword ptr [rbx+74h], 0
0x140011c0b  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x140011c10  add     rsp, 40h
0x140011c14  pop     rbx
0x140011c15  retn
```
