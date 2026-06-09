# PupOutputMessage(_DEBUG_PRINTS *,STRA *)

- ea: `0x180007020`
- end: `0x1800070ae`
- name: `?PupOutputMessage@@YAXPEAU_DEBUG_PRINTS@@PEAVSTRA@@@Z`
- size: `142`
- prototype: `void __fastcall(struct _DEBUG_PRINTS *, struct STRA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007234`

## callees

- `0x180007020`
- `0x1800081a0`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x18000709d`
- `KERNEL32!OutputDebugStringA` at `0x18000709d`
- `KERNEL32!WriteFile` at `0x180007068`
- `KERNEL32!WriteFile` at `0x180007068`

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
0x180007020  mov     rax, rsp
0x180007023  mov     [rax+10h], rbx
0x180007027  push    rdi
0x180007028  sub     rsp, 30h
0x18000702c  mov     rdi, rdx
0x18000702f  mov     rbx, rcx
0x180007032  test    rcx, rcx
0x180007035  jz      short loc_180007099
0x180007037  test    byte ptr [rcx+288h], 2
0x18000703e  jz      short loc_18000706E
0x180007040  mov     rcx, [rcx+270h]; hFile
0x180007047  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000704b  jz      short loc_18000706E
0x18000704d  mov     r8d, [rdx+30h]; nNumberOfBytesToWrite
0x180007051  lea     r9, [rax+8]; lpNumberOfBytesWritten
0x180007055  mov     rdx, [rdx+20h]; lpBuffer
0x180007059  mov     dword ptr [rax+8], 0
0x180007060  mov     qword ptr [rax-18h], 0
0x180007068  call    cs:__imp_WriteFile
0x18000706e  test    byte ptr [rbx+288h], 20h
0x180007075  jz      short loc_180007090
0x180007077  mov     rcx, [rbx+290h]; this
0x18000707e  test    rcx, rcx
0x180007081  jz      short loc_180007090
0x180007083  mov     r8d, [rdi+30h]; unsigned int
0x180007087  mov     rdx, [rdi+20h]; char *
0x18000708b  call    ?Append@CMemoryLog@@QEAAKPEBDK@Z; CMemoryLog::Append(char const *,ulong)
0x180007090  test    byte ptr [rbx+288h], 1
0x180007097  jz      short loc_1800070A3
0x180007099  mov     rcx, [rdi+20h]; lpOutputString
0x18000709d  call    cs:__imp_OutputDebugStringA
0x1800070a3  mov     rbx, [rsp+38h+arg_8]
0x1800070a8  add     rsp, 30h
0x1800070ac  pop     rdi
0x1800070ad  retn
```
