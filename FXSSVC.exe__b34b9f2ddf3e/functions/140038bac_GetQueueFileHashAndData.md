# GetQueueFileHashAndData

- ea: `0x140038bac`
- end: `0x140038f8d`
- name: `GetQueueFileHashAndData`
- size: `993`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14003a558`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140038bac`
- `0x140065d14`
- `0x140065dbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140038c24`
- `KERNEL32!GetLastError` at `0x140038c7e`
- `KERNEL32!GetLastError` at `0x140038d74`
- `KERNEL32!GetLastError` at `0x140038e07`
- `KERNEL32!GetLastError` at `0x140038ec1`
- `KERNEL32!GetLastError` at `0x140038c24`
- `KERNEL32!GetLastError` at `0x140038c7e`
- `KERNEL32!GetLastError` at `0x140038d74`
- `KERNEL32!GetLastError` at `0x140038e07`
- `KERNEL32!GetLastError` at `0x140038ec1`
- `KERNEL32!GetFileSize` at `0x140038dfc`
- `KERNEL32!GetFileSize` at `0x140038dfc`
- `KERNEL32!ReadFile` at `0x140038c74`
- `KERNEL32!ReadFile` at `0x140038d6a`
- `KERNEL32!ReadFile` at `0x140038eb7`
- `KERNEL32!ReadFile` at `0x140038c74`
- `KERNEL32!ReadFile` at `0x140038d6a`
- `KERNEL32!ReadFile` at `0x140038eb7`
- `KERNEL32!SetFilePointer` at `0x140038c19`
- `KERNEL32!SetFilePointer` at `0x140038c19`

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
0x140038bac  push    rbp
0x140038bae  push    rbx
0x140038baf  push    rsi
0x140038bb0  push    rdi
0x140038bb1  push    r12
0x140038bb3  push    r13
0x140038bb5  push    r14
0x140038bb7  push    r15
0x140038bb9  mov     rbp, rsp
0x140038bbc  sub     rsp, 48h
0x140038bc0  xor     edi, edi
0x140038bc2  mov     r15, r9
0x140038bc5  mov     [rbp+Buffer], edi
0x140038bc8  xor     r14d, r14d
0x140038bcb  mov     [rbp+NumberOfBytesRead], edi
0x140038bce  mov     r12, r8
0x140038bd1  mov     r13, rdx
0x140038bd4  mov     rbx, rcx
0x140038bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140038bde  lea     rax, WPP_GLOBAL_Control
0x140038be5  lea     esi, [rdi+4]
0x140038be8  cmp     rcx, rax
0x140038beb  jz      short loc_140038C0E
0x140038bed  test    [rcx+1Ch], sil
0x140038bf1  jz      short loc_140038C0E
0x140038bf3  cmp     byte ptr [rcx+19h], 5
0x140038bf7  jb      short loc_140038C0E
0x140038bf9  mov     rcx, [rcx+10h]
0x140038bfd  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038c04  mov     edx, 139h
0x140038c09  call    WPP_SF_
0x140038c0e  xor     r9d, r9d; dwMoveMethod
0x140038c11  xor     r8d, r8d; lpDistanceToMoveHigh
0x140038c14  mov     edx, esi; lDistanceToMove
0x140038c16  mov     rcx, rbx; hFile
0x140038c19  call    cs:__imp_SetFilePointer
0x140038c1f  cmp     eax, 0FFFFFFFFh
0x140038c22  jnz     short loc_140038C61
0x140038c24  call    cs:__imp_GetLastError
0x140038c2a  mov     ebx, eax
0x140038c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038c33  lea     rax, WPP_GLOBAL_Control
0x140038c3a  cmp     rcx, rax
0x140038c3d  jz      loc_140038F00
0x140038c43  test    [rcx+1Ch], sil
0x140038c47  jz      loc_140038F00
0x140038c4d  cmp     byte ptr [rcx+19h], 2
0x140038c51  jb      loc_140038F00
0x140038c57  mov     edx, 13Ah
0x140038c5c  jmp     loc_140038EED
0x140038c61  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x140038c65  mov     [rsp+48h+lpOverlapped], rdi; lpOverlapped
0x140038c6a  mov     r8d, esi; nNumberOfBytesToRead
0x140038c6d  lea     rdx, [rbp+Buffer]; lpBuffer
0x140038c71  mov     rcx, rbx; hFile
0x140038c74  call    cs:__imp_ReadFile
0x140038c7a  test    eax, eax
0x140038c7c  jnz     short loc_140038CBB
0x140038c7e  call    cs:__imp_GetLastError
0x140038c84  mov     ebx, eax
0x140038c86  mov     rcx, cs:WPP_GLOBAL_Control
0x140038c8d  lea     rax, WPP_GLOBAL_Control
0x140038c94  cmp     rcx, rax
0x140038c97  jz      loc_140038F00
0x140038c9d  test    [rcx+1Ch], sil
0x140038ca1  jz      loc_140038F00
0x140038ca7  cmp     byte ptr [rcx+19h], 2
0x140038cab  jb      loc_140038F00
0x140038cb1  mov     edx, 13Bh
0x140038cb6  jmp     loc_140038EED
0x140038cbb  cmp     [rbp+NumberOfBytesRead], esi
0x140038cbe  jz      short loc_140038D0E
0x140038cc0  mov     r9d, 26h ; '&'
0x140038cc6  mov     ebx, r9d
0x140038cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140038cd0  lea     rax, WPP_GLOBAL_Control
0x140038cd7  cmp     rcx, rax
0x140038cda  jz      loc_140038F7A
0x140038ce0  test    [rcx+1Ch], sil
0x140038ce4  jz      loc_140038F7A
0x140038cea  cmp     byte ptr [rcx+19h], 2
0x140038cee  jb      loc_140038F7A
0x140038cf4  mov     edx, 13Ch
0x140038cf9  mov     rcx, [rcx+10h]
0x140038cfd  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038d04  call    WPP_SF_d
0x140038d09  jmp     loc_140038F7A
0x140038d0e  mov     ecx, [rbp+Buffer]; dwBytes
0x140038d11  call    pMemAlloc
0x140038d16  mov     rdi, rax
0x140038d19  test    rax, rax
0x140038d1c  jnz     short loc_140038D57
0x140038d1e  lea     ebx, [rax+8]
0x140038d21  mov     rcx, cs:WPP_GLOBAL_Control
0x140038d28  lea     rax, WPP_GLOBAL_Control
0x140038d2f  cmp     rcx, rax
0x140038d32  jz      loc_140038F7A
0x140038d38  test    [rcx+1Ch], sil
0x140038d3c  jz      loc_140038F7A
0x140038d42  cmp     byte ptr [rcx+19h], 2
0x140038d46  jb      loc_140038F7A
0x140038d4c  mov     r9d, [rbp+Buffer]
0x140038d50  mov     edx, 13Dh
0x140038d55  jmp     short loc_140038CF9
0x140038d57  mov     r8d, [rbp+Buffer]; nNumberOfBytesToRead
0x140038d5b  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x140038d5f  mov     rdx, rdi; lpBuffer
0x140038d62  mov     [rsp+48h+lpOverlapped], r14; lpOverlapped
0x140038d67  mov     rcx, rbx; hFile
0x140038d6a  call    cs:__imp_ReadFile
0x140038d70  test    eax, eax
0x140038d72  jnz     short loc_140038DB1
0x140038d74  call    cs:__imp_GetLastError
0x140038d7a  mov     ebx, eax
0x140038d7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038d83  lea     rax, WPP_GLOBAL_Control
0x140038d8a  cmp     rcx, rax
0x140038d8d  jz      loc_140038F00
0x140038d93  test    [rcx+1Ch], sil
0x140038d97  jz      loc_140038F00
0x140038d9d  cmp     byte ptr [rcx+19h], 2
0x140038da1  jb      loc_140038F00
0x140038da7  mov     edx, 13Eh
0x140038dac  jmp     loc_140038EED
0x140038db1  mov     eax, [rbp+NumberOfBytesRead]
0x140038db4  cmp     [rbp+Buffer], eax
0x140038db7  jz      short loc_140038DF7
0x140038db9  mov     r9d, 26h ; '&'
0x140038dbf  mov     ebx, r9d
0x140038dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140038dc9  lea     rax, WPP_GLOBAL_Control
0x140038dd0  cmp     rcx, rax
0x140038dd3  jz      loc_140038F4D
0x140038dd9  test    [rcx+1Ch], sil
0x140038ddd  jz      loc_140038F4D
0x140038de3  cmp     byte ptr [rcx+19h], 2
0x140038de7  jb      loc_140038F4D
0x140038ded  mov     edx, 13Fh
0x140038df2  jmp     loc_140038F3D
0x140038df7  xor     edx, edx; lpFileSizeHigh
0x140038df9  mov     rcx, rbx; hFile
0x140038dfc  call    cs:__imp_GetFileSize
0x140038e02  cmp     eax, 0FFFFFFFFh
0x140038e05  jnz     short loc_140038E44
0x140038e07  call    cs:__imp_GetLastError
0x140038e0d  mov     ebx, eax
0x140038e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140038e16  lea     rax, WPP_GLOBAL_Control
0x140038e1d  cmp     rcx, rax
0x140038e20  jz      loc_140038F00
0x140038e26  test    [rcx+1Ch], sil
0x140038e2a  jz      loc_140038F00
0x140038e30  cmp     byte ptr [rcx+19h], 2
0x140038e34  jb      loc_140038F00
0x140038e3a  mov     edx, 140h
0x140038e3f  jmp     loc_140038EED
0x140038e44  sub     eax, [rbp+Buffer]
0x140038e47  lea     esi, [rax-8]
0x140038e4a  mov     ecx, esi; dwBytes
0x140038e4c  call    pMemAlloc
0x140038e51  mov     r14, rax
0x140038e54  test    rax, rax
0x140038e57  jnz     short loc_140038EA1
0x140038e59  lea     ebx, [rax+8]
0x140038e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038e63  lea     rax, WPP_GLOBAL_Control
0x140038e6a  cmp     rcx, rax
0x140038e6d  jz      loc_140038F4D
0x140038e73  test    byte ptr [rcx+1Ch], 4
0x140038e77  jz      loc_140038F4D
0x140038e7d  cmp     byte ptr [rcx+19h], 2
0x140038e81  jb      loc_140038F4D
0x140038e87  mov     rcx, [rcx+10h]
0x140038e8b  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038e92  mov     edx, 141h
0x140038e97  call    WPP_SF_
0x140038e9c  jmp     loc_140038F4D
0x140038ea1  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x140038ea5  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x140038eae  mov     r8d, esi; nNumberOfBytesToRead
0x140038eb1  mov     rdx, r14; lpBuffer
0x140038eb4  mov     rcx, rbx; hFile
0x140038eb7  call    cs:__imp_ReadFile
0x140038ebd  test    eax, eax
0x140038ebf  jnz     short loc_140038F0B
0x140038ec1  call    cs:__imp_GetLastError
0x140038ec7  mov     ebx, eax
0x140038ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x140038ed0  lea     rax, WPP_GLOBAL_Control
0x140038ed7  cmp     rcx, rax
0x140038eda  jz      short loc_140038F00
0x140038edc  test    byte ptr [rcx+1Ch], 4
0x140038ee0  jz      short loc_140038F00
0x140038ee2  cmp     byte ptr [rcx+19h], 2
0x140038ee6  jb      short loc_140038F00
0x140038ee8  mov     edx, 142h
0x140038eed  mov     rcx, [rcx+10h]
0x140038ef1  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038ef8  mov     r9d, ebx
0x140038efb  call    WPP_SF_d
0x140038f00  test    ebx, ebx
0x140038f02  jz      short loc_140038F7A
0x140038f04  test    rdi, rdi
0x140038f07  jz      short loc_140038F55
0x140038f09  jmp     short loc_140038F4D
0x140038f0b  cmp     esi, [rbp+NumberOfBytesRead]
0x140038f0e  jz      short loc_140038F64
0x140038f10  mov     r9d, 26h ; '&'
0x140038f16  mov     ebx, r9d
0x140038f19  mov     rcx, cs:WPP_GLOBAL_Control
0x140038f20  lea     rax, WPP_GLOBAL_Control
0x140038f27  cmp     rcx, rax
0x140038f2a  jz      short loc_140038F4D
0x140038f2c  test    byte ptr [rcx+1Ch], 4
0x140038f30  jz      short loc_140038F4D
0x140038f32  cmp     byte ptr [rcx+19h], 2
0x140038f36  jb      short loc_140038F4D
0x140038f38  mov     edx, 143h
0x140038f3d  mov     rcx, [rcx+10h]
0x140038f41  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038f48  call    WPP_SF_d
0x140038f4d  mov     rcx, rdi; lpMem
0x140038f50  call    pMemFree
0x140038f55  test    r14, r14
0x140038f58  jz      short loc_140038F7A
0x140038f5a  mov     rcx, r14; lpMem
0x140038f5d  call    pMemFree
0x140038f62  jmp     short loc_140038F7A
0x140038f64  mov     eax, [rbp+Buffer]
0x140038f67  xor     ebx, ebx
0x140038f69  mov     [r12], eax
0x140038f6d  mov     rax, [rbp+arg_20]
0x140038f71  mov     [r13+0], rdi
0x140038f75  mov     [r15], r14
0x140038f78  mov     [rax], esi
0x140038f7a  mov     eax, ebx
0x140038f7c  add     rsp, 48h
0x140038f80  pop     r15
0x140038f82  pop     r14
0x140038f84  pop     r13
0x140038f86  pop     r12
0x140038f88  pop     rdi
0x140038f89  pop     rsi
0x140038f8a  pop     rbx
0x140038f8b  pop     rbp
0x140038f8c  retn
```
