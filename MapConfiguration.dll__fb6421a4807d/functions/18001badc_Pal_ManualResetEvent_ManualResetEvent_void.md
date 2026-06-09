# Pal::ManualResetEvent::ManualResetEvent(void)

- ea: `0x18001badc`
- end: `0x18001bb23`
- name: `??0ManualResetEvent@Pal@@QEAA@XZ`
- size: `71`
- prototype: `Pal::ManualResetEvent *__fastcall(Pal::ManualResetEvent *this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001fc0`
- `0x18000d8a4`
- `0x1800109e8`
- `0x18001c2c8`
- `0x180022d40`

## callees

- `0x180009988`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001bb09`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001bb09`

## pseudocode

```c
Pal::ManualResetEvent *__fastcall Pal::ManualResetEvent::ManualResetEvent(Pal::ManualResetEvent *this)
{
  HANDLE *v2; // rbx
  Pal::ManualResetEvent *result; // rax

  v2 = (HANDLE *)operator new(8u);
  *v2 = CreateEventExW(0, 0, 1u, 0x1F0003u);
  result = this;
  *(_QWORD *)this = v2;
  return result;
}

```

## disassembly

```asm
0x18001badc  mov     [rsp+arg_8], rbx
0x18001bae1  push    rdi
0x18001bae2  sub     rsp, 20h
0x18001bae6  mov     rdi, rcx
0x18001bae9  mov     ecx, 8; Size
0x18001baee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001baf3  xor     edx, edx; lpName
0x18001baf5  mov     [rsp+28h+arg_0], rax
0x18001bafa  xor     ecx, ecx; lpEventAttributes
0x18001bafc  mov     r9d, 1F0003h; dwDesiredAccess
0x18001bb02  mov     rbx, rax
0x18001bb05  lea     r8d, [rdx+1]; dwFlags
0x18001bb09  call    cs:__imp_CreateEventExW
0x18001bb0f  mov     [rbx], rax
0x18001bb12  mov     rax, rdi
0x18001bb15  mov     [rdi], rbx
0x18001bb18  mov     rbx, [rsp+28h+arg_8]
0x18001bb1d  add     rsp, 20h
0x18001bb21  pop     rdi
0x18001bb22  retn
```
