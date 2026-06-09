# common_lseek_nolock<__int64>(int,__int64,int)

- ea: `0x4145f3`
- end: `0x41466f`
- name: `??$common_lseek_nolock@_J@@YA_JH_JH@Z`
- size: `124`
- prototype: `DWORD __cdecl(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x41466f`

## callees

- `0x40ff73`
- `0x40ffa9`
- `0x411199`
- `0x4145f3`

## import_xrefs

- `KERNEL32!GetLastError` at `0x414636`
- `KERNEL32!GetLastError` at `0x414636`
- `KERNEL32!SetFilePointerEx` at `0x41462c`
- `KERNEL32!SetFilePointerEx` at `0x41462c`

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
  *(_BYTE *)(dword_4181B0[FileHandle >> 6] + 56 * (FileHandle & 0x3F) + 40) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x4145f3  mov     edi, edi
0x4145f5  push    ebp
0x4145f6  mov     ebp, esp
0x4145f8  push    ecx
0x4145f9  push    ecx
0x4145fa  push    esi
0x4145fb  mov     esi, [ebp+FileHandle]
0x4145fe  push    edi
0x4145ff  push    esi; FileHandle
0x414600  call    __get_osfhandle
0x414605  or      edi, 0FFFFFFFFh
0x414608  pop     ecx
0x414609  cmp     eax, edi
0x41460b  jnz     short loc_41461E
0x41460d  call    __errno
0x414612  mov     dword ptr [eax], 9
0x414618  mov     eax, edi
0x41461a  mov     edx, edi
0x41461c  jmp     short loc_41466B
0x41461e  push    [ebp+dwMoveMethod]; dwMoveMethod
0x414621  lea     ecx, [ebp+NewFilePointer]
0x414624  push    ecx; lpNewFilePointer
0x414625  push    dword ptr [ebp+liDistanceToMove+4]
0x414628  push    dword ptr [ebp+liDistanceToMove]; liDistanceToMove
0x41462b  push    eax; hFile
0x41462c  call    ds:SetFilePointerEx
0x414632  test    eax, eax
0x414634  jnz     short loc_414645
0x414636  call    ds:GetLastError
0x41463c  push    eax
0x41463d  call    ___acrt_errno_map_os_error
0x414642  pop     ecx
0x414643  jmp     short loc_414618
0x414645  mov     eax, dword ptr [ebp+NewFilePointer]
0x414648  mov     edx, dword ptr [ebp+NewFilePointer+4]
0x41464b  and     eax, edx
0x41464d  cmp     eax, edi
0x41464f  jz      short loc_414618
0x414651  mov     eax, dword ptr [ebp+NewFilePointer]
0x414654  mov     ecx, esi
0x414656  and     esi, 3Fh
0x414659  sar     ecx, 6
0x41465c  imul    esi, 38h ; '8'
0x41465f  mov     ecx, dword_4181B0[ecx*4]
0x414666  and     byte ptr [ecx+esi+28h], 0FDh
0x41466b  pop     edi
0x41466c  pop     esi
0x41466d  leave
0x41466e  retn
```
