# CreateCombinedHashTable

- ea: `0x18007ed54`
- end: `0x18007edd9`
- name: `CreateCombinedHashTable`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007ec24`
- `0x18007fc5c`

## callees

- `0x1800135ac`
- `0x1800197d0`
- `0x18007ed54`

## import_xrefs

- `ntdll!RtlCreateHashTable` at `0x18007ed84`
- `ntdll!RtlCreateHashTable` at `0x18007ed84`

## string_xrefs

- `0x18007ed9a`: `RtlCreateHashTable`
- `0x18007edae`: `CreateCombinedHashTable`

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
0x18007ed54  push    rbx
0x18007ed56  push    rsi
0x18007ed57  push    rdi
0x18007ed58  push    r14
0x18007ed5a  sub     rsp, 28h
0x18007ed5e  mov     eax, [rcx]
0x18007ed60  lea     rsi, [rcx+8]
0x18007ed64  xor     ebx, ebx
0x18007ed66  mov     r14, rdx
0x18007ed69  mov     rdi, rcx
0x18007ed6c  test    eax, eax
0x18007ed6e  jz      short loc_18007ED7C
0x18007ed70  inc     eax
0x18007ed72  mov     [rcx], eax
0x18007ed74  mov     rax, [rsi]
0x18007ed77  mov     [rdx], rax
0x18007ed7a  jmp     short loc_18007EDCB
0x18007ed7c  xor     r8d, r8d
0x18007ed7f  xor     edx, edx
0x18007ed81  mov     rcx, rsi
0x18007ed84  call    cs:__imp_RtlCreateHashTable
0x18007ed8b  nop     dword ptr [rax+rax+00h]
0x18007ed90  test    al, al
0x18007ed92  jnz     short loc_18007EDBF
0x18007ed94  mov     r8d, 0C0000001h
0x18007ed9a  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x18007eda1  call    WfpReportSysErrorAsNtStatus
0x18007eda6  mov     rbx, rax
0x18007eda9  test    rax, rax
0x18007edac  jz      short loc_18007EDCB
0x18007edae  lea     rdx, aCreatecombined; "CreateCombinedHashTable"
0x18007edb5  mov     rcx, rax
0x18007edb8  call    WfpReportError
0x18007edbd  jmp     short loc_18007EDCB
0x18007edbf  mov     rcx, [rsi]
0x18007edc2  mov     dword ptr [rdi], 1
0x18007edc8  mov     [r14], rcx
0x18007edcb  mov     rax, rbx
0x18007edce  add     rsp, 28h
0x18007edd2  pop     r14
0x18007edd4  pop     rdi
0x18007edd5  pop     rsi
0x18007edd6  pop     rbx
0x18007edd7  retn
```
