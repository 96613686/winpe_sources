# Avdtp_impl::L2capWrite(void *,void *,ulong,long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *)

- ea: `0x140019340`
- end: `0x140019513`
- name: `?L2capWrite@Avdtp_impl@@AEAAJPEAX0KP6AJPEAU_DEVICE_OBJECT@@PEAU_IRP@@0@Z0@Z`
- size: `467`
- prototype: `__int64 __fastcall(BTH_ADDR *this, void *, void *, __int64, int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *), void *)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140016ae8`
- `0x140019f5c`
- `0x14004ca14`
- `0x14004fac0`
- `0x140050cd0`

## callees

- `0x140019340`
- `0x140019718`
- `0x14002d890`
- `0x140052614`
- `0x1400526fc`
- `0x14005c870`
- `0x14005ce00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001944e`
- `ntoskrnl!ExAllocatePool2` at `0x14001944e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400194f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400194f5`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::L2capWrite(
        BTH_ADDR *this,
        void *a2,
        void *a3,
        __int64 a4,
        int (*a5)(struct _DEVICE_OBJECT *, struct _IRP *, void *),
        void *a6)
{
  size_t v6; // rsi
  int v10; // edx
  int v11; // r8d
  void *Pool2; // rax
  void *v13; // rdi
  int v14; // ebx
  struct _BRB *v15; // rax

  v6 = (unsigned int)a4;
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
  {
    LOBYTE(v11) = 1;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v10) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      LOBYTE(v11) = 0;
    if ( (_BYTE)v10 || (_BYTE)v11 )
      WPP_RECORDER_AND_TRACE_SF_Dqqq(WPP_GLOBAL_Control->AttachedDevice, v10, v11, WPP_GLOBAL_Control->DeviceExtension);
  }
  else
  {
    LOBYTE(v11) = 1;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v10) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      LOBYTE(v11) = 0;
    if ( (_BYTE)v10 || (_BYTE)v11 )
      WPP_RECORDER_AND_TRACE_SF_Dqq(WPP_GLOBAL_Control->AttachedDevice, v10, v11, WPP_GLOBAL_Control->DeviceExtension);
  }
  Pool2 = (void *)ExAllocatePool2(64, v6, 1096172595);
  v13 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, a3, v6);
    v15 = (struct _BRB *)((__int64 (__fastcall *)(__int64, __int64))this[131])(261, 1096172594);
    if ( v15 )
    {
      v15->BrbL2caRegisterServer.BtAddress = this[141];
      v15->BrbL2caUnregisterServer.ServerHandle = a2;
      v15->BrbL2caAclTransfer.TransferFlags = 0;
      v15->BrbL2caAclTransfer.BufferSize = v6;
      v15->BrbL2caRegisterServer.IndicationCallbackContext = v13;
      v14 = Avdtp_impl::SendBTHDWithTempBuffer((Avdtp_impl *)this, v15, v13, a5, a6, 0);
      if ( v14 >= 0 )
        return (unsigned int)v14;
    }
    else
    {
      v14 = -1073741670;
    }
    ExFreePoolWithTag(v13, 0x41564433u);
    return (unsigned int)v14;
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x140019340  push    rbx
0x140019342  push    rbp
0x140019343  push    rsi
0x140019344  push    rdi
0x140019345  push    r12
0x140019347  push    r14
0x140019349  push    r15
0x14001934b  sub     rsp, 60h
0x14001934f  mov     esi, r9d
0x140019352  mov     r15, r8
0x140019355  mov     r14, rdx
0x140019358  mov     rbp, rcx
0x14001935b  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140019360  xor     r12d, r12d
0x140019363  test    eax, eax
0x140019365  jz      short loc_1400193D9
0x140019367  mov     rcx, cs:WPP_GLOBAL_Control
0x14001936e  lea     rax, WPP_GLOBAL_Control
0x140019375  mov     r8b, 1
0x140019378  cmp     rcx, rax
0x14001937b  jz      short loc_14001938D
0x14001937d  mov     eax, [rcx+2Ch]
0x140019380  test    al, 8
0x140019382  jz      short loc_14001938D
0x140019384  cmp     byte ptr [rcx+29h], 5
0x140019388  mov     dl, r8b
0x14001938b  jnb     short loc_140019390
0x14001938d  mov     dl, r12b
0x140019390  lea     rax, WPP_RECORDER_INITIALIZED
0x140019397  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001939e  jz      short loc_1400193A7
0x1400193a0  cmp     [rcx+48h], r12w
0x1400193a5  jnz     short loc_1400193AA
0x1400193a7  mov     r8b, r12b
0x1400193aa  test    dl, dl
0x1400193ac  jnz     short loc_1400193B7
0x1400193ae  test    r8b, r8b
0x1400193b1  jz      loc_140019440
0x1400193b7  mov     r9, [rcx+40h]
0x1400193bb  mov     rcx, [rcx+18h]
0x1400193bf  mov     [rsp+98h+var_40], rbp
0x1400193c4  mov     [rsp+98h+var_48], r14
0x1400193c9  mov     [rsp+98h+var_50], r15
0x1400193ce  mov     [rsp+98h+var_58], esi
0x1400193d2  call    WPP_RECORDER_AND_TRACE_SF_Dqqq
0x1400193d7  jmp     short loc_140019440
0x1400193d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400193e0  lea     rax, WPP_GLOBAL_Control
0x1400193e7  mov     r8b, 1
0x1400193ea  cmp     rcx, rax
0x1400193ed  jz      short loc_1400193FF
0x1400193ef  mov     eax, [rcx+2Ch]
0x1400193f2  test    al, 8
0x1400193f4  jz      short loc_1400193FF
0x1400193f6  cmp     byte ptr [rcx+29h], 5
0x1400193fa  mov     dl, r8b
0x1400193fd  jnb     short loc_140019402
0x1400193ff  mov     dl, r12b
0x140019402  lea     rax, WPP_RECORDER_INITIALIZED
0x140019409  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019410  jz      short loc_140019419
0x140019412  cmp     [rcx+48h], r12w
0x140019417  jnz     short loc_14001941C
0x140019419  mov     r8b, r12b
0x14001941c  test    dl, dl
0x14001941e  jnz     short loc_140019425
0x140019420  test    r8b, r8b
0x140019423  jz      short loc_140019440
0x140019425  mov     r9, [rcx+40h]
0x140019429  mov     rcx, [rcx+18h]
0x14001942d  mov     [rsp+98h+var_48], r14
0x140019432  mov     [rsp+98h+var_50], r15
0x140019437  mov     [rsp+98h+var_58], esi
0x14001943b  call    WPP_RECORDER_AND_TRACE_SF_Dqq
0x140019440  mov     r8d, 41564433h
0x140019446  mov     rdx, rsi
0x140019449  mov     ecx, 40h ; '@'
0x14001944e  call    cs:__imp_ExAllocatePool2
0x140019455  nop     dword ptr [rax+rax+00h]
0x14001945a  mov     rdi, rax
0x14001945d  test    rax, rax
0x140019460  jnz     short loc_14001946C
0x140019462  mov     ebx, 0C000009Ah
0x140019467  jmp     loc_140019501
0x14001946c  mov     r8, rsi; Size
0x14001946f  mov     rdx, r15; Src
0x140019472  mov     rcx, rdi; void *
0x140019475  call    memmove
0x14001947a  mov     rax, [rbp+418h]
0x140019481  mov     edx, 41564432h
0x140019486  mov     ecx, 105h
0x14001948b  call    _guard_dispatch_icall
0x140019490  mov     rdx, rax; struct _BRB *
0x140019493  test    rax, rax
0x140019496  jnz     short loc_14001949F
0x140019498  mov     ebx, 0C000009Ah
0x14001949d  jmp     short loc_1400194ED
0x14001949f  mov     rax, [rbp+468h]
0x1400194a6  mov     r8, rdi; void *
0x1400194a9  mov     r9, [rsp+98h+arg_20]; int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *)
0x1400194b1  mov     rcx, rbp; this
0x1400194b4  mov     [rdx+70h], rax
0x1400194b8  mov     rax, [rsp+98h+arg_28]
0x1400194c0  mov     [rsp+98h+var_70], r12b; bool
0x1400194c5  mov     [rsp+98h+var_78], rax; void *
0x1400194ca  mov     [rdx+78h], r14
0x1400194ce  mov     [rdx+80h], r12d
0x1400194d5  mov     [rdx+84h], esi
0x1400194db  mov     [rdx+88h], rdi
0x1400194e2  call    ?SendBTHDWithTempBuffer@Avdtp_impl@@AEAAJPEAU_BRB@@PEAXP6AJPEAU_DEVICE_OBJECT@@PEAU_IRP@@1@Z1_N@Z; Avdtp_impl::SendBTHDWithTempBuffer(_BRB *,void *,long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *,bool)
0x1400194e7  mov     ebx, eax
0x1400194e9  test    eax, eax
0x1400194eb  jns     short loc_140019501
0x1400194ed  mov     edx, 41564433h; Tag
0x1400194f2  mov     rcx, rdi; P
0x1400194f5  call    cs:__imp_ExFreePoolWithTag
0x1400194fc  nop     dword ptr [rax+rax+00h]
0x140019501  mov     eax, ebx
0x140019503  add     rsp, 60h
0x140019507  pop     r15
0x140019509  pop     r14
0x14001950b  pop     r12
0x14001950d  pop     rdi
0x14001950e  pop     rsi
0x14001950f  pop     rbp
0x140019510  pop     rbx
0x140019511  retn
```
