# CRegistryHelper::ReadAdapterRegistryString(_UNICODE_STRING *,_WDF_OBJECT_ATTRIBUTES *,WDFSTRING__ * *)

- ea: `0x14008218c`
- end: `0x140082346`
- name: `?ReadAdapterRegistryString@CRegistryHelper@@QEAAHPEAU_UNICODE_STRING@@PEAU_WDF_OBJECT_ATTRIBUTES@@PEAPEAUWDFSTRING__@@@Z`
- size: `442`
- prototype: `int(CRegistryHelper *__hidden this, struct _UNICODE_STRING *, struct _WDF_OBJECT_ATTRIBUTES *, struct WDFSTRING__ **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x140077e34`

## callees

- `0x140017a90`
- `0x140034ec4`
- `0x14008218c`
- `0x14008234c`
- `0x1400a4630`
- `0x1400da680`

## import_xrefs

- `NDIS!NdisReadConfiguration` at `0x140082263`
- `NDIS!NdisReadConfiguration` at `0x140082263`

## pseudocode

```c
__int64 __fastcall CRegistryHelper::ReadAdapterRegistryString(
        CRegistryHelper *this,
        struct _UNICODE_STRING *a2,
        struct _WDF_OBJECT_ATTRIBUTES *a3,
        struct WDFSTRING__ **a4)
{
  bool v4; // zf
  __int64 result; // rax
  int v9; // edx
  void *v10; // r8
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  int v14; // r8d
  char v15; // [rsp+28h] [rbp-58h]
  __int128 v16; // [rsp+40h] [rbp-40h] BYREF
  __int128 v17; // [rsp+50h] [rbp-30h]
  __int128 v18; // [rsp+60h] [rbp-20h]
  __int64 v19; // [rsp+70h] [rbp-10h]
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+A0h] [rbp+20h] BYREF
  int Status; // [rsp+B0h] [rbp+30h] BYREF
  int v22; // [rsp+B4h] [rbp+34h]

  v22 = HIDWORD(a3);
  Status = 0;
  v4 = *((_QWORD *)this + 1) == 0;
  v17 = 0;
  v19 = 0;
  v16 = 0;
  LODWORD(v16) = 56;
  v18 = 0;
  *(_QWORD *)&v18 = g_pWdiDriver->m_CtlDevice.m_WdfDevice;
  *((_QWORD *)&v17 + 1) = 0x100000001LL;
  if ( v4 )
  {
    result = CRegistryHelper::Open(this);
    Status = result;
    if ( (_DWORD)result )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return result;
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        29,
        (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
        result);
      return (unsigned int)Status;
    }
  }
  v10 = (void *)*((_QWORD *)this + 1);
  ParameterValue = 0;
  NdisReadConfiguration(&Status, &ParameterValue, v10, a2, NdisParameterString);
  result = (unsigned int)Status;
  if ( Status )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return result;
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_SD(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      v12,
      30,
      (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
      (__int64)a2->Buffer,
      Status);
    return (unsigned int)Status;
  }
  v13 = ((__int64 (__fastcall *)(_QWORD, union _NDIS_CONFIGURATION_PARAMETER::$CAEDC0C5BA1E496165C848BD75AE74FE *, __int128 *, struct WDFSTRING__ **))WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[38].DeferredContext)(
          *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement,
          &ParameterValue->ParameterData,
          &v16,
          a4);
  result = (v13 >> 31) & 0xC0000001;
  Status = (v13 >> 31) & 0xC0000001;
  if ( v13 < 0 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v15 = v13;
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      v14,
      31,
      (__int64)WPP_19d62edbdf383644155d22999bb9fee2_Traceguids,
      v15);
    return (unsigned int)Status;
  }
  return result;
}

```

## disassembly

```asm
0x14008218c  mov     [rsp-18h+arg_8], rbx
0x140082191  mov     qword ptr [rsp-18h+Status], r8
0x140082196  push    rbp
0x140082197  push    rsi
0x140082198  push    rdi
0x140082199  mov     rbp, rsp
0x14008219c  sub     rsp, 80h
0x1400821a3  xor     eax, eax
0x1400821a5  mov     [rbp+Status], 0
0x1400821ac  cmp     qword ptr [rcx+8], 0
0x1400821b1  xorps   xmm0, xmm0
0x1400821b4  movups  [rbp+var_30], xmm0
0x1400821b8  mov     [rbp+var_10], rax
0x1400821bc  mov     rdi, rdx
0x1400821bf  mov     rax, cs:?g_pWdiDriver@@3PEAVCWdiDriver@@EA; CWdiDriver * g_pWdiDriver
0x1400821c6  mov     rsi, r9
0x1400821c9  movups  [rbp+var_40], xmm0
0x1400821cd  mov     rbx, rcx
0x1400821d0  mov     dword ptr [rbp+var_40], 38h ; '8'
0x1400821d7  movups  [rbp+var_20], xmm0
0x1400821db  mov     rdx, [rax+28h]
0x1400821df  mov     qword ptr [rbp+var_20], rdx
0x1400821e3  mov     dword ptr [rbp+var_30+8], 1
0x1400821ea  mov     dword ptr [rbp+var_30+0Ch], 1
0x1400821f1  jnz     short loc_140082244
0x1400821f3  call    ?Open@CRegistryHelper@@AEAAHXZ; CRegistryHelper::Open(void)
0x1400821f8  mov     [rbp+Status], eax
0x1400821fb  test    eax, eax
0x1400821fd  jz      short loc_140082244
0x1400821ff  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140082206  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008220d  jz      loc_140082332
0x140082213  mov     rcx, cs:WPP_GLOBAL_Control
0x14008221a  mov     r9d, 1Dh
0x140082220  mov     dword ptr [rsp+80h+var_58], eax
0x140082224  mov     dl, 2
0x140082226  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x14008222d  mov     qword ptr [rsp+80h+ParameterType], rax
0x140082232  mov     rcx, [rcx+40h]
0x140082236  lea     r8d, [r9-1Ch]
0x14008223a  call    WPP_RECORDER_SF_D
0x14008223f  jmp     loc_14008232F
0x140082244  mov     r8, [rbx+8]; ConfigurationHandle
0x140082248  lea     rdx, [rbp+ParameterValue]; ParameterValue
0x14008224c  mov     r9, rdi; Keyword
0x14008224f  mov     [rbp+ParameterValue], 0
0x140082257  lea     rcx, [rbp+Status]; Status
0x14008225b  mov     [rsp+80h+ParameterType], 2; ParameterType
0x140082263  call    cs:__imp_NdisReadConfiguration
0x14008226a  nop     dword ptr [rax+rax+00h]
0x14008226f  mov     eax, [rbp+Status]
0x140082272  test    eax, eax
0x140082274  jz      short loc_1400822BD
0x140082276  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008227d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140082284  jz      loc_140082332
0x14008228a  mov     rcx, cs:WPP_GLOBAL_Control
0x140082291  mov     r9d, 1Eh
0x140082297  mov     [rsp+80h+var_50], eax
0x14008229b  mov     dl, 2
0x14008229d  mov     rax, [rdi+8]
0x1400822a1  mov     [rsp+80h+var_58], rax
0x1400822a6  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x1400822ad  mov     rcx, [rcx+40h]
0x1400822b1  mov     qword ptr [rsp+80h+ParameterType], rax
0x1400822b6  call    WPP_RECORDER_SF_SD
0x1400822bb  jmp     short loc_14008232F
0x1400822bd  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400822c4  lea     r8, [rbp+var_40]
0x1400822c8  mov     rdx, [rbp+ParameterValue]
0x1400822cc  mov     r9, rsi
0x1400822cf  mov     rcx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x1400822d6  add     rdx, 8
0x1400822da  mov     rax, [rax+9A0h]
0x1400822e1  call    _guard_dispatch_icall
0x1400822e6  mov     edx, eax
0x1400822e8  sar     eax, 1Fh
0x1400822eb  and     eax, 0C0000001h
0x1400822f0  mov     [rbp+Status], eax
0x1400822f3  test    edx, edx
0x1400822f5  jns     short loc_140082332
0x1400822f7  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400822fe  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140082305  jz      short loc_140082332
0x140082307  mov     rcx, cs:WPP_GLOBAL_Control
0x14008230e  lea     rax, WPP_19d62edbdf383644155d22999bb9fee2_Traceguids
0x140082315  mov     dword ptr [rsp+80h+var_58], edx
0x140082319  mov     r9d, 1Fh
0x14008231f  mov     dl, 2
0x140082321  mov     qword ptr [rsp+80h+ParameterType], rax
0x140082326  mov     rcx, [rcx+40h]
0x14008232a  call    WPP_RECORDER_SF_d
0x14008232f  mov     eax, [rbp+Status]
0x140082332  mov     rbx, [rsp+80h+arg_8]
0x14008233a  add     rsp, 80h
0x140082341  pop     rdi
0x140082342  pop     rsi
0x140082343  pop     rbp
0x140082344  retn
```
