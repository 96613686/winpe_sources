# Avdtp_impl::AcceptIncomingMediaChannelConnection(void *,ulong)

- ea: `0x140046688`
- end: `0x1400468b6`
- name: `?AcceptIncomingMediaChannelConnection@Avdtp_impl@@AEAAJPEAXK@Z`
- size: `558`
- prototype: `__int64 __fastcall(Avdtp_impl *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400516e0`

## callees

- `0x14000e690`
- `0x140010628`
- `0x140019718`
- `0x14002d890`
- `0x140046688`
- `0x14004cc08`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400467c8`
- `ntoskrnl!ExAllocatePool2` at `0x1400467c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046884`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046884`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::AcceptIncomingMediaChannelConnection(Avdtp_impl *this, void *a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // ebp
  int v7; // edx
  __int64 v8; // r8
  __int64 v9; // rbx
  _DWORD *Pool2; // r14
  int v11; // ebx

  v4 = a3;
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
  {
    LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v8,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        4,
        70,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        v4,
        (char)this);
  }
  else
  {
    LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v8,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        4,
        71,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        v4);
  }
  v9 = (*((__int64 (__fastcall **)(__int64, __int64, __int64))this + 131))(531, 1096172594, v8);
  if ( !v9 )
    return (unsigned int)-1073741670;
  Pool2 = (_DWORD *)ExAllocatePool2(64, 24, 1096172592);
  if ( !Pool2 )
  {
    (*((void (__fastcall **)(__int64))this + 132))(v9);
    return (unsigned int)-1073741670;
  }
  *(_QWORD *)(v9 + 280) = *((_QWORD *)this + 136);
  if ( v4 >= 4 )
  {
    *(_WORD *)(v9 + 120) = 4;
  }
  else
  {
    *(_WORD *)(v9 + 120) = 0;
    *(_QWORD *)(v9 + 128) = *((_QWORD *)this + 141);
  }
  *(_QWORD *)(v9 + 112) = a2;
  *(_DWORD *)(v9 + 124) = 0;
  Avdtp_impl::InitializeAvdtpConnectionParameters(
    (struct _BRB_L2CA_OPEN_ENHANCED_CHANNEL *)v9,
    *((_WORD *)this + 556),
    1);
  *(_QWORD *)(v9 + 264) = Avdtp_impl::Indication_Callback;
  *(_DWORD *)(v9 + 256) = 65;
  *(_QWORD *)(v9 + 272) = this;
  *(_QWORD *)Pool2 = this;
  Pool2[2] = v4;
  v11 = Avdtp_impl::SendBTHDWithTempBuffer(
          this,
          (struct _BRB *)v9,
          0,
          (int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *))Avdtp_impl::L2CA_OPEN_CHANNEL_Completion_Acceptor_Media,
          Pool2,
          0);
  if ( v11 < 0 )
    ExFreePoolWithTag(Pool2, 0x41564430u);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140046688  push    rbx
0x14004668a  push    rbp
0x14004668b  push    rsi
0x14004668c  push    rdi
0x14004668d  push    r14
0x14004668f  push    r15
0x140046691  sub     rsp, 58h
0x140046695  mov     ebp, r8d
0x140046698  mov     r15, rdx
0x14004669b  mov     rsi, rcx
0x14004669e  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400466a3  test    eax, eax
0x1400466a5  jz      short loc_140046725
0x1400466a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400466ae  lea     rax, WPP_GLOBAL_Control
0x1400466b5  mov     edi, 4
0x1400466ba  cmp     rcx, rax
0x1400466bd  jz      short loc_1400466D0
0x1400466bf  mov     eax, [rcx+2Ch]
0x1400466c2  test    al, 8
0x1400466c4  jz      short loc_1400466D0
0x1400466c6  cmp     [rcx+29h], dil
0x1400466ca  jb      short loc_1400466D0
0x1400466cc  mov     dl, 1
0x1400466ce  jmp     short loc_1400466D2
0x1400466d0  xor     dl, dl
0x1400466d2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400466d9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400466e0  setnz   r8b
0x1400466e4  test    dl, dl
0x1400466e6  jnz     short loc_1400466F1
0x1400466e8  test    r8b, r8b
0x1400466eb  jz      loc_140046798
0x1400466f1  mov     r9, [rcx+40h]
0x1400466f5  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x1400466fc  mov     rcx, [rcx+18h]
0x140046700  mov     [rsp+88h+var_40], rsi
0x140046705  mov     [rsp+88h+var_48], ebp
0x140046709  mov     [rsp+88h+var_50], rax
0x14004670e  mov     [rsp+88h+var_58], 46h ; 'F'
0x140046715  mov     dword ptr [rsp+88h+var_60], edi
0x140046719  mov     byte ptr [rsp+88h+var_68], dil
0x14004671e  call    WPP_RECORDER_AND_TRACE_SF_dq
0x140046723  jmp     short loc_140046798
0x140046725  mov     rcx, cs:WPP_GLOBAL_Control
0x14004672c  lea     rax, WPP_GLOBAL_Control
0x140046733  mov     edi, 4
0x140046738  cmp     rcx, rax
0x14004673b  jz      short loc_14004674E
0x14004673d  mov     eax, [rcx+2Ch]
0x140046740  test    al, 8
0x140046742  jz      short loc_14004674E
0x140046744  cmp     [rcx+29h], dil
0x140046748  jb      short loc_14004674E
0x14004674a  mov     dl, 1
0x14004674c  jmp     short loc_140046750
0x14004674e  xor     dl, dl
0x140046750  lea     rax, WPP_RECORDER_INITIALIZED
0x140046757  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004675e  setnz   r8b
0x140046762  test    dl, dl
0x140046764  jnz     short loc_14004676B
0x140046766  test    r8b, r8b
0x140046769  jz      short loc_140046798
0x14004676b  mov     r9, [rcx+40h]
0x14004676f  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x140046776  mov     rcx, [rcx+18h]
0x14004677a  mov     [rsp+88h+var_48], ebp
0x14004677e  mov     [rsp+88h+var_50], rax
0x140046783  mov     [rsp+88h+var_58], 47h ; 'G'
0x14004678a  mov     dword ptr [rsp+88h+var_60], edi
0x14004678e  mov     byte ptr [rsp+88h+var_68], dil
0x140046793  call    WPP_RECORDER_AND_TRACE_SF_d
0x140046798  mov     rax, [rsi+418h]
0x14004679f  mov     edx, 41564432h
0x1400467a4  mov     ecx, 213h
0x1400467a9  call    _guard_dispatch_icall
0x1400467ae  mov     rbx, rax
0x1400467b1  test    rax, rax
0x1400467b4  jz      loc_1400468A1
0x1400467ba  mov     edx, 18h
0x1400467bf  mov     r8d, 41564430h
0x1400467c5  lea     ecx, [rdx+28h]
0x1400467c8  call    cs:__imp_ExAllocatePool2
0x1400467cf  nop     dword ptr [rax+rax+00h]
0x1400467d4  mov     r14, rax
0x1400467d7  test    rax, rax
0x1400467da  jz      loc_140046892
0x1400467e0  mov     rcx, [rsi+440h]
0x1400467e7  mov     [rbx+118h], rcx
0x1400467ee  cmp     ebp, edi
0x1400467f0  jnb     short loc_140046808
0x1400467f2  xor     ecx, ecx
0x1400467f4  mov     [rbx+78h], cx
0x1400467f8  mov     rcx, [rsi+468h]
0x1400467ff  mov     [rbx+80h], rcx
0x140046806  jmp     short loc_14004680C
0x140046808  mov     [rbx+78h], di
0x14004680c  mov     [rbx+70h], r15
0x140046810  mov     r8b, 1; bool
0x140046813  mov     dword ptr [rbx+7Ch], 0
0x14004681a  mov     rcx, rbx; struct _BRB_L2CA_OPEN_ENHANCED_CHANNEL *
0x14004681d  movzx   edx, word ptr [rsi+458h]; unsigned __int16
0x140046824  call    ?InitializeAvdtpConnectionParameters@Avdtp_impl@@CAXPEAU_BRB_L2CA_OPEN_ENHANCED_CHANNEL@@G_N@Z; Avdtp_impl::InitializeAvdtpConnectionParameters(_BRB_L2CA_OPEN_ENHANCED_CHANNEL *,ushort,bool)
0x140046829  lea     rax, ?Indication_Callback@Avdtp_impl@@CAXPEAXW4_INDICATION_CODE@@PEAU_INDICATION_PARAMETERS_ENHANCED@@@Z; Avdtp_impl::Indication_Callback(void *,_INDICATION_CODE,_INDICATION_PARAMETERS_ENHANCED *)
0x140046830  mov     [rsp+88h+var_60], 0; bool
0x140046835  lea     r9, ?L2CA_OPEN_CHANNEL_Completion_Acceptor_Media@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *)
0x14004683c  mov     [rbx+108h], rax
0x140046843  xor     r8d, r8d; void *
0x140046846  mov     dword ptr [rbx+100h], 41h ; 'A'
0x140046850  mov     rdx, rbx; struct _BRB *
0x140046853  mov     [rbx+110h], rsi
0x14004685a  mov     rcx, rsi; this
0x14004685d  mov     [r14], rsi
0x140046860  mov     [r14+8], ebp
0x140046864  mov     [rsp+88h+var_68], r14; void *
0x140046869  call    ?SendBTHDWithTempBuffer@Avdtp_impl@@AEAAJPEAU_BRB@@PEAXP6AJPEAU_DEVICE_OBJECT@@PEAU_IRP@@1@Z1_N@Z; Avdtp_impl::SendBTHDWithTempBuffer(_BRB *,void *,long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *,bool)
0x14004686e  xor     ecx, ecx
0x140046870  mov     ebx, eax
0x140046872  test    eax, eax
0x140046874  cmovs   rcx, r14; P
0x140046878  jns     short loc_1400468A6
0x14004687a  test    rcx, rcx
0x14004687d  jz      short loc_1400468A6
0x14004687f  mov     edx, 41564430h; Tag
0x140046884  call    cs:__imp_ExFreePoolWithTag
0x14004688b  nop     dword ptr [rax+rax+00h]
0x140046890  jmp     short loc_1400468A6
0x140046892  mov     rax, [rsi+420h]
0x140046899  mov     rcx, rbx
0x14004689c  call    _guard_dispatch_icall
0x1400468a1  mov     ebx, 0C000009Ah
0x1400468a6  mov     eax, ebx
0x1400468a8  add     rsp, 58h
0x1400468ac  pop     r15
0x1400468ae  pop     r14
0x1400468b0  pop     rdi
0x1400468b1  pop     rsi
0x1400468b2  pop     rbp
0x1400468b3  pop     rbx
0x1400468b4  retn
```
