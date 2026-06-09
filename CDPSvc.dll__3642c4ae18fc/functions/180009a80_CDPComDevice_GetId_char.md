# CDPComDevice::GetId(char * *)

- ea: `0x180009a80`
- end: `0x180009ae3`
- name: `?GetId@CDPComDevice@@UEAAJPEAPEAD@Z`
- size: `99`
- prototype: `__int64 __fastcall(CDPComDevice *__hidden this, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009a80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180009ad0`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180009ad0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009aa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009aa3`

## pseudocode

```c
__int64 __fastcall CDPComDevice::GetId(CDPComDevice *this, char **a2)
{
  char *v5; // rax
  const char *v6; // r8

  if ( !a2 )
    return 2147500035LL;
  v5 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 6) + 1LL);
  *a2 = v5;
  if ( !v5 )
    return 2147942414LL;
  v6 = (char *)this + 32;
  if ( *((_QWORD *)this + 7) > 0xFu )
    v6 = *(const char **)v6;
  strcpy_s(v5, *((_QWORD *)this + 6) + 1LL, v6);
  return 0;
}

```

## disassembly

```asm
0x180009a80  mov     [rsp+arg_0], rbx
0x180009a85  push    rdi
0x180009a86  sub     rsp, 20h
0x180009a8a  mov     rdi, rdx
0x180009a8d  mov     rbx, rcx
0x180009a90  test    rdx, rdx
0x180009a93  jnz     short loc_180009A9C
0x180009a95  mov     eax, 80004003h
0x180009a9a  jmp     short loc_180009AD8
0x180009a9c  mov     rcx, [rcx+30h]
0x180009aa0  inc     rcx; cb
0x180009aa3  call    cs:__imp_CoTaskMemAlloc
0x180009aa9  mov     [rdi], rax
0x180009aac  test    rax, rax
0x180009aaf  jnz     short loc_180009AB8
0x180009ab1  mov     eax, 8007000Eh
0x180009ab6  jmp     short loc_180009AD8
0x180009ab8  lea     r8, [rbx+20h]
0x180009abc  cmp     qword ptr [r8+18h], 0Fh
0x180009ac1  jbe     short loc_180009AC6
0x180009ac3  mov     r8, [r8]; Source
0x180009ac6  mov     rdx, [rbx+30h]
0x180009aca  mov     rcx, rax; Destination
0x180009acd  inc     rdx; SizeInBytes
0x180009ad0  call    cs:__imp_strcpy_s
0x180009ad6  xor     eax, eax
0x180009ad8  mov     rbx, [rsp+28h+arg_0]
0x180009add  add     rsp, 20h
0x180009ae1  pop     rdi
0x180009ae2  retn
```
