# CFileDownload_DMChannel::GetBlockDataWithIndex(long,tagSAFEARRAY * &)

- ea: `0x18001209c`
- end: `0x1800122ec`
- name: `?GetBlockDataWithIndex@CFileDownload_DMChannel@@QEAAJJAEAPEAUtagSAFEARRAY@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(CFileDownload_DMChannel *__hidden this, int, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000a320`

## callees

- `0x180001090`
- `0x180011fe0`
- `0x18001209c`
- `0x180012374`
- `0x180012570`
- `0x180012840`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012212`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800122a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800122a5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800120e4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800122bd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800120e4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800122bd`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800121bd`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800121bd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180012259`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180012259`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180012194`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180012194`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180012202`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180012202`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180012246`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180012246`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    liDistanceToMove.LowPart = LogFileSize;
    v25 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)&word_180041B16,
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
0x18001209c  mov     [rsp-28h+arg_0], rbx
0x1800120a1  mov     [rsp-28h+arg_8], rsi
0x1800120a6  push    rbp
0x1800120a7  push    rdi
0x1800120a8  push    r12
0x1800120aa  push    r14
0x1800120ac  push    r15
0x1800120ae  mov     rbp, rsp
0x1800120b1  sub     rsp, 50h
0x1800120b5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800120b9  mov     [rbp+arg_18], 0
0x1800120c0  mov     r14, rcx
0x1800120c3  mov     [rbp+hFile], rdi
0x1800120c7  mov     rcx, [r8]; psa
0x1800120ca  mov     rsi, r8
0x1800120cd  mov     [rbp+NumberOfBytesRead], 0
0x1800120d4  mov     r15d, edx
0x1800120d7  mov     [rbp+ppvData], 0
0x1800120df  test    rcx, rcx
0x1800120e2  jz      short loc_1800120F0
0x1800120e4  call    cs:__imp_SafeArrayDestroy
0x1800120eb  nop     dword ptr [rax+rax+00h]
0x1800120f0  lea     rdx, [rbp+liDistanceToMove]; union _LARGE_INTEGER *
0x1800120f4  mov     qword ptr [rsi], 0
0x1800120fb  mov     rcx, r14; this
0x1800120fe  mov     qword ptr [rbp+liDistanceToMove], 0
0x180012106  call    ?GetLogFileSize@CFileDownload_DMChannel@@IEAAJAEAT_LARGE_INTEGER@@@Z; CFileDownload_DMChannel::GetLogFileSize(_LARGE_INTEGER &)
0x18001210b  mov     ebx, eax
0x18001210d  test    eax, eax
0x18001210f  js      loc_18001226C
0x180012115  mov     r12d, dword ptr [rbp+liDistanceToMove]
0x180012119  lea     rdx, [rbp+arg_18]; int *
0x18001211d  mov     rcx, r14; this
0x180012120  call    ?GetBlockSizeKB@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockSizeKB(long &)
0x180012125  mov     ebx, eax
0x180012127  test    eax, eax
0x180012129  js      loc_18001226C
0x18001212f  lea     rdx, [rbp+liDistanceToMove]; int *
0x180012133  mov     dword ptr [rbp+liDistanceToMove], 0
0x18001213a  mov     rcx, r14; this
0x18001213d  call    ?GetBlockCount@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockCount(long &)
0x180012142  mov     ebx, eax
0x180012144  test    eax, eax
0x180012146  js      loc_18001226C
0x18001214c  test    r15d, r15d
0x18001214f  js      loc_180012267
0x180012155  cmp     r15d, dword ptr [rbp+liDistanceToMove]
0x180012159  jge     loc_180012267
0x18001215f  lea     rdx, [rbp+hFile]; void **
0x180012163  mov     rcx, r14; this
0x180012166  call    ?OpenLogFile@CFileDownload_DMChannel@@IEAAJAEAPEAX@Z; CFileDownload_DMChannel::OpenLogFile(void * &)
0x18001216b  mov     ebx, eax
0x18001216d  test    eax, eax
0x18001216f  js      short loc_1800121AD
0x180012171  mov     r14d, [rbp+arg_18]
0x180012175  mov     ecx, 11h; vt
0x18001217a  shl     r14d, 0Ah
0x18001217e  mov     edi, r14d
0x180012181  imul    edi, r15d
0x180012185  sub     r12d, edi
0x180012188  cmp     r12d, r14d
0x18001218b  cmovb   r14d, r12d
0x18001218f  xor     edx, edx; lLbound
0x180012191  mov     r8d, r14d; cElements
0x180012194  call    cs:__imp_SafeArrayCreateVector
0x18001219b  nop     dword ptr [rax+rax+00h]
0x1800121a0  mov     [rsi], rax
0x1800121a3  test    rax, rax
0x1800121a6  jnz     short loc_1800121B6
0x1800121a8  mov     ebx, 8007000Eh
0x1800121ad  mov     rdi, [rbp+hFile]
0x1800121b1  jmp     loc_18001226C
0x1800121b6  lea     rdx, [rbp+ppvData]; ppvData
0x1800121ba  mov     rcx, rax; psa
0x1800121bd  call    cs:__imp_SafeArrayAccessData
0x1800121c4  nop     dword ptr [rax+rax+00h]
0x1800121c9  mov     ebx, eax
0x1800121cb  test    eax, eax
0x1800121cd  js      short loc_1800121AD
0x1800121cf  mov     rcx, [rbp+ppvData]
0x1800121d3  mov     eax, r14d
0x1800121d6  test    r14d, r14d
0x1800121d9  jz      short loc_1800121E7
0x1800121db  mov     byte ptr [rcx], 0
0x1800121de  inc     rcx
0x1800121e1  sub     rax, 1
0x1800121e5  jnz     short loc_1800121DB
0x1800121e7  mov     dword ptr [rbp+liDistanceToMove], edi
0x1800121ea  xor     r9d, r9d; dwMoveMethod
0x1800121ed  mov     rdi, [rbp+hFile]
0x1800121f1  xor     r8d, r8d; lpNewFilePointer
0x1800121f4  mov     dword ptr [rbp+liDistanceToMove+4], 0
0x1800121fb  mov     rcx, rdi; hFile
0x1800121fe  mov     rdx, qword ptr [rbp+liDistanceToMove]; liDistanceToMove
0x180012202  call    cs:__imp_SetFilePointerEx
0x180012209  nop     dword ptr [rax+rax+00h]
0x18001220e  test    eax, eax
0x180012210  jnz     short loc_18001222F
0x180012212  call    cs:__imp_GetLastError
0x180012219  nop     dword ptr [rax+rax+00h]
0x18001221e  mov     ebx, eax
0x180012220  test    eax, eax
0x180012222  jle     short loc_18001226C
0x180012224  movzx   ebx, ax
0x180012227  or      ebx, 80070000h
0x18001222d  jmp     short loc_18001226C
0x18001222f  mov     rdx, [rbp+ppvData]; lpBuffer
0x180012233  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180012237  mov     r8d, r14d; nNumberOfBytesToRead
0x18001223a  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x180012243  mov     rcx, rdi; hFile
0x180012246  call    cs:__imp_ReadFile
0x18001224d  nop     dword ptr [rax+rax+00h]
0x180012252  test    eax, eax
0x180012254  jz      short loc_180012212
0x180012256  mov     rcx, [rsi]; psa
0x180012259  call    cs:__imp_SafeArrayUnaccessData
0x180012260  nop     dword ptr [rax+rax+00h]
0x180012265  jmp     short loc_18001226C
0x180012267  mov     ebx, 80070057h
0x18001226c  mov     eax, cs:dword_18004AE90
0x180012272  cmp     eax, 5
0x180012275  jbe     short loc_18001229C
0x180012277  lea     rax, [rbp+liDistanceToMove]
0x18001227b  mov     dword ptr [rbp+liDistanceToMove], ebx
0x18001227e  mov     [rsp+50h+var_28], rax
0x180012283  lea     rdx, word_180041B16
0x18001228a  lea     rax, [rbp+arg_18]
0x18001228e  mov     [rbp+arg_18], r15d
0x180012292  mov     [rsp+50h+lpOverlapped], rax
0x180012297  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001229c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800122a0  jz      short loc_1800122B1
0x1800122a2  mov     rcx, rdi; hObject
0x1800122a5  call    cs:__imp_CloseHandle
0x1800122ac  nop     dword ptr [rax+rax+00h]
0x1800122b1  test    ebx, ebx
0x1800122b3  jns     short loc_1800122D0
0x1800122b5  cmp     qword ptr [rsi], 0
0x1800122b9  jnz     short loc_1800122D0
0x1800122bb  xor     ecx, ecx; psa
0x1800122bd  call    cs:__imp_SafeArrayDestroy
0x1800122c4  nop     dword ptr [rax+rax+00h]
0x1800122c9  mov     qword ptr [rsi], 0
0x1800122d0  lea     r11, [rsp+50h+var_s0]
0x1800122d5  mov     eax, ebx
0x1800122d7  mov     rbx, [r11+30h]
0x1800122db  mov     rsi, [r11+38h]
0x1800122df  mov     rsp, r11
0x1800122e2  pop     r15
0x1800122e4  pop     r14
0x1800122e6  pop     r12
0x1800122e8  pop     rdi
0x1800122e9  pop     rbp
0x1800122ea  retn
```
