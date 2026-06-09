# FindRdpSessionAgentSystemProcess(ulong,ushort const *,int *)

- ea: `0x180015924`
- end: `0x180015bf1`
- name: `?FindRdpSessionAgentSystemProcess@@YAJKPEBGPEAH@Z`
- size: `717`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180037e30`

## callees

- `0x180003f30`
- `0x180015924`
- `0x18001a280`
- `0x18001ace4`
- `0x18001ad5c`
- `0x1800211c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800159ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015a7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015a7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ba8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800159df`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800159df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001599f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001599f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015b9a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180015ac0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180015ac0`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180015b14`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180015b14`
- `WINSTA!WinStationFreeGAPMemory` at `0x180015bbf`
- `WINSTA!WinStationFreeGAPMemory` at `0x180015bbf`
- `WINSTA!WinStationGetAllProcesses` at `0x180015a33`
- `WINSTA!WinStationGetAllProcesses` at `0x180015a33`

## string_xrefs

- `0x180015ae0`: `RDV: FindRdpSessionAgentSystemPrcoess, OpenProcess failed for process ID %lu [0x%x].`
- `0x180015b30`: `RDV: FindRdpSessionAgentSystemPrcoess, QueryFullProcessImageNameW failed for process ID %lu [0x%x].`
- `0x1800159b2`: `FindRdpSessionAgentSystemProcess`
- `0x180015a0d`: `FindRdpSessionAgentSystemProcess`
- `0x180015a03`: `CreateWellKnownSid failed: 0x%x in %s`
- `0x180015b66`: `RDV: FindRdpSessionAgentSystemPrcoess, CUtils::IsProcessRunningAsUser failed for process ID %lu [0x%x].`

## pseudocode

```c
__int64 __fastcall FindRdpSessionAgentSystemProcess(int a1, wchar_t *a2, int *a3)
{
  HLOCAL v4; // rax
  void *v5; // r12
  signed int v6; // ebx
  void *v7; // rdi
  signed int LastError; // eax
  signed int v9; // eax
  int v10; // r15d
  __int64 i; // r14
  __int64 v12; // rsi
  HANDLE v13; // rax
  signed int v14; // eax
  signed int v15; // eax
  int IsProcessRunningAsUser; // eax
  unsigned int v18; // [rsp+20h] [rbp-E0h] BYREF
  DWORD dwSize; // [rsp+24h] [rbp-DCh] BYREF
  int v20; // [rsp+28h] [rbp-D8h] BYREF
  DWORD cbSid; // [rsp+2Ch] [rbp-D4h] BYREF
  int v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *String2; // [rsp+40h] [rbp-C0h]
  WCHAR ExeName[264]; // [rsp+50h] [rbp-B0h] BYREF

  String2 = a2;
  v22 = a1;
  v23 = 0;
  v18 = 0;
  memset_0(ExeName, 0, 0x208u);
  dwSize = 0;
  cbSid = 68;
  v20 = 0;
  v4 = LocalAlloc(0x40u, 0x44u);
  v5 = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
    _DbgPrintMessage(8, "LocalAlloc failed: 0x%x in %s", -2147024882, "FindRdpSessionAgentSystemProcess");
    goto LABEL_39;
  }
  v7 = 0;
  if ( CreateWellKnownSid(WinLocalSystemSid, 0, v4, &cbSid) )
  {
    v6 = 0;
    goto LABEL_10;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_10:
    if ( (unsigned __int8)WinStationGetAllProcesses(0, 0, &v18, &v23) )
      goto LABEL_15;
    v9 = GetLastError();
    v6 = v9;
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
    if ( v6 >= 0 )
    {
LABEL_15:
      v10 = 0;
      for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
      {
        ExeName[0] = 0;
        if ( v7 )
        {
          CloseHandle(v7);
          v7 = 0;
        }
        v12 = *(_QWORD *)(v23 + 24 * i);
        if ( v22 == *(_DWORD *)(v12 + 88) && !wcsicmp(*(const wchar_t **)(v12 + 64), L"RdpSaUacHelper.exe") )
        {
          v13 = OpenProcess(0x400u, 0, *(_DWORD *)(v12 + 76));
          v7 = v13;
          if ( v13 )
          {
            dwSize = 260;
            if ( QueryFullProcessImageNameW(v13, 0, ExeName, &dwSize) )
            {
              if ( !wcsicmp(ExeName, String2) )
              {
                IsProcessRunningAsUser = CUtils::IsProcessRunningAsUser(v7, v5, &v20);
                v6 = IsProcessRunningAsUser;
                if ( IsProcessRunningAsUser >= 0 )
                {
                  if ( v20 )
                  {
                    v10 = 1;
                    break;
                  }
                }
                else
                {
                  _DbgPrintMessage(
                    8,
                    "RDV: FindRdpSessionAgentSystemPrcoess, CUtils::IsProcessRunningAsUser failed for process ID %lu [0x%x].",
                    *(_DWORD *)(v12 + 76),
                    IsProcessRunningAsUser);
                  v6 = 0;
                }
              }
            }
            else
            {
              v15 = GetLastError();
              if ( v15 > 0 )
                v15 = (unsigned __int16)v15 | 0x80070000;
              _DbgPrintMessage(
                8,
                "RDV: FindRdpSessionAgentSystemPrcoess, QueryFullProcessImageNameW failed for process ID %lu [0x%x].",
                *(unsigned int *)(v12 + 76),
                (unsigned int)v15);
            }
          }
          else
          {
            v14 = GetLastError();
            if ( v14 > 0 )
              v14 = (unsigned __int16)v14 | 0x80070000;
            _DbgPrintMessage(
              8,
              "RDV: FindRdpSessionAgentSystemPrcoess, OpenProcess failed for process ID %lu [0x%x].",
              *(unsigned int *)(v12 + 76),
              (unsigned int)v14);
          }
        }
      }
      *a3 = v10;
    }
    else
    {
      _DbgPrintMessage(
        8,
        "WinStationGetAllProcesses failed: 0x%x in %s",
        (unsigned int)v6,
        "FindRdpSessionAgentSystemProcess");
    }
    goto LABEL_37;
  }
  _DbgPrintMessage(8, "CreateWellKnownSid failed: 0x%x in %s", (unsigned int)v6, "FindRdpSessionAgentSystemProcess");
LABEL_37:
  LocalFree(v5);
  if ( v7 )
    CloseHandle(v7);
LABEL_39:
  if ( v23 )
    WinStationFreeGAPMemory(0, v23, v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015924  mov     [rsp-8+arg_0], rbx
0x180015929  push    rbp
0x18001592a  push    rsi
0x18001592b  push    rdi
0x18001592c  push    r12
0x18001592e  push    r13
0x180015930  push    r14
0x180015932  push    r15
0x180015934  lea     rbp, [rsp-170h]
0x18001593c  sub     rsp, 270h
0x180015943  mov     rax, cs:__security_cookie
0x18001594a  xor     rax, rsp
0x18001594d  mov     [rbp+1A0h+var_40], rax
0x180015954  mov     r13, r8
0x180015957  mov     [rsp+2A0h+String2], rdx
0x18001595c  mov     [rsp+2A0h+var_270], ecx
0x180015960  xor     edx, edx; Val
0x180015962  mov     r8d, 208h; Size
0x180015968  mov     [rsp+2A0h+var_268], 0
0x180015971  lea     rcx, [rsp+2A0h+ExeName]; void *
0x180015976  mov     [rsp+2A0h+var_280], 0
0x18001597e  call    memset_0
0x180015983  mov     edx, 44h ; 'D'; uBytes
0x180015988  mov     [rsp+2A0h+dwSize], 0
0x180015990  mov     [rsp+2A0h+cbSid], edx
0x180015994  mov     [rsp+2A0h+var_278], 0
0x18001599c  lea     ecx, [rdx-4]; uFlags
0x18001599f  call    cs:__imp_LocalAlloc
0x1800159a5  mov     r12, rax
0x1800159a8  test    rax, rax
0x1800159ab  jnz     short loc_1800159D0
0x1800159ad  mov     ebx, 8007000Eh
0x1800159b2  lea     r9, aFindrdpsession; "FindRdpSessionAgentSystemProcess"
0x1800159b9  mov     r8d, ebx
0x1800159bc  lea     rdx, aLocalallocFail; "LocalAlloc failed: 0x%x in %s"
0x1800159c3  lea     ecx, [rax+8]; int
0x1800159c6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800159cb  jmp     loc_180015BAE
0x1800159d0  xor     edi, edi
0x1800159d2  lea     r9, [rsp+2A0h+cbSid]; cbSid
0x1800159d7  mov     r8, r12; pSid
0x1800159da  xor     edx, edx; DomainSid
0x1800159dc  lea     ecx, [rdi+16h]; WellKnownSidType
0x1800159df  call    cs:__imp_CreateWellKnownSid
0x1800159e5  mov     esi, 80070000h
0x1800159ea  test    eax, eax
0x1800159ec  jnz     short loc_180015A23
0x1800159ee  call    cs:__imp_GetLastError
0x1800159f4  mov     ebx, eax
0x1800159f6  test    eax, eax
0x1800159f8  jle     short loc_1800159FF
0x1800159fa  movzx   ebx, ax
0x1800159fd  or      ebx, esi
0x1800159ff  test    ebx, ebx
0x180015a01  jns     short loc_180015A25
0x180015a03  lea     rdx, aCreatewellknow; "CreateWellKnownSid failed: 0x%x in %s"
0x180015a0a  mov     r8d, ebx
0x180015a0d  lea     r9, aFindrdpsession; "FindRdpSessionAgentSystemProcess"
0x180015a14  mov     ecx, 8; int
0x180015a19  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015a1e  jmp     loc_180015B97
0x180015a23  xor     ebx, ebx
0x180015a25  lea     r9, [rsp+2A0h+var_268]
0x180015a2a  xor     edx, edx
0x180015a2c  lea     r8, [rsp+2A0h+var_280]
0x180015a31  xor     ecx, ecx
0x180015a33  call    cs:__imp_WinStationGetAllProcesses
0x180015a39  test    al, al
0x180015a3b  jnz     short loc_180015A5B
0x180015a3d  call    cs:__imp_GetLastError
0x180015a43  mov     ebx, eax
0x180015a45  test    eax, eax
0x180015a47  jle     short loc_180015A4E
0x180015a49  movzx   ebx, ax
0x180015a4c  or      ebx, esi
0x180015a4e  test    ebx, ebx
0x180015a50  jns     short loc_180015A5B
0x180015a52  lea     rdx, aWinstationgeta_0; "WinStationGetAllProcesses failed: 0x%x "...
0x180015a59  jmp     short loc_180015A0A
0x180015a5b  xor     r15d, r15d
0x180015a5e  xor     r14d, r14d
0x180015a61  cmp     r14d, [rsp+2A0h+var_280]
0x180015a66  jnb     loc_180015B93
0x180015a6c  xor     eax, eax
0x180015a6e  mov     [rsp+2A0h+ExeName], ax
0x180015a73  test    rdi, rdi
0x180015a76  jz      short loc_180015A83
0x180015a78  mov     rcx, rdi; hObject
0x180015a7b  call    cs:__imp_CloseHandle
0x180015a81  xor     edi, edi
0x180015a83  mov     rax, [rsp+2A0h+var_268]
0x180015a88  lea     rcx, [r14+r14*2]
0x180015a8c  mov     rsi, [rax+rcx*8]
0x180015a90  mov     eax, [rsp+2A0h+var_270]
0x180015a94  cmp     eax, [rsi+58h]
0x180015a97  jnz     loc_180015B85
0x180015a9d  mov     rcx, [rsi+40h]; String1
0x180015aa1  lea     rdx, aRdpsauachelper; "RdpSaUacHelper.exe"
0x180015aa8  call    _wcsicmp
0x180015aad  test    eax, eax
0x180015aaf  jnz     loc_180015B85
0x180015ab5  mov     r8d, [rsi+4Ch]; dwProcessId
0x180015ab9  xor     edx, edx; bInheritHandle
0x180015abb  mov     ecx, 400h; dwDesiredAccess
0x180015ac0  call    cs:__imp_OpenProcess
0x180015ac6  mov     rdi, rax
0x180015ac9  test    rax, rax
0x180015acc  jnz     short loc_180015AFD
0x180015ace  call    cs:__imp_GetLastError
0x180015ad4  test    eax, eax
0x180015ad6  jle     short loc_180015AE0
0x180015ad8  movzx   eax, ax
0x180015adb  or      eax, 80070000h
0x180015ae0  lea     rdx, aRdvFindrdpsess_0; "RDV: FindRdpSessionAgentSystemPrcoess, "...
0x180015ae7  mov     r8d, [rsi+4Ch]
0x180015aeb  mov     r9d, eax
0x180015aee  mov     ecx, 8; int
0x180015af3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015af8  jmp     loc_180015B85
0x180015afd  lea     r9, [rsp+2A0h+dwSize]; lpdwSize
0x180015b02  mov     [rsp+2A0h+dwSize], 104h
0x180015b0a  lea     r8, [rsp+2A0h+ExeName]; lpExeName
0x180015b0f  xor     edx, edx; dwFlags
0x180015b11  mov     rcx, rdi; hProcess
0x180015b14  call    cs:__imp_QueryFullProcessImageNameW
0x180015b1a  test    eax, eax
0x180015b1c  jnz     short loc_180015B39
0x180015b1e  call    cs:__imp_GetLastError
0x180015b24  test    eax, eax
0x180015b26  jle     short loc_180015B30
0x180015b28  movzx   eax, ax
0x180015b2b  or      eax, 80070000h
0x180015b30  lea     rdx, aRdvFindrdpsess; "RDV: FindRdpSessionAgentSystemPrcoess, "...
0x180015b37  jmp     short loc_180015AE7
0x180015b39  mov     rdx, [rsp+2A0h+String2]; String2
0x180015b3e  lea     rcx, [rsp+2A0h+ExeName]; String1
0x180015b43  call    _wcsicmp
0x180015b48  test    eax, eax
0x180015b4a  jnz     short loc_180015B85
0x180015b4c  lea     r8, [rsp+2A0h+var_278]; int *
0x180015b51  mov     rdx, r12; void *
0x180015b54  mov     rcx, rdi; void *
0x180015b57  call    ?IsProcessRunningAsUser@CUtils@@SAJPEAX0PEAH@Z; CUtils::IsProcessRunningAsUser(void *,void *,int *)
0x180015b5c  mov     ebx, eax
0x180015b5e  test    eax, eax
0x180015b60  jns     short loc_180015B7E
0x180015b62  mov     r8d, [rsi+4Ch]
0x180015b66  lea     rdx, aRdvFindrdpsess_1; "RDV: FindRdpSessionAgentSystemPrcoess, "...
0x180015b6d  mov     r9d, eax
0x180015b70  mov     ecx, 8; int
0x180015b75  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015b7a  xor     ebx, ebx
0x180015b7c  jmp     short loc_180015B85
0x180015b7e  cmp     [rsp+2A0h+var_278], r15d
0x180015b83  jnz     short loc_180015B8D
0x180015b85  inc     r14d
0x180015b88  jmp     loc_180015A61
0x180015b8d  mov     r15d, 1
0x180015b93  mov     [r13+0], r15d
0x180015b97  mov     rcx, r12; hMem
0x180015b9a  call    cs:__imp_LocalFree
0x180015ba0  test    rdi, rdi
0x180015ba3  jz      short loc_180015BAE
0x180015ba5  mov     rcx, rdi; hObject
0x180015ba8  call    cs:__imp_CloseHandle
0x180015bae  mov     rdx, [rsp+2A0h+var_268]
0x180015bb3  test    rdx, rdx
0x180015bb6  jz      short loc_180015BC5
0x180015bb8  mov     r8d, [rsp+2A0h+var_280]
0x180015bbd  xor     ecx, ecx
0x180015bbf  call    cs:__imp_WinStationFreeGAPMemory
0x180015bc5  mov     eax, ebx
0x180015bc7  mov     rcx, [rbp+1A0h+var_40]
0x180015bce  xor     rcx, rsp; StackCookie
0x180015bd1  call    __security_check_cookie
0x180015bd6  mov     rbx, [rsp+2A0h+arg_0]
0x180015bde  add     rsp, 270h
0x180015be5  pop     r15
0x180015be7  pop     r14
0x180015be9  pop     r13
0x180015beb  pop     r12
0x180015bed  pop     rdi
0x180015bee  pop     rsi
0x180015bef  pop     rbp
0x180015bf0  retn
```
