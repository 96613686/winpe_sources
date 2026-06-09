# InternalFtpGetFileW

- ea: `0x180174810`
- end: `0x180174cbc`
- name: `InternalFtpGetFileW`
- size: `1196`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, int, unsigned int, __int64, int)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops`

## callers

- `0x180173410`
- `0x180173f60`

## callees

- `0x180003c40`
- `0x1800388a4`
- `0x180039788`
- `0x18003a870`
- `0x18003e350`
- `0x180053788`
- `0x180064060`
- `0x1800641c0`
- `0x180065860`
- `0x18006625c`
- `0x1800701d0`
- `0x18007ad20`
- `0x1800bdee8`
- `0x1800d7824`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x180170564`
- `0x1801730cc`
- `0x180174810`
- `0x1801d3508`
- `0x1801e1790`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180174a09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180174a09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180174b53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180174b53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180174c7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180174c7a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180174b94`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180174b94`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180174c97`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180174c97`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180174c47`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180174c47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180174c89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180174c89`

## pseudocode

```c
__int64 __fastcall InternalFtpGetFileW(
        void *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        DWORD a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        int a8)
{
  unsigned int v9; // r15d
  __int64 v12; // rcx
  DWORD LastError; // ebx
  unsigned int v14; // edi
  __int64 v15; // rdx
  int v16; // ecx
  unsigned __int64 v18; // rsi
  CFsm_FtpGetFile *v19; // rax
  CFsm_FtpGetFile *v20; // rbx
  CFsm_FtpGetFile *File; // rax
  HINTERNET v22; // rbx
  __int64 v23; // r14
  __int64 FileW; // r12
  unsigned int v25; // eax
  __int64 v26; // rcx
  unsigned __int8 *v27; // rsi
  __int64 v28; // rax
  int v29; // [rsp+60h] [rbp-61h] BYREF
  unsigned int v30; // [rsp+64h] [rbp-5Dh]
  BOOL v31; // [rsp+68h] [rbp-59h]
  __int64 ThreadInfo; // [rsp+70h] [rbp-51h]
  unsigned __int64 v33; // [rsp+78h] [rbp-49h]
  LPCWSTR lpFileName; // [rsp+80h] [rbp-41h]
  HINTERNET hInternet; // [rsp+88h] [rbp-39h]
  unsigned int Buffer; // [rsp+90h] [rbp-31h] BYREF
  HANDLE_OBJECT *v37; // [rsp+98h] [rbp-29h] BYREF
  HANDLE_OBJECT *v38; // [rsp+A0h] [rbp-21h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+A8h] [rbp-19h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+ACh] [rbp-15h] BYREF
  DWORD dwBufferLength; // [rsp+B0h] [rbp-11h] BYREF

  v9 = a6;
  hInternet = a1;
  v12 = a5;
  v30 = a5;
  v33 = a7;
  nNumberOfBytesToWrite = a4;
  lpFileName = a3;
  if ( (xmmword_180266B60 & 0x80u) != 0LL )
    WPP_SF_qSSlDDPl(a5, (_DWORD)a2, (_DWORD)a3, (_DWORD)a1, (__int64)a2, (__int64)a3, a4, a5, a6, a7, a8);
  v37 = 0;
  v38 = 0;
  if ( !GlobalDataInitialized )
  {
    LastError = 12172;
    goto LABEL_26;
  }
  ThreadInfo = InternetGetThreadInfo(v12, a2, a3);
  if ( !ThreadInfo )
  {
    LastError = 12004;
LABEL_26:
    v14 = 0;
    if ( (xmmword_180266B50 & 4) != 0 )
      WPP_SF_d(514, 20, &WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids, LastError);
    goto LABEL_28;
  }
  v14 = 1;
  v31 = 1;
  LastError = MapHandleToAddress(a1, &v37, 0);
  if ( !LastError || v37 )
  {
    InternetSetObjectHandle(ThreadInfo, a1, v37);
    InternetSetContext(ThreadInfo, v33);
    InternetSetLastError(ThreadInfo, v15, 0, 0, 0);
    if ( !LastError )
    {
      NumberOfBytesWritten = 0;
      v29 = 0;
      LastError = RIsHandleLocal(v37, &NumberOfBytesWritten, &v29, 1852785478);
      if ( !LastError )
      {
        v16 = *(_DWORD *)(ThreadInfo + 64);
        if ( !v16 || !a8 )
        {
          if ( !a2 || !*a2 || !a3 || !*a3 )
            goto LABEL_19;
          if ( (a6 & 3) != 0 )
          {
            if ( (a6 & 3) - 1 > 1 )
            {
LABEL_19:
              LastError = 87;
              goto LABEL_20;
            }
          }
          else
          {
            v9 = a6 | 2;
          }
          if ( !v16 )
          {
            if ( v29 )
            {
              v18 = v33;
              if ( v33 )
              {
                v19 = (CFsm_FtpGetFile *)operator new(0xF8u);
                v20 = v19;
                if ( v19
                  && (memset_0(v19, 0, 0xF8u),
                      (File = CFsm_FtpGetFile::CFsm_FtpGetFile(v20, a1, v18, a2, a3, nNumberOfBytesToWrite, v30, v9)) != 0) )
                {
                  if ( *((_DWORD *)File + 10) )
                  {
                    LastError = *((_DWORD *)File + 10);
                    (**(void (__fastcall ***)(CFsm_FtpGetFile *, __int64))File)(File, 1);
                  }
                  else
                  {
                    LastError = CFsm::InternalQueueWorkItem(File, 1);
                    v31 = LastError != 997;
                  }
                }
                else
                {
                  LastError = 8;
                }
                if ( (xmmword_180266B60 & 0x80u) != 0LL )
                  WPP_SF_d(1031, 19, &WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids, LastError);
                goto LABEL_20;
              }
            }
          }
        }
        v22 = hInternet;
        v23 = 0;
        Buffer = 0;
        FileW = -1;
        dwBufferLength = 4;
        if ( InternetQueryOptionA(hInternet, 0xCu, &Buffer, &dwBufferLength) )
        {
          v25 = Buffer;
        }
        else
        {
          v25 = 4096;
          Buffer = 4096;
        }
        v27 = (unsigned __int8 *)HeapAlloc(g_hWxProcessHeap, 0, v25);
        if ( v27
          && (FileW = (__int64)CreateFileW(
                                 lpFileName,
                                 0x40000000u,
                                 0,
                                 0,
                                 2 - (unsigned int)(nNumberOfBytesToWrite != 0),
                                 v30 | 0x8000000,
                                 0),
              FileW != -1)
          && (v28 = InternalFtpOpenFileW(v22, a2, 0x80000000LL, v9, v33, 1), (v23 = v28) != 0) )
        {
          LastError = MapHandleToAddress(v28, &v38, 0);
          DereferenceObject(v38);
          if ( !LastError )
          {
            while ( 1 )
            {
              nNumberOfBytesToWrite = 0;
              if ( (unsigned int)HANDLE_OBJECT::IsInvalidated(v38) || (unsigned int)HANDLE_OBJECT::IsInvalidated(v37) )
                break;
              if ( !(unsigned int)FtpReadFile(v38, v27, Buffer, &nNumberOfBytesToWrite) )
                goto LABEL_58;
              if ( !nNumberOfBytesToWrite )
              {
                LastError = 0;
                goto LABEL_59;
              }
              NumberOfBytesWritten = 0;
              if ( !WriteFile((HANDLE)FileW, v27, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
                goto LABEL_58;
            }
            LastError = 12017;
          }
        }
        else
        {
LABEL_58:
          LastError = WxGetLastError(v26);
          if ( !v27 )
            goto LABEL_60;
        }
LABEL_59:
        HeapFree(g_hWxProcessHeap, 0, v27);
LABEL_60:
        if ( FileW != -1 )
        {
          CloseHandle((HANDLE)FileW);
          if ( LastError )
            DeleteFileW(lpFileName);
        }
        if ( v23 )
          InternetCloseHandle(v23);
        InternetSetContext(ThreadInfo, v33);
      }
    }
  }
LABEL_20:
  if ( v38 )
    DereferenceObject(v38);
  if ( v37 && v31 )
    DereferenceObject(v37);
  if ( LastError )
    goto LABEL_26;
LABEL_28:
  if ( (xmmword_180266B60 & 0x80u) != 0LL )
    WPP_SF_d(1031, 21, &WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids, v14);
  SetLastError(LastError);
  return v14;
}

```

## disassembly

```asm
0x180174810  push    rbp
0x180174812  push    rbx
0x180174813  push    rsi
0x180174814  push    rdi
0x180174815  push    r12
0x180174817  push    r13
0x180174819  push    r14
0x18017481b  push    r15
0x18017481d  lea     rbp, [rsp-7]
0x180174822  sub     rsp, 0C8h
0x180174829  mov     rax, cs:__security_cookie
0x180174830  xor     rax, rsp
0x180174833  mov     [rbp+3Fh+var_48], rax
0x180174837  mov     rax, [rbp+3Fh+arg_30]
0x18017483b  mov     r14, rcx
0x18017483e  mov     r15d, [rbp+3Fh+arg_28]
0x180174842  mov     r12, r8
0x180174845  mov     [rbp+3Fh+hInternet], rcx
0x180174849  mov     r13, rdx
0x18017484c  mov     ecx, [rbp+3Fh+arg_20]
0x18017484f  mov     [rbp+3Fh+var_9C], ecx
0x180174852  mov     [rbp+3Fh+var_88], rax
0x180174856  mov     [rbp+3Fh+nNumberOfBytesToWrite], r9d
0x18017485a  mov     [rbp+3Fh+lpFileName], r8
0x18017485e  mov     esi, [rbp+3Fh+arg_38]
0x180174864  xor     ebx, ebx
0x180174866  cmp     byte ptr cs:xmmword_180266B60, bl
0x18017486c  jge     short loc_180174897
0x18017486e  mov     [rsp+100h+var_B0], esi
0x180174872  mov     [rsp+100h+var_B8], rax
0x180174877  mov     [rsp+100h+var_C0], r15d
0x18017487c  mov     [rsp+100h+var_C8], ecx
0x180174880  mov     dword ptr [rsp+100h+hTemplateFile], r9d
0x180174885  mov     r9, r14
0x180174888  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], r8
0x18017488d  mov     qword ptr [rsp+100h+dwCreationDisposition], rdx
0x180174892  call    WPP_SF_qSSlDDPl
0x180174897  cmp     cs:GlobalDataInitialized, ebx
0x18017489d  mov     [rbp+3Fh+var_68], rbx
0x1801748a1  mov     [rbp+3Fh+var_60], rbx
0x1801748a5  jnz     short loc_1801748B4
0x1801748a7  mov     ebx, 2F8Ch
0x1801748ac  xor     r15d, r15d
0x1801748af  jmp     loc_1801749C0
0x1801748b4  call    InternetGetThreadInfo
0x1801748b9  mov     [rbp+3Fh+var_90], rax
0x1801748bd  test    rax, rax
0x1801748c0  jnz     short loc_1801748C9
0x1801748c2  mov     ebx, 2EE4h
0x1801748c7  jmp     short loc_1801748AC
0x1801748c9  mov     edi, 1
0x1801748ce  lea     rdx, [rbp+3Fh+var_68]
0x1801748d2  xor     r8d, r8d
0x1801748d5  mov     [rbp+3Fh+var_98], edi
0x1801748d8  mov     rcx, r14
0x1801748db  call    MapHandleToAddress
0x1801748e0  mov     ebx, eax
0x1801748e2  xor     eax, eax
0x1801748e4  test    ebx, ebx
0x1801748e6  jz      short loc_1801748F2
0x1801748e8  cmp     [rbp+3Fh+var_68], rax
0x1801748ec  jz      loc_180174997
0x1801748f2  mov     r8, [rbp+3Fh+var_68]
0x1801748f6  mov     rdx, r14
0x1801748f9  mov     rcx, [rbp+3Fh+var_90]
0x1801748fd  call    _InternetSetObjectHandle
0x180174902  mov     rdx, [rbp+3Fh+var_88]
0x180174906  mov     rcx, [rbp+3Fh+var_90]
0x18017490a  call    _InternetSetContext
0x18017490f  mov     rcx, [rbp+3Fh+var_90]
0x180174913  xor     r9d, r9d
0x180174916  xor     r8d, r8d
0x180174919  mov     [rsp+100h+dwCreationDisposition], 0
0x180174921  call    _InternetSetLastError
0x180174926  xor     eax, eax
0x180174928  test    ebx, ebx
0x18017492a  jnz     short loc_180174997
0x18017492c  mov     rcx, [rbp+3Fh+var_68]
0x180174930  lea     r8, [rbp+3Fh+var_A0]
0x180174934  mov     r9d, 6E6F4346h
0x18017493a  mov     [rbp+3Fh+NumberOfBytesWritten], eax
0x18017493d  lea     rdx, [rbp+3Fh+NumberOfBytesWritten]
0x180174941  mov     [rbp+3Fh+var_A0], eax
0x180174944  call    RIsHandleLocal
0x180174949  xor     edx, edx
0x18017494b  mov     ebx, eax
0x18017494d  test    eax, eax
0x18017494f  jnz     short loc_180174997
0x180174951  mov     rax, [rbp+3Fh+var_90]
0x180174955  mov     ecx, [rax+40h]
0x180174958  test    ecx, ecx
0x18017495a  jz      short loc_180174964
0x18017495c  test    esi, esi
0x18017495e  jnz     loc_180174B0C
0x180174964  test    r13, r13
0x180174967  jz      short loc_180174992
0x180174969  cmp     [r13+0], dx
0x18017496e  jz      short loc_180174992
0x180174970  test    r12, r12
0x180174973  jz      short loc_180174992
0x180174975  cmp     [r12], dx
0x18017497a  jz      short loc_180174992
0x18017497c  mov     eax, r15d
0x18017497f  and     eax, 3
0x180174982  jz      loc_180174A31
0x180174988  dec     eax
0x18017498a  cmp     eax, edi
0x18017498c  jbe     loc_180174A35
0x180174992  mov     ebx, 57h ; 'W'
0x180174997  xor     r15d, r15d
0x18017499a  mov     rcx, [rbp+3Fh+var_60]
0x18017499e  test    rcx, rcx
0x1801749a1  jz      short loc_1801749A8
0x1801749a3  call    DereferenceObject
0x1801749a8  mov     rcx, [rbp+3Fh+var_68]
0x1801749ac  test    rcx, rcx
0x1801749af  jz      short loc_1801749BC
0x1801749b1  cmp     [rbp+3Fh+var_98], r15d
0x1801749b5  jz      short loc_1801749BC
0x1801749b7  call    DereferenceObject
0x1801749bc  test    ebx, ebx
0x1801749be  jz      short loc_1801749E5
0x1801749c0  mov     edi, r15d
0x1801749c3  test    byte ptr cs:xmmword_180266B50, 4
0x1801749ca  jz      short loc_1801749E5
0x1801749cc  mov     edx, 14h
0x1801749d1  lea     r8, WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids
0x1801749d8  mov     ecx, 202h
0x1801749dd  mov     r9d, ebx
0x1801749e0  call    WPP_SF_d
0x1801749e5  cmp     byte ptr cs:xmmword_180266B60, r15b
0x1801749ec  jge     short loc_180174A07
0x1801749ee  mov     edx, 15h
0x1801749f3  lea     r8, WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids
0x1801749fa  mov     ecx, 407h
0x1801749ff  mov     r9d, edi
0x180174a02  call    WPP_SF_d
0x180174a07  mov     ecx, ebx; dwErrCode
0x180174a09  call    cs:__imp_SetLastError
0x180174a0f  mov     eax, edi
0x180174a11  mov     rcx, [rbp+3Fh+var_48]
0x180174a15  xor     rcx, rsp; StackCookie
0x180174a18  call    __security_check_cookie
0x180174a1d  add     rsp, 0C8h
0x180174a24  pop     r15
0x180174a26  pop     r14
0x180174a28  pop     r13
0x180174a2a  pop     r12
0x180174a2c  pop     rdi
0x180174a2d  pop     rsi
0x180174a2e  pop     rbx
0x180174a2f  pop     rbp
0x180174a30  retn
0x180174a31  or      r15d, 2
0x180174a35  test    ecx, ecx
0x180174a37  jnz     loc_180174B0C
0x180174a3d  cmp     [rbp+3Fh+var_A0], edx
0x180174a40  jz      loc_180174B0C
0x180174a46  mov     rsi, [rbp+3Fh+var_88]
0x180174a4a  test    rsi, rsi
0x180174a4d  jz      loc_180174B0C
0x180174a53  mov     ecx, 0F8h; unsigned __int64
0x180174a58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180174a5d  mov     rbx, rax
0x180174a60  test    rax, rax
0x180174a63  jz      short loc_180174AD9
0x180174a65  xor     edx, edx; Val
0x180174a67  mov     r8d, 0F8h; Size
0x180174a6d  mov     rcx, rax; void *
0x180174a70  call    memset_0
0x180174a75  mov     eax, [rbp+3Fh+var_9C]
0x180174a78  mov     r9, r13; unsigned __int16 *
0x180174a7b  mov     ecx, [rbp+3Fh+nNumberOfBytesToWrite]
0x180174a7e  mov     r8, rsi; unsigned __int64
0x180174a81  mov     [rsp+100h+var_C8], r15d; unsigned int
0x180174a86  mov     rdx, r14; void *
0x180174a89  mov     dword ptr [rsp+100h+hTemplateFile], eax; unsigned int
0x180174a8d  mov     [rsp+100h+dwFlagsAndAttributes], ecx; int
0x180174a91  mov     rcx, rbx; this
0x180174a94  mov     qword ptr [rsp+100h+dwCreationDisposition], r12; unsigned __int16 *
0x180174a99  call    ??0CFsm_FtpGetFile@@QEAA@PEAX_KPEBG2HKK@Z; CFsm_FtpGetFile::CFsm_FtpGetFile(void *,unsigned __int64,ushort const *,ushort const *,int,ulong,ulong)
0x180174a9e  xor     r15d, r15d
0x180174aa1  mov     rcx, rax; this
0x180174aa4  test    rax, rax
0x180174aa7  jz      short loc_180174ADC
0x180174aa9  mov     edx, edi; int
0x180174aab  cmp     [rax+28h], r15d
0x180174aaf  jnz     short loc_180174AC9
0x180174ab1  call    ?InternalQueueWorkItem@CFsm@@AEAAKH@Z; CFsm::InternalQueueWorkItem(int)
0x180174ab6  mov     ebx, eax
0x180174ab8  mov     eax, r15d
0x180174abb  cmp     ebx, 3E5h
0x180174ac1  setnz   al
0x180174ac4  mov     [rbp+3Fh+var_98], eax
0x180174ac7  jmp     short loc_180174AE1
0x180174ac9  mov     ebx, [rax+28h]
0x180174acc  mov     rax, [rax]
0x180174acf  mov     rax, [rax]
0x180174ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174ad7  jmp     short loc_180174AE1
0x180174ad9  xor     r15d, r15d
0x180174adc  mov     ebx, 8
0x180174ae1  cmp     byte ptr cs:xmmword_180266B60, r15b
0x180174ae8  jge     loc_18017499A
0x180174aee  mov     edx, 13h
0x180174af3  lea     r8, WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids
0x180174afa  mov     ecx, 407h
0x180174aff  mov     r9d, ebx
0x180174b02  call    WPP_SF_d
0x180174b07  jmp     loc_18017499A
0x180174b0c  mov     rbx, [rbp+3Fh+hInternet]
0x180174b10  lea     r9, [rbp+3Fh+dwBufferLength]; lpdwBufferLength
0x180174b14  mov     r14, rdx
0x180174b17  mov     [rbp+3Fh+Buffer], edx
0x180174b1a  or      r12, 0FFFFFFFFFFFFFFFFh
0x180174b1e  mov     [rbp+3Fh+dwBufferLength], 4
0x180174b25  lea     r8, [rbp+3Fh+Buffer]; lpBuffer
0x180174b29  mov     rcx, rbx; hInternet
0x180174b2c  lea     edx, [r12+0Dh]; dwOption
0x180174b31  call    InternetQueryOptionA
0x180174b36  test    eax, eax
0x180174b38  jnz     short loc_180174B44
0x180174b3a  mov     eax, 1000h
0x180174b3f  mov     [rbp+3Fh+Buffer], eax
0x180174b42  jmp     short loc_180174B47
0x180174b44  mov     eax, [rbp+3Fh+Buffer]
0x180174b47  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180174b4e  xor     edx, edx; dwFlags
0x180174b50  mov     r8d, eax; dwBytes
0x180174b53  call    cs:__imp_HeapAlloc
0x180174b59  xor     edx, edx
0x180174b5b  mov     rsi, rax
0x180174b5e  test    rax, rax
0x180174b61  jz      loc_180174C5F
0x180174b67  mov     eax, [rbp+3Fh+var_9C]
0x180174b6a  mov     ecx, [rbp+3Fh+nNumberOfBytesToWrite]
0x180174b6d  bts     eax, 1Bh
0x180174b71  neg     ecx
0x180174b73  mov     [rsp+100h+hTemplateFile], rdx; hTemplateFile
0x180174b78  mov     [rsp+100h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180174b7c  mov     edx, 40000000h; dwDesiredAccess
0x180174b81  sbb     ecx, ecx
0x180174b83  xor     r9d, r9d; lpSecurityAttributes
0x180174b86  add     ecx, 2
0x180174b89  xor     r8d, r8d; dwShareMode
0x180174b8c  mov     [rsp+100h+dwCreationDisposition], ecx; dwCreationDisposition
0x180174b90  mov     rcx, [rbp+3Fh+lpFileName]; lpFileName
0x180174b94  call    cs:__imp_CreateFileW
0x180174b9a  mov     r12, rax
0x180174b9d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180174ba1  jz      loc_180174C5F
0x180174ba7  mov     rax, [rbp+3Fh+var_88]
0x180174bab  mov     r9d, r15d
0x180174bae  mov     [rsp+100h+dwFlagsAndAttributes], edi
0x180174bb2  mov     r8d, 80000000h
0x180174bb8  mov     rdx, r13
0x180174bbb  mov     qword ptr [rsp+100h+dwCreationDisposition], rax
0x180174bc0  mov     rcx, rbx
0x180174bc3  call    InternalFtpOpenFileW
0x180174bc8  xor     r15d, r15d
0x180174bcb  mov     r14, rax
0x180174bce  test    rax, rax
0x180174bd1  jz      loc_180174C62
0x180174bd7  xor     r8d, r8d
0x180174bda  lea     rdx, [rbp+3Fh+var_60]
0x180174bde  mov     rcx, rax
0x180174be1  call    MapHandleToAddress
0x180174be6  mov     rcx, [rbp+3Fh+var_60]
0x180174bea  mov     ebx, eax
0x180174bec  call    DereferenceObject
0x180174bf1  test    ebx, ebx
0x180174bf3  jnz     short loc_180174C6E
0x180174bf5  mov     rcx, [rbp+3Fh+var_60]; this
0x180174bf9  mov     [rbp+3Fh+nNumberOfBytesToWrite], r15d
0x180174bfd  call    ?IsInvalidated@HANDLE_OBJECT@@QEBAHXZ; HANDLE_OBJECT::IsInvalidated(void)
0x180174c02  test    eax, eax
0x180174c04  jnz     short loc_180174C58
0x180174c06  mov     rcx, [rbp+3Fh+var_68]; this
0x180174c0a  call    ?IsInvalidated@HANDLE_OBJECT@@QEBAHXZ; HANDLE_OBJECT::IsInvalidated(void)
0x180174c0f  test    eax, eax
0x180174c11  jnz     short loc_180174C58
0x180174c13  mov     r8d, [rbp+3Fh+Buffer]; unsigned int
0x180174c17  lea     r9, [rbp+3Fh+nNumberOfBytesToWrite]; unsigned int *
0x180174c1b  mov     rcx, [rbp+3Fh+var_60]; this
0x180174c1f  mov     rdx, rsi; Src
0x180174c22  call    FtpReadFile
0x180174c27  test    eax, eax
0x180174c29  jz      short loc_180174C62
0x180174c2b  mov     r8d, [rbp+3Fh+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180174c2f  test    r8d, r8d
0x180174c32  jz      short loc_180174C53
0x180174c34  lea     r9, [rbp+3Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180174c38  mov     [rbp+3Fh+NumberOfBytesWritten], r15d
0x180174c3c  mov     rdx, rsi; lpBuffer
0x180174c3f  mov     qword ptr [rsp+100h+dwCreationDisposition], r15; lpOverlapped
0x180174c44  mov     rcx, r12; hFile
0x180174c47  call    cs:__imp_WriteFile
0x180174c4d  test    eax, eax
0x180174c4f  jnz     short loc_180174BF5
0x180174c51  jmp     short loc_180174C62
  ... truncated ...
```
