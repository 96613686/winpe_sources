# CFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x14004d8b0`
- end: `0x14004d949`
- name: `?Seek@CFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x14004d8b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d910`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14004d903`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14004d903`

## pseudocode

```c
__int64 __fastcall CFileStream::Seek(CFileStream *this, union _LARGE_INTEGER a2, int a3, union _ULARGE_INTEGER *a4)
{
  int v5; // r8d
  DWORD v7; // r9d
  void *v8; // rcx
  signed int v9; // ebx
  DWORD v10; // esi
  signed int LastError; // eax
  LONG DistanceToMoveHigh; // [rsp+40h] [rbp+18h] BYREF

  if ( a3 )
  {
    v5 = a3 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
        return 2147942487LL;
      v7 = 2;
    }
    else
    {
      v7 = 1;
    }
  }
  else
  {
    v7 = 0;
  }
  v8 = (void *)*((_QWORD *)this + 3);
  v9 = 0;
  DistanceToMoveHigh = a2.HighPart;
  v10 = SetFilePointer(v8, a2.LowPart, &DistanceToMoveHigh, v7);
  if ( v10 != -1 )
    goto LABEL_12;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 >= 0 )
  {
LABEL_12:
    if ( a4 )
    {
      a4->HighPart = DistanceToMoveHigh;
      a4->LowPart = v10;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14004d8b0  mov     [rsp+arg_0], rbx
0x14004d8b5  mov     [rsp+arg_8], rsi
0x14004d8ba  push    rdi
0x14004d8bb  sub     rsp, 20h
0x14004d8bf  mov     rdi, r9
0x14004d8c2  test    r8d, r8d
0x14004d8c5  jz      short loc_14004D8EA
0x14004d8c7  sub     r8d, 1
0x14004d8cb  jz      short loc_14004D8E2
0x14004d8cd  cmp     r8d, 1
0x14004d8d1  jz      short loc_14004D8DA
0x14004d8d3  mov     eax, 80070057h
0x14004d8d8  jmp     short loc_14004D939
0x14004d8da  mov     r9d, 2
0x14004d8e0  jmp     short loc_14004D8ED
0x14004d8e2  mov     r9d, 1
0x14004d8e8  jmp     short loc_14004D8ED
0x14004d8ea  xor     r9d, r9d; dwMoveMethod
0x14004d8ed  mov     rcx, [rcx+18h]; hFile
0x14004d8f1  lea     r8, [rsp+28h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x14004d8f6  mov     rax, rdx
0x14004d8f9  xor     ebx, ebx
0x14004d8fb  shr     rax, 20h
0x14004d8ff  mov     [rsp+28h+DistanceToMoveHigh], eax
0x14004d903  call    cs:__imp_SetFilePointer
0x14004d909  mov     esi, eax
0x14004d90b  cmp     eax, 0FFFFFFFFh
0x14004d90e  jnz     short loc_14004D929
0x14004d910  call    cs:__imp_GetLastError
0x14004d916  mov     ebx, eax
0x14004d918  test    eax, eax
0x14004d91a  jle     short loc_14004D925
0x14004d91c  movzx   ebx, ax
0x14004d91f  or      ebx, 80070000h
0x14004d925  test    ebx, ebx
0x14004d927  js      short loc_14004D937
0x14004d929  test    rdi, rdi
0x14004d92c  jz      short loc_14004D937
0x14004d92e  mov     ecx, [rsp+28h+DistanceToMoveHigh]
0x14004d932  mov     [rdi+4], ecx
0x14004d935  mov     [rdi], esi
0x14004d937  mov     eax, ebx
0x14004d939  mov     rbx, [rsp+28h+arg_0]
0x14004d93e  mov     rsi, [rsp+28h+arg_8]
0x14004d943  add     rsp, 20h
0x14004d947  pop     rdi
0x14004d948  retn
```
