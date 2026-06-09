# DiagHubCommon::AutoSrwLock::~AutoSrwLock(void)

- ea: `0x140007ab0`
- end: `0x140007adf`
- name: `??1AutoSrwLock@DiagHubCommon@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(DiagHubCommon::AutoSrwLock *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140014e32`
- `0x140014e98`
- `0x140014eda`
- `0x140015084`

## callees

- `0x140007ab0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140007ad4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140007ad4`
- `KERNEL32!ReleaseSRWLockShared` at `0x140007ac5`

## pseudocode

```c
void __fastcall DiagHubCommon::AutoSrwLock::~AutoSrwLock(DiagHubCommon::AutoSrwLock *this)
{
  int v1; // edx

  v1 = *((_DWORD *)this + 2);
  if ( v1 )
  {
    if ( v1 == 1 )
      ReleaseSRWLockExclusive(*(PSRWLOCK *)this);
  }
  else
  {
    ReleaseSRWLockShared(*(PSRWLOCK *)this);
  }
}

```

## disassembly

```asm
0x140007ab0  sub     rsp, 28h
0x140007ab4  mov     edx, [rcx+8]
0x140007ab7  mov     rax, [rcx]
0x140007aba  test    edx, edx
0x140007abc  jnz     short loc_140007ACC
0x140007abe  mov     rcx, rax
0x140007ac1  add     rsp, 28h
0x140007ac5  jmp     cs:__imp_ReleaseSRWLockShared
0x140007acc  cmp     edx, 1
0x140007acf  jnz     short loc_140007ADA
0x140007ad1  mov     rcx, rax; SRWLock
0x140007ad4  call    cs:__imp_ReleaseSRWLockExclusive
0x140007ada  add     rsp, 28h
0x140007ade  retn
```
