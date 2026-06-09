# CScriptManager::Init(void)

- ea: `0x180001548`
- end: `0x180001984`
- name: `?Init@CScriptManager@@QEAAJXZ`
- size: `1084`
- prototype: `__int64 __fastcall(CScriptManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004a64`

## callees

- `0x180001548`
- `0x18000f614`
- `0x18004197c`
- `0x180064010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800017d8`
- `ole32!CoCreateInstance` at `0x1800017d8`
- `KERNEL32!DeleteCriticalSection` at `0x18000187b`
- `KERNEL32!DeleteCriticalSection` at `0x180001892`
- `KERNEL32!DeleteCriticalSection` at `0x1800018a3`
- `KERNEL32!DeleteCriticalSection` at `0x18000187b`
- `KERNEL32!DeleteCriticalSection` at `0x180001892`
- `KERNEL32!DeleteCriticalSection` at `0x1800018a3`
- `KERNEL32!GetLastError` at `0x1800015a9`
- `KERNEL32!GetLastError` at `0x180001602`
- `KERNEL32!GetLastError` at `0x180001660`
- `KERNEL32!GetLastError` at `0x1800015a9`
- `KERNEL32!GetLastError` at `0x180001602`
- `KERNEL32!GetLastError` at `0x180001660`
- `iisutil!RemoveWorkItem` at `0x180001869`
- `iisutil!RemoveWorkItem` at `0x180001869`
- `iisutil!ScheduleWorkItem` at `0x18000178e`
- `iisutil!ScheduleWorkItem` at `0x18000178e`
- `iisutil!IISInitializeCriticalSection` at `0x18000159f`
- `iisutil!IISInitializeCriticalSection` at `0x1800015f8`
- `iisutil!IISInitializeCriticalSection` at `0x180001656`
- `iisutil!IISInitializeCriticalSection` at `0x18000159f`
- `iisutil!IISInitializeCriticalSection` at `0x1800015f8`
- `iisutil!IISInitializeCriticalSection` at `0x180001656`

## pseudocode

```c
__int64 __fastcall CScriptManager::Init(CScriptManager *this)
{
  int v2; // ebx
  signed int LastError; // eax
  int v4; // edi
  signed int v5; // eax
  int v6; // r15d
  signed int v7; // eax
  unsigned int v8; // ecx
  unsigned __int16 v9; // r8
  unsigned __int16 v10; // dx
  _DWORD v11[16]; // [rsp+38h] [rbp-40h]
  int v12; // [rsp+90h] [rbp+18h]
  LPVOID ppv; // [rsp+98h] [rbp+20h] BYREF

  v11[0] = 3;
  v11[1] = 11;
  v11[2] = 23;
  v11[3] = 57;
  v11[4] = 89;
  if ( byte_18007CC48 )
    return 1247;
  v2 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&CriticalSection) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
  }
  v4 = 0;
  v12 = 0;
  if ( v2 < 0 )
  {
    v6 = 0;
    goto LABEL_31;
  }
  v2 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&stru_18007CD68) )
  {
    v5 = GetLastError();
    v2 = v5;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
  }
  v6 = 1;
  if ( v2 < 0 )
    goto LABEL_31;
  v2 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&stru_18007CEA8) )
  {
    v7 = GetLastError();
    v2 = v7;
    if ( v7 > 0 )
      v2 = (unsigned __int16)v7 | 0x80070000;
  }
  v12 = 1;
  if ( v2 < 0 )
    goto LABEL_31;
  qword_18007CF00 = 11;
  qword_18007CEF0 = 0;
  dword_18007CED8 |= 1u;
  v4 = 1;
  v8 = ((unsigned int)dword_180079F7C >> 1) + 1;
  v9 = 4;
  v10 = 4;
  while ( v11[v10] >= v8 )
  {
    if ( !--v10 )
      goto LABEL_20;
  }
  v8 = v11[v10];
LABEL_20:
  if ( v8 < 0xB )
    v8 = 3;
  qword_18007CC80 = v8;
  qword_18007CC70 = 0;
  dword_18007CC58 |= 1u;
  do
  {
    if ( v11[v9] < 5u )
      break;
    --v9;
  }
  while ( v9 );
  qword_18007CDC0 = 3;
  qword_18007CDB0 = 0;
  dword_18007CD98 |= 1u;
  dword_18007CFFC = 45000;
  dword_18007CFF8 = ScheduleWorkItem(
                      (void (*)(void *))CScriptManager::ScriptKillerSchedulerCallback,
                      &g_ScriptManager,
                      0xAFC8u,
                      1);
  if ( !dword_18007CFF8 )
  {
    v2 = -2147467259;
LABEL_31:
    if ( dword_18007CFF8 )
      RemoveWorkItem(dword_18007CFF8);
    if ( v6 )
      DeleteCriticalSection(&CriticalSection);
    if ( v12 )
      DeleteCriticalSection(&stru_18007CD68);
    if ( v4 )
    {
      DeleteCriticalSection(&stru_18007CEA8);
      CHashTable::UnInit((CHashTable *)&qword_18007CED0);
      CHashTable::UnInit((CHashTable *)&qword_18007CC50);
      CHashTable::UnInit((CHashTable *)&qword_18007CD90);
    }
    if ( g_pWrapTypelibs )
    {
      (*(void (__fastcall **)(struct IWrapTypeLibs *))(*(_QWORD *)g_pWrapTypelibs + 16LL))(g_pWrapTypelibs);
      g_pWrapTypelibs = 0;
    }
    goto LABEL_41;
  }
  ppv = 0;
  v2 = CoCreateInstance(&rclsid, 0, 1u, &IID_IActiveScript, &ppv);
  if ( v2 < 0 )
    goto LABEL_31;
  v2 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IWrapTypeLibs **))ppv)(
         ppv,
         &IID_IWrapTypeLibs,
         &g_pWrapTypelibs);
  if ( v2 < 0 )
    goto LABEL_31;
  byte_18007CC48 = 1;
LABEL_41:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180001548  mov     rax, rsp
0x18000154b  mov     [rax+8], rcx
0x18000154f  push    rbx
0x180001550  push    rdi
0x180001551  push    r14
0x180001553  push    r15
0x180001555  sub     rsp, 58h
0x180001559  mov     r14d, 3
0x18000155f  mov     [rax-40h], r14d
0x180001563  mov     dword ptr [rax-3Ch], 0Bh
0x18000156a  mov     dword ptr [rax-38h], 17h
0x180001571  mov     dword ptr [rax-34h], 39h ; '9'
0x180001578  mov     dword ptr [rax-30h], 59h ; 'Y'
0x18000157f  cmp     cs:byte_18007CC48, 0
0x180001586  jz      short loc_180001592
0x180001588  mov     eax, 4DFh
0x18000158d  jmp     loc_180001979
0x180001592  xor     ebx, ebx
0x180001594  mov     [rsp+78h+var_48], ebx
0x180001598  lea     rcx, CriticalSection
0x18000159f  call    cs:__imp_IISInitializeCriticalSection
0x1800015a5  test    eax, eax
0x1800015a7  jnz     short loc_1800015C2
0x1800015a9  call    cs:__imp_GetLastError
0x1800015af  mov     ebx, eax
0x1800015b1  test    eax, eax
0x1800015b3  jle     short loc_1800015BE
0x1800015b5  movzx   ebx, ax
0x1800015b8  or      ebx, 80070000h
0x1800015be  mov     [rsp+78h+var_48], ebx
0x1800015c2  jmp     short loc_1800015D3
0x1800015c4  mov     ebx, 8000FFFFh
0x1800015c9  mov     [rsp+78h+var_48], ebx
0x1800015cd  mov     r14d, 3
0x1800015d3  xor     edi, edi
0x1800015d5  mov     [rsp+78h+arg_0], edi
0x1800015dc  mov     [rsp+78h+arg_10], edi
0x1800015e3  test    ebx, ebx
0x1800015e5  js      loc_18000185C
0x1800015eb  xor     ebx, ebx
0x1800015ed  mov     [rsp+78h+var_48], ebx
0x1800015f1  lea     rcx, stru_18007CD68
0x1800015f8  call    cs:__imp_IISInitializeCriticalSection
0x1800015fe  test    eax, eax
0x180001600  jnz     short loc_18000161B
0x180001602  call    cs:__imp_GetLastError
0x180001608  mov     ebx, eax
0x18000160a  test    eax, eax
0x18000160c  jle     short loc_180001617
0x18000160e  movzx   ebx, ax
0x180001611  or      ebx, 80070000h
0x180001617  mov     [rsp+78h+var_48], ebx
0x18000161b  jmp     short loc_180001633
0x18000161d  mov     ebx, 8000FFFFh
0x180001622  mov     [rsp+78h+var_48], ebx
0x180001626  mov     r14d, 3
0x18000162c  mov     edi, [rsp+78h+arg_0]
0x180001633  mov     r15d, 1
0x180001639  mov     [rsp+78h+arg_8], r15d
0x180001641  test    ebx, ebx
0x180001643  js      loc_18000185F
0x180001649  xor     ebx, ebx
0x18000164b  mov     [rsp+78h+var_48], ebx
0x18000164f  lea     rcx, stru_18007CEA8
0x180001656  call    cs:__imp_IISInitializeCriticalSection
0x18000165c  test    eax, eax
0x18000165e  jnz     short loc_180001679
0x180001660  call    cs:__imp_GetLastError
0x180001666  mov     ebx, eax
0x180001668  test    eax, eax
0x18000166a  jle     short loc_180001675
0x18000166c  movzx   ebx, ax
0x18000166f  or      ebx, 80070000h
0x180001675  mov     [rsp+78h+var_48], ebx
0x180001679  jmp     short loc_180001699
0x18000167b  mov     ebx, 8000FFFFh
0x180001680  mov     [rsp+78h+var_48], ebx
0x180001684  mov     r14d, 3
0x18000168a  mov     edi, [rsp+78h+arg_0]
0x180001691  mov     r15d, [rsp+78h+arg_8]
0x180001699  mov     [rsp+78h+arg_10], 1
0x1800016a4  test    ebx, ebx
0x1800016a6  js      loc_18000185F
0x1800016ac  mov     cs:qword_18007CF00, 0Bh
0x1800016b7  mov     cs:qword_18007CEF0, 0
0x1800016c2  or      cs:dword_18007CED8, 1
0x1800016c9  mov     edi, 1
0x1800016ce  mov     [rsp+78h+arg_0], edi
0x1800016d5  mov     ecx, cs:dword_180079F7C
0x1800016db  shr     ecx, 1
0x1800016dd  inc     ecx
0x1800016df  lea     r8d, [rdi+3]
0x1800016e3  movzx   edx, r8w
0x1800016e7  mov     r10d, 0FFFFh
0x1800016ed  movzx   eax, dx
0x1800016f0  mov     r9d, [rsp+rax*4+78h+var_40]
0x1800016f5  cmp     r9d, ecx
0x1800016f8  jb      short loc_180001702
0x1800016fa  add     dx, r10w
0x1800016fe  jnz     short loc_1800016ED
0x180001700  jmp     short loc_180001705
0x180001702  mov     ecx, r9d
0x180001705  cmp     ecx, 0Bh
0x180001708  cmovb   ecx, r14d
0x18000170c  mov     dword ptr cs:qword_18007CC80, ecx
0x180001712  mov     dword ptr cs:qword_18007CC80+4, 0
0x18000171c  mov     cs:qword_18007CC70, 0
0x180001727  or      cs:dword_18007CC58, edi
0x18000172d  mov     ecx, 5
0x180001732  movzx   eax, r8w
0x180001736  mov     edx, [rsp+rax*4+78h+var_40]
0x18000173a  cmp     edx, ecx
0x18000173c  jb      short loc_180001746
0x18000173e  add     r8w, r10w
0x180001742  jnz     short loc_180001732
0x180001744  jmp     short loc_180001748
0x180001746  mov     ecx, edx
0x180001748  cmp     ecx, 0Bh
0x18000174b  cmovb   ecx, r14d
0x18000174f  mov     dword ptr cs:qword_18007CDC0, ecx
0x180001755  mov     dword ptr cs:qword_18007CDC0+4, 0
0x18000175f  mov     cs:qword_18007CDB0, 0
0x18000176a  or      cs:dword_18007CD98, edi
0x180001770  mov     r8d, 0AFC8h
0x180001776  mov     cs:dword_18007CFFC, r8d
0x18000177d  mov     r9d, edi
0x180001780  lea     rdx, ?g_ScriptManager@@3VCScriptManager@@A; CScriptManager g_ScriptManager
0x180001787  lea     rcx, ?ScriptKillerSchedulerCallback@CScriptManager@@CAXPEAX@Z; CScriptManager::ScriptKillerSchedulerCallback(void *)
0x18000178e  call    cs:__imp_?ScheduleWorkItem@@YAKP6AXPEAX@Z0KH@Z; ScheduleWorkItem(void (*)(void *),void *,ulong,int)
0x180001794  mov     cs:dword_18007CFF8, eax
0x18000179a  test    eax, eax
0x18000179c  jnz     short loc_1800017AC
0x18000179e  mov     ebx, 80004005h
0x1800017a3  mov     [rsp+78h+var_48], ebx
0x1800017a7  jmp     loc_18000185F
0x1800017ac  mov     [rsp+78h+arg_18], 0
0x1800017b8  lea     rax, [rsp+78h+arg_18]
0x1800017c0  mov     [rsp+78h+ppv], rax; ppv
0x1800017c5  lea     r9, IID_IActiveScript; riid
0x1800017cc  xor     edx, edx; pUnkOuter
0x1800017ce  mov     r8d, edi; dwClsContext
0x1800017d1  lea     rcx, rclsid; rclsid
0x1800017d8  call    cs:__imp_CoCreateInstance
0x1800017de  mov     ebx, eax
0x1800017e0  mov     [rsp+78h+var_48], eax
0x1800017e4  test    eax, eax
0x1800017e6  js      short loc_18000185F
0x1800017e8  mov     rcx, [rsp+78h+arg_18]
0x1800017f0  mov     rax, [rcx]
0x1800017f3  lea     r8, ?g_pWrapTypelibs@@3PEAUIWrapTypeLibs@@EA; IWrapTypeLibs * g_pWrapTypelibs
0x1800017fa  lea     rdx, IID_IWrapTypeLibs
0x180001801  mov     rax, [rax]
0x180001804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001809  mov     ebx, eax
0x18000180b  mov     [rsp+78h+var_48], eax
0x18000180f  jmp     short loc_18000184C
0x180001811  mov     ebx, eax
0x180001813  lea     rax, aCscriptmanager_0; "CScriptManager::Init()"
0x18000181a  mov     [rsp+78h+var_50], rax
0x18000181f  lea     rax, aIactivescriptQ; "IActiveScript::QueryInterface()"
0x180001826  mov     [rsp+78h+ppv], rax
0x18000182b  mov     r9d, ebx
0x18000182e  xor     edx, edx; struct CHitObj *
0x180001830  mov     ecx, 3F4h; unsigned int
0x180001835  lea     r8d, [rdx+1]; int
0x180001839  call    ?HandleErrorMissingFilename@@YAXIPEAVCHitObj@@HZZ; HandleErrorMissingFilename(uint,CHitObj *,int,...)
0x18000183e  mov     [rsp+78h+var_48], ebx
0x180001842  mov     edi, [rsp+78h+arg_0]
0x180001849  mov     r15d, edi
0x18000184c  test    ebx, ebx
0x18000184e  js      short loc_18000185F
0x180001850  mov     cs:byte_18007CC48, 1
0x180001857  jmp     loc_18000192D
0x18000185c  xor     r15d, r15d
0x18000185f  mov     ecx, cs:dword_18007CFF8
0x180001865  test    ecx, ecx
0x180001867  jz      short loc_18000186F
0x180001869  call    cs:__imp_?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x18000186f  test    r15d, r15d
0x180001872  jz      short loc_180001881
0x180001874  lea     rcx, CriticalSection; lpCriticalSection
0x18000187b  call    cs:__imp_DeleteCriticalSection
0x180001881  cmp     [rsp+78h+arg_10], 0
0x180001889  jz      short loc_180001898
0x18000188b  lea     rcx, stru_18007CD68; lpCriticalSection
0x180001892  call    cs:__imp_DeleteCriticalSection
0x180001898  test    edi, edi
0x18000189a  jz      short loc_1800018D9
0x18000189c  lea     rcx, stru_18007CEA8; lpCriticalSection
0x1800018a3  call    cs:__imp_DeleteCriticalSection
0x1800018a9  test    edi, edi
0x1800018ab  jz      short loc_1800018D9
0x1800018ad  lea     rcx, qword_18007CED0; this
0x1800018b4  call    ?UnInit@CHashTable@@QEAAJXZ; CHashTable::UnInit(void)
0x1800018b9  test    edi, edi
0x1800018bb  jz      short loc_1800018D9
0x1800018bd  lea     rcx, qword_18007CC50; this
0x1800018c4  call    ?UnInit@CHashTable@@QEAAJXZ; CHashTable::UnInit(void)
0x1800018c9  test    edi, edi
0x1800018cb  jz      short loc_1800018D9
0x1800018cd  lea     rcx, qword_18007CD90; this
0x1800018d4  call    ?UnInit@CHashTable@@QEAAJXZ; CHashTable::UnInit(void)
0x1800018d9  mov     rcx, cs:?g_pWrapTypelibs@@3PEAUIWrapTypeLibs@@EA; IWrapTypeLibs * g_pWrapTypelibs
0x1800018e0  test    rcx, rcx
0x1800018e3  jz      short loc_18000192D
0x1800018e5  mov     rax, [rcx]
0x1800018e8  mov     rax, [rax+10h]
0x1800018ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018f1  jmp     short loc_180001922
0x1800018f3  mov     r9d, eax
0x1800018f6  lea     rax, aCscriptmanager_0; "CScriptManager::Init()"
0x1800018fd  mov     [rsp+78h+var_50], rax
0x180001902  lea     rax, aIwraptypelibsR; "IWrapTypeLibs::Release()"
0x180001909  mov     [rsp+78h+ppv], rax
0x18000190e  xor     edx, edx; struct CHitObj *
0x180001910  mov     ecx, 3F4h; unsigned int
0x180001915  lea     r8d, [rdx+1]; int
0x180001919  call    ?HandleErrorMissingFilename@@YAXIPEAVCHitObj@@HZZ; HandleErrorMissingFilename(uint,CHitObj *,int,...)
0x18000191e  mov     ebx, [rsp+78h+var_48]
0x180001922  mov     cs:?g_pWrapTypelibs@@3PEAUIWrapTypeLibs@@EA, 0; IWrapTypeLibs * g_pWrapTypelibs
0x18000192d  mov     rcx, [rsp+78h+arg_18]
0x180001935  test    rcx, rcx
0x180001938  jz      short loc_180001977
0x18000193a  mov     rax, [rcx]
0x18000193d  mov     rax, [rax+10h]
0x180001941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001946  jmp     short loc_180001977
0x180001948  mov     r9d, eax
0x18000194b  lea     rax, aCscriptmanager_0; "CScriptManager::Init()"
0x180001952  mov     [rsp+78h+var_50], rax
0x180001957  lea     rax, aIactivescriptR; "IActiveScript::Release()"
0x18000195e  mov     [rsp+78h+ppv], rax
0x180001963  xor     edx, edx; struct CHitObj *
0x180001965  mov     ecx, 3F4h; unsigned int
0x18000196a  lea     r8d, [rdx+1]; int
0x18000196e  call    ?HandleErrorMissingFilename@@YAXIPEAVCHitObj@@HZZ; HandleErrorMissingFilename(uint,CHitObj *,int,...)
0x180001973  mov     ebx, [rsp+78h+var_48]
0x180001977  mov     eax, ebx
0x180001979  add     rsp, 58h
0x18000197d  pop     r15
0x18000197f  pop     r14
0x180001981  pop     rdi
0x180001982  pop     rbx
0x180001983  retn
```
