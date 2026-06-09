# CAuthenticatorList::~CAuthenticatorList(void)

- ea: `0x1800838ac`
- end: `0x1800838f3`
- name: `??1CAuthenticatorList@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(CAuthenticatorList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005a258`

## callees

- `0x1800838ac`
- `0x1800838fc`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800838e7`
- `ntdll!RtlDeleteCriticalSection` at `0x1800838e7`

## pseudocode

```c
void __fastcall CAuthenticatorList::~CAuthenticatorList(CAuthenticatorList *this)
{
  union _LARGE_INTEGER v2; // [rsp+30h] [rbp+8h] BYREF
  union _LARGE_INTEGER v3; // [rsp+38h] [rbp+10h] BYREF

  v2.QuadPart = 0;
  v3.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
  CAuthenticatorList::Age((PRTL_GENERIC_TABLE)this, &v3, &v2);
  if ( *((_BYTE *)this + 128) )
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 88));
}

```

## disassembly

```asm
0x1800838ac  mov     rax, rsp
0x1800838af  push    rbx
0x1800838b0  sub     rsp, 20h
0x1800838b4  lea     r8, [rax+8]; union _LARGE_INTEGER *
0x1800838b8  mov     qword ptr [rax+8], 0
0x1800838c0  lea     rdx, [rax+10h]; union _LARGE_INTEGER *
0x1800838c4  mov     dword ptr [rax+14h], 7FFFFFFFh
0x1800838cb  mov     rbx, rcx
0x1800838ce  mov     dword ptr [rax+10h], 0FFFFFFFFh
0x1800838d5  call    ?Age@CAuthenticatorList@@AEAAKAEBT_LARGE_INTEGER@@0@Z; CAuthenticatorList::Age(_LARGE_INTEGER const &,_LARGE_INTEGER const &)
0x1800838da  cmp     byte ptr [rbx+80h], 0
0x1800838e1  jz      short loc_1800838ED
0x1800838e3  lea     rcx, [rbx+58h]; CriticalSection
0x1800838e7  call    cs:__imp_RtlDeleteCriticalSection
0x1800838ed  add     rsp, 20h
0x1800838f1  pop     rbx
0x1800838f2  retn
```
