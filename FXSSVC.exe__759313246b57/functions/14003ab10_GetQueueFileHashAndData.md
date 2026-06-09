# GetQueueFileHashAndData

- ea: `0x14003ab10`
- end: `0x14003af2e`
- name: `GetQueueFileHashAndData`
- size: `1054`
- prototype: `__int64 __fastcall(HANDLE hFile, _QWORD *, _DWORD *, _QWORD *, DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14003c638`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14003ab10`
- `0x1400698ec`
- `0x14006998c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003ab8e`
- `KERNEL32!GetLastError` at `0x14003abf4`
- `KERNEL32!GetLastError` at `0x14003acf6`
- `KERNEL32!GetLastError` at `0x14003ad95`
- `KERNEL32!GetLastError` at `0x14003ae5b`
- `KERNEL32!GetLastError` at `0x14003ab8e`
- `KERNEL32!GetLastError` at `0x14003abf4`
- `KERNEL32!GetLastError` at `0x14003acf6`
- `KERNEL32!GetLastError` at `0x14003ad95`
- `KERNEL32!GetLastError` at `0x14003ae5b`
- `KERNEL32!GetFileSize` at `0x14003ad84`
- `KERNEL32!GetFileSize` at `0x14003ad84`
- `KERNEL32!ReadFile` at `0x14003abe4`
- `KERNEL32!ReadFile` at `0x14003ace6`
- `KERNEL32!ReadFile` at `0x14003ae4b`
- `KERNEL32!ReadFile` at `0x14003abe4`
- `KERNEL32!ReadFile` at `0x14003ace6`
- `KERNEL32!ReadFile` at `0x14003ae4b`
- `KERNEL32!SetFilePointer` at `0x14003ab7d`
- `KERNEL32!SetFilePointer` at `0x14003ab7d`

## pseudocode

```c
__int64 __fastcall GetQueueFileHashAndData(HANDLE hFile, _QWORD *a2, _DWORD *a3, _QWORD *a4, DWORD *a5)
{
  void *v5; // rdi
  void *v7; // r14
  DWORD LastError; // ebx
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  void *v17; // rax
  CMapDeviceId *v18; // rcx
  __int64 v19; // rdx
  DWORD FileSize; // eax
  DWORD v21; // esi
  void *v22; // rax
  DWORD Buffer; // [rsp+30h] [rbp-18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+34h] [rbp-14h] BYREF

  v5 = 0;
  Buffer = 0;
  v7 = 0;
  NumberOfBytesRead = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  if ( SetFilePointer(hFile, 4, 0, 0) == -1 )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 314;
LABEL_51:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
      goto LABEL_52;
    }
    goto LABEL_52;
  }
  if ( !ReadFile(hFile, &Buffer, 4u, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 315;
      goto LABEL_51;
    }
LABEL_52:
    if ( !LastError )
      return LastError;
    if ( !v5 )
      goto LABEL_62;
    goto LABEL_61;
  }
  if ( NumberOfBytesRead != 4 )
  {
    v14 = 38;
    LastError = 38;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v16 = 316;
    goto LABEL_20;
  }
  v17 = (void *)pMemAlloc(Buffer);
  v5 = v17;
  if ( !v17 )
  {
    LastError = 8;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v14 = Buffer;
    v16 = 317;
LABEL_20:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v14);
    return LastError;
  }
  if ( !ReadFile(hFile, v17, Buffer, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 318;
      goto LABEL_51;
    }
    goto LABEL_52;
  }
  if ( Buffer != NumberOfBytesRead )
  {
    LastError = 38;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_61;
    }
    v19 = 319;
    goto LABEL_60;
  }
  FileSize = GetFileSize(hFile, 0);
  if ( FileSize == -1 )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 320;
      goto LABEL_51;
    }
    goto LABEL_52;
  }
  v21 = FileSize - Buffer - 8;
  v22 = (void *)pMemAlloc(v21);
  v7 = v22;
  if ( !v22 )
  {
    LastError = 8;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
    }
    goto LABEL_61;
  }
  if ( !ReadFile(hFile, v22, v21, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 322;
      goto LABEL_51;
    }
    goto LABEL_52;
  }
  if ( v21 == NumberOfBytesRead )
  {
    LastError = 0;
    *a3 = Buffer;
    *a2 = v5;
    *a4 = v7;
    *a5 = v21;
    return LastError;
  }
  LastError = 38;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = 323;
LABEL_60:
    WPP_SF_d(*((_QWORD *)v18 + 2), v19, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, 38);
  }
LABEL_61:
  pMemFree(v5);
LABEL_62:
  if ( v7 )
    pMemFree(v7);
  return LastError;
}

```

## disassembly

```asm
0x14003ab10  push    rbp
0x14003ab12  push    rbx
0x14003ab13  push    rsi
0x14003ab14  push    rdi
0x14003ab15  push    r12
0x14003ab17  push    r13
0x14003ab19  push    r14
0x14003ab1b  push    r15
0x14003ab1d  mov     rbp, rsp
0x14003ab20  sub     rsp, 48h
0x14003ab24  xor     edi, edi
0x14003ab26  mov     r15, r9
0x14003ab29  mov     [rbp+Buffer], edi
0x14003ab2c  xor     r14d, r14d
0x14003ab2f  mov     [rbp+NumberOfBytesRead], edi
0x14003ab32  mov     r12, r8
0x14003ab35  mov     r13, rdx
0x14003ab38  mov     rbx, rcx
0x14003ab3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab42  lea     rax, WPP_GLOBAL_Control
0x14003ab49  lea     esi, [rdi+4]
0x14003ab4c  cmp     rcx, rax
0x14003ab4f  jz      short loc_14003AB72
0x14003ab51  test    [rcx+1Ch], sil
0x14003ab55  jz      short loc_14003AB72
0x14003ab57  cmp     byte ptr [rcx+19h], 5
0x14003ab5b  jb      short loc_14003AB72
0x14003ab5d  mov     rcx, [rcx+10h]
0x14003ab61  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003ab68  mov     edx, 139h
0x14003ab6d  call    WPP_SF_
0x14003ab72  xor     r9d, r9d; dwMoveMethod
0x14003ab75  xor     r8d, r8d; lpDistanceToMoveHigh
0x14003ab78  mov     edx, esi; lDistanceToMove
0x14003ab7a  mov     rcx, rbx; hFile
0x14003ab7d  call    cs:__imp_SetFilePointer
0x14003ab84  nop     dword ptr [rax+rax+00h]
0x14003ab89  cmp     eax, 0FFFFFFFFh
0x14003ab8c  jnz     short loc_14003ABD1
0x14003ab8e  call    cs:__imp_GetLastError
0x14003ab95  nop     dword ptr [rax+rax+00h]
0x14003ab9a  mov     ebx, eax
0x14003ab9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aba3  lea     rax, WPP_GLOBAL_Control
0x14003abaa  cmp     rcx, rax
0x14003abad  jz      loc_14003AEA0
0x14003abb3  test    [rcx+1Ch], sil
0x14003abb7  jz      loc_14003AEA0
0x14003abbd  cmp     byte ptr [rcx+19h], 2
0x14003abc1  jb      loc_14003AEA0
0x14003abc7  mov     edx, 13Ah
0x14003abcc  jmp     loc_14003AE8D
0x14003abd1  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x14003abd5  mov     [rsp+48h+lpOverlapped], rdi; lpOverlapped
0x14003abda  mov     r8d, esi; nNumberOfBytesToRead
0x14003abdd  lea     rdx, [rbp+Buffer]; lpBuffer
0x14003abe1  mov     rcx, rbx; hFile
0x14003abe4  call    cs:__imp_ReadFile
0x14003abeb  nop     dword ptr [rax+rax+00h]
0x14003abf0  test    eax, eax
0x14003abf2  jnz     short loc_14003AC37
0x14003abf4  call    cs:__imp_GetLastError
0x14003abfb  nop     dword ptr [rax+rax+00h]
0x14003ac00  mov     ebx, eax
0x14003ac02  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac09  lea     rax, WPP_GLOBAL_Control
0x14003ac10  cmp     rcx, rax
0x14003ac13  jz      loc_14003AEA0
0x14003ac19  test    [rcx+1Ch], sil
0x14003ac1d  jz      loc_14003AEA0
0x14003ac23  cmp     byte ptr [rcx+19h], 2
0x14003ac27  jb      loc_14003AEA0
0x14003ac2d  mov     edx, 13Bh
0x14003ac32  jmp     loc_14003AE8D
0x14003ac37  cmp     [rbp+NumberOfBytesRead], esi
0x14003ac3a  jz      short loc_14003AC8A
0x14003ac3c  mov     r9d, 26h ; '&'
0x14003ac42  mov     ebx, r9d
0x14003ac45  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac4c  lea     rax, WPP_GLOBAL_Control
0x14003ac53  cmp     rcx, rax
0x14003ac56  jz      loc_14003AF1A
0x14003ac5c  test    [rcx+1Ch], sil
0x14003ac60  jz      loc_14003AF1A
0x14003ac66  cmp     byte ptr [rcx+19h], 2
0x14003ac6a  jb      loc_14003AF1A
0x14003ac70  mov     edx, 13Ch
0x14003ac75  mov     rcx, [rcx+10h]
0x14003ac79  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003ac80  call    WPP_SF_d
0x14003ac85  jmp     loc_14003AF1A
0x14003ac8a  mov     ecx, [rbp+Buffer]; dwBytes
0x14003ac8d  call    pMemAlloc
0x14003ac92  mov     rdi, rax
0x14003ac95  test    rax, rax
0x14003ac98  jnz     short loc_14003ACD3
0x14003ac9a  lea     ebx, [rax+8]
0x14003ac9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aca4  lea     rax, WPP_GLOBAL_Control
0x14003acab  cmp     rcx, rax
0x14003acae  jz      loc_14003AF1A
0x14003acb4  test    [rcx+1Ch], sil
0x14003acb8  jz      loc_14003AF1A
0x14003acbe  cmp     byte ptr [rcx+19h], 2
0x14003acc2  jb      loc_14003AF1A
0x14003acc8  mov     r9d, [rbp+Buffer]
0x14003accc  mov     edx, 13Dh
0x14003acd1  jmp     short loc_14003AC75
0x14003acd3  mov     r8d, [rbp+Buffer]; nNumberOfBytesToRead
0x14003acd7  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x14003acdb  mov     rdx, rdi; lpBuffer
0x14003acde  mov     [rsp+48h+lpOverlapped], r14; lpOverlapped
0x14003ace3  mov     rcx, rbx; hFile
0x14003ace6  call    cs:__imp_ReadFile
0x14003aced  nop     dword ptr [rax+rax+00h]
0x14003acf2  test    eax, eax
0x14003acf4  jnz     short loc_14003AD39
0x14003acf6  call    cs:__imp_GetLastError
0x14003acfd  nop     dword ptr [rax+rax+00h]
0x14003ad02  mov     ebx, eax
0x14003ad04  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ad0b  lea     rax, WPP_GLOBAL_Control
0x14003ad12  cmp     rcx, rax
0x14003ad15  jz      loc_14003AEA0
0x14003ad1b  test    [rcx+1Ch], sil
0x14003ad1f  jz      loc_14003AEA0
0x14003ad25  cmp     byte ptr [rcx+19h], 2
0x14003ad29  jb      loc_14003AEA0
0x14003ad2f  mov     edx, 13Eh
0x14003ad34  jmp     loc_14003AE8D
0x14003ad39  mov     eax, [rbp+NumberOfBytesRead]
0x14003ad3c  cmp     [rbp+Buffer], eax
0x14003ad3f  jz      short loc_14003AD7F
0x14003ad41  mov     r9d, 26h ; '&'
0x14003ad47  mov     ebx, r9d
0x14003ad4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ad51  lea     rax, WPP_GLOBAL_Control
0x14003ad58  cmp     rcx, rax
0x14003ad5b  jz      loc_14003AEED
0x14003ad61  test    [rcx+1Ch], sil
0x14003ad65  jz      loc_14003AEED
0x14003ad6b  cmp     byte ptr [rcx+19h], 2
0x14003ad6f  jb      loc_14003AEED
0x14003ad75  mov     edx, 13Fh
0x14003ad7a  jmp     loc_14003AEDD
0x14003ad7f  xor     edx, edx; lpFileSizeHigh
0x14003ad81  mov     rcx, rbx; hFile
0x14003ad84  call    cs:__imp_GetFileSize
0x14003ad8b  nop     dword ptr [rax+rax+00h]
0x14003ad90  cmp     eax, 0FFFFFFFFh
0x14003ad93  jnz     short loc_14003ADD8
0x14003ad95  call    cs:__imp_GetLastError
0x14003ad9c  nop     dword ptr [rax+rax+00h]
0x14003ada1  mov     ebx, eax
0x14003ada3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003adaa  lea     rax, WPP_GLOBAL_Control
0x14003adb1  cmp     rcx, rax
0x14003adb4  jz      loc_14003AEA0
0x14003adba  test    [rcx+1Ch], sil
0x14003adbe  jz      loc_14003AEA0
0x14003adc4  cmp     byte ptr [rcx+19h], 2
0x14003adc8  jb      loc_14003AEA0
0x14003adce  mov     edx, 140h
0x14003add3  jmp     loc_14003AE8D
0x14003add8  sub     eax, [rbp+Buffer]
0x14003addb  lea     esi, [rax-8]
0x14003adde  mov     ecx, esi; dwBytes
0x14003ade0  call    pMemAlloc
0x14003ade5  mov     r14, rax
0x14003ade8  test    rax, rax
0x14003adeb  jnz     short loc_14003AE35
0x14003aded  lea     ebx, [rax+8]
0x14003adf0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003adf7  lea     rax, WPP_GLOBAL_Control
0x14003adfe  cmp     rcx, rax
0x14003ae01  jz      loc_14003AEED
0x14003ae07  test    byte ptr [rcx+1Ch], 4
0x14003ae0b  jz      loc_14003AEED
0x14003ae11  cmp     byte ptr [rcx+19h], 2
0x14003ae15  jb      loc_14003AEED
0x14003ae1b  mov     rcx, [rcx+10h]
0x14003ae1f  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003ae26  mov     edx, 141h
0x14003ae2b  call    WPP_SF_
0x14003ae30  jmp     loc_14003AEED
0x14003ae35  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x14003ae39  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x14003ae42  mov     r8d, esi; nNumberOfBytesToRead
0x14003ae45  mov     rdx, r14; lpBuffer
0x14003ae48  mov     rcx, rbx; hFile
0x14003ae4b  call    cs:__imp_ReadFile
0x14003ae52  nop     dword ptr [rax+rax+00h]
0x14003ae57  test    eax, eax
0x14003ae59  jnz     short loc_14003AEAB
0x14003ae5b  call    cs:__imp_GetLastError
0x14003ae62  nop     dword ptr [rax+rax+00h]
0x14003ae67  mov     ebx, eax
0x14003ae69  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ae70  lea     rax, WPP_GLOBAL_Control
0x14003ae77  cmp     rcx, rax
0x14003ae7a  jz      short loc_14003AEA0
0x14003ae7c  test    byte ptr [rcx+1Ch], 4
0x14003ae80  jz      short loc_14003AEA0
0x14003ae82  cmp     byte ptr [rcx+19h], 2
0x14003ae86  jb      short loc_14003AEA0
0x14003ae88  mov     edx, 142h
0x14003ae8d  mov     rcx, [rcx+10h]
0x14003ae91  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003ae98  mov     r9d, ebx
0x14003ae9b  call    WPP_SF_d
0x14003aea0  test    ebx, ebx
0x14003aea2  jz      short loc_14003AF1A
0x14003aea4  test    rdi, rdi
0x14003aea7  jz      short loc_14003AEF5
0x14003aea9  jmp     short loc_14003AEED
0x14003aeab  cmp     esi, [rbp+NumberOfBytesRead]
0x14003aeae  jz      short loc_14003AF04
0x14003aeb0  mov     r9d, 26h ; '&'
0x14003aeb6  mov     ebx, r9d
0x14003aeb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aec0  lea     rax, WPP_GLOBAL_Control
0x14003aec7  cmp     rcx, rax
0x14003aeca  jz      short loc_14003AEED
0x14003aecc  test    byte ptr [rcx+1Ch], 4
0x14003aed0  jz      short loc_14003AEED
0x14003aed2  cmp     byte ptr [rcx+19h], 2
0x14003aed6  jb      short loc_14003AEED
0x14003aed8  mov     edx, 143h
0x14003aedd  mov     rcx, [rcx+10h]
0x14003aee1  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003aee8  call    WPP_SF_d
0x14003aeed  mov     rcx, rdi; lpMem
0x14003aef0  call    pMemFree
0x14003aef5  test    r14, r14
0x14003aef8  jz      short loc_14003AF1A
0x14003aefa  mov     rcx, r14; lpMem
0x14003aefd  call    pMemFree
0x14003af02  jmp     short loc_14003AF1A
0x14003af04  mov     eax, [rbp+Buffer]
0x14003af07  xor     ebx, ebx
0x14003af09  mov     [r12], eax
0x14003af0d  mov     rax, [rbp+arg_20]
0x14003af11  mov     [r13+0], rdi
0x14003af15  mov     [r15], r14
0x14003af18  mov     [rax], esi
0x14003af1a  mov     eax, ebx
0x14003af1c  add     rsp, 48h
0x14003af20  pop     r15
0x14003af22  pop     r14
0x14003af24  pop     r13
0x14003af26  pop     r12
0x14003af28  pop     rdi
0x14003af29  pop     rsi
0x14003af2a  pop     rbx
0x14003af2b  pop     rbp
0x14003af2c  retn
```
