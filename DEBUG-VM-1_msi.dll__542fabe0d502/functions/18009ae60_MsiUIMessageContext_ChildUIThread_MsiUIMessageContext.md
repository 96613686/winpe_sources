# MsiUIMessageContext::ChildUIThread(MsiUIMessageContext *)

- ea: `0x18009ae60`
- end: `0x18009b234`
- name: `?ChildUIThread@MsiUIMessageContext@@CAKPEAU1@@Z`
- size: `980`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callees

- `0x18000a150`
- `0x180025a18`
- `0x18006e484`
- `0x18009ae60`
- `0x18009bc00`
- `0x18011ada4`
- `0x180156e60`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GetExitCodeThread` at `0x18009b063`
- `KERNEL32!GetExitCodeThread` at `0x18009b063`
- `KERNEL32!GetLastError` at `0x18009b0d2`
- `KERNEL32!GetLastError` at `0x18009b1dd`
- `KERNEL32!GetLastError` at `0x18009b0d2`
- `KERNEL32!GetLastError` at `0x18009b1dd`
- `KERNEL32!WaitForSingleObject` at `0x18009afb0`
- `KERNEL32!WaitForSingleObject` at `0x18009afb0`
- `KERNEL32!GetModuleFileNameW` at `0x18009aecf`
- `KERNEL32!GetModuleFileNameW` at `0x18009aecf`
- `KERNEL32!SetEvent` at `0x18009b1cc`
- `KERNEL32!SetEvent` at `0x18009b1cc`
- `KERNEL32!WaitForMultipleObjects` at `0x18009af9e`
- `KERNEL32!WaitForMultipleObjects` at `0x18009af9e`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18009b22d`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18009b22d`

## string_xrefs

- `0x18009b1f2`: `Wait Failed in ChildUIThread. GetLastError returned %d.`
- `0x18009b01b`: `ChildUIThread wait timed out`
- `0x18009b088`: `hMainThread is gone. ChildUIThread will finish as well.`
- `0x18009b0dd`: `GetExitCodeThread returned %d in MsiUIMessageContext::ChildUIThread`
- `0x18009b141`: `Invalid event trigger in ChildUIThread`

## pseudocode

```c
__int64 __fastcall MsiUIMessageContext::ChildUIThread(unsigned int *Parameter)
{
  unsigned int v1; // eax
  HMODULE LibraryW; // r15
  bool v4; // r8
  DWORD v6; // ebp
  int v7; // esi
  char v8; // r14
  DWORD v9; // eax
  CBasicUI *v10; // rcx
  void *v11; // rcx
  DWORD LastError; // eax
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // r8
  DWORD v16; // eax
  unsigned int v17; // [rsp+50h] [rbp-288h]
  void *v18; // [rsp+58h] [rbp-280h]
  DWORD ExitCode[4]; // [rsp+60h] [rbp-278h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-268h] BYREF

  v1 = Parameter[47];
  if ( v1 == 5 )
  {
    Parameter[47] = 0;
LABEL_3:
    if ( !*((_BYTE *)Parameter + 229) && (int)((__int64 (__fastcall *)(_QWORD))OLE32::CoInitialize)(0) >= 0 )
      *((_BYTE *)Parameter + 229) = 1;
    if ( GetModuleFileNameW(g_hInstance, Filename, 0x103u) )
    {
      Filename[259] = 0;
      LibraryW = (HMODULE)IsolationAwareLoadLibraryW(Filename);
    }
    else
    {
      LibraryW = 0;
    }
    v6 = 0;
    v7 = 0;
    v8 = 1;
    while ( 1 )
    {
      v9 = *((_QWORD *)Parameter + 10)
         ? WaitForMultipleObjects(2u, (const HANDLE *)Parameter + 9, 0, g_iUIWaitTick)
         : WaitForSingleObject(*((HANDLE *)Parameter + 9), g_iUIWaitTick);
      if ( v9 == -1 )
        break;
      if ( v9 == 258 )
      {
        if ( !*((_QWORD *)Parameter + 21) )
          MsiUIMessageContext::ProcessMessage(Parameter, 167772160, &off_180305DB0);
        if ( !Parameter[48] )
        {
          v7 += g_iUITicksStep;
          if ( v7 >= g_cWaitTimeout )
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                "ChildUIThread wait timed out",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                "(NULL)",
                v17,
                v18);
            v7 = 0;
          }
        }
      }
      else if ( v9 == 1 )
      {
        v11 = (void *)*((_QWORD *)Parameter + 10);
        ExitCode[0] = 0;
        if ( GetExitCodeThread(v11, ExitCode) )
        {
          if ( ExitCode[0] != 259 )
          {
            if ( g_dmDiagnosticMode )
              DebugString(
                9,
                0,
                0,
                L"hMainThread is gone. ChildUIThread will finish as well.",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            v8 = 0;
          }
        }
        else if ( g_dmDiagnosticMode )
        {
          LastError = GetLastError();
          DebugString(
            9,
            0,
            0,
            L"GetExitCodeThread returned %d in MsiUIMessageContext::ChildUIThread",
            (const unsigned __int16 *)LastError,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
      }
      else
      {
        v13 = Parameter[16];
        v7 = 0;
        if ( (_DWORD)v13 == 0x80000000 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              "Invalid event trigger in ChildUIThread",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              v17,
              v18);
        }
        else
        {
          if ( (_DWORD)v13 == 251658549 )
          {
            if ( byte_180306EA4 )
              CBasicUI::Terminate(v10);
            if ( *((_BYTE *)Parameter + 229) == 1 )
            {
              OLE32::CoUninitialize();
              *((_BYTE *)Parameter + 229) = 0;
            }
            v8 = 0;
            v14 = 0;
          }
          else
          {
            v15 = *((_QWORD *)Parameter + 7);
            Parameter[36] = -2147483647;
            v14 = MsiUIMessageContext::ProcessMessage(Parameter, v13, v15);
            Parameter[16] = 0x80000000;
          }
          Parameter[36] = v14;
          SetEvent(*((HANDLE *)Parameter + 11));
        }
      }
      if ( !v8 )
        goto LABEL_50;
    }
    v16 = GetLastError();
    v6 = v16;
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"Wait Failed in ChildUIThread. GetLastError returned %d.",
        (const unsigned __int16 *)v16,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
LABEL_50:
    FreeLibraryAndExitThread(LibraryW, v6);
  }
  if ( v1 == 3 || (v4 = 0, v1 == 0x2000) )
    v4 = 1;
  if ( CBasicUI::Initialize(
         (CBasicUI *)Parameter,
         qword_180309948,
         v4,
         *((_BYTE *)Parameter + 204),
         *((_BYTE *)Parameter + 313),
         *((_BYTE *)Parameter + 224),
         *((_BYTE *)Parameter + 225),
         *((_BYTE *)Parameter + 226)) )
  {
    goto LABEL_3;
  }
  return 1631;
}

```

## disassembly

```asm
0x18009ae60  push    rbx
0x18009ae62  push    rbp
0x18009ae63  push    rsi
0x18009ae64  push    rdi
0x18009ae65  push    r12
0x18009ae67  push    r13
0x18009ae69  push    r14
0x18009ae6b  push    r15
0x18009ae6d  sub     rsp, 298h
0x18009ae74  mov     rax, cs:__security_cookie
0x18009ae7b  xor     rax, rsp
0x18009ae7e  mov     [rsp+2D8h+var_58], rax
0x18009ae86  mov     eax, [rcx+0BCh]
0x18009ae8c  xor     ebx, ebx
0x18009ae8e  mov     rdi, rcx
0x18009ae91  cmp     eax, 5
0x18009ae94  jnz     short loc_18009AEE5
0x18009ae96  mov     [rcx+0BCh], ebx
0x18009ae9c  cmp     [rdi+0E5h], bl
0x18009aea2  jnz     short loc_18009AEBD
0x18009aea4  mov     rax, cs:?CoInitialize@OLE32@@3P6AJPEAX@ZEA; long (*OLE32::CoInitialize)(void *)
0x18009aeab  xor     ecx, ecx
0x18009aead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aeb2  test    eax, eax
0x18009aeb4  js      short loc_18009AEBD
0x18009aeb6  mov     byte ptr [rdi+0E5h], 1
0x18009aebd  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18009aec4  lea     rdx, [rsp+2D8h+Filename]; lpFilename
0x18009aec9  mov     r8d, 103h; nSize
0x18009aecf  call    cs:__imp_GetModuleFileNameW
0x18009aed5  test    eax, eax
0x18009aed7  jnz     loc_18009AF63
0x18009aedd  mov     r15, rbx
0x18009aee0  jmp     loc_18009AF78
0x18009aee5  cmp     eax, 3
0x18009aee8  jz      short loc_18009AEF4
0x18009aeea  mov     r8b, bl
0x18009aeed  cmp     eax, 2000h
0x18009aef2  jnz     short loc_18009AEF7
0x18009aef4  mov     r8b, 1; bool
0x18009aef7  mov     al, [rcx+0E2h]
0x18009aefd  mov     r9b, [rcx+0CCh]; bool
0x18009af04  mov     rdx, cs:qword_180309948; HWND
0x18009af0b  mov     byte ptr [rsp+2D8h+var_2A0], al; bool
0x18009af0f  mov     al, [rcx+0E1h]
0x18009af15  mov     byte ptr [rsp+2D8h+var_2A8], al; bool
0x18009af19  mov     al, [rcx+0E0h]
0x18009af1f  mov     byte ptr [rsp+2D8h+var_2B0], al; bool
0x18009af23  mov     al, [rcx+139h]
0x18009af29  mov     byte ptr [rsp+2D8h+var_2B8], al; bool
0x18009af2d  call    ?Initialize@CBasicUI@@QEAA_NPEAUHWND__@@_N11111@Z; CBasicUI::Initialize(HWND__ *,bool,bool,bool,bool,bool,bool)
0x18009af32  test    al, al
0x18009af34  jnz     loc_18009AE9C
0x18009af3a  mov     eax, 65Fh
0x18009af3f  mov     rcx, [rsp+2D8h+var_58]
0x18009af47  xor     rcx, rsp; StackCookie
0x18009af4a  call    __security_check_cookie
0x18009af4f  add     rsp, 298h
0x18009af56  pop     r15
0x18009af58  pop     r14
0x18009af5a  pop     r13
0x18009af5c  pop     r12
0x18009af5e  pop     rdi
0x18009af5f  pop     rsi
0x18009af60  pop     rbp
0x18009af61  pop     rbx
0x18009af62  retn
0x18009af63  lea     rcx, [rsp+2D8h+Filename]; lpLibFileName
0x18009af68  mov     [rsp+2D8h+var_62], bx
0x18009af70  call    IsolationAwareLoadLibraryW
0x18009af75  mov     r15, rax
0x18009af78  mov     ebp, ebx
0x18009af7a  lea     r13, aNull; "(NULL)"
0x18009af81  mov     esi, ebx
0x18009af83  mov     r14b, 1
0x18009af86  cmp     [rdi+50h], rbx
0x18009af8a  jz      short loc_18009AFA6
0x18009af8c  mov     r9d, cs:?g_iUIWaitTick@@3HA; dwMilliseconds
0x18009af93  lea     rdx, [rdi+48h]; lpHandles
0x18009af97  xor     r8d, r8d; bWaitAll
0x18009af9a  lea     ecx, [r8+2]; nCount
0x18009af9e  call    cs:__imp_WaitForMultipleObjects
0x18009afa4  jmp     short loc_18009AFB6
0x18009afa6  mov     edx, cs:?g_iUIWaitTick@@3HA; dwMilliseconds
0x18009afac  mov     rcx, [rdi+48h]; hHandle
0x18009afb0  call    cs:__imp_WaitForSingleObject
0x18009afb6  cmp     eax, 0FFFFFFFFh
0x18009afb9  jz      loc_18009B1DD
0x18009afbf  cmp     eax, 102h
0x18009afc4  jnz     loc_18009B04D
0x18009afca  cmp     [rdi+0A8h], rbx
0x18009afd1  jnz     short loc_18009AFE7
0x18009afd3  lea     r8, off_180305DB0
0x18009afda  mov     edx, 0A000000h
0x18009afdf  mov     rcx, rdi
0x18009afe2  call    ?ProcessMessage@MsiUIMessageContext@@AEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::ProcessMessage(imtEnum,IMsiRecord *)
0x18009afe7  cmp     [rdi+0C0h], ebx
0x18009afed  jnz     loc_18009B1D2
0x18009aff3  add     esi, cs:?g_iUITicksStep@@3HA; int g_iUITicksStep
0x18009aff9  cmp     esi, cs:?g_cWaitTimeout@@3HA; int g_cWaitTimeout
0x18009afff  jl      loc_18009B1D2
0x18009b005  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18009b00b  jz      short loc_18009B046
0x18009b00d  lea     rax, aNull_0; "(NULL)"
0x18009b014  xor     edx, edx; unsigned __int16
0x18009b016  mov     [rsp+2D8h+var_290], rax; char *
0x18009b01b  lea     r9, aChilduithreadW; "ChildUIThread wait timed out"
0x18009b022  mov     [rsp+2D8h+var_298], rax; char *
0x18009b027  xor     r8d, r8d; int
0x18009b02a  mov     [rsp+2D8h+var_2A0], rax; char *
0x18009b02f  mov     [rsp+2D8h+var_2A8], rax; char *
0x18009b034  lea     ecx, [rdx+9]; int
0x18009b037  mov     [rsp+2D8h+var_2B0], rax; char *
0x18009b03c  mov     [rsp+2D8h+var_2B8], rax; char *
0x18009b041  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18009b046  mov     esi, ebx
0x18009b048  jmp     loc_18009B1D2
0x18009b04d  cmp     eax, 1
0x18009b050  jnz     loc_18009B11A
0x18009b056  mov     rcx, [rdi+50h]; hThread
0x18009b05a  lea     rdx, [rsp+2D8h+ExitCode]; lpExitCode
0x18009b05f  mov     [rsp+2D8h+ExitCode], ebx
0x18009b063  call    cs:__imp_GetExitCodeThread
0x18009b069  test    eax, eax
0x18009b06b  jz      short loc_18009B0C6
0x18009b06d  cmp     [rsp+2D8h+ExitCode], 103h
0x18009b075  jz      loc_18009B1D2
0x18009b07b  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18009b081  jz      short loc_18009B0BE
0x18009b083  mov     [rsp+2D8h+var_280], rbx; void *
0x18009b088  lea     r9, aHmainthreadIsG; "hMainThread is gone. ChildUIThread will"...
0x18009b08f  mov     [rsp+2D8h+var_288], ebx; unsigned int
0x18009b093  xor     edx, edx; unsigned __int16
0x18009b095  mov     [rsp+2D8h+var_290], r13; unsigned __int16 *
0x18009b09a  xor     r8d, r8d; int
0x18009b09d  mov     [rsp+2D8h+var_298], r13; unsigned __int16 *
0x18009b0a2  mov     [rsp+2D8h+var_2A0], r13; unsigned __int16 *
0x18009b0a7  mov     [rsp+2D8h+var_2A8], r13; unsigned __int16 *
0x18009b0ac  lea     ecx, [rdx+9]; int
0x18009b0af  mov     [rsp+2D8h+var_2B0], r13; unsigned __int16 *
0x18009b0b4  mov     [rsp+2D8h+var_2B8], r13; unsigned __int16 *
0x18009b0b9  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009b0be  mov     r14b, bl
0x18009b0c1  jmp     loc_18009B1D2
0x18009b0c6  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18009b0cc  jz      loc_18009B1D2
0x18009b0d2  call    cs:__imp_GetLastError
0x18009b0d8  mov     [rsp+2D8h+var_280], rbx; void *
0x18009b0dd  lea     r9, aGetexitcodethr; "GetExitCodeThread returned %d in MsiUIM"...
0x18009b0e4  mov     [rsp+2D8h+var_288], ebx; unsigned int
0x18009b0e8  xor     edx, edx; unsigned __int16
0x18009b0ea  mov     [rsp+2D8h+var_290], r13; unsigned __int16 *
0x18009b0ef  xor     r8d, r8d; int
0x18009b0f2  mov     [rsp+2D8h+var_298], r13; unsigned __int16 *
0x18009b0f7  mov     [rsp+2D8h+var_2A0], r13; unsigned __int16 *
0x18009b0fc  mov     [rsp+2D8h+var_2A8], r13; unsigned __int16 *
0x18009b101  lea     ecx, [rdx+9]; int
0x18009b104  mov     eax, eax
0x18009b106  mov     [rsp+2D8h+var_2B0], r13; unsigned __int16 *
0x18009b10b  mov     [rsp+2D8h+var_2B8], rax; unsigned __int16 *
0x18009b110  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009b115  jmp     loc_18009B1D2
0x18009b11a  mov     edx, [rdi+40h]
0x18009b11d  mov     esi, ebx
0x18009b11f  cmp     edx, 80000000h
0x18009b125  jnz     short loc_18009B16E
0x18009b127  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18009b12d  jz      loc_18009B1D2
0x18009b133  lea     rax, aNull_0; "(NULL)"
0x18009b13a  xor     edx, edx; unsigned __int16
0x18009b13c  mov     [rsp+2D8h+var_290], rax; char *
0x18009b141  lea     r9, aInvalidEventTr_0; "Invalid event trigger in ChildUIThread"
0x18009b148  mov     [rsp+2D8h+var_298], rax; char *
0x18009b14d  xor     r8d, r8d; int
0x18009b150  mov     [rsp+2D8h+var_2A0], rax; char *
0x18009b155  mov     [rsp+2D8h+var_2A8], rax; char *
0x18009b15a  lea     ecx, [rdx+9]; int
0x18009b15d  mov     [rsp+2D8h+var_2B0], rax; char *
0x18009b162  mov     [rsp+2D8h+var_2B8], rax; char *
0x18009b167  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18009b16c  jmp     short loc_18009B1D2
0x18009b16e  cmp     edx, 0F000135h
0x18009b174  jnz     short loc_18009B1A5
0x18009b176  cmp     cs:byte_180306EA4, bl
0x18009b17c  jz      short loc_18009B183
0x18009b17e  call    ?Terminate@CBasicUI@@QEAA_NXZ; CBasicUI::Terminate(void)
0x18009b183  cmp     byte ptr [rdi+0E5h], 1
0x18009b18a  jnz     short loc_18009B19E
0x18009b18c  mov     rax, cs:?CoUninitialize@OLE32@@3P6AXXZEA; void (*OLE32::CoUninitialize)(void)
0x18009b193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b198  mov     [rdi+0E5h], bl
0x18009b19e  mov     r14b, bl
0x18009b1a1  mov     eax, ebx
0x18009b1a3  jmp     short loc_18009B1C2
0x18009b1a5  mov     r8, [rdi+38h]
0x18009b1a9  mov     rcx, rdi
0x18009b1ac  mov     dword ptr [rdi+90h], 80000001h
0x18009b1b6  call    ?ProcessMessage@MsiUIMessageContext@@AEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::ProcessMessage(imtEnum,IMsiRecord *)
0x18009b1bb  mov     dword ptr [rdi+40h], 80000000h
0x18009b1c2  mov     [rdi+90h], eax
0x18009b1c8  mov     rcx, [rdi+58h]; hEvent
0x18009b1cc  call    cs:__imp_SetEvent
0x18009b1d2  test    r14b, r14b
0x18009b1d5  jnz     loc_18009AF86
0x18009b1db  jmp     short loc_18009B228
0x18009b1dd  call    cs:__imp_GetLastError
0x18009b1e3  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18009b1e9  mov     ebp, eax
0x18009b1eb  jz      short loc_18009B228
0x18009b1ed  mov     [rsp+2D8h+var_280], rbx; void *
0x18009b1f2  lea     r9, aWaitFailedInCh; "Wait Failed in ChildUIThread. GetLastEr"...
0x18009b1f9  mov     [rsp+2D8h+var_288], ebx; unsigned int
0x18009b1fd  xor     edx, edx; unsigned __int16
0x18009b1ff  mov     [rsp+2D8h+var_290], r13; unsigned __int16 *
0x18009b204  xor     r8d, r8d; int
0x18009b207  mov     [rsp+2D8h+var_298], r13; unsigned __int16 *
0x18009b20c  mov     [rsp+2D8h+var_2A0], r13; unsigned __int16 *
0x18009b211  mov     [rsp+2D8h+var_2A8], r13; unsigned __int16 *
0x18009b216  lea     ecx, [rdx+9]; int
0x18009b219  mov     [rsp+2D8h+var_2B0], r13; unsigned __int16 *
0x18009b21e  mov     [rsp+2D8h+var_2B8], rbp; unsigned __int16 *
0x18009b223  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009b228  mov     edx, ebp; dwExitCode
0x18009b22a  mov     rcx, r15; hLibModule
0x18009b22d  call    cs:__imp_FreeLibraryAndExitThread
```
