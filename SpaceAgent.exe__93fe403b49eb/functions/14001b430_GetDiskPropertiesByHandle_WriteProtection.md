# GetDiskPropertiesByHandle_WriteProtection

- ea: `0x14001b430`
- end: `0x14001b515`
- name: `GetDiskPropertiesByHandle_WriteProtection`
- size: `229`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a85c`
- `0x14001ac00`

## callees

- `0x14001b430`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001b4d1`
- `KERNEL32!GetLastError` at `0x14001b4d1`
- `KERNEL32!DeviceIoControl` at `0x14001b488`
- `KERNEL32!DeviceIoControl` at `0x14001b4c5`
- `KERNEL32!DeviceIoControl` at `0x14001b488`
- `KERNEL32!DeviceIoControl` at `0x14001b4c5`

## pseudocode

```c
__int64 __fastcall GetDiskPropertiesByHandle_WriteProtection(HANDLE hDevice, int *a2)
{
  unsigned int v4; // ebx
  BOOL v5; // edi
  int v6; // eax
  __int128 lpOutBuffer; // [rsp+40h] [rbp-28h] BYREF

  lpOutBuffer = 0;
  v4 = DeviceIoControl(hDevice, 0x700F0u, 0, 0, &lpOutBuffer, 0x10u, 0, 0);
  if ( v4 )
  {
    v5 = DeviceIoControl(hDevice, 0x70024u, 0, 0, 0, 0, 0, 0);
    if ( v5 || GetLastError() != 21 )
    {
      if ( (BYTE8(lpOutBuffer) & 2) != 0 || !v5 )
      {
        v6 = 1;
        goto LABEL_6;
      }
    }
    else
    {
      v4 = 0;
    }
  }
  v6 = 0;
LABEL_6:
  *a2 = v6;
  return v4;
}

```

## disassembly

```asm
0x14001b430  mov     r11, rsp
0x14001b433  mov     [r11+18h], rbx
0x14001b437  mov     [r11+20h], rsi
0x14001b43b  push    rdi
0x14001b43c  sub     rsp, 60h
0x14001b440  mov     rax, cs:__security_cookie
0x14001b447  xor     rax, rsp
0x14001b44a  mov     [rsp+68h+var_18], rax
0x14001b44f  mov     qword ptr [r11-30h], 0
0x14001b457  lea     rax, [r11-28h]
0x14001b45b  mov     qword ptr [r11-38h], 0
0x14001b463  mov     rsi, rdx
0x14001b466  xorps   xmm0, xmm0
0x14001b469  mov     [rsp+68h+nOutBufferSize], 10h; nOutBufferSize
0x14001b471  xor     r9d, r9d; nInBufferSize
0x14001b474  mov     [r11-48h], rax
0x14001b478  xor     r8d, r8d; lpInBuffer
0x14001b47b  mov     edx, 700F0h; dwIoControlCode
0x14001b480  mov     rdi, rcx
0x14001b483  movups  [rsp+68h+var_28], xmm0
0x14001b488  call    cs:__imp_DeviceIoControl
0x14001b48e  mov     ebx, eax
0x14001b490  test    eax, eax
0x14001b492  jz      short loc_14001B4DE
0x14001b494  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x14001b49d  xor     r9d, r9d; nInBufferSize
0x14001b4a0  mov     [rsp+68h+lpBytesReturned], 0; lpBytesReturned
0x14001b4a9  xor     r8d, r8d; lpInBuffer
0x14001b4ac  mov     [rsp+68h+nOutBufferSize], 0; nOutBufferSize
0x14001b4b4  mov     edx, 70024h; dwIoControlCode
0x14001b4b9  mov     rcx, rdi; hDevice
0x14001b4bc  mov     [rsp+68h+lpOutBuffer], 0; lpOutBuffer
0x14001b4c5  call    cs:__imp_DeviceIoControl
0x14001b4cb  mov     edi, eax
0x14001b4cd  test    eax, eax
0x14001b4cf  jnz     short loc_14001B503
0x14001b4d1  call    cs:__imp_GetLastError
0x14001b4d7  cmp     eax, 15h
0x14001b4da  jnz     short loc_14001B503
0x14001b4dc  xor     ebx, ebx
0x14001b4de  xor     eax, eax
0x14001b4e0  mov     [rsi], eax
0x14001b4e2  mov     eax, ebx
0x14001b4e4  mov     rcx, [rsp+68h+var_18]
0x14001b4e9  xor     rcx, rsp; StackCookie
0x14001b4ec  call    __security_check_cookie
0x14001b4f1  lea     r11, [rsp+68h+var_8]
0x14001b4f6  mov     rbx, [r11+20h]
0x14001b4fa  mov     rsi, [r11+28h]
0x14001b4fe  mov     rsp, r11
0x14001b501  pop     rdi
0x14001b502  retn
0x14001b503  test    byte ptr [rsp+68h+var_28+8], 2
0x14001b508  jnz     short loc_14001B50E
0x14001b50a  test    edi, edi
0x14001b50c  jnz     short loc_14001B4DE
0x14001b50e  mov     eax, 1
0x14001b513  jmp     short loc_14001B4E0
```
