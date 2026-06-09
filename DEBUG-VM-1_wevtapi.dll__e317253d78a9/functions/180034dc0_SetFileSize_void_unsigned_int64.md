# SetFileSize(void *,unsigned __int64)

- ea: `0x180034dc0`
- end: `0x180034e32`
- name: `?SetFileSize@@YAKPEAX_K@Z`
- size: `114`
- prototype: `unsigned int __fastcall(void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800314a0`
- `0x1800323a4`
- `0x180033258`

## callees

- `0x180023548`
- `0x180034dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034de4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180034dda`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180034dda`

## pseudocode

```c
__int64 __fastcall SetFileSize(void *a1, __int64 a2)
{
  DWORD LastError; // ebx
  __int64 FileInformation; // [rsp+38h] [rbp+10h] BYREF

  FileInformation = a2;
  if ( SetFileInformationByHandle(a1, FileEndOfFileInfo, &FileInformation, 8u) )
    return 0;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_f9efb118310932df1b6c7c37b5e7929e_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180034dc0  push    rbx
0x180034dc2  sub     rsp, 20h
0x180034dc6  mov     r9d, 8; dwBufferSize
0x180034dcc  mov     [rsp+28h+FileInformation], rdx
0x180034dd1  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x180034dd6  lea     edx, [r9-2]; FileInformationClass
0x180034dda  call    cs:__imp_SetFileInformationByHandle
0x180034de0  test    eax, eax
0x180034de2  jnz     short loc_180034E2A
0x180034de4  call    cs:__imp_GetLastError
0x180034dea  mov     ebx, eax
0x180034dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180034df3  lea     rax, WPP_GLOBAL_Control
0x180034dfa  cmp     rcx, rax
0x180034dfd  jz      short loc_180034E26
0x180034dff  test    dword ptr [rcx+1Ch], 8000h
0x180034e06  jz      short loc_180034E26
0x180034e08  cmp     byte ptr [rcx+19h], 2
0x180034e0c  jb      short loc_180034E26
0x180034e0e  mov     rcx, [rcx+10h]
0x180034e12  lea     r8, WPP_f9efb118310932df1b6c7c37b5e7929e_Traceguids
0x180034e19  mov     edx, 0Bh
0x180034e1e  mov     r9d, ebx
0x180034e21  call    WPP_SF_D
0x180034e26  mov     eax, ebx
0x180034e28  jmp     short loc_180034E2C
0x180034e2a  xor     eax, eax
0x180034e2c  add     rsp, 20h
0x180034e30  pop     rbx
0x180034e31  retn
```
