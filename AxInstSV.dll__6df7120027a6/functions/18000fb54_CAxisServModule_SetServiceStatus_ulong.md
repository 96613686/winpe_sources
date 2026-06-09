# CAxisServModule::SetServiceStatus(ulong)

- ea: `0x18000fb54`
- end: `0x18000fb78`
- name: `?SetServiceStatus@CAxisServModule@@QEAAXK@Z`
- size: `36`
- prototype: `void __fastcall(CAxisServModule *this, DWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000aa50`
- `0x18000f170`
- `0x18000fd10`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000fb71`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAxisServModule::SetServiceStatus(CAxisServModule *this, DWORD a2)
{
  struct _SERVICE_STATUS *v3; // rdx
  SERVICE_STATUS_HANDLE v4; // rcx

  *((_DWORD *)this + 309) = 0;
  v3 = (struct _SERVICE_STATUS *)((char *)this + 1216);
  v4 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 151);
  v3->dwCurrentState = a2;
  SetServiceStatus(v4, v3);
}

```

## disassembly

```asm
0x18000fb54  mov     eax, edx
0x18000fb56  mov     dword ptr [rcx+4D4h], 0
0x18000fb60  lea     rdx, [rcx+4C0h]
0x18000fb67  mov     rcx, [rcx+4B8h]
0x18000fb6e  mov     [rdx+4], eax
0x18000fb71  jmp     cs:__imp_SetServiceStatus
```
