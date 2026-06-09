# CServiceManager::CheckStartType(CServiceManager::StartType *)

- ea: `0x1801b2798`
- end: `0x1801b2969`
- name: `?CheckStartType@CServiceManager@@QEAAHPEAW4StartType@1@@Z`
- size: `465`
- prototype: `__int64 __fastcall(CServiceManager *__hidden this, enum CServiceManager::StartType *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180107668`

## callees

- `0x180008920`
- `0x1800621e0`
- `0x1801123a8`
- `0x18011a6d4`
- `0x180123604`
- `0x1801b2798`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b2814`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b2854`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b2814`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b2854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b289c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b289c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1801b2903`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1801b2903`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1801b2873`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1801b2873`

## pseudocode

```c
__int64 __fastcall CServiceManager::CheckStartType(CServiceManager *this, enum CServiceManager::StartType *a2)
{
  PVOID *v4; // rcx
  struct _QUERY_SERVICE_CONFIGW *v6; // rax
  struct _QUERY_SERVICE_CONFIGW *v7; // rsi
  unsigned int v8; // edi
  PVOID *v9; // rcx
  DWORD LastError; // eax
  SC_HANDLE v11; // rcx
  struct _QUERY_SERVICE_CONFIGW *v12; // [rsp+30h] [rbp-38h] BYREF
  int Buffer; // [rsp+70h] [rbp+8h] BYREF
  DWORD pcbBytesNeeded; // [rsp+80h] [rbp+18h] BYREF
  DWORD v15; // [rsp+88h] [rbp+20h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_131781640eb33655e7041cbe01785ecd_Traceguids, this);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)this )
  {
    pcbBytesNeeded = 0;
    *(_DWORD *)a2 = 1;
    v6 = (struct _QUERY_SERVICE_CONFIGW *)WSManMemory::Alloc(0x2000, 0, 0);
    v12 = v6;
    v7 = v6;
    if ( !v6 )
    {
      SetLastError(0xEu);
      v8 = 0;
LABEL_23:
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v12);
      return v8;
    }
    v8 = QueryServiceConfigW(*((SC_HANDLE *)this + 2), v6, 0x2000u, &pcbBytesNeeded);
    if ( v8 )
    {
      if ( v7->dwStartType == 2 )
      {
        *(_DWORD *)a2 = 2;
        v11 = (SC_HANDLE)*((_QWORD *)this + 2);
        Buffer = 0;
        v15 = 0;
        v8 = QueryServiceConfig2W(v11, 3u, (LPBYTE)&Buffer, 4u, &v15);
        if ( v8 )
        {
          if ( Buffer )
            *(_DWORD *)a2 = 3;
        }
      }
    }
    else
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_23;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      {
LABEL_20:
        if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x200000) != 0 )
          WPP_SF_qLd(v9[2], 19, WPP_131781640eb33655e7041cbe01785ecd_Traceguids, this, v8, *(_DWORD *)a2);
        goto LABEL_23;
      }
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_131781640eb33655e7041cbe01785ecd_Traceguids, LastError);
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x400000) != 0 )
    WPP_SF_d(v4[2], 17, WPP_131781640eb33655e7041cbe01785ecd_Traceguids, *((unsigned int *)this + 1));
  SetLastError(*((_DWORD *)this + 1));
  return 0;
}

```

## disassembly

```asm
0x1801b2798  push    rbx
0x1801b279a  push    rsi
0x1801b279b  push    rdi
0x1801b279c  push    r14
0x1801b279e  push    r15
0x1801b27a0  sub     rsp, 40h
0x1801b27a4  mov     r14, rdx
0x1801b27a7  mov     rbx, rcx
0x1801b27aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b27b1  lea     r15, WPP_GLOBAL_Control
0x1801b27b8  cmp     rcx, r15
0x1801b27bb  jz      short loc_1801B27E5
0x1801b27bd  test    dword ptr [rcx+1Ch], 200000h
0x1801b27c4  jz      short loc_1801B27E5
0x1801b27c6  mov     rcx, [rcx+10h]
0x1801b27ca  lea     r8, WPP_131781640eb33655e7041cbe01785ecd_Traceguids
0x1801b27d1  mov     edx, 10h
0x1801b27d6  mov     r9, rbx
0x1801b27d9  call    WPP_SF_q
0x1801b27de  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b27e5  cmp     dword ptr [rbx], 0
0x1801b27e8  jnz     short loc_1801B2821
0x1801b27ea  cmp     rcx, r15
0x1801b27ed  jz      short loc_1801B2811
0x1801b27ef  test    dword ptr [rcx+1Ch], 400000h
0x1801b27f6  jz      short loc_1801B2811
0x1801b27f8  mov     r9d, [rbx+4]
0x1801b27fc  lea     r8, WPP_131781640eb33655e7041cbe01785ecd_Traceguids
0x1801b2803  mov     rcx, [rcx+10h]
0x1801b2807  mov     edx, 11h
0x1801b280c  call    WPP_SF_d
0x1801b2811  mov     ecx, [rbx+4]; dwErrCode
0x1801b2814  call    cs:__imp_SetLastError
0x1801b281a  xor     eax, eax
0x1801b281c  jmp     loc_1801B295D
0x1801b2821  mov     edi, 2000h
0x1801b2826  mov     [rsp+68h+pcbBytesNeeded], 0
0x1801b2831  mov     ecx, edi
0x1801b2833  mov     dword ptr [r14], 1
0x1801b283a  xor     r8d, r8d
0x1801b283d  xor     edx, edx
0x1801b283f  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1801b2844  mov     [rsp+68h+var_38], rax
0x1801b2849  mov     rsi, rax
0x1801b284c  test    rax, rax
0x1801b284f  jnz     short loc_1801B2861
0x1801b2851  lea     ecx, [rax+0Eh]; dwErrCode
0x1801b2854  call    cs:__imp_SetLastError
0x1801b285a  xor     edi, edi
0x1801b285c  jmp     loc_1801B2951
0x1801b2861  mov     rcx, [rbx+10h]; hService
0x1801b2865  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x1801b286d  mov     r8d, edi; cbBufSize
0x1801b2870  mov     rdx, rsi; lpServiceConfig
0x1801b2873  call    cs:__imp_QueryServiceConfigW
0x1801b2879  mov     edi, eax
0x1801b287b  test    eax, eax
0x1801b287d  jnz     short loc_1801B28C1
0x1801b287f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b2886  cmp     rcx, r15
0x1801b2889  jz      loc_1801B2951
0x1801b288f  test    dword ptr [rcx+1Ch], 400000h
0x1801b2896  jz      loc_1801B2920
0x1801b289c  call    cs:__imp_GetLastError
0x1801b28a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b28a9  lea     edx, [rdi+12h]
0x1801b28ac  mov     r9d, eax
0x1801b28af  lea     r8, WPP_131781640eb33655e7041cbe01785ecd_Traceguids
0x1801b28b6  mov     rcx, [rcx+10h]
0x1801b28ba  call    WPP_SF_d
0x1801b28bf  jmp     short loc_1801B2919
0x1801b28c1  cmp     dword ptr [rsi+4], 2
0x1801b28c5  jnz     short loc_1801B2919
0x1801b28c7  mov     r9d, 4; cbBufSize
0x1801b28cd  mov     dword ptr [r14], 2
0x1801b28d4  mov     rcx, [rbx+10h]; hService
0x1801b28d8  lea     rax, [rsp+68h+arg_18]
0x1801b28e0  lea     r8, [rsp+68h+Buffer]; lpBuffer
0x1801b28e5  mov     [rsp+68h+Buffer], 0
0x1801b28ed  mov     [rsp+68h+arg_18], 0
0x1801b28f8  lea     esi, [r9-1]
0x1801b28fc  mov     [rsp+68h+var_48], rax; pcbBytesNeeded
0x1801b2901  mov     edx, esi; dwInfoLevel
0x1801b2903  call    cs:__imp_QueryServiceConfig2W
0x1801b2909  mov     edi, eax
0x1801b290b  test    eax, eax
0x1801b290d  jz      short loc_1801B2919
0x1801b290f  cmp     [rsp+68h+Buffer], 0
0x1801b2914  jz      short loc_1801B2919
0x1801b2916  mov     [r14], esi
0x1801b2919  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b2920  cmp     rcx, r15
0x1801b2923  jz      short loc_1801B2951
0x1801b2925  test    dword ptr [rcx+1Ch], 200000h
0x1801b292c  jz      short loc_1801B2951
0x1801b292e  mov     eax, [r14]
0x1801b2931  lea     r8, WPP_131781640eb33655e7041cbe01785ecd_Traceguids
0x1801b2938  mov     rcx, [rcx+10h]
0x1801b293c  mov     edx, 13h
0x1801b2941  mov     [rsp+68h+var_40], eax
0x1801b2945  mov     r9, rbx
0x1801b2948  mov     dword ptr [rsp+68h+var_48], edi
0x1801b294c  call    WPP_SF_qLd
0x1801b2951  lea     rcx, [rsp+68h+var_38]
0x1801b2956  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1801b295b  mov     eax, edi
0x1801b295d  add     rsp, 40h
0x1801b2961  pop     r15
0x1801b2963  pop     r14
0x1801b2965  pop     rdi
0x1801b2966  pop     rsi
0x1801b2967  pop     rbx
0x1801b2968  retn
```
