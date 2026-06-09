# COleChangeSourceDialog::~COleChangeSourceDialog(void)

- ea: `0x18008af00`
- end: `0x18008af47`
- name: `??1COleChangeSourceDialog@@UEAA@XZ`
- size: `71`
- prototype: `void __fastcall(COleChangeSourceDialog *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008af80`

## callees

- `0x18002d490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008af1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008af27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008af34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008af1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008af27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008af34`

## pseudocode

```c
void __fastcall COleChangeSourceDialog::~COleChangeSourceDialog(LPVOID *this)
{
  *this = &COleChangeSourceDialog::`vftable';
  CoTaskMemFree(this[41]);
  CoTaskMemFree(this[40]);
  CoTaskMemFree(this[38]);
  CDialog::~CDialog((CDialog *)this);
}

```

## disassembly

```asm
0x18008af00  push    rbx
0x18008af02  sub     rsp, 20h
0x18008af06  lea     rax, ??_7COleChangeSourceDialog@@6B@; const COleChangeSourceDialog::`vftable'
0x18008af0d  mov     rbx, rcx
0x18008af10  mov     [rcx], rax
0x18008af13  mov     rcx, [rcx+148h]; pv
0x18008af1a  call    cs:__imp_CoTaskMemFree
0x18008af20  mov     rcx, [rbx+140h]; pv
0x18008af27  call    cs:__imp_CoTaskMemFree
0x18008af2d  mov     rcx, [rbx+130h]; pv
0x18008af34  call    cs:__imp_CoTaskMemFree
0x18008af3a  mov     rcx, rbx; this
0x18008af3d  add     rsp, 20h
0x18008af41  pop     rbx
0x18008af42  jmp     ??1CDialog@@UEAA@XZ; CDialog::~CDialog(void)
```
