# CConnectJob::GenerateRoamTaskTlv_TLVParserStaging(ulong *,uchar * *)

- ea: `0x140030d88`
- end: `0x140030fb2`
- name: `?GenerateRoamTaskTlv_TLVParserStaging@CConnectJob@@AEAAHPEAKPEAPEAE@Z`
- size: `554`
- prototype: `__int64 __fastcall(CConnectJob *__hidden this, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x140030b60`

## callees

- `0x14000c940`
- `0x140018270`
- `0x14001e2c0`
- `0x14002eeb8`
- `0x140030d88`
- `0x140040a38`
- `0x1400508d4`
- `0x1400739a0`
- `0x1400a0ec4`
- `0x1400a15ac`
- `0x1400a6c04`

## pseudocode

```c
__int64 __fastcall CConnectJob::GenerateRoamTaskTlv_TLVParserStaging(
        CConnectJob *this,
        unsigned int *a2,
        struct _WFC_MESSAGE_METADATA **a3)
{
  _DWORD *v6; // rdx
  unsigned int v7; // eax
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // edi
  int v11; // r9d
  int v12; // r8d
  unsigned int WdiTaskRoamToIhv; // eax
  CPropertyCache *AdapterPropertyCache; // rax
  unsigned int PropertyULongOrDefault; // eax
  CPropertyCache *v16; // rax
  char v17; // al
  int v18; // edx
  int v19; // r8d
  int v21; // [rsp+30h] [rbp-D0h]
  int v22; // [rsp+38h] [rbp-C8h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  char v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v26; // [rsp+1D0h] [rbp+D0h]
  char v27; // [rsp+1D8h] [rbp+D8h]
  unsigned int v28; // [rsp+208h] [rbp+108h] BYREF
  struct _WFC_MESSAGE_METADATA *v29; // [rsp+218h] [rbp+118h] BYREF

  _WDI_CONNECT_PARAMETERS_CONTAINER::_WDI_CONNECT_PARAMETERS_CONTAINER((_WDI_CONNECT_PARAMETERS_CONTAINER *)&v23);
  *v6 = 0;
  LOBYTE(v6) = 1;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v7 = CConnectJob::FillConnectRoamTaskParameters_TLVParserStaging(this, (__int16)v6, &v23, (__int64)&v25);
  v10 = v7;
  if ( v7 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_12;
    v11 = 364;
    v22 = v7;
    v21 = *((_DWORD *)this + 4);
    goto LABEL_4;
  }
  v12 = *((_QWORD *)this + 67) + 5384;
  v24 = 1;
  WdiTaskRoamToIhv = GenerateWdiTaskRoamToIhv((unsigned int)&v23, 48, v12, (unsigned int)&v28, (__int64)&v29);
  v10 = WdiTaskRoamToIhv;
  if ( WdiTaskRoamToIhv )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v22 = WdiTaskRoamToIhv;
      v11 = 365;
      v21 = *((_DWORD *)this + 4);
LABEL_4:
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        v9,
        v11,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        v21,
        v22);
    }
  }
  else
  {
    AdapterPropertyCache = CJobBase::get_AdapterPropertyCache(this);
    PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault(AdapterPropertyCache, 0x10u, 0xFFFFFFFF);
    v10 = CMessageHelper::FitMessageToBufferSize(v29, v28, PropertyULongOrDefault, 0x34u, a2);
    if ( v10 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = CJobBase::get_AdapterPropertyCache(this);
        v17 = CPropertyCache::GetPropertyULongOrDefault(v16, 0x10u, 0xFFFFFFFF);
        WPP_RECORDER_SF_qDDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          v19,
          366,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v10,
          v28,
          v17);
      }
    }
    else
    {
      *a3 = v29;
      v29 = 0;
    }
  }
LABEL_12:
  if ( v29 )
    operator delete(v29);
  WiFiCxTLVStaging::_WDI_TASK_ROAM_PARAMETERS::~_WDI_TASK_ROAM_PARAMETERS((WiFiCxTLVStaging::_WDI_TASK_ROAM_PARAMETERS *)&v23);
  return v10;
}

```

## disassembly

```asm
0x140030d88  mov     [rsp-8+arg_0], rbx
0x140030d8d  mov     [rsp-8+arg_10], rsi
0x140030d92  push    rbp
0x140030d93  push    rdi
0x140030d94  push    r14
0x140030d96  lea     rbp, [rsp-0E0h]
0x140030d9e  sub     rsp, 1E0h
0x140030da5  mov     rbx, rcx
0x140030da8  mov     rsi, r8
0x140030dab  lea     rcx, [rsp+1F0h+var_1A0]; this
0x140030db0  mov     r14, rdx
0x140030db3  call    ??0_WDI_CONNECT_PARAMETERS_CONTAINER@@QEAA@XZ; _WDI_CONNECT_PARAMETERS_CONTAINER::_WDI_CONNECT_PARAMETERS_CONTAINER(void)
0x140030db8  mov     dword ptr [rdx], 0
0x140030dbe  lea     r9, [rbp+0F0h+var_28]
0x140030dc5  mov     dl, 1
0x140030dc7  mov     [rbp+0F0h+var_28], 0
0x140030dd1  lea     r8, [rsp+1F0h+var_1A0]
0x140030dd6  mov     [rbp+0F0h+var_20], 0
0x140030de1  mov     rcx, rbx; this
0x140030de4  mov     [rbp+0F0h+var_18], 0
0x140030deb  mov     [rbp+0F0h+arg_8], 0
0x140030df5  mov     [rbp+0F0h+arg_18], 0
0x140030e00  call    ?FillConnectRoamTaskParameters_TLVParserStaging@CConnectJob@@AEAAH_NPEAU_WDI_CONNECT_PARAMETERS_CONTAINER@WiFiCxTLVStaging@@PEAU?$ArrayOfElements@U_WDI_CONNECT_BSS_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@@Z; CConnectJob::FillConnectRoamTaskParameters_TLVParserStaging(bool,WiFiCxTLVStaging::_WDI_CONNECT_PARAMETERS_CONTAINER *,ArrayOfElements<WiFiCxTLVStaging::_WDI_CONNECT_BSS_ENTRY_CONTAINER> *)
0x140030e05  mov     edi, eax
0x140030e07  test    eax, eax
0x140030e09  jz      short loc_140030E58
0x140030e0b  lea     rcx, WPP_RECORDER_INITIALIZED
0x140030e12  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140030e19  jz      loc_140030F7C
0x140030e1f  mov     ecx, [rbx+10h]
0x140030e22  mov     r9d, 16Ch
0x140030e28  mov     [rsp+1F0h+var_1B8], eax
0x140030e2c  mov     [rsp+1F0h+var_1C0], ecx
0x140030e30  mov     rcx, cs:WPP_GLOBAL_Control
0x140030e37  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x140030e3e  mov     [rsp+1F0h+var_1C8], rbx
0x140030e43  mov     dl, 2
0x140030e45  mov     [rsp+1F0h+var_1D0], rax
0x140030e4a  mov     rcx, [rcx+40h]
0x140030e4e  call    WPP_RECORDER_SF_qDD
0x140030e53  jmp     loc_140030F7C
0x140030e58  mov     r8, [rbx+218h]
0x140030e5f  lea     rax, [rbp+0F0h+arg_18]
0x140030e66  add     r8, 1508h
0x140030e6d  mov     [rsp+1F0h+var_19C], 1
0x140030e72  lea     r9, [rbp+0F0h+arg_8]
0x140030e79  mov     [rsp+1F0h+var_1D0], rax
0x140030e7e  mov     edx, 30h ; '0'
0x140030e83  lea     rcx, [rsp+1F0h+var_1A0]
0x140030e88  call    GenerateWdiTaskRoamToIhv
0x140030e8d  mov     edi, eax
0x140030e8f  test    eax, eax
0x140030e91  jz      short loc_140030EBD
0x140030e93  lea     rcx, WPP_RECORDER_INITIALIZED
0x140030e9a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140030ea1  jz      loc_140030F7C
0x140030ea7  mov     [rsp+1F0h+var_1B8], eax
0x140030eab  mov     r9d, 16Dh
0x140030eb1  mov     eax, [rbx+10h]
0x140030eb4  mov     [rsp+1F0h+var_1C0], eax
0x140030eb8  jmp     loc_140030E30
0x140030ebd  mov     rcx, rbx; this
0x140030ec0  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x140030ec5  or      r8d, 0FFFFFFFFh; unsigned int
0x140030ec9  mov     edx, 10h; unsigned int
0x140030ece  mov     rcx, rax; this
0x140030ed1  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x140030ed6  mov     edx, [rbp+0F0h+arg_8]; unsigned int
0x140030edc  mov     r9d, 34h ; '4'; unsigned __int16
0x140030ee2  mov     rcx, [rbp+0F0h+arg_18]; struct _WFC_MESSAGE_METADATA *
0x140030ee9  mov     r8d, eax; unsigned int
0x140030eec  mov     [rsp+1F0h+var_1D0], r14; unsigned int *
0x140030ef1  call    ?FitMessageToBufferSize@CMessageHelper@@SAHPEAU_WFC_MESSAGE_METADATA@@KKGPEAK@Z; CMessageHelper::FitMessageToBufferSize(_WFC_MESSAGE_METADATA *,ulong,ulong,ushort,ulong *)
0x140030ef6  mov     edi, eax
0x140030ef8  test    eax, eax
0x140030efa  jz      short loc_140030F67
0x140030efc  lea     rcx, WPP_RECORDER_INITIALIZED
0x140030f03  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140030f0a  jz      short loc_140030F7C
0x140030f0c  mov     rcx, rbx; this
0x140030f0f  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x140030f14  or      r8d, 0FFFFFFFFh; unsigned int
0x140030f18  mov     edx, 10h; unsigned int
0x140030f1d  mov     rcx, rax; this
0x140030f20  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x140030f25  mov     rcx, cs:WPP_GLOBAL_Control
0x140030f2c  mov     r9d, 16Eh
0x140030f32  mov     [rsp+1F0h+var_1A8], eax
0x140030f36  mov     eax, [rbp+0F0h+arg_8]
0x140030f3c  mov     [rsp+1F0h+var_1B0], eax
0x140030f40  mov     eax, [rbx+10h]
0x140030f43  mov     rcx, [rcx+40h]
0x140030f47  mov     [rsp+1F0h+var_1B8], edi
0x140030f4b  mov     [rsp+1F0h+var_1C0], eax
0x140030f4f  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x140030f56  mov     [rsp+1F0h+var_1C8], rbx
0x140030f5b  mov     [rsp+1F0h+var_1D0], rax
0x140030f60  call    WPP_RECORDER_SF_qDDdd
0x140030f65  jmp     short loc_140030F7C
0x140030f67  mov     rax, [rbp+0F0h+arg_18]
0x140030f6e  mov     [rsi], rax
0x140030f71  mov     [rbp+0F0h+arg_18], 0
0x140030f7c  mov     rcx, [rbp+0F0h+arg_18]; void *
0x140030f83  test    rcx, rcx
0x140030f86  jz      short loc_140030F8D
0x140030f88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140030f8d  lea     rcx, [rsp+1F0h+var_1A0]; this
0x140030f92  call    ??1_WDI_TASK_ROAM_PARAMETERS@WiFiCxTLVStaging@@QEAA@XZ; WiFiCxTLVStaging::_WDI_TASK_ROAM_PARAMETERS::~_WDI_TASK_ROAM_PARAMETERS(void)
0x140030f97  lea     r11, [rsp+1F0h+var_10]
0x140030f9f  mov     eax, edi
0x140030fa1  mov     rbx, [r11+20h]
0x140030fa5  mov     rsi, [r11+30h]
0x140030fa9  mov     rsp, r11
0x140030fac  pop     r14
0x140030fae  pop     rdi
0x140030faf  pop     rbp
0x140030fb0  retn
```
