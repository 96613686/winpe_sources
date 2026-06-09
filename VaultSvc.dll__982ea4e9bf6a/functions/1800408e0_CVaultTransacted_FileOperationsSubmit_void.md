# CVaultTransacted::FileOperationsSubmit(void)

- ea: `0x1800408e0`
- end: `0x180040925`
- name: `?FileOperationsSubmit@CVaultTransacted@@UEAAKXZ`
- size: `69`
- prototype: `DWORD __fastcall(HANDLE *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800408e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800408fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040907`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040907`
- `ktmw32!CommitTransaction` at `0x1800408ed`
- `ktmw32!CommitTransaction` at `0x1800408ed`

## pseudocode

```c
DWORD __fastcall CVaultTransacted::FileOperationsSubmit(HANDLE *this)
{
  DWORD result; // eax

  if ( !CommitTransaction(this[1]) || !CloseHandle(this[1]) )
    return GetLastError();
  *((_BYTE *)this + 16) = 1;
  result = 0;
  this[1] = 0;
  return result;
}

```

## disassembly

```asm
0x1800408e0  push    rbx
0x1800408e2  sub     rsp, 20h
0x1800408e6  mov     rbx, rcx
0x1800408e9  mov     rcx, [rcx+8]; TransactionHandle
0x1800408ed  call    cs:__imp_CommitTransaction
0x1800408f3  test    eax, eax
0x1800408f5  jnz     short loc_180040903
0x1800408f7  add     rsp, 20h
0x1800408fb  pop     rbx
0x1800408fc  jmp     cs:__imp_GetLastError
0x180040903  mov     rcx, [rbx+8]; hObject
0x180040907  call    cs:__imp_CloseHandle
0x18004090d  test    eax, eax
0x18004090f  jz      short loc_1800408F7
0x180040911  mov     byte ptr [rbx+10h], 1
0x180040915  xor     eax, eax
0x180040917  mov     qword ptr [rbx+8], 0
0x18004091f  add     rsp, 20h
0x180040923  pop     rbx
0x180040924  retn
```
