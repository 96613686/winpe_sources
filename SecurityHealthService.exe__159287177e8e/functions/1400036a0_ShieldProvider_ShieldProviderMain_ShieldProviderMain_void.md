# ShieldProvider::ShieldProviderMain::~ShieldProviderMain(void)

- ea: `0x1400036a0`
- end: `0x1400036c6`
- name: `??1ShieldProviderMain@ShieldProvider@@UEAA@XZ`
- size: `38`
- prototype: `void __fastcall(ShieldProvider::ShieldProviderMain *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400036d0`

## callees

- `0x1400036a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400036bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400036bb`

## pseudocode

```c
void __fastcall ShieldProvider::ShieldProviderMain::~ShieldProviderMain(ShieldProvider::ShieldProviderMain *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rcx

  *(_QWORD *)this = &ShieldProvider::ShieldProviderMain::`vftable';
  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  if ( v1->RecursionCount != 252844334 )
    DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x1400036a0  sub     rsp, 28h
0x1400036a4  lea     rax, ??_7ShieldProviderMain@ShieldProvider@@6B@; const ShieldProvider::ShieldProviderMain::`vftable'
0x1400036ab  mov     [rcx], rax
0x1400036ae  add     rcx, 8; lpCriticalSection
0x1400036b2  cmp     dword ptr [rcx+0Ch], 0F12192Eh
0x1400036b9  jz      short loc_1400036C1
0x1400036bb  call    cs:__imp_DeleteCriticalSection
0x1400036c1  add     rsp, 28h
0x1400036c5  retn
```
