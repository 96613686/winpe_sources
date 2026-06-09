# CConnectJob::GenerateRoamTaskTlv(ulong *,uchar * *)

- ea: `0x140030b60`
- end: `0x140030d7f`
- name: `?GenerateRoamTaskTlv@CConnectJob@@AEAAHPEAKPEAPEAE@Z`
- size: `543`
- prototype: `__int64 __fastcall(CConnectJob *__hidden this, unsigned int *, unsigned __int8 **)`
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
- `0x140030b60`
- `0x140030d88`
- `0x140040a38`
- `0x1400508d4`
- `0x1400739a0`
- `0x1400a0fd0`
- `0x1400a15ac`
- `0x1400a621c`

## pseudocode

```c
__int64 __fastcall CConnectJob::GenerateRoamTaskTlv(CConnectJob *this, unsigned int *a2, unsigned __int8 **a3)
{
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
  int v20; // [rsp+30h] [rbp-D0h]
  int v21; // [rsp+38h] [rbp-C8h]
  struct _WFC_MESSAGE_METADATA *v22; // [rsp+50h] [rbp-B0h] BYREF
  void *v23[47]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[24]; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned int v25; // [rsp+228h] [rbp+128h] BYREF

  if ( (unsigned int)Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline(this, a2, a3) )
    return CConnectJob::GenerateRoamTaskTlv_TLVParserStaging(this, a2, a3);
  _WDI_TASK_ROAM_PARAMETERS::_WDI_TASK_ROAM_PARAMETERS((_WDI_TASK_ROAM_PARAMETERS *)v23);
  v25 = 0;
  v22 = 0;
  *a2 = 0;
  v7 = CConnectJob::FillConnectRoamTaskParameters(this, v23, (__int64)v24, 1);
  v10 = v7;
  if ( v7 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = 367;
      v21 = v7;
      v20 = *((_DWORD *)this + 4);
LABEL_6:
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        v9,
        v11,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        v20,
        v21);
    }
  }
  else
  {
    v12 = *((_QWORD *)this + 67) + 5384;
    BYTE4(v23[0]) = 1;
    WdiTaskRoamToIhv = GenerateWdiTaskRoamToIhv((unsigned int)v23, 48, v12, (unsigned int)&v25, (__int64)&v22);
    v10 = WdiTaskRoamToIhv;
    if ( !WdiTaskRoamToIhv )
    {
      AdapterPropertyCache = CJobBase::get_AdapterPropertyCache(this);
      PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault(AdapterPropertyCache, 0x10u, 0xFFFFFFFF);
      v10 = CMessageHelper::FitMessageToBufferSize(v22, v25, PropertyULongOrDefault, 0x34u, a2);
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
            369,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            v10,
            v25,
            v17);
        }
      }
      else
      {
        *a3 = (unsigned __int8 *)v22;
        v22 = 0;
      }
      goto LABEL_14;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = WdiTaskRoamToIhv;
      v11 = 368;
      v20 = *((_DWORD *)this + 4);
      goto LABEL_6;
    }
  }
LABEL_14:
  if ( v22 )
    operator delete(v22);
  WiFiCxTLVStaging::_WDI_TASK_ROAM_PARAMETERS::~_WDI_TASK_ROAM_PARAMETERS((WiFiCxTLVStaging::_WDI_TASK_ROAM_PARAMETERS *)v23);
  return v10;
}

```

## disassembly

```asm
0x140030b60  mov     [rsp-8+arg_0], rbx
0x140030b65  mov     [rsp-8+arg_8], rsi
0x140030b6a  push    rbp
0x140030b6b  push    rdi
0x140030b6c  push    r14
0x140030b6e  lea     rbp, [rsp-0F0h]
0x140030b76  sub     rsp, 1F0h
0x140030b7d  mov     r14, r8
0x140030b80  mov     rsi, rdx
0x140030b83  mov     rbx, rcx
0x140030b86  call    Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline
0x140030b8b  test    eax, eax
0x140030b8d  jz      short loc_140030BA2
0x140030b8f  mov     r8, r14; unsigned __int8 **
0x140030b92  mov     rdx, rsi; unsigned int *
0x140030b95  mov     rcx, rbx; this
0x140030b98  call    ?GenerateRoamTaskTlv_TLVParserStaging@CConnectJob@@AEAAHPEAKPEAPEAE@Z; CConnectJob::GenerateRoamTaskTlv_TLVParserStaging(ulong *,uchar * *)
0x140030b9d  jmp     loc_140030D66
0x140030ba2  lea     rcx, [rsp+200h+var_1A0]; this
0x140030ba7  call    ??0_WDI_TASK_ROAM_PARAMETERS@@QEAA@XZ; _WDI_TASK_ROAM_PARAMETERS::_WDI_TASK_ROAM_PARAMETERS(void)
0x140030bac  mov     r9b, 1
0x140030baf  mov     [rbp+100h+arg_18], 0
0x140030bb9  lea     r8, [rbp+100h+var_28]
0x140030bc0  mov     [rsp+200h+var_1B0], 0
0x140030bc9  lea     rdx, [rsp+200h+var_1A0]; struct _WDI_CONNECT_PARAMETERS_CONTAINER *
0x140030bce  mov     dword ptr [rsi], 0
0x140030bd4  mov     rcx, rbx; this
0x140030bd7  call    ?FillConnectRoamTaskParameters@CConnectJob@@AEAAHPEAU_WDI_CONNECT_PARAMETERS_CONTAINER@@PEAU?$ArrayOfElements@U_WDI_CONNECT_BSS_ENTRY_CONTAINER@@@@_N@Z; CConnectJob::FillConnectRoamTaskParameters(_WDI_CONNECT_PARAMETERS_CONTAINER *,ArrayOfElements<_WDI_CONNECT_BSS_ENTRY_CONTAINER> *,bool)
0x140030bdc  mov     edi, eax
0x140030bde  test    eax, eax
0x140030be0  jz      short loc_140030C2F
0x140030be2  lea     rcx, WPP_RECORDER_INITIALIZED
0x140030be9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140030bf0  jz      loc_140030D4B
0x140030bf6  mov     ecx, [rbx+10h]
0x140030bf9  mov     r9d, 16Fh
0x140030bff  mov     [rsp+200h+var_1C8], eax
0x140030c03  mov     [rsp+200h+var_1D0], ecx
0x140030c07  mov     rcx, cs:WPP_GLOBAL_Control
0x140030c0e  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x140030c15  mov     [rsp+200h+var_1D8], rbx
0x140030c1a  mov     dl, 2
0x140030c1c  mov     [rsp+200h+var_1E0], rax
0x140030c21  mov     rcx, [rcx+40h]
0x140030c25  call    WPP_RECORDER_SF_qDD
0x140030c2a  jmp     loc_140030D4B
0x140030c2f  mov     r8, [rbx+218h]
0x140030c36  lea     rax, [rsp+200h+var_1B0]
0x140030c3b  add     r8, 1508h
0x140030c42  mov     [rsp+200h+var_19C], 1
0x140030c47  lea     r9, [rbp+100h+arg_18]
0x140030c4e  mov     [rsp+200h+var_1E0], rax
0x140030c53  mov     edx, 30h ; '0'
0x140030c58  lea     rcx, [rsp+200h+var_1A0]
0x140030c5d  call    GenerateWdiTaskRoamToIhv
0x140030c62  mov     edi, eax
0x140030c64  test    eax, eax
0x140030c66  jz      short loc_140030C92
0x140030c68  lea     rcx, WPP_RECORDER_INITIALIZED
0x140030c6f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140030c76  jz      loc_140030D4B
0x140030c7c  mov     [rsp+200h+var_1C8], eax
0x140030c80  mov     r9d, 170h
0x140030c86  mov     eax, [rbx+10h]
0x140030c89  mov     [rsp+200h+var_1D0], eax
0x140030c8d  jmp     loc_140030C07
0x140030c92  mov     rcx, rbx; this
0x140030c95  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x140030c9a  or      r8d, 0FFFFFFFFh; unsigned int
0x140030c9e  mov     edx, 10h; unsigned int
0x140030ca3  mov     rcx, rax; this
0x140030ca6  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x140030cab  mov     edx, [rbp+100h+arg_18]; unsigned int
0x140030cb1  mov     r9d, 34h ; '4'; unsigned __int16
0x140030cb7  mov     rcx, [rsp+200h+var_1B0]; struct _WFC_MESSAGE_METADATA *
0x140030cbc  mov     r8d, eax; unsigned int
0x140030cbf  mov     [rsp+200h+var_1E0], rsi; unsigned int *
0x140030cc4  call    ?FitMessageToBufferSize@CMessageHelper@@SAHPEAU_WFC_MESSAGE_METADATA@@KKGPEAK@Z; CMessageHelper::FitMessageToBufferSize(_WFC_MESSAGE_METADATA *,ulong,ulong,ushort,ulong *)
0x140030cc9  mov     edi, eax
0x140030ccb  test    eax, eax
0x140030ccd  jz      short loc_140030D3A
0x140030ccf  lea     rcx, WPP_RECORDER_INITIALIZED
0x140030cd6  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140030cdd  jz      short loc_140030D4B
0x140030cdf  mov     rcx, rbx; this
0x140030ce2  call    ?get_AdapterPropertyCache@CJobBase@@IEAAPEAVCAdapterPropertyCache@@XZ; CJobBase::get_AdapterPropertyCache(void)
0x140030ce7  or      r8d, 0FFFFFFFFh; unsigned int
0x140030ceb  mov     edx, 10h; unsigned int
0x140030cf0  mov     rcx, rax; this
0x140030cf3  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x140030cf8  mov     rcx, cs:WPP_GLOBAL_Control
0x140030cff  mov     r9d, 171h
0x140030d05  mov     [rsp+200h+var_1B8], eax
0x140030d09  mov     eax, [rbp+100h+arg_18]
0x140030d0f  mov     [rsp+200h+var_1C0], eax
0x140030d13  mov     eax, [rbx+10h]
0x140030d16  mov     rcx, [rcx+40h]
0x140030d1a  mov     [rsp+200h+var_1C8], edi
0x140030d1e  mov     [rsp+200h+var_1D0], eax
0x140030d22  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x140030d29  mov     [rsp+200h+var_1D8], rbx
0x140030d2e  mov     [rsp+200h+var_1E0], rax
0x140030d33  call    WPP_RECORDER_SF_qDDdd
0x140030d38  jmp     short loc_140030D4B
0x140030d3a  mov     rax, [rsp+200h+var_1B0]
0x140030d3f  mov     [r14], rax
0x140030d42  mov     [rsp+200h+var_1B0], 0
0x140030d4b  mov     rcx, [rsp+200h+var_1B0]; void *
0x140030d50  test    rcx, rcx
0x140030d53  jz      short loc_140030D5A
0x140030d55  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140030d5a  lea     rcx, [rsp+200h+var_1A0]; this
0x140030d5f  call    ??1_WDI_TASK_ROAM_PARAMETERS@WiFiCxTLVStaging@@QEAA@XZ; WiFiCxTLVStaging::_WDI_TASK_ROAM_PARAMETERS::~_WDI_TASK_ROAM_PARAMETERS(void)
0x140030d64  mov     eax, edi
0x140030d66  lea     r11, [rsp+200h+var_10]
0x140030d6e  mov     rbx, [r11+20h]
0x140030d72  mov     rsi, [r11+28h]
0x140030d76  mov     rsp, r11
0x140030d79  pop     r14
0x140030d7b  pop     rdi
0x140030d7c  pop     rbp
0x140030d7d  retn
```
