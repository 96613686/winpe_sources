# AiUpdateDriverCertDataFromRegistry

- ea: `0x140002b48`
- end: `0x140002c60`
- name: `AiUpdateDriverCertDataFromRegistry`
- size: `280`
- prototype: `__int64 __fastcall(HANDLE hDevice, _WORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x140001bc4`

## callees

- `0x140002b48`
- `0x140002d39`
- `0x140002d60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c31`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140002c27`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140002c27`

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
0x140002b48  mov     [rsp+arg_10], rbx
0x140002b4d  mov     [rsp+arg_18], rsi
0x140002b52  push    rdi
0x140002b53  sub     rsp, 0F0h
0x140002b5a  mov     rax, cs:__security_cookie
0x140002b61  xor     rax, rsp
0x140002b64  mov     [rsp+0F8h+var_18], rax
0x140002b6c  mov     rbx, rdx
0x140002b6f  mov     rdi, rcx
0x140002b72  xor     edx, edx; Val
0x140002b74  lea     rcx, [rsp+0F8h+var_A6]; void *
0x140002b79  mov     r8d, 82h; Size
0x140002b7f  call    memset_0
0x140002b84  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002b88  xor     esi, esi
0x140002b8a  inc     rax
0x140002b8d  cmp     [rbx+rax*2], si
0x140002b91  jnz     short loc_140002B8A
0x140002b93  add     ax, ax
0x140002b96  mov     [rsp+0F8h+InBuffer], ax
0x140002b9b  jnz     short loc_140002BA7
0x140002b9d  mov     ebx, 57h ; 'W'
0x140002ba2  jmp     loc_140002C39
0x140002ba7  mov     ecx, 7FFFFFFEh
0x140002bac  lea     rax, [rsp+0F8h+var_A6]
0x140002bb1  mov     edx, 41h ; 'A'
0x140002bb6  test    rcx, rcx
0x140002bb9  jz      short loc_140002BDA
0x140002bbb  movzx   r8d, word ptr [rbx]
0x140002bbf  test    r8w, r8w
0x140002bc3  jz      short loc_140002BDA
0x140002bc5  mov     [rax], r8w
0x140002bc9  add     rbx, 2
0x140002bcd  add     rax, 2
0x140002bd1  dec     rcx
0x140002bd4  sub     rdx, 1
0x140002bd8  jnz     short loc_140002BB6
0x140002bda  test    rdx, rdx
0x140002bdd  lea     rcx, [rax-2]
0x140002be1  cmovnz  rcx, rax
0x140002be5  mov     [rcx], si
0x140002be8  jnz     short loc_140002BF1
0x140002bea  mov     ebx, 7Ah ; 'z'
0x140002bef  jmp     short loc_140002C39
0x140002bf1  movzx   r9d, [rsp+0F8h+InBuffer]
0x140002bf7  lea     rax, [rsp+0F8h+BytesReturned]
0x140002bfc  mov     [rsp+0F8h+lpOverlapped], rsi; lpOverlapped
0x140002c01  lea     r8, [rsp+0F8h+InBuffer]; lpInBuffer
0x140002c06  mov     [rsp+0F8h+lpBytesReturned], rax; lpBytesReturned
0x140002c0b  add     r9d, 2; nInBufferSize
0x140002c0f  mov     [rsp+0F8h+nOutBufferSize], esi; nOutBufferSize
0x140002c13  mov     edx, 22A000h; dwIoControlCode
0x140002c18  mov     rcx, rdi; hDevice
0x140002c1b  mov     [rsp+0F8h+BytesReturned], r9d
0x140002c20  mov     [rsp+0F8h+lpOutBuffer], rsi; lpOutBuffer
0x140002c25  mov     ebx, esi
0x140002c27  call    cs:__imp_DeviceIoControl
0x140002c2d  test    eax, eax
0x140002c2f  jnz     short loc_140002C39
0x140002c31  call    cs:__imp_GetLastError
0x140002c37  mov     ebx, eax
0x140002c39  mov     eax, ebx
0x140002c3b  mov     rcx, [rsp+0F8h+var_18]
0x140002c43  xor     rcx, rsp; StackCookie
0x140002c46  call    __security_check_cookie
0x140002c4b  lea     r11, [rsp+0F8h+var_8]
0x140002c53  mov     rbx, [r11+20h]
0x140002c57  mov     rsi, [r11+28h]
0x140002c5b  mov     rsp, r11
0x140002c5e  pop     rdi
0x140002c5f  retn
```
