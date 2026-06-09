# ExtractThreadIdFromPebHandle(void *,ulong *,int)

- ea: `0x14003215c`
- end: `0x140032621`
- name: `?ExtractThreadIdFromPebHandle@@YAJPEAXPEAKH@Z`
- size: `1221`
- prototype: `__int64 __fastcall(HANDLE hProcess, unsigned int *lpBuffer, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140020fc0`

## callees

- `0x14000d2ec`
- `0x140014474`
- `0x140015b40`
- `0x14003215c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400322aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003230a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400323d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400322aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003230a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400323d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032593`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003228f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003228f`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1400322a0`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x140032300`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1400322a0`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x140032300`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400323cb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140032489`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140032589`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400323cb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140032489`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140032589`
- `ntdll!NtQueryInformationProcess` at `0x1400321af`
- `ntdll!NtQueryInformationProcess` at `0x140032218`
- `ntdll!NtQueryInformationProcess` at `0x1400321af`
- `ntdll!NtQueryInformationProcess` at `0x140032218`

## pseudocode

```c
__int64 __fastcall ExtractThreadIdFromPebHandle(HANDLE hProcess, unsigned int *lpBuffer, int a3)
{
  NTSTATUS v5; // ebx
  unsigned int v6; // ebx
  CUserModeHangReport *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rax
  NTSTATUS InformationProcess; // ebx
  SIZE_T v12; // rbx
  __int64 v13; // r13
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  bool v16; // sf
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  signed int v20; // eax
  bool v21; // sf
  CUserModeHangReport *v22; // r10
  __int64 v23; // rdx
  signed int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  __int64 ProcessInformation; // [rsp+30h] [rbp-50h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-48h] BYREF
  __int64 v30; // [rsp+40h] [rbp-40h] BYREF
  char *Buffer; // [rsp+48h] [rbp-38h] BYREF
  _OWORD v32[3]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 v33; // [rsp+C8h] [rbp+48h] BYREF
  int v34; // [rsp+D0h] [rbp+50h] BYREF
  unsigned __int16 v35; // [rsp+D8h] [rbp+58h] BYREF

  v34 = a3;
  *lpBuffer = 0;
  NumberOfBytesRead = 0;
  ProcessInformation = 0;
  Buffer = 0;
  v30 = 0;
  memset(v32, 0, sizeof(v32));
  v5 = NtQueryInformationProcess(hProcess, ProcessWow64Information, &ProcessInformation, 8u, 0);
  if ( v5 < 0 )
  {
    v6 = v5 | 0x10000000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 11;
LABEL_5:
      v9 = v6;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids, v9);
      return v6;
    }
    return v6;
  }
  v10 = ProcessInformation;
  if ( ProcessInformation )
  {
    v12 = 4;
    v13 = 20;
LABEL_14:
    if ( !v10 )
    {
      v33 = 0;
      LOWORD(v34) = 0;
      v35 = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !(unsigned int)IsWow64Process2(CurrentProcess, &v33, &v35) )
      {
        LastError = GetLastError();
        v16 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v16 = LastError < 0;
        }
        if ( !v16 )
          LastError = -2147467259;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            &WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids,
            (unsigned int)LastError);
        }
        v33 = 0;
        v35 = 0;
      }
      if ( (unsigned int)IsWow64Process2(hProcess, &v34, 0) )
      {
        v23 = (unsigned __int16)v34;
        v22 = WPP_GLOBAL_Control;
      }
      else
      {
        v20 = GetLastError();
        v21 = v20 < 0;
        if ( v20 > 0 )
        {
          v20 = (unsigned __int16)v20 | 0x80070000;
          v21 = v20 < 0;
        }
        v17 = 2147500037LL;
        if ( !v21 )
          v20 = -2147467259;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            &WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids,
            (unsigned int)v20);
          v22 = WPP_GLOBAL_Control;
        }
        v23 = 0;
        LOWORD(v34) = 0;
      }
      if ( v22 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 4) != 0 )
      {
        WPP_SF_DDD(
          *((_QWORD *)v22 + 2),
          15,
          &WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids,
          (unsigned __int16)v23,
          v33,
          v35);
        v23 = (unsigned __int16)v34;
      }
      v10 = ProcessInformation;
      if ( v33 != (_WORD)v23 && !ProcessInformation )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v17, v23, v18, v19);
        v10 = ProcessInformation;
      }
    }
    if ( ReadProcessMemory(hProcess, (LPCVOID)(v10 + v13), &Buffer, v12, &NumberOfBytesRead) )
    {
      if ( NumberOfBytesRead != v12 )
      {
        v9 = 2147942699LL;
        v6 = -2147024597;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 17;
          goto LABEL_6;
        }
        return v6;
      }
      if ( Buffer )
      {
        if ( ReadProcessMemory(hProcess, Buffer, &v30, 8u, &NumberOfBytesRead) )
        {
          if ( NumberOfBytesRead != 8 )
          {
            v9 = 2147942699LL;
            v6 = -2147024597;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 20;
              goto LABEL_6;
            }
            return v6;
          }
          if ( (unsigned int)v30 < 0x498 )
          {
            v9 = 2147943705LL;
            v6 = -2147023591;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 21;
              goto LABEL_6;
            }
            return v6;
          }
          if ( HIDWORD(v30) != 1464157250 )
          {
            v9 = 2147943705LL;
            v6 = -2147023591;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 22;
              goto LABEL_6;
            }
            return v6;
          }
          if ( ReadProcessMemory(hProcess, Buffer + 8, lpBuffer, 4u, &NumberOfBytesRead) )
          {
            if ( NumberOfBytesRead == 4 )
            {
              if ( !*lpBuffer || (*(_BYTE *)lpBuffer & 3) != 0 )
              {
                *lpBuffer = 0;
                return (unsigned int)-2147023452;
              }
              else
              {
                return 0;
              }
            }
            else
            {
              v9 = 2147942699LL;
              v6 = -2147024597;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 24;
                goto LABEL_6;
              }
            }
            return v6;
          }
          v26 = GetLastError();
          v6 = v26;
          if ( v26 > 0 )
            v6 = (unsigned __int16)v26 | 0x80070000;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            return v6;
          }
          v8 = 23;
        }
        else
        {
          v25 = GetLastError();
          v6 = v25;
          if ( v25 > 0 )
            v6 = (unsigned __int16)v25 | 0x80070000;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            return v6;
          }
          v8 = 19;
        }
      }
      else
      {
        v6 = -2147023728;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
          return v6;
        }
        v8 = 18;
      }
    }
    else
    {
      v24 = GetLastError();
      v6 = v24;
      if ( v24 > 0 )
        v6 = (unsigned __int16)v24 | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        return v6;
      }
      v8 = 16;
    }
    v9 = v6;
    goto LABEL_6;
  }
  InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, v32, 0x30u, 0);
  if ( InformationProcess >= 0 )
  {
    v10 = *((_QWORD *)&v32[0] + 1);
    v12 = 8;
    ProcessInformation = *((_QWORD *)&v32[0] + 1);
    v13 = 40;
    goto LABEL_14;
  }
  v6 = InformationProcess | 0x10000000;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 12;
    goto LABEL_5;
  }
  return v6;
}

```

## disassembly

```asm
0x14003215c  mov     [rsp-38h+arg_10], r8d
0x140032161  push    rbp
0x140032162  push    rbx
0x140032163  push    rdi
0x140032164  push    r12
0x140032166  push    r13
0x140032168  push    r14
0x14003216a  push    r15
0x14003216c  mov     rbp, rsp
0x14003216f  sub     rsp, 80h
0x140032176  xor     edi, edi
0x140032178  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x14003217c  xorps   xmm0, xmm0
0x14003217f  mov     [rdx], edi
0x140032181  mov     r15, rdx
0x140032184  mov     [rbp+NumberOfBytesRead], rdi
0x140032188  mov     r12, rcx
0x14003218b  mov     [rbp+ProcessInformation], rdi
0x14003218f  lea     r9d, [rdi+8]; ProcessInformationLength
0x140032193  mov     [rbp+Buffer], rdi
0x140032197  lea     edx, [rdi+1Ah]; ProcessInformationClass
0x14003219a  mov     [rbp+var_40], rdi
0x14003219e  movups  [rbp+var_30], xmm0
0x1400321a2  mov     [rsp+80h+ReturnLength], rdi; ReturnLength
0x1400321a7  movups  [rbp+var_20], xmm0
0x1400321ab  movups  [rbp+var_10], xmm0
0x1400321af  call    cs:__imp_NtQueryInformationProcess
0x1400321b5  mov     ebx, eax
0x1400321b7  test    eax, eax
0x1400321b9  jns     short loc_1400321FD
0x1400321bb  bts     ebx, 1Ch
0x1400321bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400321c6  lea     rdi, WPP_GLOBAL_Control
0x1400321cd  cmp     rcx, rdi
0x1400321d0  jz      loc_14003260C
0x1400321d6  test    byte ptr [rcx+1Ch], 1
0x1400321da  jz      loc_14003260C
0x1400321e0  mov     edx, 0Bh
0x1400321e5  mov     r9d, ebx
0x1400321e8  lea     r8, WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids
0x1400321ef  mov     rcx, [rcx+10h]
0x1400321f3  call    WPP_SF_d
0x1400321f8  jmp     loc_14003260C
0x1400321fd  mov     rax, [rbp+ProcessInformation]
0x140032201  test    rax, rax
0x140032204  jnz     short loc_140032263
0x140032206  lea     r9d, [rax+30h]; ProcessInformationLength
0x14003220a  mov     [rsp+80h+ReturnLength], rdi; ReturnLength
0x14003220f  lea     r8, [rbp+var_30]; ProcessInformation
0x140032213  xor     edx, edx; ProcessInformationClass
0x140032215  mov     rcx, r12; ProcessHandle
0x140032218  call    cs:__imp_NtQueryInformationProcess
0x14003221e  mov     ebx, eax
0x140032220  test    eax, eax
0x140032222  jns     short loc_140032250
0x140032224  bts     ebx, 1Ch
0x140032228  mov     rcx, cs:WPP_GLOBAL_Control
0x14003222f  lea     rdi, WPP_GLOBAL_Control
0x140032236  cmp     rcx, rdi
0x140032239  jz      loc_14003260C
0x14003223f  test    byte ptr [rcx+1Ch], 1
0x140032243  jz      loc_14003260C
0x140032249  mov     edx, 0Ch
0x14003224e  jmp     short loc_1400321E5
0x140032250  mov     rax, qword ptr [rbp+var_30+8]
0x140032254  mov     ebx, 8
0x140032259  mov     [rbp+ProcessInformation], rax
0x14003225d  lea     r13d, [rbx+20h]
0x140032261  jmp     short loc_14003226C
0x140032263  mov     ebx, 4
0x140032268  lea     r13d, [rbx+10h]
0x14003226c  lea     rdi, WPP_GLOBAL_Control
0x140032273  lea     r14, WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids
0x14003227a  test    rax, rax
0x14003227d  jnz     loc_1400323B4
0x140032283  mov     [rbp+arg_8], ax
0x140032287  mov     word ptr [rbp+arg_10], ax
0x14003228b  mov     [rbp+arg_18], ax
0x14003228f  call    cs:__imp_GetCurrentProcess
0x140032295  mov     rcx, rax
0x140032298  lea     r8, [rbp+arg_18]
0x14003229c  lea     rdx, [rbp+arg_8]
0x1400322a0  call    cs:__imp_IsWow64Process2
0x1400322a6  test    eax, eax
0x1400322a8  jnz     short loc_1400322F6
0x1400322aa  call    cs:__imp_GetLastError
0x1400322b0  test    eax, eax
0x1400322b2  jle     short loc_1400322BE
0x1400322b4  movzx   eax, ax
0x1400322b7  or      eax, 80070000h
0x1400322bc  test    eax, eax
0x1400322be  mov     ecx, 80004005h
0x1400322c3  cmovns  eax, ecx
0x1400322c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400322cd  cmp     rcx, rdi
0x1400322d0  jz      short loc_1400322EC
0x1400322d2  test    byte ptr [rcx+1Ch], 1
0x1400322d6  jz      short loc_1400322EC
0x1400322d8  mov     rcx, [rcx+10h]
0x1400322dc  mov     edx, 0Dh
0x1400322e1  mov     r9d, eax
0x1400322e4  mov     r8, r14
0x1400322e7  call    WPP_SF_d
0x1400322ec  xor     eax, eax
0x1400322ee  mov     [rbp+arg_8], ax
0x1400322f2  mov     [rbp+arg_18], ax
0x1400322f6  xor     r8d, r8d
0x1400322f9  lea     rdx, [rbp+arg_10]
0x1400322fd  mov     rcx, r12
0x140032300  call    cs:__imp_IsWow64Process2
0x140032306  test    eax, eax
0x140032308  jnz     short loc_14003235C
0x14003230a  call    cs:__imp_GetLastError
0x140032310  test    eax, eax
0x140032312  jle     short loc_14003231E
0x140032314  movzx   eax, ax
0x140032317  or      eax, 80070000h
0x14003231c  test    eax, eax
0x14003231e  mov     ecx, 80004005h
0x140032323  cmovns  eax, ecx
0x140032326  mov     r10, cs:WPP_GLOBAL_Control
0x14003232d  cmp     r10, rdi
0x140032330  jz      short loc_140032354
0x140032332  test    byte ptr [r10+1Ch], 1
0x140032337  jz      short loc_140032354
0x140032339  mov     rcx, [r10+10h]
0x14003233d  mov     edx, 0Eh
0x140032342  mov     r9d, eax
0x140032345  mov     r8, r14
0x140032348  call    WPP_SF_d
0x14003234d  mov     r10, cs:WPP_GLOBAL_Control
0x140032354  xor     edx, edx
0x140032356  mov     word ptr [rbp+arg_10], dx
0x14003235a  jmp     short loc_140032367
0x14003235c  movzx   edx, word ptr [rbp+arg_10]
0x140032360  mov     r10, cs:WPP_GLOBAL_Control
0x140032367  cmp     r10, rdi
0x14003236a  jz      short loc_14003239C
0x14003236c  test    byte ptr [r10+1Ch], 4
0x140032371  jz      short loc_14003239C
0x140032373  movzx   ecx, [rbp+arg_8]
0x140032377  mov     r8, r14
0x14003237a  movzx   eax, [rbp+arg_18]
0x14003237e  mov     [rsp+80h+var_58], eax
0x140032382  mov     dword ptr [rsp+80h+ReturnLength], ecx
0x140032386  mov     rcx, [r10+10h]
0x14003238a  movzx   r9d, dx
0x14003238e  mov     edx, 0Fh
0x140032393  call    WPP_SF_DDD
0x140032398  movzx   edx, word ptr [rbp+arg_10]
0x14003239c  mov     rax, [rbp+ProcessInformation]
0x1400323a0  cmp     [rbp+arg_8], dx
0x1400323a4  jz      short loc_1400323B4
0x1400323a6  test    rax, rax
0x1400323a9  jnz     short loc_1400323B4
0x1400323ab  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400323b0  mov     rax, [rbp+ProcessInformation]
0x1400323b4  lea     rdx, [rax+r13]; lpBaseAddress
0x1400323b8  mov     r9, rbx; nSize
0x1400323bb  lea     rax, [rbp+NumberOfBytesRead]
0x1400323bf  mov     rcx, r12; hProcess
0x1400323c2  lea     r8, [rbp+Buffer]; lpBuffer
0x1400323c6  mov     [rsp+80h+ReturnLength], rax; lpNumberOfBytesRead
0x1400323cb  call    cs:__imp_ReadProcessMemory
0x1400323d1  test    eax, eax
0x1400323d3  jnz     short loc_140032414
0x1400323d5  call    cs:__imp_GetLastError
0x1400323db  mov     ebx, eax
0x1400323dd  test    eax, eax
0x1400323df  jle     short loc_1400323EA
0x1400323e1  movzx   ebx, ax
0x1400323e4  or      ebx, 80070000h
0x1400323ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400323f1  cmp     rcx, rdi
0x1400323f4  jz      loc_14003260C
0x1400323fa  test    byte ptr [rcx+1Ch], 1
0x1400323fe  jz      loc_14003260C
0x140032404  mov     edx, 10h
0x140032409  mov     r9d, ebx
0x14003240c  mov     r8, r14
0x14003240f  jmp     loc_1400321EF
0x140032414  cmp     [rbp+NumberOfBytesRead], rbx
0x140032418  jz      short loc_140032444
0x14003241a  mov     r9d, 8007012Bh
0x140032420  mov     ebx, r9d
0x140032423  mov     rcx, cs:WPP_GLOBAL_Control
0x14003242a  cmp     rcx, rdi
0x14003242d  jz      loc_14003260C
0x140032433  test    byte ptr [rcx+1Ch], 1
0x140032437  jz      loc_14003260C
0x14003243d  mov     edx, 11h
0x140032442  jmp     short loc_14003240C
0x140032444  mov     rdx, [rbp+Buffer]; lpBaseAddress
0x140032448  test    rdx, rdx
0x14003244b  jnz     short loc_140032473
0x14003244d  mov     ebx, 80070490h
0x140032452  mov     rcx, cs:WPP_GLOBAL_Control
0x140032459  cmp     rcx, rdi
0x14003245c  jz      loc_14003260C
0x140032462  test    byte ptr [rcx+1Ch], 2
0x140032466  jz      loc_14003260C
0x14003246c  mov     edx, 12h
0x140032471  jmp     short loc_140032409
0x140032473  lea     rax, [rbp+NumberOfBytesRead]
0x140032477  mov     r9d, 8; nSize
0x14003247d  lea     r8, [rbp+var_40]; lpBuffer
0x140032481  mov     [rsp+80h+ReturnLength], rax; lpNumberOfBytesRead
0x140032486  mov     rcx, r12; hProcess
0x140032489  call    cs:__imp_ReadProcessMemory
0x14003248f  test    eax, eax
0x140032491  jnz     short loc_1400324CC
0x140032493  call    cs:__imp_GetLastError
0x140032499  mov     ebx, eax
0x14003249b  test    eax, eax
0x14003249d  jle     short loc_1400324A8
0x14003249f  movzx   ebx, ax
0x1400324a2  or      ebx, 80070000h
0x1400324a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400324af  cmp     rcx, rdi
0x1400324b2  jz      loc_14003260C
0x1400324b8  test    byte ptr [rcx+1Ch], 1
0x1400324bc  jz      loc_14003260C
0x1400324c2  mov     edx, 13h
0x1400324c7  jmp     loc_140032409
0x1400324cc  cmp     [rbp+NumberOfBytesRead], 8
0x1400324d1  jz      short loc_140032500
0x1400324d3  mov     r9d, 8007012Bh
0x1400324d9  mov     ebx, r9d
0x1400324dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400324e3  cmp     rcx, rdi
0x1400324e6  jz      loc_14003260C
0x1400324ec  test    byte ptr [rcx+1Ch], 1
0x1400324f0  jz      loc_14003260C
0x1400324f6  mov     edx, 14h
0x1400324fb  jmp     loc_14003240C
0x140032500  cmp     dword ptr [rbp+var_40], 498h
0x140032507  jnb     short loc_140032536
0x140032509  mov     r9d, 80070519h
0x14003250f  mov     ebx, r9d
0x140032512  mov     rcx, cs:WPP_GLOBAL_Control
0x140032519  cmp     rcx, rdi
0x14003251c  jz      loc_14003260C
0x140032522  test    byte ptr [rcx+1Ch], 1
0x140032526  jz      loc_14003260C
0x14003252c  mov     edx, 15h
0x140032531  jmp     loc_14003240C
0x140032536  cmp     dword ptr [rbp+var_40+4], 57454442h
0x14003253d  jz      short loc_14003256C
0x14003253f  mov     r9d, 80070519h
0x140032545  mov     ebx, r9d
0x140032548  mov     rcx, cs:WPP_GLOBAL_Control
0x14003254f  cmp     rcx, rdi
0x140032552  jz      loc_14003260C
0x140032558  test    byte ptr [rcx+1Ch], 1
0x14003255c  jz      loc_14003260C
0x140032562  mov     edx, 16h
0x140032567  jmp     loc_14003240C
0x14003256c  mov     rdx, [rbp+Buffer]
0x140032570  lea     rax, [rbp+NumberOfBytesRead]
0x140032574  add     rdx, 8; lpBaseAddress
0x140032578  mov     [rsp+80h+ReturnLength], rax; lpNumberOfBytesRead
0x14003257d  mov     r9d, 4; nSize
0x140032583  mov     r8, r15; lpBuffer
0x140032586  mov     rcx, r12; hProcess
0x140032589  call    cs:__imp_ReadProcessMemory
0x14003258f  test    eax, eax
0x140032591  jnz     short loc_1400325C4
0x140032593  call    cs:__imp_GetLastError
0x140032599  mov     ebx, eax
0x14003259b  test    eax, eax
0x14003259d  jle     short loc_1400325A8
0x14003259f  movzx   ebx, ax
0x1400325a2  or      ebx, 80070000h
0x1400325a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400325af  cmp     rcx, rdi
0x1400325b2  jz      short loc_14003260C
0x1400325b4  test    byte ptr [rcx+1Ch], 1
0x1400325b8  jz      short loc_14003260C
0x1400325ba  mov     edx, 17h
0x1400325bf  jmp     loc_140032409
0x1400325c4  cmp     [rbp+NumberOfBytesRead], 4
0x1400325c9  jz      short loc_1400325F0
0x1400325cb  mov     r9d, 8007012Bh
0x1400325d1  mov     ebx, r9d
0x1400325d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400325db  cmp     rcx, rdi
0x1400325de  jz      short loc_14003260C
0x1400325e0  test    byte ptr [rcx+1Ch], 1
0x1400325e4  jz      short loc_14003260C
0x1400325e6  mov     edx, 18h
0x1400325eb  jmp     loc_14003240C
0x1400325f0  cmp     dword ptr [r15], 0
0x1400325f4  jz      short loc_140032600
0x1400325f6  test    byte ptr [r15], 3
0x1400325fa  jnz     short loc_140032600
0x1400325fc  xor     ebx, ebx
0x1400325fe  jmp     short loc_14003260C
0x140032600  mov     dword ptr [r15], 0
0x140032607  mov     ebx, 800705A4h
0x14003260c  mov     eax, ebx
  ... truncated ...
```
