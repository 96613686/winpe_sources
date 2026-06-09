# DsPrivLogMicrophone_NotifyShims

- ea: `0x180032690`
- end: `0x180032a4a`
- name: `DsPrivLogMicrophone_NotifyShims`
- size: `954`
- prototype: `void __fastcall(int, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000f114`
- `0x180031d40`
- `0x180032690`
- `0x180033aa4`
- `0x180033e50`
- `0x180053530`
- `0x1800535c0`
- `0x180059175`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800326f6`
- `ntdll!RtlFreeHeap` at `0x18003272b`
- `ntdll!RtlFreeHeap` at `0x1800326f6`
- `ntdll!RtlFreeHeap` at `0x18003272b`
- `ntdll!RtlAllocateHeap` at `0x18003276c`
- `ntdll!RtlAllocateHeap` at `0x1800327d9`
- `ntdll!RtlAllocateHeap` at `0x18003276c`
- `ntdll!RtlAllocateHeap` at `0x1800327d9`

## string_xrefs

- `0x18003297e`: `devenum.DLL`
- `0x18003285a`: `Error adding COM hook`
- `0x180032826`: `MMDevAPI.DLL`

## pseudocode

```c
void __fastcall DsPrivLogMicrophone_NotifyShims(int a1, void *a2)
{
  int v3; // ecx
  int v4; // ecx
  _QWORD *v5; // rbx
  unsigned __int64 i; // rdx
  __int64 v7; // rcx
  const char * near *v8; // rax
  PrivLog::PrivacyLogging *v9; // rbx
  __int16 v10; // r9
  __int64 ShimId; // rbx

  if ( dword_1800810A8 )
  {
    v3 = a1 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( !v4 || v4 == 99 )
      {
        if ( qword_180081090 )
        {
          PrivLog::PrivacyLogging::FlushFinalEvent((PrivLog::PrivacyLogging *)qword_180081090);
          if ( qword_180081090 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, qword_180081090);
            qword_180081090 = 0;
          }
        }
        if ( qword_180081098 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, qword_180081098);
          qword_180081098 = 0;
        }
      }
    }
    else
    {
      if ( !qword_180081098 )
      {
        qword_180081098 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x48u);
        v5 = qword_180081098;
        memset_0(qword_180081098, 0, 0x48u);
        for ( i = 0; i < 3; ++i )
        {
          v7 = 3 * i;
          v5[v7 + 2] = 0;
          v8 = (&NS_PrivLogMicrophone::g_pApiNames)[i];
          v5[v7] = v8;
          LODWORD(v5[v7 + 1]) = 0;
        }
      }
      if ( !qword_180081090 )
      {
        qword_180081090 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
        v9 = (PrivLog::PrivacyLogging *)qword_180081090;
        memset_0(qword_180081090, 0, 0x50u);
        PrivLog::PrivacyLogging::Initialize(v9, "Microphone", (struct PrivLog::ApiState *)qword_180081098, v10);
      }
      if ( qword_180081088 )
      {
        ShimId = SE_GetShimId(a2);
        SE_COM_AddServer(L"MMDevAPI.DLL", 0);
        if ( !(unsigned int)SE_COM_AddHook(
                              ShimId,
                              &NS_PrivLogMicrophone::CLSID_MMDeviceEnumerator,
                              &NS_PrivLogMicrophone::IID_IMMDeviceEnumerator,
                              3,
                              NS_PrivLogMicrophone::COMHook_IMMDeviceEnumerator_EnumAudioEndpoints) )
          AslLogCallPrintf(1, "NS_PrivLogMicrophone::DsPrivLogMicrophone_NotifyShims", 718, "Error adding COM hook");
        if ( !(unsigned int)SE_COM_AddHook(
                              ShimId,
                              &NS_PrivLogMicrophone::CLSID_MMDeviceEnumerator,
                              &NS_PrivLogMicrophone::IID_IMMDeviceEnumerator,
                              4,
                              NS_PrivLogMicrophone::COMHook_IMMDeviceEnumerator_GetDefaultAudioEndpoint) )
          AslLogCallPrintf(1, "NS_PrivLogMicrophone::DsPrivLogMicrophone_NotifyShims", 719, "Error adding COM hook");
        if ( !(unsigned int)SE_COM_AddHook(
                              ShimId,
                              &NS_PrivLogMicrophone::CLSID_MMDeviceEnumerator,
                              &NS_PrivLogMicrophone::IID_IMMDeviceEnumerator,
                              5,
                              NS_PrivLogMicrophone::COMHook_IMMDeviceEnumerator_GetDevice) )
          AslLogCallPrintf(1, "NS_PrivLogMicrophone::DsPrivLogMicrophone_NotifyShims", 720, "Error adding COM hook");
        if ( !(unsigned int)SE_COM_AddHook(
                              ShimId,
                              &GUID_NULL,
                              &NS_PrivLogMicrophone::IID_IMMDeviceCollection,
                              4,
                              NS_PrivLogMicrophone::COMHook_IMMDeviceCollection_Item) )
          AslLogCallPrintf(1, "NS_PrivLogMicrophone::DsPrivLogMicrophone_NotifyShims", 721, "Error adding COM hook");
        if ( !(unsigned int)SE_COM_AddHook(
                              ShimId,
                              &GUID_NULL,
                              &NS_PrivLogMicrophone::IID_IMMDevice,
                              3,
                              NS_PrivLogMicrophone::COMHook_IMMDevice_Activate) )
          AslLogCallPrintf(1, "NS_PrivLogMicrophone::DsPrivLogMicrophone_NotifyShims", 722, "Error adding COM hook");
        SE_COM_AddServer(L"devenum.DLL", 0);
        if ( !(unsigned int)SE_COM_AddHook(
                              ShimId,
                              qword_180075028,
                              &NS_PrivLogMicrophone::IID_ICreateDevEnum,
                              3,
                              NS_PrivLogMicrophone::COMHook_ICreateDevEnum_CreateClassEnumerator) )
          AslLogCallPrintf(1, "NS_PrivLogMicrophone::DsPrivLogMicrophone_NotifyShims", 725, "Error adding COM hook");
        if ( !(unsigned int)SE_COM_AddHook(
                              ShimId,
                              &GUID_NULL,
                              &NS_PrivLogMicrophone::IID_IEnumMoniker,
                              3,
                              NS_PrivLogMicrophone::COMHook_IEnumMoniker_Next) )
          AslLogCallPrintf(1, "NS_PrivLogMicrophone::DsPrivLogMicrophone_NotifyShims", 726, "Error adding COM hook");
        if ( !(unsigned int)SE_COM_AddHook(
                              ShimId,
                              &GUID_NULL,
                              &NS_PrivLogMicrophone::IID_IMoniker,
                              8,
                              NS_PrivLogMicrophone::COMHook_IMoniker_BindToObject) )
          AslLogCallPrintf(1, "NS_PrivLogMicrophone::DsPrivLogMicrophone_NotifyShims", 727, "Error adding COM hook");
      }
    }
  }
}

```

## disassembly

```asm
0x180032690  push    rbx
0x180032692  push    rsi
0x180032693  push    rdi
0x180032694  push    r12
0x180032696  push    r14
0x180032698  push    r15
0x18003269a  sub     rsp, 38h
0x18003269e  cmp     cs:dword_1800810A8, 0
0x1800326a5  mov     rdi, rdx
0x1800326a8  jz      loc_180032A3C
0x1800326ae  sub     ecx, 1
0x1800326b1  jz      loc_180032741
0x1800326b7  sub     ecx, 1
0x1800326ba  jz      short loc_1800326C5
0x1800326bc  cmp     ecx, 63h ; 'c'
0x1800326bf  jnz     loc_180032A3C
0x1800326c5  mov     rcx, cs:qword_180081090; this
0x1800326cc  test    rcx, rcx
0x1800326cf  jz      short loc_180032707
0x1800326d1  call    ?FlushFinalEvent@PrivacyLogging@PrivLog@@QEAAXXZ; PrivLog::PrivacyLogging::FlushFinalEvent(void)
0x1800326d6  cmp     cs:qword_180081090, 0
0x1800326de  jz      short loc_180032707
0x1800326e0  mov     rcx, gs:60h
0x1800326e9  xor     edx, edx; Flags
0x1800326eb  mov     r8, cs:qword_180081090; P
0x1800326f2  mov     rcx, [rcx+30h]; HeapHandle
0x1800326f6  call    cs:__imp_RtlFreeHeap
0x1800326fc  mov     cs:qword_180081090, 0
0x180032707  cmp     cs:qword_180081098, 0
0x18003270f  jz      loc_180032A3C
0x180032715  mov     rcx, gs:60h
0x18003271e  xor     edx, edx; Flags
0x180032720  mov     r8, cs:qword_180081098; P
0x180032727  mov     rcx, [rcx+30h]; HeapHandle
0x18003272b  call    cs:__imp_RtlFreeHeap
0x180032731  mov     cs:qword_180081098, 0
0x18003273c  jmp     loc_180032A3C
0x180032741  cmp     cs:qword_180081098, 0
0x180032749  mov     r14d, 1
0x18003274f  lea     r15d, [r14+2]
0x180032753  jnz     short loc_1800327B7
0x180032755  mov     rcx, gs:60h
0x18003275e  lea     esi, [r14+47h]
0x180032762  mov     r8d, esi; Size
0x180032765  lea     edx, [rsi-40h]; Flags
0x180032768  mov     rcx, [rcx+30h]; HeapHandle
0x18003276c  call    cs:__imp_RtlAllocateHeap
0x180032772  mov     r8d, esi; Size
0x180032775  xor     edx, edx; Val
0x180032777  mov     rcx, rax; void *
0x18003277a  mov     cs:qword_180081098, rax
0x180032781  mov     rbx, rax
0x180032784  call    memset_0
0x180032789  xor     edx, edx
0x18003278b  lea     rcx, [rdx+rdx*2]
0x18003278f  lea     rax, ?g_pApiNames@NS_PrivLogMicrophone@@3PAPEBDA; char const * near * NS_PrivLogMicrophone::g_pApiNames
0x180032796  mov     qword ptr [rbx+rcx*8+10h], 0
0x18003279f  mov     rax, [rax+rdx*8]
0x1800327a3  add     rdx, r14
0x1800327a6  mov     [rbx+rcx*8], rax
0x1800327aa  mov     dword ptr [rbx+rcx*8+8], 0
0x1800327b2  cmp     rdx, r15
0x1800327b5  jb      short loc_18003278B
0x1800327b7  cmp     cs:qword_180081090, 0
0x1800327bf  jnz     short loc_18003280C
0x1800327c1  mov     rcx, gs:60h
0x1800327ca  mov     esi, 50h ; 'P'
0x1800327cf  mov     r8d, esi; Size
0x1800327d2  mov     rcx, [rcx+30h]; HeapHandle
0x1800327d6  lea     edx, [rsi-48h]; Flags
0x1800327d9  call    cs:__imp_RtlAllocateHeap
0x1800327df  mov     r8d, esi; Size
0x1800327e2  xor     edx, edx; Val
0x1800327e4  mov     rcx, rax; void *
0x1800327e7  mov     cs:qword_180081090, rax
0x1800327ee  mov     rbx, rax
0x1800327f1  call    memset_0
0x1800327f6  mov     r8, cs:qword_180081098; struct PrivLog::ApiState *
0x1800327fd  lea     rdx, aMicrophone; "Microphone"
0x180032804  mov     rcx, rbx; this
0x180032807  call    ?Initialize@PrivacyLogging@PrivLog@@QEAAXPEBDPEAVApiState@2@F@Z; PrivLog::PrivacyLogging::Initialize(char const *,PrivLog::ApiState *,short)
0x18003280c  mov     rdx, cs:qword_180081088
0x180032813  test    rdx, rdx
0x180032816  jz      loc_180032A3C
0x18003281c  mov     rcx, rdi; Address
0x18003281f  call    SE_GetShimId
0x180032824  xor     edx, edx
0x180032826  lea     rcx, aMmdevapiDll; "MMDevAPI.DLL"
0x18003282d  mov     rbx, rax
0x180032830  call    SE_COM_AddServer
0x180032835  lea     rax, ?COMHook_IMMDeviceEnumerator_EnumAudioEndpoints@NS_PrivLogMicrophone@@YAJPEAXW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@KPEAPEAUIMMDeviceCollection@@@Z; NS_PrivLogMicrophone::COMHook_IMMDeviceEnumerator_EnumAudioEndpoints(void *,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,ulong,IMMDeviceCollection * *)
0x18003283c  mov     r9, r15
0x18003283f  lea     r8, ?IID_IMMDeviceEnumerator@NS_PrivLogMicrophone@@3U_GUID@@A; _GUID NS_PrivLogMicrophone::IID_IMMDeviceEnumerator
0x180032846  mov     [rsp+68h+var_48], rax
0x18003284b  lea     rdx, ?CLSID_MMDeviceEnumerator@NS_PrivLogMicrophone@@3U_GUID@@A; _GUID NS_PrivLogMicrophone::CLSID_MMDeviceEnumerator
0x180032852  mov     rcx, rbx
0x180032855  call    SE_COM_AddHook
0x18003285a  lea     rdi, aErrorAddingCom; "Error adding COM hook"
0x180032861  lea     rsi, aNsPrivlogmicro_0; "NS_PrivLogMicrophone::DsPrivLogMicropho"...
0x180032868  test    eax, eax
0x18003286a  jnz     short loc_180032880
0x18003286c  mov     r9, rdi
0x18003286f  mov     r8d, 2CEh
0x180032875  mov     rdx, rsi
0x180032878  mov     ecx, r14d
0x18003287b  call    AslLogCallPrintf
0x180032880  lea     rax, ?COMHook_IMMDeviceEnumerator_GetDefaultAudioEndpoint@NS_PrivLogMicrophone@@YAJPEAXW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0002@@PEAPEAUIMMDevice@@@Z; NS_PrivLogMicrophone::COMHook_IMMDeviceEnumerator_GetDefaultAudioEndpoint(void *,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0002,IMMDevice * *)
0x180032887  mov     r12d, 4
0x18003288d  mov     r9d, r12d
0x180032890  mov     [rsp+68h+var_48], rax
0x180032895  lea     r8, ?IID_IMMDeviceEnumerator@NS_PrivLogMicrophone@@3U_GUID@@A; _GUID NS_PrivLogMicrophone::IID_IMMDeviceEnumerator
0x18003289c  mov     rcx, rbx
0x18003289f  lea     rdx, ?CLSID_MMDeviceEnumerator@NS_PrivLogMicrophone@@3U_GUID@@A; _GUID NS_PrivLogMicrophone::CLSID_MMDeviceEnumerator
0x1800328a6  call    SE_COM_AddHook
0x1800328ab  test    eax, eax
0x1800328ad  jnz     short loc_1800328C3
0x1800328af  mov     r9, rdi
0x1800328b2  mov     r8d, 2CFh
0x1800328b8  mov     rdx, rsi
0x1800328bb  mov     ecx, r14d
0x1800328be  call    AslLogCallPrintf
0x1800328c3  lea     rax, ?COMHook_IMMDeviceEnumerator_GetDevice@NS_PrivLogMicrophone@@YAJPEAXPEBGPEAPEAUIMMDevice@@@Z; NS_PrivLogMicrophone::COMHook_IMMDeviceEnumerator_GetDevice(void *,ushort const *,IMMDevice * *)
0x1800328ca  mov     r9d, 5
0x1800328d0  lea     r8, ?IID_IMMDeviceEnumerator@NS_PrivLogMicrophone@@3U_GUID@@A; _GUID NS_PrivLogMicrophone::IID_IMMDeviceEnumerator
0x1800328d7  mov     [rsp+68h+var_48], rax
0x1800328dc  lea     rdx, ?CLSID_MMDeviceEnumerator@NS_PrivLogMicrophone@@3U_GUID@@A; _GUID NS_PrivLogMicrophone::CLSID_MMDeviceEnumerator
0x1800328e3  mov     rcx, rbx
0x1800328e6  call    SE_COM_AddHook
0x1800328eb  test    eax, eax
0x1800328ed  jnz     short loc_180032903
0x1800328ef  mov     r9, rdi
0x1800328f2  mov     r8d, 2D0h
0x1800328f8  mov     rdx, rsi
0x1800328fb  mov     ecx, r14d
0x1800328fe  call    AslLogCallPrintf
0x180032903  mov     r9, r12
0x180032906  lea     rax, ?COMHook_IMMDeviceCollection_Item@NS_PrivLogMicrophone@@YAJPEAXIPEAPEAUIMMDevice@@@Z; NS_PrivLogMicrophone::COMHook_IMMDeviceCollection_Item(void *,uint,IMMDevice * *)
0x18003290d  lea     r12, GUID_NULL
0x180032914  mov     [rsp+68h+var_48], rax
0x180032919  mov     rdx, r12
0x18003291c  lea     r8, ?IID_IMMDeviceCollection@NS_PrivLogMicrophone@@3U_GUID@@A; _GUID NS_PrivLogMicrophone::IID_IMMDeviceCollection
0x180032923  mov     rcx, rbx
0x180032926  call    SE_COM_AddHook
0x18003292b  test    eax, eax
0x18003292d  jnz     short loc_180032943
0x18003292f  mov     r9, rdi
0x180032932  mov     r8d, 2D1h
0x180032938  mov     rdx, rsi
0x18003293b  mov     ecx, r14d
0x18003293e  call    AslLogCallPrintf
0x180032943  lea     rax, ?COMHook_IMMDevice_Activate@NS_PrivLogMicrophone@@YAJPEAXAEBU_GUID@@KPEAUtagPROPVARIANT@@PEAPEAX@Z; NS_PrivLogMicrophone::COMHook_IMMDevice_Activate(void *,_GUID const &,ulong,tagPROPVARIANT *,void * *)
0x18003294a  mov     r9, r15
0x18003294d  lea     r8, ?IID_IMMDevice@NS_PrivLogMicrophone@@3U_GUID@@A; _GUID NS_PrivLogMicrophone::IID_IMMDevice
0x180032954  mov     [rsp+68h+var_48], rax
0x180032959  mov     rdx, r12
0x18003295c  mov     rcx, rbx
0x18003295f  call    SE_COM_AddHook
0x180032964  test    eax, eax
0x180032966  jnz     short loc_18003297C
0x180032968  mov     r9, rdi
0x18003296b  mov     r8d, 2D2h
0x180032971  mov     rdx, rsi
0x180032974  mov     ecx, r14d
0x180032977  call    AslLogCallPrintf
0x18003297c  xor     edx, edx
0x18003297e  lea     rcx, aDevenumDll; "devenum.DLL"
0x180032985  call    SE_COM_AddServer
0x18003298a  lea     rax, ?COMHook_ICreateDevEnum_CreateClassEnumerator@NS_PrivLogMicrophone@@YAJPEAXAEBU_GUID@@PEAPEAUIEnumMoniker@@K@Z; NS_PrivLogMicrophone::COMHook_ICreateDevEnum_CreateClassEnumerator(void *,_GUID const &,IEnumMoniker * *,ulong)
0x180032991  mov     r9, r15
0x180032994  lea     r8, ?IID_ICreateDevEnum@NS_PrivLogMicrophone@@3U_GUID@@A; _GUID NS_PrivLogMicrophone::IID_ICreateDevEnum
0x18003299b  mov     [rsp+68h+var_48], rax
0x1800329a0  lea     rdx, qword_180075028
0x1800329a7  mov     rcx, rbx
0x1800329aa  call    SE_COM_AddHook
0x1800329af  test    eax, eax
0x1800329b1  jnz     short loc_1800329C7
0x1800329b3  mov     r9, rdi
0x1800329b6  mov     r8d, 2D5h
0x1800329bc  mov     rdx, rsi
0x1800329bf  mov     ecx, r14d
0x1800329c2  call    AslLogCallPrintf
0x1800329c7  lea     rax, ?COMHook_IEnumMoniker_Next@NS_PrivLogMicrophone@@YAJPEAXKPEAPEAUIMoniker@@PEAK@Z; NS_PrivLogMicrophone::COMHook_IEnumMoniker_Next(void *,ulong,IMoniker * *,ulong *)
0x1800329ce  mov     r9, r15
0x1800329d1  lea     r8, ?IID_IEnumMoniker@NS_PrivLogMicrophone@@3U_GUID@@A; _GUID NS_PrivLogMicrophone::IID_IEnumMoniker
0x1800329d8  mov     [rsp+68h+var_48], rax
0x1800329dd  mov     rdx, r12
0x1800329e0  mov     rcx, rbx
0x1800329e3  call    SE_COM_AddHook
0x1800329e8  test    eax, eax
0x1800329ea  jnz     short loc_180032A00
0x1800329ec  mov     r9, rdi
0x1800329ef  mov     r8d, 2D6h
0x1800329f5  mov     rdx, rsi
0x1800329f8  mov     ecx, r14d
0x1800329fb  call    AslLogCallPrintf
0x180032a00  lea     rax, ?COMHook_IMoniker_BindToObject@NS_PrivLogMicrophone@@YAJPEAXPEAUIBindCtx@@PEAUIMoniker@@AEBU_GUID@@PEAPEAX@Z; NS_PrivLogMicrophone::COMHook_IMoniker_BindToObject(void *,IBindCtx *,IMoniker *,_GUID const &,void * *)
0x180032a07  mov     r9d, 8
0x180032a0d  lea     r8, ?IID_IMoniker@NS_PrivLogMicrophone@@3U_GUID@@A; _GUID NS_PrivLogMicrophone::IID_IMoniker
0x180032a14  mov     [rsp+68h+var_48], rax
0x180032a19  mov     rdx, r12
0x180032a1c  mov     rcx, rbx
0x180032a1f  call    SE_COM_AddHook
0x180032a24  test    eax, eax
0x180032a26  jnz     short loc_180032A3C
0x180032a28  mov     r9, rdi
0x180032a2b  mov     r8d, 2D7h
0x180032a31  mov     rdx, rsi
0x180032a34  mov     ecx, r14d
0x180032a37  call    AslLogCallPrintf
0x180032a3c  add     rsp, 38h
0x180032a40  pop     r15
0x180032a42  pop     r14
0x180032a44  pop     r12
0x180032a46  pop     rdi
0x180032a47  pop     rsi
0x180032a48  pop     rbx
0x180032a49  retn
```
