# DigestStorage(HINSTANCE__ *,HINSTANCE__ *,IStorage &,unsigned __int64,char const *,hashTypeEnum,ulong *)

- ea: `0x180001be0`
- end: `0x180001f1a`
- name: `?DigestStorage@@YAPEAEPEAUHINSTANCE__@@0AEAUIStorage@@_KPEBDW4hashTypeEnum@@PEAK@Z`
- size: `826`
- prototype: `void *__fastcall(HINSTANCE, HMODULE, struct IStorage *, __int64, __int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800011c0`

## callees

- `0x180001be0`
- `0x180003370`
- `0x180003a70`
- `0x18000d2da`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180001c35`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180001caf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180001ccb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180001ce7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180001c35`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180001caf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180001ccb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180001ce7`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180001d7c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180001dbb`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180001e41`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180001e52`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180001d7c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180001dbb`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180001e41`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180001e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001d84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001d84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001e75`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180001dfb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180001dfb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180001efc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180001efc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180001bff`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180001bff`

## string_xrefs

- `0x180001bf8`: `crypt32.dll`
- `0x180001c93`: `CryptCreateHash`

## pseudocode

```c
void *__fastcall DigestStorage(
        HINSTANCE a1,
        HMODULE a2,
        struct IStorage *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _DWORD *a7)
{
  HMODULE LibraryW; // rax
  HMODULE v10; // rsi
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  unsigned int v13; // ebx
  const wchar_t *v14; // rbx
  DWORD v15; // r13d
  FARPROC v16; // rbp
  FARPROC v17; // r15
  FARPROC v18; // r12
  int v19; // eax
  DWORD v20; // ebx
  DWORD v21; // ecx
  void *v23; // rbx
  unsigned __int64 v24; // rcx
  HLOCAL v25; // rax
  DWORD LastError; // ecx
  unsigned __int64 v27; // [rsp+30h] [rbp-48h] BYREF

  LibraryW = LoadLibraryW(L"crypt32.dll");
  v10 = LibraryW;
  if ( !LibraryW || !a1 || !a2 )
    return 0;
  ProcAddress = GetProcAddress(LibraryW, "CryptFindOIDInfo");
  if ( !ProcAddress )
  {
    LastError = GetLastError();
LABEL_33:
    SetLastError(LastError);
    goto LABEL_34;
  }
  v12 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD))ProcAddress)(1, a5, 0);
  if ( !v12 )
  {
LABEL_41:
    LastError = -2146893816;
    goto LABEL_33;
  }
  v13 = *(_DWORD *)(v12 + 28);
  if ( v13 != -1 )
    goto LABEL_35;
  v14 = *(const wchar_t **)(v12 + 48);
  if ( wcscmp_0(v14, L"SHA256") )
  {
    if ( !wcscmp_0(v14, L"SHA512") )
    {
      v13 = 32782;
      goto LABEL_9;
    }
    if ( !wcscmp_0(v14, L"SHA384") )
    {
      v13 = 32781;
LABEL_35:
      if ( v13 )
        goto LABEL_9;
LABEL_34:
      SetLastError(0x80090008);
      return 0;
    }
    goto LABEL_41;
  }
  v13 = 32780;
LABEL_9:
  v15 = 0;
  v16 = GetProcAddress(a2, "CryptCreateHash");
  if ( !v16 )
    v15 = GetLastError();
  v17 = GetProcAddress(a2, "CryptGetHashParam");
  if ( !v17 )
    v15 = GetLastError();
  v18 = GetProcAddress(a2, "CryptDestroyHash");
  if ( !v18 )
    v15 = GetLastError();
  if ( !v16 || !v17 || !v18 )
  {
    FreeLibrary(v10);
    v21 = v15;
    goto LABEL_23;
  }
  v27 = 0;
  if ( !((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, unsigned __int64 *))v16)(a4, v13, 0, 0, &v27)
    || (a6 != 1
      ? (v19 = DigestStorageContentHelper(a1, a2, a3, 0, v27))
      : (v19 = DigestStorageMetadataHelper(a1, a2, a3, 0, v27)),
        !v19) )
  {
    v20 = GetLastError();
    FreeLibrary(v10);
    v21 = v20;
LABEL_23:
    SetLastError(v21);
    return 0;
  }
  v23 = 0;
  v24 = v27;
  *a7 = 0;
  ((void (__fastcall *)(unsigned __int64, __int64, _QWORD, _DWORD *, _DWORD))v17)(v24, 2, 0, a7, 0);
  if ( *a7 )
  {
    v25 = LocalAlloc(0x40u, (unsigned int)*a7);
    v23 = v25;
    if ( !v25 )
    {
      FreeLibrary(v10);
      v21 = 8;
      goto LABEL_23;
    }
    if ( !((unsigned int (__fastcall *)(unsigned __int64, __int64, HLOCAL, _DWORD *, _DWORD))v17)(v27, 2, v25, a7, 0) )
    {
      LocalFree(v23);
      v23 = 0;
    }
  }
  ((void (__fastcall *)(unsigned __int64))v18)(v27);
  FreeLibrary(v10);
  return v23;
}

```

## disassembly

```asm
0x180001be0  mov     [rsp+arg_18], r9
0x180001be5  mov     [rsp+arg_10], r8
0x180001bea  push    rsi
0x180001beb  push    rdi
0x180001bec  push    r14
0x180001bee  sub     rsp, 60h
0x180001bf2  mov     r14, rcx
0x180001bf5  mov     rdi, rdx
0x180001bf8  lea     rcx, aCrypt32Dll; "crypt32.dll"
0x180001bff  call    cs:__imp_LoadLibraryW
0x180001c05  mov     rsi, rax
0x180001c08  test    rax, rax
0x180001c0b  jz      loc_180001F13
0x180001c11  test    r14, r14
0x180001c14  jz      loc_180001F13
0x180001c1a  test    rdi, rdi
0x180001c1d  jz      loc_180001F13
0x180001c23  lea     rdx, aCryptfindoidin; "CryptFindOIDInfo"
0x180001c2a  mov     [rsp+78h+arg_0], rbx
0x180001c32  mov     rcx, rax; hModule
0x180001c35  call    cs:__imp_GetProcAddress
0x180001c3b  test    rax, rax
0x180001c3e  jz      loc_180001E62
0x180001c44  mov     rdx, [rsp+78h+arg_20]
0x180001c4c  xor     r8d, r8d
0x180001c4f  mov     ecx, 1
0x180001c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c59  test    rax, rax
0x180001c5c  jz      loc_180001F09
0x180001c62  mov     ebx, [rax+1Ch]
0x180001c65  cmp     ebx, 0FFFFFFFFh
0x180001c68  jnz     loc_180001E8E
0x180001c6e  mov     rbx, [rax+30h]
0x180001c72  lea     rdx, aSha256; "SHA256"
0x180001c79  mov     rcx, rbx; String1
0x180001c7c  call    wcscmp_0
0x180001c81  test    eax, eax
0x180001c83  jnz     loc_180001E98
0x180001c89  mov     ebx, 800Ch
0x180001c8e  mov     [rsp+78h+var_20], rbp
0x180001c93  lea     rdx, aCryptcreatehas; "CryptCreateHash"
0x180001c9a  mov     [rsp+78h+var_28], r12
0x180001c9f  mov     rcx, rdi; hModule
0x180001ca2  mov     [rsp+78h+var_30], r13
0x180001ca7  xor     r13d, r13d
0x180001caa  mov     [rsp+78h+var_38], r15
0x180001caf  call    cs:__imp_GetProcAddress
0x180001cb5  mov     rbp, rax
0x180001cb8  test    rax, rax
0x180001cbb  jz      loc_180001ECF
0x180001cc1  lea     rdx, aCryptgethashpa; "CryptGetHashParam"
0x180001cc8  mov     rcx, rdi; hModule
0x180001ccb  call    cs:__imp_GetProcAddress
0x180001cd1  mov     r15, rax
0x180001cd4  test    rax, rax
0x180001cd7  jz      loc_180001EDD
0x180001cdd  lea     rdx, aCryptdestroyha; "CryptDestroyHash"
0x180001ce4  mov     rcx, rdi; hModule
0x180001ce7  call    cs:__imp_GetProcAddress
0x180001ced  mov     r12, rax
0x180001cf0  test    rax, rax
0x180001cf3  jz      loc_180001EEB
0x180001cf9  test    rbp, rbp
0x180001cfc  jz      loc_180001DB8
0x180001d02  test    r15, r15
0x180001d05  jz      loc_180001DB8
0x180001d0b  test    r12, r12
0x180001d0e  jz      loc_180001DB8
0x180001d14  mov     rcx, [rsp+78h+arg_18]
0x180001d1c  lea     rax, [rsp+78h+var_48]
0x180001d21  mov     [rsp+78h+var_58], rax
0x180001d26  xor     r9d, r9d
0x180001d29  mov     rax, rbp
0x180001d2c  mov     [rsp+78h+var_48], 0
0x180001d35  xor     r8d, r8d
0x180001d38  mov     edx, ebx
0x180001d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d3f  test    eax, eax
0x180001d41  jz      short loc_180001D71
0x180001d43  mov     rax, [rsp+78h+var_48]
0x180001d48  xor     r9d, r9d; bool
0x180001d4b  cmp     [rsp+78h+arg_28], 1
0x180001d53  mov     rdx, rdi; HINSTANCE
0x180001d56  mov     r8, [rsp+78h+arg_10]; struct IStorage *
0x180001d5e  mov     rcx, r14; HINSTANCE
0x180001d61  mov     [rsp+78h+var_58], rax; unsigned __int64
0x180001d66  jnz     short loc_180001DB1
0x180001d68  call    ?DigestStorageMetadataHelper@@YAHPEAUHINSTANCE__@@0AEAUIStorage@@_N_K@Z; DigestStorageMetadataHelper(HINSTANCE__ *,HINSTANCE__ *,IStorage &,bool,unsigned __int64)
0x180001d6d  test    eax, eax
0x180001d6f  jnz     short loc_180001DC6
0x180001d71  call    cs:__imp_GetLastError
0x180001d77  mov     rcx, rsi; hLibModule
0x180001d7a  mov     ebx, eax
0x180001d7c  call    cs:__imp_FreeLibrary
0x180001d82  mov     ecx, ebx; dwErrCode
0x180001d84  call    cs:__imp_SetLastError
0x180001d8a  xor     eax, eax
0x180001d8c  mov     r13, [rsp+78h+var_30]
0x180001d91  mov     r12, [rsp+78h+var_28]
0x180001d96  mov     rbp, [rsp+78h+var_20]
0x180001d9b  mov     r15, [rsp+78h+var_38]
0x180001da0  mov     rbx, [rsp+78h+arg_0]
0x180001da8  add     rsp, 60h
0x180001dac  pop     r14
0x180001dae  pop     rdi
0x180001daf  pop     rsi
0x180001db0  retn
0x180001db1  call    ?DigestStorageContentHelper@@YAHPEAUHINSTANCE__@@0AEAUIStorage@@_N_K@Z; DigestStorageContentHelper(HINSTANCE__ *,HINSTANCE__ *,IStorage &,bool,unsigned __int64)
0x180001db6  jmp     short loc_180001D6D
0x180001db8  mov     rcx, rsi; hLibModule
0x180001dbb  call    cs:__imp_FreeLibrary
0x180001dc1  mov     ecx, r13d
0x180001dc4  jmp     short loc_180001D84
0x180001dc6  mov     rdi, [rsp+78h+arg_30]
0x180001dce  xor     ebx, ebx
0x180001dd0  mov     rcx, [rsp+78h+var_48]
0x180001dd5  mov     r9, rdi
0x180001dd8  xor     r8d, r8d
0x180001ddb  mov     dword ptr [rsp+78h+var_58], ebx
0x180001ddf  mov     edx, 2
0x180001de4  mov     rax, r15
0x180001de7  mov     [rdi], ebx
0x180001de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dee  mov     eax, [rdi]
0x180001df0  test    eax, eax
0x180001df2  jz      short loc_180001E31
0x180001df4  mov     edx, eax; uBytes
0x180001df6  mov     ecx, 40h ; '@'; uFlags
0x180001dfb  call    cs:__imp_LocalAlloc
0x180001e01  mov     rbx, rax
0x180001e04  test    rax, rax
0x180001e07  jz      short loc_180001E4F
0x180001e09  mov     rcx, [rsp+78h+var_48]
0x180001e0e  mov     r8, rax
0x180001e11  mov     rax, r15
0x180001e14  mov     dword ptr [rsp+78h+var_58], 0
0x180001e1c  mov     r9, rdi
0x180001e1f  mov     edx, 2
0x180001e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e29  test    eax, eax
0x180001e2b  jz      loc_180001EF9
0x180001e31  mov     rcx, [rsp+78h+var_48]
0x180001e36  mov     rax, r12
0x180001e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e3e  mov     rcx, rsi; hLibModule
0x180001e41  call    cs:__imp_FreeLibrary
0x180001e47  mov     rax, rbx
0x180001e4a  jmp     loc_180001D8C
0x180001e4f  mov     rcx, rsi; hLibModule
0x180001e52  call    cs:__imp_FreeLibrary
0x180001e58  mov     ecx, 8
0x180001e5d  jmp     loc_180001D84
0x180001e62  call    cs:__imp_GetLastError
0x180001e68  mov     ecx, eax; dwErrCode
0x180001e6a  call    cs:__imp_SetLastError
0x180001e70  mov     ecx, 80090008h; dwErrCode
0x180001e75  call    cs:__imp_SetLastError
0x180001e7b  mov     rbx, [rsp+78h+arg_0]
0x180001e83  xor     eax, eax
0x180001e85  add     rsp, 60h
0x180001e89  pop     r14
0x180001e8b  pop     rdi
0x180001e8c  pop     rsi
0x180001e8d  retn
0x180001e8e  test    ebx, ebx
0x180001e90  jnz     loc_180001C8E
0x180001e96  jmp     short loc_180001E70
0x180001e98  lea     rdx, aSha512; "SHA512"
0x180001e9f  mov     rcx, rbx; String1
0x180001ea2  call    wcscmp_0
0x180001ea7  test    eax, eax
0x180001ea9  jnz     short loc_180001EB5
0x180001eab  mov     ebx, 800Eh
0x180001eb0  jmp     loc_180001C8E
0x180001eb5  lea     rdx, aSha384; "SHA384"
0x180001ebc  mov     rcx, rbx; String1
0x180001ebf  call    wcscmp_0
0x180001ec4  test    eax, eax
0x180001ec6  jnz     short loc_180001F09
0x180001ec8  mov     ebx, 800Dh
0x180001ecd  jmp     short loc_180001E8E
0x180001ecf  call    cs:__imp_GetLastError
0x180001ed5  mov     r13d, eax
0x180001ed8  jmp     loc_180001CC1
0x180001edd  call    cs:__imp_GetLastError
0x180001ee3  mov     r13d, eax
0x180001ee6  jmp     loc_180001CDD
0x180001eeb  call    cs:__imp_GetLastError
0x180001ef1  mov     r13d, eax
0x180001ef4  jmp     loc_180001CF9
0x180001ef9  mov     rcx, rbx; hMem
0x180001efc  call    cs:__imp_LocalFree
0x180001f02  xor     ebx, ebx
0x180001f04  jmp     loc_180001E31
0x180001f09  mov     ecx, 80090008h
0x180001f0e  jmp     loc_180001E6A
0x180001f13  xor     eax, eax
0x180001f15  jmp     loc_180001DA8
```
