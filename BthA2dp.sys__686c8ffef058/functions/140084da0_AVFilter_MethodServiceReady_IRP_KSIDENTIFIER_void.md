# AVFilter::MethodServiceReady(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140084da0`
- end: `0x140084eea`
- name: `?MethodServiceReady@AVFilter@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `330`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x140003530`
- `0x14000e690`
- `0x14001027c`
- `0x14001dc6c`
- `0x14001e1f4`
- `0x140058390`
- `0x140084da0`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x140084e2a`
- `ks!KsGetFilterFromIrp` at `0x140084e2a`

## pseudocode

```c
__int64 __fastcall AVFilter::MethodServiceReady(PIRP Irp, struct KSIDENTIFIER *a2, void *a3)
{
  char v4; // bl
  bool v5; // dl
  struct _KSFILTER *FilterFromIrp; // rax
  int v7; // edi
  A2DP_Device *v8; // rbp
  int v9; // edx
  int v10; // r8d

  v4 = 1;
  v5 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      10,
      (__int64)WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids,
      (char)Irp);
  FilterFromIrp = KsGetFilterFromIrp(Irp);
  v7 = -1073741808;
  v8 = (A2DP_Device *)*((_QWORD *)AVFilter::FromKsFilter(FilterFromIrp) + 2);
  if ( (unsigned __int8)IrpList_IsEmpty((char *)v8 + 288) )
  {
    v7 = IoQueue_AddEx((char *)v8 + 288, Irp);
    if ( v7 >= 0 )
      A2DP_Device::OnServiceReady(v8);
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v4 = 0;
  }
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = v4;
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v9,
      v10,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      11,
      (__int64)WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids,
      v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140084da0  push    rbx
0x140084da2  push    rbp
0x140084da3  push    rsi
0x140084da4  push    rdi
0x140084da5  push    r12
0x140084da7  push    r14
0x140084da9  push    r15
0x140084dab  sub     rsp, 50h
0x140084daf  mov     rsi, rcx
0x140084db2  mov     rcx, cs:WPP_GLOBAL_Control
0x140084db9  lea     r15, WPP_GLOBAL_Control
0x140084dc0  mov     bl, 1
0x140084dc2  cmp     rcx, r15
0x140084dc5  jz      short loc_140084DD8
0x140084dc7  mov     eax, [rcx+2Ch]
0x140084dca  test    al, 10h
0x140084dcc  jz      short loc_140084DD8
0x140084dce  cmp     byte ptr [rcx+29h], 4
0x140084dd2  jb      short loc_140084DD8
0x140084dd4  mov     dl, bl
0x140084dd6  jmp     short loc_140084DDA
0x140084dd8  xor     dl, dl
0x140084dda  lea     r12, WPP_RECORDER_INITIALIZED
0x140084de1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140084de8  lea     r9, WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids
0x140084def  setnz   r8b
0x140084df3  test    dl, dl
0x140084df5  jnz     short loc_140084DFC
0x140084df7  test    r8b, r8b
0x140084dfa  jz      short loc_140084E27
0x140084dfc  mov     [rsp+88h+var_48], rsi
0x140084e01  mov     [rsp+88h+var_50], r9
0x140084e06  mov     r9, [rcx+40h]
0x140084e0a  mov     rcx, [rcx+18h]
0x140084e0e  mov     [rsp+88h+var_58], 0Ah
0x140084e15  mov     [rsp+88h+var_60], 5
0x140084e1d  mov     [rsp+88h+var_68], 4
0x140084e22  call    WPP_RECORDER_AND_TRACE_SF_q
0x140084e27  mov     rcx, rsi; Irp
0x140084e2a  call    cs:__imp_KsGetFilterFromIrp
0x140084e31  nop     dword ptr [rax+rax+00h]
0x140084e36  mov     rcx, rax; struct _KSFILTER *
0x140084e39  call    ?FromKsFilter@AVFilter@@SAPEAV1@PEAU_KSFILTER@@@Z; AVFilter::FromKsFilter(_KSFILTER *)
0x140084e3e  mov     edi, 0C0000010h
0x140084e43  mov     rbp, [rax+10h]
0x140084e47  lea     r14, [rbp+120h]
0x140084e4e  mov     rcx, r14
0x140084e51  call    IrpList_IsEmpty
0x140084e56  test    al, al
0x140084e58  jz      short loc_140084E73
0x140084e5a  mov     rdx, rsi
0x140084e5d  mov     rcx, r14
0x140084e60  call    IoQueue_AddEx
0x140084e65  mov     edi, eax
0x140084e67  test    eax, eax
0x140084e69  js      short loc_140084E73
0x140084e6b  mov     rcx, rbp; this
0x140084e6e  call    ?OnServiceReady@A2DP_Device@@QEAAXXZ; A2DP_Device::OnServiceReady(void)
0x140084e73  mov     r10, cs:WPP_GLOBAL_Control
0x140084e7a  cmp     r10, r15
0x140084e7d  jz      short loc_140084E8F
0x140084e7f  mov     ecx, [r10+2Ch]
0x140084e83  test    cl, 10h
0x140084e86  jz      short loc_140084E8F
0x140084e88  cmp     byte ptr [r10+29h], 4
0x140084e8d  jnb     short loc_140084E91
0x140084e8f  xor     bl, bl
0x140084e91  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140084e98  setnz   r8b
0x140084e9c  test    bl, bl
0x140084e9e  jnz     short loc_140084EA5
0x140084ea0  test    r8b, r8b
0x140084ea3  jz      short loc_140084ED8
0x140084ea5  mov     r9, [r10+40h]
0x140084ea9  lea     rcx, WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids
0x140084eb0  mov     dword ptr [rsp+88h+var_48], edi
0x140084eb4  mov     dl, bl
0x140084eb6  mov     [rsp+88h+var_50], rcx
0x140084ebb  mov     rcx, [r10+18h]
0x140084ebf  mov     [rsp+88h+var_58], 0Bh
0x140084ec6  mov     [rsp+88h+var_60], 5
0x140084ece  mov     [rsp+88h+var_68], 4
0x140084ed3  call    WPP_RECORDER_AND_TRACE_SF_d
0x140084ed8  mov     eax, edi
0x140084eda  add     rsp, 50h
0x140084ede  pop     r15
0x140084ee0  pop     r14
0x140084ee2  pop     r12
0x140084ee4  pop     rdi
0x140084ee5  pop     rsi
0x140084ee6  pop     rbp
0x140084ee7  pop     rbx
0x140084ee8  retn
```
