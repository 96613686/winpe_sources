# CImpIADOSecurity::~CImpIADOSecurity(void)

- ea: `0x180029248`
- end: `0x18002929c`
- name: `??1CImpIADOSecurity@@QEAA@XZ`
- size: `84`
- prototype: `void __fastcall(CImpIADOSecurity *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013aa8`
- `0x18002ebd3`

## callees

- `0x180029930`
- `0x1800299a0`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x180029295`

## pseudocode

```c
void __fastcall CImpIADOSecurity::~CImpIADOSecurity(CImpIADOSecurity *this)
{
  *(_QWORD *)this = &CImpIADOSecurity::`vftable'{for `IADOSecurity'};
  *((_QWORD *)this + 1) = &CImpIADOSecurity::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 2) = &CImpIADOSecurity::`vftable'{for `IObjectSafety'};
  CImpIADOSecurity::SetURL(this, 0);
  CImpIADOSecurity::SetSite((CImpIADOSecurity *)((char *)this + 8), 0);
  MPDeleteCriticalSection((char *)this + 48);
}

```

## disassembly

```asm
0x180029248  mov     [rsp+arg_0], rbx
0x18002924d  push    rdi
0x18002924e  sub     rsp, 20h
0x180029252  lea     rax, ??_7CImpIADOSecurity@@6BIADOSecurity@@@; const CImpIADOSecurity::`vftable'{for `IADOSecurity'}
0x180029259  xor     edx, edx; unsigned __int16 *
0x18002925b  mov     [rcx], rax
0x18002925e  mov     rdi, rcx
0x180029261  lea     rax, ??_7CImpIADOSecurity@@6BIObjectWithSite@@@; const CImpIADOSecurity::`vftable'{for `IObjectWithSite'}
0x180029268  mov     [rcx+8], rax
0x18002926c  lea     rax, ??_7CImpIADOSecurity@@6BIObjectSafety@@@; const CImpIADOSecurity::`vftable'{for `IObjectSafety'}
0x180029273  mov     [rcx+10h], rax
0x180029277  call    ?SetURL@CImpIADOSecurity@@UEAAJPEAG@Z; CImpIADOSecurity::SetURL(ushort *)
0x18002927c  xor     edx, edx; struct IUnknown *
0x18002927e  lea     rcx, [rdi+8]; this
0x180029282  call    ?SetSite@CImpIADOSecurity@@UEAAJPEAUIUnknown@@@Z; CImpIADOSecurity::SetSite(IUnknown *)
0x180029287  lea     rcx, [rdi+30h]
0x18002928b  mov     rbx, [rsp+28h+arg_0]
0x180029290  add     rsp, 20h
0x180029294  pop     rdi
0x180029295  jmp     cs:__imp_MPDeleteCriticalSection
```
