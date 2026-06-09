# CProviderDSO::~CProviderDSO(void)

- ea: `0x18002cec4`
- end: `0x18002cf28`
- name: `??1CProviderDSO@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(CProviderDSO *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180013aa8`
- `0x18002ebc1`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18002cf12`
- `MSDART!MPDeleteCriticalSection` at `0x18002cf12`
- `MSDART!MPDeleteCriticalSection` at `0x18002cf21`

## pseudocode

```c
void __fastcall CProviderDSO::~CProviderDSO(CProviderDSO *this)
{
  *(_QWORD *)this = &CProviderDSO::`vftable'{for `IDSOCallBack'};
  *((_QWORD *)this + 1) = &CProviderDSO::`vftable'{for `IPersist'};
  *((_QWORD *)this + 2) = &CProviderDSO::`vftable'{for `IDBInitialize'};
  *((_QWORD *)this + 3) = &CProviderDSO::`vftable'{for `IDBProperties'};
  *((_QWORD *)this + 4) = &CProviderDSO::`vftable'{for `IPersist'};
  *((_QWORD *)this + 5) = &CProviderDSO::`vftable'{for `ISupportErrorInfo'};
  MPDeleteCriticalSection((char *)this + 72);
  MPDeleteCriticalSection((char *)this + 56);
}

```

## disassembly

```asm
0x18002cec4  push    rbx
0x18002cec6  sub     rsp, 20h
0x18002ceca  lea     rax, ??_7CProviderDSO@@6BIDSOCallBack@@@; const CProviderDSO::`vftable'{for `IDSOCallBack'}
0x18002ced1  mov     rbx, rcx
0x18002ced4  mov     [rcx], rax
0x18002ced7  lea     rax, ??_7CProviderDSO@@6BIPersist@@@; const CProviderDSO::`vftable'{for `IPersist'}
0x18002cede  mov     [rcx+8], rax
0x18002cee2  lea     rax, ??_7CProviderDSO@@6BIDBInitialize@@@; const CProviderDSO::`vftable'{for `IDBInitialize'}
0x18002cee9  mov     [rcx+10h], rax
0x18002ceed  lea     rax, ??_7CProviderDSO@@6BIDBProperties@@@; const CProviderDSO::`vftable'{for `IDBProperties'}
0x18002cef4  mov     [rcx+18h], rax
0x18002cef8  lea     rax, ??_7CProviderDSO@@6BIPersist@@@; const CProviderDSO::`vftable'{for `IPersist'}
0x18002ceff  mov     [rcx+20h], rax
0x18002cf03  lea     rax, ??_7CProviderDSO@@6BISupportErrorInfo@@@; const CProviderDSO::`vftable'{for `ISupportErrorInfo'}
0x18002cf0a  mov     [rcx+28h], rax
0x18002cf0e  add     rcx, 48h ; 'H'
0x18002cf12  call    cs:__imp_MPDeleteCriticalSection
0x18002cf18  lea     rcx, [rbx+38h]
0x18002cf1c  add     rsp, 20h
0x18002cf20  pop     rbx
0x18002cf21  jmp     cs:__imp_MPDeleteCriticalSection
```
