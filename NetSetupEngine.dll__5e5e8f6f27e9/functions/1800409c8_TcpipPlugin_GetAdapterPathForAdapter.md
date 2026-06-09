# TcpipPlugin::GetAdapterPathForAdapter

- ea: `0x1800409c8`
- end: `0x180040a57`
- name: `TcpipPlugin::GetAdapterPathForAdapter`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, service_task`

## callers

- `0x180018570`
- `0x18004072c`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180040a44`
- `msvcrt!swprintf_s` at `0x180040a44`

## string_xrefs

- `0x180040a13`: `Services\Tcpip\Parameters\Adapters\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}`

## pseudocode

```c
int __fastcall TcpipPlugin::GetAdapterPathForAdapter(unsigned int *a1, wchar_t *a2)
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
           L"Services\\Tcpip\\Parameters\\Adapters\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
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
0x1800409c8  push    rbx
0x1800409ca  push    rbp
0x1800409cb  push    rsi
0x1800409cc  push    rdi
0x1800409cd  push    r14
0x1800409cf  push    r15
0x1800409d1  sub     rsp, 78h
0x1800409d5  movzx   r8d, byte ptr [rcx+0Eh]
0x1800409da  mov     r15, rdx
0x1800409dd  movzx   r9d, byte ptr [rcx+0Dh]
0x1800409e2  mov     edx, 104h; BufferCount
0x1800409e7  movzx   eax, byte ptr [rcx+0Fh]
0x1800409eb  movzx   r10d, byte ptr [rcx+0Ch]
0x1800409f0  movzx   r11d, byte ptr [rcx+0Bh]
0x1800409f5  movzx   ebx, byte ptr [rcx+0Ah]
0x1800409f9  movzx   edi, byte ptr [rcx+9]
0x1800409fd  movzx   esi, byte ptr [rcx+8]
0x180040a01  movzx   ebp, word ptr [rcx+6]
0x180040a05  movzx   r14d, word ptr [rcx+4]
0x180040a0a  mov     [rsp+0A8h+var_40], eax
0x180040a0e  mov     [rsp+0A8h+var_48], r8d
0x180040a13  lea     r8, aServicesTcpipP; "Services\\Tcpip\\Parameters\\Adapters\\"...
0x180040a1a  mov     [rsp+0A8h+var_50], r9d
0x180040a1f  mov     r9d, [rcx]
0x180040a22  mov     rcx, r15; Buffer
0x180040a25  mov     [rsp+0A8h+var_58], r10d
0x180040a2a  mov     [rsp+0A8h+var_60], r11d
0x180040a2f  mov     [rsp+0A8h+var_68], ebx
0x180040a33  mov     [rsp+0A8h+var_70], edi
0x180040a37  mov     [rsp+0A8h+var_78], esi
0x180040a3b  mov     [rsp+0A8h+var_80], ebp
0x180040a3f  mov     [rsp+0A8h+var_88], r14d
0x180040a44  call    cs:__imp_swprintf_s
0x180040a4a  add     rsp, 78h
0x180040a4e  pop     r15
0x180040a50  pop     r14
0x180040a52  pop     rdi
0x180040a53  pop     rsi
0x180040a54  pop     rbp
0x180040a55  pop     rbx
0x180040a56  retn
```
