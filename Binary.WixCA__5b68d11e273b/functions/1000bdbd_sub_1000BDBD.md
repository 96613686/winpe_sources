# sub_1000BDBD

- ea: `0x1000bdbd`
- end: `0x1000c0be`
- name: `sub_1000BDBD`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1000c0be`

## callees

- `0x1000ad15`
- `0x1000ae3a`
- `0x1000ae5c`
- `0x1000aeff`
- `0x1000af39`
- `0x1000b0b5`
- `0x1000bdbd`
- `0x10010720`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x1000be36`
- `ADVAPI32!OpenProcessToken` at `0x1000be36`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1000bef4`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1000bf38`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1000c079`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1000bedd`
- `ADVAPI32!AdjustTokenPrivileges` at `0x1000c079`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1000be8b`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1000be8b`
- `KERNEL32!CloseHandle` at `0x1000c061`
- `KERNEL32!CloseHandle` at `0x1000c092`
- `KERNEL32!CloseHandle` at `0x1000c061`
- `KERNEL32!CloseHandle` at `0x1000c092`
- `KERNEL32!GetLastError` at `0x1000be40`
- `KERNEL32!GetLastError` at `0x1000be95`
- `KERNEL32!GetLastError` at `0x1000bf3e`
- `KERNEL32!GetLastError` at `0x1000bfa0`
- `KERNEL32!GetLastError` at `0x1000c01e`
- `KERNEL32!GetLastError` at `0x1000be40`
- `KERNEL32!GetLastError` at `0x1000be95`
- `KERNEL32!GetLastError` at `0x1000bf3e`
- `KERNEL32!GetLastError` at `0x1000bfa0`
- `KERNEL32!GetLastError` at `0x1000c01e`
- `KERNEL32!OpenProcess` at `0x1000bf75`
- `KERNEL32!OpenProcess` at `0x1000bf75`
- `KERNEL32!GetCurrentProcess` at `0x1000be1c`
- `KERNEL32!GetCurrentProcess` at `0x1000be33`
- `KERNEL32!GetCurrentProcess` at `0x1000bdd3`
- `KERNEL32!EnterCriticalSection` at `0x1000bfcd`
- `KERNEL32!EnterCriticalSection` at `0x1000bfcd`
- `KERNEL32!LeaveCriticalSection` at `0x1000c0a5`
- `KERNEL32!LeaveCriticalSection` at `0x1000c0a5`
- `KERNEL32!GetProcessTimes` at `0x1000bf96`
- `KERNEL32!GetProcessTimes` at `0x1000bf96`

## string_xrefs

- `0x1000be80`: `SeDebugPrivilege`

## pseudocode

```c
signed int __stdcall sub_1000BDBD(struct _RTL_CRITICAL_SECTION *a1, DWORD a2)
{
  signed int v2; // esi
  struct _TOKEN_PRIVILEGES *v3; // edi
  HANDLE CurrentProcess; // eax
  HANDLE v5; // eax
  signed int v6; // eax
  bool v7; // sf
  signed int v8; // eax
  bool v9; // sf
  struct _TOKEN_PRIVILEGES *v10; // eax
  struct _TOKEN_PRIVILEGES *v11; // eax
  signed int v12; // eax
  bool v13; // sf
  HANDLE v14; // ebx
  signed int LastError; // eax
  bool v16; // sf
  LPCRITICAL_SECTION v17; // esi
  int v18; // eax
  LPCRITICAL_SECTION v19; // edx
  DWORD *v20; // eax
  signed int v21; // eax
  struct _FILETIME ExitTime; // [esp+Ch] [ebp-58h] BYREF
  struct _FILETIME KernelTime; // [esp+14h] [ebp-50h] BYREF
  struct _FILETIME UserTime; // [esp+1Ch] [ebp-48h] BYREF
  DWORD dwHighDateTime; // [esp+24h] [ebp-40h]
  DWORD dwLowDateTime; // [esp+28h] [ebp-3Ch]
  struct _FILETIME CreationTime; // [esp+2Ch] [ebp-38h] BYREF
  int v29; // [esp+34h] [ebp-30h]
  int v30; // [esp+38h] [ebp-2Ch]
  DWORD dwProcessId; // [esp+3Ch] [ebp-28h]
  int v32; // [esp+40h] [ebp-24h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [esp+44h] [ebp-20h]
  DWORD BufferLength; // [esp+48h] [ebp-1Ch] BYREF
  HANDLE TokenHandle; // [esp+4Ch] [ebp-18h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [esp+50h] [ebp-14h] BYREF

  lpCriticalSection = a1;
  dwProcessId = a2;
  CreationTime.dwLowDateTime = 0;
  memset(&NewState, 0, sizeof(NewState));
  v2 = 0;
  CreationTime.dwHighDateTime = 0;
  ExitTime.dwLowDateTime = 0;
  ExitTime.dwHighDateTime = 0;
  KernelTime.dwLowDateTime = 0;
  KernelTime.dwHighDateTime = 0;
  UserTime.dwLowDateTime = 0;
  UserTime.dwHighDateTime = 0;
  v29 = 0;
  TokenHandle = 0;
  v3 = 0;
  BufferLength = 0;
  v30 = 0;
  v32 = 0;
  CurrentProcess = GetCurrentProcess();
  sub_1000B0B5(CurrentProcess, (int)&v32);
  if ( !v32 )
  {
LABEL_26:
    v14 = OpenProcess(0x400u, 0, dwProcessId);
    if ( v14 )
    {
      if ( GetProcessTimes(v14, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
      {
        v17 = lpCriticalSection;
        EnterCriticalSection(lpCriticalSection);
        dwLowDateTime = CreationTime.dwLowDateTime;
        dwHighDateTime = CreationTime.dwHighDateTime;
        v18 = v17[1].SpinCount + 1;
        v29 = 1;
        v2 = sub_1000AE5C(&v17[2], v18, 12, 5);
        if ( v2 >= 0 )
        {
          v19 = lpCriticalSection;
          v20 = (DWORD *)(&lpCriticalSection[2].DebugInfo->Type + 6 * lpCriticalSection[1].SpinCount);
          *v20 = dwProcessId;
          v20[1] = dwLowDateTime;
          v20[2] = dwHighDateTime;
          ++v19[1].SpinCount;
        }
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        v16 = LastError < 0;
        if ( LastError > 0 )
        {
          v2 = (unsigned __int16)LastError | 0x80070000;
          v16 = 1;
        }
        if ( !v16 )
          v2 = -2147467259;
        nullsub_1("d:\\a\\_work\\1\\s\\src\\libs\\dutil\\rmutil.cpp", 198, v2);
      }
      goto LABEL_42;
    }
    v21 = GetLastError();
    if ( v21 == 5 )
    {
      v2 = -2147023728;
    }
    else if ( v21 )
    {
      if ( v21 > 0 )
        v2 = (unsigned __int16)v21 | 0x80070000;
      else
        v2 = v21;
      nullsub_1("d:\\a\\_work\\1\\s\\src\\libs\\dutil\\rmutil.cpp", 216, v2);
LABEL_42:
      if ( v14 )
        CloseHandle(v14);
    }
    if ( v30 )
      AdjustTokenPrivileges(TokenHandle, 0, v3, 0, 0, 0);
    goto LABEL_46;
  }
  v5 = GetCurrentProcess();
  if ( !OpenProcessToken(v5, 0x28u, &TokenHandle) )
  {
    v6 = GetLastError();
    v2 = v6;
    v7 = v6 < 0;
    if ( v6 > 0 )
    {
      v2 = (unsigned __int16)v6 | 0x80070000;
      v7 = 1;
    }
    if ( !v7 )
      v2 = -2147467259;
    nullsub_1("d:\\a\\_work\\1\\s\\src\\libs\\dutil\\rmutil.cpp", 164, v2);
    goto LABEL_48;
  }
  NewState.Privileges[0].Attributes = 2;
  NewState.PrivilegeCount = 1;
  if ( !LookupPrivilegeValueW(0, L"SeDebugPrivilege", &NewState.Privileges[0].Luid) )
  {
    v8 = GetLastError();
    v2 = v8;
    v9 = v8 < 0;
    if ( v8 > 0 )
    {
      v2 = (unsigned __int16)v8 | 0x80070000;
      v9 = 1;
    }
    if ( !v9 )
      v2 = -2147467259;
    nullsub_1("d:\\a\\_work\\1\\s\\src\\libs\\dutil\\rmutil.cpp", 171, v2);
    goto LABEL_48;
  }
  BufferLength = 16;
  v10 = (struct _TOKEN_PRIVILEGES *)sub_1000AE3A(0x10u, 1);
  v3 = v10;
  if ( !v10 )
  {
    v2 = -2147024882;
    nullsub_1("d:\\a\\_work\\1\\s\\src\\libs\\dutil\\rmutil.cpp", 176, -2147024882);
    goto LABEL_48;
  }
  if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, BufferLength, v10, &BufferLength) )
  {
LABEL_25:
    v30 = 1;
    goto LABEL_26;
  }
  v11 = (struct _TOKEN_PRIVILEGES *)sub_1000AF39(v3, BufferLength, 1);
  if ( v11 )
  {
    v3 = v11;
    if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, BufferLength, v11, &BufferLength) )
    {
      v12 = GetLastError();
      v2 = v12;
      v13 = v12 < 0;
      if ( v12 > 0 )
      {
        v2 = (unsigned __int16)v12 | 0x80070000;
        v13 = 1;
      }
      if ( !v13 )
        v2 = -2147467259;
      nullsub_1("d:\\a\\_work\\1\\s\\src\\libs\\dutil\\rmutil.cpp", 186, v2);
      goto LABEL_46;
    }
    goto LABEL_25;
  }
  v2 = -2147024882;
  nullsub_1("d:\\a\\_work\\1\\s\\src\\libs\\dutil\\rmutil.cpp", 181, -2147024882);
LABEL_46:
  if ( v3 )
    sub_1000AEFF(v3);
LABEL_48:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v29 )
    LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x1000bdbd  push    ebp
0x1000bdbe  mov     ebp, esp
0x1000bdc0  sub     esp, 58h
0x1000bdc3  mov     eax, ___security_cookie
0x1000bdc8  xor     eax, ebp
0x1000bdca  mov     [ebp+var_4], eax
0x1000bdcd  mov     eax, [ebp+arg_0]
0x1000bdd0  xor     ecx, ecx
0x1000bdd2  push    ebx
0x1000bdd3  mov     ebx, ds:GetCurrentProcess
0x1000bdd9  mov     [ebp+lpCriticalSection], eax
0x1000bddc  mov     eax, [ebp+arg_4]
0x1000bddf  push    esi
0x1000bde0  push    edi
0x1000bde1  mov     [ebp+dwProcessId], eax
0x1000bde4  lea     edi, [ebp+NewState]
0x1000bde7  xor     eax, eax
0x1000bde9  mov     [ebp+CreationTime.dwLowDateTime], ecx
0x1000bdec  stosd
0x1000bded  mov     esi, ecx
0x1000bdef  mov     [ebp+CreationTime.dwHighDateTime], ecx
0x1000bdf2  mov     [ebp+ExitTime.dwLowDateTime], ecx
0x1000bdf5  mov     [ebp+ExitTime.dwHighDateTime], ecx
0x1000bdf8  stosd
0x1000bdf9  mov     [ebp+KernelTime.dwLowDateTime], ecx
0x1000bdfc  mov     [ebp+KernelTime.dwHighDateTime], ecx
0x1000bdff  mov     [ebp+UserTime.dwLowDateTime], ecx
0x1000be02  stosd
0x1000be03  mov     [ebp+UserTime.dwHighDateTime], ecx
0x1000be06  mov     [ebp+var_30], ecx
0x1000be09  mov     [ebp+TokenHandle], ecx
0x1000be0c  stosd
0x1000be0d  lea     eax, [ebp+var_24]
0x1000be10  push    eax; int
0x1000be11  mov     edi, ecx
0x1000be13  mov     [ebp+BufferLength], ecx
0x1000be16  mov     [ebp+var_2C], ecx
0x1000be19  mov     [ebp+var_24], ecx
0x1000be1c  call    ebx ; GetCurrentProcess
0x1000be1e  push    eax; ProcessHandle
0x1000be1f  call    sub_1000B0B5
0x1000be24  cmp     [ebp+var_24], esi
0x1000be27  jz      loc_1000BF6B
0x1000be2d  lea     eax, [ebp+TokenHandle]
0x1000be30  push    eax; TokenHandle
0x1000be31  push    28h ; '('; DesiredAccess
0x1000be33  call    ebx ; GetCurrentProcess
0x1000be35  push    eax; ProcessHandle
0x1000be36  call    ds:OpenProcessToken
0x1000be3c  test    eax, eax
0x1000be3e  jnz     short loc_1000BE73
0x1000be40  call    ds:GetLastError
0x1000be46  mov     esi, eax
0x1000be48  test    esi, esi
0x1000be4a  jle     short loc_1000BE57
0x1000be4c  movzx   esi, si
0x1000be4f  or      esi, 80070000h
0x1000be55  test    esi, esi
0x1000be57  js      short loc_1000BE5E
0x1000be59  mov     esi, 80004005h
0x1000be5e  push    esi
0x1000be5f  push    0A4h
0x1000be64  push    offset aDAWork1SSrcLib_5; "d:\\a\\_work\\1\\s\\src\\libs\\dutil\\r"...
0x1000be69  call    nullsub_1
0x1000be6e  jmp     loc_1000C089
0x1000be73  lea     eax, [ebp+NewState.Privileges]
0x1000be76  mov     [ebp+NewState.Privileges.Attributes], 2
0x1000be7d  push    eax; lpLuid
0x1000be7e  xor     ebx, ebx
0x1000be80  push    offset aSedebugprivile; "SeDebugPrivilege"
0x1000be85  inc     ebx
0x1000be86  push    0; lpSystemName
0x1000be88  mov     [ebp+NewState.PrivilegeCount], ebx
0x1000be8b  call    ds:LookupPrivilegeValueW
0x1000be91  test    eax, eax
0x1000be93  jnz     short loc_1000BEBB
0x1000be95  call    ds:GetLastError
0x1000be9b  mov     esi, eax
0x1000be9d  test    esi, esi
0x1000be9f  jle     short loc_1000BEAC
0x1000bea1  movzx   esi, si
0x1000bea4  or      esi, 80070000h
0x1000beaa  test    esi, esi
0x1000beac  js      short loc_1000BEB3
0x1000beae  mov     esi, 80004005h
0x1000beb3  push    esi
0x1000beb4  push    0ABh
0x1000beb9  jmp     short loc_1000BE64
0x1000bebb  push    10h
0x1000bebd  pop     eax
0x1000bebe  push    ebx; int
0x1000bebf  push    eax; dwBytes
0x1000bec0  mov     [ebp+BufferLength], eax
0x1000bec3  call    sub_1000AE3A
0x1000bec8  mov     edi, eax
0x1000beca  test    edi, edi
0x1000becc  jnz     short loc_1000BEDD
0x1000bece  mov     eax, 8007000Eh
0x1000bed3  push    eax
0x1000bed4  mov     esi, eax
0x1000bed6  push    0B0h
0x1000bedb  jmp     short loc_1000BE64
0x1000bedd  mov     ebx, ds:AdjustTokenPrivileges
0x1000bee3  lea     eax, [ebp+BufferLength]
0x1000bee6  push    eax; ReturnLength
0x1000bee7  push    edi; PreviousState
0x1000bee8  push    [ebp+BufferLength]; BufferLength
0x1000beeb  lea     eax, [ebp+NewState]
0x1000beee  push    eax; NewState
0x1000beef  push    0; DisableAllPrivileges
0x1000bef1  push    [ebp+TokenHandle]; TokenHandle
0x1000bef4  call    ebx ; AdjustTokenPrivileges
0x1000bef6  test    eax, eax
0x1000bef8  jnz     short loc_1000BF64
0x1000befa  push    1; int
0x1000befc  push    [ebp+BufferLength]; dwBytes
0x1000beff  push    edi; lpMem
0x1000bf00  call    sub_1000AF39
0x1000bf05  test    eax, eax
0x1000bf07  jnz     short loc_1000BF25
0x1000bf09  mov     eax, 8007000Eh
0x1000bf0e  push    eax
0x1000bf0f  mov     esi, eax
0x1000bf11  push    0B5h
0x1000bf16  push    offset aDAWork1SSrcLib_5; "d:\\a\\_work\\1\\s\\src\\libs\\dutil\\r"...
0x1000bf1b  call    nullsub_1
0x1000bf20  jmp     loc_1000C07F
0x1000bf25  lea     ecx, [ebp+BufferLength]
0x1000bf28  mov     edi, eax
0x1000bf2a  push    ecx; ReturnLength
0x1000bf2b  push    eax; PreviousState
0x1000bf2c  push    [ebp+BufferLength]; BufferLength
0x1000bf2f  lea     eax, [ebp+NewState]
0x1000bf32  push    eax; NewState
0x1000bf33  push    0; DisableAllPrivileges
0x1000bf35  push    [ebp+TokenHandle]; TokenHandle
0x1000bf38  call    ebx ; AdjustTokenPrivileges
0x1000bf3a  test    eax, eax
0x1000bf3c  jnz     short loc_1000BF64
0x1000bf3e  call    ds:GetLastError
0x1000bf44  mov     esi, eax
0x1000bf46  test    esi, esi
0x1000bf48  jle     short loc_1000BF55
0x1000bf4a  movzx   esi, si
0x1000bf4d  or      esi, 80070000h
0x1000bf53  test    esi, esi
0x1000bf55  js      short loc_1000BF5C
0x1000bf57  mov     esi, 80004005h
0x1000bf5c  push    esi
0x1000bf5d  push    0BAh
0x1000bf62  jmp     short loc_1000BF16
0x1000bf64  mov     [ebp+var_2C], 1
0x1000bf6b  push    [ebp+dwProcessId]; dwProcessId
0x1000bf6e  push    0; bInheritHandle
0x1000bf70  push    400h; dwDesiredAccess
0x1000bf75  call    ds:OpenProcess
0x1000bf7b  mov     ebx, eax
0x1000bf7d  test    ebx, ebx
0x1000bf7f  jz      loc_1000C01E
0x1000bf85  lea     eax, [ebp+UserTime]
0x1000bf88  push    eax; lpUserTime
0x1000bf89  lea     eax, [ebp+KernelTime]
0x1000bf8c  push    eax; lpKernelTime
0x1000bf8d  lea     eax, [ebp+ExitTime]
0x1000bf90  push    eax; lpExitTime
0x1000bf91  lea     eax, [ebp+CreationTime]
0x1000bf94  push    eax; lpCreationTime
0x1000bf95  push    ebx; hProcess
0x1000bf96  call    ds:GetProcessTimes
0x1000bf9c  test    eax, eax
0x1000bf9e  jnz     short loc_1000BFC9
0x1000bfa0  call    ds:GetLastError
0x1000bfa6  mov     esi, eax
0x1000bfa8  test    esi, esi
0x1000bfaa  jle     short loc_1000BFB7
0x1000bfac  movzx   esi, si
0x1000bfaf  or      esi, 80070000h
0x1000bfb5  test    esi, esi
0x1000bfb7  js      short loc_1000BFBE
0x1000bfb9  mov     esi, 80004005h
0x1000bfbe  push    esi
0x1000bfbf  push    0C6h
0x1000bfc4  jmp     loc_1000C052
0x1000bfc9  mov     esi, [ebp+lpCriticalSection]
0x1000bfcc  push    esi; lpCriticalSection
0x1000bfcd  call    ds:EnterCriticalSection
0x1000bfd3  mov     eax, [ebp+CreationTime.dwLowDateTime]
0x1000bfd6  lea     ecx, [esi+30h]
0x1000bfd9  mov     [ebp+var_3C], eax
0x1000bfdc  mov     eax, [ebp+CreationTime.dwHighDateTime]
0x1000bfdf  mov     [ebp+var_40], eax
0x1000bfe2  mov     eax, [esi+2Ch]
0x1000bfe5  push    5
0x1000bfe7  push    0Ch
0x1000bfe9  inc     eax
0x1000bfea  mov     [ebp+var_30], 1
0x1000bff1  push    eax
0x1000bff2  push    ecx
0x1000bff3  call    sub_1000AE5C
0x1000bff8  mov     esi, eax
0x1000bffa  test    esi, esi
0x1000bffc  js      short loc_1000C05C
0x1000bffe  mov     edx, [ebp+lpCriticalSection]
0x1000c001  mov     ecx, [ebp+dwProcessId]
0x1000c004  imul    eax, [edx+2Ch], 0Ch
0x1000c008  add     eax, [edx+30h]
0x1000c00b  mov     [eax], ecx
0x1000c00d  mov     ecx, [ebp+var_3C]
0x1000c010  mov     [eax+4], ecx
0x1000c013  mov     ecx, [ebp+var_40]
0x1000c016  mov     [eax+8], ecx
0x1000c019  inc     dword ptr [edx+2Ch]
0x1000c01c  jmp     short loc_1000C05C
0x1000c01e  call    ds:GetLastError
0x1000c024  cmp     eax, 5
0x1000c027  jnz     short loc_1000C030
0x1000c029  mov     esi, 80070490h
0x1000c02e  jmp     short loc_1000C067
0x1000c030  test    eax, eax
0x1000c032  jz      short loc_1000C067
0x1000c034  jg      short loc_1000C03A
0x1000c036  mov     esi, eax
0x1000c038  jmp     short loc_1000C043
0x1000c03a  movzx   esi, ax
0x1000c03d  or      esi, 80070000h
0x1000c043  test    esi, esi
0x1000c045  js      short loc_1000C04C
0x1000c047  mov     esi, 80004005h
0x1000c04c  push    esi
0x1000c04d  push    0D8h
0x1000c052  push    offset aDAWork1SSrcLib_5; "d:\\a\\_work\\1\\s\\src\\libs\\dutil\\r"...
0x1000c057  call    nullsub_1
0x1000c05c  test    ebx, ebx
0x1000c05e  jz      short loc_1000C067
0x1000c060  push    ebx; hObject
0x1000c061  call    ds:CloseHandle
0x1000c067  cmp     [ebp+var_2C], 0
0x1000c06b  jz      short loc_1000C07F
0x1000c06d  push    0; ReturnLength
0x1000c06f  push    0; PreviousState
0x1000c071  push    0; BufferLength
0x1000c073  push    edi; NewState
0x1000c074  push    0; DisableAllPrivileges
0x1000c076  push    [ebp+TokenHandle]; TokenHandle
0x1000c079  call    ds:AdjustTokenPrivileges
0x1000c07f  test    edi, edi
0x1000c081  jz      short loc_1000C089
0x1000c083  push    edi; lpMem
0x1000c084  call    sub_1000AEFF
0x1000c089  cmp     [ebp+TokenHandle], 0
0x1000c08d  jz      short loc_1000C09C
0x1000c08f  push    [ebp+TokenHandle]; hObject
0x1000c092  call    ds:CloseHandle
0x1000c098  and     [ebp+TokenHandle], 0
0x1000c09c  cmp     [ebp+var_30], 0
0x1000c0a0  jz      short loc_1000C0AB
0x1000c0a2  push    [ebp+lpCriticalSection]; lpCriticalSection
0x1000c0a5  call    ds:LeaveCriticalSection
0x1000c0ab  mov     ecx, [ebp+var_4]
0x1000c0ae  mov     eax, esi
0x1000c0b0  pop     edi
0x1000c0b1  pop     esi
0x1000c0b2  xor     ecx, ebp; StackCookie
0x1000c0b4  pop     ebx
0x1000c0b5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000c0ba  leave
0x1000c0bb  retn    8
```
