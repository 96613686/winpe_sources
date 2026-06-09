# DavAddConnection

- ea: `0x180005450`
- end: `0x180005981`
- name: `DavAddConnection`
- size: `1329`
- prototype: `DWORD __stdcall(HANDLE *ConnectionHandle, LPCWSTR RemoteName, LPCWSTR UserName, LPCWSTR Password, PBYTE ClientCert, DWORD CertSize)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800027c0`
- `0x180005450`
- `0x180005c7c`
- `0x180005ce4`
- `0x180005d38`
- `0x1800060cd`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000550c`
- `msvcrt!_wcsnicmp` at `0x18000550c`
- `ntdll!NtCreateFile` at `0x180005852`
- `ntdll!NtCreateFile` at `0x18000589e`
- `ntdll!NtCreateFile` at `0x180005852`
- `ntdll!NtCreateFile` at `0x18000589e`
- `ntdll!RtlNtStatusToDosError` at `0x180005901`
- `ntdll!RtlNtStatusToDosError` at `0x180005901`
- `ntdll!NtFsControlFile` at `0x1800058e9`
- `ntdll!NtFsControlFile` at `0x1800058e9`
- `ntdll!NtClose` at `0x1800058f9`
- `ntdll!NtClose` at `0x1800058f9`
- `KERNEL32!LocalFree` at `0x180005955`
- `KERNEL32!LocalFree` at `0x18000595e`
- `KERNEL32!LocalFree` at `0x180005955`
- `KERNEL32!LocalFree` at `0x18000595e`
- `KERNEL32!GetLastError` at `0x180005564`
- `KERNEL32!GetLastError` at `0x18000566b`
- `KERNEL32!GetLastError` at `0x180005564`
- `KERNEL32!GetLastError` at `0x18000566b`
- `KERNEL32!LocalAlloc` at `0x180005556`
- `KERNEL32!LocalAlloc` at `0x18000565d`
- `KERNEL32!LocalAlloc` at `0x180005556`
- `KERNEL32!LocalAlloc` at `0x18000565d`

## pseudocode

```c
DWORD __stdcall DavAddConnection(
        HANDLE *ConnectionHandle,
        LPCWSTR RemoteName,
        LPCWSTR UserName,
        LPCWSTR Password,
        PBYTE ClientCert,
        DWORD CertSize)
{
  __int64 v6; // rdi
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rax
  DWORD UNCFromHTTPPath; // eax
  DWORD LastError; // ebx
  _WORD *v14; // rax
  _WORD *v15; // r13
  HRESULT v16; // eax
  __int64 v17; // rax
  int v18; // ebx
  unsigned int v19; // ecx
  __int64 v20; // r12
  char *v21; // rax
  char *EaBuffer; // rdi
  HRESULT v23; // eax
  _DWORD *v24; // rsi
  HRESULT v25; // eax
  __int64 v26; // rbx
  char *v27; // rbx
  unsigned __int16 v28; // si
  size_t v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r10
  unsigned int v33; // r11d
  ULONG ShareAccess; // r15d
  __int64 v35; // r10
  ULONG v36; // esi
  NTSTATUS v37; // ebx
  void *v38; // rcx
  ULONG v39; // eax
  char *i; // rax
  ULONG EaLength; // [rsp+50h] [rbp-79h]
  DWORD Size; // [rsp+60h] [rbp-69h] BYREF
  ULONG InputBuffer; // [rsp+64h] [rbp-65h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-61h] BYREF
  DWORD v46; // [rsp+70h] [rbp-59h]
  __int64 v47; // [rsp+78h] [rbp-51h] BYREF
  _WORD *v48; // [rsp+80h] [rbp-49h]
  HANDLE Handle; // [rsp+88h] [rbp-41h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-29h] BYREF

  v6 = -1;
  Size = 0;
  FileHandle = (void *)-1LL;
  Handle = (HANDLE)-1LL;
  v47 = 0;
  v48 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( ConnectionHandle )
  {
    if ( ClientCert )
    {
      if ( RemoteName )
      {
        if ( !UserName )
          goto LABEL_8;
        v10 = -1;
        do
          ++v10;
        while ( UserName[v10] );
        if ( v10 <= 0x201 )
        {
LABEL_8:
          if ( !Password )
            goto LABEL_68;
          v11 = -1;
          do
            ++v11;
          while ( Password[v11] );
          if ( v11 <= 0x100 )
          {
LABEL_68:
            if ( !_wcsnicmp(RemoteName, L"https://", 8u) )
            {
              UNCFromHTTPPath = DavGetUNCFromHTTPPath(RemoteName, 0, &Size);
              LastError = UNCFromHTTPPath;
              if ( UNCFromHTTPPath != 122 )
              {
                if ( UNCFromHTTPPath )
                  return LastError;
                return 87;
              }
              if ( Size > 0x7FE7 )
                return 87;
              v14 = LocalAlloc(0x40u, 2LL * (Size + 23));
              v15 = v14;
              if ( !v14 )
                return GetLastError();
              LastError = DavGetUNCFromHTTPPath(RemoteName, v14 + 23, &Size);
              if ( LastError )
              {
LABEL_63:
                LocalFree(v15);
                return LastError;
              }
              v48 = v15;
              WORD1(v47) = 2 * (Size + 23);
              LOWORD(v47) = WORD1(v47);
              v16 = StringCchCopyW(v15, 0x19u, L"\\Device\\WebDavRedirector");
              if ( v16 < 0 )
              {
                LastError = (unsigned __int16)v16;
                goto LABEL_63;
              }
              v15[24] = 92;
              Size = 0;
              ObjectAttributes.Attributes = 64;
              ObjectAttributes.ObjectName = (PUNICODE_STRING)&v47;
              ObjectAttributes.Length = 48;
              ObjectAttributes.RootDirectory = 0;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              if ( Password )
              {
                v17 = -1;
                do
                  ++v17;
                while ( Password[v17] );
                v18 = (unsigned __int16)(2 * v17);
                v19 = (v18 + 21) & 0xFFFFFFFC;
              }
              else
              {
                v19 = 0;
                LOWORD(v18) = 0;
              }
              if ( UserName )
              {
                do
                  ++v6;
                while ( UserName[v6] );
                Size = (unsigned __int16)(2 * v6);
                v19 += (Size + 21) & 0xFFFFFFFC;
              }
              v46 = (CertSize + 23) & 0xFFFFFFFC;
              InputBuffer = v19 + v46 + 52;
              v20 = InputBuffer;
              v21 = (char *)LocalAlloc(0x40u, InputBuffer);
              EaBuffer = v21;
              if ( !v21 )
              {
                LastError = GetLastError();
                goto LABEL_63;
              }
              v23 = StringCbCopyA(v21 + 8, 8u, "Https:");
              if ( v23 < 0 )
                goto LABEL_33;
              *((_DWORD *)EaBuffer + 1) = 1792;
              v24 = EaBuffer + 16;
              *(_DWORD *)EaBuffer = 16;
              if ( Password )
              {
                v23 = StringCbCopyA(EaBuffer + 24, 0xAu, "Password");
                if ( v23 < 0 )
                {
LABEL_33:
                  LastError = (unsigned __int16)v23;
                  goto LABEL_60;
                }
                EaBuffer[21] = 9;
                v25 = StringCbCopyW((STRSAFE_LPWSTR)EaBuffer + 17, (unsigned __int16)v18 + 2LL, Password);
                if ( v25 < 0 )
                  goto LABEL_37;
                *((_WORD *)EaBuffer + 11) = v18;
                EaBuffer[20] = 0;
                v26 = ((unsigned __int16)v18 + 21) & 0xFFFFFFFC;
                *v24 = v26;
                v27 = (char *)v24 + v26;
              }
              else
              {
                v27 = EaBuffer + 16;
              }
              if ( UserName )
              {
                v25 = StringCbCopyA(v27 + 8, 0xAu, "UserName");
                if ( v25 < 0 )
                  goto LABEL_37;
                v28 = Size;
                v29 = (unsigned __int16)Size + 2LL;
                v27[5] = 9;
                v25 = StringCbCopyW((STRSAFE_LPWSTR)v27 + 9, v29, UserName);
                if ( v25 < 0 )
                  goto LABEL_37;
                *((_WORD *)v27 + 3) = v28;
                v30 = (v28 + 21) & 0xFFFFFFFC;
                v27[4] = 0;
                *(_DWORD *)v27 = v30;
                v27 += v30;
              }
              v25 = StringCbCopyA(v27 + 8, 0xCu, "Client-Cert");
              if ( v25 >= 0 )
              {
                v27[5] = 11;
                memcpy_0(v27 + 20, ClientCert, CertSize);
                v31 = v46;
                *((_WORD *)v27 + 3) = CertSize;
                *(_DWORD *)v27 = v31;
                v27[4] = 0;
                v25 = StringCbCopyA(&v27[v31 + 8], 8u, "Type");
                if ( v25 >= 0 )
                {
                  *(_DWORD *)&v27[v32 + 4] = 263936;
                  *(_DWORD *)&v27[v32 + 16] = 1;
                  *(_DWORD *)&v27[v32] = 20;
                  ShareAccess = v33 - 1;
                  v25 = StringCbCopyA(&v27[v32 + 28], v33, "mrxdav");
                  if ( v25 >= 0 )
                  {
                    v36 = InputBuffer;
                    EaLength = InputBuffer;
                    *(_DWORD *)&v27[v35 + 24] = 1792;
                    *(_DWORD *)&v27[v35 + 20] = 0;
                    v37 = NtCreateFile(
                            &FileHandle,
                            0x100000u,
                            &ObjectAttributes,
                            &IoStatusBlock,
                            0,
                            2u,
                            ShareAccess,
                            1u,
                            0xA0u,
                            EaBuffer,
                            EaLength);
                    if ( !v37 )
                    {
                      v37 = NtCreateFile(
                              &Handle,
                              0x100001u,
                              &ObjectAttributes,
                              &IoStatusBlock,
                              0,
                              0x80u,
                              ShareAccess,
                              1u,
                              0x21u,
                              EaBuffer,
                              v36);
                      if ( v37 )
                      {
                        InputBuffer = 2;
                        NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x4000020u, &InputBuffer, 4u, 0, 0);
                        v38 = FileHandle;
                      }
                      else
                      {
                        v38 = Handle;
                      }
                      NtClose(v38);
                    }
                    v39 = RtlNtStatusToDosError(v37);
                    LastError = v39;
                    switch ( v39 )
                    {
                      case 0u:
                        *ConnectionHandle = FileHandle;
                        break;
                      case 2u:
                      case 0x7Bu:
                        goto LABEL_57;
                      case 0x4CDu:
                        LastError = 67;
                        break;
                      case 0x8CAu:
LABEL_57:
                        LastError = 53;
                        break;
                    }
LABEL_60:
                    for ( i = EaBuffer; v20; --v20 )
                      *i++ = 0;
                    LocalFree(EaBuffer);
                    goto LABEL_63;
                  }
                }
              }
LABEL_37:
              LastError = (unsigned __int16)v25;
              goto LABEL_60;
            }
          }
        }
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180005450  mov     [rsp-8+arg_0], rcx
0x180005455  push    rbp
0x180005456  push    rbx
0x180005457  push    rsi
0x180005458  push    rdi
0x180005459  push    r12
0x18000545b  push    r13
0x18000545d  push    r14
0x18000545f  push    r15
0x180005461  lea     rbp, [rsp-0Fh]
0x180005466  sub     rsp, 0D8h
0x18000546d  xor     r12d, r12d
0x180005470  xorps   xmm0, xmm0
0x180005473  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180005477  mov     [rbp+47h+Size], r12d
0x18000547b  mov     [rbp+47h+FileHandle], rdi
0x18000547f  mov     r14, r9
0x180005482  mov     [rbp+47h+Handle], rdi
0x180005486  mov     r15, r8
0x180005489  mov     [rbp+47h+var_98], r12
0x18000548d  mov     rsi, rdx
0x180005490  mov     [rbp+47h+var_90], r12
0x180005494  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x180005498  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x18000549c  movups  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800054a0  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x1800054a4  test    rcx, rcx
0x1800054a7  jz      loc_180005968
0x1800054ad  cmp     [rbp+47h+ClientCert], r12
0x1800054b1  jz      loc_180005968
0x1800054b7  test    rdx, rdx
0x1800054ba  jz      loc_180005968
0x1800054c0  test    r8, r8
0x1800054c3  jz      short loc_1800054DE
0x1800054c5  mov     rax, rdi
0x1800054c8  inc     rax
0x1800054cb  cmp     [r8+rax*2], r12w
0x1800054d0  jnz     short loc_1800054C8
0x1800054d2  cmp     rax, 201h
0x1800054d8  ja      loc_180005968
0x1800054de  test    r14, r14
0x1800054e1  jz      short loc_1800054FC
0x1800054e3  mov     rax, rdi
0x1800054e6  inc     rax
0x1800054e9  cmp     [r9+rax*2], r12w
0x1800054ee  jnz     short loc_1800054E6
0x1800054f0  cmp     rax, 100h
0x1800054f6  ja      loc_180005968
0x1800054fc  mov     r8d, 8; MaxCount
0x180005502  lea     rdx, aHttps_0; "https://"
0x180005509  mov     rcx, rsi; String1
0x18000550c  call    cs:__imp__wcsnicmp
0x180005512  test    eax, eax
0x180005514  jnz     loc_180005968
0x18000551a  lea     r8, [rbp+47h+Size]; lpSize
0x18000551e  xor     edx, edx; UncPath
0x180005520  mov     rcx, rsi; Url
0x180005523  call    DavGetUNCFromHTTPPath
0x180005528  mov     ebx, eax
0x18000552a  cmp     eax, 7Ah ; 'z'
0x18000552d  jz      short loc_180005541
0x18000552f  test    eax, eax
0x180005531  jnz     loc_180005964
0x180005537  mov     ebx, 57h ; 'W'
0x18000553c  jmp     loc_180005964
0x180005541  mov     eax, [rbp+47h+Size]
0x180005544  cmp     eax, 7FE7h
0x180005549  ja      short loc_180005537
0x18000554b  lea     edx, [rax+17h]
0x18000554e  mov     ecx, 40h ; '@'; uFlags
0x180005553  add     rdx, rdx; uBytes
0x180005556  call    cs:__imp_LocalAlloc
0x18000555c  mov     r13, rax
0x18000555f  test    rax, rax
0x180005562  jnz     short loc_180005571
0x180005564  call    cs:__imp_GetLastError
0x18000556a  mov     ebx, eax
0x18000556c  jmp     loc_180005964
0x180005571  lea     rdx, [rax+2Eh]; UncPath
0x180005575  mov     rcx, rsi; Url
0x180005578  lea     r8, [rbp+47h+Size]; lpSize
0x18000557c  call    DavGetUNCFromHTTPPath
0x180005581  mov     ebx, eax
0x180005583  test    eax, eax
0x180005585  jnz     loc_18000595B
0x18000558b  movzx   eax, word ptr [rbp+47h+Size]
0x18000558f  lea     r8, aDeviceWebdavre; "\\Device\\WebDavRedirector"
0x180005596  add     ax, 17h
0x18000559a  mov     [rbp+47h+var_90], r13
0x18000559e  add     ax, ax
0x1800055a1  lea     edx, [rbx+19h]; cchDest
0x1800055a4  mov     rcx, r13; pszDest
0x1800055a7  mov     word ptr [rbp+47h+var_98+2], ax
0x1800055ab  mov     word ptr [rbp+47h+var_98], ax
0x1800055af  call    StringCchCopyW
0x1800055b4  test    eax, eax
0x1800055b6  jns     short loc_1800055C0
0x1800055b8  movzx   ebx, ax
0x1800055bb  jmp     loc_18000595B
0x1800055c0  mov     word ptr [r13+30h], 5Ch ; '\'
0x1800055c7  mov     edx, r12d
0x1800055ca  mov     [rbp+47h+Size], edx
0x1800055cd  mov     r8d, 40h ; '@'
0x1800055d3  mov     [rbp+47h+ObjectAttributes.Attributes], r8d
0x1800055d7  lea     rax, [rbp+47h+var_98]
0x1800055db  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x1800055df  xorps   xmm0, xmm0
0x1800055e2  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x1800055e9  mov     r9d, 0FFFFFFFCh
0x1800055ef  mov     [rbp+47h+ObjectAttributes.RootDirectory], r12
0x1800055f3  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800055f8  test    r14, r14
0x1800055fb  jz      short loc_180005618
0x1800055fd  mov     rax, rdi
0x180005600  inc     rax
0x180005603  cmp     [r14+rax*2], r12w
0x180005608  jnz     short loc_180005600
0x18000560a  add     ax, ax
0x18000560d  movzx   ebx, ax
0x180005610  lea     ecx, [rbx+15h]
0x180005613  and     ecx, r9d
0x180005616  jmp     short loc_18000561E
0x180005618  mov     ecx, r12d
0x18000561b  mov     ebx, r12d
0x18000561e  test    r15, r15
0x180005621  jz      short loc_180005641
0x180005623  inc     rdi
0x180005626  cmp     [r15+rdi*2], r12w
0x18000562b  jnz     short loc_180005623
0x18000562d  add     di, di
0x180005630  movzx   eax, di
0x180005633  movzx   edx, ax
0x180005636  add     eax, 15h
0x180005639  and     eax, r9d
0x18000563c  mov     [rbp+47h+Size], edx
0x18000563f  add     ecx, eax
0x180005641  mov     eax, [rbp+47h+CertSize]
0x180005644  add     eax, 17h
0x180005647  and     eax, r9d
0x18000564a  mov     [rbp+47h+var_A0], eax
0x18000564d  add     eax, 34h ; '4'
0x180005650  add     eax, ecx
0x180005652  mov     ecx, r8d; uFlags
0x180005655  mov     edx, eax; uBytes
0x180005657  mov     [rbp+47h+InputBuffer], eax
0x18000565a  mov     r12d, eax
0x18000565d  call    cs:__imp_LocalAlloc
0x180005663  mov     rdi, rax
0x180005666  test    rax, rax
0x180005669  jnz     short loc_180005678
0x18000566b  call    cs:__imp_GetLastError
0x180005671  mov     ebx, eax
0x180005673  jmp     loc_18000595B
0x180005678  lea     rcx, [rax+8]; pszDest
0x18000567c  mov     edx, 8; cbDest
0x180005681  lea     r8, aHttps; "Https:"
0x180005688  call    StringCbCopyA
0x18000568d  test    eax, eax
0x18000568f  jns     short loc_18000569C
0x180005691  movzx   ebx, ax
0x180005694  xor     r14d, r14d
0x180005697  jmp     loc_18000593E
0x18000569c  mov     dword ptr [rdi+4], 700h
0x1800056a3  lea     rsi, [rdi+10h]
0x1800056a7  mov     dword ptr [rdi], 10h
0x1800056ad  test    r14, r14
0x1800056b0  jz      short loc_180005709
0x1800056b2  lea     rcx, [rsi+8]; pszDest
0x1800056b6  mov     edx, 0Ah; cbDest
0x1800056bb  lea     r8, aPassword; "Password"
0x1800056c2  call    StringCbCopyA
0x1800056c7  test    eax, eax
0x1800056c9  js      short loc_180005691
0x1800056cb  movzx   edx, bx
0x1800056ce  lea     rcx, [rsi+12h]; pszDest
0x1800056d2  add     rdx, 2; cbDest
0x1800056d6  mov     byte ptr [rsi+5], 9
0x1800056da  mov     r8, r14; pszSrc
0x1800056dd  call    StringCbCopyW
0x1800056e2  xor     r14d, r14d
0x1800056e5  test    eax, eax
0x1800056e7  jns     short loc_1800056F1
0x1800056e9  movzx   ebx, ax
0x1800056ec  jmp     loc_18000593E
0x1800056f1  mov     [rsi+6], bx
0x1800056f5  movzx   ebx, bx
0x1800056f8  add     ebx, 15h
0x1800056fb  mov     [rsi+4], r14b
0x1800056ff  and     ebx, 0FFFFFFFCh
0x180005702  mov     [rsi], ebx
0x180005704  add     rbx, rsi
0x180005707  jmp     short loc_18000570F
0x180005709  mov     rbx, rsi
0x18000570c  xor     r14d, r14d
0x18000570f  test    r15, r15
0x180005712  jz      short loc_180005761
0x180005714  lea     rcx, [rbx+8]; pszDest
0x180005718  mov     edx, 0Ah; cbDest
0x18000571d  lea     r8, aUsername; "UserName"
0x180005724  call    StringCbCopyA
0x180005729  test    eax, eax
0x18000572b  js      short loc_1800056E9
0x18000572d  mov     esi, [rbp+47h+Size]
0x180005730  lea     rcx, [rbx+12h]; pszDest
0x180005734  movzx   edx, si
0x180005737  mov     r8, r15; pszSrc
0x18000573a  add     rdx, 2; cbDest
0x18000573e  mov     byte ptr [rbx+5], 9
0x180005742  call    StringCbCopyW
0x180005747  test    eax, eax
0x180005749  js      short loc_1800056E9
0x18000574b  movzx   ecx, si
0x18000574e  add     ecx, 15h
0x180005751  mov     [rbx+6], si
0x180005755  and     ecx, 0FFFFFFFCh
0x180005758  mov     [rbx+4], r14b
0x18000575c  mov     [rbx], ecx
0x18000575e  add     rbx, rcx
0x180005761  lea     rcx, [rbx+8]; pszDest
0x180005765  mov     edx, 0Ch; cbDest
0x18000576a  lea     r8, aClientCert; "Client-Cert"
0x180005771  call    StringCbCopyA
0x180005776  test    eax, eax
0x180005778  js      loc_1800056E9
0x18000577e  mov     esi, [rbp+47h+CertSize]
0x180005781  lea     rcx, [rbx+14h]; void *
0x180005785  mov     rdx, [rbp+47h+ClientCert]; Src
0x180005789  mov     r8d, esi; Size
0x18000578c  mov     byte ptr [rbx+5], 0Bh
0x180005790  call    memcpy_0
0x180005795  mov     eax, [rbp+47h+var_A0]
0x180005798  lea     r8, aType; "Type"
0x18000579f  mov     r11d, 8
0x1800057a5  mov     [rbx+6], si
0x1800057a9  mov     edx, r11d; cbDest
0x1800057ac  mov     [rbx], eax
0x1800057ae  mov     [rbx+4], r14b
0x1800057b2  mov     r10d, eax
0x1800057b5  lea     rcx, [rax+8]
0x1800057b9  add     rcx, rbx; pszDest
0x1800057bc  call    StringCbCopyA
0x1800057c1  test    eax, eax
0x1800057c3  js      loc_1800056E9
0x1800057c9  mov     dword ptr [r10+rbx+4], 40700h
0x1800057d2  lea     rcx, [r10+1Ch]
0x1800057d6  mov     dword ptr [r10+rbx+10h], 1
0x1800057df  lea     r8, aMrxdav; "mrxdav"
0x1800057e6  add     rcx, rbx; pszDest
0x1800057e9  mov     dword ptr [r10+rbx], 14h
0x1800057f1  mov     edx, r11d; cbDest
0x1800057f4  lea     r15d, [r11-1]
0x1800057f8  call    StringCbCopyA
0x1800057fd  test    eax, eax
0x1800057ff  js      loc_1800056E9
0x180005805  mov     esi, [rbp+47h+InputBuffer]
0x180005808  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x18000580c  mov     [rsp+110h+EaLength], esi; EaLength
0x180005810  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180005814  mov     [rsp+110h+EaBuffer], rdi; EaBuffer
0x180005819  lea     rcx, [rbp+47h+FileHandle]; FileHandle
0x18000581d  mov     [rsp+110h+CreateOptions], 0A0h; CreateOptions
0x180005825  mov     edx, 100000h; DesiredAccess
0x18000582a  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x180005832  mov     [rsp+110h+ShareAccess], r15d; ShareAccess
0x180005837  mov     [rsp+110h+FileAttributes], 2; FileAttributes
0x18000583f  mov     [rsp+110h+AllocationSize], r14; AllocationSize
0x180005844  mov     dword ptr [r10+rbx+18h], 700h
0x18000584d  mov     [r10+rbx+14h], r14d
0x180005852  call    cs:__imp_NtCreateFile
0x180005858  mov     ebx, eax
0x18000585a  test    eax, eax
0x18000585c  jnz     loc_1800058FF
0x180005862  mov     [rsp+110h+EaLength], esi; EaLength
0x180005866  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x18000586a  mov     [rsp+110h+EaBuffer], rdi; EaBuffer
0x18000586f  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180005873  mov     [rsp+110h+CreateOptions], 21h ; '!'; CreateOptions
0x18000587b  lea     rcx, [rbp+47h+Handle]; FileHandle
0x18000587f  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x180005887  mov     edx, 100001h; DesiredAccess
0x18000588c  mov     [rsp+110h+ShareAccess], r15d; ShareAccess
0x180005891  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x180005899  mov     [rsp+110h+AllocationSize], r14; AllocationSize
0x18000589e  call    cs:__imp_NtCreateFile
0x1800058a4  mov     ebx, eax
0x1800058a6  test    eax, eax
0x1800058a8  jz      short loc_1800058F5
0x1800058aa  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x1800058ae  lea     rax, [rbp+47h+InputBuffer]
0x1800058b2  mov     dword ptr [rsp+110h+EaBuffer], r14d; OutputBufferLength
0x1800058b7  xor     r9d, r9d; ApcContext
0x1800058ba  mov     qword ptr [rsp+110h+CreateOptions], r14; OutputBuffer
0x1800058bf  xor     r8d, r8d; ApcRoutine
0x1800058c2  mov     [rsp+110h+CreateDisposition], 4; InputBufferLength
0x1800058ca  xor     edx, edx; Event
0x1800058cc  mov     qword ptr [rsp+110h+ShareAccess], rax; InputBuffer
0x1800058d1  lea     rax, [rbp+47h+IoStatusBlock]
0x1800058d5  mov     [rsp+110h+FileAttributes], 4000020h; FsControlCode
0x1800058dd  mov     [rsp+110h+AllocationSize], rax; IoStatusBlock
0x1800058e2  mov     [rbp+47h+InputBuffer], 2
  ... truncated ...
```
