# StateRepoHelpers::ExplorerCommandVerb::~ExplorerCommandVerb(void)

- ea: `0x180007c24`
- end: `0x180007c50`
- name: `??1ExplorerCommandVerb@StateRepoHelpers@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(StateRepoHelpers::ExplorerCommandVerb *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000618c`
- `0x180007920`
- `0x180007f00`
- `0x18001cda4`

## callees

- `0x180007c24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c44`

## pseudocode

```c
void __fastcall StateRepoHelpers::ExplorerCommandVerb::~ExplorerCommandVerb(
        StateRepoHelpers::ExplorerCommandVerb *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    CoTaskMemFree(v2);
  if ( *(_QWORD *)this )
    CoTaskMemFree(*(LPVOID *)this);
}

```

## disassembly

```asm
0x180007c24  push    rbx
0x180007c26  sub     rsp, 20h
0x180007c2a  mov     rbx, rcx
0x180007c2d  mov     rcx, [rcx+8]; pv
0x180007c31  test    rcx, rcx
0x180007c34  jz      short loc_180007C3C
0x180007c36  call    cs:__imp_CoTaskMemFree
0x180007c3c  mov     rcx, [rbx]; pv
0x180007c3f  test    rcx, rcx
0x180007c42  jz      short loc_180007C4A
0x180007c44  call    cs:__imp_CoTaskMemFree
0x180007c4a  add     rsp, 20h
0x180007c4e  pop     rbx
0x180007c4f  retn
```
