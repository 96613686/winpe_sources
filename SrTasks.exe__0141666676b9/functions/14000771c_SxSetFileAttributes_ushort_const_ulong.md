# SxSetFileAttributes(ushort const *,ulong)

- ea: `0x14000771c`
- end: `0x14000794b`
- name: `?SxSetFileAttributes@@YAJPEBGK@Z`
- size: `559`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x1400074d8`
- `0x1400075cc`

## callees

- `0x140002e1c`
- `0x140005658`
- `0x140006cc8`
- `0x140006d58`
- `0x14000771c`
- `0x14000e324`
- `0x14000e41c`
- `0x140010980`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140007917`
- `KERNEL32!CloseHandle` at `0x140007917`
- `KERNEL32!CreateFileW` at `0x1400077ff`
- `KERNEL32!CreateFileW` at `0x1400077ff`
- `ntdll!NtSetInformationFile` at `0x1400078ef`
- `ntdll!NtSetInformationFile` at `0x1400078ef`
- `ntdll!NtQueryInformationFile` at `0x1400078b5`
- `ntdll!NtQueryInformationFile` at `0x1400078b5`

## string_xrefs

- `0x14000777f`: `SxSetFileAttributes`

## pseudocode

```c
__int64 __fastcall SxSetFileAttributes(LPCWSTR lpFileName, int a2)
{
  int LastFailureAsHRESULT; // ebx
  HANDLE FileW; // rdi
  unsigned int v6; // eax
  __int16 v7; // ax
  unsigned int v8; // eax
  int v10; // [rsp+40h] [rbp-49h] BYREF
  __int16 v11; // [rsp+44h] [rbp-45h]
  __int16 v12; // [rsp+46h] [rbp-43h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-11h] BYREF
  _BYTE FileInformation[40]; // [rsp+88h] [rbp-1h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "SxSetFileAttributes", 0x94Cu, 1u);
  memset(FileInformation, 0, sizeof(FileInformation));
  IoStatusBlock = 0;
  if ( !lpFileName )
  {
    LastFailureAsHRESULT = -2147024809;
    v10 = -2147024809;
    v12 = 2386;
    goto LABEL_18;
  }
  v10 = 0;
  v11 = 2386;
  FileW = CreateFileW(lpFileName, 0x180u, 7u, 0, 3u, 0x2200000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v10 = 0;
    v11 = 2395;
    memset(FileInformation, 0, sizeof(FileInformation));
    v6 = NtQueryInformationFile(FileW, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v6);
    v10 = LastFailureAsHRESULT;
    v7 = 2399;
    if ( LastFailureAsHRESULT >= 0
      && (v11 = 2399,
          *(_DWORD *)&FileInformation[32] = a2 | 0x80,
          v8 = NtSetInformationFile(FileW, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation),
          LastFailureAsHRESULT = HRESULTFromNTSTATUS(v8),
          v10 = LastFailureAsHRESULT,
          v7 = 2405,
          LastFailureAsHRESULT >= 0) )
    {
      v11 = 2405;
    }
    else
    {
      v12 = v7;
    }
LABEL_17:
    CloseHandle(FileW);
    goto LABEL_18;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT();
  v10 = LastFailureAsHRESULT;
  v12 = 2395;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      (unsigned int)WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids,
      (unsigned int)"sh.IsValid()",
      (__int64)lpFileName,
      LastFailureAsHRESULT);
    LastFailureAsHRESULT = v10;
  }
  if ( FileW != (HANDLE)-1LL && FileW )
    goto LABEL_17;
LABEL_18:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x14000771c  mov     [rsp-8+arg_10], rbx
0x140007721  push    rbp
0x140007722  push    rsi
0x140007723  push    rdi
0x140007724  push    r12
0x140007726  push    r14
0x140007728  lea     rbp, [rsp-37h]
0x14000772d  sub     rsp, 0C0h
0x140007734  mov     rax, cs:__security_cookie
0x14000773b  xor     rax, rsp
0x14000773e  mov     [rbp+57h+var_30], rax
0x140007742  mov     r14d, edx
0x140007745  mov     rsi, rcx
0x140007748  mov     rcx, cs:WPP_GLOBAL_Control
0x14000774f  lea     r12, WPP_GLOBAL_Control
0x140007756  cmp     rcx, r12
0x140007759  jz      short loc_140007779
0x14000775b  test    dword ptr [rcx+1Ch], 20000000h
0x140007762  jz      short loc_140007779
0x140007764  mov     rcx, [rcx+10h]
0x140007768  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x14000776f  mov     edx, 43h ; 'C'
0x140007774  call    WPP_SF_
0x140007779  mov     r9d, 1; unsigned __int16
0x14000777f  lea     rdx, aSxsetfileattri; "SxSetFileAttributes"
0x140007786  mov     r8d, 94Ch; unsigned __int16
0x14000778c  lea     rcx, [rbp+57h+var_A0]; this
0x140007790  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140007795  xorps   xmm0, xmm0
0x140007798  mov     dword ptr [rbp+57h+FileInformation], 0
0x14000779f  xor     eax, eax
0x1400077a1  mov     [rbp+57h+var_34], eax
0x1400077a4  movups  [rbp+57h+FileInformation+4], xmm0
0x1400077a8  movups  [rbp+57h+var_44], xmm0
0x1400077ac  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400077b0  test    rsi, rsi
0x1400077b3  jnz     short loc_1400077CB
0x1400077b5  mov     ebx, 80070057h
0x1400077ba  mov     eax, 952h
0x1400077bf  mov     [rbp+57h+var_A0], ebx
0x1400077c2  mov     [rbp+57h+var_9A], ax
0x1400077c6  jmp     loc_14000791D
0x1400077cb  xor     r9d, r9d; lpSecurityAttributes
0x1400077ce  mov     [rbp+57h+var_A0], eax
0x1400077d1  mov     eax, 952h
0x1400077d6  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x1400077df  mov     [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1400077e7  mov     edx, 180h; dwDesiredAccess
0x1400077ec  mov     rcx, rsi; lpFileName
0x1400077ef  mov     [rbp+57h+var_9C], ax
0x1400077f3  lea     r8d, [r9+7]; dwShareMode
0x1400077f7  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1400077ff  call    cs:__imp_CreateFileW
0x140007805  mov     rdi, rax
0x140007808  inc     rax
0x14000780b  test    rax, 0FFFFFFFFFFFFFFFEh
0x140007811  jnz     short loc_14000787B
0x140007813  call    GetLastFailureAsHRESULT
0x140007818  mov     ebx, eax
0x14000781a  mov     [rbp+57h+var_A0], eax
0x14000781d  mov     eax, 95Bh
0x140007822  mov     [rbp+57h+var_9A], ax
0x140007826  mov     rcx, cs:WPP_GLOBAL_Control
0x14000782d  cmp     rcx, r12
0x140007830  jz      short loc_140007863
0x140007832  test    dword ptr [rcx+1Ch], 2000000h
0x140007839  jz      short loc_140007863
0x14000783b  mov     rcx, [rcx+10h]
0x14000783f  lea     r9, aShIsvalid; "sh.IsValid()"
0x140007846  mov     edx, 44h ; 'D'
0x14000784b  mov     [rsp+0E0h+dwFlagsAndAttributes], ebx
0x14000784f  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x140007856  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rsi
0x14000785b  call    WPP_SF_sSd
0x140007860  mov     ebx, [rbp+57h+var_A0]
0x140007863  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140007867  jz      loc_14000791D
0x14000786d  test    rdi, rdi
0x140007870  jz      loc_14000791D
0x140007876  jmp     loc_140007914
0x14000787b  xorps   xmm0, xmm0
0x14000787e  mov     [rbp+57h+var_A0], 0
0x140007885  mov     eax, 95Bh
0x14000788a  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14000788e  mov     [rbp+57h+var_9C], ax
0x140007892  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140007896  xor     eax, eax
0x140007898  mov     rcx, rdi; FileHandle
0x14000789b  movups  [rbp+57h+FileInformation], xmm0
0x14000789f  mov     qword ptr [rbp+57h+var_44+0Ch], rax
0x1400078a3  movups  xmmword ptr [rbp+0Fh], xmm0
0x1400078a7  lea     r12d, [rax+28h]
0x1400078ab  lea     esi, [rax+4]
0x1400078ae  mov     r9d, r12d; Length
0x1400078b1  mov     [rsp+0E0h+dwCreationDisposition], esi; FileInformationClass
0x1400078b5  call    cs:__imp_NtQueryInformationFile
0x1400078bb  mov     ecx, eax
0x1400078bd  call    HRESULTFromNTSTATUS
0x1400078c2  mov     ebx, eax
0x1400078c4  mov     [rbp+57h+var_A0], eax
0x1400078c7  test    eax, eax
0x1400078c9  mov     eax, 95Fh
0x1400078ce  js      short loc_14000790A
0x1400078d0  bts     r14d, 7
0x1400078d5  mov     [rbp+57h+var_9C], ax
0x1400078d9  mov     r9d, r12d; Length
0x1400078dc  mov     dword ptr [rbp+57h+var_44+0Ch], r14d
0x1400078e0  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1400078e4  mov     [rsp+0E0h+dwCreationDisposition], esi; FileInformationClass
0x1400078e8  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400078ec  mov     rcx, rdi; FileHandle
0x1400078ef  call    cs:__imp_NtSetInformationFile
0x1400078f5  mov     ecx, eax
0x1400078f7  call    HRESULTFromNTSTATUS
0x1400078fc  mov     ebx, eax
0x1400078fe  mov     [rbp+57h+var_A0], eax
0x140007901  test    eax, eax
0x140007903  mov     eax, 965h
0x140007908  jns     short loc_140007910
0x14000790a  mov     [rbp+57h+var_9A], ax
0x14000790e  jmp     short loc_140007914
0x140007910  mov     [rbp+57h+var_9C], ax
0x140007914  mov     rcx, rdi; hObject
0x140007917  call    cs:__imp_CloseHandle
0x14000791d  lea     rcx, [rbp+57h+var_A0]; this
0x140007921  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140007926  mov     eax, ebx
0x140007928  mov     rcx, [rbp+57h+var_30]
0x14000792c  xor     rcx, rsp; StackCookie
0x14000792f  call    __security_check_cookie
0x140007934  mov     rbx, [rsp+0E0h+arg_10]
0x14000793c  add     rsp, 0C0h
0x140007943  pop     r14
0x140007945  pop     r12
0x140007947  pop     rdi
0x140007948  pop     rsi
0x140007949  pop     rbp
0x14000794a  retn
```
