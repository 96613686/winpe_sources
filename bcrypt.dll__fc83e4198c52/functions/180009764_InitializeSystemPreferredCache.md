# InitializeSystemPreferredCache

- ea: `0x180009764`
- end: `0x180009975`
- name: `InitializeSystemPreferredCache`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a768`

## callees

- `0x180005060`
- `0x180007a7c`
- `0x180009430`
- `0x180009764`
- `0x18000997c`
- `0x18001267c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000977d`
- `ntdll!RtlAllocateHeap` at `0x1800097fc`
- `ntdll!RtlAllocateHeap` at `0x18000977d`
- `ntdll!RtlAllocateHeap` at `0x1800097fc`
- `ntdll!RtlInitializeResource` at `0x18000979c`
- `ntdll!RtlInitializeResource` at `0x18000979c`
- `ntdll!RtlInitializeCriticalSection` at `0x18000981b`
- `ntdll!RtlInitializeCriticalSection` at `0x18000981b`

## string_xrefs

- `0x1800097cc`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x180009864`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x1800098b7`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`
- `0x18000992c`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 InitializeSystemPreferredCache()
{
  struct _RTL_RESOURCE *Heap; // rax
  int v1; // edx
  int v2; // r8d
  struct _RTL_CRITICAL_SECTION *v3; // rax
  int v4; // edx
  int v5; // ebx
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  _QWORD *v10; // rcx
  char v11; // [rsp+30h] [rbp-18h]

  Heap = (struct _RTL_RESOURCE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x60u);
  g_pCachedRngRWLock = Heap;
  if ( !Heap )
  {
    v5 = -1073741801;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v11 = 14;
LABEL_19:
    WPP_SF_sDsd(
      v10[2],
      v1,
      v2,
      (unsigned int)"Status",
      23,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
      v11);
    goto LABEL_8;
  }
  RtlInitializeResource(Heap);
  v3 = (struct _RTL_CRITICAL_SECTION *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x28u);
  CriticalSection = v3;
  if ( !v3 )
  {
    v5 = -1073741801;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v11 = 34;
    goto LABEL_19;
  }
  v5 = RtlInitializeCriticalSection(v3);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        v6,
        (unsigned int)"Status",
        v5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
        41);
    MSCryptFree(CriticalSection);
    CriticalSection = 0;
  }
  else
  {
    v5 = BcpRegisterConfigChangeNotifyNoLogging(&qword_180024AF0);
    if ( v5 >= 0 )
    {
      dword_180024AA4 = 1;
      v5 = 0;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v8,
        (unsigned int)"Status",
        v5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
        52);
    }
  }
LABEL_8:
  if ( v5 < 0 )
    CleanupSystemPreferredCache();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009764  push    rbx
0x180009766  sub     rsp, 40h
0x18000976a  mov     rcx, gs:60h
0x180009773  xor     edx, edx; Flags
0x180009775  lea     r8d, [rdx+60h]; Size
0x180009779  mov     rcx, [rcx+30h]; HeapHandle
0x18000977d  call    cs:__imp_RtlAllocateHeap
0x180009784  nop     dword ptr [rax+rax+00h]
0x180009789  mov     cs:g_pCachedRngRWLock, rax
0x180009790  test    rax, rax
0x180009793  jz      loc_1800098FE
0x180009799  mov     rcx, rax; Resource
0x18000979c  call    cs:__imp_RtlInitializeResource
0x1800097a3  nop     dword ptr [rax+rax+00h]
0x1800097a8  jmp     short loc_1800097E9
0x1800097aa  mov     rcx, cs:g_pCachedRngRWLock
0x1800097b1  call    MSCryptFree
0x1800097b6  mov     cs:g_pCachedRngRWLock, 0
0x1800097c1  mov     ebx, 0C00000E5h
0x1800097c6  mov     r9d, 119h
0x1800097cc  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800097d3  lea     rdx, aStatus; "Status"
0x1800097da  mov     ecx, 0C00000E5h
0x1800097df  call    DebugTraceError
0x1800097e4  jmp     loc_180009884
0x1800097e9  mov     rcx, gs:60h
0x1800097f2  xor     edx, edx; Flags
0x1800097f4  lea     r8d, [rdx+28h]; Size
0x1800097f8  mov     rcx, [rcx+30h]; HeapHandle
0x1800097fc  call    cs:__imp_RtlAllocateHeap
0x180009803  nop     dword ptr [rax+rax+00h]
0x180009808  mov     cs:CriticalSection, rax
0x18000980f  test    rax, rax
0x180009812  jz      loc_180009945
0x180009818  mov     rcx, rax; CriticalSection
0x18000981b  call    cs:__imp_RtlInitializeCriticalSection
0x180009822  nop     dword ptr [rax+rax+00h]
0x180009827  mov     ebx, eax
0x180009829  test    eax, eax
0x18000982b  js      short loc_180009896
0x18000982d  lea     rcx, qword_180024AF0
0x180009834  call    BcpRegisterConfigChangeNotifyNoLogging
0x180009839  mov     ebx, eax
0x18000983b  test    eax, eax
0x18000983d  jns     loc_1800098F0
0x180009843  lea     rax, WPP_GLOBAL_Control
0x18000984a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009851  cmp     rcx, rax
0x180009854  jz      short loc_180009884
0x180009856  test    byte ptr [rcx+1Ch], 1
0x18000985a  jz      short loc_180009884
0x18000985c  mov     dword ptr [rsp+48h+var_18], 134h
0x180009864  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000986b  mov     [rsp+48h+var_20], rax
0x180009870  mov     [rsp+48h+var_28], ebx
0x180009874  lea     r9, aStatus; "Status"
0x18000987b  mov     rcx, [rcx+10h]
0x18000987f  call    WPP_SF_sDsd
0x180009884  test    ebx, ebx
0x180009886  jns     short loc_18000988D
0x180009888  call    CleanupSystemPreferredCache
0x18000988d  mov     eax, ebx
0x18000988f  add     rsp, 40h
0x180009893  pop     rbx
0x180009894  retn
0x180009896  lea     rax, WPP_GLOBAL_Control
0x18000989d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098a4  cmp     rcx, rax
0x1800098a7  jz      short loc_1800098D7
0x1800098a9  test    byte ptr [rcx+1Ch], 1
0x1800098ad  jz      short loc_1800098D7
0x1800098af  mov     dword ptr [rsp+48h+var_18], 129h
0x1800098b7  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800098be  mov     [rsp+48h+var_20], rax
0x1800098c3  mov     [rsp+48h+var_28], ebx
0x1800098c7  lea     r9, aStatus; "Status"
0x1800098ce  mov     rcx, [rcx+10h]
0x1800098d2  call    WPP_SF_sDsd
0x1800098d7  mov     rcx, cs:CriticalSection
0x1800098de  call    MSCryptFree
0x1800098e3  mov     cs:CriticalSection, 0
0x1800098ee  jmp     short loc_180009884
0x1800098f0  mov     cs:dword_180024AA4, 1
0x1800098fa  xor     ebx, ebx
0x1800098fc  jmp     short loc_180009884
0x1800098fe  mov     ebx, 0C0000017h
0x180009903  lea     rax, WPP_GLOBAL_Control
0x18000990a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009911  cmp     rcx, rax
0x180009914  jz      loc_180009884
0x18000991a  test    byte ptr [rcx+1Ch], 1
0x18000991e  jz      loc_180009884
0x180009924  mov     dword ptr [rsp+48h+var_18], 10Eh
0x18000992c  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009933  mov     [rsp+48h+var_20], rax
0x180009938  mov     [rsp+48h+var_28], 0C0000017h
0x180009940  jmp     loc_180009874
0x180009945  mov     ebx, 0C0000017h
0x18000994a  lea     rax, WPP_GLOBAL_Control
0x180009951  mov     rcx, cs:WPP_GLOBAL_Control
0x180009958  cmp     rcx, rax
0x18000995b  jz      loc_180009884
0x180009961  test    byte ptr [rcx+1Ch], 1
0x180009965  jz      loc_180009884
0x18000996b  mov     dword ptr [rsp+48h+var_18], 122h
0x180009973  jmp     short loc_18000992C
```
