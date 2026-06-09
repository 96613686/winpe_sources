# USBDInternal_BuildServicePath

- ea: `0x14000f470`
- end: `0x14000f5ba`
- name: `USBDInternal_BuildServicePath`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140013230`

## callees

- `0x14000f470`
- `0x14000f5c0`
- `0x140013a40`
- `0x140013d40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f595`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f595`
- `ntoskrnl!RtlCompareMemory` at `0x14000f4cb`
- `ntoskrnl!RtlCompareMemory` at `0x14000f4cb`
- `ntoskrnl!DbgPrintEx` at `0x14000f4a7`
- `ntoskrnl!DbgPrintEx` at `0x14000f52e`
- `ntoskrnl!DbgPrintEx` at `0x14000f581`
- `ntoskrnl!DbgPrintEx` at `0x14000f4a7`
- `ntoskrnl!DbgPrintEx` at `0x14000f52e`
- `ntoskrnl!DbgPrintEx` at `0x14000f581`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f4fa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f4fa`

## string_xrefs

- `0x14000f522`: `Couldnt allocate servicePath of size %d\n`

## pseudocode

```c
__int64 __fastcall USBDInternal_BuildServicePath(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rbx
  void *v3; // rdi
  unsigned int v5; // ebx
  __int64 v6; // r15
  unsigned int v7; // ebp
  PVOID PoolWithTag; // rax
  NTSTRSAFE_PCWSTR v9; // r8
  NTSTATUS v10; // eax

  v2 = *(_QWORD *)(a1 + 8);
  v3 = 0;
  if ( *(_WORD *)(v2 + 56) > 0x10u && RtlCompareMemory(*(const void **)(v2 + 64), L"\\Driver\\", 0x10u) == 16 )
  {
    v6 = *(_QWORD *)(v2 + 64);
    v7 = *(unsigned __int16 *)(v2 + 56) - 16;
    PoolWithTag = ExAllocatePoolWithTag(PoolType, v7 + 24, 0x53414D55u);
    v3 = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v7 + 24);
      memmove(v3, (const void *)(v6 + 16), v7);
      v10 = RtlStringCbCatW((NTSTRSAFE_PWSTR)v3, v7 + 24, v9);
      v5 = v10;
      if ( v10 >= 0 )
      {
        v5 = 0;
      }
      else
      {
        if ( g_EnableDbgPrints )
          DbgPrintEx(0x4Du, 0, "RtlStringCchCatW failed with status 0x%x", v10);
        ExFreePoolWithTag(v3, 0x53414D55u);
        v3 = 0;
      }
    }
    else
    {
      v5 = -1073741670;
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "Couldnt allocate servicePath of size %d\n", v7 + 24);
    }
  }
  else
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "Unexpected Driver name, Drvobj 0x%p\n", (const void *)v2);
    v5 = -1073741595;
  }
  *a2 = v3;
  return v5;
}

```

## disassembly

```asm
0x14000f470  push    rbx
0x14000f472  push    rbp
0x14000f473  push    rsi
0x14000f474  push    rdi
0x14000f475  push    r14
0x14000f477  push    r15
0x14000f479  sub     rsp, 28h
0x14000f47d  mov     rbx, [rcx+8]
0x14000f481  xor     edi, edi
0x14000f483  mov     r14, rdx
0x14000f486  lea     esi, [rdi+10h]
0x14000f489  cmp     [rbx+38h], si
0x14000f48d  ja      short loc_14000F4BD
0x14000f48f  cmp     cs:g_EnableDbgPrints, dil
0x14000f496  jz      short loc_14000F4B3
0x14000f498  xor     edx, edx; Level
0x14000f49a  lea     r8, aUnexpectedDriv; "Unexpected Driver name, Drvobj 0x%p\n"
0x14000f4a1  mov     r9, rbx
0x14000f4a4  lea     ecx, [rdx+4Dh]; ComponentId
0x14000f4a7  call    cs:__imp_DbgPrintEx
0x14000f4ae  nop     dword ptr [rax+rax+00h]
0x14000f4b3  mov     ebx, 0C00000E5h
0x14000f4b8  jmp     loc_14000F5A7
0x14000f4bd  mov     rcx, [rbx+40h]; Source1
0x14000f4c1  lea     rdx, aDriver; "\\Driver\\"
0x14000f4c8  mov     r8, rsi; Length
0x14000f4cb  call    cs:__imp_RtlCompareMemory
0x14000f4d2  nop     dword ptr [rax+rax+00h]
0x14000f4d7  cmp     rax, rsi
0x14000f4da  jnz     short loc_14000F48F
0x14000f4dc  movzx   ebp, word ptr [rbx+38h]
0x14000f4e0  mov     r8d, 53414D55h; Tag
0x14000f4e6  mov     r15, [rbx+40h]
0x14000f4ea  add     ebp, 0FFFFFFF0h
0x14000f4ed  mov     ecx, cs:PoolType; PoolType
0x14000f4f3  lea     esi, [rbp+18h]
0x14000f4f6  mov     edx, esi; NumberOfBytes
0x14000f4f8  mov     ebx, esi
0x14000f4fa  call    cs:__imp_ExAllocatePoolWithTag
0x14000f501  nop     dword ptr [rax+rax+00h]
0x14000f506  mov     rdi, rax
0x14000f509  test    rax, rax
0x14000f50c  jnz     short loc_14000F53C
0x14000f50e  cmp     cs:g_EnableDbgPrints, al
0x14000f514  mov     ebx, 0C000009Ah
0x14000f519  jz      loc_14000F5A7
0x14000f51f  mov     r9d, esi
0x14000f522  lea     r8, aCouldntAllocat; "Couldnt allocate servicePath of size %d"...
0x14000f529  xor     edx, edx; Level
0x14000f52b  lea     ecx, [rax+4Dh]; ComponentId
0x14000f52e  call    cs:__imp_DbgPrintEx
0x14000f535  nop     dword ptr [rax+rax+00h]
0x14000f53a  jmp     short loc_14000F5A7
0x14000f53c  mov     r8, rbx; Size
0x14000f53f  xor     edx, edx; Val
0x14000f541  mov     rcx, rdi; void *
0x14000f544  call    memset
0x14000f549  mov     r8d, ebp; Size
0x14000f54c  lea     rdx, [r15+10h]; Src
0x14000f550  mov     rcx, rdi; void *
0x14000f553  call    memmove
0x14000f558  mov     rdx, rbx; cbDest
0x14000f55b  mov     rcx, rdi; pszDest
0x14000f55e  call    RtlStringCbCatW
0x14000f563  mov     ebx, eax
0x14000f565  test    eax, eax
0x14000f567  jns     short loc_14000F5A5
0x14000f569  cmp     cs:g_EnableDbgPrints, 0
0x14000f570  jz      short loc_14000F58D
0x14000f572  xor     edx, edx; Level
0x14000f574  lea     r8, aRtlstringcchca; "RtlStringCchCatW failed with status 0x%"...
0x14000f57b  mov     r9d, eax
0x14000f57e  lea     ecx, [rdx+4Dh]; ComponentId
0x14000f581  call    cs:__imp_DbgPrintEx
0x14000f588  nop     dword ptr [rax+rax+00h]
0x14000f58d  mov     edx, 53414D55h; Tag
0x14000f592  mov     rcx, rdi; P
0x14000f595  call    cs:__imp_ExFreePoolWithTag
0x14000f59c  nop     dword ptr [rax+rax+00h]
0x14000f5a1  xor     edi, edi
0x14000f5a3  jmp     short loc_14000F5A7
0x14000f5a5  xor     ebx, ebx
0x14000f5a7  mov     [r14], rdi
0x14000f5aa  mov     eax, ebx
0x14000f5ac  add     rsp, 28h
0x14000f5b0  pop     r15
0x14000f5b2  pop     r14
0x14000f5b4  pop     rdi
0x14000f5b5  pop     rsi
0x14000f5b6  pop     rbp
0x14000f5b7  pop     rbx
0x14000f5b8  retn
```
