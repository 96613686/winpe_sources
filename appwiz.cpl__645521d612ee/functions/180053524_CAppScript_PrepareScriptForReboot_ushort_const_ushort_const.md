# CAppScript::PrepareScriptForReboot(ushort const *,ushort const *)

- ea: `0x180053524`
- end: `0x180053821`
- name: `?PrepareScriptForReboot@CAppScript@@AEAAHPEBG0@Z`
- size: `765`
- prototype: `__int64 __fastcall(CAppScript *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180053a84`

## callees

- `0x180007960`
- `0x180053524`
- `0x180053c1c`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005380d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005380d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800536a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800536a8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180053790`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180053790`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800537db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800537db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800537c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800537c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005369f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800536c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800537e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005369f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800536c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800537e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053593`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005363c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053727`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053593`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005363c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053727`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180053687`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180053687`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800535ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800535ea`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800536b8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800536b8`

## string_xrefs

- `0x1800537b3`: `ZZZAppCompatScript`

## pseudocode

```c
_BOOL8 __fastcall CAppScript::PrepareScriptForReboot(
        CAppScript *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r15
  __int64 v4; // rdi
  BOOL v5; // r13d
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  unsigned __int16 *v8; // rax
  WCHAR *v9; // r14
  BOOL v10; // ebx
  HANDLE FileW; // r12
  __int64 v12; // rax
  unsigned __int64 v13; // rsi
  char *v14; // rax
  char *v15; // r15
  __int64 v16; // rsi
  __int64 v17; // rdx
  __int64 v18; // rax
  unsigned __int64 v19; // rsi
  unsigned __int16 *v20; // rax
  BYTE *v21; // rbx
  DWORD NumberOfBytesWritten[2]; // [rsp+50h] [rbp-59h] BYREF
  const unsigned __int16 *v24; // [rsp+58h] [rbp-51h]
  char v25[16]; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 v26[16]; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int16 v27[8]; // [rsp+90h] [rbp-19h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-9h]
  __int64 v29; // [rsp+B0h] [rbp+7h]

  v3 = a3;
  v4 = -1;
  v24 = a3;
  *(_OWORD *)v26 = *(_OWORD *)L"%s\\RunOnce.cmd";
  v5 = 0;
  *(_OWORD *)&v26[7] = *(_OWORD *)L"nce.cmd";
  v6 = -1;
  do
    ++v6;
  while ( *(&Buffer + v6) );
  v7 = v6 + 15;
  v8 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v6 + 15));
  v9 = v8;
  if ( v8 )
  {
    v10 = 0;
    if ( StringCchPrintfW(v8, v7, v26, &Buffer) >= 0 )
    {
      FileW = CreateFileW(v9, 0x40000000u, 0, 0, 1u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        v10 = GetLastError() == 80;
      }
      else
      {
        v12 = -1;
        strcpy(v25, "cd %S\r\n%%1\r\n");
        do
          ++v12;
        while ( *(&Buffer + v12) );
        v13 = v12 + 13;
        v14 = (char *)LocalAlloc(0x40u, v12 + 13);
        v15 = v14;
        if ( v14 )
        {
          if ( (int)StringCchPrintfA(v14, v13, v25, &Buffer) >= 0 )
          {
            v16 = -1;
            do
              ++v16;
            while ( v15[v16] );
            NumberOfBytesWritten[0] = 0;
            if ( WriteFile(FileW, v15, v16, NumberOfBytesWritten, 0) )
            {
              if ( (_DWORD)v16 == NumberOfBytesWritten[0] )
                v10 = 1;
            }
          }
          LocalFree(v15);
        }
        CloseHandle(FileW);
        if ( !v10 )
          DeleteFileW(v9);
        v3 = v24;
      }
    }
    LocalFree(v9);
    if ( v10 )
    {
      v17 = -1;
      *(_OWORD *)v27 = *(_OWORD *)L"\"%s\\RunOnce.cmd\" %s";
      v29 = *(_QWORD *)L" %s";
      v28 = *(_OWORD *)L"nce.cmd\" %s";
      do
        ++v17;
      while ( *(&Buffer + v17) );
      v18 = -1;
      do
        ++v18;
      while ( v3[v18] );
      v19 = v17 + v18 + 20;
      v20 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v19);
      v21 = (BYTE *)v20;
      if ( v20 )
      {
        if ( StringCchPrintfW(v20, v19, v27, &Buffer, v3) >= 0 )
        {
          *(_QWORD *)NumberOfBytesWritten = 0;
          if ( !RegCreateKeyExW(
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\RunOnce",
                  0,
                  0,
                  0,
                  2u,
                  0,
                  (PHKEY)NumberOfBytesWritten,
                  0) )
          {
            do
              ++v4;
            while ( *(_WORD *)&v21[2 * v4] );
            v5 = RegSetValueExW(*(HKEY *)NumberOfBytesWritten, L"ZZZAppCompatScript", 0, 1u, v21, 2 * v4 + 2) == 0;
            RegCloseKey(*(HKEY *)NumberOfBytesWritten);
          }
        }
        LocalFree(v21);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180053524  push    rbp
0x180053526  push    rbx
0x180053527  push    rsi
0x180053528  push    rdi
0x180053529  push    r12
0x18005352b  push    r13
0x18005352d  push    r14
0x18005352f  push    r15
0x180053531  lea     rbp, [rsp-1Fh]
0x180053536  sub     rsp, 0C8h
0x18005353d  mov     rax, cs:__security_cookie
0x180053544  xor     rax, rsp
0x180053547  mov     [rbp+57h+var_48], rax
0x18005354b  movups  xmm0, xmmword ptr cs:aSRunonceCmd; "%s\\RunOnce.cmd"
0x180053552  xor     r12d, r12d
0x180053555  mov     r15, r8
0x180053558  movups  xmm1, xmmword ptr cs:aSRunonceCmd+0Eh; "nce.cmd"
0x18005355f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180053563  mov     [rbp+57h+var_A8], r8
0x180053567  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x18005356b  mov     r13d, r12d
0x18005356e  lea     rcx, Buffer
0x180053575  movups  xmmword ptr [rbp+57h+var_90+0Eh], xmm1
0x180053579  mov     rax, rdi
0x18005357c  inc     rax
0x18005357f  cmp     [rcx+rax*2], r12w
0x180053584  jnz     short loc_18005357C
0x180053586  lea     rsi, [rax+0Fh]
0x18005358a  mov     ecx, 40h ; '@'; uFlags
0x18005358f  lea     rdx, [rsi+rsi]; uBytes
0x180053593  call    cs:__imp_LocalAlloc
0x180053599  mov     r14, rax
0x18005359c  test    rax, rax
0x18005359f  jz      loc_1800537EA
0x1800535a5  lea     r9, Buffer
0x1800535ac  mov     rdx, rsi; unsigned __int64
0x1800535af  lea     r8, [rbp+57h+var_90]; unsigned __int16 *
0x1800535b3  mov     rcx, rax; unsigned __int16 *
0x1800535b6  mov     ebx, r12d
0x1800535b9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800535be  mov     esi, 1
0x1800535c3  test    eax, eax
0x1800535c5  js      loc_1800536C2
0x1800535cb  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x1800535d0  xor     r9d, r9d; lpSecurityAttributes
0x1800535d3  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800535db  xor     r8d, r8d; dwShareMode
0x1800535de  mov     edx, 40000000h; dwDesiredAccess
0x1800535e3  mov     [rsp+100h+dwCreationDisposition], esi; dwCreationDisposition
0x1800535e7  mov     rcx, r14; lpFileName
0x1800535ea  call    cs:__imp_CreateFileW
0x1800535f0  mov     r12, rax
0x1800535f3  cmp     rax, rdi
0x1800535f6  jz      loc_18005380D
0x1800535fc  mov     eax, dword ptr cs:aCdS1+8; "%1\r\n"
0x180053602  lea     rdx, Buffer
0x180053609  movsd   xmm0, qword ptr cs:aCdS1; "cd %S\r\n%%1\r\n"
0x180053611  xor     ecx, ecx
0x180053613  mov     dword ptr [rbp+57h+var_A0+8], eax
0x180053616  mov     al, byte ptr cs:aCdS1+0Ch; ""
0x18005361c  mov     [rbp+57h+var_A0+0Ch], al
0x18005361f  mov     rax, rdi
0x180053622  movsd   qword ptr [rbp+57h+var_A0], xmm0
0x180053627  inc     rax
0x18005362a  cmp     [rdx+rax*2], cx
0x18005362e  jnz     short loc_180053627
0x180053630  lea     rsi, [rax+0Dh]
0x180053634  mov     ecx, 40h ; '@'; uFlags
0x180053639  mov     rdx, rsi; uBytes
0x18005363c  call    cs:__imp_LocalAlloc
0x180053642  mov     r15, rax
0x180053645  test    rax, rax
0x180053648  jz      short loc_1800536A5
0x18005364a  lea     r9, Buffer
0x180053651  mov     rdx, rsi; unsigned __int64
0x180053654  lea     r8, [rbp+57h+var_A0]; char *
0x180053658  mov     rcx, rax; char *
0x18005365b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180053660  xor     ecx, ecx
0x180053662  test    eax, eax
0x180053664  js      short loc_18005369C
0x180053666  mov     rsi, rdi
0x180053669  inc     rsi
0x18005366c  cmp     [r15+rsi], cl
0x180053670  jnz     short loc_180053669
0x180053672  mov     [rbp+57h+NumberOfBytesWritten], ecx
0x180053675  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180053679  mov     qword ptr [rsp+100h+dwCreationDisposition], rcx; lpOverlapped
0x18005367e  mov     r8d, esi; nNumberOfBytesToWrite
0x180053681  mov     rcx, r12; hFile
0x180053684  mov     rdx, r15; lpBuffer
0x180053687  call    cs:__imp_WriteFile
0x18005368d  test    eax, eax
0x18005368f  jz      short loc_18005369C
0x180053691  cmp     esi, [rbp+57h+NumberOfBytesWritten]
0x180053694  mov     eax, 1
0x180053699  cmovz   ebx, eax
0x18005369c  mov     rcx, r15; hMem
0x18005369f  call    cs:__imp_LocalFree
0x1800536a5  mov     rcx, r12; hObject
0x1800536a8  call    cs:__imp_CloseHandle
0x1800536ae  xor     r12d, r12d
0x1800536b1  test    ebx, ebx
0x1800536b3  jnz     short loc_1800536BE
0x1800536b5  mov     rcx, r14; lpFileName
0x1800536b8  call    cs:__imp_DeleteFileW
0x1800536be  mov     r15, [rbp+57h+var_A8]
0x1800536c2  mov     rcx, r14; hMem
0x1800536c5  call    cs:__imp_LocalFree
0x1800536cb  test    ebx, ebx
0x1800536cd  jz      loc_1800537EA
0x1800536d3  movups  xmm0, xmmword ptr cs:aSRunonceCmdS; "\"%s\\RunOnce.cmd\" %s"
0x1800536da  mov     rdx, rdi
0x1800536dd  lea     r14, Buffer
0x1800536e4  movups  xmm1, xmmword ptr cs:aSRunonceCmdS+10h; "nce.cmd\" %s"
0x1800536eb  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x1800536ef  movsd   xmm0, qword ptr cs:aSRunonceCmdS+20h; " %s"
0x1800536f7  movsd   [rbp+57h+var_50], xmm0
0x1800536fc  movups  [rbp+57h+var_60], xmm1
0x180053700  inc     rdx
0x180053703  cmp     [r14+rdx*2], r12w
0x180053708  jnz     short loc_180053700
0x18005370a  mov     rax, rdi
0x18005370d  inc     rax
0x180053710  cmp     [r15+rax*2], r12w
0x180053715  jnz     short loc_18005370D
0x180053717  lea     rsi, [rax+14h]
0x18005371b  mov     ecx, 40h ; '@'; uFlags
0x180053720  add     rsi, rdx
0x180053723  lea     rdx, [rsi+rsi]; uBytes
0x180053727  call    cs:__imp_LocalAlloc
0x18005372d  mov     rbx, rax
0x180053730  test    rax, rax
0x180053733  jz      loc_1800537EA
0x180053739  mov     r9, r14
0x18005373c  mov     qword ptr [rsp+100h+dwCreationDisposition], r15
0x180053741  lea     r8, [rbp+57h+var_70]; unsigned __int16 *
0x180053745  mov     rdx, rsi; unsigned __int64
0x180053748  mov     rcx, rax; unsigned __int16 *
0x18005374b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180053750  test    eax, eax
0x180053752  js      loc_1800537E1
0x180053758  mov     [rsp+100h+lpdwDisposition], r12; lpdwDisposition
0x18005375d  lea     rax, [rbp+57h+NumberOfBytesWritten]
0x180053761  mov     [rsp+100h+phkResult], rax; phkResult
0x180053766  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005376d  mov     [rsp+100h+hTemplateFile], r12; lpSecurityAttributes
0x180053772  xor     r9d, r9d; lpClass
0x180053775  mov     [rsp+100h+dwFlagsAndAttributes], 2; samDesired
0x18005377d  xor     r8d, r8d; Reserved
0x180053780  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180053787  mov     [rsp+100h+dwCreationDisposition], r12d; dwOptions
0x18005378c  mov     qword ptr [rbp+57h+NumberOfBytesWritten], r12
0x180053790  call    cs:__imp_RegCreateKeyExW
0x180053796  test    eax, eax
0x180053798  jnz     short loc_1800537E1
0x18005379a  inc     rdi
0x18005379d  cmp     [rbx+rdi*2], r12w
0x1800537a2  jnz     short loc_18005379A
0x1800537a4  mov     rcx, qword ptr [rbp+57h+NumberOfBytesWritten]; hKey
0x1800537a8  lea     eax, ds:2[rdi*2]
0x1800537af  mov     [rsp+100h+dwFlagsAndAttributes], eax; cbData
0x1800537b3  lea     rdx, aZzzappcompatsc; "ZZZAppCompatScript"
0x1800537ba  mov     r9d, 1; dwType
0x1800537c0  mov     qword ptr [rsp+100h+dwCreationDisposition], rbx; lpData
0x1800537c5  xor     r8d, r8d; Reserved
0x1800537c8  call    cs:__imp_RegSetValueExW
0x1800537ce  mov     rcx, qword ptr [rbp+57h+NumberOfBytesWritten]; hKey
0x1800537d2  mov     r13d, r12d
0x1800537d5  test    eax, eax
0x1800537d7  setz    r13b
0x1800537db  call    cs:__imp_RegCloseKey
0x1800537e1  mov     rcx, rbx; hMem
0x1800537e4  call    cs:__imp_LocalFree
0x1800537ea  mov     eax, r13d
0x1800537ed  mov     rcx, [rbp+57h+var_48]
0x1800537f1  xor     rcx, rsp; StackCookie
0x1800537f4  call    __security_check_cookie
0x1800537f9  add     rsp, 0C8h
0x180053800  pop     r15
0x180053802  pop     r14
0x180053804  pop     r13
0x180053806  pop     r12
0x180053808  pop     rdi
0x180053809  pop     rsi
0x18005380a  pop     rbx
0x18005380b  pop     rbp
0x18005380c  retn
0x18005380d  call    cs:__imp_GetLastError
0x180053813  cmp     eax, 50h ; 'P'
0x180053816  cmovz   ebx, esi
0x180053819  xor     r12d, r12d
0x18005381c  jmp     loc_1800536C2
```
