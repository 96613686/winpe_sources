# SafeDeleteFileByHandle(ushort *)

- ea: `0x14006ff04`
- end: `0x140070063`
- name: `?SafeDeleteFileByHandle@@YAHPEAG@Z`
- size: `351`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140072490`

## callees

- `0x140004ca8`
- `0x140004f64`
- `0x14006e208`
- `0x14006ff04`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x14006ff8f`
- `KERNEL32!SetFileInformationByHandle` at `0x14006ff8f`
- `KERNEL32!CreateFileW` at `0x14006ff36`
- `KERNEL32!CreateFileW` at `0x14006ff36`
- `KERNEL32!GetLastError` at `0x14006ffce`
- `KERNEL32!GetLastError` at `0x14006fff9`
- `KERNEL32!GetLastError` at `0x14006ffce`
- `KERNEL32!GetLastError` at `0x14006fff9`
- `KERNEL32!CloseHandle` at `0x14006ff68`
- `KERNEL32!CloseHandle` at `0x14006ffa2`
- `KERNEL32!CloseHandle` at `0x14006ff68`
- `KERNEL32!CloseHandle` at `0x14006ffa2`

## pseudocode

```c
__int64 __fastcall SafeDeleteFileByHandle(unsigned __int16 *a1)
{
  HANDLE FileW; // rax
  void *v3; // rdi
  unsigned int v4; // ebx
  CMapDeviceId *v5; // rcx
  DWORD LastError; // eax
  __int64 v7; // rdx
  char FileInformation; // [rsp+78h] [rbp+10h] BYREF

  FileW = CreateFileW(a1, 0x10000u, 5u, 0, 3u, 0x200080u, 0);
  v3 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v4 = 0;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    LastError = GetLastError();
    v7 = 84;
    goto LABEL_14;
  }
  if ( !(unsigned int)IsValidFilePath(a1, FileW) )
  {
    CloseHandle(v3);
    v4 = 0;
LABEL_15:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  v4 = 1;
  FileInformation = 1;
  if ( SetFileInformationByHandle(v3, FileDispositionInfo, &FileInformation, 1u) )
  {
    CloseHandle(v3);
    goto LABEL_15;
  }
  v5 = WPP_GLOBAL_Control;
  v4 = 0;
  if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v7 = 83;
LABEL_14:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, LastError);
    goto LABEL_15;
  }
LABEL_16:
  if ( v5 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 && *((_BYTE *)v5 + 25) >= 2u )
    WPP_SF_Sd(*((_QWORD *)v5 + 2), 85, (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, (_DWORD)a1, v4);
  return v4;
}

```

## disassembly

```asm
0x14006ff04  push    rbx
0x14006ff06  push    rsi
0x14006ff07  push    rdi
0x14006ff08  push    r14
0x14006ff0a  sub     rsp, 48h
0x14006ff0e  xor     r9d, r9d; lpSecurityAttributes
0x14006ff11  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x14006ff1a  mov     [rsp+68h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x14006ff22  mov     edx, 10000h; dwDesiredAccess
0x14006ff27  mov     rsi, rcx
0x14006ff2a  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x14006ff32  lea     r8d, [r9+5]; dwShareMode
0x14006ff36  call    cs:__imp_CreateFileW
0x14006ff3d  nop     dword ptr [rax+rax+00h]
0x14006ff42  lea     r14, WPP_GLOBAL_Control
0x14006ff49  mov     rdi, rax
0x14006ff4c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006ff50  jz      loc_14006FFDF
0x14006ff56  mov     rdx, rax; hFile
0x14006ff59  mov     rcx, rsi; unsigned __int16 *
0x14006ff5c  call    ?IsValidFilePath@@YAHPEAGPEAX@Z; IsValidFilePath(ushort *,void *)
0x14006ff61  mov     rcx, rdi; hFile
0x14006ff64  test    eax, eax
0x14006ff66  jnz     short loc_14006FF7B
0x14006ff68  call    cs:__imp_CloseHandle
0x14006ff6f  nop     dword ptr [rax+rax+00h]
0x14006ff74  xor     ebx, ebx
0x14006ff76  jmp     loc_140070022
0x14006ff7b  mov     ebx, 1
0x14006ff80  lea     r8, [rsp+68h+FileInformation]; lpFileInformation
0x14006ff85  mov     r9d, ebx; dwBufferSize
0x14006ff88  mov     [rsp+68h+FileInformation], bl
0x14006ff8c  lea     edx, [rbx+3]; FileInformationClass
0x14006ff8f  call    cs:__imp_SetFileInformationByHandle
0x14006ff96  nop     dword ptr [rax+rax+00h]
0x14006ff9b  test    eax, eax
0x14006ff9d  jz      short loc_14006FFB0
0x14006ff9f  mov     rcx, rdi; hObject
0x14006ffa2  call    cs:__imp_CloseHandle
0x14006ffa9  nop     dword ptr [rax+rax+00h]
0x14006ffae  jmp     short loc_140070022
0x14006ffb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ffb7  xor     ebx, ebx
0x14006ffb9  cmp     rcx, r14
0x14006ffbc  jz      loc_140070056
0x14006ffc2  test    byte ptr [rcx+1Ch], 2
0x14006ffc6  jz      short loc_140070029
0x14006ffc8  cmp     byte ptr [rcx+19h], 2
0x14006ffcc  jb      short loc_140070029
0x14006ffce  call    cs:__imp_GetLastError
0x14006ffd5  nop     dword ptr [rax+rax+00h]
0x14006ffda  lea     edx, [rbx+53h]
0x14006ffdd  jmp     short loc_140070008
0x14006ffdf  xor     ebx, ebx
0x14006ffe1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ffe8  cmp     rcx, r14
0x14006ffeb  jz      short loc_140070056
0x14006ffed  test    byte ptr [rcx+1Ch], 2
0x14006fff1  jz      short loc_140070029
0x14006fff3  cmp     byte ptr [rcx+19h], 2
0x14006fff7  jb      short loc_140070029
0x14006fff9  call    cs:__imp_GetLastError
0x140070000  nop     dword ptr [rax+rax+00h]
0x140070005  lea     edx, [rbx+54h]
0x140070008  mov     rcx, cs:WPP_GLOBAL_Control
0x14007000f  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140070016  mov     r9d, eax
0x140070019  mov     rcx, [rcx+10h]
0x14007001d  call    WPP_SF_d
0x140070022  mov     rcx, cs:WPP_GLOBAL_Control
0x140070029  cmp     rcx, r14
0x14007002c  jz      short loc_140070056
0x14007002e  test    byte ptr [rcx+1Ch], 2
0x140070032  jz      short loc_140070056
0x140070034  cmp     byte ptr [rcx+19h], 2
0x140070038  jb      short loc_140070056
0x14007003a  mov     rcx, [rcx+10h]
0x14007003e  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x140070045  mov     edx, 55h ; 'U'
0x14007004a  mov     [rsp+68h+dwCreationDisposition], ebx
0x14007004e  mov     r9, rsi
0x140070051  call    WPP_SF_Sd
0x140070056  mov     eax, ebx
0x140070058  add     rsp, 48h
0x14007005c  pop     r14
0x14007005e  pop     rdi
0x14007005f  pop     rsi
0x140070060  pop     rbx
0x140070061  retn
```
