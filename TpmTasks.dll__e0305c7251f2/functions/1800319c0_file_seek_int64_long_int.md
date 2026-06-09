# file_seek(__int64,long,int)

- ea: `0x1800319c0`
- end: `0x1800319fe`
- name: `?file_seek@@YAJ_JJH@Z`
- size: `62`
- prototype: `int __cdecl(INT_PTR hf, int dist, int seektype)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x1800319c0`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800319cc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800319cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800319d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800319d9`

## string_xrefs

- `0x1800319e5`: `file_seek: SetFilePointer failed, GLE=0x%08X`

## pseudocode

```c
__int64 __fastcall file_seek(INT_PTR hf, LONG dist, DWORD seektype)
{
  DWORD v3; // ebx
  DWORD LastError; // eax

  v3 = SetFilePointer((HANDLE)hf, dist, 0, seektype);
  if ( v3 != -1 )
    return v3;
  LastError = GetLastError();
  if ( !LastError )
    return v3;
  SBServicingLogMessage((wchar_t *)L"file_seek: SetFilePointer failed, GLE=0x%08X", LastError);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800319c0  push    rbx
0x1800319c2  sub     rsp, 20h
0x1800319c6  mov     r9d, r8d; dwMoveMethod
0x1800319c9  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800319cc  call    cs:__imp_SetFilePointer
0x1800319d2  mov     ebx, eax
0x1800319d4  cmp     eax, 0FFFFFFFFh
0x1800319d7  jnz     short loc_1800319F6
0x1800319d9  call    cs:__imp_GetLastError
0x1800319df  test    eax, eax
0x1800319e1  jz      short loc_1800319F6
0x1800319e3  mov     edx, eax
0x1800319e5  lea     rcx, aFileSeekSetfil; "file_seek: SetFilePointer failed, GLE=0"...
0x1800319ec  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800319f1  or      eax, 0FFFFFFFFh
0x1800319f4  jmp     short loc_1800319F8
0x1800319f6  mov     eax, ebx
0x1800319f8  add     rsp, 20h
0x1800319fc  pop     rbx
0x1800319fd  retn
```
