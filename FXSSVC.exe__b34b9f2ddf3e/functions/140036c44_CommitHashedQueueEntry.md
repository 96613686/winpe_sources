# CommitHashedQueueEntry

- ea: `0x140036c44`
- end: `0x140036eac`
- name: `CommitHashedQueueEntry`
- size: `616`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140036eb4`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140036c44`
- `0x14003764c`
- `0x140065dbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140036d39`
- `KERNEL32!GetLastError` at `0x140036d9a`
- `KERNEL32!GetLastError` at `0x140036df9`
- `KERNEL32!GetLastError` at `0x140036e47`
- `KERNEL32!GetLastError` at `0x140036d39`
- `KERNEL32!GetLastError` at `0x140036d9a`
- `KERNEL32!GetLastError` at `0x140036df9`
- `KERNEL32!GetLastError` at `0x140036e47`
- `KERNEL32!WriteFile` at `0x140036d2f`
- `KERNEL32!WriteFile` at `0x140036d90`
- `KERNEL32!WriteFile` at `0x140036def`
- `KERNEL32!WriteFile` at `0x140036e3d`
- `KERNEL32!WriteFile` at `0x140036d2f`
- `KERNEL32!WriteFile` at `0x140036d90`
- `KERNEL32!WriteFile` at `0x140036def`
- `KERNEL32!WriteFile` at `0x140036e3d`

## pseudocode

```c
__int64 __fastcall CommitHashedQueueEntry(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  DWORD LastError; // ebx
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx
  DWORD nNumberOfBytesToWritea; // [rsp+30h] [rbp-10h] BYREF
  int Buffer; // [rsp+34h] [rbp-Ch] BYREF
  LPCVOID lpBuffera; // [rsp+38h] [rbp-8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp+38h] BYREF

  nNumberOfBytesToWritea = 0;
  lpBuffera = 0;
  Buffer = 1;
  NumberOfBytesWritten = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 330, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  LastError = ComputeHashCode(lpBuffer, nNumberOfBytesToWrite, &lpBuffera, &nNumberOfBytesToWritea);
  if ( !LastError )
  {
    if ( WriteFile(hFile, &Buffer, 4u, &NumberOfBytesWritten, 0) )
    {
      if ( WriteFile(hFile, &nNumberOfBytesToWritea, 4u, &NumberOfBytesWritten, 0) )
      {
        if ( WriteFile(hFile, lpBuffera, nNumberOfBytesToWritea, &NumberOfBytesWritten, 0) )
        {
          if ( WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
            goto LABEL_31;
          LastError = GetLastError();
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_31;
          }
          v8 = 335;
        }
        else
        {
          LastError = GetLastError();
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_31;
          }
          v8 = 334;
        }
      }
      else
      {
        LastError = GetLastError();
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_31;
        }
        v8 = 333;
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_31;
      }
      v8 = 332;
    }
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 331, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
  }
LABEL_31:
  if ( lpBuffera )
    pMemFree((LPVOID)lpBuffera);
  return LastError;
}

```

## disassembly

```asm
0x140036c44  mov     [rsp-18h+arg_0], rbx
0x140036c49  mov     [rsp-18h+arg_8], rdi
0x140036c4e  push    rbp
0x140036c4f  push    r14
0x140036c51  push    r15
0x140036c53  mov     rbp, rsp
0x140036c56  sub     rsp, 40h
0x140036c5a  mov     r14d, r8d
0x140036c5d  mov     [rbp+nNumberOfBytesToWrite], 0
0x140036c64  mov     r15, rdx
0x140036c67  mov     [rbp+lpBuffer], 0
0x140036c6f  mov     rdi, rcx
0x140036c72  mov     [rbp+Buffer], 1
0x140036c79  mov     [rbp+NumberOfBytesWritten], 0
0x140036c80  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c87  lea     rax, WPP_GLOBAL_Control
0x140036c8e  cmp     rcx, rax
0x140036c91  jz      short loc_140036CB4
0x140036c93  test    byte ptr [rcx+1Ch], 4
0x140036c97  jz      short loc_140036CB4
0x140036c99  cmp     byte ptr [rcx+19h], 5
0x140036c9d  jb      short loc_140036CB4
0x140036c9f  mov     rcx, [rcx+10h]
0x140036ca3  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140036caa  mov     edx, 14Ah
0x140036caf  call    WPP_SF_
0x140036cb4  lea     r9, [rbp+nNumberOfBytesToWrite]
0x140036cb8  mov     edx, r14d
0x140036cbb  lea     r8, [rbp+lpBuffer]
0x140036cbf  mov     rcx, r15
0x140036cc2  call    ComputeHashCode
0x140036cc7  mov     ebx, eax
0x140036cc9  test    eax, eax
0x140036ccb  jz      short loc_140036D15
0x140036ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x140036cd4  lea     rax, WPP_GLOBAL_Control
0x140036cdb  cmp     rcx, rax
0x140036cde  jz      loc_140036E86
0x140036ce4  test    byte ptr [rcx+1Ch], 4
0x140036ce8  jz      loc_140036E86
0x140036cee  cmp     byte ptr [rcx+19h], 2
0x140036cf2  jb      loc_140036E86
0x140036cf8  mov     rcx, [rcx+10h]
0x140036cfc  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140036d03  mov     edx, 14Bh
0x140036d08  mov     r9d, ebx
0x140036d0b  call    WPP_SF_d
0x140036d10  jmp     loc_140036E86
0x140036d15  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140036d19  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x140036d22  mov     r8d, 4; nNumberOfBytesToWrite
0x140036d28  lea     rdx, [rbp+Buffer]; lpBuffer
0x140036d2c  mov     rcx, rdi; hFile
0x140036d2f  call    cs:__imp_WriteFile
0x140036d35  test    eax, eax
0x140036d37  jnz     short loc_140036D76
0x140036d39  call    cs:__imp_GetLastError
0x140036d3f  mov     ebx, eax
0x140036d41  mov     rcx, cs:WPP_GLOBAL_Control
0x140036d48  lea     rax, WPP_GLOBAL_Control
0x140036d4f  cmp     rcx, rax
0x140036d52  jz      loc_140036E86
0x140036d58  test    byte ptr [rcx+1Ch], 4
0x140036d5c  jz      loc_140036E86
0x140036d62  cmp     byte ptr [rcx+19h], 2
0x140036d66  jb      loc_140036E86
0x140036d6c  mov     edx, 14Ch
0x140036d71  jmp     loc_140036E73
0x140036d76  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140036d7a  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x140036d83  mov     r8d, 4; nNumberOfBytesToWrite
0x140036d89  lea     rdx, [rbp+nNumberOfBytesToWrite]; lpBuffer
0x140036d8d  mov     rcx, rdi; hFile
0x140036d90  call    cs:__imp_WriteFile
0x140036d96  test    eax, eax
0x140036d98  jnz     short loc_140036DD7
0x140036d9a  call    cs:__imp_GetLastError
0x140036da0  mov     ebx, eax
0x140036da2  mov     rcx, cs:WPP_GLOBAL_Control
0x140036da9  lea     rax, WPP_GLOBAL_Control
0x140036db0  cmp     rcx, rax
0x140036db3  jz      loc_140036E86
0x140036db9  test    byte ptr [rcx+1Ch], 4
0x140036dbd  jz      loc_140036E86
0x140036dc3  cmp     byte ptr [rcx+19h], 2
0x140036dc7  jb      loc_140036E86
0x140036dcd  mov     edx, 14Dh
0x140036dd2  jmp     loc_140036E73
0x140036dd7  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x140036ddb  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140036ddf  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x140036de3  mov     rcx, rdi; hFile
0x140036de6  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x140036def  call    cs:__imp_WriteFile
0x140036df5  test    eax, eax
0x140036df7  jnz     short loc_140036E27
0x140036df9  call    cs:__imp_GetLastError
0x140036dff  mov     ebx, eax
0x140036e01  mov     rcx, cs:WPP_GLOBAL_Control
0x140036e08  lea     rax, WPP_GLOBAL_Control
0x140036e0f  cmp     rcx, rax
0x140036e12  jz      short loc_140036E86
0x140036e14  test    byte ptr [rcx+1Ch], 4
0x140036e18  jz      short loc_140036E86
0x140036e1a  cmp     byte ptr [rcx+19h], 2
0x140036e1e  jb      short loc_140036E86
0x140036e20  mov     edx, 14Eh
0x140036e25  jmp     short loc_140036E73
0x140036e27  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140036e2b  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x140036e34  mov     r8d, r14d; nNumberOfBytesToWrite
0x140036e37  mov     rdx, r15; lpBuffer
0x140036e3a  mov     rcx, rdi; hFile
0x140036e3d  call    cs:__imp_WriteFile
0x140036e43  test    eax, eax
0x140036e45  jnz     short loc_140036E86
0x140036e47  call    cs:__imp_GetLastError
0x140036e4d  mov     ebx, eax
0x140036e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140036e56  lea     rax, WPP_GLOBAL_Control
0x140036e5d  cmp     rcx, rax
0x140036e60  jz      short loc_140036E86
0x140036e62  test    byte ptr [rcx+1Ch], 4
0x140036e66  jz      short loc_140036E86
0x140036e68  cmp     byte ptr [rcx+19h], 2
0x140036e6c  jb      short loc_140036E86
0x140036e6e  mov     edx, 14Fh
0x140036e73  mov     rcx, [rcx+10h]
0x140036e77  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140036e7e  mov     r9d, ebx
0x140036e81  call    WPP_SF_d
0x140036e86  cmp     [rbp+lpBuffer], 0
0x140036e8b  jz      short loc_140036E96
0x140036e8d  mov     rcx, [rbp+lpBuffer]; lpMem
0x140036e91  call    pMemFree
0x140036e96  mov     rdi, [rsp+40h+arg_8]
0x140036e9b  mov     eax, ebx
0x140036e9d  mov     rbx, [rsp+40h+arg_0]
0x140036ea2  add     rsp, 40h
0x140036ea6  pop     r15
0x140036ea8  pop     r14
0x140036eaa  pop     rbp
0x140036eab  retn
```
