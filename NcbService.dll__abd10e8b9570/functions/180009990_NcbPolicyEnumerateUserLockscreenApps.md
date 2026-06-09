# NcbPolicyEnumerateUserLockscreenApps

- ea: `0x180009990`
- end: `0x180009dc9`
- name: `NcbPolicyEnumerateUserLockscreenApps`
- size: `1081`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007314`
- `0x180007a70`

## callees

- `0x180009990`
- `0x18000a0a0`
- `0x18000a160`
- `0x18000a1c0`
- `0x18001d8e0`
- `0x180033010`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x180009be5`
- `ntdll!RtlLookupEntryHashTable` at `0x180009be5`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009c26`
- `ntdll!RtlGetNextEntryHashTable` at `0x180009c26`
- `ntdll!RtlInsertEntryHashTable` at `0x180009cbc`
- `ntdll!RtlInsertEntryHashTable` at `0x180009cbc`
- `ntdll!RtlFreeSid` at `0x180009ccb`
- `ntdll!RtlFreeSid` at `0x180009ccb`
- `ntdll!RtlEqualSid` at `0x180009bff`
- `ntdll!RtlEqualSid` at `0x180009c10`
- `ntdll!RtlEqualSid` at `0x180009bff`
- `ntdll!RtlEqualSid` at `0x180009c10`
- `ntdll!RtlLengthSid` at `0x180009b9a`
- `ntdll!RtlLengthSid` at `0x180009c7b`
- `ntdll!RtlLengthSid` at `0x180009b9a`
- `ntdll!RtlLengthSid` at `0x180009c7b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180009d66`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180009d66`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009a1e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009a1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009cdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ceb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009cdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ceb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d36`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800099f0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800099f0`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180009b64`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180009b64`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180009b4d`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180009b4d`

## string_xrefs

- `0x180009db8`: `NcbPolicy: AppContainerDeriveSidFromMoniker failed with error - `

## pseudocode

```c
void __fastcall NcbPolicyEnumerateUserLockscreenApps(unsigned __int8 *Sid, __int64 a2)
{
  unsigned __int8 *v3; // r14
  __int64 v4; // r8
  unsigned int i; // r13d
  __int64 v6; // r12
  const WCHAR *v7; // r15
  unsigned __int16 *v8; // rdi
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  PSID v15; // rsi
  ULONG v16; // eax
  unsigned __int8 *v17; // r8
  unsigned int v18; // ecx
  ULONG j; // r9d
  int v20; // edx
  __int64 NextEntryHashTable; // rax
  __int64 v22; // rbx
  unsigned __int16 *v23; // rcx
  int v24; // edx
  int v25; // eax
  __int64 Policy; // rax
  __int64 v27; // rdi
  unsigned __int8 *v28; // rbx
  ULONG v29; // eax
  unsigned int v30; // edx
  ULONG k; // r8d
  int v32; // ecx
  unsigned int v33; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v36; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  PSID Sida; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid1; // [rsp+68h] [rbp-98h]
  __int128 v41; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v42; // [rsp+80h] [rbp-80h]
  __int64 v43; // [rsp+88h] [rbp-78h]
  UINT32 *p_packageFamilyNameLength; // [rsp+90h] [rbp-70h]
  __int64 v45; // [rsp+98h] [rbp-68h]
  WCHAR packageFamilyName[264]; // [rsp+A0h] [rbp-60h] BYREF

  Sid1 = Sid;
  v3 = Sid;
  ppv = 0;
  v37 = 0;
  v33 = 0;
  pv = 0;
  v36 = 0;
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    if ( CoCreateInstance(
           &GUID_d648fea1_ea00_4ff4_b8bd_034bd2b25a23,
           0,
           1u,
           &GUID_9a12b667_ddbe_4fe9_9279_520c986e61d4,
           &ppv) >= 0 )
    {
      if ( (*(int (__fastcall **)(LPVOID, __int64, SID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             a2,
             &SID_BackgroundAccessManagerService,
             &GUID_428d4ddd_3462_43df_9395_1eff13ae7a4b,
             &v37) >= 0 )
      {
        if ( (*(int (__fastcall **)(__int64, __int64, unsigned int *, LPVOID *, LPVOID *))(*(_QWORD *)v37 + 144LL))(
               v37,
               a2,
               &v33,
               &pv,
               &v36) >= 0 )
        {
          for ( i = 0; i < v33; ++i )
          {
            v6 = 8LL * i;
            v7 = *(const WCHAR **)((char *)v36 + v6);
            v8 = *(unsigned __int16 **)((char *)pv + v6);
            if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            {
              packageFamilyNameLength = 0;
              p_packageFamilyNameLength = &packageFamilyNameLength;
              v42 = L"NcbPolicy: NcbPolicyOnAppLockScreenAddHandlerUnderLock called - ";
              v43 = 130;
              v45 = 4;
              McGenEventWrite_EventWriteTransfer(
                L"NcbPolicy: NcbPolicyOnAppLockScreenAddHandlerUnderLock called - ",
                NcbApiStatus,
                v4,
                3,
                &v41);
            }
            Sida = 0;
            packageFamilyNameLength = 260;
            v9 = PackageFamilyNameFromFullName(v7, &packageFamilyNameLength, packageFamilyName);
            if ( v9 )
            {
              if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
                McTemplateU0zq_EventWriteTransfer(
                  v11,
                  v10,
                  L"NcbPolicy: PackageFamilyNameFromFullName failed with error - ",
                  v9);
            }
            else
            {
              v12 = AppContainerDeriveSidFromMoniker(packageFamilyName, &Sida);
              if ( v12 < 0 )
              {
                if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
                  McTemplateU0zq_EventWriteTransfer(
                    v14,
                    v13,
                    L"NcbPolicy: AppContainerDeriveSidFromMoniker failed with error - ",
                    (unsigned int)v12);
              }
              else
              {
                v15 = Sida;
                if ( Sida )
                {
                  v42 = 0;
                  v41 = 0;
                  if ( v3 )
                  {
                    v16 = RtlLengthSid(v3);
                    v17 = v3;
                    v18 = 0;
                    for ( j = 0; j < v16; v18 = v20 + 37 * v18 )
                    {
                      v20 = *v17++;
                      ++j;
                    }
                    v41 = 0;
                    NextEntryHashTable = RtlLookupEntryHashTable(g_NcbPolicies, v18 | 0x80000000LL, &v41);
                    v3 = (unsigned __int8 *)Sid1;
                    while ( 1 )
                    {
                      v22 = NextEntryHashTable;
                      if ( !NextEntryHashTable )
                        break;
                      if ( RtlEqualSid(v3, *(PSID *)(NextEntryHashTable + 24)) && RtlEqualSid(v15, *(PSID *)(v22 + 40)) )
                      {
                        if ( !v8 )
                          goto LABEL_29;
                        v23 = v8;
                        do
                        {
                          v24 = *(unsigned __int16 *)((char *)v23 + *(_QWORD *)(v22 + 48) - (_QWORD)v8);
                          v25 = *v23 - v24;
                          if ( v25 )
                            break;
                          ++v23;
                        }
                        while ( v24 );
                        if ( !v25 )
                          goto LABEL_29;
                      }
                      NextEntryHashTable = RtlGetNextEntryHashTable(g_NcbPolicies, &v41);
                    }
                  }
                  Policy = NcbPolicyCreatePolicy(v3, v15);
                  v27 = Policy;
                  if ( Policy )
                  {
                    v28 = *(unsigned __int8 **)(Policy + 24);
                    v29 = RtlLengthSid(v28);
                    v30 = 0;
                    for ( k = 0; k < v29; v30 = v32 + 37 * v30 )
                    {
                      v32 = *v28++;
                      ++k;
                    }
                    RtlInsertEntryHashTable(g_NcbPolicies, v27, v30 | 0x80000000LL, 0);
                    ++g_NcbPolicyCounter;
                  }
LABEL_29:
                  RtlFreeSid(v15);
                }
              }
            }
            CoTaskMemFree(*(LPVOID *)((char *)pv + v6));
            CoTaskMemFree(*(LPVOID *)((char *)v36 + v6));
          }
          CoTaskMemFree(pv);
          CoTaskMemFree(v36);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x180009990  push    rbp
0x180009992  push    rbx
0x180009993  push    r14
0x180009995  lea     rbp, [rsp-1E0h]
0x18000999d  sub     rsp, 2E0h
0x1800099a4  mov     rax, cs:__security_cookie
0x1800099ab  xor     rax, rsp
0x1800099ae  mov     [rbp+1F0h+var_40], rax
0x1800099b5  mov     rbx, rdx
0x1800099b8  mov     [rsp+2F0h+Sid1], rcx
0x1800099bd  mov     r14, rcx
0x1800099c0  mov     [rsp+2F0h+var_298], 0
0x1800099c9  xor     edx, edx; dwCoInit
0x1800099cb  mov     [rsp+2F0h+var_2A0], 0
0x1800099d4  xor     ecx, ecx; pvReserved
0x1800099d6  mov     [rsp+2F0h+var_2C0], 0
0x1800099de  mov     [rsp+2F0h+pv], 0
0x1800099e7  mov     [rsp+2F0h+var_2A8], 0
0x1800099f0  call    cs:__imp_CoInitializeEx
0x1800099f6  test    eax, eax
0x1800099f8  js      loc_180009D6C
0x1800099fe  lea     rax, [rsp+2F0h+var_298]
0x180009a03  xor     edx, edx; pUnkOuter
0x180009a05  lea     r9, _GUID_9a12b667_ddbe_4fe9_9279_520c986e61d4; riid
0x180009a0c  mov     [rsp+2F0h+ppv], rax; ppv
0x180009a11  mov     r8d, 1; dwClsContext
0x180009a17  lea     rcx, _GUID_d648fea1_ea00_4ff4_b8bd_034bd2b25a23; rclsid
0x180009a1e  call    cs:__imp_CoCreateInstance
0x180009a24  test    eax, eax
0x180009a26  js      loc_180009D66
0x180009a2c  mov     rcx, [rsp+2F0h+var_298]
0x180009a31  lea     rdx, [rsp+2F0h+var_2A0]
0x180009a36  mov     [rsp+2F0h+ppv], rdx
0x180009a3b  lea     r9, _GUID_428d4ddd_3462_43df_9395_1eff13ae7a4b
0x180009a42  lea     r8, SID_BackgroundAccessManagerService
0x180009a49  mov     rdx, rbx
0x180009a4c  mov     rax, [rcx]
0x180009a4f  mov     rax, [rax+18h]
0x180009a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a58  test    eax, eax
0x180009a5a  js      loc_180009D55
0x180009a60  mov     rcx, [rsp+2F0h+var_2A0]
0x180009a65  lea     rdx, [rsp+2F0h+var_2A8]
0x180009a6a  mov     [rsp+2F0h+ppv], rdx
0x180009a6f  lea     r9, [rsp+2F0h+pv]
0x180009a74  lea     r8, [rsp+2F0h+var_2C0]
0x180009a79  mov     rdx, rbx
0x180009a7c  mov     rax, [rcx]
0x180009a7f  mov     rax, [rax+90h]
0x180009a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a8b  test    eax, eax
0x180009a8d  js      loc_180009D44
0x180009a93  xor     ebx, ebx
0x180009a95  mov     [rsp+2F0h+var_28], r13
0x180009a9d  mov     r13d, ebx
0x180009aa0  cmp     [rsp+2F0h+var_2C0], ebx
0x180009aa4  jbe     loc_180009D26
0x180009aaa  mov     [rsp+2F0h+arg_10], rsi
0x180009ab2  lea     rcx, aNcbpolicyNcbpo_10; "NcbPolicy: NcbPolicyOnAppLockScreenAddH"...
0x180009ab9  mov     [rsp+2F0h+var_18], rdi
0x180009ac1  mov     [rsp+2F0h+var_20], r12
0x180009ac9  mov     [rsp+2F0h+var_30], r15
0x180009ad1  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180009ad8  mov     eax, r13d
0x180009adb  lea     r12, ds:0[rax*8]
0x180009ae3  mov     rax, [rsp+2F0h+var_2A8]
0x180009ae8  mov     r15, [r12+rax]
0x180009aec  mov     rax, [rsp+2F0h+pv]
0x180009af1  mov     rdi, [r12+rax]
0x180009af5  jz      short loc_180009B34
0x180009af7  lea     rax, [rsp+2F0h+packageFamilyNameLength]
0x180009afc  mov     [rsp+2F0h+packageFamilyNameLength], ebx
0x180009b00  mov     [rbp+1F0h+var_260], rax
0x180009b04  lea     rdx, NcbApiStatus
0x180009b0b  lea     rax, [rsp+2F0h+var_280]
0x180009b10  mov     [rbp+1F0h+var_270], rcx
0x180009b14  mov     r9d, 3
0x180009b1a  mov     [rsp+2F0h+ppv], rax
0x180009b1f  mov     [rbp+1F0h+var_268], 82h
0x180009b27  mov     [rbp+1F0h+var_258], 4
0x180009b2f  call    McGenEventWrite_EventWriteTransfer
0x180009b34  lea     r8, [rbp+1F0h+packageFamilyName]; packageFamilyName
0x180009b38  mov     [rsp+2F0h+Sid], rbx
0x180009b3d  lea     rdx, [rsp+2F0h+packageFamilyNameLength]; packageFamilyNameLength
0x180009b42  mov     [rsp+2F0h+packageFamilyNameLength], 104h
0x180009b4a  mov     rcx, r15; packageFullName
0x180009b4d  call    cs:__imp_PackageFamilyNameFromFullName
0x180009b53  test    eax, eax
0x180009b55  jnz     loc_180009D87
0x180009b5b  lea     rdx, [rsp+2F0h+Sid]
0x180009b60  lea     rcx, [rbp+1F0h+packageFamilyName]
0x180009b64  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180009b6a  test    eax, eax
0x180009b6c  js      loc_180009DA8
0x180009b72  mov     rsi, [rsp+2F0h+Sid]
0x180009b77  test    rsi, rsi
0x180009b7a  jz      loc_180009CD3
0x180009b80  xor     eax, eax
0x180009b82  xorps   xmm0, xmm0
0x180009b85  mov     [rbp+1F0h+var_270], rax
0x180009b89  movups  [rsp+2F0h+var_280], xmm0
0x180009b8e  test    r14, r14
0x180009b91  jz      loc_180009C5B
0x180009b97  mov     rcx, r14; Sid
0x180009b9a  call    cs:__imp_RtlLengthSid
0x180009ba0  mov     r8, r14
0x180009ba3  mov     ecx, ebx
0x180009ba5  mov     r9d, ebx
0x180009ba8  test    eax, eax
0x180009baa  jz      short loc_180009BC5
0x180009bac  nop     dword ptr [rax+00h]
0x180009bb0  movzx   edx, byte ptr [r8]
0x180009bb4  lea     r8, [r8+1]
0x180009bb8  imul    ecx, 25h ; '%'
0x180009bbb  inc     r9d
0x180009bbe  add     ecx, edx
0x180009bc0  cmp     r9d, eax
0x180009bc3  jb      short loc_180009BB0
0x180009bc5  mov     edx, ecx
0x180009bc7  lea     r8, [rsp+2F0h+var_280]
0x180009bcc  xorps   xmm0, xmm0
0x180009bcf  lea     rcx, g_NcbPolicies
0x180009bd6  mov     r14d, 80000000h
0x180009bdc  or      rdx, r14
0x180009bdf  movdqu  [rsp+2F0h+var_280], xmm0
0x180009be5  call    cs:__imp_RtlLookupEntryHashTable
0x180009beb  mov     r14, [rsp+2F0h+Sid1]
0x180009bf0  mov     rbx, rax
0x180009bf3  test    rax, rax
0x180009bf6  jz      short loc_180009C5B
0x180009bf8  mov     rdx, [rax+18h]; Sid2
0x180009bfc  mov     rcx, r14; Sid1
0x180009bff  call    cs:__imp_RtlEqualSid
0x180009c05  test    al, al
0x180009c07  jz      short loc_180009C1A
0x180009c09  mov     rdx, [rbx+28h]; Sid2
0x180009c0d  mov     rcx, rsi; Sid1
0x180009c10  call    cs:__imp_RtlEqualSid
0x180009c16  test    al, al
0x180009c18  jnz     short loc_180009C2E
0x180009c1a  lea     rdx, [rsp+2F0h+var_280]
0x180009c1f  lea     rcx, g_NcbPolicies
0x180009c26  call    cs:__imp_RtlGetNextEntryHashTable
0x180009c2c  jmp     short loc_180009BF0
0x180009c2e  test    rdi, rdi
0x180009c31  jz      loc_180009CC8
0x180009c37  mov     r8, [rbx+30h]
0x180009c3b  mov     rcx, rdi
0x180009c3e  sub     r8, rdi
0x180009c41  movzx   eax, word ptr [rcx]
0x180009c44  movzx   edx, word ptr [rcx+r8]
0x180009c49  sub     eax, edx
0x180009c4b  jnz     short loc_180009C55
0x180009c4d  add     rcx, 2
0x180009c51  test    edx, edx
0x180009c53  jnz     short loc_180009C41
0x180009c55  test    eax, eax
0x180009c57  jnz     short loc_180009C1A
0x180009c59  jmp     short loc_180009CC8
0x180009c5b  mov     r9, r15
0x180009c5e  mov     r8, rdi
0x180009c61  mov     rdx, rsi; SourceSid
0x180009c64  mov     rcx, r14; Sid
0x180009c67  call    NcbPolicyCreatePolicy
0x180009c6c  mov     rdi, rax
0x180009c6f  test    rax, rax
0x180009c72  jz      short loc_180009CC8
0x180009c74  mov     rbx, [rax+18h]
0x180009c78  mov     rcx, rbx; Sid
0x180009c7b  call    cs:__imp_RtlLengthSid
0x180009c81  xor     edx, edx
0x180009c83  xor     r8d, r8d
0x180009c86  test    eax, eax
0x180009c88  jz      short loc_180009CA4
0x180009c8a  nop     word ptr [rax+rax+00h]
0x180009c90  movzx   ecx, byte ptr [rbx]
0x180009c93  lea     rbx, [rbx+1]
0x180009c97  imul    edx, 25h ; '%'
0x180009c9a  inc     r8d
0x180009c9d  add     edx, ecx
0x180009c9f  cmp     r8d, eax
0x180009ca2  jb      short loc_180009C90
0x180009ca4  mov     r8d, edx
0x180009ca7  lea     rcx, g_NcbPolicies
0x180009cae  mov     eax, 80000000h
0x180009cb3  xor     r9d, r9d
0x180009cb6  or      r8, rax
0x180009cb9  mov     rdx, rdi
0x180009cbc  call    cs:__imp_RtlInsertEntryHashTable
0x180009cc2  inc     cs:g_NcbPolicyCounter
0x180009cc8  mov     rcx, rsi; Sid
0x180009ccb  call    cs:__imp_RtlFreeSid
0x180009cd1  xor     ebx, ebx
0x180009cd3  mov     rcx, [rsp+2F0h+pv]
0x180009cd8  mov     rcx, [r12+rcx]; pv
0x180009cdc  call    cs:__imp_CoTaskMemFree
0x180009ce2  mov     rcx, [rsp+2F0h+var_2A8]
0x180009ce7  mov     rcx, [r12+rcx]; pv
0x180009ceb  call    cs:__imp_CoTaskMemFree
0x180009cf1  inc     r13d
0x180009cf4  lea     rcx, aNcbpolicyNcbpo_10; "NcbPolicy: NcbPolicyOnAppLockScreenAddH"...
0x180009cfb  cmp     r13d, [rsp+2F0h+var_2C0]
0x180009d00  jb      loc_180009AD1
0x180009d06  mov     r15, [rsp+2F0h+var_30]
0x180009d0e  mov     r12, [rsp+2F0h+var_20]
0x180009d16  mov     rdi, [rsp+2F0h+var_18]
0x180009d1e  mov     rsi, [rsp+2F0h+arg_10]
0x180009d26  mov     rcx, [rsp+2F0h+pv]; pv
0x180009d2b  call    cs:__imp_CoTaskMemFree
0x180009d31  mov     rcx, [rsp+2F0h+var_2A8]; pv
0x180009d36  call    cs:__imp_CoTaskMemFree
0x180009d3c  mov     r13, [rsp+2F0h+var_28]
0x180009d44  mov     rcx, [rsp+2F0h+var_2A0]
0x180009d49  mov     rax, [rcx]
0x180009d4c  mov     rax, [rax+10h]
0x180009d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d55  mov     rcx, [rsp+2F0h+var_298]
0x180009d5a  mov     rax, [rcx]
0x180009d5d  mov     rax, [rax+10h]
0x180009d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d66  call    cs:__imp_CoUninitialize
0x180009d6c  mov     rcx, [rbp+1F0h+var_40]
0x180009d73  xor     rcx, rsp; StackCookie
0x180009d76  call    __security_check_cookie
0x180009d7b  add     rsp, 2E0h
0x180009d82  pop     r14
0x180009d84  pop     rbx
0x180009d85  pop     rbp
0x180009d86  retn
0x180009d87  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180009d8e  jz      loc_180009CD3
0x180009d94  mov     r9d, eax
0x180009d97  lea     r8, aNcbpolicyPacka; "NcbPolicy: PackageFamilyNameFromFullNam"...
0x180009d9e  call    McTemplateU0zq_EventWriteTransfer
0x180009da3  jmp     loc_180009CD3
0x180009da8  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180009daf  jz      loc_180009CD3
0x180009db5  mov     r9d, eax
0x180009db8  lea     r8, aNcbpolicyAppco; "NcbPolicy: AppContainerDeriveSidFromMon"...
0x180009dbf  call    McTemplateU0zq_EventWriteTransfer
0x180009dc4  jmp     loc_180009CD3
```
