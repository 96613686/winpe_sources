# common_lseek_nolock<__int64>(int,__int64,int)

- ea: `0x41b1c1`
- end: `0x41b23d`
- name: `??$common_lseek_nolock@_J@@YA_JH_JH@Z`
- size: `124`
- prototype: `DWORD __cdecl(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x41b23d`

## callees

- `0x41040d`
- `0x410443`
- `0x415f4f`
- `0x41b1c1`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x41b1fa`
- `KERNEL32!SetFilePointerEx` at `0x41b1fa`
- `KERNEL32!GetLastError` at `0x41b204`
- `KERNEL32!GetLastError` at `0x41b204`

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
  *(_BYTE *)(dword_43E588[FileHandle >> 6] + 56 * (FileHandle & 0x3F) + 40) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x41b1c1  mov     edi, edi
0x41b1c3  push    ebp
0x41b1c4  mov     ebp, esp
0x41b1c6  push    ecx
0x41b1c7  push    ecx
0x41b1c8  push    esi
0x41b1c9  mov     esi, [ebp+FileHandle]
0x41b1cc  push    edi
0x41b1cd  push    esi; FileHandle
0x41b1ce  call    __get_osfhandle
0x41b1d3  or      edi, 0FFFFFFFFh
0x41b1d6  pop     ecx
0x41b1d7  cmp     eax, edi
0x41b1d9  jnz     short loc_41B1EC
0x41b1db  call    __errno
0x41b1e0  mov     dword ptr [eax], 9
0x41b1e6  mov     eax, edi
0x41b1e8  mov     edx, edi
0x41b1ea  jmp     short loc_41B239
0x41b1ec  push    [ebp+dwMoveMethod]; dwMoveMethod
0x41b1ef  lea     ecx, [ebp+NewFilePointer]
0x41b1f2  push    ecx; lpNewFilePointer
0x41b1f3  push    dword ptr [ebp+liDistanceToMove+4]
0x41b1f6  push    dword ptr [ebp+liDistanceToMove]; liDistanceToMove
0x41b1f9  push    eax; hFile
0x41b1fa  call    ds:SetFilePointerEx
0x41b200  test    eax, eax
0x41b202  jnz     short loc_41B213
0x41b204  call    ds:GetLastError
0x41b20a  push    eax
0x41b20b  call    ___acrt_errno_map_os_error
0x41b210  pop     ecx
0x41b211  jmp     short loc_41B1E6
0x41b213  mov     eax, dword ptr [ebp+NewFilePointer]
0x41b216  mov     edx, dword ptr [ebp+NewFilePointer+4]
0x41b219  and     eax, edx
0x41b21b  cmp     eax, edi
0x41b21d  jz      short loc_41B1E6
0x41b21f  mov     eax, dword ptr [ebp+NewFilePointer]
0x41b222  mov     ecx, esi
0x41b224  and     esi, 3Fh
0x41b227  sar     ecx, 6
0x41b22a  imul    esi, 38h ; '8'
0x41b22d  mov     ecx, dword_43E588[ecx*4]
0x41b234  and     byte ptr [ecx+esi+28h], 0FDh
0x41b239  pop     edi
0x41b23a  pop     esi
0x41b23b  leave
0x41b23c  retn
```
