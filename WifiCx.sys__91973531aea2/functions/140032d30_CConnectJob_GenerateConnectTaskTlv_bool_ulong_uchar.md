# CConnectJob::GenerateConnectTaskTlv(bool,ulong *,uchar * *)

- ea: `0x140032d30`
- end: `0x140032f45`
- name: `?GenerateConnectTaskTlv@CConnectJob@@AEAAH_NPEAKPEAPEAE@Z`
- size: `533`
- prototype: `__int64 __fastcall(CConnectJob *__hidden this, bool, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1400b511c`

## callees

- `0x1400032f0`
- `0x14000c940`
- `0x140018270`
- `0x14001e2c0`
- `0x14002eeb8`
- `0x140032d30`
- `0x140032f4c`
- `0x1400406bc`
- `0x1400508d4`
- `0x1400739a0`
- `0x1400a0fd0`
- `0x1400a15ac`
- `0x1400a621c`

## pseudocode

```c
__int64 __fastcall CConnectJob::GenerateConnectTaskTlv(
        CConnectJob *this,
        __int64 a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  char v6; // si
  unsigned int v9; // eax
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // edi
  int v13; // r9d
  __int64 v14; // r8
  unsigned int WdiTaskConnectToIhv; // eax
  CPropertyCache *AdapterPropertyCache; // rax
  unsigned int PropertyULongOrDefault; // eax
  CPropertyCache *v18; // rax
  char v19; // al
  int v20; // edx
  int v21; // r8d
  int v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+38h] [rbp-C8h]
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  struct _WFC_MESSAGE_METADATA *v25; // [rsp+58h] [rbp-A8h] BYREF
  void *v26[47]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[72]; // [rsp+1D8h] [rbp+D8h] BYREF

  v6 = a2;
  if ( (unsigned int)Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline(this, a2, a3) )
    return CConnectJob::GenerateConnectTaskTlv_TLVParserStaging(this, v6, a3, a4);
  _WDI_TASK_ROAM_PARAMETERS::_WDI_TASK_ROAM_PARAMETERS((_WDI_TASK_ROAM_PARAMETERS *)v26);
  v24 = 0;
  v25 = 0;
  *a3 = 0;
  v9 = CConnectJob::FillConnectRoamTaskParameters(this, v26, (__int64)v27, v6);
  v12 = v9;
  if ( v9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 373;
      v23 = v9;
      v22 = *((_DWORD *)this + 4);
LABEL_6:
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        v13,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        v22,
        v23);
    }
  }
  else
  {
    v14 = *((_QWORD *)this + 67);
    BYTE4(v26[0]) = v6 != 0;
    WdiTaskConnectToIhv = GenerateWdiTaskConnectToIhv(
                            (unsigned int)v26,
                            48,
                            (int)v14 + 5384,
                            (unsigned int)&v24,
                            (__int64)&v25);
    v12 = WdiTaskConnectToIhv;
    if ( !WdiTaskConnectToIhv )
    {
      AdapterPropertyCache = CJobBase::get_AdapterPropertyCache(this);
      PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault(AdapterPropertyCache, 0x10u, 0xFFFFFFFF);
      v12 = CMessageHelper::FitMessageToBufferSize(v25, v24, PropertyULongOrDefault, 0x34u, a3);
      if ( v12 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v18 = CJobBase::get_AdapterPropertyCache(this);
          v19 = CPropertyCache::GetPropertyULongOrDefault(v18, 0x10u, 0xFFFFFFFF);
          WPP_RECORDER_SF_qDDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v20,
            v21,
            375,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            v12,
            v24,
            v19);
        }
      }
      else
      {
        *a4 = (unsigned __int8 *)v25;
        v25 = 0;
      }
      goto LABEL_14;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = WdiTaskConnectToIhv;
      v13 = 374;
      v22 = *((_DWORD *)this + 4);
      goto LABEL_6;
    }
  }
LABEL_14:
  if ( v25 )
    operator delete(v25);
  WiFiCxTLVStaging::_WDI_TASK_ROAM_PARAMETERS::~_WDI_TASK_ROAM_PARAMETERS((WiFiCxTLVStaging::_WDI_TASK_ROAM_PARAMETERS *)v26);
  return v12;
}

```

## disassembly

```asm
0x140032d30  push    rbp
0x140032d32  push    rbx
0x140032d33  push    rsi
0x140032d34  push    rdi
0x140032d35  push    r14
0x140032d37  push    r15
0x140032d39  lea     rbp, [rsp-0F8h]
0x140032d41  sub     rsp, 1F8h
0x140032d48  mov     r15, r9
0x140032d4b  mov     r14, r8
0x140032d4e  mov     sil, dl
0x140032d51  mov     rbx, rcx
0x140032d54  call    Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline
0x140032d59  test    eax, eax
0x140032d5b  jz      short loc_140032D73
0x140032d5d  mov     r9, r15; unsigned __int8 **
0x140032d60  mov     r8, r14; unsigned int *
0x140032d63  mov     dl, sil; bool
0x140032d66  mov     rcx, rbx; this
0x140032d69  call    ?GenerateConnectTaskTlv_TLVParserStaging@CConnectJob@@AEAAH_NPEAKPEAPEAE@Z; CConnectJob::GenerateConnectTaskTlv_TLVParserStaging(bool,ulong *,uchar * *)
0x140032d6e  jmp     loc_140032F34
0x140032d73  lea     rcx, [rsp+220h+var_1C0]; this
0x140032d78  call    ??0_WDI_TASK_ROAM_PARAMETERS@@QEAA@XZ; _WDI_TASK_ROAM_PARAMETERS::_WDI_TASK_ROAM_PARAMETERS(void)
0x140032d7d  mov     r9b, sil
0x140032d80  mov     [rsp+220h+var_1D0], 0
0x140032d88  lea     r8, [rbp+120h+var_48]
0x140032d8f  mov     [rsp+220h+var_1C8], 0
0x140032d98  lea     rdx, [rsp+220h+var_1C0]; struct _WDI_CONNECT_PARAMETERS_CONTAINER *
0x140032d9d  mov     dword ptr [r14], 0
0x140032da4  mov     rcx, rbx; this
0x140032da7  call    ?FillConnectRoamTaskParameters@CConnectJob@@AEAAHPEAU_WDI_CONNECT_PARAMETERS_CONTAINER@@PEAU?$ArrayOfElements@U_WDI_CONNECT_BSS_ENTRY_CONTAINER@@@@_N@Z; CConnectJob::FillConnectRoamTaskParameters(_WDI_CONNECT_PARAMETERS_CONTAINER *,ArrayOfElements<_WDI_CONNECT_BSS_ENTRY_CONTAINER> *,bool)
0x140032dac  mov     edi, eax
0x140032dae  test    eax, eax
0x140032db0  jz      short loc_140032DFF
0x140032db2  lea     rcx, WPP_RECORDER_INITIALIZED
0x140032db9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140032dc0  jz      loc_140032F19
0x140032dc6  mov     ecx, [rbx+10h]
0x140032dc9  mov     r9d, 175h
0x140032dcf  mov     [rsp+220h+var_1E8], eax
0x140032dd3  mov     [rsp+220h+var_1F0], ecx
0x140032dd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140032dde  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x140032de5  mov     [rsp+220h+var_1F8], rbx
0x140032dea  mov     dl, 2
0x140032dec  mov     [rsp+220h+var_200], rax
0x140032df1  mov     rcx, [rcx+40h]
0x140032df5  call    WPP_RECORDER_SF_qDD
0x140032dfa  jmp     loc_140032F19
0x140032dff  mov     r8, [rbx+218h]
0x140032e06  lea     rax, [rsp+220h+var_1C8]
0x140032e0b  test    sil, sil
0x140032e0e  mov     [rsp+220h+var_200], rax
0x140032e13  lea     r9, [rsp+220h+var_1D0]
0x140032e18  mov     edx, 30h ; '0'
0x140032e1d  setnz   [rsp+220h+var_1BC]
0x140032e22  lea     rcx, [rsp+220h+var_1C0]
0x140032e27  add     r8, 1508h
0x140032e2e  call    GenerateWdiTaskConnectToIhv
0x140032e33  mov     edi, eax
0x140032e35  test    eax, eax
0x140032e37  jz      short loc_140032E63
0x140032e39  lea     rcx, WPP_RECORDER_INITIALIZED
0x140032e40  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140032e47  jz      loc_140032F19
0x140032e4d  mov     [rsp+220h+var_1E8], eax
0x140032e51  mov     r9d, 176h
0x140032e57  mov     eax, [rbx+10h]
0x140032e5a  mov     [rsp+220h+var_1F0], eax
0x140032e5e  jmp     loc_140032DD7
0x140032e63  mov     rcx, rbx; this
0x140032e66  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x140032e6b  or      esi, 0FFFFFFFFh
0x140032e6e  mov     edx, 10h; unsigned int
0x140032e73  mov     r8d, esi; unsigned int
0x140032e76  mov     rcx, rax; this
0x140032e79  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x140032e7e  mov     edx, [rsp+220h+var_1D0]; unsigned int
0x140032e82  mov     r9d, 34h ; '4'; unsigned __int16
0x140032e88  mov     rcx, [rsp+220h+var_1C8]; struct _WFC_MESSAGE_METADATA *
0x140032e8d  mov     r8d, eax; unsigned int
0x140032e90  mov     [rsp+220h+var_200], r14; unsigned int *
0x140032e95  call    ?FitMessageToBufferSize@CMessageHelper@@SAHPEAU_WFC_MESSAGE_METADATA@@KKGPEAK@Z; CMessageHelper::FitMessageToBufferSize(_WFC_MESSAGE_METADATA *,ulong,ulong,ushort,ulong *)
0x140032e9a  mov     edi, eax
0x140032e9c  test    eax, eax
0x140032e9e  jz      short loc_140032F08
0x140032ea0  lea     rcx, WPP_RECORDER_INITIALIZED
0x140032ea7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140032eae  jz      short loc_140032F19
0x140032eb0  mov     rcx, rbx; this
0x140032eb3  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x140032eb8  mov     r8d, esi; unsigned int
0x140032ebb  mov     edx, 10h; unsigned int
0x140032ec0  mov     rcx, rax; this
0x140032ec3  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x140032ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ecf  mov     r9d, 177h
0x140032ed5  mov     [rsp+220h+var_1D8], eax
0x140032ed9  mov     eax, [rsp+220h+var_1D0]
0x140032edd  mov     [rsp+220h+var_1E0], eax
0x140032ee1  mov     eax, [rbx+10h]
0x140032ee4  mov     rcx, [rcx+40h]
0x140032ee8  mov     [rsp+220h+var_1E8], edi
0x140032eec  mov     [rsp+220h+var_1F0], eax
0x140032ef0  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x140032ef7  mov     [rsp+220h+var_1F8], rbx
0x140032efc  mov     [rsp+220h+var_200], rax
0x140032f01  call    WPP_RECORDER_SF_qDDdd
0x140032f06  jmp     short loc_140032F19
0x140032f08  mov     rax, [rsp+220h+var_1C8]
0x140032f0d  mov     [r15], rax
0x140032f10  mov     [rsp+220h+var_1C8], 0
0x140032f19  mov     rcx, [rsp+220h+var_1C8]; void *
0x140032f1e  test    rcx, rcx
0x140032f21  jz      short loc_140032F28
0x140032f23  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140032f28  lea     rcx, [rsp+220h+var_1C0]; this
0x140032f2d  call    ??1_WDI_TASK_ROAM_PARAMETERS@WiFiCxTLVStaging@@QEAA@XZ; WiFiCxTLVStaging::_WDI_TASK_ROAM_PARAMETERS::~_WDI_TASK_ROAM_PARAMETERS(void)
0x140032f32  mov     eax, edi
0x140032f34  add     rsp, 1F8h
0x140032f3b  pop     r15
0x140032f3d  pop     r14
0x140032f3f  pop     rdi
0x140032f40  pop     rsi
0x140032f41  pop     rbx
0x140032f42  pop     rbp
0x140032f43  retn
```
