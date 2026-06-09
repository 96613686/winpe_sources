# MachineName::Initialize(IRequestContext &)

- ea: `0x180023330`
- end: `0x180023694`
- name: `?Initialize@MachineName@@UEAA_NAEAVIRequestContext@@@Z`
- size: `868`
- prototype: `bool __fastcall(MachineName *__hidden this, struct IRequestContext *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180013384`
- `0x180023330`
- `0x18004a900`
- `0x180112380`
- `0x1801123a8`
- `0x1801133b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002342f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800234ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002342f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800234ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800233d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023481`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800233d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023481`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180023379`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180023401`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180023427`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800234cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180023379`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180023401`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180023427`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800234cc`

## string_xrefs

- `0x1800235cf`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180023642`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`

## pseudocode

```c
char __fastcall MachineName::Initialize(MachineName *this, struct IRequestContext *a2)
{
  BOOL ComputerName; // ebx
  DWORD LastError; // eax
  DWORD v6; // esi
  SIZE_T v7; // rbx
  CHeap *v8; // rcx
  void *Handle; // rax
  WCHAR *v10; // rsi
  BOOL v11; // ebx
  DWORD v12; // eax
  CHeap *v13; // rcx
  SIZE_T v14; // rbx
  CHeap *v15; // rcx
  void *v16; // rax
  WCHAR *v17; // rbx
  PVOID *v19; // rcx
  DWORD v20; // ebx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  DWORD nSize; // [rsp+80h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids);
  nSize = 0;
  ComputerName = GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize);
  LastError = GetLastError();
  v6 = LastError;
  if ( ComputerName || LastError != 234 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      goto LABEL_33;
    v24 = 170;
    goto LABEL_37;
  }
  v7 = 2LL * nSize;
  if ( !is_mul_ok(nSize, 2u) )
    v7 = -1;
  if ( CHeap::GetHandle((CHeap *)nSize) )
  {
    Handle = CHeap::GetHandle(v8);
    v10 = (WCHAR *)HeapAlloc(Handle, 0, v7);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
    v10 = 0;
  }
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr((char *)this + 16);
  *((_QWORD *)this + 2) = v10;
  if ( !v10 )
    goto LABEL_17;
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v10, &nSize) )
  {
    v20 = GetLastError();
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      goto LABEL_27;
    v25 = 171;
    goto LABEL_44;
  }
  nSize = 0;
  v11 = GetComputerNameExW(ComputerNameDnsHostname, 0, &nSize);
  v12 = GetLastError();
  v6 = v12;
  if ( v11 || v12 != 234 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      goto LABEL_33;
    v24 = 172;
LABEL_37:
    WPP_SF_d(v23[2], v24, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, v6);
LABEL_33:
    v22 = v6;
    goto LABEL_28;
  }
  v14 = 2LL * nSize;
  if ( !is_mul_ok(nSize, 2u) )
    v14 = -1;
  if ( CHeap::GetHandle(v13) )
  {
    v16 = CHeap::GetHandle(v15);
    v17 = (WCHAR *)HeapAlloc(v16, 0, v14);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
    v17 = 0;
  }
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr((char *)this + 8);
  *((_QWORD *)this + 1) = v17;
  if ( !v17 )
  {
LABEL_17:
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    return 0;
  }
  if ( !GetComputerNameExW(ComputerNameDnsHostname, v17, &nSize) )
  {
    v20 = GetLastError();
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      goto LABEL_27;
    v25 = 173;
LABEL_44:
    WPP_SF_d(v21[2], v25, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, v20);
LABEL_27:
    v22 = v20;
LABEL_28:
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v22);
    return 0;
  }
  if ( MachineName::SetComputerNameFQDN(this) )
    goto LABEL_21;
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
    {
LABEL_22:
      if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x1000000) != 0 )
        WPP_SF_S(v19[2], 175, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, *((_QWORD *)this + 1));
      return 1;
    }
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids);
LABEL_21:
    v19 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  return 1;
}

```

## disassembly

```asm
0x180023330  push    rbx
0x180023332  push    rbp
0x180023333  push    rsi
0x180023334  push    rdi
0x180023335  push    r12
0x180023337  push    r15
0x180023339  sub     rsp, 38h
0x18002333d  mov     rdi, rdx
0x180023340  mov     rbp, rcx
0x180023343  mov     rcx, cs:WPP_GLOBAL_Control
0x18002334a  lea     r15, WPP_GLOBAL_Control
0x180023351  lea     r12, WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids
0x180023358  cmp     rcx, r15
0x18002335b  jnz     loc_180023591
0x180023361  xor     edx, edx; lpBuffer
0x180023363  mov     [rsp+68h+nSize], 0
0x18002336e  lea     r8, [rsp+68h+nSize]; nSize
0x180023376  lea     ecx, [rdx+3]; NameType
0x180023379  call    cs:__imp_GetComputerNameExW
0x18002337f  mov     ebx, eax
0x180023381  call    cs:__imp_GetLastError
0x180023387  mov     esi, eax
0x180023389  test    ebx, ebx
0x18002338b  jnz     loc_180023566
0x180023391  cmp     eax, 0EAh
0x180023396  jnz     loc_180023566
0x18002339c  mov     ecx, [rsp+68h+nSize]; this
0x1800233a3  lea     eax, [rbx+2]
0x1800233a6  mul     rcx
0x1800233a9  mov     rbx, rax
0x1800233ac  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800233b3  cmovb   rbx, rax
0x1800233b7  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x1800233bc  test    rax, rax
0x1800233bf  jz      loc_1800235B4
0x1800233c5  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x1800233ca  mov     r8, rbx; dwBytes
0x1800233cd  xor     edx, edx; dwFlags
0x1800233cf  mov     rcx, rax; hHeap
0x1800233d2  call    cs:__imp_HeapAlloc
0x1800233d8  mov     rsi, rax
0x1800233db  lea     rcx, [rbp+10h]
0x1800233df  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800233e4  mov     [rbp+10h], rsi
0x1800233e8  test    rsi, rsi
0x1800233eb  jz      loc_18002349E
0x1800233f1  lea     r8, [rsp+68h+nSize]; nSize
0x1800233f9  mov     rdx, rsi; lpBuffer
0x1800233fc  mov     ecx, 3; NameType
0x180023401  call    cs:__imp_GetComputerNameExW
0x180023407  test    eax, eax
0x180023409  jz      loc_1800235E2
0x18002340f  xor     edx, edx; lpBuffer
0x180023411  mov     [rsp+68h+nSize], 0
0x18002341c  lea     r8, [rsp+68h+nSize]; nSize
0x180023424  lea     ecx, [rdx+1]; NameType
0x180023427  call    cs:__imp_GetComputerNameExW
0x18002342d  mov     ebx, eax
0x18002342f  call    cs:__imp_GetLastError
0x180023435  mov     esi, eax
0x180023437  test    ebx, ebx
0x180023439  jnz     loc_180023552
0x18002343f  cmp     eax, 0EAh
0x180023444  jnz     loc_180023552
0x18002344a  mov     r10d, [rsp+68h+nSize]
0x180023452  lea     eax, [rbx+2]
0x180023455  mul     r10
0x180023458  mov     rbx, rax
0x18002345b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180023462  cmovb   rbx, rax
0x180023466  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18002346b  test    rax, rax
0x18002346e  jz      loc_180023627
0x180023474  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180023479  mov     r8, rbx; dwBytes
0x18002347c  xor     edx, edx; dwFlags
0x18002347e  mov     rcx, rax; hHeap
0x180023481  call    cs:__imp_HeapAlloc
0x180023487  mov     rbx, rax
0x18002348a  lea     rsi, [rbp+8]
0x18002348e  mov     rcx, rsi
0x180023491  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180023496  mov     [rsi], rbx
0x180023499  test    rbx, rbx
0x18002349c  jnz     short loc_1800234BC
0x18002349e  mov     rax, [rdi]
0x1800234a1  mov     rcx, rdi
0x1800234a4  mov     rax, [rax+18h]
0x1800234a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234ad  xor     al, al
0x1800234af  add     rsp, 38h
0x1800234b3  pop     r15
0x1800234b5  pop     r12
0x1800234b7  pop     rdi
0x1800234b8  pop     rsi
0x1800234b9  pop     rbp
0x1800234ba  pop     rbx
0x1800234bb  retn
0x1800234bc  lea     r8, [rsp+68h+nSize]; nSize
0x1800234c4  mov     rdx, rbx; lpBuffer
0x1800234c7  mov     ecx, 1; NameType
0x1800234cc  call    cs:__imp_GetComputerNameExW
0x1800234d2  test    eax, eax
0x1800234d4  jz      short loc_1800234FF
0x1800234d6  mov     rcx, rbp; this
0x1800234d9  call    ?SetComputerNameFQDN@MachineName@@QEAA_NXZ; MachineName::SetComputerNameFQDN(void)
0x1800234de  test    al, al
0x1800234e0  jz      short loc_18002352A
0x1800234e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234e9  cmp     rcx, r15
0x1800234ec  jz      short loc_1800234FB
0x1800234ee  test    dword ptr [rcx+1Ch], 1000000h
0x1800234f5  jnz     loc_180023664
0x1800234fb  mov     al, 1
0x1800234fd  jmp     short loc_1800234AF
0x1800234ff  call    cs:__imp_GetLastError
0x180023505  mov     ebx, eax
0x180023507  mov     rcx, cs:WPP_GLOBAL_Control
0x18002350e  cmp     rcx, r15
0x180023511  jnz     loc_180023655
0x180023517  mov     edx, ebx
0x180023519  mov     rax, [rdi]
0x18002351c  mov     rcx, rdi
0x18002351f  mov     rax, [rax+48h]
0x180023523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023528  jmp     short loc_1800234AD
0x18002352a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023531  cmp     rcx, r15
0x180023534  jz      short loc_1800234FB
0x180023536  test    dword ptr [rcx+1Ch], 800000h
0x18002353d  jz      short loc_1800234E9
0x18002353f  mov     rcx, [rcx+10h]
0x180023543  mov     edx, 0AEh
0x180023548  mov     r8, r12
0x18002354b  call    WPP_SF_
0x180023550  jmp     short loc_1800234E2
0x180023552  mov     rcx, cs:WPP_GLOBAL_Control
0x180023559  cmp     rcx, r15
0x18002355c  jnz     loc_18002367D
0x180023562  mov     edx, esi
0x180023564  jmp     short loc_180023519
0x180023566  mov     rcx, cs:WPP_GLOBAL_Control
0x18002356d  cmp     rcx, r15
0x180023570  jz      short loc_180023562
0x180023572  test    dword ptr [rcx+1Ch], 800000h
0x180023579  jz      short loc_180023562
0x18002357b  mov     edx, 0AAh
0x180023580  mov     rcx, [rcx+10h]
0x180023584  mov     r9d, esi
0x180023587  mov     r8, r12
0x18002358a  call    WPP_SF_d
0x18002358f  jmp     short loc_180023562
0x180023591  test    dword ptr [rcx+1Ch], 1000000h
0x180023598  jz      loc_180023361
0x18002359e  mov     rcx, [rcx+10h]
0x1800235a2  mov     edx, 0A9h
0x1800235a7  mov     r8, r12
0x1800235aa  call    WPP_SF_
0x1800235af  jmp     loc_180023361
0x1800235b4  mov     r9d, 54Fh; unsigned int
0x1800235ba  mov     [rsp+68h+var_48], 0; struct IRequestContext *
0x1800235c3  lea     r8, a170; "170"
0x1800235ca  mov     edx, 0AAh; unsigned int
0x1800235cf  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x1800235d6  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800235db  xor     esi, esi
0x1800235dd  jmp     loc_1800233DB
0x1800235e2  call    cs:__imp_GetLastError
0x1800235e8  mov     ebx, eax
0x1800235ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235f1  cmp     rcx, r15
0x1800235f4  jz      loc_180023517
0x1800235fa  test    dword ptr [rcx+1Ch], 800000h
0x180023601  jz      loc_180023517
0x180023607  mov     edx, 0ABh
0x18002360c  jmp     short loc_180023613
0x18002360e  mov     edx, 0ADh
0x180023613  mov     rcx, [rcx+10h]
0x180023617  mov     r9d, ebx
0x18002361a  mov     r8, r12
0x18002361d  call    WPP_SF_d
0x180023622  jmp     loc_180023517
0x180023627  mov     r9d, 54Fh; unsigned int
0x18002362d  mov     [rsp+68h+var_48], 0; struct IRequestContext *
0x180023636  lea     r8, a170; "170"
0x18002363d  mov     edx, 0AAh; unsigned int
0x180023642  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x180023649  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18002364e  xor     ebx, ebx
0x180023650  jmp     loc_18002348A
0x180023655  test    dword ptr [rcx+1Ch], 800000h
0x18002365c  jz      loc_180023517
0x180023662  jmp     short loc_18002360E
0x180023664  mov     r9, [rsi]
0x180023667  mov     edx, 0AFh
0x18002366c  mov     rcx, [rcx+10h]
0x180023670  mov     r8, r12
0x180023673  call    WPP_SF_S
0x180023678  jmp     loc_1800234FB
0x18002367d  test    dword ptr [rcx+1Ch], 800000h
0x180023684  jz      loc_180023562
0x18002368a  mov     edx, 0ACh
0x18002368f  jmp     loc_180023580
```
