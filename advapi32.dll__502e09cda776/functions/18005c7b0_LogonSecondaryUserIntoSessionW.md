# LogonSecondaryUserIntoSessionW

- ea: `0x18005c7b0`
- end: `0x18005cd5c`
- name: `LogonSecondaryUserIntoSessionW`
- size: `1452`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002e84`
- `0x18002f694`
- `0x1800415f4`
- `0x18005bdac`
- `0x18005bfa0`
- `0x18005c7b0`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18005c95a`
- `ntdll!RtlNtStatusToDosError` at `0x18005c95a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cba4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cba4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005ca36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005ca36`
- `KERNEL32!GetLastError` at `0x18005cc99`
- `KERNEL32!GetLastError` at `0x18005cc99`
- `KERNEL32!HeapAlloc` at `0x18005c8f5`
- `KERNEL32!HeapAlloc` at `0x18005c8f5`
- `KERNEL32!GetProcessHeap` at `0x18005c80a`
- `KERNEL32!GetProcessHeap` at `0x18005c80a`
- `KERNEL32!HeapFree` at `0x18005ccfd`
- `KERNEL32!HeapFree` at `0x18005cd1b`
- `KERNEL32!HeapFree` at `0x180072e11`
- `KERNEL32!HeapFree` at `0x180072e37`
- `KERNEL32!HeapFree` at `0x18005ccfd`
- `KERNEL32!HeapFree` at `0x18005cd1b`
- `KERNEL32!HeapFree` at `0x180072e11`
- `KERNEL32!HeapFree` at `0x180072e37`
- `KERNEL32!SetLastError` at `0x18005cb61`
- `KERNEL32!SetLastError` at `0x18005cd29`
- `KERNEL32!SetLastError` at `0x180072e47`
- `KERNEL32!SetLastError` at `0x18005cb61`
- `KERNEL32!SetLastError` at `0x18005cd29`
- `KERNEL32!SetLastError` at `0x180072e47`
- `CRYPTBASE!SystemFunction040` at `0x18005c946`
- `CRYPTBASE!SystemFunction040` at `0x18005c946`
- `USER32!GetThreadDesktop` at `0x18005cbb2`
- `USER32!GetThreadDesktop` at `0x18005cbb2`
- `USER32!GetUserObjectInformationW` at `0x18005cc00`
- `USER32!GetUserObjectInformationW` at `0x18005cc64`
- `USER32!GetUserObjectInformationW` at `0x18005cc00`
- `USER32!GetUserObjectInformationW` at `0x18005cc64`
- `USER32!GetProcessWindowStation` at `0x18005cb8c`
- `USER32!GetProcessWindowStation` at `0x18005cb8c`

## pseudocode

```c
_BOOL8 __fastcall LogonSecondaryUserIntoSessionW(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        _QWORD *a5)
{
  BOOL v6; // r12d
  unsigned __int64 v7; // rsi
  HANDLE ProcessHeap; // r13
  unsigned __int16 *v9; // r14
  signed int v10; // ebx
  __int64 v11; // r12
  __int64 v12; // rax
  unsigned int v13; // ecx
  unsigned __int64 v14; // rdi
  unsigned int v15; // eax
  unsigned __int16 *v16; // rax
  int v17; // eax
  int v18; // eax
  ULONG LastError; // eax
  HWINSTA ProcessWindowStation; // rbx
  HDESK ThreadDesktop; // r15
  DWORD CurrentThreadId; // eax
  BOOL UserObjectInformationW; // ecx
  const wchar_t *v24; // rax
  __int64 v25; // rcx
  bool v26; // zf
  __int64 v27; // rcx
  unsigned __int16 *v28; // rax
  DWORD nLengthNeeded; // [rsp+40h] [rbp-5D8h] BYREF
  BOOL v31; // [rsp+44h] [rbp-5D4h]
  int v32; // [rsp+48h] [rbp-5D0h]
  unsigned __int16 *v33; // [rsp+50h] [rbp-5C8h] BYREF
  unsigned __int16 *v34; // [rsp+58h] [rbp-5C0h]
  unsigned __int64 v35; // [rsp+60h] [rbp-5B8h] BYREF
  unsigned __int64 v36; // [rsp+68h] [rbp-5B0h] BYREF
  BOOL v37; // [rsp+70h] [rbp-5A8h]
  unsigned __int16 *v38; // [rsp+78h] [rbp-5A0h]
  _QWORD *v39; // [rsp+80h] [rbp-598h]
  int v40; // [rsp+90h] [rbp-588h] BYREF
  unsigned __int16 *v41; // [rsp+98h] [rbp-580h]
  int v42; // [rsp+A0h] [rbp-578h]
  unsigned __int16 *v43; // [rsp+A8h] [rbp-570h]
  __int16 v44; // [rsp+B0h] [rbp-568h]
  __int16 v45; // [rsp+B2h] [rbp-566h]
  const wchar_t *v46; // [rsp+B8h] [rbp-560h]
  const wchar_t *v47; // [rsp+100h] [rbp-518h]
  LPVOID lpMem; // [rsp+160h] [rbp-4B8h]
  DWORD CurrentProcessId; // [rsp+168h] [rbp-4B0h]
  DWORD v50; // [rsp+174h] [rbp-4A4h]
  int v51; // [rsp+17Ch] [rbp-49Ch]
  DWORD dwErrCode[4]; // [rsp+1A0h] [rbp-478h] BYREF
  _WORD pvInfo[528]; // [rsp+1B0h] [rbp-468h] BYREF

  nLengthNeeded = a4;
  v38 = a2;
  v33 = a1;
  v39 = a5;
  v6 = 0;
  LODWORD(v7) = 0;
  v32 = 0;
  ProcessHeap = GetProcessHeap();
  LOWORD(v40) = 0;
  memset_0((char *)&v40 + 2, 0, 0x106u);
  *(_OWORD *)dwErrCode = 0;
  v9 = 0;
  v34 = 0;
  memset_0(pvInfo, 0, 0x414u);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonSecondaryUserIntoSessionWForMcpServers>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LogonSecondaryUserIntoSessionWForMcpServers>::GetImpl'::`2'::impl) )
  {
    v10 = 50;
    goto LABEL_54;
  }
  if ( a3 && *a3 )
  {
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    v13 = v12 + 1;
    v14 = (unsigned int)(v12 + 1);
    v15 = (2 * ((_BYTE)v12 + 1)) & 7;
    v10 = 8;
    if ( v15 )
      v7 = v13 + ((8 - (unsigned __int64)v15) >> 1);
    else
      LODWORD(v7) = v14;
    v32 = v7;
    if ( (unsigned int)v7 < v13 || (unsigned int)v7 >= 0x7FFE )
    {
      v10 = 111;
      goto LABEL_53;
    }
    v16 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2LL * (unsigned int)(v7 + 1));
    v9 = v16;
    v34 = v16;
    if ( !v16 )
    {
LABEL_53:
      v6 = 0;
      goto LABEL_54;
    }
    v17 = StringCchCopyW(v16, v14, a3);
    if ( v17 < 0 )
    {
      v10 = v17;
      goto LABEL_53;
    }
    v18 = SystemFunction040(v9, 2 * v7, 2u);
    if ( v18 < 0 )
    {
      LastError = RtlNtStatusToDosError(v18);
LABEL_17:
      v10 = LastError;
      goto LABEL_53;
    }
    v9[(unsigned int)v7] = 0;
    v44 = v7;
    v45 = v7 + 1;
    v46 = v9;
  }
  else
  {
    v46 = &P;
    v35 = 0;
    v10 = StringCchLengthW(&P, 0xFFFEu, &v35);
    if ( v10 < 0 )
      goto LABEL_54;
    v44 = v35;
    v45 = v35 + 1;
    v11 = -1;
  }
  if ( (nLengthNeeded & 0xFFFFFFFC) != 0 )
  {
    v10 = 87;
    goto LABEL_53;
  }
  v50 = nLengthNeeded;
  CurrentProcessId = GetCurrentProcessId();
  v41 = v33;
  if ( v33 )
  {
    v36 = 0;
    v10 = StringCchLengthW(v33, 0xFFFEu, &v36);
    if ( v10 < 0 )
      goto LABEL_53;
    LOWORD(v40) = v36;
    HIWORD(v40) = v36 + 1;
  }
  else
  {
    v40 = 0;
  }
  v43 = v38;
  if ( v38 )
  {
    v33 = 0;
    v10 = StringCchLengthW(v38, 0xFFFEu, (unsigned __int64 *)&v33);
    if ( v10 < 0 )
    {
      v6 = 0;
      goto LABEL_54;
    }
    LOWORD(v42) = (_WORD)v33;
    HIWORD(v42) = (_WORD)v33 + 1;
  }
  else
  {
    v42 = 0;
  }
  if ( v47 && *v47 )
  {
    v51 |= 1u;
  }
  else
  {
    nLengthNeeded = 0;
    ProcessWindowStation = 0;
    ThreadDesktop = 0;
    if ( (unsigned __int8)IsGetThreadDesktopPresent() )
      ProcessWindowStation = GetProcessWindowStation();
    if ( (unsigned __int8)IsGetThreadDesktopPresent() )
    {
      CurrentThreadId = GetCurrentThreadId();
      ThreadDesktop = GetThreadDesktop(CurrentThreadId);
    }
    v31 = 0;
    v47 = &P;
    if ( (unsigned __int8)IsGetThreadDesktopPresent() )
    {
      UserObjectInformationW = GetUserObjectInformationW(ProcessWindowStation, 2, pvInfo, 0x208u, &nLengthNeeded);
      v31 = UserObjectInformationW;
      if ( UserObjectInformationW )
      {
        do
          ++v11;
        while ( pvInfo[v11] );
        pvInfo[(unsigned int)v11] = 92;
        nLengthNeeded = v11 + 1;
        UserObjectInformationW = GetUserObjectInformationW(
                                   ThreadDesktop,
                                   2,
                                   &pvInfo[(unsigned int)(v11 + 1)],
                                   0x208u,
                                   &nLengthNeeded);
        v31 = UserObjectInformationW;
        v24 = pvInfo;
        if ( !UserObjectInformationW )
          v24 = v47;
        v47 = v24;
      }
      if ( !UserObjectInformationW )
      {
        LastError = GetLastError();
        goto LABEL_17;
      }
    }
  }
  v10 = c_SeclLogonSecondaryUserIntoSessionW(
          (struct _SECL_SLI *)&v40,
          (struct _SECL_LOGONSECONDARYUSERINTOSESSION_SLRI *)dwErrCode);
  if ( v10 )
    goto LABEL_53;
  v6 = dwErrCode[2] == 0;
  v37 = v6;
  if ( dwErrCode[2] )
  {
    v10 = dwErrCode[2];
    SetLastError(dwErrCode[2]);
  }
  else
  {
    *v39 = *(_QWORD *)dwErrCode;
    v10 = 0;
  }
LABEL_54:
  if ( v9 )
  {
    v25 = (unsigned int)(v7 + 1);
    v26 = 2 * v25 == 0;
    v27 = 2 * v25;
    v28 = v9;
    if ( !v26 )
    {
      do
      {
        *(_BYTE *)v28 = 0;
        v28 = (unsigned __int16 *)((char *)v28 + 1);
        --v27;
      }
      while ( v27 );
    }
    HeapFree(ProcessHeap, 0, v9);
  }
  if ( lpMem )
    HeapFree(ProcessHeap, 0, lpMem);
  SetLastError(v10);
  return v6;
}

```

## disassembly

```asm
0x18005c7b0  push    rbx
0x18005c7b2  push    rsi
0x18005c7b3  push    rdi
0x18005c7b4  push    r12
0x18005c7b6  push    r13
0x18005c7b8  push    r14
0x18005c7ba  push    r15
0x18005c7bc  sub     rsp, 5E0h
0x18005c7c3  mov     rax, cs:__security_cookie
0x18005c7ca  xor     rax, rsp
0x18005c7cd  mov     [rsp+618h+var_48], rax
0x18005c7d5  mov     [rsp+618h+nLengthNeeded], r9d
0x18005c7da  mov     r15, r8
0x18005c7dd  mov     [rsp+618h+var_5A0], rdx
0x18005c7e2  mov     [rsp+618h+var_5C8], rcx
0x18005c7e7  mov     rax, [rsp+618h+arg_20]
0x18005c7ef  mov     [rsp+618h+var_598], rax
0x18005c7f7  xor     ebx, ebx
0x18005c7f9  mov     r12d, ebx
0x18005c7fc  mov     [rsp+618h+var_5E4], ebx
0x18005c800  mov     esi, ebx
0x18005c802  mov     [rsp+618h+var_5D0], ebx
0x18005c806  mov     [rsp+618h+var_5E8], ebx
0x18005c80a  call    cs:__imp_GetProcessHeap
0x18005c811  nop     dword ptr [rax+rax+00h]
0x18005c816  mov     r13, rax
0x18005c819  mov     [rsp+618h+hHeap], rax
0x18005c81e  mov     eax, ebx
0x18005c820  mov     word ptr [rsp+618h+var_588], bx
0x18005c828  xor     edx, edx; Val
0x18005c82a  mov     r8d, 106h; Size
0x18005c830  lea     rcx, [rsp+618h+var_588+2]; void *
0x18005c838  call    memset_0
0x18005c83d  xorps   xmm0, xmm0
0x18005c840  movups  xmmword ptr [rsp+618h+dwErrCode], xmm0
0x18005c848  mov     r14d, ebx
0x18005c84b  mov     [rsp+618h+var_5C0], rbx
0x18005c850  xor     edx, edx; Val
0x18005c852  mov     r8d, 414h; Size
0x18005c858  lea     rcx, [rsp+618h+pvInfo]; void *
0x18005c860  call    memset_0
0x18005c865  nop
0x18005c866  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LogonSecondaryUserIntoSessionWForMcpServers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LogonSecondaryUserIntoSessionWForMcpServers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonSecondaryUserIntoSessionWForMcpServers> `wil::Feature<__WilFeatureTraits_Feature_LogonSecondaryUserIntoSessionWForMcpServers>::GetImpl(void)'::`2'::impl
0x18005c86d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LogonSecondaryUserIntoSessionWForMcpServers@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonSecondaryUserIntoSessionWForMcpServers>::__private_IsEnabled(void)
0x18005c872  xor     edx, edx; dwFlags
0x18005c874  test    al, al
0x18005c876  jnz     short loc_18005C887
0x18005c878  lea     ebx, [rdx+32h]
0x18005c87b  mov     [rsp+618h+var_5E8], ebx
0x18005c87f  lea     edi, [rdx+1]
0x18005c882  jmp     loc_18005CCDB
0x18005c887  test    r15, r15
0x18005c88a  jz      loc_18005C9BD
0x18005c890  cmp     dx, [r15]
0x18005c894  jz      loc_18005C9BD
0x18005c89a  or      r12, 0FFFFFFFFFFFFFFFFh
0x18005c89e  mov     rax, r12
0x18005c8a1  inc     rax
0x18005c8a4  cmp     [r15+rax*2], dx
0x18005c8a9  jnz     short loc_18005C8A1
0x18005c8ab  lea     ecx, [rax+1]
0x18005c8ae  mov     edi, ecx
0x18005c8b0  lea     rax, [rcx+rcx]
0x18005c8b4  and     eax, 7
0x18005c8b7  mov     ebx, 8
0x18005c8bc  jnz     short loc_18005C8C2
0x18005c8be  mov     esi, edi
0x18005c8c0  jmp     short loc_18005C8CE
0x18005c8c2  mov     rsi, rbx
0x18005c8c5  sub     rsi, rax
0x18005c8c8  shr     rsi, 1
0x18005c8cb  add     rsi, rdi
0x18005c8ce  mov     [rsp+618h+var_5D0], esi
0x18005c8d2  cmp     esi, ecx
0x18005c8d4  jb      loc_18005C9AC
0x18005c8da  cmp     esi, 7FFEh
0x18005c8e0  jnb     loc_18005C9AC
0x18005c8e6  lea     r13d, [rsi+1]
0x18005c8ea  mov     r8d, r13d
0x18005c8ed  add     r8, r8; dwBytes
0x18005c8f0  mov     rcx, [rsp+618h+hHeap]; hHeap
0x18005c8f5  call    cs:__imp_HeapAlloc
0x18005c8fc  nop     dword ptr [rax+rax+00h]
0x18005c901  mov     r14, rax
0x18005c904  mov     [rsp+618h+var_5C0], rax
0x18005c909  xor     edx, edx
0x18005c90b  test    rax, rax
0x18005c90e  jnz     short loc_18005C91E
0x18005c910  mov     [rsp+618h+var_5E8], ebx
0x18005c914  mov     edi, 1
0x18005c919  jmp     loc_18005CCD1
0x18005c91e  mov     r8, r15; unsigned __int16 *
0x18005c921  mov     rdx, rdi; unsigned __int64
0x18005c924  mov     rcx, r14; unsigned __int16 *
0x18005c927  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005c92c  xor     edx, edx
0x18005c92e  test    eax, eax
0x18005c930  jns     short loc_18005C93A
0x18005c932  mov     ebx, eax
0x18005c934  mov     [rsp+618h+var_5E8], eax
0x18005c938  jmp     short loc_18005C914
0x18005c93a  lea     edx, [rsi+rsi]; MemorySize
0x18005c93d  mov     r8d, 2; OptionFlags
0x18005c943  mov     rcx, r14; Memory
0x18005c946  call    cs:__imp_SystemFunction040
0x18005c94d  nop     dword ptr [rax+rax+00h]
0x18005c952  xor     edx, edx
0x18005c954  test    eax, eax
0x18005c956  jns     short loc_18005C978
0x18005c958  mov     ecx, eax; Status
0x18005c95a  call    cs:__imp_RtlNtStatusToDosError
0x18005c961  nop     dword ptr [rax+rax+00h]
0x18005c966  mov     edi, 1
0x18005c96b  mov     [rsp+618h+var_5E8], eax
0x18005c96f  mov     ebx, eax
0x18005c971  xor     edx, edx
0x18005c973  jmp     loc_18005CCD1
0x18005c978  mov     ecx, esi
0x18005c97a  mov     [r14+rcx*2], dx
0x18005c97f  mov     [rsp+618h+var_568], si
0x18005c987  mov     [rsp+618h+var_566], r13w
0x18005c990  mov     [rsp+618h+var_560], r14
0x18005c998  lea     r13, P
0x18005c99f  mov     edi, 1
0x18005c9a4  mov     r15d, 0FFFEh
0x18005c9aa  jmp     short loc_18005CA16
0x18005c9ac  mov     ebx, 6Fh ; 'o'
0x18005c9b1  mov     [rsp+618h+var_5E8], ebx
0x18005c9b5  lea     edi, [rbx-6Eh]
0x18005c9b8  jmp     loc_18005CCD6
0x18005c9bd  lea     r13, P
0x18005c9c4  mov     [rsp+618h+var_560], r13
0x18005c9cc  mov     [rsp+618h+var_5B8], rdx
0x18005c9d1  lea     r8, [rsp+618h+var_5B8]; unsigned __int64 *
0x18005c9d6  mov     r15d, 0FFFEh
0x18005c9dc  mov     edx, r15d; unsigned __int64
0x18005c9df  mov     rcx, r13; unsigned __int16 *
0x18005c9e2  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005c9e7  mov     ebx, eax
0x18005c9e9  mov     [rsp+618h+var_5E8], eax
0x18005c9ed  xor     edx, edx
0x18005c9ef  lea     edi, [rdx+1]
0x18005c9f2  test    eax, eax
0x18005c9f4  js      loc_18005CCC3
0x18005c9fa  mov     rax, [rsp+618h+var_5B8]
0x18005c9ff  mov     [rsp+618h+var_568], ax
0x18005ca07  add     ax, di
0x18005ca0a  mov     [rsp+618h+var_566], ax
0x18005ca12  or      r12, 0FFFFFFFFFFFFFFFFh
0x18005ca16  mov     eax, [rsp+618h+nLengthNeeded]
0x18005ca1a  test    eax, 0FFFFFFFCh
0x18005ca1f  jz      short loc_18005CA2F
0x18005ca21  mov     ebx, 57h ; 'W'
0x18005ca26  mov     [rsp+618h+var_5E8], ebx
0x18005ca2a  jmp     loc_18005CCD1
0x18005ca2f  mov     [rsp+618h+var_4A4], eax
0x18005ca36  call    cs:__imp_GetCurrentProcessId
0x18005ca3d  nop     dword ptr [rax+rax+00h]
0x18005ca42  mov     [rsp+618h+var_4B0], eax
0x18005ca49  mov     rax, [rsp+618h+var_5C8]
0x18005ca4e  mov     [rsp+618h+var_580], rax
0x18005ca56  xor     edx, edx
0x18005ca58  test    rax, rax
0x18005ca5b  jz      short loc_18005CA9C
0x18005ca5d  mov     [rsp+618h+var_5B0], rdx
0x18005ca62  lea     r8, [rsp+618h+var_5B0]; unsigned __int64 *
0x18005ca67  mov     rdx, r15; unsigned __int64
0x18005ca6a  mov     rcx, rax; unsigned __int16 *
0x18005ca6d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005ca72  mov     ebx, eax
0x18005ca74  mov     [rsp+618h+var_5E8], eax
0x18005ca78  xor     edx, edx
0x18005ca7a  test    eax, eax
0x18005ca7c  js      loc_18005CCD1
0x18005ca82  mov     rax, [rsp+618h+var_5B0]
0x18005ca87  mov     word ptr [rsp+618h+var_588], ax
0x18005ca8f  add     ax, di
0x18005ca92  mov     word ptr [rsp+618h+var_588+2], ax
0x18005ca9a  jmp     short loc_18005CAA3
0x18005ca9c  mov     [rsp+618h+var_588], edx
0x18005caa3  mov     rax, [rsp+618h+var_5A0]
0x18005caa8  mov     [rsp+618h+var_570], rax
0x18005cab0  test    rax, rax
0x18005cab3  jz      short loc_18005CAF4
0x18005cab5  mov     [rsp+618h+var_5C8], rdx
0x18005caba  lea     r8, [rsp+618h+var_5C8]; unsigned __int64 *
0x18005cabf  mov     rdx, r15; unsigned __int64
0x18005cac2  mov     rcx, rax; unsigned __int16 *
0x18005cac5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005caca  mov     ebx, eax
0x18005cacc  mov     [rsp+618h+var_5E8], eax
0x18005cad0  xor     edx, edx
0x18005cad2  test    eax, eax
0x18005cad4  js      loc_18005CCCA
0x18005cada  mov     rax, [rsp+618h+var_5C8]
0x18005cadf  mov     word ptr [rsp+618h+var_578], ax
0x18005cae7  add     ax, di
0x18005caea  mov     word ptr [rsp+618h+var_578+2], ax
0x18005caf2  jmp     short loc_18005CAFF
0x18005caf4  mov     [rsp+618h+var_578], 0
0x18005caff  mov     rax, [rsp+618h+var_518]
0x18005cb07  test    rax, rax
0x18005cb0a  jz      short loc_18005CB79
0x18005cb0c  cmp     [rax], dx
0x18005cb0f  jz      short loc_18005CB79
0x18005cb11  or      [rsp+618h+var_49C], edi
0x18005cb18  lea     rdx, [rsp+618h+dwErrCode]; struct _SECL_LOGONSECONDARYUSERINTOSESSION_SLRI *
0x18005cb20  lea     rcx, [rsp+618h+var_588]; struct _SECL_SLI *
0x18005cb28  call    ?c_SeclLogonSecondaryUserIntoSessionW@@YAKPEAU_SECL_SLI@@PEAU_SECL_LOGONSECONDARYUSERINTOSESSION_SLRI@@@Z; c_SeclLogonSecondaryUserIntoSessionW(_SECL_SLI *,_SECL_LOGONSECONDARYUSERINTOSESSION_SLRI *)
0x18005cb2d  mov     ebx, eax
0x18005cb2f  mov     [rsp+618h+var_5E8], eax
0x18005cb33  xor     edx, edx
0x18005cb35  test    eax, eax
0x18005cb37  jnz     loc_18005CCD1
0x18005cb3d  mov     r12d, edx
0x18005cb40  mov     ecx, [rsp+618h+dwErrCode+8]; dwErrCode
0x18005cb47  test    ecx, ecx
0x18005cb49  setz    r12b
0x18005cb4d  mov     [rsp+618h+var_5A8], r12d
0x18005cb52  test    r12d, r12d
0x18005cb55  jnz     loc_18005CCAA
0x18005cb5b  mov     ebx, ecx
0x18005cb5d  mov     [rsp+618h+var_5E8], ecx
0x18005cb61  call    cs:__imp_SetLastError
0x18005cb68  nop     dword ptr [rax+rax+00h]
0x18005cb6d  mov     r13, [rsp+618h+hHeap]
0x18005cb72  xor     edx, edx
0x18005cb74  jmp     loc_18005CCDB
0x18005cb79  mov     [rsp+618h+nLengthNeeded], edx
0x18005cb7d  mov     rbx, rdx
0x18005cb80  mov     r15, rdx
0x18005cb83  call    IsGetThreadDesktopPresent
0x18005cb88  test    al, al
0x18005cb8a  jz      short loc_18005CB9B
0x18005cb8c  call    cs:__imp_GetProcessWindowStation
0x18005cb93  nop     dword ptr [rax+rax+00h]
0x18005cb98  mov     rbx, rax
0x18005cb9b  call    IsGetThreadDesktopPresent
0x18005cba0  test    al, al
0x18005cba2  jz      short loc_18005CBC1
0x18005cba4  call    cs:__imp_GetCurrentThreadId
0x18005cbab  nop     dword ptr [rax+rax+00h]
0x18005cbb0  mov     ecx, eax; dwThreadId
0x18005cbb2  call    cs:__imp_GetThreadDesktop
0x18005cbb9  nop     dword ptr [rax+rax+00h]
0x18005cbbe  mov     r15, rax
0x18005cbc1  mov     [rsp+618h+var_5D4], 0
0x18005cbc9  mov     [rsp+618h+var_518], r13
0x18005cbd1  call    IsGetThreadDesktopPresent
0x18005cbd6  xor     r13d, r13d
0x18005cbd9  test    al, al
0x18005cbdb  jz      loc_18005CB18
0x18005cbe1  lea     rax, [rsp+618h+nLengthNeeded]
0x18005cbe6  mov     [rsp+618h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18005cbeb  mov     r9d, 208h; nLength
0x18005cbf1  lea     r8, [rsp+618h+pvInfo]; pvInfo
0x18005cbf9  lea     edx, [r13+2]; nIndex
0x18005cbfd  mov     rcx, rbx; hObj
0x18005cc00  call    cs:__imp_GetUserObjectInformationW
0x18005cc07  nop     dword ptr [rax+rax+00h]
0x18005cc0c  mov     ecx, eax
0x18005cc0e  mov     [rsp+618h+var_5D4], eax
0x18005cc12  test    eax, eax
0x18005cc14  jz      short loc_18005CC91
0x18005cc16  lea     rax, [rsp+618h+pvInfo]
0x18005cc1e  inc     r12
0x18005cc21  cmp     [rax+r12*2], r13w
0x18005cc26  jnz     short loc_18005CC1E
0x18005cc28  mov     eax, r12d
0x18005cc2b  mov     [rsp+618h+nLengthNeeded], eax
0x18005cc2f  mov     ecx, 5Ch ; '\'
0x18005cc34  mov     [rsp+rax*2+618h+pvInfo], cx
0x18005cc3c  inc     eax
0x18005cc3e  mov     [rsp+618h+nLengthNeeded], eax
0x18005cc42  lea     r8, [rsp+618h+pvInfo]
0x18005cc4a  lea     r8, [r8+rax*2]; pvInfo
0x18005cc4e  lea     rax, [rsp+618h+nLengthNeeded]
0x18005cc53  mov     [rsp+618h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18005cc58  lea     edx, [rcx-5Ah]; nIndex
0x18005cc5b  mov     r9d, 208h; nLength
0x18005cc61  mov     rcx, r15; hObj
0x18005cc64  call    cs:__imp_GetUserObjectInformationW
0x18005cc6b  nop     dword ptr [rax+rax+00h]
0x18005cc70  mov     ecx, eax
0x18005cc72  mov     [rsp+618h+var_5D4], eax
0x18005cc76  lea     rax, [rsp+618h+pvInfo]
0x18005cc7e  test    ecx, ecx
0x18005cc80  cmovz   rax, [rsp+618h+var_518]
0x18005cc89  mov     [rsp+618h+var_518], rax
0x18005cc91  test    ecx, ecx
0x18005cc93  jnz     loc_18005CB18
0x18005cc99  call    cs:__imp_GetLastError
0x18005cca0  nop     dword ptr [rax+rax+00h]
0x18005cca5  jmp     loc_18005C96B
0x18005ccaa  mov     rax, qword ptr [rsp+618h+dwErrCode]
0x18005ccb2  mov     rcx, [rsp+618h+var_598]
0x18005ccba  mov     [rcx], rax
0x18005ccbd  mov     ebx, edx
0x18005ccbf  mov     [rsp+618h+var_5E8], edx
0x18005ccc3  mov     r13, [rsp+618h+hHeap]
  ... truncated ...
```
