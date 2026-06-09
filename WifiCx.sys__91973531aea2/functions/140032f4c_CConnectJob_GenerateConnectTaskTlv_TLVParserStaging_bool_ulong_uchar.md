# CConnectJob::GenerateConnectTaskTlv_TLVParserStaging(bool,ulong *,uchar * *)

- ea: `0x140032f4c`
- end: `0x140033184`
- name: `?GenerateConnectTaskTlv_TLVParserStaging@CConnectJob@@AEAAH_NPEAKPEAPEAE@Z`
- size: `568`
- prototype: `__int64 __fastcall(CConnectJob *__hidden this, bool, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x140032d30`

## callees

- `0x14000c940`
- `0x140018270`
- `0x14001e2c0`
- `0x14002eeb8`
- `0x140032f4c`
- `0x1400406bc`
- `0x1400508d4`
- `0x1400739a0`
- `0x1400a0ec4`
- `0x1400a15d8`
- `0x1400a6c04`

## pseudocode

```c
__int64 __fastcall CConnectJob::GenerateConnectTaskTlv_TLVParserStaging(
        CConnectJob *this,
        char a2,
        unsigned int *a3,
        struct _WFC_MESSAGE_METADATA **a4)
{
  _DWORD *v8; // r8
  __int16 v9; // dx
  unsigned int v10; // eax
  int v11; // edx
  int v12; // r8d
  unsigned int v13; // edi
  int v14; // r9d
  __int64 v15; // r8
  unsigned int WdiTaskConnectToIhv; // eax
  CPropertyCache *AdapterPropertyCache; // rax
  unsigned int PropertyULongOrDefault; // eax
  CPropertyCache *v19; // rax
  char v20; // al
  int v21; // edx
  int v22; // r8d
  int v24; // [rsp+30h] [rbp-D0h]
  int v25; // [rsp+38h] [rbp-C8h]
  struct _WFC_MESSAGE_METADATA *v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+60h] [rbp-A0h] BYREF
  int v28; // [rsp+68h] [rbp-98h] BYREF
  bool v29; // [rsp+6Ch] [rbp-94h]
  int v30; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v31; // [rsp+1E8h] [rbp+E8h]
  char v32; // [rsp+1F0h] [rbp+F0h]
  int v33; // [rsp+1F8h] [rbp+F8h]
  __int64 v34; // [rsp+200h] [rbp+100h]
  char v35; // [rsp+208h] [rbp+108h]
  unsigned int v36; // [rsp+260h] [rbp+160h] BYREF

  v27 &= ~1u;
  _WDI_CONNECT_PARAMETERS_CONTAINER::_WDI_CONNECT_PARAMETERS_CONTAINER((_WDI_CONNECT_PARAMETERS_CONTAINER *)&v28);
  *v8 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v26 = 0;
  v10 = CConnectJob::FillConnectRoamTaskParameters_TLVParserStaging(this, v9, &v28, (__int64)&v30);
  v13 = v10;
  if ( v10 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_12;
    v14 = 370;
    v25 = v10;
    v24 = *((_DWORD *)this + 4);
    goto LABEL_4;
  }
  v15 = *((_QWORD *)this + 67);
  v29 = a2 != 0;
  WdiTaskConnectToIhv = GenerateWdiTaskConnectToIhv(
                          (unsigned int)&v27,
                          48,
                          (int)v15 + 5384,
                          (unsigned int)&v36,
                          (__int64)&v26);
  v13 = WdiTaskConnectToIhv;
  if ( WdiTaskConnectToIhv )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v25 = WdiTaskConnectToIhv;
      v14 = 371;
      v24 = *((_DWORD *)this + 4);
LABEL_4:
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        v12,
        v14,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        v24,
        v25);
    }
  }
  else
  {
    AdapterPropertyCache = CJobBase::get_AdapterPropertyCache(this);
    PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault(AdapterPropertyCache, 0x10u, 0xFFFFFFFF);
    v13 = CMessageHelper::FitMessageToBufferSize(v26, v36, PropertyULongOrDefault, 0x34u, a3);
    if ( v13 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v19 = CJobBase::get_AdapterPropertyCache(this);
        v20 = CPropertyCache::GetPropertyULongOrDefault(v19, 0x10u, 0xFFFFFFFF);
        WPP_RECORDER_SF_qDDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v21,
          v22,
          372,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v13,
          v36,
          v20);
      }
    }
    else
    {
      *a4 = v26;
      v26 = 0;
    }
  }
LABEL_12:
  if ( v26 )
    operator delete(v26);
  WiFiCxTLVStaging::_WDI_TASK_CONNECT_PARAMETERS::~_WDI_TASK_CONNECT_PARAMETERS((WiFiCxTLVStaging::_WDI_TASK_CONNECT_PARAMETERS *)&v27);
  return v13;
}

```

## disassembly

```asm
0x140032f4c  push    rbp
0x140032f4e  push    rbx
0x140032f4f  push    rsi
0x140032f50  push    rdi
0x140032f51  push    r14
0x140032f53  push    r15
0x140032f55  lea     rbp, [rsp-118h]
0x140032f5d  sub     rsp, 218h
0x140032f64  and     [rsp+240h+var_1E0], 0FFFFFFFEh
0x140032f69  mov     rbx, rcx
0x140032f6c  lea     rcx, [rsp+240h+var_1D8]; this
0x140032f71  mov     r14, r9
0x140032f74  mov     r15, r8
0x140032f77  mov     sil, dl
0x140032f7a  call    ??0_WDI_CONNECT_PARAMETERS_CONTAINER@@QEAA@XZ; _WDI_CONNECT_PARAMETERS_CONTAINER::_WDI_CONNECT_PARAMETERS_CONTAINER(void)
0x140032f7f  mov     dword ptr [r8], 0
0x140032f86  lea     r9, [rbp+140h+var_60]
0x140032f8d  lea     r8, [rsp+240h+var_1D8]
0x140032f92  mov     [rbp+140h+var_60], 0
0x140032f9c  mov     rcx, rbx; this
0x140032f9f  mov     [rbp+140h+var_58], 0
0x140032faa  mov     [rbp+140h+var_50], 0
0x140032fb1  mov     [rbp+140h+var_48], 0
0x140032fbb  mov     [rbp+140h+var_40], 0
0x140032fc6  mov     [rbp+140h+var_38], 0
0x140032fcd  mov     [rbp+140h+arg_10], 0
0x140032fd7  mov     [rsp+240h+var_1F0], 0
0x140032fe0  call    ?FillConnectRoamTaskParameters_TLVParserStaging@CConnectJob@@AEAAH_NPEAU_WDI_CONNECT_PARAMETERS_CONTAINER@WiFiCxTLVStaging@@PEAU?$ArrayOfElements@U_WDI_CONNECT_BSS_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@@Z; CConnectJob::FillConnectRoamTaskParameters_TLVParserStaging(bool,WiFiCxTLVStaging::_WDI_CONNECT_PARAMETERS_CONTAINER *,ArrayOfElements<WiFiCxTLVStaging::_WDI_CONNECT_BSS_ENTRY_CONTAINER> *)
0x140032fe5  mov     edi, eax
0x140032fe7  test    eax, eax
0x140032fe9  jz      short loc_140033038
0x140032feb  lea     rcx, WPP_RECORDER_INITIALIZED
0x140032ff2  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140032ff9  jz      loc_140033158
0x140032fff  mov     ecx, [rbx+10h]
0x140033002  mov     r9d, 172h
0x140033008  mov     [rsp+240h+var_208], eax
0x14003300c  mov     [rsp+240h+var_210], ecx
0x140033010  mov     rcx, cs:WPP_GLOBAL_Control
0x140033017  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x14003301e  mov     [rsp+240h+var_218], rbx
0x140033023  mov     dl, 2
0x140033025  mov     [rsp+240h+var_220], rax
0x14003302a  mov     rcx, [rcx+40h]
0x14003302e  call    WPP_RECORDER_SF_qDD
0x140033033  jmp     loc_140033158
0x140033038  mov     r8, [rbx+218h]
0x14003303f  lea     rax, [rsp+240h+var_1F0]
0x140033044  test    sil, sil
0x140033047  mov     [rsp+240h+var_220], rax
0x14003304c  lea     r9, [rbp+140h+arg_10]
0x140033053  mov     edx, 30h ; '0'
0x140033058  setnz   [rsp+240h+var_1D4]
0x14003305d  lea     rcx, [rsp+240h+var_1E0]
0x140033062  add     r8, 1508h
0x140033069  call    GenerateWdiTaskConnectToIhv
0x14003306e  mov     edi, eax
0x140033070  test    eax, eax
0x140033072  jz      short loc_14003309E
0x140033074  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003307b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140033082  jz      loc_140033158
0x140033088  mov     [rsp+240h+var_208], eax
0x14003308c  mov     r9d, 173h
0x140033092  mov     eax, [rbx+10h]
0x140033095  mov     [rsp+240h+var_210], eax
0x140033099  jmp     loc_140033010
0x14003309e  mov     rcx, rbx; this
0x1400330a1  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x1400330a6  or      esi, 0FFFFFFFFh
0x1400330a9  mov     edx, 10h; unsigned int
0x1400330ae  mov     r8d, esi; unsigned int
0x1400330b1  mov     rcx, rax; this
0x1400330b4  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x1400330b9  mov     edx, [rbp+140h+arg_10]; unsigned int
0x1400330bf  mov     r9d, 34h ; '4'; unsigned __int16
0x1400330c5  mov     rcx, [rsp+240h+var_1F0]; struct _WFC_MESSAGE_METADATA *
0x1400330ca  mov     r8d, eax; unsigned int
0x1400330cd  mov     [rsp+240h+var_220], r15; unsigned int *
0x1400330d2  call    ?FitMessageToBufferSize@CMessageHelper@@SAHPEAU_WFC_MESSAGE_METADATA@@KKGPEAK@Z; CMessageHelper::FitMessageToBufferSize(_WFC_MESSAGE_METADATA *,ulong,ulong,ushort,ulong *)
0x1400330d7  mov     edi, eax
0x1400330d9  test    eax, eax
0x1400330db  jz      short loc_140033147
0x1400330dd  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400330e4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400330eb  jz      short loc_140033158
0x1400330ed  mov     rcx, rbx; this
0x1400330f0  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x1400330f5  mov     r8d, esi; unsigned int
0x1400330f8  mov     edx, 10h; unsigned int
0x1400330fd  mov     rcx, rax; this
0x140033100  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x140033105  mov     rcx, cs:WPP_GLOBAL_Control
0x14003310c  mov     r9d, 174h
0x140033112  mov     [rsp+240h+var_1F8], eax
0x140033116  mov     eax, [rbp+140h+arg_10]
0x14003311c  mov     [rsp+240h+var_200], eax
0x140033120  mov     eax, [rbx+10h]
0x140033123  mov     rcx, [rcx+40h]
0x140033127  mov     [rsp+240h+var_208], edi
0x14003312b  mov     [rsp+240h+var_210], eax
0x14003312f  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x140033136  mov     [rsp+240h+var_218], rbx
0x14003313b  mov     [rsp+240h+var_220], rax
0x140033140  call    WPP_RECORDER_SF_qDDdd
0x140033145  jmp     short loc_140033158
0x140033147  mov     rax, [rsp+240h+var_1F0]
0x14003314c  mov     [r14], rax
0x14003314f  mov     [rsp+240h+var_1F0], 0
0x140033158  mov     rcx, [rsp+240h+var_1F0]; void *
0x14003315d  test    rcx, rcx
0x140033160  jz      short loc_140033167
0x140033162  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140033167  lea     rcx, [rsp+240h+var_1E0]; this
0x14003316c  call    ??1_WDI_TASK_CONNECT_PARAMETERS@WiFiCxTLVStaging@@QEAA@XZ; WiFiCxTLVStaging::_WDI_TASK_CONNECT_PARAMETERS::~_WDI_TASK_CONNECT_PARAMETERS(void)
0x140033171  mov     eax, edi
0x140033173  add     rsp, 218h
0x14003317a  pop     r15
0x14003317c  pop     r14
0x14003317e  pop     rdi
0x14003317f  pop     rsi
0x140033180  pop     rbx
0x140033181  pop     rbp
0x140033182  retn
```
