# CommitHashedQueueEntry

- ea: `0x140038aa4`
- end: `0x140038d3d`
- name: `CommitHashedQueueEntry`
- size: `665`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140038d44`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140038aa4`
- `0x14003950c`
- `0x14006998c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140038b9f`
- `KERNEL32!GetLastError` at `0x140038c0c`
- `KERNEL32!GetLastError` at `0x140038c77`
- `KERNEL32!GetLastError` at `0x140038cd1`
- `KERNEL32!GetLastError` at `0x140038b9f`
- `KERNEL32!GetLastError` at `0x140038c0c`
- `KERNEL32!GetLastError` at `0x140038c77`
- `KERNEL32!GetLastError` at `0x140038cd1`
- `KERNEL32!WriteFile` at `0x140038b8f`
- `KERNEL32!WriteFile` at `0x140038bfc`
- `KERNEL32!WriteFile` at `0x140038c67`
- `KERNEL32!WriteFile` at `0x140038cc1`
- `KERNEL32!WriteFile` at `0x140038b8f`
- `KERNEL32!WriteFile` at `0x140038bfc`
- `KERNEL32!WriteFile` at `0x140038c67`
- `KERNEL32!WriteFile` at `0x140038cc1`

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
0x140038aa4  mov     [rsp-18h+arg_0], rbx
0x140038aa9  mov     [rsp-18h+arg_8], rdi
0x140038aae  push    rbp
0x140038aaf  push    r14
0x140038ab1  push    r15
0x140038ab3  mov     rbp, rsp
0x140038ab6  sub     rsp, 40h
0x140038aba  mov     r14d, r8d
0x140038abd  mov     [rbp+nNumberOfBytesToWrite], 0
0x140038ac4  mov     r15, rdx
0x140038ac7  mov     [rbp+lpBuffer], 0
0x140038acf  mov     rdi, rcx
0x140038ad2  mov     [rbp+Buffer], 1
0x140038ad9  mov     [rbp+NumberOfBytesWritten], 0
0x140038ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x140038ae7  lea     rax, WPP_GLOBAL_Control
0x140038aee  cmp     rcx, rax
0x140038af1  jz      short loc_140038B14
0x140038af3  test    byte ptr [rcx+1Ch], 4
0x140038af7  jz      short loc_140038B14
0x140038af9  cmp     byte ptr [rcx+19h], 5
0x140038afd  jb      short loc_140038B14
0x140038aff  mov     rcx, [rcx+10h]
0x140038b03  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038b0a  mov     edx, 14Ah
0x140038b0f  call    WPP_SF_
0x140038b14  lea     r9, [rbp+nNumberOfBytesToWrite]
0x140038b18  mov     edx, r14d
0x140038b1b  lea     r8, [rbp+lpBuffer]
0x140038b1f  mov     rcx, r15
0x140038b22  call    ComputeHashCode
0x140038b27  mov     ebx, eax
0x140038b29  test    eax, eax
0x140038b2b  jz      short loc_140038B75
0x140038b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140038b34  lea     rax, WPP_GLOBAL_Control
0x140038b3b  cmp     rcx, rax
0x140038b3e  jz      loc_140038D16
0x140038b44  test    byte ptr [rcx+1Ch], 4
0x140038b48  jz      loc_140038D16
0x140038b4e  cmp     byte ptr [rcx+19h], 2
0x140038b52  jb      loc_140038D16
0x140038b58  mov     rcx, [rcx+10h]
0x140038b5c  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038b63  mov     edx, 14Bh
0x140038b68  mov     r9d, ebx
0x140038b6b  call    WPP_SF_d
0x140038b70  jmp     loc_140038D16
0x140038b75  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140038b79  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x140038b82  mov     r8d, 4; nNumberOfBytesToWrite
0x140038b88  lea     rdx, [rbp+Buffer]; lpBuffer
0x140038b8c  mov     rcx, rdi; hFile
0x140038b8f  call    cs:__imp_WriteFile
0x140038b96  nop     dword ptr [rax+rax+00h]
0x140038b9b  test    eax, eax
0x140038b9d  jnz     short loc_140038BE2
0x140038b9f  call    cs:__imp_GetLastError
0x140038ba6  nop     dword ptr [rax+rax+00h]
0x140038bab  mov     ebx, eax
0x140038bad  mov     rcx, cs:WPP_GLOBAL_Control
0x140038bb4  lea     rax, WPP_GLOBAL_Control
0x140038bbb  cmp     rcx, rax
0x140038bbe  jz      loc_140038D16
0x140038bc4  test    byte ptr [rcx+1Ch], 4
0x140038bc8  jz      loc_140038D16
0x140038bce  cmp     byte ptr [rcx+19h], 2
0x140038bd2  jb      loc_140038D16
0x140038bd8  mov     edx, 14Ch
0x140038bdd  jmp     loc_140038D03
0x140038be2  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140038be6  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x140038bef  mov     r8d, 4; nNumberOfBytesToWrite
0x140038bf5  lea     rdx, [rbp+nNumberOfBytesToWrite]; lpBuffer
0x140038bf9  mov     rcx, rdi; hFile
0x140038bfc  call    cs:__imp_WriteFile
0x140038c03  nop     dword ptr [rax+rax+00h]
0x140038c08  test    eax, eax
0x140038c0a  jnz     short loc_140038C4F
0x140038c0c  call    cs:__imp_GetLastError
0x140038c13  nop     dword ptr [rax+rax+00h]
0x140038c18  mov     ebx, eax
0x140038c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140038c21  lea     rax, WPP_GLOBAL_Control
0x140038c28  cmp     rcx, rax
0x140038c2b  jz      loc_140038D16
0x140038c31  test    byte ptr [rcx+1Ch], 4
0x140038c35  jz      loc_140038D16
0x140038c3b  cmp     byte ptr [rcx+19h], 2
0x140038c3f  jb      loc_140038D16
0x140038c45  mov     edx, 14Dh
0x140038c4a  jmp     loc_140038D03
0x140038c4f  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x140038c53  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140038c57  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x140038c5b  mov     rcx, rdi; hFile
0x140038c5e  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x140038c67  call    cs:__imp_WriteFile
0x140038c6e  nop     dword ptr [rax+rax+00h]
0x140038c73  test    eax, eax
0x140038c75  jnz     short loc_140038CAB
0x140038c77  call    cs:__imp_GetLastError
0x140038c7e  nop     dword ptr [rax+rax+00h]
0x140038c83  mov     ebx, eax
0x140038c85  mov     rcx, cs:WPP_GLOBAL_Control
0x140038c8c  lea     rax, WPP_GLOBAL_Control
0x140038c93  cmp     rcx, rax
0x140038c96  jz      short loc_140038D16
0x140038c98  test    byte ptr [rcx+1Ch], 4
0x140038c9c  jz      short loc_140038D16
0x140038c9e  cmp     byte ptr [rcx+19h], 2
0x140038ca2  jb      short loc_140038D16
0x140038ca4  mov     edx, 14Eh
0x140038ca9  jmp     short loc_140038D03
0x140038cab  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140038caf  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x140038cb8  mov     r8d, r14d; nNumberOfBytesToWrite
0x140038cbb  mov     rdx, r15; lpBuffer
0x140038cbe  mov     rcx, rdi; hFile
0x140038cc1  call    cs:__imp_WriteFile
0x140038cc8  nop     dword ptr [rax+rax+00h]
0x140038ccd  test    eax, eax
0x140038ccf  jnz     short loc_140038D16
0x140038cd1  call    cs:__imp_GetLastError
0x140038cd8  nop     dword ptr [rax+rax+00h]
0x140038cdd  mov     ebx, eax
0x140038cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x140038ce6  lea     rax, WPP_GLOBAL_Control
0x140038ced  cmp     rcx, rax
0x140038cf0  jz      short loc_140038D16
0x140038cf2  test    byte ptr [rcx+1Ch], 4
0x140038cf6  jz      short loc_140038D16
0x140038cf8  cmp     byte ptr [rcx+19h], 2
0x140038cfc  jb      short loc_140038D16
0x140038cfe  mov     edx, 14Fh
0x140038d03  mov     rcx, [rcx+10h]
0x140038d07  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038d0e  mov     r9d, ebx
0x140038d11  call    WPP_SF_d
0x140038d16  cmp     [rbp+lpBuffer], 0
0x140038d1b  jz      short loc_140038D26
0x140038d1d  mov     rcx, [rbp+lpBuffer]; lpMem
0x140038d21  call    pMemFree
0x140038d26  mov     rdi, [rsp+40h+arg_8]
0x140038d2b  mov     eax, ebx
0x140038d2d  mov     rbx, [rsp+40h+arg_0]
0x140038d32  add     rsp, 40h
0x140038d36  pop     r15
0x140038d38  pop     r14
0x140038d3a  pop     rbp
0x140038d3b  retn
```
