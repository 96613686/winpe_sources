# AiUpdateDriverCertDataFromRegistry

- ea: `0x180008de0`
- end: `0x180008ef8`
- name: `AiUpdateDriverCertDataFromRegistry`
- size: `280`
- prototype: `__int64 __fastcall(HANDLE hDevice, _WORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800090a0`

## callees

- `0x180008de0`
- `0x18000c0a2`
- `0x18000c0e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ec9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008ebf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008ebf`

## pseudocode

```c
__int64 __fastcall AiUpdateDriverCertDataFromRegistry(HANDLE hDevice, _WORD *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  _WORD *v7; // rax
  __int64 v8; // rdx
  _WORD *v9; // rcx
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-B8h] BYREF
  unsigned __int16 InBuffer; // [rsp+50h] [rbp-A8h] BYREF
  _BYTE v13[142]; // [rsp+52h] [rbp-A6h] BYREF

  memset_0(v13, 0, 0x82u);
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  InBuffer = 2 * v4;
  if ( 2 * (_WORD)v4 )
  {
    v6 = 2147483646;
    v7 = v13;
    v8 = 65;
    do
    {
      if ( !v6 )
        break;
      if ( !*a2 )
        break;
      *v7++ = *a2++;
      --v6;
      --v8;
    }
    while ( v8 );
    v9 = v7 - 1;
    if ( v8 )
      v9 = v7;
    *v9 = 0;
    if ( v8 )
    {
      BytesReturned[0] = InBuffer + 2;
      v5 = 0;
      if ( !DeviceIoControl(hDevice, 0x22A000u, &InBuffer, BytesReturned[0], 0, 0, BytesReturned, 0) )
        return GetLastError();
    }
    else
    {
      return 122;
    }
  }
  else
  {
    return 87;
  }
  return v5;
}

```

## disassembly

```asm
0x180008de0  mov     [rsp+arg_10], rbx
0x180008de5  mov     [rsp+arg_18], rsi
0x180008dea  push    rdi
0x180008deb  sub     rsp, 0F0h
0x180008df2  mov     rax, cs:__security_cookie
0x180008df9  xor     rax, rsp
0x180008dfc  mov     [rsp+0F8h+var_18], rax
0x180008e04  mov     rbx, rdx
0x180008e07  mov     rdi, rcx
0x180008e0a  xor     edx, edx; Val
0x180008e0c  lea     rcx, [rsp+0F8h+var_A6]; void *
0x180008e11  mov     r8d, 82h; Size
0x180008e17  call    memset_0
0x180008e1c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008e20  xor     esi, esi
0x180008e22  inc     rax
0x180008e25  cmp     [rbx+rax*2], si
0x180008e29  jnz     short loc_180008E22
0x180008e2b  add     ax, ax
0x180008e2e  mov     [rsp+0F8h+InBuffer], ax
0x180008e33  jnz     short loc_180008E3F
0x180008e35  mov     ebx, 57h ; 'W'
0x180008e3a  jmp     loc_180008ED1
0x180008e3f  mov     ecx, 7FFFFFFEh
0x180008e44  lea     rax, [rsp+0F8h+var_A6]
0x180008e49  mov     edx, 41h ; 'A'
0x180008e4e  test    rcx, rcx
0x180008e51  jz      short loc_180008E72
0x180008e53  movzx   r8d, word ptr [rbx]
0x180008e57  test    r8w, r8w
0x180008e5b  jz      short loc_180008E72
0x180008e5d  mov     [rax], r8w
0x180008e61  add     rbx, 2
0x180008e65  add     rax, 2
0x180008e69  dec     rcx
0x180008e6c  sub     rdx, 1
0x180008e70  jnz     short loc_180008E4E
0x180008e72  test    rdx, rdx
0x180008e75  lea     rcx, [rax-2]
0x180008e79  cmovnz  rcx, rax
0x180008e7d  mov     [rcx], si
0x180008e80  jnz     short loc_180008E89
0x180008e82  mov     ebx, 7Ah ; 'z'
0x180008e87  jmp     short loc_180008ED1
0x180008e89  movzx   r9d, [rsp+0F8h+InBuffer]
0x180008e8f  lea     rax, [rsp+0F8h+BytesReturned]
0x180008e94  mov     [rsp+0F8h+lpOverlapped], rsi; lpOverlapped
0x180008e99  lea     r8, [rsp+0F8h+InBuffer]; lpInBuffer
0x180008e9e  mov     [rsp+0F8h+lpBytesReturned], rax; lpBytesReturned
0x180008ea3  add     r9d, 2; nInBufferSize
0x180008ea7  mov     [rsp+0F8h+nOutBufferSize], esi; nOutBufferSize
0x180008eab  mov     edx, 22A000h; dwIoControlCode
0x180008eb0  mov     rcx, rdi; hDevice
0x180008eb3  mov     [rsp+0F8h+BytesReturned], r9d
0x180008eb8  mov     [rsp+0F8h+lpOutBuffer], rsi; lpOutBuffer
0x180008ebd  mov     ebx, esi
0x180008ebf  call    cs:__imp_DeviceIoControl
0x180008ec5  test    eax, eax
0x180008ec7  jnz     short loc_180008ED1
0x180008ec9  call    cs:__imp_GetLastError
0x180008ecf  mov     ebx, eax
0x180008ed1  mov     eax, ebx
0x180008ed3  mov     rcx, [rsp+0F8h+var_18]
0x180008edb  xor     rcx, rsp; StackCookie
0x180008ede  call    __security_check_cookie
0x180008ee3  lea     r11, [rsp+0F8h+var_8]
0x180008eeb  mov     rbx, [r11+20h]
0x180008eef  mov     rsi, [r11+28h]
0x180008ef3  mov     rsp, r11
0x180008ef6  pop     rdi
0x180008ef7  retn
```
