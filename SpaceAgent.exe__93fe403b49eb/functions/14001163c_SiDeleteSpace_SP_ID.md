# SiDeleteSpace(_SP_ID *)

- ea: `0x14001163c`
- end: `0x14001167b`
- name: `?SiDeleteSpace@@YAHPEAU_SP_ID@@@Z`
- size: `63`
- prototype: `BOOL __fastcall(struct _SP_ID *lpInBuffer)`
- caller_count: `3`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14000fb94`
- `0x14000fea0`
- `0x14001297c`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x140011670`
- `KERNEL32!DeviceIoControl` at `0x140011670`

## pseudocode

```c
BOOL __fastcall SiDeleteSpace(struct _SP_ID *lpInBuffer)
{
  DWORD v2; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  return DeviceIoControl(Spaceport, 0xE7C814u, lpInBuffer, 0x20u, 0, 0, &v2, 0);
}

```

## disassembly

```asm
0x14001163c  mov     r11, rsp
0x14001163f  sub     rsp, 48h
0x140011643  xor     edx, edx
0x140011645  mov     [rsp+48h+arg_8], edx
0x140011649  mov     [r11-10h], rdx
0x14001164d  lea     rax, [r11+10h]
0x140011651  mov     [r11-18h], rax
0x140011655  lea     r9d, [rdx+20h]; nInBufferSize
0x140011659  mov     [rsp+48h+nOutBufferSize], edx; nOutBufferSize
0x14001165d  mov     r8, rcx; lpInBuffer
0x140011660  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x140011667  mov     [r11-28h], rdx
0x14001166b  mov     edx, 0E7C814h; dwIoControlCode
0x140011670  call    cs:__imp_DeviceIoControl
0x140011676  add     rsp, 48h
0x14001167a  retn
```
