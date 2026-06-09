# CBaseUpdateDescriptor::~CBaseUpdateDescriptor(void)

- ea: `0x180030dd8`
- end: `0x180030e17`
- name: `??1CBaseUpdateDescriptor@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(CBaseUpdateDescriptor *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180030e20`
- `0x180030f90`
- `0x180031180`

## callees

- `0x18001d668`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030def`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030df9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030e03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030def`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030df9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030e03`

## pseudocode

```c
void __fastcall CBaseUpdateDescriptor::~CBaseUpdateDescriptor(LPVOID *this)
{
  *this = &CBaseUpdateDescriptor::`vftable';
  CoTaskMemFree(this[2]);
  CoTaskMemFree(this[3]);
  CoTaskMemFree(this[4]);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(this + 5);
}

```

## disassembly

```asm
0x180030dd8  push    rbx
0x180030dda  sub     rsp, 20h
0x180030dde  lea     rax, ??_7CBaseUpdateDescriptor@@6B@; const CBaseUpdateDescriptor::`vftable'
0x180030de5  mov     rbx, rcx
0x180030de8  mov     [rcx], rax
0x180030deb  mov     rcx, [rcx+10h]; pv
0x180030def  call    cs:__imp_CoTaskMemFree
0x180030df5  mov     rcx, [rbx+18h]; pv
0x180030df9  call    cs:__imp_CoTaskMemFree
0x180030dff  mov     rcx, [rbx+20h]; pv
0x180030e03  call    cs:__imp_CoTaskMemFree
0x180030e09  lea     rcx, [rbx+28h]
0x180030e0d  add     rsp, 20h
0x180030e11  pop     rbx
0x180030e12  jmp     ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
```
