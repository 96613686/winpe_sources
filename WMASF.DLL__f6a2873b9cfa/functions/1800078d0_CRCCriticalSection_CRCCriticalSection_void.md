# CRCCriticalSection::~CRCCriticalSection(void)

- ea: `0x1800078d0`
- end: `0x180007909`
- name: `??1CRCCriticalSection@@UEAA@XZ`
- size: `57`
- prototype: `void __fastcall(CRCCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800079dc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800078f2`
- `KERNEL32!DeleteCriticalSection` at `0x1800078f2`

## pseudocode

```c
void __fastcall CRCCriticalSection::~CRCCriticalSection(CRCCriticalSection *this)
{
  *(_QWORD *)this = &CRCCriticalSection::`vftable'{for `IWMSCriticalSection'};
  *((_QWORD *)this + 1) = &CRCCriticalSection::`vftable'{for `CPoolReleaseItem'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *((_QWORD *)this + 1) = &CPoolReleaseItem::`vftable';
}

```

## disassembly

```asm
0x1800078d0  push    rbx
0x1800078d2  sub     rsp, 20h
0x1800078d6  lea     rax, ??_7CRCCriticalSection@@6BIWMSCriticalSection@@@; const CRCCriticalSection::`vftable'{for `IWMSCriticalSection'}
0x1800078dd  mov     rbx, rcx
0x1800078e0  mov     [rcx], rax
0x1800078e3  lea     rax, ??_7CRCCriticalSection@@6BCPoolReleaseItem@@@; const CRCCriticalSection::`vftable'{for `CPoolReleaseItem'}
0x1800078ea  mov     [rcx+8], rax
0x1800078ee  add     rcx, 20h ; ' '; lpCriticalSection
0x1800078f2  call    cs:__imp_DeleteCriticalSection
0x1800078f8  lea     rax, ??_7CPoolReleaseItem@@6B@; const CPoolReleaseItem::`vftable'
0x1800078ff  mov     [rbx+8], rax
0x180007903  add     rsp, 20h
0x180007907  pop     rbx
0x180007908  retn
```
