# InitializePnpInfo(void)

- ea: `0x18011361c`
- end: `0x1801139fa`
- name: `?InitializePnpInfo@@YAHXZ`
- size: `990`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180113a00`

## callees

- `0x180072450`
- `0x180113118`
- `0x18011361c`
- `0x180113b54`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x18011363f`
- `ntdll!RtlInitializeResource` at `0x18011363f`
- `ntdll!RtlDeleteResource` at `0x1801139d0`
- `ntdll!RtlDeleteResource` at `0x1801139d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113717`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113863`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113717`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113863`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801137f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113806`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113993`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801137f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113806`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801136f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801136f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011368e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011368e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801139ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801139ba`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801136b7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801136b7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801139a8`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1801139a8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180113834`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180113834`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180113790`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1801137bf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180113790`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1801137bf`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1801136ef`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18011374d`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1801136ef`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18011374d`

## pseudocode

```c
__int64 InitializePnpInfo(void)
{
  unsigned int KernelObjectSecurity; // esi
  void *v1; // rax
  void *v2; // rdi
  int v3; // r15d
  HANDLE CurrentProcess; // rax
  HANDLE v5; // rax
  void *v6; // r14
  _QWORD *v7; // rax
  _DWORD *v8; // rax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  PACL pDacl; // [rsp+30h] [rbp-48h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+38h] [rbp-40h] BYREF
  DWORD nLengthNeeded; // [rsp+80h] [rbp+8h] BYREF
  WINBOOL bDaclPresent; // [rsp+88h] [rbp+10h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+90h] [rbp+18h] BYREF
  PACL v17; // [rsp+98h] [rbp+20h] BYREF

  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  RtlInitializeResource(&PnpInfoResource);
  gfPnpInfoResource = 1;
  KernelObjectSecurity = 0;
  v1 = (void *)BuildSecurityDescriptor();
  v2 = v1;
  if ( v1 )
  {
    v3 = 0;
    FileMappingAttributes.nLength = 24;
    FileMappingAttributes.lpSecurityDescriptor = v1;
    FileMappingAttributes.bInheritHandle = 0;
    CurrentProcess = GetCurrentProcess();
    v5 = CreateFileMappingW(CurrentProcess, &FileMappingAttributes, 4u, 0, 0xCu, L"Global\\mmGlobalPnpInfo");
    hPnpInfo = v5;
    if ( v5 )
    {
      nLengthNeeded = 0;
      KernelObjectSecurity = GetKernelObjectSecurity(v5, 4u, 0, 0, &nLengthNeeded);
      if ( GetLastError() == 122 )
      {
        v6 = HeapAlloc(g_hHeap, 0, nLengthNeeded);
        if ( v6 )
        {
          if ( GetKernelObjectSecurity(hPnpInfo, 4u, v6, nLengthNeeded, &nLengthNeeded) )
          {
            pDacl = 0;
            v17 = 0;
            bDaclPresent = 0;
            bDaclDefaulted = 0;
            if ( GetSecurityDescriptorDacl(v2, &bDaclPresent, &pDacl, &bDaclDefaulted) )
            {
              if ( bDaclPresent && GetSecurityDescriptorDacl(v6, &bDaclPresent, &v17, &bDaclDefaulted) && bDaclPresent )
                v3 = ValidateSecurityDescriptorDacl(pDacl, v17);
            }
          }
          HeapFree(g_hHeap, 0, v6);
        }
      }
    }
    HeapFree(g_hHeap, 0, v2);
    if ( v3 )
    {
      if ( hPnpInfo )
      {
        v7 = MapViewOfFile(hPnpInfo, 2u, 0, 0, 0);
        g_pPnpInfoShared = v7;
        if ( v7 )
        {
          *v7 = 0;
          *(_QWORD *)((char *)v7 + 4) = 0;
          *(_DWORD *)v7 = 12;
          v8 = HeapAlloc(g_hHeap, 8u, 0xCu);
          g_pPnpInfoActual = v8;
          if ( v8 )
          {
            *v8 = 12;
            *((_DWORD *)g_pPnpInfoActual + 1) = 0;
            return 1;
          }
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v10 = 20;
LABEL_37:
            WPP_SF_(v9[2], v10, &WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids);
          }
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v10 = 21;
            goto LABEL_37;
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v10 = 22;
          goto LABEL_37;
        }
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v10 = 23;
        goto LABEL_37;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v10 = 24;
      goto LABEL_37;
    }
  }
  if ( !KernelObjectSecurity )
  {
    if ( g_pPnpInfoActual )
      HeapFree(g_hHeap, 0, g_pPnpInfoActual);
    if ( g_pPnpInfoShared )
      UnmapViewOfFile(g_pPnpInfoShared);
    if ( hPnpInfo )
      CloseHandle(hPnpInfo);
    if ( gfPnpInfoResource )
      RtlDeleteResource(&PnpInfoResource);
    g_pPnpInfoShared = 0;
    hPnpInfo = 0;
    gfPnpInfoResource = 0;
  }
  return KernelObjectSecurity;
}

```

## disassembly

```asm
0x18011361c  push    rsi
0x18011361e  push    rdi
0x18011361f  push    r12
0x180113621  push    r14
0x180113623  push    r15
0x180113625  sub     rsp, 50h
0x180113629  xorps   xmm0, xmm0
0x18011362c  xor     eax, eax
0x18011362e  movups  xmmword ptr [rsp+78h+FileMappingAttributes.nLength], xmm0
0x180113633  mov     qword ptr [rsp+78h+FileMappingAttributes.bInheritHandle], rax
0x180113638  lea     rcx, ?PnpInfoResource@@3U_RTL_RESOURCE@@A; Resource
0x18011363f  call    cs:__imp_RtlInitializeResource
0x180113645  mov     eax, 1
0x18011364a  mov     cs:?gfPnpInfoResource@@3HA, eax; int gfPnpInfoResource
0x180113650  jmp     short loc_18011365A
0x180113652  xor     eax, eax
0x180113654  mov     cs:?gfPnpInfoResource@@3HA, eax; int gfPnpInfoResource
0x18011365a  xor     r12d, r12d
0x18011365d  test    eax, eax
0x18011365f  jz      loc_1801139ED
0x180113665  mov     esi, r12d
0x180113668  call    ?BuildSecurityDescriptor@@YAPEAXKK@Z; BuildSecurityDescriptor(ulong,ulong)
0x18011366d  mov     rdi, rax
0x180113670  test    rax, rax
0x180113673  jz      loc_180113943
0x180113679  mov     r15d, r12d
0x18011367c  mov     [rsp+78h+FileMappingAttributes.nLength], 18h
0x180113684  mov     [rsp+78h+FileMappingAttributes.lpSecurityDescriptor], rax
0x180113689  mov     [rsp+78h+FileMappingAttributes.bInheritHandle], r12d
0x18011368e  call    cs:__imp_GetCurrentProcess
0x180113694  mov     rcx, rax; hFile
0x180113697  lea     rax, aGlobalMmglobal; "Global\\mmGlobalPnpInfo"
0x18011369e  mov     [rsp+78h+lpName], rax; lpName
0x1801136a3  mov     [rsp+78h+dwMaximumSizeLow], 0Ch; dwMaximumSizeLow
0x1801136ab  xor     r9d, r9d; dwMaximumSizeHigh
0x1801136ae  lea     r8d, [r9+4]; flProtect
0x1801136b2  lea     rdx, [rsp+78h+FileMappingAttributes]; lpFileMappingAttributes
0x1801136b7  call    cs:__imp_CreateFileMappingW
0x1801136bd  mov     cs:?hPnpInfo@@3PEAXEA, rax; void * hPnpInfo
0x1801136c4  test    rax, rax
0x1801136c7  jz      loc_1801137FA
0x1801136cd  mov     [rsp+78h+nLengthNeeded], r12d
0x1801136d5  lea     rcx, [rsp+78h+nLengthNeeded]
0x1801136dd  mov     qword ptr [rsp+78h+dwMaximumSizeLow], rcx; lpnLengthNeeded
0x1801136e2  xor     r9d, r9d; nLength
0x1801136e5  xor     r8d, r8d; pSecurityDescriptor
0x1801136e8  lea     edx, [r9+4]; RequestedInformation
0x1801136ec  mov     rcx, rax; Handle
0x1801136ef  call    cs:__imp_GetKernelObjectSecurity
0x1801136f5  mov     esi, eax
0x1801136f7  call    cs:__imp_GetLastError
0x1801136fd  cmp     eax, 7Ah ; 'z'
0x180113700  jnz     loc_1801137FA
0x180113706  mov     r8d, [rsp+78h+nLengthNeeded]; dwBytes
0x18011370e  xor     edx, edx; dwFlags
0x180113710  mov     rcx, cs:g_hHeap; hHeap
0x180113717  call    cs:__imp_HeapAlloc
0x18011371d  mov     r14, rax
0x180113720  test    rax, rax
0x180113723  jz      loc_1801137FA
0x180113729  lea     rax, [rsp+78h+nLengthNeeded]
0x180113731  mov     qword ptr [rsp+78h+dwMaximumSizeLow], rax; lpnLengthNeeded
0x180113736  mov     r9d, [rsp+78h+nLengthNeeded]; nLength
0x18011373e  mov     r8, r14; pSecurityDescriptor
0x180113741  mov     edx, 4; RequestedInformation
0x180113746  mov     rcx, cs:?hPnpInfo@@3PEAXEA; Handle
0x18011374d  call    cs:__imp_GetKernelObjectSecurity
0x180113753  test    eax, eax
0x180113755  jz      loc_1801137E8
0x18011375b  mov     [rsp+78h+pDacl], r12
0x180113760  mov     [rsp+78h+arg_18], r12
0x180113768  mov     [rsp+78h+bDaclPresent], r12d
0x180113770  mov     [rsp+78h+bDaclDefaulted], r12d
0x180113778  lea     r9, [rsp+78h+bDaclDefaulted]; lpbDaclDefaulted
0x180113780  lea     r8, [rsp+78h+pDacl]; pDacl
0x180113785  lea     rdx, [rsp+78h+bDaclPresent]; lpbDaclPresent
0x18011378d  mov     rcx, rdi; pSecurityDescriptor
0x180113790  call    cs:__imp_GetSecurityDescriptorDacl
0x180113796  test    eax, eax
0x180113798  jz      short loc_1801137E8
0x18011379a  cmp     [rsp+78h+bDaclPresent], r12d
0x1801137a2  jz      short loc_1801137E8
0x1801137a4  lea     r9, [rsp+78h+bDaclDefaulted]; lpbDaclDefaulted
0x1801137ac  lea     r8, [rsp+78h+arg_18]; pDacl
0x1801137b4  lea     rdx, [rsp+78h+bDaclPresent]; lpbDaclPresent
0x1801137bc  mov     rcx, r14; pSecurityDescriptor
0x1801137bf  call    cs:__imp_GetSecurityDescriptorDacl
0x1801137c5  test    eax, eax
0x1801137c7  jz      short loc_1801137E8
0x1801137c9  cmp     [rsp+78h+bDaclPresent], r12d
0x1801137d1  jz      short loc_1801137E8
0x1801137d3  mov     rdx, [rsp+78h+arg_18]; PACL
0x1801137db  mov     rcx, [rsp+78h+pDacl]; pAcl
0x1801137e0  call    ?ValidateSecurityDescriptorDacl@@YAHPEAU_ACL@@0@Z; ValidateSecurityDescriptorDacl(_ACL *,_ACL *)
0x1801137e5  mov     r15d, eax
0x1801137e8  mov     r8, r14; lpMem
0x1801137eb  xor     edx, edx; dwFlags
0x1801137ed  mov     rcx, cs:g_hHeap; hHeap
0x1801137f4  call    cs:__imp_HeapFree
0x1801137fa  mov     r8, rdi; lpMem
0x1801137fd  xor     edx, edx; dwFlags
0x1801137ff  mov     rcx, cs:g_hHeap; hHeap
0x180113806  call    cs:__imp_HeapFree
0x18011380c  test    r15d, r15d
0x18011380f  jz      loc_18011391D
0x180113815  mov     rcx, cs:?hPnpInfo@@3PEAXEA; hFileMappingObject
0x18011381c  test    rcx, rcx
0x18011381f  jz      loc_1801138F7
0x180113825  mov     qword ptr [rsp+78h+dwMaximumSizeLow], r12; dwNumberOfBytesToMap
0x18011382a  xor     r9d, r9d; dwFileOffsetLow
0x18011382d  xor     r8d, r8d; dwFileOffsetHigh
0x180113830  lea     edx, [r9+2]; dwDesiredAccess
0x180113834  call    cs:__imp_MapViewOfFile
0x18011383a  mov     cs:?g_pPnpInfoShared@@3PEAU_MMPNPINFO@@EA, rax; _MMPNPINFO * g_pPnpInfoShared
0x180113841  test    rax, rax
0x180113844  jz      short loc_1801138C5
0x180113846  xor     ecx, ecx
0x180113848  mov     [rax], rcx
0x18011384b  mov     [rax+4], rcx
0x18011384f  mov     dword ptr [rax], 0Ch
0x180113855  lea     edx, [rcx+8]; dwFlags
0x180113858  lea     r8d, [rcx+0Ch]; dwBytes
0x18011385c  mov     rcx, cs:g_hHeap; hHeap
0x180113863  call    cs:__imp_HeapAlloc
0x180113869  mov     cs:?g_pPnpInfoActual@@3PEAU_MMPNPINFO@@EA, rax; _MMPNPINFO * g_pPnpInfoActual
0x180113870  test    rax, rax
0x180113873  jz      short loc_180113890
0x180113875  mov     dword ptr [rax], 0Ch
0x18011387b  mov     rax, cs:?g_pPnpInfoActual@@3PEAU_MMPNPINFO@@EA; _MMPNPINFO * g_pPnpInfoActual
0x180113882  mov     [rax+4], r12d
0x180113886  mov     esi, 1
0x18011388b  jmp     loc_1801139EB
0x180113890  lea     rax, WPP_GLOBAL_Control
0x180113897  mov     rcx, cs:WPP_GLOBAL_Control
0x18011389e  cmp     rcx, rax
0x1801138a1  jz      loc_180113977
0x1801138a7  test    byte ptr [rcx+1Ch], 20h
0x1801138ab  jz      loc_180113977
0x1801138b1  cmp     byte ptr [rcx+19h], 4
0x1801138b5  jb      loc_180113977
0x1801138bb  mov     edx, 14h
0x1801138c0  jmp     loc_180113967
0x1801138c5  lea     rax, WPP_GLOBAL_Control
0x1801138cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1801138d3  cmp     rcx, rax
0x1801138d6  jz      loc_180113977
0x1801138dc  test    byte ptr [rcx+1Ch], 20h
0x1801138e0  jz      loc_180113977
0x1801138e6  cmp     byte ptr [rcx+19h], 4
0x1801138ea  jb      loc_180113977
0x1801138f0  mov     edx, 15h
0x1801138f5  jmp     short loc_180113967
0x1801138f7  lea     rax, WPP_GLOBAL_Control
0x1801138fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180113905  cmp     rcx, rax
0x180113908  jz      short loc_180113977
0x18011390a  test    byte ptr [rcx+1Ch], 20h
0x18011390e  jz      short loc_180113977
0x180113910  cmp     byte ptr [rcx+19h], 4
0x180113914  jb      short loc_180113977
0x180113916  mov     edx, 16h
0x18011391b  jmp     short loc_180113967
0x18011391d  lea     rax, WPP_GLOBAL_Control
0x180113924  mov     rcx, cs:WPP_GLOBAL_Control
0x18011392b  cmp     rcx, rax
0x18011392e  jz      short loc_180113977
0x180113930  test    byte ptr [rcx+1Ch], 20h
0x180113934  jz      short loc_180113977
0x180113936  cmp     byte ptr [rcx+19h], 4
0x18011393a  jb      short loc_180113977
0x18011393c  mov     edx, 17h
0x180113941  jmp     short loc_180113967
0x180113943  lea     rax, WPP_GLOBAL_Control
0x18011394a  mov     rcx, cs:WPP_GLOBAL_Control
0x180113951  cmp     rcx, rax
0x180113954  jz      short loc_180113977
0x180113956  test    byte ptr [rcx+1Ch], 20h
0x18011395a  jz      short loc_180113977
0x18011395c  cmp     byte ptr [rcx+19h], 4
0x180113960  jb      short loc_180113977
0x180113962  mov     edx, 18h
0x180113967  lea     r8, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids
0x18011396e  mov     rcx, [rcx+10h]
0x180113972  call    WPP_SF_
0x180113977  test    esi, esi
0x180113979  jnz     short loc_1801139EB
0x18011397b  mov     rax, cs:?g_pPnpInfoActual@@3PEAU_MMPNPINFO@@EA; _MMPNPINFO * g_pPnpInfoActual
0x180113982  test    rax, rax
0x180113985  jz      short loc_180113999
0x180113987  mov     r8, rax; lpMem
0x18011398a  xor     edx, edx; dwFlags
0x18011398c  mov     rcx, cs:g_hHeap; hHeap
0x180113993  call    cs:__imp_HeapFree
0x180113999  mov     rax, cs:?g_pPnpInfoShared@@3PEAU_MMPNPINFO@@EA; _MMPNPINFO * g_pPnpInfoShared
0x1801139a0  test    rax, rax
0x1801139a3  jz      short loc_1801139AE
0x1801139a5  mov     rcx, rax; lpBaseAddress
0x1801139a8  call    cs:__imp_UnmapViewOfFile
0x1801139ae  mov     rcx, cs:?hPnpInfo@@3PEAXEA; hObject
0x1801139b5  test    rcx, rcx
0x1801139b8  jz      short loc_1801139C0
0x1801139ba  call    cs:__imp_CloseHandle
0x1801139c0  cmp     cs:?gfPnpInfoResource@@3HA, r12d; int gfPnpInfoResource
0x1801139c7  jz      short loc_1801139D6
0x1801139c9  lea     rcx, ?PnpInfoResource@@3U_RTL_RESOURCE@@A; Resource
0x1801139d0  call    cs:__imp_RtlDeleteResource
0x1801139d6  mov     cs:?g_pPnpInfoShared@@3PEAU_MMPNPINFO@@EA, r12; _MMPNPINFO * g_pPnpInfoShared
0x1801139dd  mov     cs:?hPnpInfo@@3PEAXEA, r12; void * hPnpInfo
0x1801139e4  mov     cs:?gfPnpInfoResource@@3HA, r12d; int gfPnpInfoResource
0x1801139eb  mov     eax, esi
0x1801139ed  add     rsp, 50h
0x1801139f1  pop     r15
0x1801139f3  pop     r14
0x1801139f5  pop     r12
0x1801139f7  pop     rdi
0x1801139f8  pop     rsi
0x1801139f9  retn
```
