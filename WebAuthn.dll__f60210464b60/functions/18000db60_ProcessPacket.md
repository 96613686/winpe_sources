# _ProcessPacket

- ea: `0x18000db60`
- end: `0x18000dca5`
- name: `_ProcessPacket`
- size: `325`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ce10`
- `0x1800e9510`

## callees

- `0x18000db60`
- `0x18002bbf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbca`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000dc28`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000dc28`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000dbb7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000dbb7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000dbaf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000dbaf`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18000dc8d`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18000dc8d`

## pseudocode

```c
__int64 __fastcall ProcessPacket(int a1, __int64 a2, __int64 a3, DWORD a4, DWORD dwMilliseconds, void *a6)
{
  DWORD v6; // edi
  void *v7; // r11
  bool v9; // zf
  void *v10; // rcx
  BOOL v11; // eax
  DWORD LastError; // eax
  unsigned int NonzeroLastError; // ebx
  __int64 result; // rax
  DWORD v15; // eax
  HANDLE Handles[2]; // [rsp+30h] [rbp-38h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-28h] BYREF

  v6 = a4 + 1;
  v7 = (void *)a3;
  if ( !*(_DWORD *)(a2 + 20) )
  {
    v7 = (void *)(a3 + 1);
    v6 = a4;
  }
  v9 = a1 == 0;
  v10 = *(void **)(a2 + 8);
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( v9 )
    v11 = ReadFile(v10, v7, v6, 0, &Overlapped);
  else
    v11 = WriteFile(v10, v7, v6, 0, &Overlapped);
  if ( !v11 )
  {
    LastError = GetLastError();
    NonzeroLastError = LastError;
    if ( !LastError )
      return 2147549183LL;
    if ( LastError != 997 )
      return NonzeroLastError;
    Handles[0] = *(HANDLE *)(a2 + 8);
    Handles[1] = a6;
    v15 = WaitForMultipleObjects((a6 != 0) + 1, Handles, 0, dwMilliseconds);
    if ( v15 )
    {
      if ( v15 == 1 )
      {
        NonzeroLastError = 1223;
        goto LABEL_22;
      }
      if ( v15 == 258 )
      {
        NonzeroLastError = 1460;
        goto LABEL_22;
      }
      if ( v15 != -1 )
      {
        NonzeroLastError = -2147418113;
LABEL_22:
        CancelIoEx(*(HANDLE *)(a2 + 8), &Overlapped);
        return NonzeroLastError;
      }
      NonzeroLastError = _GetNonzeroLastError();
      if ( NonzeroLastError )
        goto LABEL_22;
    }
  }
  result = LODWORD(Overlapped.Internal);
  if ( !LODWORD(Overlapped.Internal) && LODWORD(Overlapped.InternalHigh) != v6 )
    return 24;
  return result;
}

```

## disassembly

```asm
0x18000db60  mov     [rsp+arg_8], rsi
0x18000db65  push    rdi
0x18000db66  sub     rsp, 60h
0x18000db6a  mov     r10d, [rdx+14h]
0x18000db6e  lea     rax, [r8+1]
0x18000db72  test    r10d, r10d
0x18000db75  lea     edi, [r9+1]
0x18000db79  mov     r11, r8
0x18000db7c  mov     rsi, rdx
0x18000db7f  cmovz   r11, rax
0x18000db83  cmovz   edi, r9d
0x18000db87  xorps   xmm0, xmm0
0x18000db8a  lea     rax, [rsp+68h+Overlapped]
0x18000db8f  xor     r9d, r9d; lpNumberOfBytesRead
0x18000db92  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18000db97  test    ecx, ecx
0x18000db99  mov     r8d, edi; nNumberOfBytesToRead
0x18000db9c  mov     rcx, [rsi+8]; hFile
0x18000dba0  mov     rdx, r11; lpBuffer
0x18000dba3  movups  xmmword ptr [rsp+68h+Overlapped.Internal], xmm0
0x18000dba8  movups  xmmword ptr [rsp+68h+Overlapped.10h], xmm0
0x18000dbad  jz      short loc_18000DBB7
0x18000dbaf  call    cs:__imp_WriteFile
0x18000dbb5  jmp     short loc_18000DBBD
0x18000dbb7  call    cs:__imp_ReadFile
0x18000dbbd  mov     [rsp+68h+arg_0], rbx
0x18000dbc2  test    eax, eax
0x18000dbc4  jnz     loc_18000DC55
0x18000dbca  call    cs:__imp_GetLastError
0x18000dbd0  mov     ebx, eax
0x18000dbd2  test    eax, eax
0x18000dbd4  jnz     short loc_18000DBED
0x18000dbd6  mov     ebx, 8000FFFFh
0x18000dbdb  mov     eax, ebx
0x18000dbdd  mov     rbx, [rsp+68h+arg_0]
0x18000dbe2  mov     rsi, [rsp+68h+arg_8]
0x18000dbe7  add     rsp, 60h
0x18000dbeb  pop     rdi
0x18000dbec  retn
0x18000dbed  cmp     eax, 3E5h
0x18000dbf2  jnz     loc_18000DC93
0x18000dbf8  mov     rax, [rsi+8]
0x18000dbfc  lea     rdx, [rsp+68h+Handles]; lpHandles
0x18000dc01  mov     r9d, [rsp+68h+dwMilliseconds]; dwMilliseconds
0x18000dc09  xor     ecx, ecx
0x18000dc0b  mov     [rsp+68h+Handles], rax
0x18000dc10  mov     rax, [rsp+68h+arg_28]
0x18000dc18  test    rax, rax
0x18000dc1b  mov     [rsp+68h+var_30], rax
0x18000dc20  setnz   cl
0x18000dc23  xor     r8d, r8d; bWaitAll
0x18000dc26  inc     ecx; nCount
0x18000dc28  call    cs:__imp_WaitForMultipleObjects
0x18000dc2e  test    eax, eax
0x18000dc30  jz      short loc_18000DC55
0x18000dc32  cmp     eax, 1
0x18000dc35  jz      short loc_18000DC7F
0x18000dc37  cmp     eax, 102h
0x18000dc3c  jz      short loc_18000DC78
0x18000dc3e  cmp     eax, 0FFFFFFFFh
0x18000dc41  jz      short loc_18000DC4A
0x18000dc43  mov     ebx, 8000FFFFh
0x18000dc48  jmp     short loc_18000DC84
0x18000dc4a  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x18000dc4f  mov     ebx, eax
0x18000dc51  test    eax, eax
0x18000dc53  jnz     short loc_18000DC84
0x18000dc55  mov     eax, dword ptr [rsp+68h+Overlapped.Internal]
0x18000dc59  test    eax, eax
0x18000dc5b  jnz     short loc_18000DC68
0x18000dc5d  cmp     dword ptr [rsp+68h+Overlapped.InternalHigh], edi
0x18000dc61  jz      short loc_18000DC68
0x18000dc63  mov     eax, 18h
0x18000dc68  mov     rbx, [rsp+68h+arg_0]
0x18000dc6d  mov     rsi, [rsp+68h+arg_8]
0x18000dc72  add     rsp, 60h
0x18000dc76  pop     rdi
0x18000dc77  retn
0x18000dc78  mov     ebx, 5B4h
0x18000dc7d  jmp     short loc_18000DC84
0x18000dc7f  mov     ebx, 4C7h
0x18000dc84  mov     rcx, [rsi+8]; hFile
0x18000dc88  lea     rdx, [rsp+68h+Overlapped]; lpOverlapped
0x18000dc8d  call    cs:__imp_CancelIoEx
0x18000dc93  mov     rsi, [rsp+68h+arg_8]
0x18000dc98  mov     eax, ebx
0x18000dc9a  mov     rbx, [rsp+68h+arg_0]
0x18000dc9f  add     rsp, 60h
0x18000dca3  pop     rdi
0x18000dca4  retn
```
