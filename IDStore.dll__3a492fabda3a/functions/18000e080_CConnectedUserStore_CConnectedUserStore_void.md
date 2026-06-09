# CConnectedUserStore::~CConnectedUserStore(void)

- ea: `0x18000e080`
- end: `0x18000e0bd`
- name: `??1CConnectedUserStore@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(CConnectedUserStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800108b0`

## callees

- `0x18000e080`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e0b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e0b0`

## pseudocode

```c
void __fastcall CConnectedUserStore::~CConnectedUserStore(CConnectedUserStore *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 23);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((_BYTE *)this + 64) )
  {
    *((_BYTE *)this + 64) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  }
}

```

## disassembly

```asm
0x18000e080  push    rbx
0x18000e082  sub     rsp, 20h
0x18000e086  mov     rbx, rcx
0x18000e089  mov     rcx, [rcx+0B8h]
0x18000e090  test    rcx, rcx
0x18000e093  jz      short loc_18000E0A2
0x18000e095  mov     rax, [rcx]
0x18000e098  mov     rax, [rax+10h]
0x18000e09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0a1  nop
0x18000e0a2  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000e0a6  cmp     byte ptr [rcx+28h], 0
0x18000e0aa  jz      short loc_18000E0B7
0x18000e0ac  mov     byte ptr [rcx+28h], 0
0x18000e0b0  call    cs:__imp_DeleteCriticalSection
0x18000e0b6  nop
0x18000e0b7  add     rsp, 20h
0x18000e0bb  pop     rbx
0x18000e0bc  retn
```
