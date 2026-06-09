# PCPStorageProvider::PCPStorageProvider(void)

- ea: `0x18001c258`
- end: `0x18001c302`
- name: `??0PCPStorageProvider@@QEAA@XZ`
- size: `170`
- prototype: `PCPStorageProvider *__fastcall(PCPStorageProvider *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d590`

## callees

- `0x18001c120`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18001c2d2`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18001c2d2`
- `RPCRT4!UuidCreate` at `0x18001c2e7`
- `RPCRT4!UuidCreate` at `0x18001c2e7`

## pseudocode

```c
PCPStorageProvider *__fastcall PCPStorageProvider::PCPStorageProvider(PCPStorageProvider *this)
{
  TpmObject::TpmObject(this);
  strcpy((char *)this + 88, "PCPP");
  *(_QWORD *)this = &PCPStorageProvider::`vftable';
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 40) = 0;
  *((GUID *)this + 9) = GUID_NULL;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_WORD *)this + 96) = 0;
  *((_DWORD *)this + 40) = rand();
  UuidCreate((UUID *)this + 9);
  return this;
}

```

## disassembly

```asm
0x18001c258  mov     [rsp+arg_0], rbx
0x18001c25d  push    rdi
0x18001c25e  sub     rsp, 20h
0x18001c262  mov     rdi, rcx
0x18001c265  call    ??0TpmObject@@QEAA@XZ; TpmObject::TpmObject(void)
0x18001c26a  mov     dword ptr [rdi+58h], 50504350h
0x18001c271  lea     rax, ??_7PCPStorageProvider@@6B@; const PCPStorageProvider::`vftable'
0x18001c278  mov     [rdi], rax
0x18001c27b  lea     rbx, [rdi+90h]
0x18001c282  xor     eax, eax
0x18001c284  mov     [rdi+5Ch], al
0x18001c287  mov     [rdi+60h], rax
0x18001c28b  mov     [rdi+68h], rax
0x18001c28f  mov     [rdi+70h], rax
0x18001c293  mov     [rdi+78h], rax
0x18001c297  mov     [rdi+80h], rax
0x18001c29e  mov     [rdi+88h], rax
0x18001c2a5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001c2ac  mov     [rdi+0A0h], eax
0x18001c2b2  movdqu  xmmword ptr [rbx], xmm0
0x18001c2b6  mov     [rdi+0A8h], rax
0x18001c2bd  mov     [rdi+0B0h], rax
0x18001c2c4  mov     [rdi+0B8h], rax
0x18001c2cb  mov     [rdi+0C0h], ax
0x18001c2d2  call    cs:__imp_rand
0x18001c2d9  nop     dword ptr [rax+rax+00h]
0x18001c2de  mov     rcx, rbx; Uuid
0x18001c2e1  mov     [rdi+0A0h], eax
0x18001c2e7  call    cs:__imp_UuidCreate
0x18001c2ee  nop     dword ptr [rax+rax+00h]
0x18001c2f3  mov     rbx, [rsp+28h+arg_0]
0x18001c2f8  mov     rax, rdi
0x18001c2fb  add     rsp, 20h
0x18001c2ff  pop     rdi
0x18001c300  retn
```
