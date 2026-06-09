# TcpipPlugin::GetNetBTInterfacePathForAdapter

- ea: `0x180040930`
- end: `0x1800409bf`
- name: `TcpipPlugin::GetNetBTInterfacePathForAdapter`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, service_task`

## callers

- `0x180018570`
- `0x18004072c`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800409ac`
- `msvcrt!swprintf_s` at `0x1800409ac`

## string_xrefs

- `0x18004097b`: `Services\NetBT\Parameters\Interfaces\Tcpip_{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}`

## pseudocode

```c
int __fastcall TcpipPlugin::GetNetBTInterfacePathForAdapter(unsigned int *a1, wchar_t *a2)
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
           L"Services\\NetBT\\Parameters\\Interfaces\\Tcpip_{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
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
0x180040930  push    rbx
0x180040932  push    rbp
0x180040933  push    rsi
0x180040934  push    rdi
0x180040935  push    r14
0x180040937  push    r15
0x180040939  sub     rsp, 78h
0x18004093d  movzx   r8d, byte ptr [rcx+0Eh]
0x180040942  mov     r15, rdx
0x180040945  movzx   r9d, byte ptr [rcx+0Dh]
0x18004094a  mov     edx, 104h; BufferCount
0x18004094f  movzx   eax, byte ptr [rcx+0Fh]
0x180040953  movzx   r10d, byte ptr [rcx+0Ch]
0x180040958  movzx   r11d, byte ptr [rcx+0Bh]
0x18004095d  movzx   ebx, byte ptr [rcx+0Ah]
0x180040961  movzx   edi, byte ptr [rcx+9]
0x180040965  movzx   esi, byte ptr [rcx+8]
0x180040969  movzx   ebp, word ptr [rcx+6]
0x18004096d  movzx   r14d, word ptr [rcx+4]
0x180040972  mov     [rsp+0A8h+var_40], eax
0x180040976  mov     [rsp+0A8h+var_48], r8d
0x18004097b  lea     r8, aServicesNetbtP; "Services\\NetBT\\Parameters\\Interfaces"...
0x180040982  mov     [rsp+0A8h+var_50], r9d
0x180040987  mov     r9d, [rcx]
0x18004098a  mov     rcx, r15; Buffer
0x18004098d  mov     [rsp+0A8h+var_58], r10d
0x180040992  mov     [rsp+0A8h+var_60], r11d
0x180040997  mov     [rsp+0A8h+var_68], ebx
0x18004099b  mov     [rsp+0A8h+var_70], edi
0x18004099f  mov     [rsp+0A8h+var_78], esi
0x1800409a3  mov     [rsp+0A8h+var_80], ebp
0x1800409a7  mov     [rsp+0A8h+var_88], r14d
0x1800409ac  call    cs:__imp_swprintf_s
0x1800409b2  add     rsp, 78h
0x1800409b6  pop     r15
0x1800409b8  pop     r14
0x1800409ba  pop     rdi
0x1800409bb  pop     rsi
0x1800409bc  pop     rbp
0x1800409bd  pop     rbx
0x1800409be  retn
```
