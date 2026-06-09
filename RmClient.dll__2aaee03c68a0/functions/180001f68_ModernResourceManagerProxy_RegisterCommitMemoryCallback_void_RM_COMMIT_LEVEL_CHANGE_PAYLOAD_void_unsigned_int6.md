# ModernResourceManagerProxy::RegisterCommitMemoryCallback(void (*)(_RM_COMMIT_LEVEL_CHANGE_PAYLOAD *),void (*)(unsigned __int64,unsigned __int64))

- ea: `0x180001f68`
- end: `0x180001fe7`
- name: `?RegisterCommitMemoryCallback@ModernResourceManagerProxy@@QEAAJP6AXPEAU_RM_COMMIT_LEVEL_CHANGE_PAYLOAD@@@ZP6AX_K2@Z@Z`
- size: `127`
- prototype: `__int64 __fastcall(ModernResourceManagerProxy *__hidden this, void (*)(struct _RM_COMMIT_LEVEL_CHANGE_PAYLOAD *), void (*)(unsigned __int64, unsigned __int64))`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002750`
- `0x180002860`

## callees

- `0x180001d14`
- `0x180001f68`
- `0x180002cb0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001fcb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001fcb`

## pseudocode

```c
__int64 __fastcall ModernResourceManagerProxy::RegisterCommitMemoryCallback(
        ModernResourceManagerProxy *this,
        void (*a2)(struct _RM_COMMIT_LEVEL_CHANGE_PAYLOAD *),
        void (*a3)(unsigned __int64, unsigned __int64))
{
  _QWORD *v4; // rbx
  int v5; // edi

  CempLockAcquireExclusive((char *)this + 96, a2, a3);
  v4 = (_QWORD *)((char *)this + 32);
  if ( *(_OWORD *)((char *)this + 24) == 0 )
  {
    *((_QWORD *)this + 3) = Windows::System::CMemoryManager::OnCommitLevelChangeRoutine;
    *v4 = Windows::System::CMemoryManager::OnCommitLimitChangeRoutine;
    v5 = ModernResourceManagerProxy::RegisterWithServer(this);
    if ( v5 >= 0 )
    {
      v5 = 0;
      goto LABEL_4;
    }
  }
  else
  {
    v5 = -2147483635;
  }
  *((_QWORD *)this + 3) = 0;
  *v4 = 0;
LABEL_4:
  *((_DWORD *)this + 26) = 0;
  RtlReleaseSRWLockExclusive((char *)this + 96);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001f68  push    rbx
0x180001f6a  push    rbp
0x180001f6b  push    rsi
0x180001f6c  push    rdi
0x180001f6d  sub     rsp, 28h
0x180001f71  mov     rsi, rcx
0x180001f74  add     rcx, 60h ; '`'
0x180001f78  call    CempLockAcquireExclusive
0x180001f7d  cmp     qword ptr [rsi+18h], 0
0x180001f82  lea     rbx, [rsi+20h]
0x180001f86  jnz     short loc_180001FDC
0x180001f88  cmp     qword ptr [rbx], 0
0x180001f8c  jnz     short loc_180001FDC
0x180001f8e  lea     rax, ?OnCommitLevelChangeRoutine@CMemoryManager@System@Windows@@CAXPEAU_RM_COMMIT_LEVEL_CHANGE_PAYLOAD@@@Z; Windows::System::CMemoryManager::OnCommitLevelChangeRoutine(_RM_COMMIT_LEVEL_CHANGE_PAYLOAD *)
0x180001f95  mov     rcx, rsi; this
0x180001f98  mov     [rsi+18h], rax
0x180001f9c  lea     rax, ?OnCommitLimitChangeRoutine@CMemoryManager@System@Windows@@CAX_K0@Z; Windows::System::CMemoryManager::OnCommitLimitChangeRoutine(unsigned __int64,unsigned __int64)
0x180001fa3  mov     [rbx], rax
0x180001fa6  call    ?RegisterWithServer@ModernResourceManagerProxy@@IEAAJXZ; ModernResourceManagerProxy::RegisterWithServer(void)
0x180001fab  mov     edi, eax
0x180001fad  test    eax, eax
0x180001faf  jns     short loc_180001FE3
0x180001fb1  mov     qword ptr [rsi+18h], 0
0x180001fb9  mov     qword ptr [rbx], 0
0x180001fc0  lea     rcx, [rsi+60h]
0x180001fc4  mov     dword ptr [rsi+68h], 0
0x180001fcb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001fd1  mov     eax, edi
0x180001fd3  add     rsp, 28h
0x180001fd7  pop     rdi
0x180001fd8  pop     rsi
0x180001fd9  pop     rbp
0x180001fda  pop     rbx
0x180001fdb  retn
0x180001fdc  mov     edi, 8000000Dh
0x180001fe1  jmp     short loc_180001FB1
0x180001fe3  xor     edi, edi
0x180001fe5  jmp     short loc_180001FC0
```
