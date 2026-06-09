# CTemplate::~CTemplate(void)

- ea: `0x180019fe4`
- end: `0x18001a237`
- name: `??1CTemplate@@UEAA@XZ`
- size: `595`
- prototype: `void __fastcall(CTemplate *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180019fa0`

## callees

- `0x1800145a4`
- `0x180019fe4`
- `0x18001a240`
- `0x18001a2b4`
- `0x18001a30c`
- `0x18001a3f0`
- `0x18001a424`
- `0x18005f938`
- `0x180064010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18002f54d`
- `ADVAPI32!SetThreadToken` at `0x18002f54d`
- `ADVAPI32!RevertToSelf` at `0x18002f4eb`
- `ADVAPI32!RevertToSelf` at `0x18002f4eb`
- `ADVAPI32!OpenThreadToken` at `0x18002f4e1`
- `ADVAPI32!OpenThreadToken` at `0x18002f4e1`
- `KERNEL32!HeapFree` at `0x18001a0f2`
- `KERNEL32!HeapFree` at `0x18001a114`
- `KERNEL32!HeapFree` at `0x18001a185`
- `KERNEL32!HeapFree` at `0x18001a1ab`
- `KERNEL32!HeapFree` at `0x18001a1c1`
- `KERNEL32!HeapFree` at `0x18002f529`
- `KERNEL32!HeapFree` at `0x18002f59a`
- `KERNEL32!HeapFree` at `0x18002f5c8`
- `KERNEL32!HeapFree` at `0x18001a0f2`
- `KERNEL32!HeapFree` at `0x18001a114`
- `KERNEL32!HeapFree` at `0x18001a185`
- `KERNEL32!HeapFree` at `0x18001a1ab`
- `KERNEL32!HeapFree` at `0x18001a1c1`
- `KERNEL32!HeapFree` at `0x18002f529`
- `KERNEL32!HeapFree` at `0x18002f59a`
- `KERNEL32!HeapFree` at `0x18002f5c8`
- `KERNEL32!DeleteFileA` at `0x18002f507`
- `KERNEL32!DeleteFileA` at `0x18002f507`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18002f4bd`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18002f577`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18002f4bd`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x18002f577`
- `KERNEL32!CloseHandle` at `0x18001a0d7`
- `KERNEL32!CloseHandle` at `0x18002f562`
- `KERNEL32!CloseHandle` at `0x18001a0d7`
- `KERNEL32!CloseHandle` at `0x18002f562`
- `KERNEL32!DeleteCriticalSection` at `0x18001a131`
- `KERNEL32!DeleteCriticalSection` at `0x18001a14a`
- `KERNEL32!DeleteCriticalSection` at `0x18001a131`
- `KERNEL32!DeleteCriticalSection` at `0x18001a14a`
- `KERNEL32!GetLastError` at `0x18002f4f3`
- `KERNEL32!GetLastError` at `0x18002f538`
- `KERNEL32!GetLastError` at `0x18002f557`
- `KERNEL32!GetLastError` at `0x18002f4f3`
- `KERNEL32!GetLastError` at `0x18002f538`
- `KERNEL32!GetLastError` at `0x18002f557`
- `KERNEL32!GetCurrentThread` at `0x18002f4c3`
- `KERNEL32!GetCurrentThread` at `0x18002f4c3`
- `iisutil!PuDbgPrint` at `0x18002f481`
- `iisutil!PuDbgPrint` at `0x18002f481`

## string_xrefs

- `0x18002f45d`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18002f475`: `Deleting template, m_cFilemaps = %d,  m_rgpFilemaps %p\n`
- `0x18002f44f`: `CTemplate::~CTemplate`

## pseudocode

```c
void __fastcall CTemplate::~CTemplate(CTemplate *this)
{
  bool v1; // zf
  const void **v2; // rsi
  unsigned int *v4; // rdi
  unsigned int i; // ebp
  unsigned int j; // ebp
  CTemplate::CFileMap *v7; // rcx
  unsigned int v8; // edx
  CTemplate::CWorkStore *v9; // rcx
  __int64 k; // rdi
  void *v11; // r8
  void *v12; // rcx
  void *v13; // r8
  void *v14; // r8
  __int64 v15; // rcx
  void *v16; // r8
  void *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  CIncFile *v23; // rcx
  HANDLE TokenHandle; // [rsp+60h] [rbp+8h] BYREF
  HANDLE Thread; // [rsp+68h] [rbp+10h] BYREF

  v1 = (g_dwDebugFlags & 3) == 0;
  *(_QWORD *)this = &CTemplate::`vftable'{for `CDblLink'};
  v2 = (const void **)((char *)this + 272);
  *((_QWORD *)this + 3) = &CTemplate::`vftable'{for `IDebugDocumentProvider'};
  v4 = (unsigned int *)((char *)this + 296);
  *((_QWORD *)this + 4) = &CTemplate::`vftable'{for `IDebugDocumentText'};
  *((_QWORD *)this + 5) = &CTemplate::`vftable'{for `IConnectionPointContainer'};
  if ( !v1 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
      1111,
      "CTemplate::~CTemplate",
      "Deleting template, m_cFilemaps = %d,  m_rgpFilemaps %p\n",
      *v4,
      *v2);
  for ( i = 1; i < *v4; ++i )
  {
    v23 = *(CIncFile **)(*((_QWORD *)*v2 + i) + 56LL);
    if ( v23 )
      CIncFile::RemoveTemplate(v23, this);
  }
  CTemplate::Detach(this);
  TokenHandle = 0;
  Thread = 0;
  if ( *((_QWORD *)this + 58) )
  {
    if ( g_fIsWow64Process )
      Wow64EnableWow64FsRedirection(0);
    Thread = GetCurrentThread();
    if ( OpenThreadToken(Thread, 0x2000Cu, 1, &TokenHandle) )
    {
      RevertToSelf();
    }
    else if ( GetLastError() != 1008 )
    {
      goto LABEL_47;
    }
    if ( DeleteFileA(*((LPCSTR *)this + 58)) )
    {
      *((_DWORD *)this + 98) &= ~0x1000u;
      HeapFree(CTemplate::sm_hLargeHeap, 0, *((LPVOID *)this + 58));
      *((_QWORD *)this + 58) = 0;
LABEL_48:
      if ( TokenHandle )
      {
        if ( !SetThreadToken(&Thread, TokenHandle) )
          GetLastError();
        CloseHandle(TokenHandle);
      }
      if ( g_fIsWow64Process )
        Wow64EnableWow64FsRedirection(1u);
      goto LABEL_5;
    }
LABEL_47:
    GetLastError();
    goto LABEL_48;
  }
LABEL_5:
  if ( *v2 )
  {
    for ( j = 0; j < *v4; ++j )
    {
      v7 = (CTemplate::CFileMap *)*((_QWORD *)*v2 + j);
      if ( v7 )
        CTemplate::CFileMap::`scalar deleting destructor'(v7, j);
    }
    SmallTemplateFreeNullify(v2);
  }
  CTemplate::FreeGoodTemplateMemory(this);
  v9 = (CTemplate::CWorkStore *)*((_QWORD *)this + 6);
  if ( v9 )
  {
    CTemplate::CWorkStore::`scalar deleting destructor'(v9, v8);
    *((_QWORD *)this + 6) = 0;
  }
  for ( k = 0; k != 6; ++k )
  {
    v11 = (void *)*((_QWORD *)this + k + 40);
    if ( v11 )
    {
      HeapFree(g_hDenaliHeap, 0, v11);
      *((_QWORD *)this + k + 40) = 0;
    }
  }
  v12 = (void *)*((_QWORD *)this + 7);
  if ( v12 )
    CloseHandle(v12);
  v13 = (void *)*((_QWORD *)this + 35);
  if ( v13 )
  {
    HeapFree(g_hDenaliHeap, 0, v13);
    *((_QWORD *)this + 35) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 48);
  if ( v14 )
  {
    HeapFree(g_hDenaliHeap, 0, v14);
    *((_QWORD *)this + 48) = 0;
  }
  if ( (*((_BYTE *)this + 392) & 0x10) != 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  if ( (*((_DWORD *)this + 98) & 0x8000) != 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
  v15 = *((_QWORD *)this + 54);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v16 = (void *)*((_QWORD *)this + 58);
  if ( v16 )
    HeapFree(CTemplate::sm_hLargeHeap, 0, v16);
  v17 = (void *)*((_QWORD *)this + 64);
  if ( v17 )
    HeapFree(CTemplate::sm_hSmallHeap, 0, v17);
  v18 = *((_QWORD *)this + 60);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    *((_QWORD *)this + 60) = 0;
  }
  HeapFree(g_hDenaliHeap, 0, *((LPVOID *)this + 55));
  HeapFree(g_hDenaliHeap, 0, *((LPVOID *)this + 51));
  v19 = *((_QWORD *)this + 33);
  v20 = *((_QWORD *)this + 32);
  *((_QWORD *)this + 31) = &CDblLink::`vftable';
  *(_QWORD *)(v19 + 8) = v20;
  *(_QWORD *)(*((_QWORD *)this + 32) + 16LL) = *((_QWORD *)this + 33);
  *((_QWORD *)this + 32) = (char *)this + 248;
  *((_QWORD *)this + 33) = (char *)this + 248;
  CConnectionPoint::~CConnectionPoint((CTemplate *)((char *)this + 88));
  v21 = *((_QWORD *)this + 2);
  v22 = *((_QWORD *)this + 1);
  *(_QWORD *)this = &CDblLink::`vftable';
  *(_QWORD *)(v21 + 8) = v22;
  *(_QWORD *)(*((_QWORD *)this + 1) + 16LL) = *((_QWORD *)this + 2);
  *((_QWORD *)this + 1) = this;
  *((_QWORD *)this + 2) = this;
}

```

## disassembly

```asm
0x180019fe4  mov     [rsp+arg_10], rbx
0x180019fe9  mov     [rsp+arg_18], rbp
0x180019fee  push    rsi
0x180019fef  push    rdi
0x180019ff0  push    r14
0x180019ff2  sub     rsp, 40h
0x180019ff6  test    byte ptr cs:g_dwDebugFlags, 3
0x180019ffd  lea     rax, ??_7CTemplate@@6BCDblLink@@@; const CTemplate::`vftable'{for `CDblLink'}
0x18001a004  mov     [rcx], rax
0x18001a007  lea     rsi, [rcx+110h]
0x18001a00e  lea     rax, ??_7CTemplate@@6BIDebugDocumentProvider@@@; const CTemplate::`vftable'{for `IDebugDocumentProvider'}
0x18001a015  mov     rbx, rcx
0x18001a018  mov     [rcx+18h], rax
0x18001a01c  lea     rdi, [rcx+128h]
0x18001a023  lea     rax, ??_7CTemplate@@6BIDebugDocumentText@@@; const CTemplate::`vftable'{for `IDebugDocumentText'}
0x18001a02a  mov     [rcx+20h], rax
0x18001a02e  lea     rax, ??_7CTemplate@@6BIConnectionPointContainer@@@; const CTemplate::`vftable'{for `IConnectionPointContainer'}
0x18001a035  mov     [rcx+28h], rax
0x18001a039  jnz     loc_18002F44C
0x18001a03f  mov     ebp, 1
0x18001a044  xor     r14d, r14d
0x18001a047  cmp     [rdi], ebp
0x18001a049  ja      loc_18002F48D
0x18001a04f  mov     rcx, rbx; this
0x18001a052  call    ?Detach@CTemplate@@QEAAJXZ; CTemplate::Detach(void)
0x18001a057  mov     [rsp+58h+TokenHandle], r14
0x18001a05c  mov     [rsp+58h+Thread], r14
0x18001a061  cmp     [rbx+1D0h], r14
0x18001a068  jnz     loc_18002F4B2
0x18001a06e  cmp     [rsi], r14
0x18001a071  jz      short loc_18001A09C
0x18001a073  mov     ebp, r14d
0x18001a076  cmp     [rdi], r14d
0x18001a079  jbe     short loc_18001A094
0x18001a07b  mov     rax, [rsi]
0x18001a07e  mov     edx, ebp; unsigned int
0x18001a080  mov     rcx, [rax+rdx*8]; this
0x18001a084  test    rcx, rcx
0x18001a087  jz      short loc_18001A08E
0x18001a089  call    ??_GCFileMap@CTemplate@@QEAAPEAXI@Z; CTemplate::CFileMap::`scalar deleting destructor'(uint)
0x18001a08e  inc     ebp
0x18001a090  cmp     ebp, [rdi]
0x18001a092  jb      short loc_18001A07B
0x18001a094  mov     rcx, rsi
0x18001a097  call    SmallTemplateFreeNullify
0x18001a09c  mov     rcx, rbx; this
0x18001a09f  call    ?FreeGoodTemplateMemory@CTemplate@@AEAAXXZ; CTemplate::FreeGoodTemplateMemory(void)
0x18001a0a4  mov     rcx, [rbx+30h]; this
0x18001a0a8  test    rcx, rcx
0x18001a0ab  jnz     loc_18002F583
0x18001a0b1  mov     rdi, r14
0x18001a0b4  mov     r8, [rbx+rdi*8+140h]; lpMem
0x18001a0bc  test    r8, r8
0x18001a0bf  jnz     loc_18002F591
0x18001a0c5  inc     rdi
0x18001a0c8  cmp     rdi, 6
0x18001a0cc  jnz     short loc_18001A0B4
0x18001a0ce  mov     rcx, [rbx+38h]; hObject
0x18001a0d2  test    rcx, rcx
0x18001a0d5  jz      short loc_18001A0DD
0x18001a0d7  call    cs:__imp_CloseHandle
0x18001a0dd  mov     r8, [rbx+118h]; lpMem
0x18001a0e4  test    r8, r8
0x18001a0e7  jz      short loc_18001A0FF
0x18001a0e9  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18001a0f0  xor     edx, edx; dwFlags
0x18001a0f2  call    cs:__imp_HeapFree
0x18001a0f8  mov     [rbx+118h], r14
0x18001a0ff  mov     r8, [rbx+180h]; lpMem
0x18001a106  test    r8, r8
0x18001a109  jz      short loc_18001A121
0x18001a10b  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18001a112  xor     edx, edx; dwFlags
0x18001a114  call    cs:__imp_HeapFree
0x18001a11a  mov     [rbx+180h], r14
0x18001a121  test    byte ptr [rbx+188h], 10h
0x18001a128  jz      short loc_18001A137
0x18001a12a  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x18001a131  call    cs:__imp_DeleteCriticalSection
0x18001a137  test    dword ptr [rbx+188h], 8000h
0x18001a141  jz      short loc_18001A150
0x18001a143  lea     rcx, [rbx+218h]; lpCriticalSection
0x18001a14a  call    cs:__imp_DeleteCriticalSection
0x18001a150  mov     rcx, [rbx+1B0h]
0x18001a157  test    rcx, rcx
0x18001a15a  jnz     loc_18002F5AD
0x18001a160  mov     r8, [rbx+1D0h]; lpMem
0x18001a167  test    r8, r8
0x18001a16a  jnz     loc_18002F5BF
0x18001a170  mov     r8, [rbx+200h]; lpMem
0x18001a177  test    r8, r8
0x18001a17a  jz      short loc_18001A18B
0x18001a17c  mov     rcx, cs:?sm_hSmallHeap@CTemplate@@2PEAXEA; hHeap
0x18001a183  xor     edx, edx; dwFlags
0x18001a185  call    cs:__imp_HeapFree
0x18001a18b  mov     rcx, [rbx+1E0h]
0x18001a192  test    rcx, rcx
0x18001a195  jnz     loc_18002F5D4
0x18001a19b  mov     r8, [rbx+1B8h]; lpMem
0x18001a1a2  xor     edx, edx; dwFlags
0x18001a1a4  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18001a1ab  call    cs:__imp_HeapFree
0x18001a1b1  mov     r8, [rbx+198h]; lpMem
0x18001a1b8  xor     edx, edx; dwFlags
0x18001a1ba  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18001a1c1  call    cs:__imp_HeapFree
0x18001a1c7  lea     rdx, [rbx+0F8h]
0x18001a1ce  mov     rcx, [rdx+10h]
0x18001a1d2  lea     rdi, ??_7CDblLink@@6B@; const CDblLink::`vftable'
0x18001a1d9  mov     rax, [rdx+8]
0x18001a1dd  mov     [rdx], rdi
0x18001a1e0  mov     [rcx+8], rax
0x18001a1e4  mov     rcx, [rdx+8]
0x18001a1e8  mov     rax, [rdx+10h]
0x18001a1ec  mov     [rcx+10h], rax
0x18001a1f0  lea     rcx, [rbx+58h]; this
0x18001a1f4  mov     [rdx+8], rdx
0x18001a1f8  mov     [rdx+10h], rdx
0x18001a1fc  call    ??1CConnectionPoint@@QEAA@XZ; CConnectionPoint::~CConnectionPoint(void)
0x18001a201  mov     rcx, [rbx+10h]
0x18001a205  mov     rax, [rbx+8]
0x18001a209  mov     rbp, [rsp+58h+arg_18]
0x18001a20e  mov     [rbx], rdi
0x18001a211  mov     [rcx+8], rax
0x18001a215  mov     rcx, [rbx+8]
0x18001a219  mov     rax, [rbx+10h]
0x18001a21d  mov     [rcx+10h], rax
0x18001a221  mov     [rbx+8], rbx
0x18001a225  mov     [rbx+10h], rbx
0x18001a229  mov     rbx, [rsp+58h+arg_10]
0x18001a22e  add     rsp, 40h
0x18001a232  pop     r14
0x18001a234  pop     rdi
0x18001a235  pop     rsi
0x18001a236  retn
0x18002f44c  mov     rax, [rsi]
0x18002f44f  lea     r9, aCtemplateCtemp; "CTemplate::~CTemplate"
0x18002f456  mov     rcx, cs:g_pDebug
0x18002f45d  lea     rdx, aInetsrvIisSvcs_4; "inetsrv\\iis\\svcs\\cmp\\asp\\template."...
0x18002f464  mov     [rsp+58h+var_28], rax
0x18002f469  mov     r8d, 457h
0x18002f46f  mov     eax, [rdi]
0x18002f471  mov     [rsp+58h+var_30], eax
0x18002f475  lea     rax, aDeletingTempla; "Deleting template, m_cFilemaps = %d,  m"...
0x18002f47c  mov     [rsp+58h+var_38], rax
0x18002f481  call    cs:__imp_PuDbgPrint
0x18002f487  nop
0x18002f488  jmp     loc_18001A03F
0x18002f48d  mov     rax, [rsi]
0x18002f490  mov     ecx, ebp
0x18002f492  mov     rcx, [rax+rcx*8]
0x18002f496  mov     rcx, [rcx+38h]; this
0x18002f49a  test    rcx, rcx
0x18002f49d  jz      short loc_18002F4A7
0x18002f49f  mov     rdx, rbx; struct CTemplate *
0x18002f4a2  call    ?RemoveTemplate@CIncFile@@QEAAXPEAVCTemplate@@@Z; CIncFile::RemoveTemplate(CTemplate *)
0x18002f4a7  inc     ebp
0x18002f4a9  cmp     ebp, [rdi]
0x18002f4ab  jb      short loc_18002F48D
0x18002f4ad  jmp     loc_18001A04F
0x18002f4b2  cmp     cs:?g_fIsWow64Process@@3HA, r14d; int g_fIsWow64Process
0x18002f4b9  jz      short loc_18002F4C3
0x18002f4bb  xor     ecx, ecx; Wow64FsEnableRedirection
0x18002f4bd  call    cs:__imp_Wow64EnableWow64FsRedirection
0x18002f4c3  call    cs:__imp_GetCurrentThread
0x18002f4c9  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18002f4ce  mov     edx, 2000Ch; DesiredAccess
0x18002f4d3  mov     rcx, rax; ThreadHandle
0x18002f4d6  mov     [rsp+58h+Thread], rax
0x18002f4db  mov     r8d, 1; OpenAsSelf
0x18002f4e1  call    cs:__imp_OpenThreadToken
0x18002f4e7  test    eax, eax
0x18002f4e9  jz      short loc_18002F4F3
0x18002f4eb  call    cs:__imp_RevertToSelf
0x18002f4f1  jmp     short loc_18002F500
0x18002f4f3  call    cs:__imp_GetLastError
0x18002f4f9  cmp     eax, 3F0h
0x18002f4fe  jnz     short loc_18002F538
0x18002f500  mov     rcx, [rbx+1D0h]; lpFileName
0x18002f507  call    cs:__imp_DeleteFileA
0x18002f50d  test    eax, eax
0x18002f50f  jz      short loc_18002F538
0x18002f511  btr     dword ptr [rbx+188h], 0Ch
0x18002f519  xor     edx, edx; dwFlags
0x18002f51b  mov     r8, [rbx+1D0h]; lpMem
0x18002f522  mov     rcx, cs:?sm_hLargeHeap@CTemplate@@2PEAXEA; hHeap
0x18002f529  call    cs:__imp_HeapFree
0x18002f52f  mov     [rbx+1D0h], r14
0x18002f536  jmp     short loc_18002F53E
0x18002f538  call    cs:__imp_GetLastError
0x18002f53e  mov     rdx, [rsp+58h+TokenHandle]; Token
0x18002f543  test    rdx, rdx
0x18002f546  jz      short loc_18002F568
0x18002f548  lea     rcx, [rsp+58h+Thread]; Thread
0x18002f54d  call    cs:__imp_SetThreadToken
0x18002f553  test    eax, eax
0x18002f555  jnz     short loc_18002F55D
0x18002f557  call    cs:__imp_GetLastError
0x18002f55d  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18002f562  call    cs:__imp_CloseHandle
0x18002f568  cmp     cs:?g_fIsWow64Process@@3HA, r14d; int g_fIsWow64Process
0x18002f56f  jz      loc_18001A06E
0x18002f575  mov     cl, 1; Wow64FsEnableRedirection
0x18002f577  call    cs:__imp_Wow64EnableWow64FsRedirection
0x18002f57d  nop
0x18002f57e  jmp     loc_18001A06E
0x18002f583  call    ??_GCWorkStore@CTemplate@@QEAAPEAXI@Z; CTemplate::CWorkStore::`scalar deleting destructor'(uint)
0x18002f588  mov     [rbx+30h], r14
0x18002f58c  jmp     loc_18001A0B1
0x18002f591  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002f598  xor     edx, edx; dwFlags
0x18002f59a  call    cs:__imp_HeapFree
0x18002f5a0  mov     [rbx+rdi*8+140h], r14
0x18002f5a8  jmp     loc_18001A0C5
0x18002f5ad  mov     rax, [rcx]
0x18002f5b0  mov     rax, [rax+10h]
0x18002f5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5b9  nop
0x18002f5ba  jmp     loc_18001A160
0x18002f5bf  mov     rcx, cs:?sm_hLargeHeap@CTemplate@@2PEAXEA; hHeap
0x18002f5c6  xor     edx, edx; dwFlags
0x18002f5c8  call    cs:__imp_HeapFree
0x18002f5ce  nop
0x18002f5cf  jmp     loc_18001A170
0x18002f5d4  mov     rax, [rcx]
0x18002f5d7  mov     rax, [rax+10h]
0x18002f5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5e0  mov     [rbx+1E0h], r14
0x18002f5e7  jmp     loc_18001A19B
```
