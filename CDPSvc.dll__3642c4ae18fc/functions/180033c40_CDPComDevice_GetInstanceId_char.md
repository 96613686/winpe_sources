# CDPComDevice::GetInstanceId(char * *)

- ea: `0x180033c40`
- end: `0x180033ca3`
- name: `?GetInstanceId@CDPComDevice@@UEAAJPEAPEAD@Z`
- size: `99`
- prototype: `__int64 __fastcall(CDPComDevice *__hidden this, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180033c40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180033c90`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180033c90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033c63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033c63`

## pseudocode

```c
__int64 __fastcall CDPComDevice::GetInstanceId(CDPComDevice *this, char **a2)
{
  char *v5; // rax
  const char *v6; // r8

  if ( !a2 )
    return 2147500035LL;
  v5 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 10) + 1LL);
  *a2 = v5;
  if ( !v5 )
    return 2147942414LL;
  v6 = (char *)this + 64;
  if ( *((_QWORD *)this + 11) > 0xFu )
    v6 = *(const char **)v6;
  strcpy_s(v5, *((_QWORD *)this + 10) + 1LL, v6);
  return 0;
}

```

## disassembly

```asm
0x180033c40  mov     [rsp+arg_0], rbx
0x180033c45  push    rdi
0x180033c46  sub     rsp, 20h
0x180033c4a  mov     rdi, rdx
0x180033c4d  mov     rbx, rcx
0x180033c50  test    rdx, rdx
0x180033c53  jnz     short loc_180033C5C
0x180033c55  mov     eax, 80004003h
0x180033c5a  jmp     short loc_180033C98
0x180033c5c  mov     rcx, [rcx+50h]
0x180033c60  inc     rcx; cb
0x180033c63  call    cs:__imp_CoTaskMemAlloc
0x180033c69  mov     [rdi], rax
0x180033c6c  test    rax, rax
0x180033c6f  jnz     short loc_180033C78
0x180033c71  mov     eax, 8007000Eh
0x180033c76  jmp     short loc_180033C98
0x180033c78  lea     r8, [rbx+40h]
0x180033c7c  cmp     qword ptr [r8+18h], 0Fh
0x180033c81  jbe     short loc_180033C86
0x180033c83  mov     r8, [r8]; Source
0x180033c86  mov     rdx, [rbx+50h]
0x180033c8a  mov     rcx, rax; Destination
0x180033c8d  inc     rdx; SizeInBytes
0x180033c90  call    cs:__imp_strcpy_s
0x180033c96  xor     eax, eax
0x180033c98  mov     rbx, [rsp+28h+arg_0]
0x180033c9d  add     rsp, 20h
0x180033ca1  pop     rdi
0x180033ca2  retn
```
