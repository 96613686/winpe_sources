# NetpGetComputerNameEx2

- ea: `0x180006360`
- end: `0x180006422`
- name: `NetpGetComputerNameEx2`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005dec`
- `0x180026840`

## callees

- `0x180006360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800063a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800063db`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800063a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800063db`
- `netutils!NetApiBufferFree` at `0x1800063fc`
- `netutils!NetApiBufferFree` at `0x1800063fc`
- `netutils!NetApiBufferAllocate` at `0x1800063c3`
- `netutils!NetApiBufferAllocate` at `0x1800063c3`

## pseudocode

```c
__int64 __fastcall NetpGetComputerNameEx2(LPVOID *a1, COMPUTER_NAME_FORMAT a2)
{
  DWORD LastError; // ebx
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF
  LPVOID Buffer; // [rsp+40h] [rbp+18h] BYREF

  nSize = 0;
  Buffer = 0;
  if ( !a1 )
    return 87;
  *a1 = 0;
  if ( (unsigned int)a2 >= ComputerNameMax )
    return 87;
  if ( GetComputerNameExW(a2, 0, &nSize) || GetLastError() != 234 )
  {
    return 87;
  }
  else
  {
    LastError = NetApiBufferAllocate(2 * nSize, &Buffer);
    if ( !LastError )
    {
      if ( GetComputerNameExW(a2, (LPWSTR)Buffer, &nSize) )
      {
        *a1 = Buffer;
      }
      else
      {
        LastError = GetLastError();
        NetApiBufferFree(Buffer);
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180006360  mov     rax, rsp
0x180006363  mov     [rax+10h], rbx
0x180006367  mov     [rax+20h], rsi
0x18000636b  push    rdi
0x18000636c  sub     rsp, 20h
0x180006370  mov     dword ptr [rax+8], 0
0x180006377  mov     esi, edx
0x180006379  mov     qword ptr [rax+18h], 0
0x180006381  mov     rdi, rcx
0x180006384  test    rcx, rcx
0x180006387  jz      loc_18000640D
0x18000638d  mov     qword ptr [rcx], 0
0x180006394  cmp     edx, 8
0x180006397  jnb     short loc_18000640D
0x180006399  lea     r8, [rax+8]; nSize
0x18000639d  xor     edx, edx; lpBuffer
0x18000639f  mov     ecx, esi; NameType
0x1800063a1  call    cs:__imp_GetComputerNameExW
0x1800063a7  test    eax, eax
0x1800063a9  jnz     short loc_180006404
0x1800063ab  call    cs:__imp_GetLastError
0x1800063b1  cmp     eax, 0EAh
0x1800063b6  jnz     short loc_180006404
0x1800063b8  mov     ecx, [rsp+28h+nSize]
0x1800063bc  lea     rdx, [rsp+28h+Buffer]; Buffer
0x1800063c1  add     ecx, ecx; ByteCount
0x1800063c3  call    cs:__imp_NetApiBufferAllocate
0x1800063c9  mov     ebx, eax
0x1800063cb  test    eax, eax
0x1800063cd  jnz     short loc_180006409
0x1800063cf  mov     rdx, [rsp+28h+Buffer]; lpBuffer
0x1800063d4  lea     r8, [rsp+28h+nSize]; nSize
0x1800063d9  mov     ecx, esi; NameType
0x1800063db  call    cs:__imp_GetComputerNameExW
0x1800063e1  test    eax, eax
0x1800063e3  jz      short loc_1800063EF
0x1800063e5  mov     rcx, [rsp+28h+Buffer]
0x1800063ea  mov     [rdi], rcx
0x1800063ed  jmp     short loc_180006409
0x1800063ef  call    cs:__imp_GetLastError
0x1800063f5  mov     rcx, [rsp+28h+Buffer]; Buffer
0x1800063fa  mov     ebx, eax
0x1800063fc  call    cs:__imp_NetApiBufferFree
0x180006402  jmp     short loc_180006409
0x180006404  mov     ebx, 57h ; 'W'
0x180006409  mov     eax, ebx
0x18000640b  jmp     short loc_180006412
0x18000640d  mov     eax, 57h ; 'W'
0x180006412  mov     rbx, [rsp+28h+arg_8]
0x180006417  mov     rsi, [rsp+28h+arg_18]
0x18000641c  add     rsp, 20h
0x180006420  pop     rdi
0x180006421  retn
```
