# PlaceCleanContainerFile(ushort const *)

- ea: `0x180086454`
- end: `0x180086559`
- name: `?PlaceCleanContainerFile@@YAJPEBG@Z`
- size: `261`
- prototype: `__int64 __fastcall(LPCWSTR lpNewFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180086560`

## callees

- `0x18005d488`
- `0x18005d4e8`
- `0x18006c000`
- `0x180085f78`
- `0x180086454`
- `0x180086d30`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x180086505`
- `KERNEL32!CopyFileW` at `0x180086505`
- `KERNEL32!GetSystemDirectoryW` at `0x180086493`
- `KERNEL32!GetSystemDirectoryW` at `0x180086493`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800864b1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800864b1`
- `SHLWAPI!PathFileExistsW` at `0x1800864e0`
- `SHLWAPI!PathFileExistsW` at `0x1800864e0`

## pseudocode

```c
__int64 __fastcall PlaceCleanContainerFile(LPCWSTR lpNewFileName)
{
  const char *v2; // r9
  __int64 v3; // rdx
  HRESULT v4; // eax
  unsigned int LastError; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  int v9[20]; // [rsp+20h] [rbp-278h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  DatVPrepTelemetry::WatchCurrentThread(v9, "DoDatVPrepRSCleanContainer");
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    v3 = 69;
LABEL_10:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v3,
                  (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
                  v2);
    goto LABEL_12;
  }
  v4 = PathCchAppend(Buffer, 0x104u, L"settings.dat");
  LastError = v4;
  if ( v4 >= 0 )
  {
    if ( PathFileExistsW(Buffer) )
    {
      if ( CopyFileW(Buffer, lpNewFileName, 1) )
      {
        LastError = 0;
        goto LABEL_12;
      }
      v3 = 72;
      goto LABEL_10;
    }
    LastError = -2147418113;
    v7 = 71;
    v6 = 2147549183LL;
  }
  else
  {
    v6 = (unsigned int)v4;
    v7 = 70;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\cxhdatvprep.cpp",
    (const char *)v6,
    v9[0]);
LABEL_12:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v9);
  return LastError;
}

```

## disassembly

```asm
0x180086454  mov     [rsp+arg_8], rbx
0x180086459  push    rdi
0x18008645a  sub     rsp, 290h
0x180086461  mov     rax, cs:__security_cookie
0x180086468  xor     rax, rsp
0x18008646b  mov     [rsp+298h+var_18], rax
0x180086473  mov     rdi, rcx
0x180086476  lea     rdx, aDodatvpreprscl; "DoDatVPrepRSCleanContainer"
0x18008647d  lea     rcx, [rsp+298h+var_278]
0x180086482  call    ?WatchCurrentThread@DatVPrepTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; DatVPrepTelemetry::WatchCurrentThread(char const *)
0x180086487  mov     ebx, 104h
0x18008648c  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x180086491  mov     edx, ebx; uSize
0x180086493  call    cs:__imp_GetSystemDirectoryW
0x180086499  test    eax, eax
0x18008649b  jnz     short loc_1800864A2
0x18008649d  lea     edx, [rax+45h]
0x1800864a0  jmp     short loc_180086512
0x1800864a2  lea     r8, aSettingsDat; "settings.dat"
0x1800864a9  mov     rdx, rbx; cchPath
0x1800864ac  lea     rcx, [rsp+298h+Buffer]; pszPath
0x1800864b1  call    cs:__imp_PathCchAppend
0x1800864b7  mov     ebx, eax
0x1800864b9  test    eax, eax
0x1800864bb  jns     short loc_1800864DB
0x1800864bd  mov     r9d, eax; char *
0x1800864c0  mov     edx, 46h ; 'F'; void *
0x1800864c5  mov     rcx, [rsp+298h]; this
0x1800864cd  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800864d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800864d9  jmp     short loc_18008652C
0x1800864db  lea     rcx, [rsp+298h+Buffer]; pszPath
0x1800864e0  call    cs:__imp_PathFileExistsW
0x1800864e6  test    eax, eax
0x1800864e8  jnz     short loc_1800864F7
0x1800864ea  mov     ebx, 8000FFFFh
0x1800864ef  lea     edx, [rax+47h]
0x1800864f2  mov     r9d, ebx
0x1800864f5  jmp     short loc_1800864C5
0x1800864f7  mov     r8d, 1; bFailIfExists
0x1800864fd  lea     rcx, [rsp+298h+Buffer]; lpExistingFileName
0x180086502  mov     rdx, rdi; lpNewFileName
0x180086505  call    cs:__imp_CopyFileW
0x18008650b  test    eax, eax
0x18008650d  jnz     short loc_18008652A
0x18008650f  lea     edx, [rax+48h]; void *
0x180086512  mov     rcx, [rsp+298h]; this
0x18008651a  lea     r8, aPcshellShellAu_10; "pcshell\\shell\\auth\\authux\\controlle"...
0x180086521  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180086526  mov     ebx, eax
0x180086528  jmp     short loc_18008652C
0x18008652a  xor     ebx, ebx
0x18008652c  lea     rcx, [rsp+298h+var_278]; this
0x180086531  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180086536  mov     eax, ebx
0x180086538  mov     rcx, [rsp+298h+var_18]
0x180086540  xor     rcx, rsp; StackCookie
0x180086543  call    __security_check_cookie
0x180086548  mov     rbx, [rsp+298h+arg_8]
0x180086550  add     rsp, 290h
0x180086557  pop     rdi
0x180086558  retn
```
