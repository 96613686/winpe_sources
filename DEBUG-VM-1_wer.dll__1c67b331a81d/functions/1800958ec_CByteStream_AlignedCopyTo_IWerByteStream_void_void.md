# CByteStream::AlignedCopyTo(IWerByteStream *,void *,void *)

- ea: `0x1800958ec`
- end: `0x180095be1`
- name: `?AlignedCopyTo@CByteStream@@QEAAJPEAUIWerByteStream@@PEAX1@Z`
- size: `757`
- prototype: `__int64 __fastcall(CByteStream *__hidden this, struct IWerByteStream *, void *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007fda8`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x18003bf14`
- `0x180050db0`
- `0x1800517cc`
- `0x1800958ec`
- `0x1800aa000`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095b82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095b82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800959ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800959ca`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180095b78`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180095b78`

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
0x1800958ec  push    rbp
0x1800958ee  push    rbx
0x1800958ef  push    rsi
0x1800958f0  push    rdi
0x1800958f1  push    r12
0x1800958f3  push    r13
0x1800958f5  push    r14
0x1800958f7  push    r15
0x1800958f9  lea     rbp, [rsp-0F58h]
0x180095901  mov     eax, 1058h
0x180095906  call    _alloca_probe
0x18009590b  sub     rsp, rax
0x18009590e  mov     rax, cs:__security_cookie
0x180095915  xor     rax, rsp
0x180095918  mov     [rbp+0F90h+var_50], rax
0x18009591f  mov     r15, r8
0x180095922  mov     r12, rdx
0x180095925  mov     rsi, rcx
0x180095928  xor     edi, edi
0x18009592a  xor     edx, edx; Val
0x18009592c  mov     [rsp+1090h+var_1060], edi
0x180095930  mov     r8d, 1000h; Size
0x180095936  mov     [rsp+1090h+var_105C], edi
0x18009593a  lea     rcx, [rsp+1090h+var_1050]; void *
0x18009593f  mov     r13, r9
0x180095942  call    memset_0
0x180095947  mov     rax, [rsi]
0x18009594a  xor     r9d, r9d
0x18009594d  xor     r8d, r8d
0x180095950  mov     [rsp+1090h+FileInformation], rdi
0x180095955  xor     edx, edx
0x180095957  mov     rcx, rsi
0x18009595a  mov     rax, [rax+10h]
0x18009595e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095963  mov     ebx, eax
0x180095965  test    eax, eax
0x180095967  jns     short loc_1800959A5
0x180095969  mov     rcx, cs:WPP_GLOBAL_Control
0x180095970  lea     rax, WPP_GLOBAL_Control
0x180095977  cmp     rcx, rax
0x18009597a  jz      loc_180095BBC
0x180095980  test    byte ptr [rcx+1Ch], 1
0x180095984  jz      loc_180095BBC
0x18009598a  lea     edx, [rdi+0Eh]
0x18009598d  mov     r9d, ebx
0x180095990  mov     rcx, [rcx+10h]
0x180095994  lea     r8, WPP_7066dd0f05d133a0820bef218904ca03_Traceguids
0x18009599b  call    WPP_SF_d
0x1800959a0  jmp     loc_180095BBC
0x1800959a5  xor     r14d, r14d
0x1800959a8  mov     rax, [rsi]
0x1800959ab  mov     rcx, rsi
0x1800959ae  mov     rax, [rax+20h]
0x1800959b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800959b7  cmp     r14, rax
0x1800959ba  jnb     loc_180095B45
0x1800959c0  test    r15, r15
0x1800959c3  jz      short loc_1800959D8
0x1800959c5  xor     edx, edx; dwMilliseconds
0x1800959c7  mov     rcx, r15; hHandle
0x1800959ca  call    cs:__imp_WaitForSingleObject
0x1800959d0  test    eax, eax
0x1800959d2  jz      loc_180095A81
0x1800959d8  mov     rax, [rsi]
0x1800959db  lea     r9, [rsp+1090h+var_1060]
0x1800959e0  mov     r8d, 1000h
0x1800959e6  mov     [rsp+1090h+var_1070], r15
0x1800959eb  lea     rdx, [rsp+1090h+var_1050]
0x1800959f0  mov     rcx, rsi
0x1800959f3  mov     rax, [rax]
0x1800959f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800959fb  mov     ebx, eax
0x1800959fd  test    eax, eax
0x1800959ff  js      loc_180095B1A
0x180095a05  mov     ecx, [rsp+1090h+var_1060]
0x180095a09  mov     ebx, 1000h
0x180095a0e  cmp     ecx, ebx
0x180095a10  jnb     short loc_180095A36
0x180095a12  test    edi, edi
0x180095a14  jnz     loc_180095AB7
0x180095a1a  mov     eax, ebx
0x180095a1c  xor     edx, edx; Val
0x180095a1e  sub     eax, ecx
0x180095a20  mov     edi, eax
0x180095a22  mov     r8d, eax; Size
0x180095a25  mov     eax, ecx
0x180095a27  lea     rcx, [rsp+1090h+var_1050]
0x180095a2c  add     rcx, rax; void *
0x180095a2f  call    memset_0
0x180095a34  mov     ecx, ebx
0x180095a36  mov     rax, [r12]
0x180095a3a  lea     r9, [rsp+1090h+var_105C]
0x180095a3f  mov     r8d, ecx
0x180095a42  mov     [rsp+1090h+var_1070], r15
0x180095a47  lea     rdx, [rsp+1090h+var_1050]
0x180095a4c  mov     rcx, r12
0x180095a4f  mov     rax, [rax+8]
0x180095a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095a58  mov     ebx, eax
0x180095a5a  test    eax, eax
0x180095a5c  js      loc_180095AEF
0x180095a62  mov     eax, [rsp+1090h+var_105C]
0x180095a66  cmp     [rsp+1090h+var_1060], eax
0x180095a6a  jz      short loc_180095A79
0x180095a6c  test    edi, edi
0x180095a6e  jnz     short loc_180095A79
0x180095a70  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180095a75  mov     eax, [rsp+1090h+var_105C]
0x180095a79  add     r14, rax
0x180095a7c  jmp     loc_1800959A8
0x180095a81  mov     ebx, 80004004h
0x180095a86  mov     rcx, cs:WPP_GLOBAL_Control
0x180095a8d  lea     rax, WPP_GLOBAL_Control
0x180095a94  cmp     rcx, rax
0x180095a97  jz      loc_180095BBC
0x180095a9d  test    byte ptr [rcx+1Ch], 4
0x180095aa1  jz      loc_180095BBC
0x180095aa7  mov     edx, 0Fh
0x180095aac  mov     r9d, 80004004h
0x180095ab2  jmp     loc_180095990
0x180095ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x180095abe  lea     rax, WPP_GLOBAL_Control
0x180095ac5  cmp     rcx, rax
0x180095ac8  jz      short loc_180095AE5
0x180095aca  test    byte ptr [rcx+1Ch], 1
0x180095ace  jz      short loc_180095AE5
0x180095ad0  mov     rcx, [rcx+10h]
0x180095ad4  lea     r8, WPP_7066dd0f05d133a0820bef218904ca03_Traceguids
0x180095adb  mov     edx, 11h
0x180095ae0  call    WPP_SF_
0x180095ae5  mov     ebx, 80070147h
0x180095aea  jmp     loc_180095BBC
0x180095aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180095af6  lea     rax, WPP_GLOBAL_Control
0x180095afd  cmp     rcx, rax
0x180095b00  jz      loc_180095BBC
0x180095b06  test    byte ptr [rcx+1Ch], 1
0x180095b0a  jz      loc_180095BBC
0x180095b10  mov     edx, 12h
0x180095b15  jmp     loc_18009598D
0x180095b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180095b21  lea     rax, WPP_GLOBAL_Control
0x180095b28  cmp     rcx, rax
0x180095b2b  jz      loc_180095BBC
0x180095b31  test    byte ptr [rcx+1Ch], 1
0x180095b35  jz      loc_180095BBC
0x180095b3b  mov     edx, 10h
0x180095b40  jmp     loc_18009598D
0x180095b45  test    edi, edi
0x180095b47  jz      short loc_180095BBA
0x180095b49  mov     rax, [rsi]
0x180095b4c  mov     rcx, rsi
0x180095b4f  mov     [rsp+1090h+FileInformation], 0
0x180095b58  mov     rax, [rax+20h]
0x180095b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b61  mov     r9d, 8; dwBufferSize
0x180095b67  mov     [rsp+1090h+FileInformation], rax
0x180095b6c  lea     r8, [rsp+1090h+FileInformation]; lpFileInformation
0x180095b71  mov     rcx, r13; hFile
0x180095b74  lea     edx, [r9-2]; FileInformationClass
0x180095b78  call    cs:__imp_SetFileInformationByHandle
0x180095b7e  test    eax, eax
0x180095b80  jnz     short loc_180095BBA
0x180095b82  call    cs:__imp_GetLastError
0x180095b88  mov     ebx, eax
0x180095b8a  test    eax, eax
0x180095b8c  jle     short loc_180095B97
0x180095b8e  movzx   ebx, ax
0x180095b91  or      ebx, 80070000h
0x180095b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180095b9e  lea     rax, WPP_GLOBAL_Control
0x180095ba5  cmp     rcx, rax
0x180095ba8  jz      short loc_180095BBC
0x180095baa  test    byte ptr [rcx+1Ch], 1
0x180095bae  jz      short loc_180095BBC
0x180095bb0  mov     edx, 13h
0x180095bb5  jmp     loc_18009598D
0x180095bba  xor     ebx, ebx
0x180095bbc  mov     eax, ebx
0x180095bbe  mov     rcx, [rbp+0F90h+var_50]
0x180095bc5  xor     rcx, rsp; StackCookie
0x180095bc8  call    __security_check_cookie
0x180095bcd  add     rsp, 1058h
0x180095bd4  pop     r15
0x180095bd6  pop     r14
0x180095bd8  pop     r13
0x180095bda  pop     r12
0x180095bdc  pop     rdi
0x180095bdd  pop     rsi
0x180095bde  pop     rbx
0x180095bdf  pop     rbp
0x180095be0  retn
```
