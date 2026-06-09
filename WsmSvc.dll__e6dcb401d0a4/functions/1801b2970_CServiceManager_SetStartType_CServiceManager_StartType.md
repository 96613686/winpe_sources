# CServiceManager::SetStartType(CServiceManager::StartType)

- ea: `0x1801b2970`
- end: `0x1801b2b6c`
- name: `?SetStartType@CServiceManager@@QEAAHW4StartType@1@@Z`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180107144`

## callees

- `0x180005d10`
- `0x1801123a8`
- `0x180112460`
- `0x18011d96c`
- `0x1801b2970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b29f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b29f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2af3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2af3`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1801b2a82`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1801b2a82`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1801b2ad2`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1801b2ad2`

## string_xrefs

- `0x1801b2a25`: `onecore\admin\wmi\wmx\providers\config\cservicemanager.cpp`

## pseudocode

```c
__int64 __fastcall CServiceManager::SetStartType(__int64 a1, int a2)
{
  PVOID *v4; // rcx
  unsigned int v6; // esi
  PVOID *v7; // rcx
  DWORD LastError; // eax
  __int64 v9; // rdx
  SC_HANDLE v10; // rcx
  PVOID v11; // rcx
  const wchar_t *v12; // rax
  int Info; // [rsp+80h] [rbp+8h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_131781640eb33655e7041cbe01785ecd_Traceguids, a1, a2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*(_DWORD *)a1 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x400000) != 0 )
      WPP_SF_d(v4[2], 24, WPP_131781640eb33655e7041cbe01785ecd_Traceguids, *(unsigned int *)(a1 + 4));
    SetLastError(*(_DWORD *)(a1 + 4));
    return 0;
  }
  if ( (unsigned int)(a2 - 2) > 1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\providers\\config\\cservicemanager.cpp", 249, L"249", 0x54Fu, 0);
    return 0;
  }
  v6 = ChangeServiceConfigW(*(SC_HANDLE *)(a1 + 16), 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0);
  if ( v6 )
  {
    if ( a2 != 3 )
      goto LABEL_22;
    v10 = *(SC_HANDLE *)(a1 + 16);
    Info = 1;
    v6 = ChangeServiceConfig2W(v10, 3u, &Info);
    if ( v6 )
      goto LABEL_22;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        LastError = GetLastError();
        v9 = 26;
        goto LABEL_21;
      }
LABEL_23:
      if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x200000) != 0 )
      {
        v11 = v7[2];
        v12 = L"changed";
        if ( !v6 )
          v12 = L"change failed";
        WPP_SF_qS((_DWORD)v11, 27, (unsigned int)WPP_131781640eb33655e7041cbe01785ecd_Traceguids, a1, (__int64)v12);
      }
    }
  }
  else
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        LastError = GetLastError();
        v9 = 25;
LABEL_21:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_131781640eb33655e7041cbe01785ecd_Traceguids, LastError);
LABEL_22:
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_23;
      }
      goto LABEL_23;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1801b2970  mov     [rsp+arg_8], rbx
0x1801b2975  mov     [rsp+arg_10], rsi
0x1801b297a  push    rdi
0x1801b297b  push    r14
0x1801b297d  push    r15
0x1801b297f  sub     rsp, 60h
0x1801b2983  mov     edi, edx
0x1801b2985  mov     rbx, rcx
0x1801b2988  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b298f  lea     r14, WPP_GLOBAL_Control
0x1801b2996  lea     r15, WPP_131781640eb33655e7041cbe01785ecd_Traceguids
0x1801b299d  cmp     rcx, r14
0x1801b29a0  jz      short loc_1801B29CA
0x1801b29a2  test    dword ptr [rcx+1Ch], 200000h
0x1801b29a9  jz      short loc_1801B29CA
0x1801b29ab  mov     rcx, [rcx+10h]
0x1801b29af  mov     edx, 17h
0x1801b29b4  mov     r9, rbx
0x1801b29b7  mov     dword ptr [rsp+78h+lpBinaryPathName], edi
0x1801b29bb  mov     r8, r15
0x1801b29be  call    WPP_SF_qD
0x1801b29c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b29ca  cmp     dword ptr [rbx], 0
0x1801b29cd  jnz     short loc_1801B2A02
0x1801b29cf  cmp     rcx, r14
0x1801b29d2  jz      short loc_1801B29F2
0x1801b29d4  test    dword ptr [rcx+1Ch], 400000h
0x1801b29db  jz      short loc_1801B29F2
0x1801b29dd  mov     r9d, [rbx+4]
0x1801b29e1  mov     edx, 18h
0x1801b29e6  mov     rcx, [rcx+10h]
0x1801b29ea  mov     r8, r15
0x1801b29ed  call    WPP_SF_d
0x1801b29f2  mov     ecx, [rbx+4]; dwErrCode
0x1801b29f5  call    cs:__imp_SetLastError
0x1801b29fb  xor     eax, eax
0x1801b29fd  jmp     loc_1801B2B56
0x1801b2a02  lea     eax, [rdi-2]
0x1801b2a05  cmp     eax, 1
0x1801b2a08  jbe     short loc_1801B2A33
0x1801b2a0a  mov     r9d, 54Fh; unsigned int
0x1801b2a10  mov     [rsp+78h+lpBinaryPathName], 0; struct IRequestContext *
0x1801b2a19  lea     r8, a249; "249"
0x1801b2a20  mov     edx, 0F9h; unsigned int
0x1801b2a25  lea     rcx, aOnecoreAdminWm_158; "onecore\\admin\\wmi\\wmx\\providers\\co"...
0x1801b2a2c  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801b2a31  jmp     short loc_1801B29FB
0x1801b2a33  mov     rcx, [rbx+10h]; hService
0x1801b2a37  or      edx, 0FFFFFFFFh; dwServiceType
0x1801b2a3a  mov     [rsp+78h+lpDisplayName], 0; lpDisplayName
0x1801b2a43  mov     r9d, edx; dwErrorControl
0x1801b2a46  mov     [rsp+78h+lpPassword], 0; lpPassword
0x1801b2a4f  mov     r8d, 2; dwStartType
0x1801b2a55  mov     [rsp+78h+lpServiceStartName], 0; lpServiceStartName
0x1801b2a5e  mov     [rsp+78h+lpDependencies], 0; lpDependencies
0x1801b2a67  mov     [rsp+78h+lpdwTagId], 0; lpdwTagId
0x1801b2a70  mov     [rsp+78h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x1801b2a79  mov     [rsp+78h+lpBinaryPathName], 0; lpBinaryPathName
0x1801b2a82  call    cs:__imp_ChangeServiceConfigW
0x1801b2a88  mov     esi, eax
0x1801b2a8a  test    eax, eax
0x1801b2a8c  jnz     short loc_1801B2AB2
0x1801b2a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b2a95  cmp     rcx, r14
0x1801b2a98  jz      loc_1801B2B54
0x1801b2a9e  test    dword ptr [rcx+1Ch], 400000h
0x1801b2aa5  jz      short loc_1801B2B19
0x1801b2aa7  call    cs:__imp_GetLastError
0x1801b2aad  lea     edx, [rsi+19h]
0x1801b2ab0  jmp     short loc_1801B2AFC
0x1801b2ab2  mov     edx, 3; dwInfoLevel
0x1801b2ab7  cmp     edi, edx
0x1801b2ab9  jnz     short loc_1801B2B12
0x1801b2abb  mov     rcx, [rbx+10h]; hService
0x1801b2abf  lea     r8, [rsp+78h+Info]; lpInfo
0x1801b2ac7  mov     [rsp+78h+Info], 1
0x1801b2ad2  call    cs:__imp_ChangeServiceConfig2W
0x1801b2ad8  mov     esi, eax
0x1801b2ada  test    eax, eax
0x1801b2adc  jnz     short loc_1801B2B12
0x1801b2ade  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b2ae5  cmp     rcx, r14
0x1801b2ae8  jz      short loc_1801B2B54
0x1801b2aea  test    dword ptr [rcx+1Ch], 400000h
0x1801b2af1  jz      short loc_1801B2B19
0x1801b2af3  call    cs:__imp_GetLastError
0x1801b2af9  lea     edx, [rsi+1Ah]
0x1801b2afc  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b2b03  mov     r9d, eax
0x1801b2b06  mov     r8, r15
0x1801b2b09  mov     rcx, [rcx+10h]
0x1801b2b0d  call    WPP_SF_d
0x1801b2b12  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b2b19  cmp     rcx, r14
0x1801b2b1c  jz      short loc_1801B2B54
0x1801b2b1e  test    dword ptr [rcx+1Ch], 200000h
0x1801b2b25  jz      short loc_1801B2B54
0x1801b2b27  mov     rcx, [rcx+10h]
0x1801b2b2b  lea     rdx, aChangeFailed; "change failed"
0x1801b2b32  test    esi, esi
0x1801b2b34  lea     rax, aChanged; "changed"
0x1801b2b3b  mov     r9, rbx
0x1801b2b3e  mov     r8, r15
0x1801b2b41  cmovz   rax, rdx
0x1801b2b45  mov     edx, 1Bh
0x1801b2b4a  mov     [rsp+78h+lpBinaryPathName], rax
0x1801b2b4f  call    WPP_SF_qS
0x1801b2b54  mov     eax, esi
0x1801b2b56  lea     r11, [rsp+78h+var_18]
0x1801b2b5b  mov     rbx, [r11+28h]
0x1801b2b5f  mov     rsi, [r11+30h]
0x1801b2b63  mov     rsp, r11
0x1801b2b66  pop     r15
0x1801b2b68  pop     r14
0x1801b2b6a  pop     rdi
0x1801b2b6b  retn
```
