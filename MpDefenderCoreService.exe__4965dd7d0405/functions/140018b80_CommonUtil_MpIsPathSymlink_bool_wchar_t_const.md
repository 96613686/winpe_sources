# CommonUtil::MpIsPathSymlink(bool &,wchar_t const *)

- ea: `0x140018b80`
- end: `0x140018db9`
- name: `?MpIsPathSymlink@CommonUtil@@YAJAEA_NPEB_W@Z`
- size: `569`
- prototype: `int(CommonUtil *__hidden this, bool *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140018440`

## callees

- `0x140017738`
- `0x140018b80`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d210`
- `0x1400f45a4`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x140018c7f`
- `KERNEL32!DeviceIoControl` at `0x140018c7f`
- `KERNEL32!GetFileAttributesW` at `0x140018bb3`
- `KERNEL32!GetFileAttributesW` at `0x140018bb3`
- `KERNEL32!CreateFileW` at `0x140018bf8`
- `KERNEL32!CreateFileW` at `0x140018bf8`
- `KERNEL32!CloseHandle` at `0x140018d51`
- `KERNEL32!CloseHandle` at `0x140018d51`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpIsPathSymlink(CommonUtil *this, const WCHAR *a2, const wchar_t *a3)
{
  unsigned int v5; // edi
  DWORD FileAttributesW; // eax
  const struct std::nothrow_t *v7; // rdx
  HANDLE FileW; // r15
  _DWORD *v9; // rbx
  unsigned int v10; // ebp
  DWORD v11; // r14d
  int v12; // eax
  unsigned int LastFailure; // eax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned int v17; // eax
  LPVOID lpOutBuffer; // [rsp+40h] [rbp-48h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-40h] BYREF

  *(_BYTE *)this = 0;
  v5 = 0;
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW == -1 )
    return (unsigned int)HrGetLastFailure();
  if ( (FileAttributesW & 0x400) == 0 )
    return v5;
  FileW = CreateFileW(a2, 0x80u, 1u, 0, 3u, 0x2200000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v9 = 0;
    lpOutBuffer = 0;
    v10 = 0;
    BytesReturned = 0;
    v11 = 24;
    while ( 1 )
    {
      if ( v9 )
      {
        operator delete(v9, v7);
        lpOutBuffer = 0;
      }
      v12 = CommonUtil::MpNewBuffer<unsigned char>(&lpOutBuffer, v11);
      v9 = lpOutBuffer;
      v5 = v12;
      if ( v12 < 0 )
        break;
      if ( !DeviceIoControl(FileW, 0x900A8u, 0, 0, lpOutBuffer, v11, &BytesReturned, 0) )
      {
        LastFailure = HrGetLastFailure();
        v5 = LastFailure;
        if ( LastFailure == -2147024774 || LastFailure == -2147024662 )
        {
          ++v10;
          v11 = 0x4000;
          if ( v10 <= 1 )
            continue;
        }
      }
      goto LABEL_17;
    }
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        32,
        WPP_65e53f33d5f73b8eda8fc31c371debb2_Traceguids,
        (unsigned int)v12);
LABEL_17:
      v14 = WPP_GLOBAL_Control;
    }
    if ( (v5 & 0x80000000) == 0 )
    {
      if ( BytesReturned >= 8 )
      {
        *(_BYTE *)this = *v9 == -1610612724;
        goto LABEL_30;
      }
      v5 = -2147023537;
      if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 2) != 0 )
      {
        v15 = 34;
        v16 = 2147943759LL;
        goto LABEL_22;
      }
    }
    else if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 2) != 0 )
    {
      v15 = 33;
      v16 = v5;
LABEL_22:
      WPP_SF_d(*(_QWORD *)(v14 + 16), v15, WPP_65e53f33d5f73b8eda8fc31c371debb2_Traceguids, v16);
    }
    if ( !v9 )
    {
LABEL_31:
      CloseHandle(FileW);
      return v5;
    }
LABEL_30:
    operator delete(v9, v7);
    goto LABEL_31;
  }
  v17 = HrGetLastFailure();
  v5 = v17;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, WPP_65e53f33d5f73b8eda8fc31c371debb2_Traceguids, v17);
  return v5;
}

```

## disassembly

```asm
0x140018b80  mov     [rsp+arg_10], rbx
0x140018b85  mov     [rsp+arg_18], rbp
0x140018b8a  push    rsi
0x140018b8b  push    rdi
0x140018b8c  push    r12
0x140018b8e  push    r14
0x140018b90  push    r15
0x140018b92  sub     rsp, 60h
0x140018b96  mov     rax, cs:__security_cookie
0x140018b9d  xor     rax, rsp
0x140018ba0  mov     [rsp+88h+var_38], rax
0x140018ba5  mov     r12, rcx
0x140018ba8  mov     byte ptr [rcx], 0
0x140018bab  mov     rcx, rdx; lpFileName
0x140018bae  mov     rbx, rdx
0x140018bb1  xor     edi, edi
0x140018bb3  call    cs:__imp_GetFileAttributesW
0x140018bb9  cmp     eax, 0FFFFFFFFh
0x140018bbc  jnz     short loc_140018BCA
0x140018bbe  call    HrGetLastFailure
0x140018bc3  mov     edi, eax
0x140018bc5  jmp     loc_140018D91
0x140018bca  bt      eax, 0Ah
0x140018bce  jnb     loc_140018D91
0x140018bd4  xor     r9d, r9d; lpSecurityAttributes
0x140018bd7  mov     [rsp+88h+hTemplateFile], rdi; hTemplateFile
0x140018bdc  mov     [rsp+88h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x140018be4  mov     edx, 80h; dwDesiredAccess
0x140018be9  mov     rcx, rbx; lpFileName
0x140018bec  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x140018bf4  lea     r8d, [r9+1]; dwShareMode
0x140018bf8  call    cs:__imp_CreateFileW
0x140018bfe  mov     r15, rax
0x140018c01  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140018c05  jz      loc_140018D59
0x140018c0b  xor     ebx, ebx
0x140018c0d  mov     [rsp+88h+lpOutBuffer], rbx
0x140018c12  xor     ebp, ebp
0x140018c14  mov     [rsp+88h+BytesReturned], ebx
0x140018c18  lea     r14d, [rbx+18h]
0x140018c1c  test    rbx, rbx
0x140018c1f  jz      short loc_140018C32
0x140018c21  mov     rcx, rbx; void *
0x140018c24  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140018c29  mov     [rsp+88h+lpOutBuffer], 0
0x140018c32  mov     edx, r14d
0x140018c35  lea     rcx, [rsp+88h+lpOutBuffer]
0x140018c3a  call    ??$MpNewBuffer@E@CommonUtil@@YAJPEAPEAE_K@Z; CommonUtil::MpNewBuffer<uchar>(uchar * *,unsigned __int64)
0x140018c3f  mov     rbx, [rsp+88h+lpOutBuffer]
0x140018c44  lea     rsi, WPP_GLOBAL_Control
0x140018c4b  mov     edi, eax
0x140018c4d  shr     eax, 1Fh
0x140018c50  test    al, al
0x140018c52  jnz     short loc_140018CB1
0x140018c54  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x140018c5d  lea     rax, [rsp+88h+BytesReturned]
0x140018c62  mov     [rsp+88h+hTemplateFile], rax; lpBytesReturned
0x140018c67  xor     r9d, r9d; nInBufferSize
0x140018c6a  mov     [rsp+88h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x140018c6f  xor     r8d, r8d; lpInBuffer
0x140018c72  mov     edx, 900A8h; dwIoControlCode
0x140018c77  mov     qword ptr [rsp+88h+dwCreationDisposition], rbx; lpOutBuffer
0x140018c7c  mov     rcx, r15; hDevice
0x140018c7f  call    cs:__imp_DeviceIoControl
0x140018c85  test    eax, eax
0x140018c87  jnz     short loc_140018CDB
0x140018c89  call    HrGetLastFailure
0x140018c8e  mov     edi, eax
0x140018c90  cmp     eax, 8007007Ah
0x140018c95  jz      short loc_140018C9E
0x140018c97  cmp     eax, 800700EAh
0x140018c9c  jnz     short loc_140018CDB
0x140018c9e  inc     ebp
0x140018ca0  mov     r14d, 4000h
0x140018ca6  cmp     ebp, 1
0x140018ca9  jbe     loc_140018C1C
0x140018caf  jmp     short loc_140018CDB
0x140018cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140018cb8  cmp     rcx, rsi
0x140018cbb  jz      short loc_140018CE2
0x140018cbd  test    byte ptr [rcx+1Ch], 2
0x140018cc1  jz      short loc_140018CE2
0x140018cc3  mov     rcx, [rcx+10h]
0x140018cc7  lea     r8, WPP_65e53f33d5f73b8eda8fc31c371debb2_Traceguids
0x140018cce  mov     edx, 20h ; ' '
0x140018cd3  mov     r9d, edi
0x140018cd6  call    WPP_SF_d
0x140018cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x140018ce2  mov     eax, edi
0x140018ce4  shr     eax, 1Fh
0x140018ce7  test    al, al
0x140018ce9  jz      short loc_140018D15
0x140018ceb  cmp     rcx, rsi
0x140018cee  jz      short loc_140018D0E
0x140018cf0  test    byte ptr [rcx+1Ch], 2
0x140018cf4  jz      short loc_140018D0E
0x140018cf6  mov     edx, 21h ; '!'
0x140018cfb  mov     r9d, edi
0x140018cfe  mov     rcx, [rcx+10h]
0x140018d02  lea     r8, WPP_65e53f33d5f73b8eda8fc31c371debb2_Traceguids
0x140018d09  call    WPP_SF_d
0x140018d0e  test    rbx, rbx
0x140018d11  jz      short loc_140018D4E
0x140018d13  jmp     short loc_140018D46
0x140018d15  cmp     [rsp+88h+BytesReturned], 8
0x140018d1a  jnb     short loc_140018D39
0x140018d1c  mov     edi, 8007054Fh
0x140018d21  cmp     rcx, rsi
0x140018d24  jz      short loc_140018D0E
0x140018d26  test    byte ptr [rcx+1Ch], 2
0x140018d2a  jz      short loc_140018D0E
0x140018d2c  mov     edx, 22h ; '"'
0x140018d31  mov     r9d, 8007054Fh
0x140018d37  jmp     short loc_140018CFE
0x140018d39  cmp     dword ptr [rbx], 0A000000Ch
0x140018d3f  setz    al
0x140018d42  mov     [r12], al
0x140018d46  mov     rcx, rbx; void *
0x140018d49  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140018d4e  mov     rcx, r15; hObject
0x140018d51  call    cs:__imp_CloseHandle
0x140018d57  jmp     short loc_140018D91
0x140018d59  call    HrGetLastFailure
0x140018d5e  mov     edi, eax
0x140018d60  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d67  lea     rsi, WPP_GLOBAL_Control
0x140018d6e  cmp     rcx, rsi
0x140018d71  jz      short loc_140018D91
0x140018d73  test    byte ptr [rcx+1Ch], 2
0x140018d77  jz      short loc_140018D91
0x140018d79  mov     rcx, [rcx+10h]
0x140018d7d  lea     r8, WPP_65e53f33d5f73b8eda8fc31c371debb2_Traceguids
0x140018d84  mov     edx, 1Fh
0x140018d89  mov     r9d, eax
0x140018d8c  call    WPP_SF_d
0x140018d91  mov     eax, edi
0x140018d93  mov     rcx, [rsp+88h+var_38]
0x140018d98  xor     rcx, rsp; StackCookie
0x140018d9b  call    __security_check_cookie
0x140018da0  lea     r11, [rsp+88h+var_28]
0x140018da5  mov     rbx, [r11+40h]
0x140018da9  mov     rbp, [r11+48h]
0x140018dad  mov     rsp, r11
0x140018db0  pop     r15
0x140018db2  pop     r14
0x140018db4  pop     r12
0x140018db6  pop     rdi
0x140018db7  pop     rsi
0x140018db8  retn
```
