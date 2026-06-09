# Xc_Process_user_free(void *)

- ea: `0x180013458`
- end: `0x180013491`
- name: `?Xc_Process_user_free@@YAXPEAX@Z`
- size: `57`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c4a0`
- `0x18000cf80`
- `0x18000dea0`
- `0x1800123d4`
- `0x180012a4c`
- `0x180012e8c`

## callees

- `0x180013458`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001347d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001347d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013485`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013485`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013473`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013473`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013465`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013465`

## pseudocode

```c
void __fastcall Xc_Process_user_free(void *lpMem)
{
  HANDLE ProcessHeap; // rax
  DWORD LastError; // eax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    if ( !HeapFree(ProcessHeap, 0, lpMem) )
    {
      LastError = GetLastError();
      SetLastError(LastError);
    }
  }
}

```

## disassembly

```asm
0x180013458  test    rcx, rcx
0x18001345b  jz      short locret_180013490
0x18001345d  push    rbx
0x18001345e  sub     rsp, 20h
0x180013462  mov     rbx, rcx
0x180013465  call    cs:__imp_GetProcessHeap
0x18001346b  mov     r8, rbx; lpMem
0x18001346e  xor     edx, edx; dwFlags
0x180013470  mov     rcx, rax; hHeap
0x180013473  call    cs:__imp_HeapFree
0x180013479  test    eax, eax
0x18001347b  jnz     short loc_18001348B
0x18001347d  call    cs:__imp_GetLastError
0x180013483  mov     ecx, eax; dwErrCode
0x180013485  call    cs:__imp_SetLastError
0x18001348b  add     rsp, 20h
0x18001348f  pop     rbx
0x180013490  retn
```
