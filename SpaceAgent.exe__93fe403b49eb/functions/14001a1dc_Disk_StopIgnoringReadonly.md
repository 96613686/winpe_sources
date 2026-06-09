# Disk_StopIgnoringReadonly

- ea: `0x14001a1dc`
- end: `0x14001a245`
- name: `Disk_StopIgnoringReadonly`
- size: `105`
- prototype: `BOOL __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140019e18`
- `0x14001b8c4`

## callees

- `0x14001edc0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x14001a22d`
- `KERNEL32!DeviceIoControl` at `0x14001a22d`

## pseudocode

```c
BOOL __fastcall Disk_StopIgnoringReadonly(void *a1)
{
  _QWORD v2[3]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v3; // [rsp+58h] [rbp-20h]

  v2[0] = 40;
  v3 = 0;
  v2[1] = 2;
  v2[2] = 2;
  return DeviceIoControl(a1, 0x7C0F4u, v2, 0x28u, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x14001a1dc  mov     r11, rsp
0x14001a1df  sub     rsp, 78h
0x14001a1e3  mov     rax, cs:__security_cookie
0x14001a1ea  xor     rax, rsp
0x14001a1ed  mov     [rsp+78h+var_10], rax
0x14001a1f2  xor     edx, edx
0x14001a1f4  mov     qword ptr [r11-38h], 28h ; '('
0x14001a1fc  mov     [r11-40h], rdx
0x14001a200  lea     r8, [r11-38h]; lpInBuffer
0x14001a204  mov     [r11-48h], rdx
0x14001a208  xorps   xmm0, xmm0
0x14001a20b  mov     [rsp+78h+nOutBufferSize], edx; nOutBufferSize
0x14001a20f  lea     eax, [rdx+2]
0x14001a212  mov     [r11-58h], rdx
0x14001a216  movdqu  [rsp+78h+var_20], xmm0
0x14001a21c  lea     r9d, [rdx+28h]; nInBufferSize
0x14001a220  mov     [r11-30h], rax
0x14001a224  mov     edx, 7C0F4h; dwIoControlCode
0x14001a229  mov     [r11-28h], rax
0x14001a22d  call    cs:__imp_DeviceIoControl
0x14001a233  mov     rcx, [rsp+78h+var_10]
0x14001a238  xor     rcx, rsp; StackCookie
0x14001a23b  call    __security_check_cookie
0x14001a240  add     rsp, 78h
0x14001a244  retn
```
