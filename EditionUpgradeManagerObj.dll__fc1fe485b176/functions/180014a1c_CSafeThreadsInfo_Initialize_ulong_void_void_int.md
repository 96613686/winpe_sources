# CSafeThreadsInfo::Initialize(ulong (*)(void *),void *,int)

- ea: `0x180014a1c`
- end: `0x180014b75`
- name: `?Initialize@CSafeThreadsInfo@@AEAAJP6AKPEAX@Z0H@Z`
- size: `345`
- prototype: `__int64 __fastcall(CSafeThreadsInfo *this, unsigned int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800166e8`

## callees

- `0x180001ac0`
- `0x1800090dc`
- `0x180009480`
- `0x180014a1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014b1f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014b1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180014aba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180014aba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014b0d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b2e`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180014a71`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180014a71`

## pseudocode

```c
__int64 __fastcall CSafeThreadsInfo::Initialize(CSafeThreadsInfo *this, unsigned int (*a2)(void *), void *a3)
{
  signed int LastError; // eax
  unsigned int v5; // edi
  unsigned int v6; // ebx
  __int64 v7; // rcx
  DWORD ModuleFileNameW; // eax
  signed int v9; // eax
  HMODULE Library; // rax
  HMODULE v11; // rcx
  HMODULE v12; // r14
  signed int v13; // eax
  struct _MEMORY_BASIC_INFORMATION Buffer; // [rsp+20h] [rbp-278h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-248h] BYREF

  *(_OWORD *)&Buffer.BaseAddress = 0;
  *((_QWORD *)this + 2) = a3;
  *(_OWORD *)&Buffer.AllocationProtect = 0;
  *((_QWORD *)this + 1) = LaunchProgressUI;
  *(_OWORD *)&Buffer.State = 0;
  *((_DWORD *)this + 8) = 0;
  if ( !VirtualQuery(LaunchProgressUI, &Buffer, 0x30u) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    v6 = v5;
    v7 = v5;
    goto LABEL_7;
  }
  ModuleFileNameW = GetModuleFileNameW((HMODULE)Buffer.AllocationBase, Filename, 0x104u);
  Filename[259] = 0;
  if ( !ModuleFileNameW )
  {
    v9 = GetLastError();
    v6 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( (v6 & 0x80000000) != 0 )
      goto LABEL_17;
LABEL_19:
    Library = LoadLibraryExW(Filename, 0, 0);
    v11 = (HMODULE)*((_QWORD *)this + 3);
    v12 = Library;
    if ( v11 )
      FreeLibrary(v11);
    if ( v12 )
    {
      *((_QWORD *)this + 3) = v12;
      goto LABEL_27;
    }
    *((_QWORD *)this + 3) = 0;
    v13 = GetLastError();
    v6 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v6 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    goto LABEL_17;
  }
  if ( ModuleFileNameW < 0x104 )
  {
    v6 = 0;
    goto LABEL_19;
  }
  v6 = -2147024774;
LABEL_17:
  v7 = v6;
LABEL_7:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_27:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  return v6;
}

```

## disassembly

```asm
0x180014a1c  push    rbx
0x180014a1e  push    rbp
0x180014a1f  push    rdi
0x180014a20  push    r14
0x180014a22  sub     rsp, 278h
0x180014a29  mov     rax, cs:__security_cookie
0x180014a30  xor     rax, rsp
0x180014a33  mov     [rsp+298h+var_38], rax
0x180014a3b  mov     rbp, rcx
0x180014a3e  lea     rdx, [rsp+298h+Buffer]; lpBuffer
0x180014a43  xorps   xmm0, xmm0
0x180014a46  lea     rcx, ?LaunchProgressUI@@YAKPEAX@Z; lpAddress
0x180014a4d  movups  xmmword ptr [rsp+298h+Buffer.BaseAddress], xmm0
0x180014a52  mov     [rbp+10h], r8
0x180014a56  mov     r8d, 30h ; '0'; dwLength
0x180014a5c  movups  xmmword ptr [rsp+298h+Buffer.AllocationProtect], xmm0
0x180014a61  mov     [rbp+8], rcx
0x180014a65  movups  xmmword ptr [rsp+298h+Buffer.State], xmm0
0x180014a6a  mov     dword ptr [rbp+20h], 0
0x180014a71  call    cs:__imp_VirtualQuery
0x180014a77  test    rax, rax
0x180014a7a  jnz     short loc_180014AA8
0x180014a7c  call    cs:__imp_GetLastError
0x180014a82  mov     edi, eax
0x180014a84  test    eax, eax
0x180014a86  jnz     short loc_180014A8F
0x180014a88  mov     edi, 80004005h
0x180014a8d  jmp     short loc_180014A9A
0x180014a8f  jle     short loc_180014A9A
0x180014a91  movzx   edi, ax
0x180014a94  or      edi, 80070000h
0x180014a9a  mov     ebx, edi
0x180014a9c  mov     ecx, edi
0x180014a9e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180014aa3  jmp     loc_180014B4F
0x180014aa8  mov     rcx, [rsp+298h+Buffer.AllocationBase]; hModule
0x180014aad  lea     rdx, [rsp+298h+Filename]; lpFilename
0x180014ab2  mov     ebx, 104h
0x180014ab7  mov     r8d, ebx; nSize
0x180014aba  call    cs:__imp_GetModuleFileNameW
0x180014ac0  xor     ecx, ecx
0x180014ac2  mov     edi, 80004005h
0x180014ac7  mov     [rsp+298h+var_42], cx
0x180014acf  test    eax, eax
0x180014ad1  jnz     short loc_180014AF4
0x180014ad3  call    cs:__imp_GetLastError
0x180014ad9  mov     ebx, eax
0x180014adb  test    eax, eax
0x180014add  jnz     short loc_180014AE3
0x180014adf  mov     ebx, edi
0x180014ae1  jmp     short loc_180014AEE
0x180014ae3  jle     short loc_180014AEE
0x180014ae5  movzx   ebx, ax
0x180014ae8  or      ebx, 80070000h
0x180014aee  test    ebx, ebx
0x180014af0  jns     short loc_180014B03
0x180014af2  jmp     short loc_180014AFD
0x180014af4  cmp     eax, ebx
0x180014af6  jb      short loc_180014B01
0x180014af8  mov     ebx, 8007007Ah
0x180014afd  mov     ecx, ebx
0x180014aff  jmp     short loc_180014A9E
0x180014b01  xor     ebx, ebx
0x180014b03  xor     r8d, r8d; dwFlags
0x180014b06  lea     rcx, [rsp+298h+Filename]; lpLibFileName
0x180014b0b  xor     edx, edx; hFile
0x180014b0d  call    cs:__imp_LoadLibraryExW
0x180014b13  mov     rcx, [rbp+18h]; hLibModule
0x180014b17  mov     r14, rax
0x180014b1a  test    rcx, rcx
0x180014b1d  jz      short loc_180014B25
0x180014b1f  call    cs:__imp_FreeLibrary
0x180014b25  test    r14, r14
0x180014b28  jnz     short loc_180014B4B
0x180014b2a  mov     [rbp+18h], r14
0x180014b2e  call    cs:__imp_GetLastError
0x180014b34  mov     ebx, eax
0x180014b36  test    eax, eax
0x180014b38  jnz     short loc_180014B3E
0x180014b3a  mov     ebx, edi
0x180014b3c  jmp     short loc_180014AFD
0x180014b3e  jle     short loc_180014AFD
0x180014b40  movzx   ebx, ax
0x180014b43  or      ebx, 80070000h
0x180014b49  jmp     short loc_180014AFD
0x180014b4b  mov     [rbp+18h], r14
0x180014b4f  mov     ecx, ebx
0x180014b51  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180014b56  mov     eax, ebx
0x180014b58  mov     rcx, [rsp+298h+var_38]
0x180014b60  xor     rcx, rsp; StackCookie
0x180014b63  call    __security_check_cookie
0x180014b68  add     rsp, 278h
0x180014b6f  pop     r14
0x180014b71  pop     rdi
0x180014b72  pop     rbp
0x180014b73  pop     rbx
0x180014b74  retn
```
