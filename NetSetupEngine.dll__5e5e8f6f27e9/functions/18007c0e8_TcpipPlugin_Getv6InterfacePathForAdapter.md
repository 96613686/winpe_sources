# TcpipPlugin::Getv6InterfacePathForAdapter

- ea: `0x18007c0e8`
- end: `0x18007c177`
- name: `TcpipPlugin::Getv6InterfacePathForAdapter`
- size: `143`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, service_task`

## callers

- `0x180018570`
- `0x18004072c`
- `0x180051cf0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18007c164`
- `msvcrt!swprintf_s` at `0x18007c164`

## string_xrefs

- `0x18007c133`: `Services\Tcpip6\Parameters\Interfaces\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}`

## pseudocode

```c
int __fastcall TcpipPlugin::Getv6InterfacePathForAdapter(unsigned int *a1, wchar_t *a2)
{
  int v3; // [rsp+20h] [rbp-88h]
  int v4; // [rsp+28h] [rbp-80h]
  int v5; // [rsp+30h] [rbp-78h]
  int v6; // [rsp+38h] [rbp-70h]
  int v7; // [rsp+40h] [rbp-68h]
  int v8; // [rsp+48h] [rbp-60h]
  int v9; // [rsp+50h] [rbp-58h]
  int v10; // [rsp+58h] [rbp-50h]
  int v11; // [rsp+60h] [rbp-48h]
  int v12; // [rsp+68h] [rbp-40h]

  v12 = *((unsigned __int8 *)a1 + 15);
  v11 = *((unsigned __int8 *)a1 + 14);
  v10 = *((unsigned __int8 *)a1 + 13);
  v9 = *((unsigned __int8 *)a1 + 12);
  v8 = *((unsigned __int8 *)a1 + 11);
  v7 = *((unsigned __int8 *)a1 + 10);
  v6 = *((unsigned __int8 *)a1 + 9);
  v5 = *((unsigned __int8 *)a1 + 8);
  v4 = *((unsigned __int16 *)a1 + 3);
  v3 = *((unsigned __int16 *)a1 + 2);
  return swprintf_s(
           a2,
           0x104u,
           L"Services\\Tcpip6\\Parameters\\Interfaces\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
           *a1,
           v3,
           v4,
           v5,
           v6,
           v7,
           v8,
           v9,
           v10,
           v11,
           v12);
}

```

## disassembly

```asm
0x18007c0e8  push    rbx
0x18007c0ea  push    rbp
0x18007c0eb  push    rsi
0x18007c0ec  push    rdi
0x18007c0ed  push    r14
0x18007c0ef  push    r15
0x18007c0f1  sub     rsp, 78h
0x18007c0f5  movzx   r8d, byte ptr [rcx+0Eh]
0x18007c0fa  mov     r15, rdx
0x18007c0fd  movzx   r9d, byte ptr [rcx+0Dh]
0x18007c102  mov     edx, 104h; BufferCount
0x18007c107  movzx   eax, byte ptr [rcx+0Fh]
0x18007c10b  movzx   r10d, byte ptr [rcx+0Ch]
0x18007c110  movzx   r11d, byte ptr [rcx+0Bh]
0x18007c115  movzx   ebx, byte ptr [rcx+0Ah]
0x18007c119  movzx   edi, byte ptr [rcx+9]
0x18007c11d  movzx   esi, byte ptr [rcx+8]
0x18007c121  movzx   ebp, word ptr [rcx+6]
0x18007c125  movzx   r14d, word ptr [rcx+4]
0x18007c12a  mov     [rsp+0A8h+var_40], eax
0x18007c12e  mov     [rsp+0A8h+var_48], r8d
0x18007c133  lea     r8, aServicesTcpip6; "Services\\Tcpip6\\Parameters\\Interface"...
0x18007c13a  mov     [rsp+0A8h+var_50], r9d
0x18007c13f  mov     r9d, [rcx]
0x18007c142  mov     rcx, r15; Buffer
0x18007c145  mov     [rsp+0A8h+var_58], r10d
0x18007c14a  mov     [rsp+0A8h+var_60], r11d
0x18007c14f  mov     [rsp+0A8h+var_68], ebx
0x18007c153  mov     [rsp+0A8h+var_70], edi
0x18007c157  mov     [rsp+0A8h+var_78], esi
0x18007c15b  mov     [rsp+0A8h+var_80], ebp
0x18007c15f  mov     [rsp+0A8h+var_88], r14d
0x18007c164  call    cs:__imp_swprintf_s
0x18007c16a  add     rsp, 78h
0x18007c16e  pop     r15
0x18007c170  pop     r14
0x18007c172  pop     rdi
0x18007c173  pop     rsi
0x18007c174  pop     rbp
0x18007c175  pop     rbx
0x18007c176  retn
```
