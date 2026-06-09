# CJobBase::Initialize(EventQueue *,DeviceCommandScheduler *,ActiveJobsList *,SerializedJobList *,_WFC_JOB_TYPE,bool,bool,_WFC_SERIALIZED_JOB_PRIORITY_SCOPE,_WFC_SERIALIZED_JOB_PRIORITY,IPropertyCacheDirectory *,INdisConversion *,ulong,bool,bool)

- ea: `0x14001d860`
- end: `0x14001da37`
- name: `?Initialize@CJobBase@@IEAAHPEAVEventQueue@@PEAVDeviceCommandScheduler@@PEAVActiveJobsList@@PEAVSerializedJobList@@W4_WFC_JOB_TYPE@@_N5W4_WFC_SERIALIZED_JOB_PRIORITY_SCOPE@@W4_WFC_SERIALIZED_JOB_PRIORITY@@PEAVIPropertyCacheDirectory@@PEAVINdisConversion@@K55@Z`
- size: `471`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `29`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002dc1c`
- `0x14005c2dc`
- `0x140065bc0`
- `0x140065c80`
- `0x140065d40`
- `0x140065e00`
- `0x140065ec0`
- `0x140065f80`
- `0x140068f4c`
- `0x140068fdc`
- `0x14006906c`
- `0x140069100`
- `0x1400693f4`
- `0x140069494`
- `0x140069540`
- `0x14006c458`
- `0x14006c550`
- `0x140079958`
- `0x140079f40`
- `0x140084700`
- `0x1400903cc`
- `0x140090b08`
- `0x14009d240`
- `0x14009f3e8`
- `0x1400aa1c0`
- `0x1400aa534`
- `0x1400c06bc`
- `0x1400c7cb0`
- `0x1400c7dac`

## callees

- `0x14001d860`
- `0x14001e2c0`
- `0x14001eed0`

## pseudocode

```c
__int64 __fastcall CJobBase::Initialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        unsigned __int8 a7,
        unsigned __int8 a8,
        int a9,
        int a10,
        __int64 a11,
        __int64 a12,
        int a13,
        char a14)
{
  __int64 v16; // rdi
  __int64 v17; // r14
  unsigned int v18; // ebx

  v16 = a2;
  v17 = a3;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      10,
      (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
      a1,
      *(_DWORD *)(a1 + 16));
  }
  if ( !v16 || !v17 || !a4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        a3,
        11,
        (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
        a1,
        *(_DWORD *)(a1 + 16));
    }
    goto LABEL_14;
  }
  LODWORD(a2) = a8;
  LODWORD(a3) = a7;
  if ( !a12 && (a8 || a7) )
  {
LABEL_14:
    v18 = -1073741811;
    goto LABEL_15;
  }
  v18 = 0;
  *(_QWORD *)(a1 + 88) = a5;
  *(_DWORD *)(a1 + 44) = a9;
  *(_DWORD *)(a1 + 48) = a10;
  *(_DWORD *)(a1 + 60) = a6;
  *(_DWORD *)(a1 + 56) = a13;
  *(_QWORD *)(a1 + 496) = a11;
  *(_BYTE *)(a1 + 504) = a14;
  *(_QWORD *)(a1 + 32) = v16;
  *(_QWORD *)(a1 + 72) = v17;
  *(_QWORD *)(a1 + 80) = a4;
  *(_BYTE *)(a1 + 40) = a7;
  *(_BYTE *)(a1 + 41) = a8;
  *(_QWORD *)(a1 + 488) = a12;
  *(_BYTE *)(a1 + 506) = 0;
LABEL_15:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      12,
      (__int64)WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids,
      a1,
      *(_DWORD *)(a1 + 16),
      v18);
  }
  return v18;
}

```

## disassembly

```asm
0x14001d860  push    rsi
0x14001d862  push    r12
0x14001d864  sub     rsp, 48h
0x14001d868  mov     [rsp+58h+arg_8], rbp
0x14001d86d  mov     rsi, rcx
0x14001d870  mov     [rsp+58h+arg_10], rdi
0x14001d875  mov     rbp, r9
0x14001d878  mov     [rsp+58h+arg_18], r14
0x14001d87d  mov     rdi, rdx
0x14001d880  mov     [rsp+58h+var_18], r15
0x14001d885  mov     r14, r8
0x14001d888  lea     r15, WPP_RECORDER_INITIALIZED
0x14001d88f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001d896  lea     r12, WPP_a168a220f6e038dcb24b8923f2bc6606_Traceguids
0x14001d89d  jz      short loc_14001D8D5
0x14001d89f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d8a6  cmp     byte ptr [rcx+29h], 5
0x14001d8aa  jnb     short loc_14001D8B3
0x14001d8ac  cmp     word ptr [rcx+48h], 0
0x14001d8b1  jz      short loc_14001D8D5
0x14001d8b3  mov     eax, [rsi+10h]
0x14001d8b6  mov     r9d, 0Ah
0x14001d8bc  mov     rcx, [rcx+40h]
0x14001d8c0  mov     dl, 5
0x14001d8c2  mov     [rsp+58h+var_28], eax
0x14001d8c6  mov     [rsp+58h+var_30], rsi
0x14001d8cb  mov     [rsp+58h+var_38], r12
0x14001d8d0  call    WPP_RECORDER_SF_qD
0x14001d8d5  mov     [rsp+58h+arg_0], rbx
0x14001d8da  test    rdi, rdi
0x14001d8dd  jz      loc_14001D999
0x14001d8e3  test    r14, r14
0x14001d8e6  jz      loc_14001D999
0x14001d8ec  test    rbp, rbp
0x14001d8ef  jz      loc_14001D999
0x14001d8f5  mov     rcx, [rsp+58h+arg_58]
0x14001d8fd  movzx   edx, [rsp+58h+arg_38]
0x14001d905  movzx   r8d, [rsp+58h+arg_30]
0x14001d90e  test    rcx, rcx
0x14001d911  jnz     short loc_14001D924
0x14001d913  test    dl, dl
0x14001d915  jnz     loc_14001D9CB
0x14001d91b  test    r8b, r8b
0x14001d91e  jnz     loc_14001D9CB
0x14001d924  mov     rax, [rsp+58h+arg_20]
0x14001d92c  xor     ebx, ebx
0x14001d92e  mov     [rsi+58h], rax
0x14001d932  mov     eax, [rsp+58h+arg_40]
0x14001d939  mov     [rsi+2Ch], eax
0x14001d93c  mov     eax, [rsp+58h+arg_48]
0x14001d943  mov     [rsi+30h], eax
0x14001d946  mov     eax, [rsp+58h+arg_28]
0x14001d94d  mov     [rsi+3Ch], eax
0x14001d950  mov     eax, [rsp+58h+arg_60]
0x14001d957  mov     [rsi+38h], eax
0x14001d95a  mov     rax, [rsp+58h+arg_50]
0x14001d962  mov     [rsi+1F0h], rax
0x14001d969  movzx   eax, [rsp+58h+arg_68]
0x14001d971  mov     [rsi+1F8h], al
0x14001d977  mov     [rsi+20h], rdi
0x14001d97b  mov     [rsi+48h], r14
0x14001d97f  mov     [rsi+50h], rbp
0x14001d983  mov     [rsi+28h], r8b
0x14001d987  mov     [rsi+29h], dl
0x14001d98a  mov     [rsi+1E8h], rcx
0x14001d991  mov     [rsi+1FAh], bl
0x14001d997  jmp     short loc_14001D9D0
0x14001d999  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001d9a0  jz      short loc_14001D9CB
0x14001d9a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d9a9  mov     r9d, 0Bh
0x14001d9af  mov     eax, [rsi+10h]
0x14001d9b2  mov     dl, 2
0x14001d9b4  mov     [rsp+58h+var_28], eax
0x14001d9b8  mov     [rsp+58h+var_30], rsi
0x14001d9bd  mov     rcx, [rcx+40h]
0x14001d9c1  mov     [rsp+58h+var_38], r12
0x14001d9c6  call    WPP_RECORDER_SF_qD
0x14001d9cb  mov     ebx, 0C000000Dh
0x14001d9d0  mov     r14, [rsp+58h+arg_18]
0x14001d9d5  mov     rdi, [rsp+58h+arg_10]
0x14001d9da  mov     rbp, [rsp+58h+arg_8]
0x14001d9df  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001d9e6  mov     r15, [rsp+58h+var_18]
0x14001d9eb  jz      short loc_14001DA27
0x14001d9ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d9f4  cmp     byte ptr [rcx+29h], 5
0x14001d9f8  jnb     short loc_14001DA01
0x14001d9fa  cmp     word ptr [rcx+48h], 0
0x14001d9ff  jz      short loc_14001DA27
0x14001da01  mov     eax, [rsi+10h]
0x14001da04  mov     r9d, 0Ch
0x14001da0a  mov     rcx, [rcx+40h]
0x14001da0e  mov     dl, 5
0x14001da10  mov     [rsp+58h+var_20], ebx
0x14001da14  mov     [rsp+58h+var_28], eax
0x14001da18  mov     [rsp+58h+var_30], rsi
0x14001da1d  mov     [rsp+58h+var_38], r12
0x14001da22  call    WPP_RECORDER_SF_qDD
0x14001da27  mov     eax, ebx
0x14001da29  mov     rbx, [rsp+58h+arg_0]
0x14001da2e  add     rsp, 48h
0x14001da32  pop     r12
0x14001da34  pop     rsi
0x14001da35  retn
```
