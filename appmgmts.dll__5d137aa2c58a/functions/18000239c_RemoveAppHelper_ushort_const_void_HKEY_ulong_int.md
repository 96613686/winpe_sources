# RemoveAppHelper(ushort const *,void *,HKEY__ *,ulong,int *)

- ea: `0x18000239c`
- end: `0x180002780`
- name: `?RemoveAppHelper@@YAKPEBGPEAXPEAUHKEY__@@KPEAH@Z`
- size: `996`
- prototype: `__int64 __fastcall(LPCWSTR lpString2, void *, HKEY, unsigned int, BYTE *lpData)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180002b90`

## callees

- `0x18000239c`
- `0x180005294`
- `0x180007de4`
- `0x180008fe4`
- `0x18000a2cc`
- `0x18000a7c0`
- `0x18000b16c`
- `0x18000b648`
- `0x18000d11c`
- `0x18000d5fc`
- `0x18000df00`
- `0x18000e4f0`
- `0x18000e69c`
- `0x18000e744`
- `0x180010ae8`
- `0x180011610`
- `0x180012690`
- `0x18001b1a0`
- `0x1800295b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000251d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000251d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000272f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000272f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002687`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002687`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800024f4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800024f4`
- `USERENV!LeaveCriticalPolicySection` at `0x1800026f5`
- `USERENV!LeaveCriticalPolicySection` at `0x1800026f5`
- `KERNEL32!lstrcmpiW` at `0x18000254d`
- `KERNEL32!lstrcmpiW` at `0x18000254d`

## pseudocode

```c
__int64 __fastcall RemoveAppHelper(LPCWSTR lpString2, void *a2, HKEY a3, unsigned int a4, BYTE *lpData)
{
  struct CAppInfo *v9; // r15
  unsigned int PolicyList; // ebx
  unsigned int OrderedLocalAppList; // edi
  DWORD LastError; // eax
  CAppInfo *v14; // rsi
  struct CAppInfo *i; // rbx
  int v16; // ebx
  unsigned int v17; // eax
  unsigned int v18[4]; // [rsp+50h] [rbp-B0h] BYREF
  IWbemServices *v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v20; // [rsp+70h] [rbp-90h]
  __int128 v21; // [rsp+80h] [rbp-80h]
  __int64 v22; // [rsp+90h] [rbp-70h] BYREF
  struct CAppInfo *v23; // [rsp+98h] [rbp-68h]
  __int128 v24; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+B0h] [rbp-50h]
  _BYTE *v26; // [rsp+B8h] [rbp-48h]
  int v27; // [rsp+C0h] [rbp-40h]
  int v28; // [rsp+C4h] [rbp-3Ch]
  _BYTE v29[264]; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE hToken; // [rsp+1D8h] [rbp+D8h]
  HKEY hKey; // [rsp+1F0h] [rbp+F0h]
  int v32; // [rsp+1F8h] [rbp+F8h]
  _BYTE v33[16]; // [rsp+228h] [rbp+128h] BYREF
  _BYTE v34[32]; // [rsp+238h] [rbp+138h] BYREF
  int v35; // [rsp+258h] [rbp+158h]
  int v36; // [rsp+25Ch] [rbp+15Ch]
  HANDLE hSection; // [rsp+278h] [rbp+178h]
  _BYTE v38[208]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v18[0] = 14;
  v9 = 0;
  *(_DWORD *)lpData = 0;
  CRsopAppContext::CRsopAppContext((CRsopAppContext *)v38, 4u, 0, 0);
  CManagedAppProcessor::CManagedAppProcessor(
    (CManagedAppProcessor *)v29,
    a2 == 0,
    a2,
    a3,
    0,
    0,
    0,
    (struct CRsopAppContext *)v38,
    v18);
  PolicyList = v18[0];
  if ( v18[0] )
    goto LABEL_4;
  v24 = 0;
  v23 = (struct CAppInfo *)&v22;
  v22 = (__int64)&v22;
  v19[1] = 0;
  v20 = 0;
  v21 = 0;
  v19[0] = (IWbemServices *)&CAppList::`vftable';
  v25 = 0;
  v26 = v34;
  v27 = -2147467259;
  v28 = 0;
  PolicyList = CManagedAppProcessor::LoadPolicyList((CManagedAppProcessor *)v29);
  if ( PolicyList )
  {
    CAppList::~CAppList((CAppList *)v19);
LABEL_4:
    CManagedAppProcessor::~CManagedAppProcessor((CManagedAppProcessor *)v29);
    CRsopAppContext::~CRsopAppContext((CRsopAppContext *)v38);
    return PolicyList;
  }
  OrderedLocalAppList = CManagedAppProcessor::GetOrderedLocalAppList(
                          (CManagedAppProcessor *)v29,
                          (struct CAppList *)v19);
  if ( !OrderedLocalAppList )
  {
    if ( v36 == 1 || !v32 || ImpersonateLoggedOnUser(hToken) )
    {
      OrderedLocalAppList = 0;
    }
    else
    {
      if ( *(_DWORD *)&gDebugLevel )
      {
        LastError = GetLastError();
        _DebugMsg(OrderedLocalAppList + 2, 0xBC4u, LastError);
      }
      OrderedLocalAppList = GetLastError();
    }
    if ( !OrderedLocalAppList )
    {
      v14 = 0;
      *((_QWORD *)&v24 + 1) = v24;
      for ( i = v23; ; i = *(struct CAppInfo **)(v24 + 8) )
      {
        *(_QWORD *)&v24 = i;
        if ( i == (struct CAppInfo *)&v22 )
          i = 0;
        if ( !i )
          break;
        if ( !lstrcmpiW(*((LPCWSTR *)i + 10), lpString2) && (*((_BYTE *)i + 224) & 3) != 0 )
        {
          v9 = i;
          *(_DWORD *)lpData = 1;
          if ( (*((_BYTE *)i + 224) & 2) != 0 )
          {
            if ( !a4 )
            {
              if ( *(_DWORD *)&gDebugLevel )
                _DebugMsg(4, 0xBF5u, *((_QWORD *)i + 5), lpString2);
              CAppInfo::Unassign(i, 0x125u, 1);
            }
            CAppInfo::SetAction(i, 4, 4);
          }
          else
          {
            if ( !a4 && *(_DWORD *)&gDebugLevel )
              _DebugMsg(4, 0xBF6u, *((_QWORD *)i + 5), lpString2);
            v14 = i;
          }
        }
      }
      if ( a4 && v9 )
        CEvents::Uninstall((CEvents *)v33, a4, v9);
      v16 = 0;
      if ( v14 )
      {
        if ( !a4 )
        {
          v17 = CAppInfo::Assign(v14, 293, 1, 0);
          OrderedLocalAppList = v17;
          if ( v17 )
            CEvents::Assign((CEvents *)v33, v17, v14);
        }
        if ( v35 )
          LOBYTE(v16) = v14 == v9;
      }
      if ( v36 != 1 && v32 )
        RevertToSelf();
      CRsopContext::GetExclusiveLoggingAccess((CRsopContext *)v34, a2 == 0);
      if ( v35 )
      {
        CAppList::WriteLog((CAppList *)v19, 1u);
        if ( v16 )
        {
          CAppList::MarkRSOPEntryAsRemoved(v19, v14, 0);
        }
        else if ( v14 )
        {
          CAppList::WriteAppToRsopLog((CAppList *)v19, v14);
        }
      }
      if ( hSection )
      {
        LeaveCriticalPolicySection(hSection);
        hSection = 0;
      }
      if ( *(_DWORD *)lpData && a2 )
      {
        OrderedLocalAppList = RegSetValueExW(hKey, L"FullPolicy", 0, 4u, lpData, 4u);
        if ( !OrderedLocalAppList )
          OrderedLocalAppList = ForceSynchronousRefresh(hToken);
      }
    }
  }
  CAppList::~CAppList((CAppList *)v19);
  CManagedAppProcessor::~CManagedAppProcessor((CManagedAppProcessor *)v29);
  CRsopAppContext::~CRsopAppContext((CRsopAppContext *)v38);
  return OrderedLocalAppList;
}

```

## disassembly

```asm
0x18000239c  mov     [rsp-8+arg_8], rdx
0x1800023a1  push    rbp
0x1800023a2  push    rbx
0x1800023a3  push    rsi
0x1800023a4  push    rdi
0x1800023a5  push    r12
0x1800023a7  push    r13
0x1800023a9  push    r14
0x1800023ab  push    r15
0x1800023ad  lea     rbp, [rsp-258h]
0x1800023b5  sub     rsp, 358h
0x1800023bc  mov     r14d, r9d
0x1800023bf  mov     rbx, r8
0x1800023c2  mov     rdi, rdx
0x1800023c5  mov     r12, rcx
0x1800023c8  mov     [rsp+390h+var_340], 0Eh
0x1800023d0  xor     r15d, r15d
0x1800023d3  mov     r13, [rbp+290h+arg_20]
0x1800023da  mov     [r13+0], r15d
0x1800023de  xor     r9d, r9d; struct _APPKEY *
0x1800023e1  xor     r8d, r8d; void *
0x1800023e4  lea     edx, [r15+4]; unsigned int
0x1800023e8  lea     rcx, [rbp+290h+var_D0]; this
0x1800023ef  call    ??0CRsopAppContext@@QEAA@KPEAXPEAU_APPKEY@@@Z; CRsopAppContext::CRsopAppContext(ulong,void *,_APPKEY *)
0x1800023f4  nop
0x1800023f5  mov     edx, r15d
0x1800023f8  test    rdi, rdi
0x1800023fb  setz    dl; unsigned int
0x1800023fe  lea     rax, [rsp+390h+var_340]
0x180002403  mov     [rsp+390h+var_350], rax; unsigned int *
0x180002408  lea     rax, [rbp+290h+var_D0]
0x18000240f  mov     [rsp+390h+var_358], rax; struct CRsopAppContext *
0x180002414  mov     [rsp+390h+var_360], r15d; int
0x180002419  mov     [rsp+390h+cbData], r15d; int
0x18000241e  mov     [rsp+390h+lpData], r15; cbData
0x180002423  mov     r9, rbx; HKEY
0x180002426  mov     r8, rdi; void *
0x180002429  lea     rcx, [rbp+290h+var_2C0]; this
0x18000242d  call    ??0CManagedAppProcessor@@QEAA@KPEAXPEAUHKEY__@@P6AKHPEAG@ZHHPEAVCRsopAppContext@@AEAK@Z; CManagedAppProcessor::CManagedAppProcessor(ulong,void *,HKEY__ *,ulong (*)(int,ushort *),int,int,CRsopAppContext *,ulong &)
0x180002432  nop
0x180002433  mov     ebx, [rsp+390h+var_340]
0x180002437  test    ebx, ebx
0x180002439  jnz     short loc_1800024A6
0x18000243b  xorps   xmm0, xmm0
0x18000243e  movdqa  [rbp+290h+var_2F0], xmm0
0x180002443  lea     rax, [rbp+290h+var_300]
0x180002447  mov     [rbp+290h+var_2F8], rax
0x18000244b  lea     rax, [rbp+290h+var_300]
0x18000244f  mov     [rbp+290h+var_300], rax
0x180002453  mov     [rsp+390h+var_328], r15
0x180002458  movdqa  [rsp+390h+var_320], xmm0
0x18000245e  xorps   xmm1, xmm1
0x180002461  movdqa  [rbp+290h+var_310], xmm1
0x180002466  lea     rax, ??_7CAppList@@6B@; const CAppList::`vftable'
0x18000246d  mov     [rsp+390h+var_330], rax
0x180002472  mov     [rbp+290h+var_2E0], r15
0x180002476  lea     rax, [rbp+290h+var_158]
0x18000247d  mov     [rbp+290h+var_2D8], rax
0x180002481  mov     [rbp+290h+var_2D0], 80004005h
0x180002488  mov     [rbp+290h+var_2CC], r15d
0x18000248c  lea     rcx, [rbp+290h+var_2C0]; this
0x180002490  call    ?LoadPolicyList@CManagedAppProcessor@@QEAAKXZ; CManagedAppProcessor::LoadPolicyList(void)
0x180002495  mov     ebx, eax
0x180002497  test    eax, eax
0x180002499  jz      short loc_1800024C3
0x18000249b  lea     rcx, [rsp+390h+var_330]; this
0x1800024a0  call    ??1CAppList@@UEAA@XZ; CAppList::~CAppList(void)
0x1800024a5  nop
0x1800024a6  lea     rcx, [rbp+290h+var_2C0]; this
0x1800024aa  call    ??1CManagedAppProcessor@@QEAA@XZ; CManagedAppProcessor::~CManagedAppProcessor(void)
0x1800024af  nop
0x1800024b0  lea     rcx, [rbp+290h+var_D0]; this
0x1800024b7  call    ??1CRsopAppContext@@QEAA@XZ; CRsopAppContext::~CRsopAppContext(void)
0x1800024bc  mov     eax, ebx
0x1800024be  jmp     loc_18000276C
0x1800024c3  lea     rdx, [rsp+390h+var_330]; struct CAppList *
0x1800024c8  lea     rcx, [rbp+290h+var_2C0]; this
0x1800024cc  call    ?GetOrderedLocalAppList@CManagedAppProcessor@@QEAAKAEAVCAppList@@@Z; CManagedAppProcessor::GetOrderedLocalAppList(CAppList &)
0x1800024d1  mov     edi, eax
0x1800024d3  test    eax, eax
0x1800024d5  jnz     loc_180002749
0x1800024db  cmp     [rbp+290h+var_134], 1
0x1800024e2  jz      short loc_180002527
0x1800024e4  cmp     [rbp+290h+var_198], r15d
0x1800024eb  jz      short loc_180002527
0x1800024ed  mov     rcx, [rbp+290h+hToken]; hToken
0x1800024f4  call    cs:__imp_ImpersonateLoggedOnUser
0x1800024fa  test    eax, eax
0x1800024fc  jnz     short loc_180002527
0x1800024fe  cmp     cs:?gDebugLevel@@3KA, r15d; ulong gDebugLevel
0x180002505  jz      short loc_18000251D
0x180002507  call    cs:__imp_GetLastError
0x18000250d  mov     r8d, eax
0x180002510  mov     edx, 0BC4h; unsigned int
0x180002515  lea     ecx, [rdi+2]; unsigned int
0x180002518  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000251d  call    cs:__imp_GetLastError
0x180002523  mov     edi, eax
0x180002525  jmp     short loc_18000252A
0x180002527  mov     edi, r15d
0x18000252a  test    edi, edi
0x18000252c  jnz     loc_180002749
0x180002532  mov     rsi, r15
0x180002535  mov     rax, qword ptr [rbp+290h+var_2F0]
0x180002539  mov     qword ptr [rbp+290h+var_2F0+8], rax
0x18000253d  mov     rbx, [rbp+290h+var_2F8]
0x180002541  jmp     loc_1800025F5
0x180002546  mov     rdx, r12; lpString2
0x180002549  mov     rcx, [rbx+50h]; lpString1
0x18000254d  call    cs:__imp_lstrcmpiW
0x180002553  test    eax, eax
0x180002555  jnz     loc_1800025ED
0x18000255b  test    byte ptr [rbx+0E0h], 3
0x180002562  jz      loc_1800025ED
0x180002568  mov     r15, rbx
0x18000256b  mov     dword ptr [r13+0], 1
0x180002573  test    byte ptr [rbx+0E0h], 2
0x18000257a  jz      short loc_1800025C7
0x18000257c  test    r14d, r14d
0x18000257f  jnz     short loc_1800025B1
0x180002581  cmp     cs:?gDebugLevel@@3KA, r14d; ulong gDebugLevel
0x180002588  jz      short loc_18000259E
0x18000258a  mov     r9, r12
0x18000258d  mov     r8, [rbx+28h]
0x180002591  mov     edx, 0BF5h; unsigned int
0x180002596  lea     ecx, [rax+4]; unsigned int
0x180002599  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000259e  mov     edx, 125h; unsigned int
0x1800025a3  mov     r8d, 1; int
0x1800025a9  mov     rcx, rbx; this
0x1800025ac  call    ?Unassign@CAppInfo@@QEAAKKH@Z; CAppInfo::Unassign(ulong,int)
0x1800025b1  xor     r9d, r9d
0x1800025b4  lea     eax, [r9+4]
0x1800025b8  mov     r8d, eax
0x1800025bb  mov     edx, eax
0x1800025bd  mov     rcx, rbx
0x1800025c0  call    ?SetAction@CAppInfo@@QEAAXW4APPACTION@@KPEAV1@@Z; CAppInfo::SetAction(APPACTION,ulong,CAppInfo *)
0x1800025c5  jmp     short loc_1800025ED
0x1800025c7  test    r14d, r14d
0x1800025ca  jnz     short loc_1800025EA
0x1800025cc  cmp     cs:?gDebugLevel@@3KA, r14d; ulong gDebugLevel
0x1800025d3  jz      short loc_1800025EA
0x1800025d5  mov     r9, r12
0x1800025d8  mov     r8, [rbx+28h]
0x1800025dc  mov     edx, 0BF6h; unsigned int
0x1800025e1  lea     ecx, [r14+4]; unsigned int
0x1800025e5  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800025ea  mov     rsi, rbx
0x1800025ed  mov     rax, qword ptr [rbp+290h+var_2F0]
0x1800025f1  mov     rbx, [rax+8]
0x1800025f5  xor     eax, eax
0x1800025f7  lea     rcx, [rbp+290h+var_300]
0x1800025fb  mov     qword ptr [rbp+290h+var_2F0], rbx
0x1800025ff  cmp     rbx, rcx
0x180002602  cmovz   rbx, rax
0x180002606  test    rbx, rbx
0x180002609  jnz     loc_180002546
0x18000260f  xor     r12d, r12d
0x180002612  test    r14d, r14d
0x180002615  jz      short loc_18000262E
0x180002617  test    r15, r15
0x18000261a  jz      short loc_18000262E
0x18000261c  mov     r8, r15; struct CAppInfo *
0x18000261f  mov     edx, r14d; unsigned int
0x180002622  lea     rcx, [rbp+290h+var_168]; this
0x180002629  call    ?Uninstall@CEvents@@QEAAXKPEAVCAppInfo@@@Z; CEvents::Uninstall(ulong,CAppInfo *)
0x18000262e  mov     ebx, r12d
0x180002631  test    rsi, rsi
0x180002634  jz      short loc_180002675
0x180002636  test    r14d, r14d
0x180002639  jnz     short loc_180002666
0x18000263b  xor     r9d, r9d; int
0x18000263e  mov     edx, 125h; unsigned int
0x180002643  lea     r8d, [r14+1]; int
0x180002647  mov     rcx, rsi; this
0x18000264a  call    ?Assign@CAppInfo@@QEAAKKHH@Z; CAppInfo::Assign(ulong,int,int)
0x18000264f  mov     edi, eax
0x180002651  test    eax, eax
0x180002653  jz      short loc_180002666
0x180002655  mov     r8, rsi; struct CAppInfo *
0x180002658  mov     edx, eax; unsigned int
0x18000265a  lea     rcx, [rbp+290h+var_168]; this
0x180002661  call    ?Assign@CEvents@@QEAAXKPEAVCAppInfo@@@Z; CEvents::Assign(ulong,CAppInfo *)
0x180002666  cmp     [rbp+290h+var_138], r12d
0x18000266d  jz      short loc_180002675
0x18000266f  cmp     rsi, r15
0x180002672  setz    bl
0x180002675  cmp     [rbp+290h+var_134], 1
0x18000267c  jz      short loc_18000268D
0x18000267e  cmp     [rbp+290h+var_198], r12d
0x180002685  jz      short loc_18000268D
0x180002687  call    cs:__imp_RevertToSelf
0x18000268d  mov     edx, r12d
0x180002690  mov     r14, [rbp+290h+arg_8]
0x180002697  test    r14, r14
0x18000269a  setz    dl; int
0x18000269d  lea     rcx, [rbp+290h+var_158]; this
0x1800026a4  call    ?GetExclusiveLoggingAccess@CRsopContext@@QEAAJH@Z; CRsopContext::GetExclusiveLoggingAccess(int)
0x1800026a9  cmp     [rbp+290h+var_138], r12d
0x1800026b0  jz      short loc_1800026E9
0x1800026b2  mov     edx, 1; unsigned int
0x1800026b7  lea     rcx, [rsp+390h+var_330]; this
0x1800026bc  call    ?WriteLog@CAppList@@QEAAJK@Z; CAppList::WriteLog(ulong)
0x1800026c1  test    ebx, ebx
0x1800026c3  jz      short loc_1800026D7
0x1800026c5  xor     r8d, r8d; int
0x1800026c8  mov     rdx, rsi; struct CAppInfo *
0x1800026cb  lea     rcx, [rsp+390h+var_330]; this
0x1800026d0  call    ?MarkRSOPEntryAsRemoved@CAppList@@QEAAJPEAVCAppInfo@@H@Z; CAppList::MarkRSOPEntryAsRemoved(CAppInfo *,int)
0x1800026d5  jmp     short loc_1800026E9
0x1800026d7  test    rsi, rsi
0x1800026da  jz      short loc_1800026E9
0x1800026dc  mov     rdx, rsi; struct CAppInfo *
0x1800026df  lea     rcx, [rsp+390h+var_330]; this
0x1800026e4  call    ?WriteAppToRsopLog@CAppList@@QEAAJPEAVCAppInfo@@@Z; CAppList::WriteAppToRsopLog(CAppInfo *)
0x1800026e9  mov     rcx, [rbp+290h+hSection]; hSection
0x1800026f0  test    rcx, rcx
0x1800026f3  jz      short loc_180002702
0x1800026f5  call    cs:__imp_LeaveCriticalPolicySection
0x1800026fb  mov     [rbp+290h+hSection], r12
0x180002702  cmp     [r13+0], r12d
0x180002706  jz      short loc_180002749
0x180002708  test    r14, r14
0x18000270b  jz      short loc_180002749
0x18000270d  mov     eax, 4
0x180002712  mov     [rsp+390h+cbData], eax; cbData
0x180002716  mov     [rsp+390h+lpData], r13; lpData
0x18000271b  mov     r9d, eax; dwType
0x18000271e  xor     r8d, r8d; Reserved
0x180002721  lea     rdx, ValueName; "FullPolicy"
0x180002728  mov     rcx, [rbp+290h+hKey]; hKey
0x18000272f  call    cs:__imp_RegSetValueExW
0x180002735  mov     edi, eax
0x180002737  test    eax, eax
0x180002739  jnz     short loc_180002749
0x18000273b  mov     rcx, [rbp+290h+hToken]; void *
0x180002742  call    ?ForceSynchronousRefresh@@YAKPEAX@Z; ForceSynchronousRefresh(void *)
0x180002747  mov     edi, eax
0x180002749  lea     rcx, [rsp+390h+var_330]; this
0x18000274e  call    ??1CAppList@@UEAA@XZ; CAppList::~CAppList(void)
0x180002753  nop
0x180002754  lea     rcx, [rbp+290h+var_2C0]; this
0x180002758  call    ??1CManagedAppProcessor@@QEAA@XZ; CManagedAppProcessor::~CManagedAppProcessor(void)
0x18000275d  nop
0x18000275e  lea     rcx, [rbp+290h+var_D0]; this
0x180002765  call    ??1CRsopAppContext@@QEAA@XZ; CRsopAppContext::~CRsopAppContext(void)
0x18000276a  mov     eax, edi
0x18000276c  add     rsp, 358h
0x180002773  pop     r15
0x180002775  pop     r14
0x180002777  pop     r13
0x180002779  pop     r12
0x18000277b  pop     rdi
0x18000277c  pop     rsi
0x18000277d  pop     rbx
0x18000277e  pop     rbp
0x18000277f  retn
```
