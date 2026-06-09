# ExtractThreadIdFromPebHandle(void *,ulong *,int)

- ea: `0x14003444c`
- end: `0x140034960`
- name: `?ExtractThreadIdFromPebHandle@@YAJPEAXPEAKH@Z`
- size: `1300`
- prototype: `__int64 __fastcall(HANDLE hProcess, unsigned int *lpBuffer, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400225cc`

## callees

- `0x14000d5ac`
- `0x140014f14`
- `0x1400166ec`
- `0x14003444c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400345b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003461e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400346f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400347bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400348cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400345b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003461e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400346f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400347bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400348cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003458b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003458b`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1400345a2`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x14003460e`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1400345a2`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x14003460e`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400346e5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400347af`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400348bb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400346e5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400347af`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400348bb`
- `ntdll!NtQueryInformationProcess` at `0x14003449f`
- `ntdll!NtQueryInformationProcess` at `0x14003450e`
- `ntdll!NtQueryInformationProcess` at `0x14003449f`
- `ntdll!NtQueryInformationProcess` at `0x14003450e`

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
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids, v9);
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
            WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids,
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
            WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids,
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
          WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids,
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
0x14003444c  mov     [rsp-38h+arg_10], r8d
0x140034451  push    rbp
0x140034452  push    rbx
0x140034453  push    rdi
0x140034454  push    r12
0x140034456  push    r13
0x140034458  push    r14
0x14003445a  push    r15
0x14003445c  mov     rbp, rsp
0x14003445f  sub     rsp, 80h
0x140034466  xor     edi, edi
0x140034468  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x14003446c  xorps   xmm0, xmm0
0x14003446f  mov     [rdx], edi
0x140034471  mov     r15, rdx
0x140034474  mov     [rbp+NumberOfBytesRead], rdi
0x140034478  mov     r12, rcx
0x14003447b  mov     [rbp+ProcessInformation], rdi
0x14003447f  lea     r9d, [rdi+8]; ProcessInformationLength
0x140034483  mov     [rbp+Buffer], rdi
0x140034487  lea     edx, [rdi+1Ah]; ProcessInformationClass
0x14003448a  mov     [rbp+var_40], rdi
0x14003448e  movups  [rbp+var_30], xmm0
0x140034492  mov     [rsp+80h+ReturnLength], rdi; ReturnLength
0x140034497  movups  [rbp+var_20], xmm0
0x14003449b  movups  [rbp+var_10], xmm0
0x14003449f  call    cs:__imp_NtQueryInformationProcess
0x1400344a6  nop     dword ptr [rax+rax+00h]
0x1400344ab  mov     ebx, eax
0x1400344ad  test    eax, eax
0x1400344af  jns     short loc_1400344F3
0x1400344b1  bts     ebx, 1Ch
0x1400344b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400344bc  lea     rdi, WPP_GLOBAL_Control
0x1400344c3  cmp     rcx, rdi
0x1400344c6  jz      loc_14003494A
0x1400344cc  test    byte ptr [rcx+1Ch], 1
0x1400344d0  jz      loc_14003494A
0x1400344d6  mov     edx, 0Bh
0x1400344db  mov     r9d, ebx
0x1400344de  lea     r8, WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids
0x1400344e5  mov     rcx, [rcx+10h]
0x1400344e9  call    WPP_SF_d
0x1400344ee  jmp     loc_14003494A
0x1400344f3  mov     rax, [rbp+ProcessInformation]
0x1400344f7  test    rax, rax
0x1400344fa  jnz     short loc_14003455F
0x1400344fc  lea     r9d, [rax+30h]; ProcessInformationLength
0x140034500  mov     [rsp+80h+ReturnLength], rdi; ReturnLength
0x140034505  lea     r8, [rbp+var_30]; ProcessInformation
0x140034509  xor     edx, edx; ProcessInformationClass
0x14003450b  mov     rcx, r12; ProcessHandle
0x14003450e  call    cs:__imp_NtQueryInformationProcess
0x140034515  nop     dword ptr [rax+rax+00h]
0x14003451a  mov     ebx, eax
0x14003451c  test    eax, eax
0x14003451e  jns     short loc_14003454C
0x140034520  bts     ebx, 1Ch
0x140034524  mov     rcx, cs:WPP_GLOBAL_Control
0x14003452b  lea     rdi, WPP_GLOBAL_Control
0x140034532  cmp     rcx, rdi
0x140034535  jz      loc_14003494A
0x14003453b  test    byte ptr [rcx+1Ch], 1
0x14003453f  jz      loc_14003494A
0x140034545  mov     edx, 0Ch
0x14003454a  jmp     short loc_1400344DB
0x14003454c  mov     rax, qword ptr [rbp+var_30+8]
0x140034550  mov     ebx, 8
0x140034555  mov     [rbp+ProcessInformation], rax
0x140034559  lea     r13d, [rbx+20h]
0x14003455d  jmp     short loc_140034568
0x14003455f  mov     ebx, 4
0x140034564  lea     r13d, [rbx+10h]
0x140034568  lea     rdi, WPP_GLOBAL_Control
0x14003456f  lea     r14, WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids
0x140034576  test    rax, rax
0x140034579  jnz     loc_1400346CE
0x14003457f  mov     [rbp+arg_8], ax
0x140034583  mov     word ptr [rbp+arg_10], ax
0x140034587  mov     [rbp+arg_18], ax
0x14003458b  call    cs:__imp_GetCurrentProcess
0x140034592  nop     dword ptr [rax+rax+00h]
0x140034597  mov     rcx, rax
0x14003459a  lea     r8, [rbp+arg_18]
0x14003459e  lea     rdx, [rbp+arg_8]
0x1400345a2  call    cs:__imp_IsWow64Process2
0x1400345a9  nop     dword ptr [rax+rax+00h]
0x1400345ae  test    eax, eax
0x1400345b0  jnz     short loc_140034604
0x1400345b2  call    cs:__imp_GetLastError
0x1400345b9  nop     dword ptr [rax+rax+00h]
0x1400345be  test    eax, eax
0x1400345c0  jle     short loc_1400345CC
0x1400345c2  movzx   eax, ax
0x1400345c5  or      eax, 80070000h
0x1400345ca  test    eax, eax
0x1400345cc  mov     ecx, 80004005h
0x1400345d1  cmovns  eax, ecx
0x1400345d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400345db  cmp     rcx, rdi
0x1400345de  jz      short loc_1400345FA
0x1400345e0  test    byte ptr [rcx+1Ch], 1
0x1400345e4  jz      short loc_1400345FA
0x1400345e6  mov     rcx, [rcx+10h]
0x1400345ea  mov     edx, 0Dh
0x1400345ef  mov     r9d, eax
0x1400345f2  mov     r8, r14
0x1400345f5  call    WPP_SF_d
0x1400345fa  xor     eax, eax
0x1400345fc  mov     [rbp+arg_8], ax
0x140034600  mov     [rbp+arg_18], ax
0x140034604  xor     r8d, r8d
0x140034607  lea     rdx, [rbp+arg_10]
0x14003460b  mov     rcx, r12
0x14003460e  call    cs:__imp_IsWow64Process2
0x140034615  nop     dword ptr [rax+rax+00h]
0x14003461a  test    eax, eax
0x14003461c  jnz     short loc_140034676
0x14003461e  call    cs:__imp_GetLastError
0x140034625  nop     dword ptr [rax+rax+00h]
0x14003462a  test    eax, eax
0x14003462c  jle     short loc_140034638
0x14003462e  movzx   eax, ax
0x140034631  or      eax, 80070000h
0x140034636  test    eax, eax
0x140034638  mov     ecx, 80004005h
0x14003463d  cmovns  eax, ecx
0x140034640  mov     r10, cs:WPP_GLOBAL_Control
0x140034647  cmp     r10, rdi
0x14003464a  jz      short loc_14003466E
0x14003464c  test    byte ptr [r10+1Ch], 1
0x140034651  jz      short loc_14003466E
0x140034653  mov     rcx, [r10+10h]
0x140034657  mov     edx, 0Eh
0x14003465c  mov     r9d, eax
0x14003465f  mov     r8, r14
0x140034662  call    WPP_SF_d
0x140034667  mov     r10, cs:WPP_GLOBAL_Control
0x14003466e  xor     edx, edx
0x140034670  mov     word ptr [rbp+arg_10], dx
0x140034674  jmp     short loc_140034681
0x140034676  movzx   edx, word ptr [rbp+arg_10]
0x14003467a  mov     r10, cs:WPP_GLOBAL_Control
0x140034681  cmp     r10, rdi
0x140034684  jz      short loc_1400346B6
0x140034686  test    byte ptr [r10+1Ch], 4
0x14003468b  jz      short loc_1400346B6
0x14003468d  movzx   ecx, [rbp+arg_8]
0x140034691  mov     r8, r14
0x140034694  movzx   eax, [rbp+arg_18]
0x140034698  mov     [rsp+80h+var_58], eax
0x14003469c  mov     dword ptr [rsp+80h+ReturnLength], ecx
0x1400346a0  mov     rcx, [r10+10h]
0x1400346a4  movzx   r9d, dx
0x1400346a8  mov     edx, 0Fh
0x1400346ad  call    WPP_SF_DDD
0x1400346b2  movzx   edx, word ptr [rbp+arg_10]
0x1400346b6  mov     rax, [rbp+ProcessInformation]
0x1400346ba  cmp     [rbp+arg_8], dx
0x1400346be  jz      short loc_1400346CE
0x1400346c0  test    rax, rax
0x1400346c3  jnz     short loc_1400346CE
0x1400346c5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400346ca  mov     rax, [rbp+ProcessInformation]
0x1400346ce  lea     rdx, [rax+r13]; lpBaseAddress
0x1400346d2  mov     r9, rbx; nSize
0x1400346d5  lea     rax, [rbp+NumberOfBytesRead]
0x1400346d9  mov     rcx, r12; hProcess
0x1400346dc  lea     r8, [rbp+Buffer]; lpBuffer
0x1400346e0  mov     [rsp+80h+ReturnLength], rax; lpNumberOfBytesRead
0x1400346e5  call    cs:__imp_ReadProcessMemory
0x1400346ec  nop     dword ptr [rax+rax+00h]
0x1400346f1  test    eax, eax
0x1400346f3  jnz     short loc_14003473A
0x1400346f5  call    cs:__imp_GetLastError
0x1400346fc  nop     dword ptr [rax+rax+00h]
0x140034701  mov     ebx, eax
0x140034703  test    eax, eax
0x140034705  jle     short loc_140034710
0x140034707  movzx   ebx, ax
0x14003470a  or      ebx, 80070000h
0x140034710  mov     rcx, cs:WPP_GLOBAL_Control
0x140034717  cmp     rcx, rdi
0x14003471a  jz      loc_14003494A
0x140034720  test    byte ptr [rcx+1Ch], 1
0x140034724  jz      loc_14003494A
0x14003472a  mov     edx, 10h
0x14003472f  mov     r9d, ebx
0x140034732  mov     r8, r14
0x140034735  jmp     loc_1400344E5
0x14003473a  cmp     [rbp+NumberOfBytesRead], rbx
0x14003473e  jz      short loc_14003476A
0x140034740  mov     r9d, 8007012Bh
0x140034746  mov     ebx, r9d
0x140034749  mov     rcx, cs:WPP_GLOBAL_Control
0x140034750  cmp     rcx, rdi
0x140034753  jz      loc_14003494A
0x140034759  test    byte ptr [rcx+1Ch], 1
0x14003475d  jz      loc_14003494A
0x140034763  mov     edx, 11h
0x140034768  jmp     short loc_140034732
0x14003476a  mov     rdx, [rbp+Buffer]; lpBaseAddress
0x14003476e  test    rdx, rdx
0x140034771  jnz     short loc_140034799
0x140034773  mov     ebx, 80070490h
0x140034778  mov     rcx, cs:WPP_GLOBAL_Control
0x14003477f  cmp     rcx, rdi
0x140034782  jz      loc_14003494A
0x140034788  test    byte ptr [rcx+1Ch], 2
0x14003478c  jz      loc_14003494A
0x140034792  mov     edx, 12h
0x140034797  jmp     short loc_14003472F
0x140034799  lea     rax, [rbp+NumberOfBytesRead]
0x14003479d  mov     r9d, 8; nSize
0x1400347a3  lea     r8, [rbp+var_40]; lpBuffer
0x1400347a7  mov     [rsp+80h+ReturnLength], rax; lpNumberOfBytesRead
0x1400347ac  mov     rcx, r12; hProcess
0x1400347af  call    cs:__imp_ReadProcessMemory
0x1400347b6  nop     dword ptr [rax+rax+00h]
0x1400347bb  test    eax, eax
0x1400347bd  jnz     short loc_1400347FE
0x1400347bf  call    cs:__imp_GetLastError
0x1400347c6  nop     dword ptr [rax+rax+00h]
0x1400347cb  mov     ebx, eax
0x1400347cd  test    eax, eax
0x1400347cf  jle     short loc_1400347DA
0x1400347d1  movzx   ebx, ax
0x1400347d4  or      ebx, 80070000h
0x1400347da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400347e1  cmp     rcx, rdi
0x1400347e4  jz      loc_14003494A
0x1400347ea  test    byte ptr [rcx+1Ch], 1
0x1400347ee  jz      loc_14003494A
0x1400347f4  mov     edx, 13h
0x1400347f9  jmp     loc_14003472F
0x1400347fe  cmp     [rbp+NumberOfBytesRead], 8
0x140034803  jz      short loc_140034832
0x140034805  mov     r9d, 8007012Bh
0x14003480b  mov     ebx, r9d
0x14003480e  mov     rcx, cs:WPP_GLOBAL_Control
0x140034815  cmp     rcx, rdi
0x140034818  jz      loc_14003494A
0x14003481e  test    byte ptr [rcx+1Ch], 1
0x140034822  jz      loc_14003494A
0x140034828  mov     edx, 14h
0x14003482d  jmp     loc_140034732
0x140034832  cmp     dword ptr [rbp+var_40], 498h
0x140034839  jnb     short loc_140034868
0x14003483b  mov     r9d, 80070519h
0x140034841  mov     ebx, r9d
0x140034844  mov     rcx, cs:WPP_GLOBAL_Control
0x14003484b  cmp     rcx, rdi
0x14003484e  jz      loc_14003494A
0x140034854  test    byte ptr [rcx+1Ch], 1
0x140034858  jz      loc_14003494A
0x14003485e  mov     edx, 15h
0x140034863  jmp     loc_140034732
0x140034868  cmp     dword ptr [rbp+var_40+4], 57454442h
0x14003486f  jz      short loc_14003489E
0x140034871  mov     r9d, 80070519h
0x140034877  mov     ebx, r9d
0x14003487a  mov     rcx, cs:WPP_GLOBAL_Control
0x140034881  cmp     rcx, rdi
0x140034884  jz      loc_14003494A
0x14003488a  test    byte ptr [rcx+1Ch], 1
0x14003488e  jz      loc_14003494A
0x140034894  mov     edx, 16h
0x140034899  jmp     loc_140034732
0x14003489e  mov     rdx, [rbp+Buffer]
0x1400348a2  lea     rax, [rbp+NumberOfBytesRead]
0x1400348a6  add     rdx, 8; lpBaseAddress
0x1400348aa  mov     [rsp+80h+ReturnLength], rax; lpNumberOfBytesRead
0x1400348af  mov     r9d, 4; nSize
0x1400348b5  mov     r8, r15; lpBuffer
0x1400348b8  mov     rcx, r12; hProcess
0x1400348bb  call    cs:__imp_ReadProcessMemory
0x1400348c2  nop     dword ptr [rax+rax+00h]
0x1400348c7  test    eax, eax
0x1400348c9  jnz     short loc_140034902
0x1400348cb  call    cs:__imp_GetLastError
0x1400348d2  nop     dword ptr [rax+rax+00h]
0x1400348d7  mov     ebx, eax
0x1400348d9  test    eax, eax
0x1400348db  jle     short loc_1400348E6
0x1400348dd  movzx   ebx, ax
0x1400348e0  or      ebx, 80070000h
0x1400348e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400348ed  cmp     rcx, rdi
0x1400348f0  jz      short loc_14003494A
0x1400348f2  test    byte ptr [rcx+1Ch], 1
0x1400348f6  jz      short loc_14003494A
0x1400348f8  mov     edx, 17h
0x1400348fd  jmp     loc_14003472F
0x140034902  cmp     [rbp+NumberOfBytesRead], 4
0x140034907  jz      short loc_14003492E
0x140034909  mov     r9d, 8007012Bh
0x14003490f  mov     ebx, r9d
0x140034912  mov     rcx, cs:WPP_GLOBAL_Control
0x140034919  cmp     rcx, rdi
0x14003491c  jz      short loc_14003494A
  ... truncated ...
```
