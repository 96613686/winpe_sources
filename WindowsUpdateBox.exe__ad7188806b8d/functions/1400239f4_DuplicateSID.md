# DuplicateSID

- ea: `0x1400239f4`
- end: `0x140023abe`
- name: `DuplicateSID`
- size: `202`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140023ac4`

## callees

- `0x1400239f4`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x140023a0d`
- `ADVAPI32!GetLengthSid` at `0x140023a0d`
- `ADVAPI32!CopySid` at `0x140023a4c`
- `ADVAPI32!CopySid` at `0x140023a4c`
- `KERNEL32!HeapFree` at `0x140023a7e`
- `KERNEL32!HeapFree` at `0x140023a7e`
- `KERNEL32!HeapAlloc` at `0x140023a30`
- `KERNEL32!HeapAlloc` at `0x140023a30`
- `KERNEL32!GetProcessHeap` at `0x140023a1b`
- `KERNEL32!GetProcessHeap` at `0x140023a6a`
- `KERNEL32!GetProcessHeap` at `0x140023a1b`
- `KERNEL32!GetProcessHeap` at `0x140023a6a`
- `KERNEL32!GetLastError` at `0x140023a5c`
- `KERNEL32!GetLastError` at `0x140023a5c`
- `KERNEL32!SetLastError` at `0x140023a99`
- `KERNEL32!SetLastError` at `0x140023a99`

## pseudocode

```c
void *__fastcall DuplicateSID(PSID pSourceSid)
{
  DWORD LastError; // edi
  DWORD LengthSid; // ebp
  HANDLE ProcessHeap; // rax
  void *v5; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  LastError = 0;
  LengthSid = GetLengthSid(pSourceSid);
  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 8u, LengthSid);
  v6 = v5;
  if ( v5 )
  {
    if ( !CopySid(LengthSid, v5, pSourceSid) )
    {
      LastError = GetLastError();
      v7 = GetProcessHeap();
      if ( HeapFree(v7, 0, v6) )
        v6 = 0;
    }
  }
  else
  {
    LastError = 14;
  }
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x1400239f4  mov     [rsp+arg_0], rbx
0x1400239f9  mov     [rsp+arg_8], rbp
0x1400239fe  mov     [rsp+arg_10], rsi
0x140023a03  push    rdi
0x140023a04  sub     rsp, 20h
0x140023a08  mov     rsi, rcx
0x140023a0b  xor     edi, edi
0x140023a0d  call    cs:__imp_GetLengthSid
0x140023a14  nop     dword ptr [rax+rax+00h]
0x140023a19  mov     ebp, eax
0x140023a1b  call    cs:__imp_GetProcessHeap
0x140023a22  nop     dword ptr [rax+rax+00h]
0x140023a27  mov     r8d, ebp; dwBytes
0x140023a2a  lea     edx, [rdi+8]; dwFlags
0x140023a2d  mov     rcx, rax; hHeap
0x140023a30  call    cs:__imp_HeapAlloc
0x140023a37  nop     dword ptr [rax+rax+00h]
0x140023a3c  mov     rbx, rax
0x140023a3f  test    rax, rax
0x140023a42  jz      short loc_140023A92
0x140023a44  mov     r8, rsi; pSourceSid
0x140023a47  mov     rdx, rax; pDestinationSid
0x140023a4a  mov     ecx, ebp; nDestinationSidLength
0x140023a4c  call    cs:__imp_CopySid
0x140023a53  nop     dword ptr [rax+rax+00h]
0x140023a58  test    eax, eax
0x140023a5a  jnz     short loc_140023A97
0x140023a5c  call    cs:__imp_GetLastError
0x140023a63  nop     dword ptr [rax+rax+00h]
0x140023a68  mov     edi, eax
0x140023a6a  call    cs:__imp_GetProcessHeap
0x140023a71  nop     dword ptr [rax+rax+00h]
0x140023a76  mov     r8, rbx; lpMem
0x140023a79  xor     edx, edx; dwFlags
0x140023a7b  mov     rcx, rax; hHeap
0x140023a7e  call    cs:__imp_HeapFree
0x140023a85  nop     dword ptr [rax+rax+00h]
0x140023a8a  test    eax, eax
0x140023a8c  jz      short loc_140023A97
0x140023a8e  xor     ebx, ebx
0x140023a90  jmp     short loc_140023A97
0x140023a92  mov     edi, 0Eh
0x140023a97  mov     ecx, edi; dwErrCode
0x140023a99  call    cs:__imp_SetLastError
0x140023aa0  nop     dword ptr [rax+rax+00h]
0x140023aa5  mov     rbp, [rsp+28h+arg_8]
0x140023aaa  mov     rax, rbx
0x140023aad  mov     rbx, [rsp+28h+arg_0]
0x140023ab2  mov     rsi, [rsp+28h+arg_10]
0x140023ab7  add     rsp, 20h
0x140023abb  pop     rdi
0x140023abc  retn
```
