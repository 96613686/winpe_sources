# InitializePnpInfo(void)

- ea: `0x18011389c`
- end: `0x180113c7a`
- name: `?InitializePnpInfo@@YAHXZ`
- size: `990`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180113c80`

## callees

- `0x180071f50`
- `0x180113398`
- `0x18011389c`
- `0x180113dd4`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x1801138bf`
- `ntdll!RtlInitializeResource` at `0x1801138bf`
- `ntdll!RtlDeleteResource` at `0x180113c50`
- `ntdll!RtlDeleteResource` at `0x180113c50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113997`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113ae3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113997`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180113ae3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113a74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113a86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113c13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113a74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113a86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180113c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113977`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011390e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18011390e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180113c3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180113c3a`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180113937`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180113937`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180113c28`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180113c28`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180113ab4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180113ab4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180113a10`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180113a3f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180113a10`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180113a3f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18011396f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1801139cd`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18011396f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1801139cd`

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
            WPP_SF_(v9[2], v10, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids);
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
0x18011389c  push    rsi
0x18011389e  push    rdi
0x18011389f  push    r12
0x1801138a1  push    r14
0x1801138a3  push    r15
0x1801138a5  sub     rsp, 50h
0x1801138a9  xorps   xmm0, xmm0
0x1801138ac  xor     eax, eax
0x1801138ae  movups  xmmword ptr [rsp+78h+FileMappingAttributes.nLength], xmm0
0x1801138b3  mov     qword ptr [rsp+78h+FileMappingAttributes.bInheritHandle], rax
0x1801138b8  lea     rcx, ?PnpInfoResource@@3U_RTL_RESOURCE@@A; Resource
0x1801138bf  call    cs:__imp_RtlInitializeResource
0x1801138c5  mov     eax, 1
0x1801138ca  mov     cs:?gfPnpInfoResource@@3HA, eax; int gfPnpInfoResource
0x1801138d0  jmp     short loc_1801138DA
0x1801138d2  xor     eax, eax
0x1801138d4  mov     cs:?gfPnpInfoResource@@3HA, eax; int gfPnpInfoResource
0x1801138da  xor     r12d, r12d
0x1801138dd  test    eax, eax
0x1801138df  jz      loc_180113C6D
0x1801138e5  mov     esi, r12d
0x1801138e8  call    ?BuildSecurityDescriptor@@YAPEAXKK@Z; BuildSecurityDescriptor(ulong,ulong)
0x1801138ed  mov     rdi, rax
0x1801138f0  test    rax, rax
0x1801138f3  jz      loc_180113BC3
0x1801138f9  mov     r15d, r12d
0x1801138fc  mov     [rsp+78h+FileMappingAttributes.nLength], 18h
0x180113904  mov     [rsp+78h+FileMappingAttributes.lpSecurityDescriptor], rax
0x180113909  mov     [rsp+78h+FileMappingAttributes.bInheritHandle], r12d
0x18011390e  call    cs:__imp_GetCurrentProcess
0x180113914  mov     rcx, rax; hFile
0x180113917  lea     rax, aGlobalMmglobal; "Global\\mmGlobalPnpInfo"
0x18011391e  mov     [rsp+78h+lpName], rax; lpName
0x180113923  mov     [rsp+78h+dwMaximumSizeLow], 0Ch; dwMaximumSizeLow
0x18011392b  xor     r9d, r9d; dwMaximumSizeHigh
0x18011392e  lea     r8d, [r9+4]; flProtect
0x180113932  lea     rdx, [rsp+78h+FileMappingAttributes]; lpFileMappingAttributes
0x180113937  call    cs:__imp_CreateFileMappingW
0x18011393d  mov     cs:?hPnpInfo@@3PEAXEA, rax; void * hPnpInfo
0x180113944  test    rax, rax
0x180113947  jz      loc_180113A7A
0x18011394d  mov     [rsp+78h+nLengthNeeded], r12d
0x180113955  lea     rcx, [rsp+78h+nLengthNeeded]
0x18011395d  mov     qword ptr [rsp+78h+dwMaximumSizeLow], rcx; lpnLengthNeeded
0x180113962  xor     r9d, r9d; nLength
0x180113965  xor     r8d, r8d; pSecurityDescriptor
0x180113968  lea     edx, [r9+4]; RequestedInformation
0x18011396c  mov     rcx, rax; Handle
0x18011396f  call    cs:__imp_GetKernelObjectSecurity
0x180113975  mov     esi, eax
0x180113977  call    cs:__imp_GetLastError
0x18011397d  cmp     eax, 7Ah ; 'z'
0x180113980  jnz     loc_180113A7A
0x180113986  mov     r8d, [rsp+78h+nLengthNeeded]; dwBytes
0x18011398e  xor     edx, edx; dwFlags
0x180113990  mov     rcx, cs:g_hHeap; hHeap
0x180113997  call    cs:__imp_HeapAlloc
0x18011399d  mov     r14, rax
0x1801139a0  test    rax, rax
0x1801139a3  jz      loc_180113A7A
0x1801139a9  lea     rax, [rsp+78h+nLengthNeeded]
0x1801139b1  mov     qword ptr [rsp+78h+dwMaximumSizeLow], rax; lpnLengthNeeded
0x1801139b6  mov     r9d, [rsp+78h+nLengthNeeded]; nLength
0x1801139be  mov     r8, r14; pSecurityDescriptor
0x1801139c1  mov     edx, 4; RequestedInformation
0x1801139c6  mov     rcx, cs:?hPnpInfo@@3PEAXEA; Handle
0x1801139cd  call    cs:__imp_GetKernelObjectSecurity
0x1801139d3  test    eax, eax
0x1801139d5  jz      loc_180113A68
0x1801139db  mov     [rsp+78h+pDacl], r12
0x1801139e0  mov     [rsp+78h+arg_18], r12
0x1801139e8  mov     [rsp+78h+bDaclPresent], r12d
0x1801139f0  mov     [rsp+78h+bDaclDefaulted], r12d
0x1801139f8  lea     r9, [rsp+78h+bDaclDefaulted]; lpbDaclDefaulted
0x180113a00  lea     r8, [rsp+78h+pDacl]; pDacl
0x180113a05  lea     rdx, [rsp+78h+bDaclPresent]; lpbDaclPresent
0x180113a0d  mov     rcx, rdi; pSecurityDescriptor
0x180113a10  call    cs:__imp_GetSecurityDescriptorDacl
0x180113a16  test    eax, eax
0x180113a18  jz      short loc_180113A68
0x180113a1a  cmp     [rsp+78h+bDaclPresent], r12d
0x180113a22  jz      short loc_180113A68
0x180113a24  lea     r9, [rsp+78h+bDaclDefaulted]; lpbDaclDefaulted
0x180113a2c  lea     r8, [rsp+78h+arg_18]; pDacl
0x180113a34  lea     rdx, [rsp+78h+bDaclPresent]; lpbDaclPresent
0x180113a3c  mov     rcx, r14; pSecurityDescriptor
0x180113a3f  call    cs:__imp_GetSecurityDescriptorDacl
0x180113a45  test    eax, eax
0x180113a47  jz      short loc_180113A68
0x180113a49  cmp     [rsp+78h+bDaclPresent], r12d
0x180113a51  jz      short loc_180113A68
0x180113a53  mov     rdx, [rsp+78h+arg_18]; PACL
0x180113a5b  mov     rcx, [rsp+78h+pDacl]; pAcl
0x180113a60  call    ?ValidateSecurityDescriptorDacl@@YAHPEAU_ACL@@0@Z; ValidateSecurityDescriptorDacl(_ACL *,_ACL *)
0x180113a65  mov     r15d, eax
0x180113a68  mov     r8, r14; lpMem
0x180113a6b  xor     edx, edx; dwFlags
0x180113a6d  mov     rcx, cs:g_hHeap; hHeap
0x180113a74  call    cs:__imp_HeapFree
0x180113a7a  mov     r8, rdi; lpMem
0x180113a7d  xor     edx, edx; dwFlags
0x180113a7f  mov     rcx, cs:g_hHeap; hHeap
0x180113a86  call    cs:__imp_HeapFree
0x180113a8c  test    r15d, r15d
0x180113a8f  jz      loc_180113B9D
0x180113a95  mov     rcx, cs:?hPnpInfo@@3PEAXEA; hFileMappingObject
0x180113a9c  test    rcx, rcx
0x180113a9f  jz      loc_180113B77
0x180113aa5  mov     qword ptr [rsp+78h+dwMaximumSizeLow], r12; dwNumberOfBytesToMap
0x180113aaa  xor     r9d, r9d; dwFileOffsetLow
0x180113aad  xor     r8d, r8d; dwFileOffsetHigh
0x180113ab0  lea     edx, [r9+2]; dwDesiredAccess
0x180113ab4  call    cs:__imp_MapViewOfFile
0x180113aba  mov     cs:?g_pPnpInfoShared@@3PEAU_MMPNPINFO@@EA, rax; _MMPNPINFO * g_pPnpInfoShared
0x180113ac1  test    rax, rax
0x180113ac4  jz      short loc_180113B45
0x180113ac6  xor     ecx, ecx
0x180113ac8  mov     [rax], rcx
0x180113acb  mov     [rax+4], rcx
0x180113acf  mov     dword ptr [rax], 0Ch
0x180113ad5  lea     edx, [rcx+8]; dwFlags
0x180113ad8  lea     r8d, [rcx+0Ch]; dwBytes
0x180113adc  mov     rcx, cs:g_hHeap; hHeap
0x180113ae3  call    cs:__imp_HeapAlloc
0x180113ae9  mov     cs:?g_pPnpInfoActual@@3PEAU_MMPNPINFO@@EA, rax; _MMPNPINFO * g_pPnpInfoActual
0x180113af0  test    rax, rax
0x180113af3  jz      short loc_180113B10
0x180113af5  mov     dword ptr [rax], 0Ch
0x180113afb  mov     rax, cs:?g_pPnpInfoActual@@3PEAU_MMPNPINFO@@EA; _MMPNPINFO * g_pPnpInfoActual
0x180113b02  mov     [rax+4], r12d
0x180113b06  mov     esi, 1
0x180113b0b  jmp     loc_180113C6B
0x180113b10  lea     rax, WPP_GLOBAL_Control
0x180113b17  mov     rcx, cs:WPP_GLOBAL_Control
0x180113b1e  cmp     rcx, rax
0x180113b21  jz      loc_180113BF7
0x180113b27  test    byte ptr [rcx+1Ch], 20h
0x180113b2b  jz      loc_180113BF7
0x180113b31  cmp     byte ptr [rcx+19h], 4
0x180113b35  jb      loc_180113BF7
0x180113b3b  mov     edx, 14h
0x180113b40  jmp     loc_180113BE7
0x180113b45  lea     rax, WPP_GLOBAL_Control
0x180113b4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180113b53  cmp     rcx, rax
0x180113b56  jz      loc_180113BF7
0x180113b5c  test    byte ptr [rcx+1Ch], 20h
0x180113b60  jz      loc_180113BF7
0x180113b66  cmp     byte ptr [rcx+19h], 4
0x180113b6a  jb      loc_180113BF7
0x180113b70  mov     edx, 15h
0x180113b75  jmp     short loc_180113BE7
0x180113b77  lea     rax, WPP_GLOBAL_Control
0x180113b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180113b85  cmp     rcx, rax
0x180113b88  jz      short loc_180113BF7
0x180113b8a  test    byte ptr [rcx+1Ch], 20h
0x180113b8e  jz      short loc_180113BF7
0x180113b90  cmp     byte ptr [rcx+19h], 4
0x180113b94  jb      short loc_180113BF7
0x180113b96  mov     edx, 16h
0x180113b9b  jmp     short loc_180113BE7
0x180113b9d  lea     rax, WPP_GLOBAL_Control
0x180113ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180113bab  cmp     rcx, rax
0x180113bae  jz      short loc_180113BF7
0x180113bb0  test    byte ptr [rcx+1Ch], 20h
0x180113bb4  jz      short loc_180113BF7
0x180113bb6  cmp     byte ptr [rcx+19h], 4
0x180113bba  jb      short loc_180113BF7
0x180113bbc  mov     edx, 17h
0x180113bc1  jmp     short loc_180113BE7
0x180113bc3  lea     rax, WPP_GLOBAL_Control
0x180113bca  mov     rcx, cs:WPP_GLOBAL_Control
0x180113bd1  cmp     rcx, rax
0x180113bd4  jz      short loc_180113BF7
0x180113bd6  test    byte ptr [rcx+1Ch], 20h
0x180113bda  jz      short loc_180113BF7
0x180113bdc  cmp     byte ptr [rcx+19h], 4
0x180113be0  jb      short loc_180113BF7
0x180113be2  mov     edx, 18h
0x180113be7  lea     r8, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids
0x180113bee  mov     rcx, [rcx+10h]
0x180113bf2  call    WPP_SF_
0x180113bf7  test    esi, esi
0x180113bf9  jnz     short loc_180113C6B
0x180113bfb  mov     rax, cs:?g_pPnpInfoActual@@3PEAU_MMPNPINFO@@EA; _MMPNPINFO * g_pPnpInfoActual
0x180113c02  test    rax, rax
0x180113c05  jz      short loc_180113C19
0x180113c07  mov     r8, rax; lpMem
0x180113c0a  xor     edx, edx; dwFlags
0x180113c0c  mov     rcx, cs:g_hHeap; hHeap
0x180113c13  call    cs:__imp_HeapFree
0x180113c19  mov     rax, cs:?g_pPnpInfoShared@@3PEAU_MMPNPINFO@@EA; _MMPNPINFO * g_pPnpInfoShared
0x180113c20  test    rax, rax
0x180113c23  jz      short loc_180113C2E
0x180113c25  mov     rcx, rax; lpBaseAddress
0x180113c28  call    cs:__imp_UnmapViewOfFile
0x180113c2e  mov     rcx, cs:?hPnpInfo@@3PEAXEA; hObject
0x180113c35  test    rcx, rcx
0x180113c38  jz      short loc_180113C40
0x180113c3a  call    cs:__imp_CloseHandle
0x180113c40  cmp     cs:?gfPnpInfoResource@@3HA, r12d; int gfPnpInfoResource
0x180113c47  jz      short loc_180113C56
0x180113c49  lea     rcx, ?PnpInfoResource@@3U_RTL_RESOURCE@@A; Resource
0x180113c50  call    cs:__imp_RtlDeleteResource
0x180113c56  mov     cs:?g_pPnpInfoShared@@3PEAU_MMPNPINFO@@EA, r12; _MMPNPINFO * g_pPnpInfoShared
0x180113c5d  mov     cs:?hPnpInfo@@3PEAXEA, r12; void * hPnpInfo
0x180113c64  mov     cs:?gfPnpInfoResource@@3HA, r12d; int gfPnpInfoResource
0x180113c6b  mov     eax, esi
0x180113c6d  add     rsp, 50h
0x180113c71  pop     r15
0x180113c73  pop     r14
0x180113c75  pop     r12
0x180113c77  pop     rdi
0x180113c78  pop     rsi
0x180113c79  retn
```
