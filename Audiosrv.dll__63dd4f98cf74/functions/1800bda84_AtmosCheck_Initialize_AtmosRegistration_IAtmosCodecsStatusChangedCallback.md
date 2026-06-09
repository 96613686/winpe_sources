# AtmosCheck::Initialize(AtmosRegistration,IAtmosCodecsStatusChangedCallback *)

- ea: `0x1800bda84`
- end: `0x1800bdc74`
- name: `?Initialize@AtmosCheck@@QEAAJW4AtmosRegistration@@PEAVIAtmosCodecsStatusChangedCallback@@@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006e1c0`

## callees

- `0x1800698f0`
- `0x180072958`
- `0x18008da1c`
- `0x1800989d4`
- `0x1800b52f4`
- `0x1800bda84`
- `0x180157640`
- `0x180158170`
- `0x180158e64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bdb98`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bdb98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdbad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdbc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdbad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdbc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdc39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdc39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdc4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdc4d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800bdc26`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800bdc26`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bdaf2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bdaf2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bdb63`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bdb63`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1800bdb35`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1800bdb35`

## string_xrefs

- `0x1800bdbbf`: `Error ConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x1800bda84  mov     rax, rsp
0x1800bda87  mov     [rax+8], rbx
0x1800bda8b  mov     [rax+10h], rsi
0x1800bda8f  mov     [rax+18h], r8
0x1800bda93  push    rdi
0x1800bda94  sub     rsp, 50h
0x1800bda98  xor     esi, esi
0x1800bda9a  mov     qword ptr [rcx+0B8h], 1
0x1800bdaa5  mov     rbx, rcx
0x1800bdaa8  mov     [rax+18h], rsi
0x1800bdaac  mov     edi, esi
0x1800bdaae  mov     [rcx+2F0h], sil
0x1800bdab5  cmp     [rcx+60h], sil
0x1800bdab9  jnz     short loc_1800BDAC0
0x1800bdabb  call    ?InitializeLicenseMapLegacy@AtmosCheck@@AEAAXXZ; AtmosCheck::InitializeLicenseMapLegacy(void)
0x1800bdac0  mov     rcx, rbx; this
0x1800bdac3  call    ?IsDolbyLicenseCheckEnabledOnCurrentPlatform@AtmosCheck@@AEAA_NXZ; AtmosCheck::IsDolbyLicenseCheckEnabledOnCurrentPlatform(void)
0x1800bdac8  test    al, al
0x1800bdaca  jz      short loc_1800BDB14
0x1800bdacc  cmp     [rbx+60h], sil
0x1800bdad0  jnz     short loc_1800BDB14
0x1800bdad2  xor     edx, edx; pUnkOuter
0x1800bdad4  lea     rax, [rbx+0E0h]
0x1800bdadb  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1800bdae2  mov     [rsp+58h+ppv], rax; ppv
0x1800bdae7  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1800bdaee  lea     r8d, [rdx+17h]; dwClsContext
0x1800bdaf2  call    cs:__imp_CoCreateInstance
0x1800bdaf8  mov     edi, eax
0x1800bdafa  test    eax, eax
0x1800bdafc  js      loc_1800BDC0D
0x1800bdb02  mov     rcx, rbx; this
0x1800bdb05  call    ?InitializeCommonSpatialTechInfo@AtmosCheck@@AEAAJXZ; AtmosCheck::InitializeCommonSpatialTechInfo(void)
0x1800bdb0a  mov     edi, eax
0x1800bdb0c  test    eax, eax
0x1800bdb0e  js      loc_1800BDC0D
0x1800bdb14  mov     rcx, rbx; this
0x1800bdb17  call    ?IsLicenseEvaluationRequired@AtmosCheck@@AEAA_NXZ; AtmosCheck::IsLicenseEvaluationRequired(void)
0x1800bdb1c  test    al, al
0x1800bdb1e  jnz     short loc_1800BDB2B
0x1800bdb20  mov     byte ptr [rbx+60h], 1
0x1800bdb24  xor     eax, eax
0x1800bdb26  jmp     loc_1800BDC64
0x1800bdb2b  cmp     [rbx+60h], sil
0x1800bdb2f  jnz     loc_1800BDC09
0x1800bdb35  call    cs:__imp_SHTaskPoolGetUniqueContext
0x1800bdb3b  xor     r9d, r9d; SecurityDescriptorSize
0x1800bdb3e  mov     byte ptr [rbx+64h], 1
0x1800bdb42  mov     [rbx+0DCh], eax
0x1800bdb48  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x1800bdb4d  lea     rax, ?g_AtmosCheckCallback@@3VMyAtmosCheckCallback@@A; MyAtmosCheckCallback g_AtmosCheckCallback
0x1800bdb54  lea     rcx, aDAGaWdAGaAc; "D:(A;;GA;;;WD)(A;;GA;;;AC)"
0x1800bdb5b  mov     [rbx+28h], rax
0x1800bdb5f  lea     edx, [r9+1]; StringSDRevision
0x1800bdb63  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800bdb69  test    eax, eax
0x1800bdb6b  jz      short loc_1800BDBC8
0x1800bdb6d  mov     rax, [rsp+58h+SecurityDescriptor]
0x1800bdb72  lea     r9, Name; "Global\\Client_Atmos_Check_Event"
0x1800bdb79  xor     r8d, r8d; bInitialState
0x1800bdb7c  mov     qword ptr [rsp+58h+EventAttributes.nLength], 18h
0x1800bdb85  lea     rcx, [rsp+58h+EventAttributes]; lpEventAttributes
0x1800bdb8a  mov     [rsp+58h+EventAttributes.lpSecurityDescriptor], rax
0x1800bdb8f  mov     qword ptr [rsp+58h+EventAttributes.bInheritHandle], rsi
0x1800bdb94  lea     edx, [r8+1]; bManualReset
0x1800bdb98  call    cs:__imp_CreateEventW
0x1800bdb9e  mov     [rbx+68h], rax
0x1800bdba2  test    rax, rax
0x1800bdba5  jz      short loc_1800BDBAD
0x1800bdba7  mov     [rbx+63h], sil
0x1800bdbab  jmp     short loc_1800BDBE9
0x1800bdbad  call    cs:__imp_GetLastError
0x1800bdbb3  test    eax, eax
0x1800bdbb5  jle     short loc_1800BDBBF
0x1800bdbb7  movzx   eax, ax
0x1800bdbba  or      eax, 80070000h
0x1800bdbbf  lea     rdx, aErrorConvertst; "Error ConvertStringSecurityDescriptorTo"...
0x1800bdbc6  jmp     short loc_1800BDBE1
0x1800bdbc8  call    cs:__imp_GetLastError
0x1800bdbce  test    eax, eax
0x1800bdbd0  jle     short loc_1800BDBDA
0x1800bdbd2  movzx   eax, ax
0x1800bdbd5  or      eax, 80070000h
0x1800bdbda  lea     rdx, aErrorCreatingG; "Error creating Global\\Client_Atmos_Che"...
0x1800bdbe1  mov     r8d, eax; int
0x1800bdbe4  call    ?Trace@AtmosCheck@@AEAAXPEBDJ@Z; AtmosCheck::Trace(char const *,long)
0x1800bdbe9  cmp     [rbx+64h], sil
0x1800bdbed  jnz     short loc_1800BDBFF
0x1800bdbef  xor     edx, edx; bool
0x1800bdbf1  mov     rcx, rbx; this
0x1800bdbf4  call    ?PerformLicenseCheck@AtmosCheck@@QEAAJ_N@Z; AtmosCheck::PerformLicenseCheck(bool)
0x1800bdbf9  mov     edi, eax
0x1800bdbfb  test    eax, eax
0x1800bdbfd  js      short loc_1800BDC0D
0x1800bdbff  mov     rcx, rbx
0x1800bdc02  call    ?QueueCompleteInitialization@AtmosCheck@@AEAAJW4AtmosRegistration@@@Z; AtmosCheck::QueueCompleteInitialization(AtmosRegistration)
0x1800bdc07  mov     edi, eax
0x1800bdc09  test    edi, edi
0x1800bdc0b  jns     short loc_1800BDC43
0x1800bdc0d  mov     rcx, rbx; pv
0x1800bdc10  mov     [rbx+60h], sil
0x1800bdc14  call    ?UninitializeAppServiceMode@AtmosCheck@@AEAAXXZ; AtmosCheck::UninitializeAppServiceMode(void)
0x1800bdc19  mov     rcx, [rbx+70h]; WaitHandle
0x1800bdc1d  test    rcx, rcx
0x1800bdc20  jz      short loc_1800BDC30
0x1800bdc22  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800bdc26  call    cs:__imp_UnregisterWaitEx
0x1800bdc2c  mov     [rbx+70h], rsi
0x1800bdc30  mov     rcx, [rbx+68h]; hObject
0x1800bdc34  test    rcx, rcx
0x1800bdc37  jz      short loc_1800BDC43
0x1800bdc39  call    cs:__imp_CloseHandle
0x1800bdc3f  mov     [rbx+68h], rsi
0x1800bdc43  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x1800bdc48  test    rcx, rcx
0x1800bdc4b  jz      short loc_1800BDC53
0x1800bdc4d  call    cs:__imp_LocalFree
0x1800bdc53  mov     r8d, edi; int
0x1800bdc56  lea     rdx, aInitResult; "Init result"
0x1800bdc5d  call    ?Trace@AtmosCheck@@AEAAXPEBDJ@Z; AtmosCheck::Trace(char const *,long)
0x1800bdc62  mov     eax, edi
0x1800bdc64  mov     rbx, [rsp+58h+arg_0]
0x1800bdc69  mov     rsi, [rsp+58h+arg_8]
0x1800bdc6e  add     rsp, 50h
0x1800bdc72  pop     rdi
0x1800bdc73  retn
```
