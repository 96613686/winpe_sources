# CFileDownload_DMChannel::GetBlockDataWithIndex(long,tagSAFEARRAY * &)

- ea: `0x180011760`
- end: `0x180011979`
- name: `?GetBlockDataWithIndex@CFileDownload_DMChannel@@QEAAJJAEAPEAUtagSAFEARRAY@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(CFileDownload_DMChannel *__hidden this, int, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000a010`

## callees

- `0x18000108c`
- `0x1800116a4`
- `0x180011760`
- `0x1800119fc`
- `0x180011be8`
- `0x180011e94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001193f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001193f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800117a8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180011951`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800117a8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180011951`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180011875`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180011875`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800118f9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800118f9`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180011852`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180011852`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800118b4`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800118b4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800118ec`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800118ec`

## pseudocode

```c
__int64 __fastcall CFileDownload_DMChannel::GetBlockDataWithIndex(
        CFileDownload_DMChannel *this,
        int a2,
        struct tagSAFEARRAY **a3)
{
  __int64 v3; // rdi
  SAFEARRAY *v5; // rcx
  int v8; // ecx
  signed int LogFileSize; // ebx
  int v10; // r8d
  int v11; // r9d
  DWORD LowPart; // r12d
  ULONG v13; // r14d
  unsigned int v14; // edi
  unsigned int v15; // r12d
  SAFEARRAY *Vector; // rax
  _BYTE *v17; // rcx
  __int64 v18; // rax
  signed int LastError; // eax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-20h] BYREF
  HANDLE hFile; // [rsp+38h] [rbp-18h] BYREF
  void *ppvData; // [rsp+40h] [rbp-10h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+90h] [rbp+40h] BYREF
  int v25; // [rsp+98h] [rbp+48h] BYREF

  v3 = -1;
  v25 = 0;
  hFile = (HANDLE)-1LL;
  v5 = *a3;
  NumberOfBytesRead = 0;
  ppvData = 0;
  if ( v5 )
    SafeArrayDestroy(v5);
  *a3 = 0;
  liDistanceToMove.QuadPart = 0;
  LogFileSize = CFileDownload_DMChannel::GetLogFileSize(this, &liDistanceToMove);
  if ( LogFileSize >= 0 )
  {
    LowPart = liDistanceToMove.LowPart;
    LogFileSize = CFileDownload_DMChannel::GetBlockSizeKB(this, &v25);
    if ( LogFileSize >= 0 )
    {
      liDistanceToMove.LowPart = 0;
      LogFileSize = CFileDownload_DMChannel::GetBlockCount(this, (int *)&liDistanceToMove);
      if ( LogFileSize >= 0 )
      {
        if ( a2 < 0 || a2 >= (int)liDistanceToMove.LowPart )
        {
          LogFileSize = -2147024809;
        }
        else
        {
          LogFileSize = CFileDownload_DMChannel::OpenLogFile(this, &hFile);
          if ( LogFileSize < 0 )
          {
LABEL_13:
            v3 = (__int64)hFile;
            goto LABEL_23;
          }
          v13 = v25 << 10;
          v14 = a2 * (v25 << 10);
          v15 = LowPart - v14;
          if ( v15 < v25 << 10 )
            v13 = v15;
          Vector = SafeArrayCreateVector(0x11u, 0, v13);
          *a3 = Vector;
          if ( !Vector )
          {
            LogFileSize = -2147024882;
            goto LABEL_13;
          }
          LogFileSize = SafeArrayAccessData(Vector, &ppvData);
          if ( LogFileSize < 0 )
            goto LABEL_13;
          v17 = ppvData;
          v18 = v13;
          if ( v13 )
          {
            do
            {
              *v17++ = 0;
              --v18;
            }
            while ( v18 );
          }
          liDistanceToMove.QuadPart = v14;
          v3 = (__int64)hFile;
          if ( SetFilePointerEx(hFile, liDistanceToMove, 0, 0)
            && ReadFile((HANDLE)v3, ppvData, v13, &NumberOfBytesRead, 0) )
          {
            SafeArrayUnaccessData(*a3);
          }
          else
          {
            LastError = GetLastError();
            LogFileSize = LastError;
            if ( LastError > 0 )
              LogFileSize = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
  }
LABEL_23:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    liDistanceToMove.LowPart = LogFileSize;
    v25 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)&word_18003FB16,
      v10,
      v11,
      (__int64)&v25,
      (__int64)&liDistanceToMove);
  }
  if ( v3 != -1 )
    CloseHandle((HANDLE)v3);
  if ( LogFileSize < 0 && !*a3 )
  {
    SafeArrayDestroy(0);
    *a3 = 0;
  }
  return (unsigned int)LogFileSize;
}

```

## disassembly

```asm
0x180011760  mov     [rsp-28h+arg_0], rbx
0x180011765  mov     [rsp-28h+arg_8], rsi
0x18001176a  push    rbp
0x18001176b  push    rdi
0x18001176c  push    r12
0x18001176e  push    r14
0x180011770  push    r15
0x180011772  mov     rbp, rsp
0x180011775  sub     rsp, 50h
0x180011779  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001177d  mov     [rbp+arg_18], 0
0x180011784  mov     r14, rcx
0x180011787  mov     [rbp+hFile], rdi
0x18001178b  mov     rcx, [r8]; psa
0x18001178e  mov     rsi, r8
0x180011791  mov     [rbp+NumberOfBytesRead], 0
0x180011798  mov     r15d, edx
0x18001179b  mov     [rbp+ppvData], 0
0x1800117a3  test    rcx, rcx
0x1800117a6  jz      short loc_1800117AE
0x1800117a8  call    cs:__imp_SafeArrayDestroy
0x1800117ae  lea     rdx, [rbp+liDistanceToMove]; union _LARGE_INTEGER *
0x1800117b2  mov     qword ptr [rsi], 0
0x1800117b9  mov     rcx, r14; this
0x1800117bc  mov     qword ptr [rbp+liDistanceToMove], 0
0x1800117c4  call    ?GetLogFileSize@CFileDownload_DMChannel@@IEAAJAEAT_LARGE_INTEGER@@@Z; CFileDownload_DMChannel::GetLogFileSize(_LARGE_INTEGER &)
0x1800117c9  mov     ebx, eax
0x1800117cb  test    eax, eax
0x1800117cd  js      loc_180011906
0x1800117d3  mov     r12d, dword ptr [rbp+liDistanceToMove]
0x1800117d7  lea     rdx, [rbp+arg_18]; int *
0x1800117db  mov     rcx, r14; this
0x1800117de  call    ?GetBlockSizeKB@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockSizeKB(long &)
0x1800117e3  mov     ebx, eax
0x1800117e5  test    eax, eax
0x1800117e7  js      loc_180011906
0x1800117ed  lea     rdx, [rbp+liDistanceToMove]; int *
0x1800117f1  mov     dword ptr [rbp+liDistanceToMove], 0
0x1800117f8  mov     rcx, r14; this
0x1800117fb  call    ?GetBlockCount@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockCount(long &)
0x180011800  mov     ebx, eax
0x180011802  test    eax, eax
0x180011804  js      loc_180011906
0x18001180a  test    r15d, r15d
0x18001180d  js      loc_180011901
0x180011813  cmp     r15d, dword ptr [rbp+liDistanceToMove]
0x180011817  jge     loc_180011901
0x18001181d  lea     rdx, [rbp+hFile]; void **
0x180011821  mov     rcx, r14; this
0x180011824  call    ?OpenLogFile@CFileDownload_DMChannel@@IEAAJAEAPEAX@Z; CFileDownload_DMChannel::OpenLogFile(void * &)
0x180011829  mov     ebx, eax
0x18001182b  test    eax, eax
0x18001182d  js      short loc_180011865
0x18001182f  mov     r14d, [rbp+arg_18]
0x180011833  mov     ecx, 11h; vt
0x180011838  shl     r14d, 0Ah
0x18001183c  mov     edi, r14d
0x18001183f  imul    edi, r15d
0x180011843  sub     r12d, edi
0x180011846  cmp     r12d, r14d
0x180011849  cmovb   r14d, r12d
0x18001184d  xor     edx, edx; lLbound
0x18001184f  mov     r8d, r14d; cElements
0x180011852  call    cs:__imp_SafeArrayCreateVector
0x180011858  mov     [rsi], rax
0x18001185b  test    rax, rax
0x18001185e  jnz     short loc_18001186E
0x180011860  mov     ebx, 8007000Eh
0x180011865  mov     rdi, [rbp+hFile]
0x180011869  jmp     loc_180011906
0x18001186e  lea     rdx, [rbp+ppvData]; ppvData
0x180011872  mov     rcx, rax; psa
0x180011875  call    cs:__imp_SafeArrayAccessData
0x18001187b  mov     ebx, eax
0x18001187d  test    eax, eax
0x18001187f  js      short loc_180011865
0x180011881  mov     rcx, [rbp+ppvData]
0x180011885  mov     eax, r14d
0x180011888  test    r14d, r14d
0x18001188b  jz      short loc_180011899
0x18001188d  mov     byte ptr [rcx], 0
0x180011890  inc     rcx
0x180011893  sub     rax, 1
0x180011897  jnz     short loc_18001188D
0x180011899  mov     dword ptr [rbp+liDistanceToMove], edi
0x18001189c  xor     r9d, r9d; dwMoveMethod
0x18001189f  mov     rdi, [rbp+hFile]
0x1800118a3  xor     r8d, r8d; lpNewFilePointer
0x1800118a6  mov     dword ptr [rbp+liDistanceToMove+4], 0
0x1800118ad  mov     rcx, rdi; hFile
0x1800118b0  mov     rdx, qword ptr [rbp+liDistanceToMove]; liDistanceToMove
0x1800118b4  call    cs:__imp_SetFilePointerEx
0x1800118ba  test    eax, eax
0x1800118bc  jnz     short loc_1800118D5
0x1800118be  call    cs:__imp_GetLastError
0x1800118c4  mov     ebx, eax
0x1800118c6  test    eax, eax
0x1800118c8  jle     short loc_180011906
0x1800118ca  movzx   ebx, ax
0x1800118cd  or      ebx, 80070000h
0x1800118d3  jmp     short loc_180011906
0x1800118d5  mov     rdx, [rbp+ppvData]; lpBuffer
0x1800118d9  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800118dd  mov     r8d, r14d; nNumberOfBytesToRead
0x1800118e0  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x1800118e9  mov     rcx, rdi; hFile
0x1800118ec  call    cs:__imp_ReadFile
0x1800118f2  test    eax, eax
0x1800118f4  jz      short loc_1800118BE
0x1800118f6  mov     rcx, [rsi]; psa
0x1800118f9  call    cs:__imp_SafeArrayUnaccessData
0x1800118ff  jmp     short loc_180011906
0x180011901  mov     ebx, 80070057h
0x180011906  mov     eax, cs:dword_180048E90
0x18001190c  cmp     eax, 5
0x18001190f  jbe     short loc_180011936
0x180011911  lea     rax, [rbp+liDistanceToMove]
0x180011915  mov     dword ptr [rbp+liDistanceToMove], ebx
0x180011918  mov     [rsp+50h+var_28], rax
0x18001191d  lea     rdx, word_18003FB16
0x180011924  lea     rax, [rbp+arg_18]
0x180011928  mov     [rbp+arg_18], r15d
0x18001192c  mov     [rsp+50h+lpOverlapped], rax
0x180011931  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011936  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001193a  jz      short loc_180011945
0x18001193c  mov     rcx, rdi; hObject
0x18001193f  call    cs:__imp_CloseHandle
0x180011945  test    ebx, ebx
0x180011947  jns     short loc_18001195E
0x180011949  cmp     qword ptr [rsi], 0
0x18001194d  jnz     short loc_18001195E
0x18001194f  xor     ecx, ecx; psa
0x180011951  call    cs:__imp_SafeArrayDestroy
0x180011957  mov     qword ptr [rsi], 0
0x18001195e  lea     r11, [rsp+50h+var_s0]
0x180011963  mov     eax, ebx
0x180011965  mov     rbx, [r11+30h]
0x180011969  mov     rsi, [r11+38h]
0x18001196d  mov     rsp, r11
0x180011970  pop     r15
0x180011972  pop     r14
0x180011974  pop     r12
0x180011976  pop     rdi
0x180011977  pop     rbp
0x180011978  retn
```
