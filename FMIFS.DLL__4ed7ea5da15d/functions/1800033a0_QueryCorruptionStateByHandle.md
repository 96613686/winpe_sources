# QueryCorruptionStateByHandle

- ea: `0x1800033a0`
- end: `0x180003543`
- name: `QueryCorruptionStateByHandle`
- size: `419`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ca0`

## callees

- `0x1800033a0`
- `0x180009780`

## import_xrefs

- `msvcrt!free` at `0x18000342f`
- `msvcrt!free` at `0x18000353b`
- `msvcrt!free` at `0x18000342f`
- `msvcrt!free` at `0x18000353b`
- `msvcrt!realloc` at `0x180003467`
- `msvcrt!realloc` at `0x180003467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003523`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003523`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800034a5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800034f2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800034a5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800034f2`

## pseudocode

```c
bool __fastcall QueryCorruptionStateByHandle(HANDLE hDevice, __int64 a2, char a3)
{
  __int64 v3; // rax
  DWORD *v6; // rsi
  DWORD *lpOutBuffer; // rbx
  DWORD nOutBufferSize; // r14d
  BOOL v9; // edi
  BOOL v11; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-78h] BYREF
  int OutBuffer; // [rsp+44h] [rbp-74h] BYREF
  int InBuffer; // [rsp+48h] [rbp-70h] BYREF
  __int64 v15; // [rsp+4Ch] [rbp-6Ch]
  __int64 v16; // [rsp+54h] [rbp-64h]
  __int128 v17; // [rsp+5Ch] [rbp-5Ch]

  v15 = 36;
  BytesReturned = 0;
  v3 = 0;
  OutBuffer = 0;
  InBuffer = 128;
  if ( !a3 )
    v3 = 4;
  v16 = v3;
  v6 = 0;
  lpOutBuffer = 0;
  nOutBufferSize = 1024;
  v9 = 0;
  v17 = 0;
  while ( 1 )
  {
    if ( v9 )
    {
      *(_DWORD *)(a2 + 4) = v6[6];
      *(_DWORD *)(a2 + 8) = v6[7];
      if ( lpOutBuffer )
        goto LABEL_6;
      return v9;
    }
    lpOutBuffer = (DWORD *)realloc(v6, nOutBufferSize);
    if ( !lpOutBuffer )
      break;
    v9 = DeviceIoControl(hDevice, 0x90260u, &InBuffer, 0x24u, lpOutBuffer, nOutBufferSize, &BytesReturned, 0);
    if ( !v9 )
    {
      if ( GetLastError() != 234 )
      {
        v11 = DeviceIoControl(hDevice, 0x90078u, 0, 0, &OutBuffer, 4u, &BytesReturned, 0);
        LOBYTE(v9) = v11;
        if ( v11 )
          *(_DWORD *)(a2 + 4) = (OutBuffer & 1) != 0 ? 0x11 : 0;
LABEL_6:
        free(lpOutBuffer);
        return v9;
      }
      nOutBufferSize = *lpOutBuffer;
    }
    v6 = lpOutBuffer;
  }
  if ( v6 )
    free(v6);
  SetLastError(8u);
  return 0;
}

```

## disassembly

```asm
0x1800033a0  mov     [rsp+arg_10], rbx
0x1800033a5  push    rbp
0x1800033a6  push    rsi
0x1800033a7  push    rdi
0x1800033a8  push    r12
0x1800033aa  push    r13
0x1800033ac  push    r14
0x1800033ae  push    r15
0x1800033b0  sub     rsp, 80h
0x1800033b7  mov     rax, cs:__security_cookie
0x1800033be  xor     rax, rsp
0x1800033c1  mov     [rsp+0B8h+var_48], rax
0x1800033c6  xor     r12d, r12d
0x1800033c9  mov     [rsp+0B8h+var_6C], 24h ; '$'
0x1800033d2  test    r8b, r8b
0x1800033d5  mov     [rsp+0B8h+BytesReturned], r12d
0x1800033da  mov     eax, r12d
0x1800033dd  mov     [rsp+0B8h+OutBuffer], r12d
0x1800033e2  mov     r13d, 4
0x1800033e8  mov     [rsp+0B8h+InBuffer], 80h
0x1800033f0  cmovz   eax, r13d
0x1800033f4  xorps   xmm0, xmm0
0x1800033f7  mov     [rsp+0B8h+var_64], rax
0x1800033fc  mov     rbp, rdx
0x1800033ff  mov     r15, rcx
0x180003402  mov     esi, r12d
0x180003405  mov     ebx, r12d
0x180003408  mov     r14d, 400h
0x18000340e  mov     edi, r12d
0x180003411  movdqu  [rsp+0B8h+var_5C], xmm0
0x180003417  test    edi, edi
0x180003419  jz      short loc_180003461
0x18000341b  mov     eax, [rsi+18h]
0x18000341e  mov     [rbp+4], eax
0x180003421  mov     eax, [rsi+1Ch]
0x180003424  mov     [rbp+8], eax
0x180003427  test    rbx, rbx
0x18000342a  jz      short loc_180003435
0x18000342c  mov     rcx, rbx; Block
0x18000342f  call    cs:__imp_free
0x180003435  movzx   eax, dil
0x180003439  mov     rcx, [rsp+0B8h+var_48]
0x18000343e  xor     rcx, rsp; StackCookie
0x180003441  call    __security_check_cookie
0x180003446  mov     rbx, [rsp+0B8h+arg_10]
0x18000344e  add     rsp, 80h
0x180003455  pop     r15
0x180003457  pop     r14
0x180003459  pop     r13
0x18000345b  pop     r12
0x18000345d  pop     rdi
0x18000345e  pop     rsi
0x18000345f  pop     rbp
0x180003460  retn
0x180003461  mov     edx, r14d; Size
0x180003464  mov     rcx, rsi; Block
0x180003467  call    cs:__imp_realloc
0x18000346d  mov     rbx, rax
0x180003470  test    rax, rax
0x180003473  jz      loc_180003519
0x180003479  mov     [rsp+0B8h+lpOverlapped], r12; lpOverlapped
0x18000347e  lea     rax, [rsp+0B8h+BytesReturned]
0x180003483  mov     [rsp+0B8h+lpBytesReturned], rax; lpBytesReturned
0x180003488  lea     r8, [rsp+0B8h+InBuffer]; lpInBuffer
0x18000348d  mov     [rsp+0B8h+nOutBufferSize], r14d; nOutBufferSize
0x180003492  mov     r9d, 24h ; '$'; nInBufferSize
0x180003498  mov     edx, 90260h; dwIoControlCode
0x18000349d  mov     [rsp+0B8h+lpOutBuffer], rbx; lpOutBuffer
0x1800034a2  mov     rcx, r15; hDevice
0x1800034a5  call    cs:__imp_DeviceIoControl
0x1800034ab  mov     edi, eax
0x1800034ad  test    eax, eax
0x1800034af  jz      short loc_1800034B9
0x1800034b1  mov     rsi, rbx
0x1800034b4  jmp     loc_180003417
0x1800034b9  call    cs:__imp_GetLastError
0x1800034bf  cmp     eax, 0EAh
0x1800034c4  jz      short loc_180003530
0x1800034c6  mov     [rsp+0B8h+lpOverlapped], r12; lpOverlapped
0x1800034cb  lea     rax, [rsp+0B8h+BytesReturned]
0x1800034d0  mov     [rsp+0B8h+lpBytesReturned], rax; lpBytesReturned
0x1800034d5  xor     r9d, r9d; nInBufferSize
0x1800034d8  lea     rax, [rsp+0B8h+OutBuffer]
0x1800034dd  mov     [rsp+0B8h+nOutBufferSize], r13d; nOutBufferSize
0x1800034e2  xor     r8d, r8d; lpInBuffer
0x1800034e5  mov     [rsp+0B8h+lpOutBuffer], rax; lpOutBuffer
0x1800034ea  mov     edx, 90078h; dwIoControlCode
0x1800034ef  mov     rcx, r15; hDevice
0x1800034f2  call    cs:__imp_DeviceIoControl
0x1800034f8  mov     edi, eax
0x1800034fa  test    eax, eax
0x1800034fc  jz      loc_18000342C
0x180003502  movzx   ecx, byte ptr [rsp+0B8h+OutBuffer]
0x180003507  and     cl, 1
0x18000350a  neg     cl
0x18000350c  sbb     ecx, ecx
0x18000350e  and     ecx, 11h
0x180003511  mov     [rbp+4], ecx
0x180003514  jmp     loc_18000342C
0x180003519  test    rsi, rsi
0x18000351c  jnz     short loc_180003538
0x18000351e  mov     ecx, 8; dwErrCode
0x180003523  call    cs:__imp_SetLastError
0x180003529  xor     al, al
0x18000352b  jmp     loc_180003439
0x180003530  mov     r14d, [rbx]
0x180003533  jmp     loc_1800034B1
0x180003538  mov     rcx, rsi; Block
0x18000353b  call    cs:__imp_free
0x180003541  jmp     short loc_18000351E
```
