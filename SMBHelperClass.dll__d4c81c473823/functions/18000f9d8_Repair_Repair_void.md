# Repair::~Repair(void)

- ea: `0x18000f9d8`
- end: `0x18000fa0c`
- name: `??1Repair@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(Repair *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180009fc0`
- `0x18001014b`

## callees

- `0x18000d4d8`
- `0x18000f9d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f9f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f9f8`

## pseudocode

```c
void __fastcall Repair::~Repair(Repair *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &Repair::`vftable';
  v2 = (void *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)v2 >= 0x10000 )
    CoTaskMemFree(v2);
  AttributeList::~AttributeList((HANDLE *)this + 1);
}

```

## disassembly

```asm
0x18000f9d8  push    rbx
0x18000f9da  sub     rsp, 20h
0x18000f9de  lea     rax, ??_7Repair@@6B@; const Repair::`vftable'
0x18000f9e5  mov     rbx, rcx
0x18000f9e8  mov     [rcx], rax
0x18000f9eb  mov     rcx, [rcx+20h]; pv
0x18000f9ef  cmp     rcx, 10000h
0x18000f9f6  jb      short loc_18000F9FE
0x18000f9f8  call    cs:__imp_CoTaskMemFree
0x18000f9fe  lea     rcx, [rbx+8]; this
0x18000fa02  add     rsp, 20h
0x18000fa06  pop     rbx
0x18000fa07  jmp     ??1AttributeList@@QEAA@XZ; AttributeList::~AttributeList(void)
```
