# ConnectedStorage::File::Seek(__int64,tagSTREAM_SEEK)

- ea: `0x18004fcec`
- end: `0x18004fd7b`
- name: `?Seek@File@ConnectedStorage@@QEAA_K_JW4tagSTREAM_SEEK@@@Z`
- size: `143`
- prototype: `union _LARGE_INTEGER __fastcall(ConnectedStorage::File *this, LARGE_INTEGER, enum tagSTREAM_SEEK)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800443d0`
- `0x180044c70`
- `0x180044cd0`
- `0x180069cd0`

## callees

- `0x18000aae4`
- `0x18004fcec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fd4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fd4f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004fd3c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004fd3c`

## pseudocode

```c
union _LARGE_INTEGER __fastcall ConnectedStorage::File::Seek(
        ConnectedStorage::File *this,
        LARGE_INTEGER a2,
        enum tagSTREAM_SEEK a3)
{
  const unsigned __int16 *v4; // r8
  DWORD v5; // r9d
  void *v6; // rcx
  signed int LastError; // eax
  const unsigned __int16 *v8; // r8
  union _LARGE_INTEGER NewFilePointer; // [rsp+48h] [rbp+20h] BYREF

  if ( a3 )
  {
    v4 = (const unsigned __int16 *)(unsigned int)(a3 - 1);
    if ( (_DWORD)v4 )
    {
      if ( (_DWORD)v4 != 1 )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x80070057LL, (int)L"File::Seek - invalid origin", v4);
      v5 = 2;
    }
    else
    {
      v5 = 1;
    }
  }
  else
  {
    v5 = 0;
  }
  v6 = *(void **)this;
  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(v6, a2, &NewFilePointer, v5) )
  {
    if ( *((_DWORD *)this + 2) == 1 )
      *((_DWORD *)this + 2) = 0;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)LastError, (int)L"File::Seek", v8);
  }
  return NewFilePointer;
}

```

## disassembly

```asm
0x18004fcec  push    rbx
0x18004fcee  sub     rsp, 20h
0x18004fcf2  mov     rbx, rcx
0x18004fcf5  test    r8d, r8d
0x18004fcf8  jz      short loc_18004FD28
0x18004fcfa  sub     r8d, 1; unsigned __int16 *
0x18004fcfe  jz      short loc_18004FD20
0x18004fd00  cmp     r8d, 1
0x18004fd04  jz      short loc_18004FD18
0x18004fd06  lea     rdx, aFileSeekInvali; "File::Seek - invalid origin"
0x18004fd0d  mov     ecx, 80070057h; this
0x18004fd12  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004fd18  mov     r9d, 2
0x18004fd1e  jmp     short loc_18004FD2B
0x18004fd20  mov     r9d, 1
0x18004fd26  jmp     short loc_18004FD2B
0x18004fd28  xor     r9d, r9d; dwMoveMethod
0x18004fd2b  mov     rcx, [rcx]; hFile
0x18004fd2e  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x18004fd33  mov     qword ptr [rsp+28h+NewFilePointer], 0
0x18004fd3c  call    cs:__imp_SetFilePointerEx
0x18004fd42  test    eax, eax
0x18004fd44  jnz     short loc_18004FD70
0x18004fd46  cmp     dword ptr [rbx+8], 1
0x18004fd4a  jnz     short loc_18004FD4F
0x18004fd4c  mov     [rbx+8], eax
0x18004fd4f  call    cs:__imp_GetLastError
0x18004fd55  test    eax, eax
0x18004fd57  jle     short loc_18004FD61
0x18004fd59  movzx   eax, ax
0x18004fd5c  or      eax, 80070000h
0x18004fd61  lea     rdx, aFileSeek; "File::Seek"
0x18004fd68  mov     ecx, eax; this
0x18004fd6a  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004fd70  mov     rax, qword ptr [rsp+28h+NewFilePointer]
0x18004fd75  add     rsp, 20h
0x18004fd79  pop     rbx
0x18004fd7a  retn
```
