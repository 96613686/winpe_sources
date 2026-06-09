# CDiskIO::WriteSectorsToDevice(void *,CDisk *,__int64,ulong,uchar * const,ulong)

- ea: `0x1800589ac`
- end: `0x180058b59`
- name: `?WriteSectorsToDevice@CDiskIO@@SAKPEAXPEAVCDisk@@_JKQEAEK@Z`
- size: `429`
- prototype: `unsigned int __usercall@<eax>(HANDLE hFile@<rcx>, struct CDisk *@<rdx>, __int64@<r8>, unsigned int@<r9d>, unsigned __int8 *const, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180057b94`
- `0x180057de8`

## callees

- `0x18004f8d0`
- `0x1800589ac`
- `0x180058b60`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x180058a49`
- `KERNEL32!SetFilePointer` at `0x180058a49`
- `KERNEL32!GetLastError` at `0x180058a4f`
- `KERNEL32!GetLastError` at `0x180058ac7`
- `KERNEL32!GetLastError` at `0x180058a4f`
- `KERNEL32!GetLastError` at `0x180058ac7`
- `KERNEL32!WriteFile` at `0x180058abd`
- `KERNEL32!WriteFile` at `0x180058abd`
- `KERNEL32!SetLastError` at `0x180058a34`
- `KERNEL32!SetLastError` at `0x180058a34`

## pseudocode

```c
__int64 __fastcall CDiskIO::WriteSectorsToDevice(
        HANDLE hFile,
        struct CDisk *a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 *const lpBuffer,
        DWORD a6)
{
  __int64 v9; // rcx
  DWORD LastError; // edi
  __int64 v11; // rax
  _QWORD *v12; // r8
  __int64 v13; // rdx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-58h] BYREF
  LONG DistanceToMoveHigh[2]; // [rsp+38h] [rbp-50h] BYREF

  NumberOfBytesWritten = 0;
  if ( lpBuffer )
  {
    if ( a2 )
    {
      v9 = *((_QWORD *)a2 + 1);
      if ( a6 >= *(_DWORD *)(v9 + 20) * a4 && a3 + a4 <= *((_QWORD *)a2 + 136) )
      {
        *(_QWORD *)DistanceToMoveHigh = 0;
        *(_QWORD *)DistanceToMoveHigh = a3 * *(unsigned int *)(v9 + 20);
        SetLastError(0);
        SetFilePointer(hFile, DistanceToMoveHigh[0], &DistanceToMoveHigh[1], 0);
        LastError = GetLastError();
        if ( LastError )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              &WPP_70e883ff648235bf9018dbd80de8c80b_Traceguids,
              LastError);
          return LastError;
        }
        v11 = *((_QWORD *)a2 + 1);
        NumberOfBytesWritten = a6;
        if ( WriteFile(hFile, lpBuffer, *(_DWORD *)(v11 + 20) * a4, &NumberOfBytesWritten, 0) )
        {
          if ( NumberOfBytesWritten == a6 )
            return LastError;
          LastError = 1359;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            return LastError;
          v13 = 16;
        }
        else
        {
          LastError = GetLastError();
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            return LastError;
          v13 = 15;
        }
        WPP_SF_ddD(v12[2], v13, v12, *(_DWORD *)(*((_QWORD *)a2 + 1) + 20LL) * a4, a6, LastError);
        return LastError;
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x1800589ac  push    rbx
0x1800589ae  push    rbp
0x1800589af  push    rsi
0x1800589b0  push    rdi
0x1800589b1  push    r14
0x1800589b3  push    r15
0x1800589b5  sub     rsp, 58h
0x1800589b9  mov     rax, cs:__security_cookie
0x1800589c0  xor     rax, rsp
0x1800589c3  mov     [rsp+88h+var_48], rax
0x1800589c8  mov     r15, [rsp+88h+lpBuffer]
0x1800589d0  mov     rsi, rdx
0x1800589d3  mov     ebx, r9d
0x1800589d6  mov     r14, rcx
0x1800589d9  mov     [rsp+88h+NumberOfBytesWritten], 0
0x1800589e1  test    r15, r15
0x1800589e4  jz      loc_180058B3A
0x1800589ea  test    rdx, rdx
0x1800589ed  jz      loc_180058B3A
0x1800589f3  mov     rcx, [rdx+8]
0x1800589f7  mov     eax, ebx
0x1800589f9  mov     ebp, [rsp+88h+arg_28]
0x180058a00  imul    eax, [rcx+14h]
0x180058a04  cmp     ebp, eax
0x180058a06  jb      loc_180058B3A
0x180058a0c  lea     rax, [r8+rbx]
0x180058a10  cmp     rax, [rdx+440h]
0x180058a17  jg      loc_180058B3A
0x180058a1d  mov     qword ptr [rsp+88h+DistanceToMoveHigh], 0
0x180058a26  mov     eax, [rcx+14h]
0x180058a29  xor     ecx, ecx; dwErrCode
0x180058a2b  imul    rax, r8
0x180058a2f  mov     qword ptr [rsp+88h+DistanceToMoveHigh], rax
0x180058a34  call    cs:__imp_SetLastError
0x180058a3a  mov     edx, [rsp+88h+DistanceToMoveHigh]; lDistanceToMove
0x180058a3e  lea     r8, [rsp+88h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x180058a43  xor     r9d, r9d; dwMoveMethod
0x180058a46  mov     rcx, r14; hFile
0x180058a49  call    cs:__imp_SetFilePointer
0x180058a4f  call    cs:__imp_GetLastError
0x180058a55  mov     edi, eax
0x180058a57  test    eax, eax
0x180058a59  jz      short loc_180058A99
0x180058a5b  mov     rax, cs:WPP_GLOBAL_Control
0x180058a62  lea     rcx, WPP_GLOBAL_Control
0x180058a69  cmp     rax, rcx
0x180058a6c  jz      loc_180058B36
0x180058a72  test    byte ptr [rax+1Ch], 2
0x180058a76  jz      loc_180058B36
0x180058a7c  mov     rcx, [rax+10h]
0x180058a80  lea     r8, WPP_70e883ff648235bf9018dbd80de8c80b_Traceguids
0x180058a87  mov     edx, 0Eh
0x180058a8c  mov     r9d, edi
0x180058a8f  call    WPP_SF_d
0x180058a94  jmp     loc_180058B36
0x180058a99  mov     rax, [rsi+8]
0x180058a9d  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180058aa2  mov     r8d, ebx
0x180058aa5  mov     [rsp+88h+NumberOfBytesWritten], ebp
0x180058aa9  mov     rdx, r15; lpBuffer
0x180058aac  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x180058ab5  mov     rcx, r14; hFile
0x180058ab8  imul    r8d, [rax+14h]; nNumberOfBytesToWrite
0x180058abd  call    cs:__imp_WriteFile
0x180058ac3  test    eax, eax
0x180058ac5  jnz     short loc_180058AF0
0x180058ac7  call    cs:__imp_GetLastError
0x180058acd  mov     edi, eax
0x180058acf  mov     r8, cs:WPP_GLOBAL_Control
0x180058ad6  lea     rcx, WPP_GLOBAL_Control
0x180058add  cmp     r8, rcx
0x180058ae0  jz      short loc_180058B36
0x180058ae2  test    byte ptr [r8+1Ch], 2
0x180058ae7  jz      short loc_180058B36
0x180058ae9  mov     edx, 0Fh
0x180058aee  jmp     short loc_180058B1A
0x180058af0  cmp     [rsp+88h+NumberOfBytesWritten], ebp
0x180058af4  jz      short loc_180058B36
0x180058af6  mov     edi, 54Fh
0x180058afb  mov     r8, cs:WPP_GLOBAL_Control
0x180058b02  lea     rcx, WPP_GLOBAL_Control
0x180058b09  cmp     r8, rcx
0x180058b0c  jz      short loc_180058B36
0x180058b0e  test    byte ptr [r8+1Ch], 2
0x180058b13  jz      short loc_180058B36
0x180058b15  mov     edx, 10h
0x180058b1a  mov     rax, [rsi+8]
0x180058b1e  mov     rcx, [r8+10h]
0x180058b22  mov     [rsp+88h+var_60], edi
0x180058b26  mov     dword ptr [rsp+88h+lpOverlapped], ebp
0x180058b2a  imul    ebx, [rax+14h]
0x180058b2e  mov     r9d, ebx
0x180058b31  call    WPP_SF_ddD
0x180058b36  mov     eax, edi
0x180058b38  jmp     short loc_180058B3F
0x180058b3a  mov     eax, 57h ; 'W'
0x180058b3f  mov     rcx, [rsp+88h+var_48]
0x180058b44  xor     rcx, rsp; StackCookie
0x180058b47  call    __security_check_cookie
0x180058b4c  add     rsp, 58h
0x180058b50  pop     r15
0x180058b52  pop     r14
0x180058b54  pop     rdi
0x180058b55  pop     rsi
0x180058b56  pop     rbp
0x180058b57  pop     rbx
0x180058b58  retn
```
