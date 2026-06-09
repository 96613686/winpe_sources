# UtilReadExceptionInformationFromExceptionPointer(void *,void *,_EXCEPTION_RECORD *,_CONTEXT *)

- ea: `0x1400185c4`
- end: `0x1400186b5`
- name: `?UtilReadExceptionInformationFromExceptionPointer@@YAJPEAX0PEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(HANDLE hProcess, void *, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001533c`

## callees

- `0x1400185c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018609`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400185ff`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140018647`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14001867e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400185ff`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140018647`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14001867e`

## pseudocode

```c
signed int __fastcall UtilReadExceptionInformationFromExceptionPointer(
        HANDLE hProcess,
        void *a2,
        struct _EXCEPTION_RECORD *a3,
        struct _CONTEXT *a4)
{
  signed int result; // eax
  SIZE_T NumberOfBytesRead; // [rsp+30h] [rbp-28h] BYREF
  LPCVOID lpBaseAddress[4]; // [rsp+38h] [rbp-20h] BYREF

  NumberOfBytesRead = 0;
  *(_OWORD *)lpBaseAddress = 0;
  if ( !ReadProcessMemory(hProcess, a2, lpBaseAddress, 0x10u, &NumberOfBytesRead) )
    goto LABEL_2;
  if ( NumberOfBytesRead != 16 )
    return -2147024597;
  if ( ReadProcessMemory(hProcess, lpBaseAddress[0], a3, 0x98u, &NumberOfBytesRead) )
  {
    if ( NumberOfBytesRead == 152 )
    {
      if ( !a4 )
        return 0;
      if ( ReadProcessMemory(hProcess, lpBaseAddress[1], a4, 0x4D0u, &NumberOfBytesRead) )
        return NumberOfBytesRead != 1232 ? 0x8007012B : 0;
      goto LABEL_2;
    }
    return -2147024597;
  }
LABEL_2:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400185c4  mov     r11, rsp
0x1400185c7  mov     [r11+8], rbx
0x1400185cb  mov     [r11+10h], rsi
0x1400185cf  push    rdi
0x1400185d0  sub     rsp, 50h
0x1400185d4  mov     rbx, r9
0x1400185d7  mov     qword ptr [r11-28h], 0
0x1400185df  mov     rsi, r8
0x1400185e2  lea     rax, [r11-28h]
0x1400185e6  xorps   xmm0, xmm0
0x1400185e9  mov     [r11-38h], rax
0x1400185ed  mov     r9d, 10h; nSize
0x1400185f3  lea     r8, [r11-20h]; lpBuffer
0x1400185f7  movups  xmmword ptr [rsp+58h+lpBaseAddress], xmm0
0x1400185fc  mov     rdi, rcx
0x1400185ff  call    cs:__imp_ReadProcessMemory
0x140018605  test    eax, eax
0x140018607  jnz     short loc_140018624
0x140018609  call    cs:__imp_GetLastError
0x14001860f  test    eax, eax
0x140018611  jle     loc_1400186A5
0x140018617  movzx   eax, ax
0x14001861a  or      eax, 80070000h
0x14001861f  jmp     loc_1400186A5
0x140018624  cmp     [rsp+58h+NumberOfBytesRead], 10h
0x14001862a  jnz     short loc_1400186A0
0x14001862c  mov     rdx, [rsp+58h+lpBaseAddress]; lpBaseAddress
0x140018631  lea     rax, [rsp+58h+NumberOfBytesRead]
0x140018636  mov     r9d, 98h; nSize
0x14001863c  mov     [rsp+58h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140018641  mov     r8, rsi; lpBuffer
0x140018644  mov     rcx, rdi; hProcess
0x140018647  call    cs:__imp_ReadProcessMemory
0x14001864d  test    eax, eax
0x14001864f  jz      short loc_140018609
0x140018651  cmp     [rsp+58h+NumberOfBytesRead], 98h
0x14001865a  jnz     short loc_1400186A0
0x14001865c  test    rbx, rbx
0x14001865f  jz      short loc_14001869C
0x140018661  mov     rdx, [rsp+58h+lpBaseAddress+8]; lpBaseAddress
0x140018666  lea     rax, [rsp+58h+NumberOfBytesRead]
0x14001866b  mov     esi, 4D0h
0x140018670  mov     [rsp+58h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140018675  mov     r9d, esi; nSize
0x140018678  mov     r8, rbx; lpBuffer
0x14001867b  mov     rcx, rdi; hProcess
0x14001867e  call    cs:__imp_ReadProcessMemory
0x140018684  test    eax, eax
0x140018686  jz      short loc_140018609
0x140018688  mov     rax, [rsp+58h+NumberOfBytesRead]
0x14001868d  sub     rax, rsi
0x140018690  neg     rax
0x140018693  sbb     eax, eax
0x140018695  and     eax, 8007012Bh
0x14001869a  jmp     short loc_1400186A5
0x14001869c  xor     eax, eax
0x14001869e  jmp     short loc_1400186A5
0x1400186a0  mov     eax, 8007012Bh
0x1400186a5  mov     rbx, [rsp+58h+arg_0]
0x1400186aa  mov     rsi, [rsp+58h+arg_8]
0x1400186af  add     rsp, 50h
0x1400186b3  pop     rdi
0x1400186b4  retn
```
