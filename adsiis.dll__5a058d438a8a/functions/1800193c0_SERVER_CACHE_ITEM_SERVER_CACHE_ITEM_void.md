# SERVER_CACHE_ITEM::~SERVER_CACHE_ITEM(void)

- ea: `0x1800193c0`
- end: `0x180019414`
- name: `??1SERVER_CACHE_ITEM@@QEAA@XZ`
- size: `84`
- prototype: `void __fastcall(SERVER_CACHE_ITEM *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001941c`

## callees

- `0x1800193c0`
- `0x180019590`
- `0x18001b5ec`
- `0x18001e010`

## import_xrefs

- `IisRTL!??1STRU@@QEAA@XZ` at `0x180019400`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x180019400`

## pseudocode

```c
void __fastcall SERVER_CACHE_ITEM::~SERVER_CACHE_ITEM(SERVER_CACHE_ITEM *this)
{
  __int64 v2; // rcx
  IIsSchema *v3; // rcx

  v2 = *((_QWORD *)this + 13);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 13) = 0;
  }
  v3 = (IIsSchema *)*((_QWORD *)this + 14);
  if ( v3 )
  {
    IIsSchema::Release(v3);
    *((_QWORD *)this + 14) = 0;
  }
  STRU::~STRU((SERVER_CACHE_ITEM *)((char *)this + 48));
  CCredentials::~CCredentials((SERVER_CACHE_ITEM *)((char *)this + 8));
}

```

## disassembly

```asm
0x1800193c0  push    rbx
0x1800193c2  sub     rsp, 20h
0x1800193c6  mov     rbx, rcx
0x1800193c9  mov     rcx, [rcx+68h]
0x1800193cd  test    rcx, rcx
0x1800193d0  jz      short loc_1800193E6
0x1800193d2  mov     rax, [rcx]
0x1800193d5  mov     rax, [rax+10h]
0x1800193d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193de  mov     qword ptr [rbx+68h], 0
0x1800193e6  mov     rcx, [rbx+70h]; this
0x1800193ea  test    rcx, rcx
0x1800193ed  jz      short loc_1800193FC
0x1800193ef  call    ?Release@IIsSchema@@QEAAJXZ; IIsSchema::Release(void)
0x1800193f4  mov     qword ptr [rbx+70h], 0
0x1800193fc  lea     rcx, [rbx+30h]
0x180019400  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180019406  lea     rcx, [rbx+8]; this
0x18001940a  add     rsp, 20h
0x18001940e  pop     rbx
0x18001940f  jmp     ??1CCredentials@@QEAA@XZ; CCredentials::~CCredentials(void)
```
