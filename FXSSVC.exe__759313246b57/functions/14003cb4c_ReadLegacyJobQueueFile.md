# ReadLegacyJobQueueFile

- ea: `0x14003cb4c`
- end: `0x14003cd8d`
- name: `ReadLegacyJobQueueFile`
- size: `577`
- prototype: `__int64 __fastcall(HANDLE hFile, struct _JOB_QUEUE_FILE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14003c834`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14003cb4c`
- `0x140040c68`
- `0x1400698ec`
- `0x14006998c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003cbbe`
- `KERNEL32!GetLastError` at `0x14003ccba`
- `KERNEL32!GetLastError` at `0x14003cbbe`
- `KERNEL32!GetLastError` at `0x14003ccba`
- `KERNEL32!GetFileSize` at `0x14003cbff`
- `KERNEL32!GetFileSize` at `0x14003cbff`
- `KERNEL32!ReadFile` at `0x14003ccaa`
- `KERNEL32!ReadFile` at `0x14003ccaa`
- `KERNEL32!SetFilePointer` at `0x14003cbab`
- `KERNEL32!SetFilePointer` at `0x14003cbab`

## pseudocode

```c
__int64 __fastcall ReadLegacyJobQueueFile(HANDLE hFile, struct _JOB_QUEUE_FILE **a2)
{
  struct _JOB_QUEUE_FILE *v4; // rdi
  DWORD LastError; // eax
  unsigned int v6; // ebx
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx
  DWORD FileSize; // eax
  DWORD v10; // ebx
  struct _JOB_QUEUE_FILE *v11; // rax
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+18h] BYREF

  NumberOfBytesRead = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 341, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  if ( SetFilePointer(hFile, 0, 0, 0) == -1 )
  {
    v4 = 0;
    LastError = GetLastError();
    v6 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 342;
LABEL_27:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
    }
  }
  else
  {
    FileSize = GetFileSize(hFile, 0);
    v10 = FileSize;
    if ( FileSize < 0x678 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 343, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, FileSize);
      }
      return 1392;
    }
    v11 = (struct _JOB_QUEUE_FILE *)pMemAlloc(FileSize);
    v4 = v11;
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 344, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v10);
      }
      return 8;
    }
    if ( ReadFile(hFile, v11, v10, &NumberOfBytesRead, 0) )
    {
      if ( v10 == NumberOfBytesRead )
      {
        if ( ValidateJobQueueOffsets(v4, NumberOfBytesRead) )
        {
          v6 = 0;
          *a2 = v4;
          return v6;
        }
        v6 = 13;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_42;
        }
        v13 = 347;
      }
      else
      {
        v6 = 38;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_42;
        }
        v13 = 346;
      }
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v6);
LABEL_42:
      pMemFree(v4);
      return v6;
    }
    LastError = GetLastError();
    v6 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 345;
      goto LABEL_27;
    }
  }
  if ( v6 && v4 )
    goto LABEL_42;
  return v6;
}

```

## disassembly

```asm
0x14003cb4c  mov     rax, rsp
0x14003cb4f  push    rbx
0x14003cb50  push    rsi
0x14003cb51  push    rdi
0x14003cb52  push    r12
0x14003cb54  push    r14
0x14003cb56  push    r15
0x14003cb58  sub     rsp, 38h
0x14003cb5c  mov     r14, rdx
0x14003cb5f  mov     dword ptr [rax+18h], 0
0x14003cb66  mov     rsi, rcx
0x14003cb69  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cb70  lea     r15, WPP_GLOBAL_Control
0x14003cb77  lea     r12, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003cb7e  cmp     rcx, r15
0x14003cb81  jz      short loc_14003CBA0
0x14003cb83  test    byte ptr [rcx+1Ch], 4
0x14003cb87  jz      short loc_14003CBA0
0x14003cb89  cmp     byte ptr [rcx+19h], 5
0x14003cb8d  jb      short loc_14003CBA0
0x14003cb8f  mov     rcx, [rcx+10h]
0x14003cb93  mov     edx, 155h
0x14003cb98  mov     r8, r12
0x14003cb9b  call    WPP_SF_
0x14003cba0  xor     r9d, r9d; dwMoveMethod
0x14003cba3  xor     r8d, r8d; lpDistanceToMoveHigh
0x14003cba6  xor     edx, edx; lDistanceToMove
0x14003cba8  mov     rcx, rsi; hFile
0x14003cbab  call    cs:__imp_SetFilePointer
0x14003cbb2  nop     dword ptr [rax+rax+00h]
0x14003cbb7  cmp     eax, 0FFFFFFFFh
0x14003cbba  jnz     short loc_14003CBFA
0x14003cbbc  xor     edi, edi
0x14003cbbe  call    cs:__imp_GetLastError
0x14003cbc5  nop     dword ptr [rax+rax+00h]
0x14003cbca  mov     ebx, eax
0x14003cbcc  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cbd3  cmp     rcx, r15
0x14003cbd6  jz      loc_14003CCF4
0x14003cbdc  test    byte ptr [rcx+1Ch], 4
0x14003cbe0  jz      loc_14003CCF4
0x14003cbe6  cmp     byte ptr [rcx+19h], 2
0x14003cbea  jb      loc_14003CCF4
0x14003cbf0  mov     edx, 156h
0x14003cbf5  jmp     loc_14003CCE5
0x14003cbfa  xor     edx, edx; lpFileSizeHigh
0x14003cbfc  mov     rcx, rsi; hFile
0x14003cbff  call    cs:__imp_GetFileSize
0x14003cc06  nop     dword ptr [rax+rax+00h]
0x14003cc0b  mov     ebx, eax
0x14003cc0d  cmp     eax, 678h
0x14003cc12  jnb     short loc_14003CC4A
0x14003cc14  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cc1b  cmp     rcx, r15
0x14003cc1e  jz      short loc_14003CC40
0x14003cc20  test    byte ptr [rcx+1Ch], 4
0x14003cc24  jz      short loc_14003CC40
0x14003cc26  cmp     byte ptr [rcx+19h], 3
0x14003cc2a  jb      short loc_14003CC40
0x14003cc2c  mov     rcx, [rcx+10h]
0x14003cc30  mov     edx, 157h
0x14003cc35  mov     r9d, ebx
0x14003cc38  mov     r8, r12
0x14003cc3b  call    WPP_SF_d
0x14003cc40  mov     ebx, 570h
0x14003cc45  jmp     loc_14003CD7C
0x14003cc4a  mov     rcx, rbx; dwBytes
0x14003cc4d  call    pMemAlloc
0x14003cc52  mov     rdi, rax
0x14003cc55  test    rax, rax
0x14003cc58  jnz     short loc_14003CC90
0x14003cc5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cc61  cmp     rcx, r15
0x14003cc64  jz      short loc_14003CC86
0x14003cc66  test    byte ptr [rcx+1Ch], 4
0x14003cc6a  jz      short loc_14003CC86
0x14003cc6c  cmp     byte ptr [rcx+19h], 2
0x14003cc70  jb      short loc_14003CC86
0x14003cc72  mov     rcx, [rcx+10h]
0x14003cc76  mov     edx, 158h
0x14003cc7b  mov     r9d, ebx
0x14003cc7e  mov     r8, r12
0x14003cc81  call    WPP_SF_d
0x14003cc86  mov     ebx, 8
0x14003cc8b  jmp     loc_14003CD7C
0x14003cc90  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14003cc98  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x14003cca1  mov     r8d, ebx; nNumberOfBytesToRead
0x14003cca4  mov     rdx, rdi; lpBuffer
0x14003cca7  mov     rcx, rsi; hFile
0x14003ccaa  call    cs:__imp_ReadFile
0x14003ccb1  nop     dword ptr [rax+rax+00h]
0x14003ccb6  test    eax, eax
0x14003ccb8  jnz     short loc_14003CD03
0x14003ccba  call    cs:__imp_GetLastError
0x14003ccc1  nop     dword ptr [rax+rax+00h]
0x14003ccc6  mov     ebx, eax
0x14003ccc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cccf  cmp     rcx, r15
0x14003ccd2  jz      short loc_14003CCF4
0x14003ccd4  test    byte ptr [rcx+1Ch], 4
0x14003ccd8  jz      short loc_14003CCF4
0x14003ccda  cmp     byte ptr [rcx+19h], 2
0x14003ccde  jb      short loc_14003CCF4
0x14003cce0  mov     edx, 159h
0x14003cce5  mov     rcx, [rcx+10h]
0x14003cce9  mov     r9d, eax
0x14003ccec  mov     r8, r12
0x14003ccef  call    WPP_SF_d
0x14003ccf4  test    ebx, ebx
0x14003ccf6  jz      loc_14003CD7C
0x14003ccfc  test    rdi, rdi
0x14003ccff  jz      short loc_14003CD7C
0x14003cd01  jmp     short loc_14003CD6D
0x14003cd03  mov     edx, [rsp+68h+NumberOfBytesRead]; unsigned int
0x14003cd0a  cmp     ebx, edx
0x14003cd0c  jz      short loc_14003CD32
0x14003cd0e  mov     ebx, 26h ; '&'
0x14003cd13  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cd1a  cmp     rcx, r15
0x14003cd1d  jz      short loc_14003CD6D
0x14003cd1f  test    byte ptr [rcx+1Ch], 4
0x14003cd23  jz      short loc_14003CD6D
0x14003cd25  cmp     byte ptr [rcx+19h], 2
0x14003cd29  jb      short loc_14003CD6D
0x14003cd2b  mov     edx, 15Ah
0x14003cd30  jmp     short loc_14003CD5E
0x14003cd32  mov     rcx, rdi; struct _JOB_QUEUE_FILE *
0x14003cd35  call    ?ValidateJobQueueOffsets@@YAHPEAU_JOB_QUEUE_FILE@@K@Z; ValidateJobQueueOffsets(_JOB_QUEUE_FILE *,ulong)
0x14003cd3a  test    eax, eax
0x14003cd3c  jnz     short loc_14003CD77
0x14003cd3e  lea     ebx, [rax+0Dh]
0x14003cd41  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cd48  cmp     rcx, r15
0x14003cd4b  jz      short loc_14003CD6D
0x14003cd4d  test    byte ptr [rcx+1Ch], 4
0x14003cd51  jz      short loc_14003CD6D
0x14003cd53  cmp     byte ptr [rcx+19h], 2
0x14003cd57  jb      short loc_14003CD6D
0x14003cd59  mov     edx, 15Bh
0x14003cd5e  mov     rcx, [rcx+10h]
0x14003cd62  mov     r9d, ebx
0x14003cd65  mov     r8, r12
0x14003cd68  call    WPP_SF_d
0x14003cd6d  mov     rcx, rdi; lpMem
0x14003cd70  call    pMemFree
0x14003cd75  jmp     short loc_14003CD7C
0x14003cd77  xor     ebx, ebx
0x14003cd79  mov     [r14], rdi
0x14003cd7c  mov     eax, ebx
0x14003cd7e  add     rsp, 38h
0x14003cd82  pop     r15
0x14003cd84  pop     r14
0x14003cd86  pop     r12
0x14003cd88  pop     rdi
0x14003cd89  pop     rsi
0x14003cd8a  pop     rbx
0x14003cd8b  retn
```
