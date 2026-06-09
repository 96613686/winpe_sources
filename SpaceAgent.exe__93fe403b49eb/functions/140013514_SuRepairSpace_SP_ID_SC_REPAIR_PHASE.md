# SuRepairSpace(_SP_ID *,_SC_REPAIR_PHASE)

- ea: `0x140013514`
- end: `0x1400135bc`
- name: `?SuRepairSpace@@YAHPEAU_SP_ID@@W4_SC_REPAIR_PHASE@@@Z`
- size: `168`
- prototype: `BOOL __fastcall(__int128 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140016900`

## callees

- `0x140013514`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x140013598`
- `KERNEL32!DeviceIoControl` at `0x140013598`

## pseudocode

```c
BOOL __fastcall SuRepairSpace(__int128 *a1)
{
  __int128 v1; // xmm0
  BOOL result; // eax
  __int128 v3; // xmm1
  int v4; // ebx
  DWORD BytesReturned; // [rsp+40h] [rbp-48h] BYREF
  int InBuffer; // [rsp+48h] [rbp-40h] BYREF
  __int128 v7; // [rsp+4Ch] [rbp-3Ch]
  __int128 v8; // [rsp+5Ch] [rbp-2Ch]
  int v9; // [rsp+6Ch] [rbp-1Ch]

  v1 = *a1;
  result = 1;
  BytesReturned = 0;
  v3 = a1[1];
  InBuffer = 40;
  v4 = 1;
  v7 = v1;
  v8 = v3;
  while ( v4 <= 6 )
  {
    v9 = v4;
    result = DeviceIoControl(Spaceport, 0xE7C818u, &InBuffer, 0x28u, 0, 0, &BytesReturned, 0);
    if ( !result )
      break;
    ++v4;
  }
  return result;
}

```

## disassembly

```asm
0x140013514  push    rbx
0x140013516  sub     rsp, 80h
0x14001351d  mov     rax, cs:__security_cookie
0x140013524  xor     rax, rsp
0x140013527  mov     [rsp+88h+var_18], rax
0x14001352c  movups  xmm0, xmmword ptr [rcx]
0x14001352f  mov     eax, 1
0x140013534  mov     [rsp+88h+BytesReturned], 0
0x14001353c  movups  xmm1, xmmword ptr [rcx+10h]
0x140013540  mov     [rsp+88h+InBuffer], 28h ; '('
0x140013548  mov     ebx, eax
0x14001354a  movups  [rsp+88h+var_3C], xmm0
0x14001354f  movups  [rsp+88h+var_2C], xmm1
0x140013554  cmp     ebx, 6
0x140013557  jg      short loc_1400135A6
0x140013559  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x140013560  lea     rax, [rsp+88h+BytesReturned]
0x140013565  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x14001356e  lea     r8, [rsp+88h+InBuffer]; lpInBuffer
0x140013573  mov     [rsp+88h+lpBytesReturned], rax; lpBytesReturned
0x140013578  mov     r9d, 28h ; '('; nInBufferSize
0x14001357e  mov     [rsp+88h+nOutBufferSize], 0; nOutBufferSize
0x140013586  mov     edx, 0E7C818h; dwIoControlCode
0x14001358b  mov     [rsp+88h+lpOutBuffer], 0; lpOutBuffer
0x140013594  mov     [rsp+88h+var_1C], ebx
0x140013598  call    cs:__imp_DeviceIoControl
0x14001359e  test    eax, eax
0x1400135a0  jz      short loc_1400135A6
0x1400135a2  inc     ebx
0x1400135a4  jmp     short loc_140013554
0x1400135a6  mov     rcx, [rsp+88h+var_18]
0x1400135ab  xor     rcx, rsp; StackCookie
0x1400135ae  call    __security_check_cookie
0x1400135b3  add     rsp, 80h
0x1400135ba  pop     rbx
0x1400135bb  retn
```
