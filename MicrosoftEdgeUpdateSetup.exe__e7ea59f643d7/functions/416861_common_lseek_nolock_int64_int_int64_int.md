# common_lseek_nolock<__int64>(int,__int64,int)

- ea: `0x416861`
- end: `0x4168dd`
- name: `??$common_lseek_nolock@_J@@YA_JH_JH@Z`
- size: `124`
- prototype: `DWORD __cdecl(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x4168dd`

## callees

- `0x40ecad`
- `0x40ece3`
- `0x4104ce`
- `0x416861`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x41689a`
- `KERNEL32!SetFilePointerEx` at `0x41689a`
- `KERNEL32!GetLastError` at `0x4168a4`
- `KERNEL32!GetLastError` at `0x4168a4`

## pseudocode

```c
DWORD __cdecl common_lseek_nolock<__int64>(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)
{
  void *osfhandle; // eax
  DWORD result; // eax
  DWORD LastError; // eax
  LARGE_INTEGER NewFilePointer; // [esp+8h] [ebp-8h] BYREF

  osfhandle = (void *)_get_osfhandle(FileHandle);
  if ( osfhandle == (void *)-1 )
  {
    *_errno() = 9;
    return -1;
  }
  if ( !SetFilePointerEx(osfhandle, liDistanceToMove, &NewFilePointer, dwMoveMethod) )
  {
    LastError = GetLastError();
    __acrt_errno_map_os_error(LastError);
    return -1;
  }
  if ( (NewFilePointer.HighPart & NewFilePointer.LowPart) == -1 )
    return -1;
  result = NewFilePointer.LowPart;
  *(_BYTE *)(dword_427018[FileHandle >> 6] + 56 * (FileHandle & 0x3F) + 40) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x416861  mov     edi, edi
0x416863  push    ebp
0x416864  mov     ebp, esp
0x416866  push    ecx
0x416867  push    ecx
0x416868  push    esi
0x416869  mov     esi, [ebp+FileHandle]
0x41686c  push    edi
0x41686d  push    esi; FileHandle
0x41686e  call    __get_osfhandle
0x416873  or      edi, 0FFFFFFFFh
0x416876  pop     ecx
0x416877  cmp     eax, edi
0x416879  jnz     short loc_41688C
0x41687b  call    __errno
0x416880  mov     dword ptr [eax], 9
0x416886  mov     eax, edi
0x416888  mov     edx, edi
0x41688a  jmp     short loc_4168D9
0x41688c  push    [ebp+dwMoveMethod]; dwMoveMethod
0x41688f  lea     ecx, [ebp+NewFilePointer]
0x416892  push    ecx; lpNewFilePointer
0x416893  push    dword ptr [ebp+liDistanceToMove+4]
0x416896  push    dword ptr [ebp+liDistanceToMove]; liDistanceToMove
0x416899  push    eax; hFile
0x41689a  call    ds:SetFilePointerEx
0x4168a0  test    eax, eax
0x4168a2  jnz     short loc_4168B3
0x4168a4  call    ds:GetLastError
0x4168aa  push    eax
0x4168ab  call    ___acrt_errno_map_os_error
0x4168b0  pop     ecx
0x4168b1  jmp     short loc_416886
0x4168b3  mov     eax, dword ptr [ebp+NewFilePointer]
0x4168b6  mov     edx, dword ptr [ebp+NewFilePointer+4]
0x4168b9  and     eax, edx
0x4168bb  cmp     eax, edi
0x4168bd  jz      short loc_416886
0x4168bf  mov     eax, dword ptr [ebp+NewFilePointer]
0x4168c2  mov     ecx, esi
0x4168c4  and     esi, 3Fh
0x4168c7  sar     ecx, 6
0x4168ca  imul    esi, 38h ; '8'
0x4168cd  mov     ecx, dword_427018[ecx*4]
0x4168d4  and     byte ptr [ecx+esi+28h], 0FDh
0x4168d9  pop     edi
0x4168da  pop     esi
0x4168db  leave
0x4168dc  retn
```
