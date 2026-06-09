# ZTraceContext::Init(ushort const *,char const *,ZTraceLevel)

- ea: `0x18000258c`
- end: `0x1800027ce`
- name: `?Init@ZTraceContext@@QEAAXPEBGPEBDW4ZTraceLevel@@@Z`
- size: `578`
- prototype: `void __fastcall(__int64, _WORD *, const char *, DWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003300`
- `0x1800035c0`

## callees

- `0x180001754`
- `0x1800022be`
- `0x1800024bc`
- `0x18000258c`
- `0x1800036f8`
- `0x1800039d4`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002776`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002776`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002722`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002722`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002705`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002705`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800026c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800026c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027c7`

## pseudocode

```c
void __fastcall ZTraceContext::Init(__int64 a1, _WORD *a2, const char *a3, DWORD a4)
{
  char *v6; // rsi
  _WORD *v7; // rdi
  int v8; // eax
  bool v9; // sf
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // ecx
  ZTracer *v13; // rdi
  const char *v14; // rbx
  DWORD cbData; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  __int64 Data; // [rsp+80h] [rbp+30h] BYREF
  DWORD Type; // [rsp+98h] [rbp+48h] BYREF

  Type = a4;
  Data = a1;
  EnterCriticalSection(&g_ZTraceContext);
  if ( !dword_1800072B0 )
  {
    if ( qword_1800072B8 )
      (**(void (__fastcall ***)(ZTracer *, __int64))qword_1800072B8)(qword_1800072B8, 1);
    v6 = (char *)operator new(0xE8u);
    *(_QWORD *)v6 = &ZTracer::`vftable';
    v7 = v6 + 28;
    *((_DWORD *)v6 + 6) = 0;
    *(_OWORD *)(v6 + 8) = MICROSOFT_WINDOWS_ZTRACEMAPS;
    memset_0(v6 + 28, 0, 0xC8u);
    qword_1800072B8 = (ZTracer *)v6;
    v8 = McGenEventRegister_EventRegister(v6 + 8);
    v9 = v8 < 0;
    if ( v8 > 0 )
      v9 = 1;
    if ( !v9 )
    {
      v10 = 2147483646;
      v11 = 100;
      while ( v10 )
      {
        if ( *a2 )
        {
          *v7++ = *a2++;
          --v10;
          if ( --v11 )
            continue;
        }
        if ( !v11 )
        {
          *(v7 - 1) = 0;
          goto LABEL_15;
        }
        break;
      }
      *v7 = 0;
      if ( (*(int (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6) >= 0 )
        *((_DWORD *)v6 + 6) = 1;
    }
  }
LABEL_15:
  ++dword_1800072B0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Zune", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    LODWORD(Data) = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"ZTraceDebug", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      s_fShouldSpewDebug = Data;
    RegCloseKey(hKey);
  }
  v13 = qword_1800072B8;
  if ( qword_1800072B8 )
  {
    v14 = ":";
    if ( *a3 )
      v14 = a3;
    if ( *((_DWORD *)qword_1800072B8 + 6) && (Microsoft_Windows_ZTraceMapsEnableBits & 0x20) != 0 )
      McTemplateU0sspd_EventWriteTransfer(v12, (unsigned int)Noisy_Log, 0, (_DWORD)v14, 0, 0);
    if ( s_fShouldSpewDebug && IsDebuggerPresent() )
      ZTracer::DebugMsg(v13, "%s:%s@%p: %s (%d)", "      ", 0, 0, v14, 0);
  }
  LeaveCriticalSection(&g_ZTraceContext);
}

```

## disassembly

```asm
0x18000258c  mov     rax, rsp
0x18000258f  mov     [rax+10h], rbx
0x180002593  mov     [rax+18h], rsi
0x180002597  mov     [rax+20h], r9d
0x18000259b  mov     [rax+8], rcx
0x18000259f  push    rbp
0x1800025a0  push    rdi
0x1800025a1  push    r12
0x1800025a3  push    r14
0x1800025a5  push    r15
0x1800025a7  mov     rbp, rsp
0x1800025aa  sub     rsp, 50h
0x1800025ae  lea     rcx, ?g_ZTraceContext@@3VZTraceContext@@A; lpCriticalSection
0x1800025b5  mov     r15, r8
0x1800025b8  mov     r14, rdx
0x1800025bb  call    cs:__imp_EnterCriticalSection
0x1800025c1  xor     r12d, r12d
0x1800025c4  cmp     cs:dword_1800072B0, r12d
0x1800025cb  jnz     loc_18000269E
0x1800025d1  mov     rcx, cs:qword_1800072B8
0x1800025d8  test    rcx, rcx
0x1800025db  jz      short loc_1800025ED
0x1800025dd  mov     rax, [rcx]
0x1800025e0  lea     edx, [r12+1]
0x1800025e5  mov     rax, [rax]
0x1800025e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ed  mov     ecx, 0E8h; Size
0x1800025f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800025f7  mov     rsi, rax
0x1800025fa  xor     edx, edx; Val
0x1800025fc  lea     rax, ??_7ZTracer@@6B@; const ZTracer::`vftable'
0x180002603  mov     r8d, 0C8h; Size
0x180002609  mov     [rsi], rax
0x18000260c  lea     rdi, [rsi+1Ch]
0x180002610  movups  xmm0, cs:MICROSOFT_WINDOWS_ZTRACEMAPS
0x180002617  mov     rcx, rdi; void *
0x18000261a  mov     [rsi+18h], r12d
0x18000261e  movdqu  xmmword ptr [rsi+8], xmm0
0x180002623  call    memset_0
0x180002628  lea     rcx, [rsi+8]
0x18000262c  mov     cs:qword_1800072B8, rsi
0x180002633  call    McGenEventRegister_EventRegister
0x180002638  test    eax, eax
0x18000263a  jle     short loc_180002646
0x18000263c  movzx   eax, ax
0x18000263f  or      eax, 80070000h
0x180002644  test    eax, eax
0x180002646  js      short loc_18000269E
0x180002648  mov     ecx, 7FFFFFFEh
0x18000264d  mov     eax, 64h ; 'd'
0x180002652  test    rcx, rcx
0x180002655  jz      short loc_180002680
0x180002657  movzx   edx, word ptr [r14]
0x18000265b  test    dx, dx
0x18000265e  jz      short loc_180002674
0x180002660  mov     [rdi], dx
0x180002663  add     r14, 2
0x180002667  add     rdi, 2
0x18000266b  dec     rcx
0x18000266e  sub     rax, 1
0x180002672  jnz     short loc_180002652
0x180002674  test    rax, rax
0x180002677  jnz     short loc_180002680
0x180002679  mov     [rdi-2], r12w
0x18000267e  jmp     short loc_18000269E
0x180002680  mov     [rdi], r12w
0x180002684  mov     rcx, rsi
0x180002687  mov     rax, [rsi]
0x18000268a  mov     rax, [rax+10h]
0x18000268e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002693  test    eax, eax
0x180002695  js      short loc_18000269E
0x180002697  mov     dword ptr [rsi+18h], 1
0x18000269e  inc     cs:dword_1800072B0
0x1800026a4  lea     rax, [rbp+hKey]
0x1800026a8  mov     r9d, 20019h; samDesired
0x1800026ae  mov     [rsp+50h+phkResult], rax; phkResult
0x1800026b3  xor     r8d, r8d; ulOptions
0x1800026b6  mov     [rbp+hKey], r12
0x1800026ba  lea     rdx, SubKey; "Software\\Microsoft\\Zune"
0x1800026c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800026c8  call    cs:__imp_RegOpenKeyExW
0x1800026ce  test    eax, eax
0x1800026d0  jnz     short loc_180002728
0x1800026d2  mov     rcx, [rbp+hKey]; hKey
0x1800026d6  lea     rax, [rbp+cbData]
0x1800026da  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800026df  lea     r9, [rbp+Type]; lpType
0x1800026e3  lea     rax, [rbp+Data]
0x1800026e7  mov     [rbp+Type], r12d
0x1800026eb  xor     r8d, r8d; lpReserved
0x1800026ee  mov     [rsp+50h+phkResult], rax; lpData
0x1800026f3  lea     rdx, ValueName; "ZTraceDebug"
0x1800026fa  mov     dword ptr [rbp+Data], r12d
0x1800026fe  mov     [rbp+cbData], 4
0x180002705  call    cs:__imp_RegQueryValueExW
0x18000270b  test    eax, eax
0x18000270d  jnz     short loc_18000271E
0x18000270f  cmp     [rbp+Type], 4
0x180002713  jnz     short loc_18000271E
0x180002715  mov     eax, dword ptr [rbp+Data]
0x180002718  mov     cs:?s_fShouldSpewDebug@@3HA, eax; int s_fShouldSpewDebug
0x18000271e  mov     rcx, [rbp+hKey]; hKey
0x180002722  call    cs:__imp_RegCloseKey
0x180002728  mov     rdi, cs:qword_1800072B8
0x18000272f  test    rdi, rdi
0x180002732  jz      short loc_1800027A8
0x180002734  cmp     [r15], r12b
0x180002737  lea     rbx, asc_180005594; ":"
0x18000273e  cmovnz  rbx, r15
0x180002742  cmp     [rdi+18h], r12d
0x180002746  jz      short loc_18000276D
0x180002748  test    cs:Microsoft_Windows_ZTraceMapsEnableBits, 20h
0x18000274f  jz      short loc_18000276D
0x180002751  mov     dword ptr [rsp+50h+lpcbData], r12d
0x180002756  lea     rdx, _Noisy_Log
0x18000275d  mov     r9, rbx
0x180002760  mov     [rsp+50h+phkResult], r12
0x180002765  xor     r8d, r8d
0x180002768  call    McTemplateU0sspd_EventWriteTransfer
0x18000276d  cmp     cs:?s_fShouldSpewDebug@@3HA, r12d; int s_fShouldSpewDebug
0x180002774  jz      short loc_1800027A8
0x180002776  call    cs:__imp_IsDebuggerPresent
0x18000277c  test    eax, eax
0x18000277e  jz      short loc_1800027A8
0x180002780  mov     [rsp+50h+var_20], r12d
0x180002785  lea     r8, asc_1800055A8; "      "
0x18000278c  mov     [rsp+50h+lpcbData], rbx
0x180002791  lea     rdx, aSSPSD; "%s:%s@%p: %s (%d)"
0x180002798  xor     r9d, r9d
0x18000279b  mov     [rsp+50h+phkResult], r12
0x1800027a0  mov     rcx, rdi; this
0x1800027a3  call    ?DebugMsg@ZTracer@@QEAAXPEBDZZ; ZTracer::DebugMsg(char const *,...)
0x1800027a8  lea     rcx, ?g_ZTraceContext@@3VZTraceContext@@A; ZTraceContext g_ZTraceContext
0x1800027af  lea     r11, [rsp+50h+var_s0]
0x1800027b4  mov     rbx, [r11+38h]
0x1800027b8  mov     rsi, [r11+40h]
0x1800027bc  mov     rsp, r11
0x1800027bf  pop     r15
0x1800027c1  pop     r14
0x1800027c3  pop     r12
0x1800027c5  pop     rdi
0x1800027c6  pop     rbp
0x1800027c7  jmp     cs:__imp_LeaveCriticalSection
```
