# CDiskIO::ReadSectorsFromDevice(void *,CDisk *,__int64,ulong,uchar *,ulong)

- ea: `0x1800585d0`
- end: `0x18005875e`
- name: `?ReadSectorsFromDevice@CDiskIO@@SAKPEAXPEAVCDisk@@_JKPEAEK@Z`
- size: `398`
- prototype: `unsigned int __usercall@<eax>(HANDLE hFile@<rcx>, struct CDisk *@<rdx>, __int64@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned int)`
- caller_count: `8`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180055c80`
- `0x180055e9c`
- `0x180056080`
- `0x180057430`
- `0x180057668`
- `0x180057b94`
- `0x180057de8`
- `0x180058764`

## callees

- `0x18004f8d0`
- `0x1800585d0`
- `0x180058b60`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18005867a`
- `KERNEL32!SetFilePointer` at `0x18005867a`
- `KERNEL32!GetLastError` at `0x180058680`
- `KERNEL32!GetLastError` at `0x1800586f5`
- `KERNEL32!GetLastError` at `0x180058680`
- `KERNEL32!GetLastError` at `0x1800586f5`
- `KERNEL32!ReadFile` at `0x1800586eb`
- `KERNEL32!ReadFile` at `0x1800586eb`
- `KERNEL32!SetLastError` at `0x180058665`
- `KERNEL32!SetLastError` at `0x180058665`

## pseudocode

```c
__int64 __fastcall CDiskIO::ReadSectorsFromDevice(
        HANDLE hFile,
        struct CDisk *a2,
        signed __int64 a3,
        unsigned int a4,
        unsigned __int8 *lpBuffer,
        DWORD a6)
{
  unsigned int v7; // ebx
  __int64 v9; // rdx
  signed __int64 v10; // rcx
  DWORD LastError; // edi
  __int64 v12; // rax
  __int64 v13; // r8
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-58h] BYREF
  LONG DistanceToMoveHigh[2]; // [rsp+38h] [rbp-50h] BYREF

  v7 = a4;
  NumberOfBytesRead = 0;
  if ( !lpBuffer )
    return 87;
  if ( !a2 )
    return 87;
  v9 = *((_QWORD *)a2 + 1);
  if ( a6 < *(_DWORD *)(v9 + 20) * a4 )
    return 87;
  v10 = *((_QWORD *)a2 + 136);
  if ( a3 >= v10 )
    return 87;
  if ( a3 + a4 > v10 )
    v7 = v10 - a3;
  *(_QWORD *)DistanceToMoveHigh = 0;
  *(_QWORD *)DistanceToMoveHigh = a3 * *(unsigned int *)(v9 + 20);
  SetLastError(0);
  SetFilePointer(hFile, DistanceToMoveHigh[0], &DistanceToMoveHigh[1], 0);
  LastError = GetLastError();
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_70e883ff648235bf9018dbd80de8c80b_Traceguids, LastError);
  }
  else
  {
    v12 = *((_QWORD *)a2 + 1);
    NumberOfBytesRead = a6;
    if ( !ReadFile(hFile, lpBuffer, *(_DWORD *)(v12 + 20) * v7, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_ddD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          v13,
          *(_DWORD *)(*((_QWORD *)a2 + 1) + 20LL) * v7,
          NumberOfBytesRead,
          LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800585d0  push    rbx
0x1800585d2  push    rbp
0x1800585d3  push    rsi
0x1800585d4  push    rdi
0x1800585d5  push    r14
0x1800585d7  push    r15
0x1800585d9  sub     rsp, 58h
0x1800585dd  mov     rax, cs:__security_cookie
0x1800585e4  xor     rax, rsp
0x1800585e7  mov     [rsp+88h+var_48], rax
0x1800585ec  mov     r15, [rsp+88h+lpBuffer]
0x1800585f4  mov     rsi, rdx
0x1800585f7  mov     ebx, r9d
0x1800585fa  mov     r14, rcx
0x1800585fd  mov     [rsp+88h+NumberOfBytesRead], 0
0x180058605  test    r15, r15
0x180058608  jz      loc_18005873F
0x18005860e  test    rdx, rdx
0x180058611  jz      loc_18005873F
0x180058617  mov     rdx, [rdx+8]
0x18005861b  mov     eax, ebx
0x18005861d  mov     ebp, [rsp+88h+arg_28]
0x180058624  imul    eax, [rdx+14h]
0x180058628  cmp     ebp, eax
0x18005862a  jb      loc_18005873F
0x180058630  mov     rcx, [rsi+440h]
0x180058637  cmp     r8, rcx
0x18005863a  jge     loc_18005873F
0x180058640  lea     rax, [r8+rbx]
0x180058644  cmp     rax, rcx
0x180058647  jle     short loc_18005864E
0x180058649  mov     ebx, ecx
0x18005864b  sub     ebx, r8d
0x18005864e  mov     qword ptr [rsp+88h+DistanceToMoveHigh], 0
0x180058657  xor     ecx, ecx; dwErrCode
0x180058659  mov     eax, [rdx+14h]
0x18005865c  imul    rax, r8
0x180058660  mov     qword ptr [rsp+88h+DistanceToMoveHigh], rax
0x180058665  call    cs:__imp_SetLastError
0x18005866b  mov     edx, [rsp+88h+DistanceToMoveHigh]; lDistanceToMove
0x18005866f  lea     r8, [rsp+88h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x180058674  xor     r9d, r9d; dwMoveMethod
0x180058677  mov     rcx, r14; hFile
0x18005867a  call    cs:__imp_SetFilePointer
0x180058680  call    cs:__imp_GetLastError
0x180058686  mov     edi, eax
0x180058688  test    eax, eax
0x18005868a  jz      short loc_1800586C7
0x18005868c  mov     rcx, cs:WPP_GLOBAL_Control
0x180058693  lea     rax, WPP_GLOBAL_Control
0x18005869a  cmp     rcx, rax
0x18005869d  jz      loc_18005873B
0x1800586a3  test    byte ptr [rcx+1Ch], 2
0x1800586a7  jz      loc_18005873B
0x1800586ad  mov     rcx, [rcx+10h]
0x1800586b1  lea     r8, WPP_70e883ff648235bf9018dbd80de8c80b_Traceguids
0x1800586b8  mov     edx, 0Ch
0x1800586bd  mov     r9d, edi
0x1800586c0  call    WPP_SF_d
0x1800586c5  jmp     short loc_18005873B
0x1800586c7  mov     rax, [rsi+8]
0x1800586cb  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800586d0  mov     r8d, ebx
0x1800586d3  mov     [rsp+88h+NumberOfBytesRead], ebp
0x1800586d7  mov     rdx, r15; lpBuffer
0x1800586da  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x1800586e3  mov     rcx, r14; hFile
0x1800586e6  imul    r8d, [rax+14h]; nNumberOfBytesToRead
0x1800586eb  call    cs:__imp_ReadFile
0x1800586f1  test    eax, eax
0x1800586f3  jnz     short loc_18005873B
0x1800586f5  call    cs:__imp_GetLastError
0x1800586fb  mov     edi, eax
0x1800586fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180058704  lea     rax, WPP_GLOBAL_Control
0x18005870b  cmp     rcx, rax
0x18005870e  jz      short loc_18005873B
0x180058710  test    byte ptr [rcx+1Ch], 2
0x180058714  jz      short loc_18005873B
0x180058716  mov     rax, [rsi+8]
0x18005871a  mov     edx, 0Dh
0x18005871f  mov     rcx, [rcx+10h]
0x180058723  mov     [rsp+88h+var_60], edi
0x180058727  imul    ebx, [rax+14h]
0x18005872b  mov     eax, [rsp+88h+NumberOfBytesRead]
0x18005872f  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x180058733  mov     r9d, ebx
0x180058736  call    WPP_SF_ddD
0x18005873b  mov     eax, edi
0x18005873d  jmp     short loc_180058744
0x18005873f  mov     eax, 57h ; 'W'
0x180058744  mov     rcx, [rsp+88h+var_48]
0x180058749  xor     rcx, rsp; StackCookie
0x18005874c  call    __security_check_cookie
0x180058751  add     rsp, 58h
0x180058755  pop     r15
0x180058757  pop     r14
0x180058759  pop     rdi
0x18005875a  pop     rsi
0x18005875b  pop     rbp
0x18005875c  pop     rbx
0x18005875d  retn
```
