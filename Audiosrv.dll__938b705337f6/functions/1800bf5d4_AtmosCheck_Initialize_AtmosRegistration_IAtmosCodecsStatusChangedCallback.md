# AtmosCheck::Initialize(AtmosRegistration,IAtmosCodecsStatusChangedCallback *)

- ea: `0x1800bf5d4`
- end: `0x1800bf7c4`
- name: `?Initialize@AtmosCheck@@QEAAJW4AtmosRegistration@@PEAVIAtmosCodecsStatusChangedCallback@@@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006e6c0`

## callees

- `0x180069d80`
- `0x180072e58`
- `0x18008d970`
- `0x180098924`
- `0x1800b6e30`
- `0x1800bf5d4`
- `0x180156930`
- `0x180157460`
- `0x180158154`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bf6e8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bf6e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf6fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf6fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf718`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bf789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bf789`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bf79d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bf79d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800bf776`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800bf776`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bf642`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bf642`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bf6b3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bf6b3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1800bf685`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1800bf685`

## string_xrefs

- `0x1800bf70f`: `Error ConvertStringSecurityDescriptorToSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall AtmosCheck::Initialize(__int64 a1)
{
  HRESULT Instance; // edi
  int UniqueContext; // eax
  HANDLE v5; // rax
  signed int LastError; // eax
  AtmosCheck *v7; // rcx
  const char *v8; // rdx
  void *v9; // rcx
  void *v10; // rcx
  AtmosCheck *v11; // rcx
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+18h] BYREF

  *(_QWORD *)(a1 + 184) = 1;
  SecurityDescriptor = 0;
  Instance = 0;
  *(_BYTE *)(a1 + 752) = 0;
  if ( !*(_BYTE *)(a1 + 96) )
    AtmosCheck::InitializeLicenseMapLegacy((AtmosCheck *)a1);
  if ( AtmosCheck::IsDolbyLicenseCheckEnabledOnCurrentPlatform((AtmosCheck *)a1) && !*(_BYTE *)(a1 + 96) )
  {
    Instance = CoCreateInstance(
                 &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
                 0,
                 0x17u,
                 &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
                 (LPVOID *)(a1 + 224));
    if ( Instance < 0 )
      goto LABEL_24;
    Instance = AtmosCheck::InitializeCommonSpatialTechInfo((AtmosCheck *)a1);
    if ( Instance < 0 )
      goto LABEL_24;
  }
  if ( !AtmosCheck::IsLicenseEvaluationRequired((AtmosCheck *)a1) )
  {
    *(_BYTE *)(a1 + 96) = 1;
    return 0;
  }
  if ( *(_BYTE *)(a1 + 96) )
    goto LABEL_23;
  UniqueContext = SHTaskPoolGetUniqueContext();
  *(_BYTE *)(a1 + 100) = 1;
  *(_DWORD *)(a1 + 220) = UniqueContext;
  *(_QWORD *)(a1 + 40) = g_AtmosCheckCallback;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;WD)(A;;GA;;;AC)", 1u, &SecurityDescriptor, 0) )
  {
    *(_QWORD *)&EventAttributes.nLength = 24;
    EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&EventAttributes.bInheritHandle = 0;
    v5 = CreateEventW(&EventAttributes, 1, 0, L"Global\\Client_Atmos_Check_Event");
    *(_QWORD *)(a1 + 104) = v5;
    if ( v5 )
    {
      *(_BYTE *)(a1 + 99) = 0;
      goto LABEL_20;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = "Error ConvertStringSecurityDescriptorToSecurityDescriptor";
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = "Error creating Global\\Client_Atmos_Check_Event";
  }
  AtmosCheck::Trace(v7, v8, LastError);
LABEL_20:
  if ( !*(_BYTE *)(a1 + 100) )
  {
    Instance = AtmosCheck::PerformLicenseCheck((AtmosCheck *)a1, 0);
    if ( Instance < 0 )
      goto LABEL_24;
  }
  Instance = AtmosCheck::QueueCompleteInitialization(a1);
LABEL_23:
  if ( Instance < 0 )
  {
LABEL_24:
    *(_BYTE *)(a1 + 96) = 0;
    AtmosCheck::UninitializeAppServiceMode((PVOID)a1);
    v9 = *(void **)(a1 + 112);
    if ( v9 )
    {
      UnregisterWaitEx(v9, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *(_QWORD *)(a1 + 112) = 0;
    }
    v10 = *(void **)(a1 + 104);
    if ( v10 )
    {
      CloseHandle(v10);
      *(_QWORD *)(a1 + 104) = 0;
    }
  }
  v11 = (AtmosCheck *)SecurityDescriptor;
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  AtmosCheck::Trace(v11, "Init result", Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800bf5d4  mov     rax, rsp
0x1800bf5d7  mov     [rax+8], rbx
0x1800bf5db  mov     [rax+10h], rsi
0x1800bf5df  mov     [rax+18h], r8
0x1800bf5e3  push    rdi
0x1800bf5e4  sub     rsp, 50h
0x1800bf5e8  xor     esi, esi
0x1800bf5ea  mov     qword ptr [rcx+0B8h], 1
0x1800bf5f5  mov     rbx, rcx
0x1800bf5f8  mov     [rax+18h], rsi
0x1800bf5fc  mov     edi, esi
0x1800bf5fe  mov     [rcx+2F0h], sil
0x1800bf605  cmp     [rcx+60h], sil
0x1800bf609  jnz     short loc_1800BF610
0x1800bf60b  call    ?InitializeLicenseMapLegacy@AtmosCheck@@AEAAXXZ; AtmosCheck::InitializeLicenseMapLegacy(void)
0x1800bf610  mov     rcx, rbx; this
0x1800bf613  call    ?IsDolbyLicenseCheckEnabledOnCurrentPlatform@AtmosCheck@@AEAA_NXZ; AtmosCheck::IsDolbyLicenseCheckEnabledOnCurrentPlatform(void)
0x1800bf618  test    al, al
0x1800bf61a  jz      short loc_1800BF664
0x1800bf61c  cmp     [rbx+60h], sil
0x1800bf620  jnz     short loc_1800BF664
0x1800bf622  xor     edx, edx; pUnkOuter
0x1800bf624  lea     rax, [rbx+0E0h]
0x1800bf62b  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1800bf632  mov     [rsp+58h+ppv], rax; ppv
0x1800bf637  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1800bf63e  lea     r8d, [rdx+17h]; dwClsContext
0x1800bf642  call    cs:__imp_CoCreateInstance
0x1800bf648  mov     edi, eax
0x1800bf64a  test    eax, eax
0x1800bf64c  js      loc_1800BF75D
0x1800bf652  mov     rcx, rbx; this
0x1800bf655  call    ?InitializeCommonSpatialTechInfo@AtmosCheck@@AEAAJXZ; AtmosCheck::InitializeCommonSpatialTechInfo(void)
0x1800bf65a  mov     edi, eax
0x1800bf65c  test    eax, eax
0x1800bf65e  js      loc_1800BF75D
0x1800bf664  mov     rcx, rbx; this
0x1800bf667  call    ?IsLicenseEvaluationRequired@AtmosCheck@@AEAA_NXZ; AtmosCheck::IsLicenseEvaluationRequired(void)
0x1800bf66c  test    al, al
0x1800bf66e  jnz     short loc_1800BF67B
0x1800bf670  mov     byte ptr [rbx+60h], 1
0x1800bf674  xor     eax, eax
0x1800bf676  jmp     loc_1800BF7B4
0x1800bf67b  cmp     [rbx+60h], sil
0x1800bf67f  jnz     loc_1800BF759
0x1800bf685  call    cs:__imp_SHTaskPoolGetUniqueContext
0x1800bf68b  xor     r9d, r9d; SecurityDescriptorSize
0x1800bf68e  mov     byte ptr [rbx+64h], 1
0x1800bf692  mov     [rbx+0DCh], eax
0x1800bf698  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x1800bf69d  lea     rax, ?g_AtmosCheckCallback@@3VMyAtmosCheckCallback@@A; MyAtmosCheckCallback g_AtmosCheckCallback
0x1800bf6a4  lea     rcx, aDAGaWdAGaAc; "D:(A;;GA;;;WD)(A;;GA;;;AC)"
0x1800bf6ab  mov     [rbx+28h], rax
0x1800bf6af  lea     edx, [r9+1]; StringSDRevision
0x1800bf6b3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800bf6b9  test    eax, eax
0x1800bf6bb  jz      short loc_1800BF718
0x1800bf6bd  mov     rax, [rsp+58h+SecurityDescriptor]
0x1800bf6c2  lea     r9, Name; "Global\\Client_Atmos_Check_Event"
0x1800bf6c9  xor     r8d, r8d; bInitialState
0x1800bf6cc  mov     qword ptr [rsp+58h+EventAttributes.nLength], 18h
0x1800bf6d5  lea     rcx, [rsp+58h+EventAttributes]; lpEventAttributes
0x1800bf6da  mov     [rsp+58h+EventAttributes.lpSecurityDescriptor], rax
0x1800bf6df  mov     qword ptr [rsp+58h+EventAttributes.bInheritHandle], rsi
0x1800bf6e4  lea     edx, [r8+1]; bManualReset
0x1800bf6e8  call    cs:__imp_CreateEventW
0x1800bf6ee  mov     [rbx+68h], rax
0x1800bf6f2  test    rax, rax
0x1800bf6f5  jz      short loc_1800BF6FD
0x1800bf6f7  mov     [rbx+63h], sil
0x1800bf6fb  jmp     short loc_1800BF739
0x1800bf6fd  call    cs:__imp_GetLastError
0x1800bf703  test    eax, eax
0x1800bf705  jle     short loc_1800BF70F
0x1800bf707  movzx   eax, ax
0x1800bf70a  or      eax, 80070000h
0x1800bf70f  lea     rdx, aErrorConvertst; "Error ConvertStringSecurityDescriptorTo"...
0x1800bf716  jmp     short loc_1800BF731
0x1800bf718  call    cs:__imp_GetLastError
0x1800bf71e  test    eax, eax
0x1800bf720  jle     short loc_1800BF72A
0x1800bf722  movzx   eax, ax
0x1800bf725  or      eax, 80070000h
0x1800bf72a  lea     rdx, aErrorCreatingG; "Error creating Global\\Client_Atmos_Che"...
0x1800bf731  mov     r8d, eax; int
0x1800bf734  call    ?Trace@AtmosCheck@@AEAAXPEBDJ@Z; AtmosCheck::Trace(char const *,long)
0x1800bf739  cmp     [rbx+64h], sil
0x1800bf73d  jnz     short loc_1800BF74F
0x1800bf73f  xor     edx, edx; bool
0x1800bf741  mov     rcx, rbx; this
0x1800bf744  call    ?PerformLicenseCheck@AtmosCheck@@QEAAJ_N@Z; AtmosCheck::PerformLicenseCheck(bool)
0x1800bf749  mov     edi, eax
0x1800bf74b  test    eax, eax
0x1800bf74d  js      short loc_1800BF75D
0x1800bf74f  mov     rcx, rbx
0x1800bf752  call    ?QueueCompleteInitialization@AtmosCheck@@AEAAJW4AtmosRegistration@@@Z; AtmosCheck::QueueCompleteInitialization(AtmosRegistration)
0x1800bf757  mov     edi, eax
0x1800bf759  test    edi, edi
0x1800bf75b  jns     short loc_1800BF793
0x1800bf75d  mov     rcx, rbx; pv
0x1800bf760  mov     [rbx+60h], sil
0x1800bf764  call    ?UninitializeAppServiceMode@AtmosCheck@@AEAAXXZ; AtmosCheck::UninitializeAppServiceMode(void)
0x1800bf769  mov     rcx, [rbx+70h]; WaitHandle
0x1800bf76d  test    rcx, rcx
0x1800bf770  jz      short loc_1800BF780
0x1800bf772  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800bf776  call    cs:__imp_UnregisterWaitEx
0x1800bf77c  mov     [rbx+70h], rsi
0x1800bf780  mov     rcx, [rbx+68h]; hObject
0x1800bf784  test    rcx, rcx
0x1800bf787  jz      short loc_1800BF793
0x1800bf789  call    cs:__imp_CloseHandle
0x1800bf78f  mov     [rbx+68h], rsi
0x1800bf793  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x1800bf798  test    rcx, rcx
0x1800bf79b  jz      short loc_1800BF7A3
0x1800bf79d  call    cs:__imp_LocalFree
0x1800bf7a3  mov     r8d, edi; int
0x1800bf7a6  lea     rdx, aInitResult; "Init result"
0x1800bf7ad  call    ?Trace@AtmosCheck@@AEAAXPEBDJ@Z; AtmosCheck::Trace(char const *,long)
0x1800bf7b2  mov     eax, edi
0x1800bf7b4  mov     rbx, [rsp+58h+arg_0]
0x1800bf7b9  mov     rsi, [rsp+58h+arg_8]
0x1800bf7be  add     rsp, 50h
0x1800bf7c2  pop     rdi
0x1800bf7c3  retn
```
