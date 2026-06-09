# PupOutputMessage(_DEBUG_PRINTS *,STRA *)

- ea: `0x180034004`
- end: `0x180034092`
- name: `?PupOutputMessage@@YAXPEAU_DEBUG_PRINTS@@PEAVSTRA@@@Z`
- size: `142`
- prototype: `void __fastcall(struct _DEBUG_PRINTS *, struct STRA *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180034218`
- `0x1800342f4`

## callees

- `0x180034004`
- `0x180034918`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003404c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003404c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180034081`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180034081`

## pseudocode

```c
void __fastcall PupOutputMessage(struct _DEBUG_PRINTS *a1, struct STRA *a2)
{
  void *v4; // rcx
  DWORD v5; // r8d
  const void *v6; // rdx
  CMemoryLog *v7; // rcx
  DWORD v8; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 )
    goto LABEL_9;
  if ( (*((_BYTE *)a1 + 648) & 2) != 0 )
  {
    v4 = (void *)*((_QWORD *)a1 + 78);
    if ( v4 != (void *)-1LL )
    {
      v5 = *((_DWORD *)a2 + 12);
      v6 = (const void *)*((_QWORD *)a2 + 4);
      v8 = 0;
      WriteFile(v4, v6, v5, &v8, 0);
    }
  }
  if ( (*((_BYTE *)a1 + 648) & 0x20) != 0 )
  {
    v7 = (CMemoryLog *)*((_QWORD *)a1 + 82);
    if ( v7 )
      CMemoryLog::Append(v7, *((const char **)a2 + 4), *((_DWORD *)a2 + 12));
  }
  if ( (*((_BYTE *)a1 + 648) & 1) != 0 )
LABEL_9:
    OutputDebugStringA(*((LPCSTR *)a2 + 4));
}

```

## disassembly

```asm
0x180034004  mov     rax, rsp
0x180034007  mov     [rax+10h], rbx
0x18003400b  push    rdi
0x18003400c  sub     rsp, 30h
0x180034010  mov     rdi, rdx
0x180034013  mov     rbx, rcx
0x180034016  test    rcx, rcx
0x180034019  jz      short loc_18003407D
0x18003401b  test    byte ptr [rcx+288h], 2
0x180034022  jz      short loc_180034052
0x180034024  mov     rcx, [rcx+270h]; hFile
0x18003402b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003402f  jz      short loc_180034052
0x180034031  mov     r8d, [rdx+30h]; nNumberOfBytesToWrite
0x180034035  lea     r9, [rax+8]; lpNumberOfBytesWritten
0x180034039  mov     rdx, [rdx+20h]; lpBuffer
0x18003403d  mov     dword ptr [rax+8], 0
0x180034044  mov     qword ptr [rax-18h], 0
0x18003404c  call    cs:__imp_WriteFile
0x180034052  test    byte ptr [rbx+288h], 20h
0x180034059  jz      short loc_180034074
0x18003405b  mov     rcx, [rbx+290h]; this
0x180034062  test    rcx, rcx
0x180034065  jz      short loc_180034074
0x180034067  mov     r8d, [rdi+30h]; unsigned int
0x18003406b  mov     rdx, [rdi+20h]; char *
0x18003406f  call    ?Append@CMemoryLog@@QEAAKPEBDK@Z; CMemoryLog::Append(char const *,ulong)
0x180034074  test    byte ptr [rbx+288h], 1
0x18003407b  jz      short loc_180034087
0x18003407d  mov     rcx, [rdi+20h]; lpOutputString
0x180034081  call    cs:__imp_OutputDebugStringA
0x180034087  mov     rbx, [rsp+38h+arg_8]
0x18003408c  add     rsp, 30h
0x180034090  pop     rdi
0x180034091  retn
```
