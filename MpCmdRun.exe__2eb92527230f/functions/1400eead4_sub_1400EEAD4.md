# sub_1400EEAD4

- ea: `0x1400eead4`
- end: `0x1400eed15`
- name: `sub_1400EEAD4`
- size: `577`
- prototype: ``
- caller_count: `9`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400952c0`
- `0x14009d70c`
- `0x1400b28c0`
- `0x1400b2fc8`
- `0x1400b35dc`
- `0x1400bb2d4`
- `0x1400bc374`
- `0x1400e2ec0`
- `0x1400ed304`

## callees

- `0x14000c0bc`
- `0x140012e84`
- `0x140036780`
- `0x140081450`
- `0x1400817ec`
- `0x140081848`
- `0x1400ed948`
- `0x1400eead4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400eece8`
- `KERNEL32!CloseHandle` at `0x1400eece8`
- `KERNEL32!SetFileInformationByHandle` at `0x1400eecaf`
- `KERNEL32!SetFileInformationByHandle` at `0x1400eecaf`
- `KERNEL32!GetFileInformationByHandle` at `0x1400eeb9d`
- `KERNEL32!GetFileInformationByHandle` at `0x1400eeb9d`

## pseudocode

```c
__int64 __fastcall sub_1400EEAD4(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  char dwFileAttributes; // al
  __int64 v10; // rdx
  __int64 v11; // rcx
  HANDLE hFile; // [rsp+48h] [rbp+7h] BYREF
  char v14[8]; // [rsp+50h] [rbp+Fh] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+58h] [rbp+17h] BYREF

  hFile = (HANDLE)-1LL;
  v2 = sub_14000C0BC(&hFile, a1, 0x10000000, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      sub_140081450(*((_QWORD *)off_14018DE50 + 2), 34, qword_140168FD8, (unsigned int)v2);
    return v3;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(hFile, &FileInformation) )
  {
    v6 = sub_140012E84(v5, v4);
    v3 = v6;
    v7 = off_14018DE50;
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
    {
      v8 = 35;
LABEL_9:
      sub_140081450(v7[2], v8, qword_140168FD8, v6);
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  dwFileAttributes = FileInformation.dwFileAttributes;
  if ( (FileInformation.dwFileAttributes & 0x400) == 0 )
  {
LABEL_19:
    if ( (dwFileAttributes & 0x10) != 0 )
    {
      v3 = -2147024560;
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
        sub_140081848(*((_QWORD *)off_14018DE50 + 2), 38, (unsigned int)qword_140168FD8, a1, 80);
      goto LABEL_28;
    }
    v14[0] = 1;
    if ( SetFileInformationByHandle(hFile, FileDispositionInfo, v14, 1u) )
    {
      v3 = 0;
    }
    else
    {
      v6 = sub_140012E84(v11, v10);
      v3 = v6;
      v7 = off_14018DE50;
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
      {
        v8 = 39;
        goto LABEL_9;
      }
    }
    goto LABEL_28;
  }
  if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 4) != 0 )
    sub_1400817EC(*((_QWORD *)off_14018DE50 + 2), 36, qword_140168FD8, a1);
  v6 = sub_1400ED948(hFile);
  v3 = v6;
  if ( !v6 )
  {
    dwFileAttributes = FileInformation.dwFileAttributes;
    goto LABEL_19;
  }
  v7 = off_14018DE50;
  if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
  {
    v8 = 37;
    goto LABEL_9;
  }
LABEL_28:
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
  return v3;
}

```

## disassembly

```asm
0x1400eead4  mov     r11, rsp
0x1400eead7  mov     [r11+10h], rbx
0x1400eeadb  mov     [r11+18h], rsi
0x1400eeadf  mov     [r11+20h], rdi
0x1400eeae3  push    rbp
0x1400eeae4  lea     rbp, [r11-5Fh]
0x1400eeae8  sub     rsp, 90h
0x1400eeaef  mov     rax, cs:__security_cookie
0x1400eeaf6  xor     rax, rsp
0x1400eeaf9  mov     [rbp+57h+var_8], rax
0x1400eeafd  mov     qword ptr [r11-60h], 0
0x1400eeb05  mov     rsi, rcx
0x1400eeb08  mov     qword ptr [r11-68h], 0
0x1400eeb10  mov     rdx, rcx
0x1400eeb13  mov     [rsp+90h+var_68], 2200000h
0x1400eeb1b  lea     rcx, [rbp+57h+hFile]
0x1400eeb1f  xor     r9d, r9d
0x1400eeb22  mov     [rsp+90h+var_70], 3
0x1400eeb2a  mov     r8d, 10000000h
0x1400eeb30  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x1400eeb38  call    sub_14000C0BC
0x1400eeb3d  mov     ebx, eax
0x1400eeb3f  test    eax, eax
0x1400eeb41  jns     short loc_1400EEB81
0x1400eeb43  mov     rcx, cs:off_14018DE50
0x1400eeb4a  lea     rdi, off_14018DE50
0x1400eeb51  cmp     rcx, rdi
0x1400eeb54  jz      loc_1400EECEE
0x1400eeb5a  test    byte ptr [rcx+1Ch], 1
0x1400eeb5e  jz      loc_1400EECEE
0x1400eeb64  mov     rcx, [rcx+10h]
0x1400eeb68  lea     r8, qword_140168FD8
0x1400eeb6f  mov     edx, 22h ; '"'
0x1400eeb74  mov     r9d, eax
0x1400eeb77  call    sub_140081450
0x1400eeb7c  jmp     loc_1400EECEE
0x1400eeb81  mov     rcx, [rbp+57h+hFile]; hFile
0x1400eeb85  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x1400eeb89  xorps   xmm0, xmm0
0x1400eeb8c  xor     eax, eax
0x1400eeb8e  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x1400eeb92  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1400eeb95  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1400eeb99  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x1400eeb9d  call    cs:GetFileInformationByHandle
0x1400eeba3  test    eax, eax
0x1400eeba5  jnz     short loc_1400EEBEC
0x1400eeba7  call    sub_140012E84
0x1400eebac  mov     ebx, eax
0x1400eebae  mov     rcx, cs:off_14018DE50
0x1400eebb5  lea     rdi, off_14018DE50
0x1400eebbc  cmp     rcx, rdi
0x1400eebbf  jz      loc_1400EECDE
0x1400eebc5  test    byte ptr [rcx+1Ch], 1
0x1400eebc9  jz      loc_1400EECDE
0x1400eebcf  mov     edx, 23h ; '#'
0x1400eebd4  mov     rcx, [rcx+10h]
0x1400eebd8  lea     r8, qword_140168FD8
0x1400eebdf  mov     r9d, eax
0x1400eebe2  call    sub_140081450
0x1400eebe7  jmp     loc_1400EECDE
0x1400eebec  mov     eax, [rbp+57h+FileInformation.dwFileAttributes]
0x1400eebef  lea     rdi, off_14018DE50
0x1400eebf6  bt      eax, 0Ah
0x1400eebfa  jnb     short loc_1400EEC5C
0x1400eebfc  mov     rcx, cs:off_14018DE50
0x1400eec03  cmp     rcx, rdi
0x1400eec06  jz      short loc_1400EEC26
0x1400eec08  test    byte ptr [rcx+1Ch], 4
0x1400eec0c  jz      short loc_1400EEC26
0x1400eec0e  mov     rcx, [rcx+10h]
0x1400eec12  lea     r8, qword_140168FD8
0x1400eec19  mov     edx, 24h ; '$'
0x1400eec1e  mov     r9, rsi
0x1400eec21  call    sub_1400817EC
0x1400eec26  mov     rcx, [rbp+57h+hFile]; hDevice
0x1400eec2a  call    sub_1400ED948
0x1400eec2f  mov     ebx, eax
0x1400eec31  test    eax, eax
0x1400eec33  jz      short loc_1400EEC59
0x1400eec35  mov     rcx, cs:off_14018DE50
0x1400eec3c  cmp     rcx, rdi
0x1400eec3f  jz      loc_1400EECDE
0x1400eec45  test    byte ptr [rcx+1Ch], 1
0x1400eec49  jz      loc_1400EECDE
0x1400eec4f  mov     edx, 25h ; '%'
0x1400eec54  jmp     loc_1400EEBD4
0x1400eec59  mov     eax, [rbp+57h+FileInformation.dwFileAttributes]
0x1400eec5c  test    al, 10h
0x1400eec5e  jz      short loc_1400EEC99
0x1400eec60  mov     ebx, 80070150h
0x1400eec65  mov     rcx, cs:off_14018DE50
0x1400eec6c  cmp     rcx, rdi
0x1400eec6f  jz      short loc_1400EECDE
0x1400eec71  test    byte ptr [rcx+1Ch], 1
0x1400eec75  jz      short loc_1400EECDE
0x1400eec77  mov     rcx, [rcx+10h]
0x1400eec7b  lea     r8, qword_140168FD8
0x1400eec82  mov     edx, 26h ; '&'
0x1400eec87  mov     [rsp+90h+var_70], 80070150h
0x1400eec8f  mov     r9, rsi
0x1400eec92  call    sub_140081848
0x1400eec97  jmp     short loc_1400EECDE
0x1400eec99  mov     rcx, [rbp+57h+hFile]; hFile
0x1400eec9d  lea     r8, [rbp+57h+var_48]; lpFileInformation
0x1400eeca1  mov     r9d, 1; dwBufferSize
0x1400eeca7  mov     [rbp+57h+var_48], 1
0x1400eecab  lea     edx, [r9+3]; FileInformationClass
0x1400eecaf  call    cs:SetFileInformationByHandle
0x1400eecb5  test    eax, eax
0x1400eecb7  jnz     short loc_1400EECDC
0x1400eecb9  call    sub_140012E84
0x1400eecbe  mov     ebx, eax
0x1400eecc0  mov     rcx, cs:off_14018DE50
0x1400eecc7  cmp     rcx, rdi
0x1400eecca  jz      short loc_1400EECDE
0x1400eeccc  test    byte ptr [rcx+1Ch], 1
0x1400eecd0  jz      short loc_1400EECDE
0x1400eecd2  mov     edx, 27h ; '''
0x1400eecd7  jmp     loc_1400EEBD4
0x1400eecdc  xor     ebx, ebx
0x1400eecde  mov     rcx, [rbp+57h+hFile]; hObject
0x1400eece2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400eece6  jz      short loc_1400EECEE
0x1400eece8  call    cs:__imp_CloseHandle
0x1400eecee  mov     eax, ebx
0x1400eecf0  mov     rcx, [rbp+57h+var_8]
0x1400eecf4  xor     rcx, rsp; StackCookie
0x1400eecf7  call    __security_check_cookie
0x1400eecfc  lea     r11, [rsp+90h+var_s0]
0x1400eed04  mov     rbx, [r11+18h]
0x1400eed08  mov     rsi, [r11+20h]
0x1400eed0c  mov     rdi, [r11+28h]
0x1400eed10  mov     rsp, r11
0x1400eed13  pop     rbp
0x1400eed14  retn
```
