# CByteStream::AlignedCopyTo(IWerByteStream *,void *,void *)

- ea: `0x18009589c`
- end: `0x180095b91`
- name: `?AlignedCopyTo@CByteStream@@QEAAJPEAUIWerByteStream@@PEAX1@Z`
- size: `757`
- prototype: `__int64 __fastcall(CByteStream *__hidden this, struct IWerByteStream *, void *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007fd58`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x18003bf14`
- `0x180050db0`
- `0x1800517cc`
- `0x18009589c`
- `0x1800a9fb0`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095b32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095b32`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009597a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009597a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180095b28`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180095b28`

## pseudocode

```c
__int64 __fastcall CByteStream::AlignedCopyTo(CByteStream *this, struct IWerByteStream *a2, void *a3, void *a4)
{
  unsigned int v7; // edi
  __int64 (__fastcall **v9)(CByteStream *, _BYTE *, __int64, unsigned int *, void *); // rax
  signed int v10; // ebx
  wchar_t *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned __int64 i; // r14
  unsigned int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  signed int LastError; // eax
  unsigned int v23; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-CCh] BYREF
  __int64 FileInformation; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v26[4096]; // [rsp+40h] [rbp-C0h] BYREF

  v7 = 0;
  v23 = 0;
  v24 = 0;
  memset_0(v26, 0, sizeof(v26));
  v9 = *(__int64 (__fastcall ***)(CByteStream *, _BYTE *, __int64, unsigned int *, void *))this;
  FileInformation = 0;
  v10 = ((__int64 (__fastcall *)(CByteStream *, _QWORD, _QWORD, _QWORD))v9[2])(this, 0, 0, 0);
  if ( v10 >= 0 )
  {
    for ( i = 0; i < (*(__int64 (__fastcall **)(CByteStream *))(*(_QWORD *)this + 32LL))(this); i += v19 )
    {
      if ( a3 && !WaitForSingleObject(a3, 0) )
      {
        v10 = -2147467260;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          v12 = 15;
          v13 = 2147500036LL;
          goto LABEL_6;
        }
        return (unsigned int)v10;
      }
      v10 = (**(__int64 (__fastcall ***)(CByteStream *, _BYTE *, __int64, unsigned int *, void *))this)(
              this,
              v26,
              4096,
              &v23,
              a3);
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v12 = 16;
          goto LABEL_5;
        }
        return (unsigned int)v10;
      }
      v15 = v23;
      if ( v23 < 0x1000 )
      {
        if ( v7 )
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_7066dd0f05d133a0820bef218904ca03_Traceguids);
          return (unsigned int)-2147024569;
        }
        v7 = 4096 - v23;
        memset_0(&v26[v23], 0, 4096 - v23);
        v15 = 4096;
      }
      v10 = (*(__int64 (__fastcall **)(struct IWerByteStream *, _BYTE *, _QWORD, unsigned int *, void *))(*(_QWORD *)a2 + 8LL))(
              a2,
              v26,
              v15,
              &v24,
              a3);
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v12 = 18;
          goto LABEL_5;
        }
        return (unsigned int)v10;
      }
      v19 = v24;
      if ( v23 != v24 && !v7 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16, v18);
        v19 = v24;
      }
    }
    if ( !v7 )
      return 0;
    v20 = *(_QWORD *)this;
    FileInformation = 0;
    FileInformation = (*(__int64 (__fastcall **)(CByteStream *))(v20 + 32))(this);
    if ( SetFileInformationByHandle(a4, FileEndOfFileInfo, &FileInformation, 8u) )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v12 = 19;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 14;
LABEL_5:
      v13 = (unsigned int)v10;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_7066dd0f05d133a0820bef218904ca03_Traceguids, v13);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18009589c  push    rbp
0x18009589e  push    rbx
0x18009589f  push    rsi
0x1800958a0  push    rdi
0x1800958a1  push    r12
0x1800958a3  push    r13
0x1800958a5  push    r14
0x1800958a7  push    r15
0x1800958a9  lea     rbp, [rsp-0F58h]
0x1800958b1  mov     eax, 1058h
0x1800958b6  call    _alloca_probe
0x1800958bb  sub     rsp, rax
0x1800958be  mov     rax, cs:__security_cookie
0x1800958c5  xor     rax, rsp
0x1800958c8  mov     [rbp+0F90h+var_50], rax
0x1800958cf  mov     r15, r8
0x1800958d2  mov     r12, rdx
0x1800958d5  mov     rsi, rcx
0x1800958d8  xor     edi, edi
0x1800958da  xor     edx, edx; Val
0x1800958dc  mov     [rsp+1090h+var_1060], edi
0x1800958e0  mov     r8d, 1000h; Size
0x1800958e6  mov     [rsp+1090h+var_105C], edi
0x1800958ea  lea     rcx, [rsp+1090h+var_1050]; void *
0x1800958ef  mov     r13, r9
0x1800958f2  call    memset_0
0x1800958f7  mov     rax, [rsi]
0x1800958fa  xor     r9d, r9d
0x1800958fd  xor     r8d, r8d
0x180095900  mov     [rsp+1090h+FileInformation], rdi
0x180095905  xor     edx, edx
0x180095907  mov     rcx, rsi
0x18009590a  mov     rax, [rax+10h]
0x18009590e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095913  mov     ebx, eax
0x180095915  test    eax, eax
0x180095917  jns     short loc_180095955
0x180095919  mov     rcx, cs:WPP_GLOBAL_Control
0x180095920  lea     rax, WPP_GLOBAL_Control
0x180095927  cmp     rcx, rax
0x18009592a  jz      loc_180095B6C
0x180095930  test    byte ptr [rcx+1Ch], 1
0x180095934  jz      loc_180095B6C
0x18009593a  lea     edx, [rdi+0Eh]
0x18009593d  mov     r9d, ebx
0x180095940  mov     rcx, [rcx+10h]
0x180095944  lea     r8, WPP_7066dd0f05d133a0820bef218904ca03_Traceguids
0x18009594b  call    WPP_SF_d
0x180095950  jmp     loc_180095B6C
0x180095955  xor     r14d, r14d
0x180095958  mov     rax, [rsi]
0x18009595b  mov     rcx, rsi
0x18009595e  mov     rax, [rax+20h]
0x180095962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095967  cmp     r14, rax
0x18009596a  jnb     loc_180095AF5
0x180095970  test    r15, r15
0x180095973  jz      short loc_180095988
0x180095975  xor     edx, edx; dwMilliseconds
0x180095977  mov     rcx, r15; hHandle
0x18009597a  call    cs:__imp_WaitForSingleObject
0x180095980  test    eax, eax
0x180095982  jz      loc_180095A31
0x180095988  mov     rax, [rsi]
0x18009598b  lea     r9, [rsp+1090h+var_1060]
0x180095990  mov     r8d, 1000h
0x180095996  mov     [rsp+1090h+var_1070], r15
0x18009599b  lea     rdx, [rsp+1090h+var_1050]
0x1800959a0  mov     rcx, rsi
0x1800959a3  mov     rax, [rax]
0x1800959a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800959ab  mov     ebx, eax
0x1800959ad  test    eax, eax
0x1800959af  js      loc_180095ACA
0x1800959b5  mov     ecx, [rsp+1090h+var_1060]
0x1800959b9  mov     ebx, 1000h
0x1800959be  cmp     ecx, ebx
0x1800959c0  jnb     short loc_1800959E6
0x1800959c2  test    edi, edi
0x1800959c4  jnz     loc_180095A67
0x1800959ca  mov     eax, ebx
0x1800959cc  xor     edx, edx; Val
0x1800959ce  sub     eax, ecx
0x1800959d0  mov     edi, eax
0x1800959d2  mov     r8d, eax; Size
0x1800959d5  mov     eax, ecx
0x1800959d7  lea     rcx, [rsp+1090h+var_1050]
0x1800959dc  add     rcx, rax; void *
0x1800959df  call    memset_0
0x1800959e4  mov     ecx, ebx
0x1800959e6  mov     rax, [r12]
0x1800959ea  lea     r9, [rsp+1090h+var_105C]
0x1800959ef  mov     r8d, ecx
0x1800959f2  mov     [rsp+1090h+var_1070], r15
0x1800959f7  lea     rdx, [rsp+1090h+var_1050]
0x1800959fc  mov     rcx, r12
0x1800959ff  mov     rax, [rax+8]
0x180095a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095a08  mov     ebx, eax
0x180095a0a  test    eax, eax
0x180095a0c  js      loc_180095A9F
0x180095a12  mov     eax, [rsp+1090h+var_105C]
0x180095a16  cmp     [rsp+1090h+var_1060], eax
0x180095a1a  jz      short loc_180095A29
0x180095a1c  test    edi, edi
0x180095a1e  jnz     short loc_180095A29
0x180095a20  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180095a25  mov     eax, [rsp+1090h+var_105C]
0x180095a29  add     r14, rax
0x180095a2c  jmp     loc_180095958
0x180095a31  mov     ebx, 80004004h
0x180095a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180095a3d  lea     rax, WPP_GLOBAL_Control
0x180095a44  cmp     rcx, rax
0x180095a47  jz      loc_180095B6C
0x180095a4d  test    byte ptr [rcx+1Ch], 4
0x180095a51  jz      loc_180095B6C
0x180095a57  mov     edx, 0Fh
0x180095a5c  mov     r9d, 80004004h
0x180095a62  jmp     loc_180095940
0x180095a67  mov     rcx, cs:WPP_GLOBAL_Control
0x180095a6e  lea     rax, WPP_GLOBAL_Control
0x180095a75  cmp     rcx, rax
0x180095a78  jz      short loc_180095A95
0x180095a7a  test    byte ptr [rcx+1Ch], 1
0x180095a7e  jz      short loc_180095A95
0x180095a80  mov     rcx, [rcx+10h]
0x180095a84  lea     r8, WPP_7066dd0f05d133a0820bef218904ca03_Traceguids
0x180095a8b  mov     edx, 11h
0x180095a90  call    WPP_SF_
0x180095a95  mov     ebx, 80070147h
0x180095a9a  jmp     loc_180095B6C
0x180095a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180095aa6  lea     rax, WPP_GLOBAL_Control
0x180095aad  cmp     rcx, rax
0x180095ab0  jz      loc_180095B6C
0x180095ab6  test    byte ptr [rcx+1Ch], 1
0x180095aba  jz      loc_180095B6C
0x180095ac0  mov     edx, 12h
0x180095ac5  jmp     loc_18009593D
0x180095aca  mov     rcx, cs:WPP_GLOBAL_Control
0x180095ad1  lea     rax, WPP_GLOBAL_Control
0x180095ad8  cmp     rcx, rax
0x180095adb  jz      loc_180095B6C
0x180095ae1  test    byte ptr [rcx+1Ch], 1
0x180095ae5  jz      loc_180095B6C
0x180095aeb  mov     edx, 10h
0x180095af0  jmp     loc_18009593D
0x180095af5  test    edi, edi
0x180095af7  jz      short loc_180095B6A
0x180095af9  mov     rax, [rsi]
0x180095afc  mov     rcx, rsi
0x180095aff  mov     [rsp+1090h+FileInformation], 0
0x180095b08  mov     rax, [rax+20h]
0x180095b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b11  mov     r9d, 8; dwBufferSize
0x180095b17  mov     [rsp+1090h+FileInformation], rax
0x180095b1c  lea     r8, [rsp+1090h+FileInformation]; lpFileInformation
0x180095b21  mov     rcx, r13; hFile
0x180095b24  lea     edx, [r9-2]; FileInformationClass
0x180095b28  call    cs:__imp_SetFileInformationByHandle
0x180095b2e  test    eax, eax
0x180095b30  jnz     short loc_180095B6A
0x180095b32  call    cs:__imp_GetLastError
0x180095b38  mov     ebx, eax
0x180095b3a  test    eax, eax
0x180095b3c  jle     short loc_180095B47
0x180095b3e  movzx   ebx, ax
0x180095b41  or      ebx, 80070000h
0x180095b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180095b4e  lea     rax, WPP_GLOBAL_Control
0x180095b55  cmp     rcx, rax
0x180095b58  jz      short loc_180095B6C
0x180095b5a  test    byte ptr [rcx+1Ch], 1
0x180095b5e  jz      short loc_180095B6C
0x180095b60  mov     edx, 13h
0x180095b65  jmp     loc_18009593D
0x180095b6a  xor     ebx, ebx
0x180095b6c  mov     eax, ebx
0x180095b6e  mov     rcx, [rbp+0F90h+var_50]
0x180095b75  xor     rcx, rsp; StackCookie
0x180095b78  call    __security_check_cookie
0x180095b7d  add     rsp, 1058h
0x180095b84  pop     r15
0x180095b86  pop     r14
0x180095b88  pop     r13
0x180095b8a  pop     r12
0x180095b8c  pop     rdi
0x180095b8d  pop     rsi
0x180095b8e  pop     rbx
0x180095b8f  pop     rbp
0x180095b90  retn
```
