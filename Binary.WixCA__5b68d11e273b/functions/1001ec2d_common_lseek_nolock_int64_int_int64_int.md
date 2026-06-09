# common_lseek_nolock<__int64>(int,__int64,int)

- ea: `0x1001ec2d`
- end: `0x1001ecab`
- name: `??$common_lseek_nolock@_J@@YA_JH_JH@Z`
- size: `126`
- prototype: `int __cdecl(int FileHandle, LARGE_INTEGER liDistanceToMove, DWORD dwMoveMethod)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1001ecab`

## callees

- `0x10015d43`
- `0x10015d79`
- `0x1001d488`
- `0x1001ec2d`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001ec70`
- `KERNEL32!GetLastError` at `0x1001ec70`
- `KERNEL32!SetFilePointerEx` at `0x1001ec66`
- `KERNEL32!SetFilePointerEx` at `0x1001ec66`

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
  *(_BYTE *)(dword_10034F30[FileHandle >> 6] + 56 * (FileHandle & 0x3F) + 40) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x1001ec2d  mov     edi, edi
0x1001ec2f  push    ebp
0x1001ec30  mov     ebp, esp
0x1001ec32  push    ecx
0x1001ec33  push    ecx
0x1001ec34  push    esi
0x1001ec35  mov     esi, [ebp+FileHandle]
0x1001ec38  push    edi
0x1001ec39  push    esi; FileHandle
0x1001ec3a  call    __get_osfhandle
0x1001ec3f  or      edi, 0FFFFFFFFh
0x1001ec42  pop     ecx
0x1001ec43  cmp     eax, edi
0x1001ec45  jnz     short loc_1001EC58
0x1001ec47  call    __errno
0x1001ec4c  mov     dword ptr [eax], 9
0x1001ec52  mov     eax, edi
0x1001ec54  mov     edx, edi
0x1001ec56  jmp     short loc_1001ECA5
0x1001ec58  push    [ebp+dwMoveMethod]; dwMoveMethod
0x1001ec5b  lea     ecx, [ebp+NewFilePointer]
0x1001ec5e  push    ecx; lpNewFilePointer
0x1001ec5f  push    dword ptr [ebp+liDistanceToMove+4]
0x1001ec62  push    dword ptr [ebp+liDistanceToMove]; liDistanceToMove
0x1001ec65  push    eax; hFile
0x1001ec66  call    ds:SetFilePointerEx
0x1001ec6c  test    eax, eax
0x1001ec6e  jnz     short loc_1001EC7F
0x1001ec70  call    ds:GetLastError
0x1001ec76  push    eax
0x1001ec77  call    ___acrt_errno_map_os_error
0x1001ec7c  pop     ecx
0x1001ec7d  jmp     short loc_1001EC52
0x1001ec7f  mov     eax, dword ptr [ebp+NewFilePointer]
0x1001ec82  mov     edx, dword ptr [ebp+NewFilePointer+4]
0x1001ec85  and     eax, edx
0x1001ec87  cmp     eax, edi
0x1001ec89  jz      short loc_1001EC52
0x1001ec8b  mov     eax, dword ptr [ebp+NewFilePointer]
0x1001ec8e  mov     ecx, esi
0x1001ec90  and     esi, 3Fh
0x1001ec93  sar     ecx, 6
0x1001ec96  imul    esi, 38h ; '8'
0x1001ec99  mov     ecx, dword_10034F30[ecx*4]
0x1001eca0  and     byte ptr [ecx+esi+28h], 0FDh
0x1001eca5  pop     edi
0x1001eca6  pop     esi
0x1001eca7  mov     esp, ebp
0x1001eca9  pop     ebp
0x1001ecaa  retn
```
