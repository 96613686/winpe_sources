# CreateCombinedHashTable

- ea: `0x18007c054`
- end: `0x18007c0d2`
- name: `CreateCombinedHashTable`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007bf24`
- `0x18007cea8`

## callees

- `0x180012b54`
- `0x180018b74`
- `0x18007c054`

## import_xrefs

- `ntdll!RtlCreateHashTable` at `0x18007c084`
- `ntdll!RtlCreateHashTable` at `0x18007c084`

## string_xrefs

- `0x18007c094`: `RtlCreateHashTable`
- `0x18007c0a8`: `CreateCombinedHashTable`

## pseudocode

```c
__int64 __fastcall CreateCombinedHashTable(_DWORD *a1, _QWORD *a2)
{
  _QWORD *v2; // rsi
  __int64 v3; // rbx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx

  v2 = a1 + 2;
  v3 = 0;
  if ( *a1 )
  {
    ++*a1;
    *a2 = *v2;
  }
  else if ( (unsigned __int8)RtlCreateHashTable(a1 + 2, 0, 0) )
  {
    v8 = *v2;
    *a1 = 1;
    *a2 = v8;
  }
  else
  {
    v7 = WfpReportSysErrorAsNtStatus(v6, "RtlCreateHashTable", 3221225473LL);
    v3 = v7;
    if ( v7 )
      WfpReportError(v7, "CreateCombinedHashTable");
  }
  return v3;
}

```

## disassembly

```asm
0x18007c054  push    rbx
0x18007c056  push    rsi
0x18007c057  push    rdi
0x18007c058  push    r14
0x18007c05a  sub     rsp, 28h
0x18007c05e  mov     eax, [rcx]
0x18007c060  lea     rsi, [rcx+8]
0x18007c064  xor     ebx, ebx
0x18007c066  mov     r14, rdx
0x18007c069  mov     rdi, rcx
0x18007c06c  test    eax, eax
0x18007c06e  jz      short loc_18007C07C
0x18007c070  inc     eax
0x18007c072  mov     [rcx], eax
0x18007c074  mov     rax, [rsi]
0x18007c077  mov     [rdx], rax
0x18007c07a  jmp     short loc_18007C0C5
0x18007c07c  xor     r8d, r8d
0x18007c07f  xor     edx, edx
0x18007c081  mov     rcx, rsi
0x18007c084  call    cs:__imp_RtlCreateHashTable
0x18007c08a  test    al, al
0x18007c08c  jnz     short loc_18007C0B9
0x18007c08e  mov     r8d, 0C0000001h
0x18007c094  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x18007c09b  call    WfpReportSysErrorAsNtStatus
0x18007c0a0  mov     rbx, rax
0x18007c0a3  test    rax, rax
0x18007c0a6  jz      short loc_18007C0C5
0x18007c0a8  lea     rdx, aCreatecombined; "CreateCombinedHashTable"
0x18007c0af  mov     rcx, rax
0x18007c0b2  call    WfpReportError
0x18007c0b7  jmp     short loc_18007C0C5
0x18007c0b9  mov     rcx, [rsi]
0x18007c0bc  mov     dword ptr [rdi], 1
0x18007c0c2  mov     [r14], rcx
0x18007c0c5  mov     rax, rbx
0x18007c0c8  add     rsp, 28h
0x18007c0cc  pop     r14
0x18007c0ce  pop     rdi
0x18007c0cf  pop     rsi
0x18007c0d0  pop     rbx
0x18007c0d1  retn
```
