# FwspSetSize

- ea: `0x140011020`
- end: `0x1400110da`
- name: `FwspSetSize`
- size: `186`
- prototype: `signed int __fastcall(__int64, LARGE_INTEGER)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140011020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011099`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x14001108b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x14001108b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140011048`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x14001107d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400110c7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140011048`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x14001107d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400110c7`

## pseudocode

```c
signed int __fastcall FwspSetSize(__int64 a1, LARGE_INTEGER a2)
{
  signed int result; // eax
  signed int v5; // ebx
  signed int LastError; // eax
  union _LARGE_INTEGER NewFilePointer; // [rsp+30h] [rbp+8h] BYREF

  NewFilePointer.QuadPart = 0;
  if ( SetFilePointerEx(*(HANDLE *)(a1 + 8), 0, &NewFilePointer, 1u) && SetFilePointerEx(*(HANDLE *)(a1 + 8), a2, 0, 0) )
  {
    if ( SetEndOfFile(*(HANDLE *)(a1 + 8)) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
    }
    SetFilePointerEx(*(HANDLE *)(a1 + 8), NewFilePointer, 0, 0);
    return v5;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x140011020  mov     [rsp+arg_8], rbx
0x140011025  push    rdi
0x140011026  sub     rsp, 20h
0x14001102a  mov     rbx, rdx
0x14001102d  mov     qword ptr [rsp+28h+NewFilePointer], 0
0x140011036  xor     edx, edx; liDistanceToMove
0x140011038  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x14001103d  mov     rdi, rcx
0x140011040  mov     rcx, [rcx+8]; hFile
0x140011044  lea     r9d, [rdx+1]; dwMoveMethod
0x140011048  call    cs:__imp_SetFilePointerEx
0x14001104e  test    eax, eax
0x140011050  jnz     short loc_140011070
0x140011052  call    cs:__imp_GetLastError
0x140011058  test    eax, eax
0x14001105a  jle     short loc_140011064
0x14001105c  movzx   eax, ax
0x14001105f  or      eax, 80070000h
0x140011064  test    eax, eax
0x140011066  mov     ecx, 80004005h
0x14001106b  cmovns  eax, ecx
0x14001106e  jmp     short loc_1400110CF
0x140011070  mov     rcx, [rdi+8]; hFile
0x140011074  xor     r9d, r9d; dwMoveMethod
0x140011077  xor     r8d, r8d; lpNewFilePointer
0x14001107a  mov     rdx, rbx; liDistanceToMove
0x14001107d  call    cs:__imp_SetFilePointerEx
0x140011083  test    eax, eax
0x140011085  jz      short loc_140011052
0x140011087  mov     rcx, [rdi+8]; hFile
0x14001108b  call    cs:__imp_SetEndOfFile
0x140011091  test    eax, eax
0x140011093  jz      short loc_140011099
0x140011095  xor     ebx, ebx
0x140011097  jmp     short loc_1400110B8
0x140011099  call    cs:__imp_GetLastError
0x14001109f  mov     ebx, eax
0x1400110a1  test    eax, eax
0x1400110a3  jle     short loc_1400110AE
0x1400110a5  movzx   ebx, ax
0x1400110a8  or      ebx, 80070000h
0x1400110ae  test    ebx, ebx
0x1400110b0  mov     ecx, 80004005h
0x1400110b5  cmovns  ebx, ecx
0x1400110b8  mov     rdx, qword ptr [rsp+28h+NewFilePointer]; liDistanceToMove
0x1400110bd  xor     r9d, r9d; dwMoveMethod
0x1400110c0  mov     rcx, [rdi+8]; hFile
0x1400110c4  xor     r8d, r8d; lpNewFilePointer
0x1400110c7  call    cs:__imp_SetFilePointerEx
0x1400110cd  mov     eax, ebx
0x1400110cf  mov     rbx, [rsp+28h+arg_8]
0x1400110d4  add     rsp, 20h
0x1400110d8  pop     rdi
0x1400110d9  retn
```
