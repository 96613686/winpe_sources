# CNtService::~CNtService(void)

- ea: `0x18000c8e4`
- end: `0x18000c907`
- name: `??1CNtService@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(CNtService *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c8a8`
- `0x18001db6d`
- `0x18001db7f`

## callees

- `0x18000c8e4`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c8fb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c8fb`

## pseudocode

```c
void __fastcall CNtService::~CNtService(CNtService *this)
{
  void *v1; // rcx

  *(_QWORD *)this = &CNtService::`vftable';
  v1 = (void *)*((_QWORD *)this + 2);
  if ( v1 )
    CWin32DefaultArena::WbemMemFree(v1);
}

```

## disassembly

```asm
0x18000c8e4  sub     rsp, 28h
0x18000c8e8  lea     rax, ??_7CNtService@@6B@; const CNtService::`vftable'
0x18000c8ef  mov     [rcx], rax
0x18000c8f2  mov     rcx, [rcx+10h]
0x18000c8f6  test    rcx, rcx
0x18000c8f9  jz      short loc_18000C902
0x18000c8fb  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000c901  nop
0x18000c902  add     rsp, 28h
0x18000c906  retn
```
