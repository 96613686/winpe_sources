# CTemplate::PersistData(char *)

- ea: `0x1800121c0`
- end: `0x18001245d`
- name: `?PersistData@CTemplate@@QEAAJPEAD@Z`
- size: `669`
- prototype: `__int64 __fastcall(CTemplate *__hidden this, char *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000a9d0`
- `0x1800108d0`
- `0x1800133a8`

## callees

- `0x18000f780`
- `0x180011560`
- `0x1800121c0`
- `0x180016918`
- `0x18001a628`
- `0x180064010`

## import_xrefs

- `ADVAPI32!SetNamedSecurityInfoA` at `0x180012385`
- `ADVAPI32!SetNamedSecurityInfoA` at `0x180012385`
- `ADVAPI32!SetThreadToken` at `0x18001241f`
- `ADVAPI32!SetThreadToken` at `0x18001241f`
- `ADVAPI32!RevertToSelf` at `0x1800122e6`
- `ADVAPI32!RevertToSelf` at `0x1800122e6`
- `ADVAPI32!OpenThreadToken` at `0x1800122d8`
- `ADVAPI32!OpenThreadToken` at `0x1800122d8`
- `KERNEL32!HeapFree` at `0x18002b4bb`
- `KERNEL32!HeapFree` at `0x18002b4bb`
- `KERNEL32!HeapAlloc` at `0x180012302`
- `KERNEL32!HeapAlloc` at `0x180012302`
- `KERNEL32!GetTempFileNameA` at `0x18001232c`
- `KERNEL32!GetTempFileNameA` at `0x18001232c`
- `KERNEL32!CreateFileA` at `0x1800123ba`
- `KERNEL32!CreateFileA` at `0x1800123ba`
- `KERNEL32!WriteFile` at `0x1800123e2`
- `KERNEL32!WriteFile` at `0x1800123e2`
- `KERNEL32!LocalFree` at `0x180012445`
- `KERNEL32!LocalFree` at `0x180012445`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18002b3dc`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18002b4cf`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18002b3dc`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18002b4cf`
- `KERNEL32!CloseHandle` at `0x1800123f3`
- `KERNEL32!CloseHandle` at `0x180012432`
- `KERNEL32!CloseHandle` at `0x18002b4a0`
- `KERNEL32!CloseHandle` at `0x1800123f3`
- `KERNEL32!CloseHandle` at `0x180012432`
- `KERNEL32!CloseHandle` at `0x18002b4a0`
- `KERNEL32!GetLastError` at `0x18002b3f2`
- `KERNEL32!GetLastError` at `0x18002b403`
- `KERNEL32!GetLastError` at `0x18002b42b`
- `KERNEL32!GetLastError` at `0x18002b446`
- `KERNEL32!GetLastError` at `0x18002b464`
- `KERNEL32!GetLastError` at `0x18002b3f2`
- `KERNEL32!GetLastError` at `0x18002b403`
- `KERNEL32!GetLastError` at `0x18002b42b`
- `KERNEL32!GetLastError` at `0x18002b446`
- `KERNEL32!GetLastError` at `0x18002b464`
- `KERNEL32!GetCurrentThread` at `0x1800122b7`
- `KERNEL32!GetCurrentThread` at `0x1800122b7`

## string_xrefs

- `0x18001231b`: `ASPTemplate`

## pseudocode

```c
__int64 __fastcall CTemplate::PersistData(CTemplate *this, char *a2)
{
  signed int v3; // esi
  void *v4; // rbp
  __int64 v5; // rax
  unsigned int (__fastcall *v6)(CTemplate *__hidden); // rax
  CTemplate *v7; // rcx
  unsigned int (__fastcall *v8)(CTemplate *__hidden); // rax
  CTemplate *v9; // rcx
  bool v10; // zf
  SIZE_T v12; // rax
  CHAR *v13; // rax
  signed int v14; // eax
  HANDLE FileA; // rax
  signed int v16; // eax
  signed int LastError; // eax
  void *v18; // r8
  HANDLE TokenHandle; // [rsp+70h] [rbp+8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp+10h] BYREF
  int v21; // [rsp+7Ch] [rbp+14h]
  PACL pDacl; // [rsp+80h] [rbp+18h] BYREF
  HANDLE Thread; // [rsp+88h] [rbp+20h] BYREF

  v21 = HIDWORD(a2);
  NumberOfBytesWritten = 0;
  TokenHandle = 0;
  Thread = 0;
  pDacl = 0;
  if ( g_fIsWow64Process )
    Wow64EnableWow64FsRedirection(0);
  if ( (*((_BYTE *)this + 392) & 2) == 0 )
  {
    v3 = -2147467259;
    goto LABEL_13;
  }
  v3 = 0;
  v4 = 0;
  if ( *((_QWORD *)this + 58) )
  {
LABEL_5:
    v5 = *((_QWORD *)this + 3);
    *((_DWORD *)this + 98) |= 0x1000u;
    v6 = *(unsigned int (__fastcall **)(CTemplate *__hidden))(v5 + 8);
    v7 = (CTemplate *)((char *)this + 24);
    if ( v6 == CTemplate::AddRef )
      CTemplate::AddRef(v7);
    else
      v6(v7);
    v8 = *(unsigned int (__fastcall **)(CTemplate *__hidden))(*((_QWORD *)this + 3) + 16LL);
    v9 = (CTemplate *)((char *)this + 24);
    if ( v8 == CTemplate::Release )
      CTemplate::Release(v9);
    else
      v8(v9);
    v10 = v3 == 0;
LABEL_10:
    if ( !v10 )
    {
      if ( v4 )
        CloseHandle(v4);
      v18 = (void *)*((_QWORD *)this + 58);
      if ( v18 )
        HeapFree(CTemplate::sm_hLargeHeap, 0, v18);
      *((_QWORD *)this + 58) = 0;
    }
    if ( pDacl )
      LocalFree(pDacl);
    goto LABEL_13;
  }
  Thread = GetCurrentThread();
  if ( OpenThreadToken(Thread, 0x2000Cu, 1, &TokenHandle) )
  {
    RevertToSelf();
LABEL_18:
    v12 = _RoundUp(0x104u);
    v13 = (CHAR *)HeapAlloc(CTemplate::sm_hLargeHeap, 0, v12);
    *((_QWORD *)this + 58) = v13;
    if ( !v13 )
    {
      v3 = -2147024882;
      goto LABEL_29;
    }
    if ( !GetTempFileNameA(&CTemplateCacheManager::m_szPersistCacheDir, "ASPTemplate", 0, v13) )
      goto LABEL_41;
    v3 = CTemplate::BuildPersistedDACL(this, &pDacl);
    if ( v3 < 0 )
      goto LABEL_29;
    if ( pDacl )
    {
      v14 = SetNamedSecurityInfoA(*((LPSTR *)this + 58), SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
      if ( v14 )
      {
        if ( v14 <= 0 )
        {
          v3 = v14;
          goto LABEL_34;
        }
        goto LABEL_46;
      }
    }
    FileA = CreateFileA(*((LPCSTR *)this + 58), 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v4 = FileA;
    if ( FileA != (HANDLE)-1LL
      && WriteFile(FileA, *((LPCVOID *)this + 8), *((_DWORD *)this + 18), &NumberOfBytesWritten, 0) )
    {
      if ( CloseHandle(v4) )
      {
        v4 = 0;
LABEL_27:
        if ( NumberOfBytesWritten != *((_DWORD *)this + 18) )
          v3 = -2147467259;
LABEL_29:
        if ( TokenHandle )
        {
          if ( !SetThreadToken(&Thread, TokenHandle) )
          {
            LastError = GetLastError();
            v3 = LastError;
            if ( LastError > 0 )
              v3 = (unsigned __int16)LastError | 0x80070000;
          }
          CloseHandle(TokenHandle);
        }
        v10 = v3 == 0;
        if ( v3 < 0 )
          goto LABEL_10;
        goto LABEL_5;
      }
      v14 = GetLastError();
      v3 = v14;
      if ( v14 <= 0 )
      {
LABEL_34:
        if ( v3 < 0 )
          goto LABEL_29;
        goto LABEL_27;
      }
    }
    else
    {
LABEL_41:
      v14 = GetLastError();
      v3 = v14;
      if ( v14 <= 0 )
        goto LABEL_34;
    }
LABEL_46:
    v3 = (unsigned __int16)v14 | 0x80070000;
    goto LABEL_34;
  }
  if ( GetLastError() == 1008 )
    goto LABEL_18;
  v16 = GetLastError();
  v3 = v16;
  if ( v16 > 0 )
    v3 = (unsigned __int16)v16 | 0x80070000;
LABEL_13:
  if ( g_fIsWow64Process )
    Wow64EnableWow64FsRedirection(1u);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800121c0  mov     rax, rsp
0x1800121c3  mov     [rax+10h], rdx
0x1800121c7  sub     rsp, 68h
0x1800121cb  mov     [rax-8], rbx
0x1800121cf  mov     rbx, rcx
0x1800121d2  mov     [rax-28h], r14
0x1800121d6  xor     r14d, r14d
0x1800121d9  cmp     cs:?g_fIsWow64Process@@3HA, r14d; int g_fIsWow64Process
0x1800121e0  mov     [rax+10h], r14d
0x1800121e4  mov     [rax+8], r14
0x1800121e8  mov     [rax+20h], r14
0x1800121ec  mov     [rax+18h], r14
0x1800121f0  jnz     loc_18002B3DA
0x1800121f6  test    byte ptr [rbx+188h], 2
0x1800121fd  mov     [rsp+68h+var_18], rsi
0x180012202  jz      loc_18002B3E8
0x180012208  mov     esi, r14d
0x18001220b  mov     [rsp+68h+var_10], rbp
0x180012210  mov     rbp, r14
0x180012213  cmp     [rbx+1D0h], rsi
0x18001221a  jz      loc_1800122B7
0x180012220  mov     rax, [rbx+18h]
0x180012224  lea     rcx, ?AddRef@CTemplate@@UEAAKXZ; CTemplate::AddRef(void)
0x18001222b  or      dword ptr [rbx+188h], 1000h
0x180012235  mov     [rsp+68h+var_20], rdi
0x18001223a  mov     rax, [rax+8]
0x18001223e  cmp     rax, rcx
0x180012241  lea     rcx, [rbx+18h]; this
0x180012245  jnz     loc_18002B482
0x18001224b  call    ?AddRef@CTemplate@@UEAAKXZ; CTemplate::AddRef(void)
0x180012250  mov     rax, [rbx+18h]
0x180012254  lea     rcx, ?Release@CTemplate@@UEAAKXZ; CTemplate::Release(void)
0x18001225b  mov     rax, [rax+10h]
0x18001225f  cmp     rax, rcx
0x180012262  lea     rcx, [rbx+18h]; this
0x180012266  jnz     loc_18002B48D
0x18001226c  call    ?Release@CTemplate@@UEAAKXZ; CTemplate::Release(void)
0x180012271  mov     rdi, [rsp+68h+var_20]
0x180012276  test    esi, esi
0x180012278  jnz     loc_18002B498
0x18001227e  mov     rcx, [rsp+68h+arg_10]; hMem
0x180012286  test    rcx, rcx
0x180012289  jnz     loc_180012445
0x18001228f  mov     rbp, [rsp+68h+var_10]
0x180012294  cmp     cs:?g_fIsWow64Process@@3HA, 0; int g_fIsWow64Process
0x18001229b  mov     r14, [rsp+68h+var_28]
0x1800122a0  mov     rbx, [rsp+68h+var_8]
0x1800122a5  jnz     loc_18002B4CD
0x1800122ab  mov     eax, esi
0x1800122ad  mov     rsi, [rsp+68h+var_18]
0x1800122b2  add     rsp, 68h
0x1800122b6  retn
0x1800122b7  call    cs:__imp_GetCurrentThread
0x1800122bd  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x1800122c2  mov     edx, 2000Ch; DesiredAccess
0x1800122c7  mov     rcx, rax; ThreadHandle
0x1800122ca  mov     [rsp+68h+Thread], rax
0x1800122d2  mov     r8d, 1; OpenAsSelf
0x1800122d8  call    cs:__imp_OpenThreadToken
0x1800122de  test    eax, eax
0x1800122e0  jz      loc_18002B3F2
0x1800122e6  call    cs:__imp_RevertToSelf
0x1800122ec  mov     ecx, 104h; unsigned __int64
0x1800122f1  call    ?_RoundUp@@YA_K_K@Z; _RoundUp(unsigned __int64)
0x1800122f6  mov     rcx, cs:?sm_hLargeHeap@CTemplate@@2PEAXEA; hHeap
0x1800122fd  mov     r8, rax; dwBytes
0x180012300  xor     edx, edx; dwFlags
0x180012302  call    cs:__imp_HeapAlloc
0x180012308  mov     [rbx+1D0h], rax
0x18001230f  test    rax, rax
0x180012312  jz      loc_18002B421
0x180012318  mov     r9, rax; lpTempFileName
0x18001231b  lea     rdx, PrefixString; "ASPTemplate"
0x180012322  xor     r8d, r8d; uUnique
0x180012325  lea     rcx, ?m_szPersistCacheDir@CTemplateCacheManager@@0PADA; lpPathName
0x18001232c  call    cs:__imp_GetTempFileNameA
0x180012332  test    eax, eax
0x180012334  jz      loc_18002B42B
0x18001233a  lea     rdx, [rsp+68h+arg_10]; struct _ACL **
0x180012342  mov     rcx, rbx; this
0x180012345  call    ?BuildPersistedDACL@CTemplate@@AEAAJPEAPEAU_ACL@@@Z; CTemplate::BuildPersistedDACL(_ACL * *)
0x18001234a  mov     esi, eax
0x18001234c  test    eax, eax
0x18001234e  js      loc_18001240D
0x180012354  mov     rax, [rsp+68h+arg_10]
0x18001235c  test    rax, rax
0x18001235f  jz      short loc_180012393
0x180012361  mov     rcx, [rbx+1D0h]; pObjectName
0x180012368  xor     r9d, r9d; psidOwner
0x18001236b  mov     [rsp+68h+pSacl], r14; pSacl
0x180012370  mov     edx, 1; ObjectType
0x180012375  mov     [rsp+68h+pDacl], rax; pDacl
0x18001237a  mov     r8d, 4; SecurityInfo
0x180012380  mov     [rsp+68h+psidGroup], r14; psidGroup
0x180012385  call    cs:__imp_SetNamedSecurityInfoA
0x18001238b  test    eax, eax
0x18001238d  jnz     loc_18002B43D
0x180012393  mov     rcx, [rbx+1D0h]; lpFileName
0x18001239a  xor     r9d, r9d; lpSecurityAttributes
0x18001239d  mov     [rsp+68h+pSacl], r14; hTemplateFile
0x1800123a2  xor     r8d, r8d; dwShareMode
0x1800123a5  mov     dword ptr [rsp+68h+pDacl], 80h; dwFlagsAndAttributes
0x1800123ad  mov     edx, 40000000h; dwDesiredAccess
0x1800123b2  mov     dword ptr [rsp+68h+psidGroup], 2; dwCreationDisposition
0x1800123ba  call    cs:__imp_CreateFileA
0x1800123c0  mov     rbp, rax
0x1800123c3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800123c7  jz      loc_18002B42B
0x1800123cd  mov     r8d, [rbx+48h]; nNumberOfBytesToWrite
0x1800123d1  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800123d6  mov     rdx, [rbx+40h]; lpBuffer
0x1800123da  mov     rcx, rax; hFile
0x1800123dd  mov     [rsp+68h+psidGroup], r14; lpOverlapped
0x1800123e2  call    cs:__imp_WriteFile
0x1800123e8  test    eax, eax
0x1800123ea  jz      loc_18002B42B
0x1800123f0  mov     rcx, rbp; hObject
0x1800123f3  call    cs:__imp_CloseHandle
0x1800123f9  test    eax, eax
0x1800123fb  jz      loc_18002B446
0x180012401  mov     rbp, r14
0x180012404  mov     eax, [rbx+48h]
0x180012407  cmp     [rsp+68h+NumberOfBytesWritten], eax
0x18001240b  jnz     short loc_180012456
0x18001240d  mov     rdx, [rsp+68h+TokenHandle]; Token
0x180012412  test    rdx, rdx
0x180012415  jz      short loc_180012438
0x180012417  lea     rcx, [rsp+68h+Thread]; Thread
0x18001241f  call    cs:__imp_SetThreadToken
0x180012425  test    eax, eax
0x180012427  jz      loc_18002B464
0x18001242d  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180012432  call    cs:__imp_CloseHandle
0x180012438  test    esi, esi
0x18001243a  jns     loc_180012220
0x180012440  jmp     loc_180012278
0x180012445  call    cs:__imp_LocalFree
0x18001244b  jmp     loc_18001228F
0x180012450  test    esi, esi
0x180012452  jns     short loc_180012404
0x180012454  jmp     short loc_18001240D
0x180012456  mov     esi, 80004005h
0x18001245b  jmp     short loc_18001240D
0x18002b3da  xor     ecx, ecx; Wow64FsEnableRedirection
0x18002b3dc  call    cs:__imp_Wow64EnableWow64FsRedirection
0x18002b3e2  nop
0x18002b3e3  jmp     loc_1800121F6
0x18002b3e8  mov     esi, 80004005h
0x18002b3ed  jmp     loc_180012294
0x18002b3f2  call    cs:__imp_GetLastError
0x18002b3f8  cmp     eax, 3F0h
0x18002b3fd  jz      loc_1800122EC
0x18002b403  call    cs:__imp_GetLastError
0x18002b409  mov     esi, eax
0x18002b40b  test    eax, eax
0x18002b40d  jle     loc_18001228F
0x18002b413  movzx   esi, ax
0x18002b416  or      esi, 80070000h
0x18002b41c  jmp     loc_18001228F
0x18002b421  mov     esi, 8007000Eh
0x18002b426  jmp     loc_18001240D
0x18002b42b  call    cs:__imp_GetLastError
0x18002b431  mov     esi, eax
0x18002b433  test    eax, eax
0x18002b435  jle     loc_180012450
0x18002b43b  jmp     short loc_18002B456
0x18002b43d  jg      short loc_18002B456
0x18002b43f  mov     esi, eax
0x18002b441  jmp     loc_180012450
0x18002b446  call    cs:__imp_GetLastError
0x18002b44c  mov     esi, eax
0x18002b44e  test    eax, eax
0x18002b450  jle     loc_180012450
0x18002b456  movzx   esi, ax
0x18002b459  or      esi, 80070000h
0x18002b45f  jmp     loc_180012450
0x18002b464  call    cs:__imp_GetLastError
0x18002b46a  mov     esi, eax
0x18002b46c  test    eax, eax
0x18002b46e  jle     loc_18001242D
0x18002b474  movzx   esi, ax
0x18002b477  or      esi, 80070000h
0x18002b47d  jmp     loc_18001242D
0x18002b482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b487  nop
0x18002b488  jmp     loc_180012250
0x18002b48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b492  nop
0x18002b493  jmp     loc_180012271
0x18002b498  test    rbp, rbp
0x18002b49b  jz      short loc_18002B4A6
0x18002b49d  mov     rcx, rbp; hObject
0x18002b4a0  call    cs:__imp_CloseHandle
0x18002b4a6  mov     r8, [rbx+1D0h]; lpMem
0x18002b4ad  test    r8, r8
0x18002b4b0  jz      short loc_18002B4C1
0x18002b4b2  mov     rcx, cs:?sm_hLargeHeap@CTemplate@@2PEAXEA; hHeap
0x18002b4b9  xor     edx, edx; dwFlags
0x18002b4bb  call    cs:__imp_HeapFree
0x18002b4c1  mov     [rbx+1D0h], r14
0x18002b4c8  jmp     loc_18001227E
0x18002b4cd  mov     cl, 1; Wow64FsEnableRedirection
0x18002b4cf  call    cs:__imp_Wow64EnableWow64FsRedirection
0x18002b4d5  nop
0x18002b4d6  jmp     loc_1800122AB
```
