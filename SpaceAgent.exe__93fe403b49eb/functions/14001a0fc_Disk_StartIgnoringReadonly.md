# Disk_StartIgnoringReadonly

- ea: `0x14001a0fc`
- end: `0x14001a1d5`
- name: `Disk_StartIgnoringReadonly`
- size: `217`
- prototype: `BOOL __fastcall(HANDLE hDevice, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140019e18`
- `0x14001b8c4`

## callees

- `0x14001a0fc`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x14001a151`
- `KERNEL32!DeviceIoControl` at `0x14001a1a6`
- `KERNEL32!DeviceIoControl` at `0x14001a151`
- `KERNEL32!DeviceIoControl` at `0x14001a1a6`

## pseudocode

```c
BOOL __fastcall Disk_StartIgnoringReadonly(HANDLE hDevice, int *a2)
{
  int v2; // ebx
  BOOL result; // eax
  __int128 lpOutBuffer; // [rsp+40h] [rbp-48h] BYREF
  __int64 InBuffer; // [rsp+50h] [rbp-38h] BYREF
  int v8; // [rsp+58h] [rbp-30h]
  int v9; // [rsp+5Ch] [rbp-2Ch]
  __int64 v10; // [rsp+60h] [rbp-28h]
  __int128 v11; // [rsp+68h] [rbp-20h]

  v2 = 0;
  lpOutBuffer = 0;
  result = DeviceIoControl(hDevice, 0x700F0u, 0, 0, &lpOutBuffer, 0x10u, 0, 0);
  if ( result && (BYTE8(lpOutBuffer) & 2) != 0 )
  {
    v8 = 0;
    v9 = 0;
    v11 = 0;
    InBuffer = 40;
    v10 = 2;
    result = DeviceIoControl(hDevice, 0x7C0F4u, &InBuffer, 0x28u, 0, 0, 0, 0);
    v2 = 1;
  }
  *a2 = v2;
  return result;
}

```

## disassembly

```asm
0x14001a0fc  mov     r11, rsp
0x14001a0ff  mov     [r11+18h], rbx
0x14001a103  mov     [r11+20h], rsi
0x14001a107  push    rdi
0x14001a108  sub     rsp, 80h
0x14001a10f  mov     rax, cs:__security_cookie
0x14001a116  xor     rax, rsp
0x14001a119  mov     [rsp+88h+var_10], rax
0x14001a11e  xor     ebx, ebx
0x14001a120  lea     rax, [r11-48h]
0x14001a124  mov     [r11-50h], rbx
0x14001a128  mov     rdi, rdx
0x14001a12b  mov     [r11-58h], rbx
0x14001a12f  xorps   xmm0, xmm0
0x14001a132  mov     [rsp+88h+nOutBufferSize], 10h; nOutBufferSize
0x14001a13a  xor     r9d, r9d; nInBufferSize
0x14001a13d  xor     r8d, r8d; lpInBuffer
0x14001a140  mov     [r11-68h], rax
0x14001a144  mov     edx, 700F0h; dwIoControlCode
0x14001a149  mov     rsi, rcx
0x14001a14c  movups  [rsp+88h+var_48], xmm0
0x14001a151  call    cs:__imp_DeviceIoControl
0x14001a157  test    eax, eax
0x14001a159  jz      short loc_14001A1B1
0x14001a15b  test    byte ptr [rsp+88h+var_48+8], 2
0x14001a160  jz      short loc_14001A1B1
0x14001a162  mov     [rsp+88h+lpOverlapped], rbx; lpOverlapped
0x14001a167  lea     r9d, [rbx+28h]; nInBufferSize
0x14001a16b  mov     [rsp+88h+lpBytesReturned], rbx; lpBytesReturned
0x14001a170  lea     r8, [rsp+88h+InBuffer]; lpInBuffer
0x14001a175  xorps   xmm0, xmm0
0x14001a178  mov     [rsp+88h+nOutBufferSize], ebx; nOutBufferSize
0x14001a17c  mov     edx, 7C0F4h; dwIoControlCode
0x14001a181  mov     [rsp+88h+lpOutBuffer], rbx; lpOutBuffer
0x14001a186  mov     rcx, rsi; hDevice
0x14001a189  mov     [rsp+88h+var_34], rbx
0x14001a18e  mov     [rsp+88h+var_2C], ebx
0x14001a192  movdqu  [rsp+88h+var_20], xmm0
0x14001a198  mov     [rsp+88h+InBuffer], r9d
0x14001a19d  mov     [rsp+88h+var_28], 2
0x14001a1a6  call    cs:__imp_DeviceIoControl
0x14001a1ac  mov     ebx, 1
0x14001a1b1  mov     [rdi], ebx
0x14001a1b3  mov     rcx, [rsp+88h+var_10]
0x14001a1b8  xor     rcx, rsp; StackCookie
0x14001a1bb  call    __security_check_cookie
0x14001a1c0  lea     r11, [rsp+88h+var_8]
0x14001a1c8  mov     rbx, [r11+20h]
0x14001a1cc  mov     rsi, [r11+28h]
0x14001a1d0  mov     rsp, r11
0x14001a1d3  pop     rdi
0x14001a1d4  retn
```
