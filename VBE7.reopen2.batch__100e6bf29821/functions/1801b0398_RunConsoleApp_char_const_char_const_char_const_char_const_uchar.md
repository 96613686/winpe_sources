# RunConsoleApp(char const *,char const *,char const *,char const *,uchar * *)

- ea: `0x1801b0398`
- end: `0x1801b07e5`
- name: `?RunConsoleApp@@YAJPEBD000PEAPEAE@Z`
- size: `1101`
- prototype: `__int64 __fastcall(const char *, const char *, const char *, const char *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800e702c`

## callees

- `0x1800e6178`
- `0x1800fc26c`
- `0x180142894`
- `0x180142948`
- `0x1801487bc`
- `0x180174ff8`
- `0x1801b0398`
- `0x1801b07ec`
- `0x1801b0b2c`
- `0x180379520`

## import_xrefs

- `KERNEL32!CreatePipe` at `0x1801b0528`
- `KERNEL32!CreatePipe` at `0x1801b0528`
- `KERNEL32!GetLastError` at `0x1801b0532`
- `KERNEL32!GetLastError` at `0x1801b0532`
- `KERNEL32!CloseHandle` at `0x1801b059f`
- `KERNEL32!CloseHandle` at `0x1801b05aa`
- `KERNEL32!CloseHandle` at `0x1801b05f6`
- `KERNEL32!CloseHandle` at `0x1801b0778`
- `KERNEL32!CloseHandle` at `0x1801b0782`
- `KERNEL32!CloseHandle` at `0x1801b078d`
- `KERNEL32!CloseHandle` at `0x1801b059f`
- `KERNEL32!CloseHandle` at `0x1801b05aa`
- `KERNEL32!CloseHandle` at `0x1801b05f6`
- `KERNEL32!CloseHandle` at `0x1801b0778`
- `KERNEL32!CloseHandle` at `0x1801b0782`
- `KERNEL32!CloseHandle` at `0x1801b078d`
- `KERNEL32!SearchPathA` at `0x1801b03f5`
- `KERNEL32!SearchPathA` at `0x1801b03f5`
- `KERNEL32!MultiByteToWideChar` at `0x1801b04af`
- `KERNEL32!MultiByteToWideChar` at `0x1801b0748`
- `KERNEL32!MultiByteToWideChar` at `0x1801b04af`
- `KERNEL32!MultiByteToWideChar` at `0x1801b0748`
- `KERNEL32!GetExitCodeProcess` at `0x1801b0631`
- `KERNEL32!GetExitCodeProcess` at `0x1801b0631`
- `KERNEL32!WaitForSingleObject` at `0x1801b0622`
- `KERNEL32!WaitForSingleObject` at `0x1801b0622`
- `USER32!DispatchMessageA` at `0x1801b05e9`
- `USER32!DispatchMessageA` at `0x1801b07c3`
- `USER32!DispatchMessageA` at `0x1801b05e9`
- `USER32!DispatchMessageA` at `0x1801b07c3`
- `USER32!PeekMessageA` at `0x1801b05d7`
- `USER32!PeekMessageA` at `0x1801b07b1`
- `USER32!PeekMessageA` at `0x1801b05d7`
- `USER32!PeekMessageA` at `0x1801b07b1`

## pseudocode

```c
__int64 __fastcall RunConsoleApp(const char *a1, const char *a2, CHAR *a3, const char *a4, unsigned __int8 **a5)
{
  unsigned int v5; // eax
  int v7; // [rsp+40h] [rbp-A20h]
  int PipeToBuffer; // [rsp+40h] [rbp-A20h]
  int cchWideChar; // [rsp+44h] [rbp-A1Ch]
  signed int LastError; // [rsp+48h] [rbp-A18h]
  DWORD ExitCode; // [rsp+58h] [rbp-A08h] BYREF
  __int64 v13; // [rsp+60h] [rbp-A00h]
  __int64 v14; // [rsp+68h] [rbp-9F8h]
  HANDLE hReadPipe; // [rsp+70h] [rbp-9F0h] BYREF
  HANDLE hWritePipe; // [rsp+78h] [rbp-9E8h] BYREF
  LPWSTR v17; // [rsp+80h] [rbp-9E0h]
  LPWSTR lpWideCharStr; // [rsp+88h] [rbp-9D8h]
  struct tagMSG Msg; // [rsp+90h] [rbp-9D0h] BYREF
  char v20[128]; // [rsp+C0h] [rbp-9A0h] BYREF
  char v21[128]; // [rsp+140h] [rbp-920h] BYREF
  CHAR Buffer[2048]; // [rsp+1C0h] [rbp-8A0h] BYREF
  unsigned int v23; // [rsp+9C0h] [rbp-A0h]
  __int64 v24; // [rsp+9C8h] [rbp-98h]
  const char *v25; // [rsp+9D0h] [rbp-90h]
  const char *v26; // [rsp+9D8h] [rbp-88h]
  struct _PROCESS_INFORMATION hHandle; // [rsp+9E0h] [rbp-80h] BYREF
  struct _SECURITY_ATTRIBUTES PipeAttributes; // [rsp+9F8h] [rbp-68h] BYREF
  LPSTR FilePart; // [rsp+A10h] [rbp-50h] BYREF
  _BYTE v30[24]; // [rsp+A18h] [rbp-48h] BYREF
  _BYTE v31[24]; // [rsp+A30h] [rbp-30h] BYREF

  if ( SearchPathA(a2, a1, 0, 0x800u, Buffer, &FilePart) )
  {
    memset(&PipeAttributes, 0, sizeof(PipeAttributes));
    PipeAttributes.nLength = 24;
    PipeAttributes.bInheritHandle = 1;
    PipeAttributes.lpSecurityDescriptor = 0;
    if ( CreatePipe(&hReadPipe, &hWritePipe, &PipeAttributes, 0) )
    {
      v7 = CreateChildProcess(Buffer, a3, a4, hWritePipe, &hHandle);
      if ( v7 >= 0 )
      {
        while ( PeekMessageA(&Msg, 0, 0x1Du, 0x1Du, 1u) )
          DispatchMessageA(&Msg);
        CloseHandle(hWritePipe);
        PipeToBuffer = ReadPipeToBuffer(hReadPipe, a5);
        if ( PipeToBuffer >= 0 )
        {
          WaitForSingleObject(hHandle.hProcess, 0xFFFFFFFF);
          GetExitCodeProcess(hHandle.hProcess, &ExitCode);
          if ( ExitCode && **a5 )
          {
            PipeToBuffer = -2147467259;
          }
          else
          {
            v24 = *(_QWORD *)PebappCur();
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 40LL))(v24, *a5);
            *a5 = 0;
            if ( ExitCode )
            {
              v25 = a1;
              v14 = -1;
              do
                ++v14;
              while ( v25[v14] );
              cchWideChar = v14 + 1;
              TempBufferEx::TempBufferEx((TempBufferEx *)v31, 0x78u, 0, 2LL * (unsigned int)(v14 + 1), v20, 0, 1u);
              v17 = (LPWSTR)NAMMGR::Pgenproj((NAMMGR *)v31);
              if ( v17 )
                MultiByteToWideChar(0, 0, a1, cchWideChar, v17, cchWideChar);
              SaveErrText(0xE357u, v17, 0);
              PipeToBuffer = -2146770089;
              TempBufferEx::~TempBufferEx((TempBufferEx *)v31);
            }
          }
        }
        CloseHandle(hHandle.hThread);
        CloseHandle(hHandle.hProcess);
        CloseHandle(hReadPipe);
        while ( PeekMessageA(&Msg, 0, 0x1Du, 0x1Du, 1u) )
          DispatchMessageA(&Msg);
        return (unsigned int)PipeToBuffer;
      }
      else
      {
        CloseHandle(hReadPipe);
        CloseHandle(hWritePipe);
        return (unsigned int)v7;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      else
        return (unsigned int)LastError;
    }
  }
  else
  {
    v26 = a1;
    v13 = -1;
    do
      ++v13;
    while ( v26[v13] );
    TempBufferEx::TempBufferEx((TempBufferEx *)v30, 0x78u, 0, 2LL * (unsigned int)(v13 + 1), v21, 0, 1u);
    lpWideCharStr = (LPWSTR)NAMMGR::Pgenproj((NAMMGR *)v30);
    if ( lpWideCharStr )
      MultiByteToWideChar(0, 0, a1, v13 + 1, lpWideCharStr, v13 + 1);
    v5 = EberrOfHresult(2148179251LL);
    SaveErrText(v5, lpWideCharStr, 0);
    v23 = -2146788045;
    TempBufferEx::~TempBufferEx((TempBufferEx *)v30);
    return v23;
  }
}

```

## disassembly

```asm
0x1801b0398  mov     qword ptr [rsp-8+arg_18], r9
0x1801b039d  mov     qword ptr [rsp-8+arg_10], r8
0x1801b03a2  mov     [rsp-8+lpPath], rdx
0x1801b03a7  mov     [rsp-8+lpFileName], rcx
0x1801b03ac  push    rbp
0x1801b03ad  mov     rbp, rsp
0x1801b03b0  push    rdi
0x1801b03b1  sub     rsp, 0A58h
0x1801b03b8  mov     rax, cs:__security_cookie
0x1801b03bf  xor     rax, rsp
0x1801b03c2  mov     [rbp+var_18], rax
0x1801b03c6  mov     [rsp+0A60h+var_A20], 0
0x1801b03ce  lea     rax, [rbp+FilePart]
0x1801b03d2  mov     [rsp+0A60h+lpFilePart], rax; lpFilePart
0x1801b03d7  lea     rax, [rsp+0A60h+Buffer]
0x1801b03df  mov     [rsp+0A60h+lpBuffer], rax; lpBuffer
0x1801b03e4  mov     r9d, 800h; nBufferLength
0x1801b03ea  xor     r8d, r8d; lpExtension
0x1801b03ed  mov     rdx, [rbp+lpFileName]; lpFileName
0x1801b03f1  mov     rcx, [rbp+lpPath]; lpPath
0x1801b03f5  call    cs:__imp_SearchPathA
0x1801b03fb  test    eax, eax
0x1801b03fd  jnz     loc_1801B04F1
0x1801b0403  mov     rax, [rbp+lpFileName]
0x1801b0407  mov     [rsp+0A60h+var_88], rax
0x1801b040f  mov     [rsp+0A60h+var_A00], 0FFFFFFFFFFFFFFFFh
0x1801b0418  inc     [rsp+0A60h+var_A00]
0x1801b041d  mov     rax, [rsp+0A60h+var_88]
0x1801b0425  mov     rcx, [rsp+0A60h+var_A00]
0x1801b042a  cmp     byte ptr [rax+rcx], 0
0x1801b042e  jnz     short loc_1801B0418
0x1801b0430  mov     rax, [rsp+0A60h+var_A00]
0x1801b0435  inc     eax
0x1801b0437  mov     [rsp+0A60h+cbMultiByte], eax
0x1801b043b  mov     eax, [rsp+0A60h+cbMultiByte]
0x1801b043f  shl     rax, 1
0x1801b0442  mov     [rsp+0A60h+var_A30], 1; unsigned __int8
0x1801b0447  mov     [rsp+0A60h+lpFilePart], 0; unsigned __int64 *
0x1801b0450  lea     rcx, [rsp+0A60h+var_920]
0x1801b0458  mov     [rsp+0A60h+lpBuffer], rcx; char *
0x1801b045d  mov     r9, rax; unsigned __int64
0x1801b0460  xor     r8d, r8d; unsigned __int64
0x1801b0463  mov     edx, 78h ; 'x'; unsigned __int64
0x1801b0468  lea     rcx, [rbp+var_48]; this
0x1801b046c  call    ??0TempBufferEx@@QEAA@_K00PEADPEA_KE@Z; TempBufferEx::TempBufferEx(unsigned __int64,unsigned __int64,unsigned __int64,char *,unsigned __int64 *,uchar)
0x1801b0471  lea     rcx, [rbp+var_48]; this
0x1801b0475  call    ?Pgenproj@NAMMGR@@QEAAPEAVGEN_PROJECT@@XZ; NAMMGR::Pgenproj(void)
0x1801b047a  mov     [rsp+0A60h+lpWideCharStr], rax
0x1801b0482  cmp     [rsp+0A60h+lpWideCharStr], 0
0x1801b048b  jz      short loc_1801B04B5
0x1801b048d  mov     eax, [rsp+0A60h+cbMultiByte]
0x1801b0491  mov     dword ptr [rsp+0A60h+lpFilePart], eax; cchWideChar
0x1801b0495  mov     rax, [rsp+0A60h+lpWideCharStr]
0x1801b049d  mov     [rsp+0A60h+lpBuffer], rax; lpWideCharStr
0x1801b04a2  mov     r9d, [rsp+0A60h+cbMultiByte]; cbMultiByte
0x1801b04a7  mov     r8, [rbp+lpFileName]; lpMultiByteStr
0x1801b04ab  xor     edx, edx; dwFlags
0x1801b04ad  xor     ecx, ecx; CodePage
0x1801b04af  call    cs:__imp_MultiByteToWideChar
0x1801b04b5  mov     ecx, 800A9D33h
0x1801b04ba  call    EberrOfHresult
0x1801b04bf  xor     r8d, r8d; wchar_t *
0x1801b04c2  mov     rdx, [rsp+0A60h+lpWideCharStr]; wchar_t *
0x1801b04ca  mov     ecx, eax; unsigned int
0x1801b04cc  call    ?SaveErrText@@YAXIPEA_W0@Z; SaveErrText(uint,wchar_t *,wchar_t *)
0x1801b04d1  mov     [rsp+0A60h+var_A0], 800A9D33h
0x1801b04dc  lea     rcx, [rbp+var_48]; this
0x1801b04e0  call    ??1TempBufferEx@@QEAA@XZ; TempBufferEx::~TempBufferEx(void)
0x1801b04e5  mov     eax, [rsp+0A60h+var_A0]
0x1801b04ec  jmp     loc_1801B07CF
0x1801b04f1  lea     rax, [rbp+PipeAttributes]
0x1801b04f5  mov     rdi, rax
0x1801b04f8  xor     eax, eax
0x1801b04fa  mov     ecx, 18h
0x1801b04ff  rep stosb
0x1801b0501  mov     [rbp+PipeAttributes.nLength], 18h
0x1801b0508  mov     [rbp+PipeAttributes.bInheritHandle], 1
0x1801b050f  mov     [rbp+PipeAttributes.lpSecurityDescriptor], 0
0x1801b0517  xor     r9d, r9d; nSize
0x1801b051a  lea     r8, [rbp+PipeAttributes]; lpPipeAttributes
0x1801b051e  lea     rdx, [rsp+0A60h+hWritePipe]; hWritePipe
0x1801b0523  lea     rcx, [rsp+0A60h+hReadPipe]; hReadPipe
0x1801b0528  call    cs:__imp_CreatePipe
0x1801b052e  test    eax, eax
0x1801b0530  jnz     short loc_1801B056C
0x1801b0532  call    cs:__imp_GetLastError
0x1801b0538  mov     [rsp+0A60h+var_A18], eax
0x1801b053c  cmp     [rsp+0A60h+var_A18], 0
0x1801b0541  jg      short loc_1801B054D
0x1801b0543  mov     eax, [rsp+0A60h+var_A18]
0x1801b0547  mov     [rsp+0A60h+var_A0C], eax
0x1801b054b  jmp     short loc_1801B0563
0x1801b054d  mov     eax, [rsp+0A60h+var_A18]
0x1801b0551  and     eax, 0FFFFh
0x1801b0556  or      eax, 70000h
0x1801b055b  bts     eax, 1Fh
0x1801b055f  mov     [rsp+0A60h+var_A0C], eax
0x1801b0563  mov     eax, [rsp+0A60h+var_A0C]
0x1801b0567  jmp     loc_1801B07CF
0x1801b056c  lea     rax, [rbp+hHandle]
0x1801b0570  mov     [rsp+0A60h+lpBuffer], rax; LPPROCESS_INFORMATION
0x1801b0575  mov     r9, [rsp+0A60h+hWritePipe]; int
0x1801b057a  mov     r8, qword ptr [rbp+arg_18]; int
0x1801b057e  mov     rdx, qword ptr [rbp+arg_10]; int
0x1801b0582  lea     rcx, [rsp+0A60h+Buffer]; int
0x1801b058a  call    CreateChildProcess
0x1801b058f  mov     [rsp+0A60h+var_A20], eax
0x1801b0593  cmp     [rsp+0A60h+var_A20], 0
0x1801b0598  jge     short loc_1801B05B9
0x1801b059a  mov     rcx, [rsp+0A60h+hReadPipe]; hObject
0x1801b059f  call    cs:__imp_CloseHandle
0x1801b05a5  mov     rcx, [rsp+0A60h+hWritePipe]; hObject
0x1801b05aa  call    cs:__imp_CloseHandle
0x1801b05b0  mov     eax, [rsp+0A60h+var_A20]
0x1801b05b4  jmp     loc_1801B07CF
0x1801b05b9  mov     dword ptr [rsp+0A60h+lpBuffer], 1; wRemoveMsg
0x1801b05c1  mov     r9d, 1Dh; wMsgFilterMax
0x1801b05c7  mov     r8d, 1Dh; wMsgFilterMin
0x1801b05cd  xor     edx, edx; hWnd
0x1801b05cf  lea     rcx, [rsp+0A60h+Msg]; lpMsg
0x1801b05d7  call    cs:__imp_PeekMessageA
0x1801b05dd  test    eax, eax
0x1801b05df  jz      short loc_1801B05F1
0x1801b05e1  lea     rcx, [rsp+0A60h+Msg]; lpMsg
0x1801b05e9  call    cs:__imp_DispatchMessageA
0x1801b05ef  jmp     short loc_1801B05B9
0x1801b05f1  mov     rcx, [rsp+0A60h+hWritePipe]; hObject
0x1801b05f6  call    cs:__imp_CloseHandle
0x1801b05fc  mov     rdx, [rbp+arg_20]
0x1801b0600  mov     rcx, [rsp+0A60h+hReadPipe]
0x1801b0605  call    ReadPipeToBuffer
0x1801b060a  mov     [rsp+0A60h+var_A20], eax
0x1801b060e  cmp     [rsp+0A60h+var_A20], 0
0x1801b0613  jl      loc_1801B0774
0x1801b0619  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1801b061e  mov     rcx, [rbp+hHandle]; hHandle
0x1801b0622  call    cs:__imp_WaitForSingleObject
0x1801b0628  lea     rdx, [rsp+0A60h+ExitCode]; lpExitCode
0x1801b062d  mov     rcx, [rbp+hHandle]; hProcess
0x1801b0631  call    cs:__imp_GetExitCodeProcess
0x1801b0637  cmp     [rsp+0A60h+ExitCode], 0
0x1801b063c  jz      short loc_1801B0659
0x1801b063e  mov     rax, [rbp+arg_20]
0x1801b0642  mov     rax, [rax]
0x1801b0645  movzx   eax, byte ptr [rax]
0x1801b0648  test    eax, eax
0x1801b064a  jz      short loc_1801B0659
0x1801b064c  mov     [rsp+0A60h+var_A20], 80004005h
0x1801b0654  jmp     loc_1801B0774
0x1801b0659  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x1801b065e  mov     rax, [rax]
0x1801b0661  mov     [rsp+0A60h+var_98], rax
0x1801b0669  mov     rax, [rsp+0A60h+var_98]
0x1801b0671  mov     rax, [rax]
0x1801b0674  mov     rcx, [rbp+arg_20]
0x1801b0678  mov     rdx, [rcx]
0x1801b067b  mov     rcx, [rsp+0A60h+var_98]
0x1801b0683  call    qword ptr [rax+28h]
0x1801b0686  mov     rax, [rbp+arg_20]
0x1801b068a  mov     qword ptr [rax], 0
0x1801b0691  cmp     [rsp+0A60h+ExitCode], 0
0x1801b0696  jz      loc_1801B0774
0x1801b069c  mov     rax, [rbp+lpFileName]
0x1801b06a0  mov     [rsp+0A60h+var_90], rax
0x1801b06a8  mov     [rsp+0A60h+var_9F8], 0FFFFFFFFFFFFFFFFh
0x1801b06b1  inc     [rsp+0A60h+var_9F8]
0x1801b06b6  mov     rax, [rsp+0A60h+var_90]
0x1801b06be  mov     rcx, [rsp+0A60h+var_9F8]
0x1801b06c3  cmp     byte ptr [rax+rcx], 0
0x1801b06c7  jnz     short loc_1801B06B1
0x1801b06c9  mov     rax, [rsp+0A60h+var_9F8]
0x1801b06ce  inc     eax
0x1801b06d0  mov     [rsp+0A60h+cchWideChar], eax
0x1801b06d4  mov     eax, [rsp+0A60h+cchWideChar]
0x1801b06d8  shl     rax, 1
0x1801b06db  mov     [rsp+0A60h+var_A30], 1; unsigned __int8
0x1801b06e0  mov     [rsp+0A60h+lpFilePart], 0; unsigned __int64 *
0x1801b06e9  lea     rcx, [rsp+0A60h+var_9A0]
0x1801b06f1  mov     [rsp+0A60h+lpBuffer], rcx; char *
0x1801b06f6  mov     r9, rax; unsigned __int64
0x1801b06f9  xor     r8d, r8d; unsigned __int64
0x1801b06fc  mov     edx, 78h ; 'x'; unsigned __int64
0x1801b0701  lea     rcx, [rbp+var_30]; this
0x1801b0705  call    ??0TempBufferEx@@QEAA@_K00PEADPEA_KE@Z; TempBufferEx::TempBufferEx(unsigned __int64,unsigned __int64,unsigned __int64,char *,unsigned __int64 *,uchar)
0x1801b070a  lea     rcx, [rbp+var_30]; this
0x1801b070e  call    ?Pgenproj@NAMMGR@@QEAAPEAVGEN_PROJECT@@XZ; NAMMGR::Pgenproj(void)
0x1801b0713  mov     [rsp+0A60h+var_9E0], rax
0x1801b071b  cmp     [rsp+0A60h+var_9E0], 0
0x1801b0724  jz      short loc_1801B074E
0x1801b0726  mov     eax, [rsp+0A60h+cchWideChar]
0x1801b072a  mov     dword ptr [rsp+0A60h+lpFilePart], eax; cchWideChar
0x1801b072e  mov     rax, [rsp+0A60h+var_9E0]
0x1801b0736  mov     [rsp+0A60h+lpBuffer], rax; lpWideCharStr
0x1801b073b  mov     r9d, [rsp+0A60h+cchWideChar]; cbMultiByte
0x1801b0740  mov     r8, [rbp+lpFileName]; lpMultiByteStr
0x1801b0744  xor     edx, edx; dwFlags
0x1801b0746  xor     ecx, ecx; CodePage
0x1801b0748  call    cs:__imp_MultiByteToWideChar
0x1801b074e  xor     r8d, r8d; wchar_t *
0x1801b0751  mov     rdx, [rsp+0A60h+var_9E0]; wchar_t *
0x1801b0759  mov     ecx, 0E357h; unsigned int
0x1801b075e  call    ?SaveErrText@@YAXIPEA_W0@Z; SaveErrText(uint,wchar_t *,wchar_t *)
0x1801b0763  mov     [rsp+0A60h+var_A20], 800AE357h
0x1801b076b  lea     rcx, [rbp+var_30]; this
0x1801b076f  call    ??1TempBufferEx@@QEAA@XZ; TempBufferEx::~TempBufferEx(void)
0x1801b0774  mov     rcx, [rbp+hObject]; hObject
0x1801b0778  call    cs:__imp_CloseHandle
0x1801b077e  mov     rcx, [rbp+hHandle]; hObject
0x1801b0782  call    cs:__imp_CloseHandle
0x1801b0788  mov     rcx, [rsp+0A60h+hReadPipe]; hObject
0x1801b078d  call    cs:__imp_CloseHandle
0x1801b0793  mov     dword ptr [rsp+0A60h+lpBuffer], 1; wRemoveMsg
0x1801b079b  mov     r9d, 1Dh; wMsgFilterMax
0x1801b07a1  mov     r8d, 1Dh; wMsgFilterMin
0x1801b07a7  xor     edx, edx; hWnd
0x1801b07a9  lea     rcx, [rsp+0A60h+Msg]; lpMsg
0x1801b07b1  call    cs:__imp_PeekMessageA
0x1801b07b7  test    eax, eax
0x1801b07b9  jz      short loc_1801B07CB
0x1801b07bb  lea     rcx, [rsp+0A60h+Msg]; lpMsg
0x1801b07c3  call    cs:__imp_DispatchMessageA
0x1801b07c9  jmp     short loc_1801B0793
0x1801b07cb  mov     eax, [rsp+0A60h+var_A20]
0x1801b07cf  mov     rcx, [rbp+var_18]
0x1801b07d3  xor     rcx, rsp; StackCookie
0x1801b07d6  call    __security_check_cookie
0x1801b07db  add     rsp, 0A58h
0x1801b07e2  pop     rdi
0x1801b07e3  pop     rbp
0x1801b07e4  retn
```
