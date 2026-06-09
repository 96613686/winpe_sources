# SafeDeleteFileByHandle(ushort *)

- ea: `0x14006bff4`
- end: `0x14006c12a`
- name: `?SafeDeleteFileByHandle@@YAHPEAG@Z`
- size: `310`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14006e160`

## callees

- `0x140004b58`
- `0x140004df0`
- `0x14006a46c`
- `0x14006bff4`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x14006c06f`
- `KERNEL32!SetFileInformationByHandle` at `0x14006c06f`
- `KERNEL32!CreateFileW` at `0x14006c026`
- `KERNEL32!CreateFileW` at `0x14006c026`
- `KERNEL32!GetLastError` at `0x14006c0a2`
- `KERNEL32!GetLastError` at `0x14006c0c7`
- `KERNEL32!GetLastError` at `0x14006c0a2`
- `KERNEL32!GetLastError` at `0x14006c0c7`
- `KERNEL32!CloseHandle` at `0x14006c04e`
- `KERNEL32!CloseHandle` at `0x14006c07c`
- `KERNEL32!CloseHandle` at `0x14006c04e`
- `KERNEL32!CloseHandle` at `0x14006c07c`

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
0x14006bff4  push    rbx
0x14006bff6  push    rsi
0x14006bff7  push    rdi
0x14006bff8  push    r14
0x14006bffa  sub     rsp, 48h
0x14006bffe  xor     r9d, r9d; lpSecurityAttributes
0x14006c001  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x14006c00a  mov     [rsp+68h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x14006c012  mov     edx, 10000h; dwDesiredAccess
0x14006c017  mov     rsi, rcx
0x14006c01a  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x14006c022  lea     r8d, [r9+5]; dwShareMode
0x14006c026  call    cs:__imp_CreateFileW
0x14006c02c  lea     r14, WPP_GLOBAL_Control
0x14006c033  mov     rdi, rax
0x14006c036  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006c03a  jz      short loc_14006C0AD
0x14006c03c  mov     rdx, rax; hFile
0x14006c03f  mov     rcx, rsi; unsigned __int16 *
0x14006c042  call    ?IsValidFilePath@@YAHPEAGPEAX@Z; IsValidFilePath(ushort *,void *)
0x14006c047  mov     rcx, rdi; hFile
0x14006c04a  test    eax, eax
0x14006c04c  jnz     short loc_14006C05B
0x14006c04e  call    cs:__imp_CloseHandle
0x14006c054  xor     ebx, ebx
0x14006c056  jmp     loc_14006C0EA
0x14006c05b  mov     ebx, 1
0x14006c060  lea     r8, [rsp+68h+FileInformation]; lpFileInformation
0x14006c065  mov     r9d, ebx; dwBufferSize
0x14006c068  mov     [rsp+68h+FileInformation], bl
0x14006c06c  lea     edx, [rbx+3]; FileInformationClass
0x14006c06f  call    cs:__imp_SetFileInformationByHandle
0x14006c075  test    eax, eax
0x14006c077  jz      short loc_14006C084
0x14006c079  mov     rcx, rdi; hObject
0x14006c07c  call    cs:__imp_CloseHandle
0x14006c082  jmp     short loc_14006C0EA
0x14006c084  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c08b  xor     ebx, ebx
0x14006c08d  cmp     rcx, r14
0x14006c090  jz      loc_14006C11E
0x14006c096  test    byte ptr [rcx+1Ch], 2
0x14006c09a  jz      short loc_14006C0F1
0x14006c09c  cmp     byte ptr [rcx+19h], 2
0x14006c0a0  jb      short loc_14006C0F1
0x14006c0a2  call    cs:__imp_GetLastError
0x14006c0a8  lea     edx, [rbx+53h]
0x14006c0ab  jmp     short loc_14006C0D0
0x14006c0ad  xor     ebx, ebx
0x14006c0af  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c0b6  cmp     rcx, r14
0x14006c0b9  jz      short loc_14006C11E
0x14006c0bb  test    byte ptr [rcx+1Ch], 2
0x14006c0bf  jz      short loc_14006C0F1
0x14006c0c1  cmp     byte ptr [rcx+19h], 2
0x14006c0c5  jb      short loc_14006C0F1
0x14006c0c7  call    cs:__imp_GetLastError
0x14006c0cd  lea     edx, [rbx+54h]
0x14006c0d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c0d7  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006c0de  mov     r9d, eax
0x14006c0e1  mov     rcx, [rcx+10h]
0x14006c0e5  call    WPP_SF_d
0x14006c0ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c0f1  cmp     rcx, r14
0x14006c0f4  jz      short loc_14006C11E
0x14006c0f6  test    byte ptr [rcx+1Ch], 2
0x14006c0fa  jz      short loc_14006C11E
0x14006c0fc  cmp     byte ptr [rcx+19h], 2
0x14006c100  jb      short loc_14006C11E
0x14006c102  mov     rcx, [rcx+10h]
0x14006c106  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006c10d  mov     edx, 55h ; 'U'
0x14006c112  mov     [rsp+68h+dwCreationDisposition], ebx
0x14006c116  mov     r9, rsi
0x14006c119  call    WPP_SF_Sd
0x14006c11e  mov     eax, ebx
0x14006c120  add     rsp, 48h
0x14006c124  pop     r14
0x14006c126  pop     rdi
0x14006c127  pop     rsi
0x14006c128  pop     rbx
0x14006c129  retn
```
