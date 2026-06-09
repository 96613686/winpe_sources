# GetExeNameAndAppId(ushort * *,ushort * *)

- ea: `0x180012154`
- end: `0x180012383`
- name: `?GetExeNameAndAppId@@YAJPEAPEAG0@Z`
- size: `559`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001238c`

## callees

- `0x18000e574`
- `0x180012084`
- `0x180012154`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800122f8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800122f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800121b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800121b4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180012208`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180012208`
- `msvcrt!strchr` at `0x18001223a`
- `msvcrt!strchr` at `0x18001223a`
- `msvcrt!_wcsicmp` at `0x18001221e`
- `msvcrt!_wcsicmp` at `0x18001221e`
- `msvcrt!_stricmp` at `0x180012344`
- `msvcrt!_stricmp` at `0x180012344`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x18001222c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x18001222c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800121cb`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800121cb`

## string_xrefs

- `0x180012217`: `dllhost.exe`
- `0x18001225f`: `/ProcessID`

## pseudocode

```c
__int64 __fastcall GetExeNameAndAppId(unsigned __int16 **a1, unsigned __int16 **a2)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  const char *CommandLineA; // rax
  char *v8; // rax
  int v9; // r8d
  int v10; // r9d
  char *v11; // rcx
  CHAR v12; // al
  CHAR *v13; // rcx
  CHAR *v14; // rbx
  CHAR *v15; // rax
  __int64 v16; // rcx
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR FilePart; // [rsp+38h] [rbp-C8h] BYREF
  char *v20; // [rsp+40h] [rbp-C0h] BYREF
  char String2[24]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR WideCharStr[48]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR MultiByteStr[272]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ExeName[264]; // [rsp+1D0h] [rbp+D0h] BYREF
  WCHAR Buffer[264]; // [rsp+3E0h] [rbp+2E0h] BYREF

  FilePart = 0;
  dwSize = 261;
  if ( a1 && a2 )
  {
    *a1 = 0;
    *a2 = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize)
      || !GetFullPathNameW(ExeName, 0x105u, Buffer, &FilePart) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return v6;
    }
    if ( !_wcsicmp(L"dllhost.exe", FilePart) )
    {
      CommandLineA = GetCommandLineA();
      v8 = strchr(CommandLineA, 32);
      v11 = v8 + 1;
      if ( !v8 )
        v11 = 0;
      if ( v11 )
      {
        strcpy(String2, "/ProcessID");
        v20 = MultiByteStr;
        if ( (int)GetCommandLineArgumentsForTraceFileName(v11, &v20, v9, v10) >= 1 )
        {
          v12 = MultiByteStr[0];
          if ( MultiByteStr[0] )
          {
            v13 = MultiByteStr;
            while ( 1 )
            {
              v14 = v13 + 1;
              if ( v12 == 58 )
                break;
              v12 = *v14;
              ++v13;
              if ( !*v14 )
                goto LABEL_16;
            }
            *v13 = 0;
            v12 = *v14;
          }
          else
          {
            v14 = MultiByteStr;
          }
          if ( !v12 || _stricmp(MultiByteStr, String2) )
          {
LABEL_16:
            v14 = MultiByteStr;
LABEL_17:
            v15 = v14;
            v16 = 40;
            do
            {
              if ( !*v15 )
                break;
              ++v15;
              --v16;
            }
            while ( v16 );
            if ( v16 )
            {
              if ( MultiByteToWideChar(0, 0, v14, v16 != 0 ? 40 - v16 + 1 : 1, WideCharStr, 41) )
              {
                v6 = 0;
                if ( (int)DuplicateString(WideCharStr, a2) < 0 )
                  return v6;
              }
            }
            return (unsigned int)DuplicateString(FilePart, a1);
          }
          if ( v14 )
            goto LABEL_17;
        }
      }
    }
    return (unsigned int)DuplicateString(FilePart, a1);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180012154  mov     [rsp-8+arg_10], rbx
0x180012159  push    rbp
0x18001215a  push    rsi
0x18001215b  push    rdi
0x18001215c  lea     rbp, [rsp-500h]
0x180012164  sub     rsp, 600h
0x18001216b  mov     rax, cs:__security_cookie
0x180012172  xor     rax, rsp
0x180012175  mov     [rbp+510h+var_20], rax
0x18001217c  mov     [rsp+610h+FilePart], 0
0x180012185  mov     ebx, 105h
0x18001218a  mov     [rsp+610h+dwSize], ebx
0x18001218e  mov     rdi, rdx
0x180012191  mov     rsi, rcx
0x180012194  test    rcx, rcx
0x180012197  jz      loc_18001235C
0x18001219d  test    rdx, rdx
0x1800121a0  jz      loc_18001235C
0x1800121a6  mov     qword ptr [rcx], 0
0x1800121ad  mov     qword ptr [rdx], 0
0x1800121b4  call    cs:__imp_GetCurrentProcess
0x1800121ba  lea     r9, [rsp+610h+dwSize]; lpdwSize
0x1800121bf  xor     edx, edx; dwFlags
0x1800121c1  mov     rcx, rax; hProcess
0x1800121c4  lea     r8, [rbp+510h+ExeName]; lpExeName
0x1800121cb  call    cs:__imp_QueryFullProcessImageNameW
0x1800121d1  test    eax, eax
0x1800121d3  jnz     short loc_1800121F3
0x1800121d5  call    cs:__imp_GetLastError
0x1800121db  mov     ebx, eax
0x1800121dd  test    eax, eax
0x1800121df  jle     loc_180012324
0x1800121e5  movzx   ebx, ax
0x1800121e8  or      ebx, 80070000h
0x1800121ee  jmp     loc_180012324
0x1800121f3  lea     r9, [rsp+610h+FilePart]; lpFilePart
0x1800121f8  mov     edx, ebx; nBufferLength
0x1800121fa  lea     r8, [rbp+510h+Buffer]; lpBuffer
0x180012201  lea     rcx, [rbp+510h+ExeName]; lpFileName
0x180012208  call    cs:__imp_GetFullPathNameW
0x18001220e  test    eax, eax
0x180012210  jz      short loc_1800121D5
0x180012212  mov     rdx, [rsp+610h+FilePart]; String2
0x180012217  lea     rcx, aDllhostExe; "dllhost.exe"
0x18001221e  call    cs:__imp__wcsicmp
0x180012224  test    eax, eax
0x180012226  jnz     loc_180012315
0x18001222c  call    cs:__imp_GetCommandLineA
0x180012232  mov     rcx, rax; Str
0x180012235  mov     edx, 20h ; ' '; Val
0x18001223a  call    cs:__imp_strchr
0x180012240  test    rax, rax
0x180012243  lea     rcx, [rax+1]
0x180012247  cmovz   rcx, rax; char *
0x18001224b  test    rcx, rcx
0x18001224e  jz      loc_180012315
0x180012254  mov     eax, dword ptr cs:aProcessid+7; "sID"
0x18001225a  lea     rdx, [rsp+610h+var_5D0]; char **
0x18001225f  movsd   xmm0, qword ptr cs:aProcessid; "/ProcessID"
0x180012267  movsd   qword ptr [rsp+610h+String2], xmm0
0x18001226d  mov     dword ptr [rsp+610h+String2+7], eax
0x180012271  lea     rax, [rbp+510h+MultiByteStr]
0x180012275  mov     [rsp+610h+var_5D0], rax
0x18001227a  call    ?GetCommandLineArgumentsForTraceFileName@@YAHPEADQEAPEADHH@Z; GetCommandLineArgumentsForTraceFileName(char *,char * * const,int,int)
0x18001227f  cmp     eax, 1
0x180012282  jl      loc_180012315
0x180012288  mov     al, [rbp+510h+MultiByteStr]
0x18001228b  test    al, al
0x18001228d  jz      loc_18001232F
0x180012293  lea     rcx, [rbp+510h+MultiByteStr]
0x180012297  lea     rbx, [rcx+1]
0x18001229b  cmp     al, 3Ah ; ':'
0x18001229d  jz      loc_180012328
0x1800122a3  mov     al, [rbx]
0x1800122a5  mov     rcx, rbx
0x1800122a8  test    al, al
0x1800122aa  jnz     short loc_180012297
0x1800122ac  lea     rbx, [rbp+510h+MultiByteStr]
0x1800122b0  mov     edx, 28h ; '('
0x1800122b5  mov     rax, rbx
0x1800122b8  mov     ecx, edx
0x1800122ba  cmp     byte ptr [rax], 0
0x1800122bd  jz      short loc_1800122C8
0x1800122bf  inc     rax
0x1800122c2  sub     rcx, 1
0x1800122c6  jnz     short loc_1800122BA
0x1800122c8  sub     rdx, rcx
0x1800122cb  mov     rax, rcx
0x1800122ce  neg     rax
0x1800122d1  sbb     r9, r9
0x1800122d4  and     r9, rdx
0x1800122d7  test    rcx, rcx
0x1800122da  jz      short loc_180012315
0x1800122dc  lea     rax, [rsp+610h+WideCharStr]
0x1800122e1  mov     [rsp+610h+cchWideChar], 29h ; ')'; cchWideChar
0x1800122e9  inc     r9d; cbMultiByte
0x1800122ec  mov     [rsp+610h+lpWideCharStr], rax; lpWideCharStr
0x1800122f1  mov     r8, rbx; lpMultiByteStr
0x1800122f4  xor     edx, edx; dwFlags
0x1800122f6  xor     ecx, ecx; CodePage
0x1800122f8  call    cs:__imp_MultiByteToWideChar
0x1800122fe  test    eax, eax
0x180012300  jz      short loc_180012315
0x180012302  mov     rdx, rdi; unsigned __int16 **
0x180012305  lea     rcx, [rsp+610h+WideCharStr]; unsigned __int16 *
0x18001230a  xor     ebx, ebx
0x18001230c  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180012311  test    eax, eax
0x180012313  js      short loc_180012324
0x180012315  mov     rcx, [rsp+610h+FilePart]; unsigned __int16 *
0x18001231a  mov     rdx, rsi; unsigned __int16 **
0x18001231d  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180012322  mov     ebx, eax
0x180012324  mov     eax, ebx
0x180012326  jmp     short loc_180012361
0x180012328  mov     byte ptr [rcx], 0
0x18001232b  mov     al, [rbx]
0x18001232d  jmp     short loc_180012333
0x18001232f  lea     rbx, [rbp+510h+MultiByteStr]
0x180012333  test    al, al
0x180012335  jz      loc_1800122AC
0x18001233b  lea     rdx, [rsp+610h+String2]; String2
0x180012340  lea     rcx, [rbp+510h+MultiByteStr]; String1
0x180012344  call    cs:__imp__stricmp
0x18001234a  test    eax, eax
0x18001234c  jnz     loc_1800122AC
0x180012352  test    rbx, rbx
0x180012355  jz      short loc_180012315
0x180012357  jmp     loc_1800122B0
0x18001235c  mov     eax, 80070057h
0x180012361  mov     rcx, [rbp+510h+var_20]
0x180012368  xor     rcx, rsp; StackCookie
0x18001236b  call    __security_check_cookie
0x180012370  mov     rbx, [rsp+610h+arg_10]
0x180012378  add     rsp, 600h
0x18001237f  pop     rdi
0x180012380  pop     rsi
0x180012381  pop     rbp
0x180012382  retn
```
