# A2dpInbandAudioDevice::CreateFilterDescriptor(_GUID const &,bool,_GUID const &)

- ea: `0x14007c67c`
- end: `0x14007cb60`
- name: `?CreateFilterDescriptor@A2dpInbandAudioDevice@@AEAAJAEBU_GUID@@_N0@Z`
- size: `1252`
- prototype: `__int64 __fastcall(A2dpInbandAudioDevice *__hidden this, const struct _GUID *, bool, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14007cdb0`

## callees

- `0x140010628`
- `0x14007c5b0`
- `0x14007c67c`
- `0x14007cb94`
- `0x14007cc8c`

## import_xrefs

- `ks!_KsEdit` at `0x14007c7a1`
- `ks!_KsEdit` at `0x14007c843`
- `ks!_KsEdit` at `0x14007c910`
- `ks!_KsEdit` at `0x14007c949`
- `ks!_KsEdit` at `0x14007c7a1`
- `ks!_KsEdit` at `0x14007c843`
- `ks!_KsEdit` at `0x14007c910`
- `ks!_KsEdit` at `0x14007c949`
- `ks!KsAllocateObjectBag` at `0x14007c6ce`
- `ks!KsAllocateObjectBag` at `0x14007c6ce`
- `ks!KsReleaseDevice` at `0x14007ca50`
- `ks!KsReleaseDevice` at `0x14007cb39`
- `ks!KsReleaseDevice` at `0x14007ca50`
- `ks!KsReleaseDevice` at `0x14007cb39`
- `ks!KsAcquireDevice` at `0x14007c6a4`
- `ks!KsAcquireDevice` at `0x14007c6a4`

## pseudocode

```c
__int64 __fastcall A2dpInbandAudioDevice::CreateFilterDescriptor(
        PKSDEVICE *this,
        const struct _GUID *a2,
        bool a3,
        struct _GUID *a4)
{
  KSOBJECT_BAG *v6; // r13
  __int64 v7; // rbx
  int v8; // edx
  NTSTATUS ObjectBag; // esi
  int v10; // r8d
  PDEVICE_OBJECT v11; // r10
  bool v12; // di
  __int64 v13; // rax
  struct _KSFILTER_DESCRIPTOR **v14; // r12
  bool v15; // zf
  const struct _KSFILTER_DESCRIPTOR *v16; // rax
  KSOBJECT_BAG v17; // rcx
  ULONG v18; // r8d
  ULONG v19; // esi
  struct _KSFILTER_DESCRIPTOR *v20; // rdx
  const KSPIN_DESCRIPTOR_EX *PinDescriptors; // rax
  __int64 v22; // rcx
  int v23; // r8d
  PVOID *v24; // rax
  KSOBJECT_BAG v25; // rcx
  int v26; // edx
  int v27; // r8d
  NTSTATUS v28; // r15d
  PDEVICE_OBJECT v29; // r10
  __int64 v31; // rax
  __int16 v32; // [rsp+30h] [rbp-58h]
  __int16 v33; // [rsp+30h] [rbp-58h]
  char v34; // [rsp+40h] [rbp-48h]
  char v35; // [rsp+40h] [rbp-48h]
  char v36; // [rsp+48h] [rbp-40h]
  char v37; // [rsp+48h] [rbp-40h]
  PVOID **v38; // [rsp+90h] [rbp+8h] BYREF
  bool v39; // [rsp+A0h] [rbp+18h]
  struct _GUID *v40; // [rsp+A8h] [rbp+20h]

  v40 = a4;
  v39 = a3;
  KsAcquireDevice(this[1]);
  v6 = (KSOBJECT_BAG *)(this + 2);
  v7 = *(_QWORD *)lambda_7a453431fe2498db3fbb59b6cfe4dbcb_::_lambda_7a453431fe2498db3fbb59b6cfe4dbcb_(&v38, this);
  ObjectBag = KsAllocateObjectBag(this[1], (KSOBJECT_BAG *)this + 2);
  if ( ObjectBag >= 0 )
  {
    v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&AudioSinkServiceClass_UUID.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&AudioSinkServiceClass_UUID.Data1 )
      v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)AudioSinkServiceClass_UUID.Data4;
    v14 = (struct _KSFILTER_DESCRIPTOR **)(this + 3);
    v15 = v13 != 0;
    v16 = &gFilterDescriptor_Src;
    v17 = *v6;
    if ( v15 )
      v16 = &gFilterDescriptor_Snk;
    *v14 = (struct _KSFILTER_DESCRIPTOR *)v16;
    ObjectBag = _KsEdit(v17, (PVOID *)this + 3, 0x68u, 0x68u, 0x50444141u);
    if ( ObjectBag >= 0 )
    {
      v18 = (*v14)->PinDescriptorsCount * (*v14)->PinDescriptorSize;
      ObjectBag = _KsEdit(*v6, (PVOID *)&(*v14)->PinDescriptors, v18, v18, 0x50444141u);
      if ( ObjectBag >= 0 )
      {
        v19 = 0;
        v12 = 1;
        while ( 1 )
        {
          v20 = *v14;
          if ( v19 >= (*v14)->PinDescriptorsCount )
            break;
          PinDescriptors = v20->PinDescriptors;
          v22 = v20->PinDescriptorSize * v19;
          if ( *(KSPIN_COMMUNICATION *)((char *)&PinDescriptors->PinDescriptor.Communication + v22) != KSPIN_COMMUNICATION_BRIDGE )
          {
            v23 = *(ULONG *)((char *)&PinDescriptors->PinDescriptor.DataRangesCount + v22);
            v24 = (PVOID *)((char *)&PinDescriptors->PinDescriptor.DataRanges + v22);
            v25 = *v6;
            v38 = (PVOID **)v24;
            v28 = _KsEdit(v25, v24, 8 * v23, 8 * v23, 0x50444141u);
            if ( v28 < 0 )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (v26 = 16, (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0)
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                v12 = 0;
              }
              LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v37 = (char)this;
                v35 = v28;
                v33 = 17;
LABEL_52:
                LOBYTE(v26) = v12;
                WPP_RECORDER_AND_TRACE_SF_dq(
                  v29->AttachedDevice,
                  v26,
                  v27,
                  v29->DeviceExtension,
                  2,
                  5,
                  v33,
                  (__int64)WPP_24d325fae6053930807bc377bc068cf6_Traceguids,
                  v35,
                  v37);
              }
LABEL_53:
              KsReleaseDevice(*(PKSDEVICE *)(v7 + 8));
              return (unsigned int)v28;
            }
            v28 = _KsEdit(*v6, *v38, 0x58u, 0x58u, 0x50444141u);
            if ( v28 < 0 )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (v26 = 16, (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0)
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                v12 = 0;
              }
              LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v37 = (char)this;
                v35 = v28;
                v33 = 18;
                goto LABEL_52;
              }
              goto LABEL_53;
            }
          }
          ++v19;
        }
        v31 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&AudioSinkServiceClass_UUID.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&AudioSinkServiceClass_UUID.Data1 )
          v31 = *(_QWORD *)a2->Data4 - *(_QWORD *)AudioSinkServiceClass_UUID.Data4;
        if ( v31
          || (A2dpInbandAudioDevice::EditFilterDescriptorTopologyNodesConnectionsForSrc(
                (A2dpInbandAudioDevice *)this,
                v20,
                v39),
              ObjectBag = A2dpInbandAudioDevice::EditFilterDescriptorOutputPinCategoryForSrc(
                            (A2dpInbandAudioDevice *)this,
                            *v14,
                            v40),
              ObjectBag >= 0) )
        {
          ObjectBag = 0;
          goto LABEL_67;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (v8 = 16, (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0)
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v12 = 0;
        }
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !v12 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_67;
        v36 = (char)this;
        v34 = ObjectBag;
        v32 = 19;
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        v8 = 16;
        v12 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !v12 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_67;
        v36 = (char)this;
        v34 = ObjectBag;
        v32 = 16;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      v12 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v8 = 16;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          v12 = 1;
      }
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v12 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_67;
      v36 = (char)this;
      v34 = ObjectBag;
      v32 = 15;
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    v12 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v8 = 16;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        v12 = 1;
    }
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v12 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_67;
    v36 = (char)this;
    v34 = ObjectBag;
    v32 = 14;
  }
  LOBYTE(v8) = v12;
  WPP_RECORDER_AND_TRACE_SF_dq(
    v11->AttachedDevice,
    v8,
    v10,
    v11->DeviceExtension,
    2,
    5,
    v32,
    (__int64)WPP_24d325fae6053930807bc377bc068cf6_Traceguids,
    v34,
    v36);
LABEL_67:
  KsReleaseDevice(*(PKSDEVICE *)(v7 + 8));
  return (unsigned int)ObjectBag;
}

```

## disassembly

```asm
0x14007c67c  mov     [rsp+arg_8], rbx
0x14007c681  mov     [rsp+arg_18], r9
0x14007c686  mov     [rsp+arg_10], r8b
0x14007c68b  push    rbp
0x14007c68c  push    rsi
0x14007c68d  push    rdi
0x14007c68e  push    r12
0x14007c690  push    r13
0x14007c692  push    r14
0x14007c694  push    r15
0x14007c696  sub     rsp, 50h
0x14007c69a  mov     rbp, rcx
0x14007c69d  mov     r14, rdx
0x14007c6a0  mov     rcx, [rcx+8]; Device
0x14007c6a4  call    cs:__imp_KsAcquireDevice
0x14007c6ab  nop     dword ptr [rax+rax+00h]
0x14007c6b0  mov     rdx, rbp
0x14007c6b3  lea     rcx, [rsp+88h+arg_0]
0x14007c6bb  call    _lambda_7a453431fe2498db3fbb59b6cfe4dbcb____lambda_7a453431fe2498db3fbb59b6cfe4dbcb_
0x14007c6c0  mov     rcx, [rbp+8]; Device
0x14007c6c4  lea     r13, [rbp+10h]
0x14007c6c8  mov     rdx, r13; ObjectBag
0x14007c6cb  mov     rbx, [rax]
0x14007c6ce  call    cs:__imp_KsAllocateObjectBag
0x14007c6d5  nop     dword ptr [rax+rax+00h]
0x14007c6da  mov     esi, eax
0x14007c6dc  test    eax, eax
0x14007c6de  jns     short loc_14007C750
0x14007c6e0  mov     r10, cs:WPP_GLOBAL_Control
0x14007c6e7  lea     rcx, WPP_GLOBAL_Control
0x14007c6ee  cmp     r10, rcx
0x14007c6f1  jz      short loc_14007C70C
0x14007c6f3  mov     ecx, [r10+2Ch]
0x14007c6f7  mov     edx, 10h
0x14007c6fc  test    dl, cl
0x14007c6fe  jz      short loc_14007C70C
0x14007c700  cmp     byte ptr [r10+29h], 2
0x14007c705  jb      short loc_14007C70C
0x14007c707  lea     edi, [rdx-0Fh]
0x14007c70a  jmp     short loc_14007C70F
0x14007c70c  xor     dil, dil
0x14007c70f  lea     rax, WPP_RECORDER_INITIALIZED
0x14007c716  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007c71d  setnz   r8b
0x14007c721  test    dil, dil
0x14007c724  jnz     short loc_14007C72F
0x14007c726  test    r8b, r8b
0x14007c729  jz      loc_14007CB35
0x14007c72f  mov     qword ptr [rsp+88h+var_40], rbp
0x14007c734  lea     rax, WPP_24d325fae6053930807bc377bc068cf6_Traceguids
0x14007c73b  mov     dword ptr [rsp+88h+var_48], esi
0x14007c73f  mov     [rsp+88h+var_50], rax
0x14007c744  mov     [rsp+88h+var_58], 0Eh
0x14007c74b  jmp     loc_14007CB14
0x14007c750  mov     rax, [r14]
0x14007c753  sub     rax, qword ptr cs:AudioSinkServiceClass_UUID.Data1
0x14007c75a  jnz     short loc_14007C767
0x14007c75c  mov     rax, [r14+8]
0x14007c760  sub     rax, qword ptr cs:AudioSinkServiceClass_UUID.Data4
0x14007c767  test    rax, rax
0x14007c76a  mov     [rsp+88h+Tag], 50444141h; Tag
0x14007c772  lea     rdx, ?gFilterDescriptor_Snk@@3U_KSFILTER_DESCRIPTOR@@B; _KSFILTER_DESCRIPTOR const gFilterDescriptor_Snk
0x14007c779  mov     r8d, 68h ; 'h'; NewSize
0x14007c77f  setz    cl
0x14007c782  lea     r12, [rbp+18h]
0x14007c786  test    cl, cl
0x14007c788  lea     rax, ?gFilterDescriptor_Src@@3U_KSFILTER_DESCRIPTOR@@B; _KSFILTER_DESCRIPTOR const gFilterDescriptor_Src
0x14007c78f  mov     rcx, [r13+0]; ObjectBag
0x14007c793  mov     r9d, r8d; OldSize
0x14007c796  cmovz   rax, rdx
0x14007c79a  mov     rdx, r12; PointerToPointerToItem
0x14007c79d  mov     [r12], rax
0x14007c7a1  call    cs:__imp__KsEdit
0x14007c7a8  nop     dword ptr [rax+rax+00h]
0x14007c7ad  mov     esi, eax
0x14007c7af  test    eax, eax
0x14007c7b1  jns     short loc_14007C823
0x14007c7b3  mov     r10, cs:WPP_GLOBAL_Control
0x14007c7ba  lea     rcx, WPP_GLOBAL_Control
0x14007c7c1  cmp     r10, rcx
0x14007c7c4  jz      short loc_14007C7DF
0x14007c7c6  mov     ecx, [r10+2Ch]
0x14007c7ca  mov     edx, 10h
0x14007c7cf  test    dl, cl
0x14007c7d1  jz      short loc_14007C7DF
0x14007c7d3  cmp     byte ptr [r10+29h], 2
0x14007c7d8  jb      short loc_14007C7DF
0x14007c7da  lea     edi, [rdx-0Fh]
0x14007c7dd  jmp     short loc_14007C7E2
0x14007c7df  xor     dil, dil
0x14007c7e2  lea     rax, WPP_RECORDER_INITIALIZED
0x14007c7e9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007c7f0  setnz   r8b
0x14007c7f4  test    dil, dil
0x14007c7f7  jnz     short loc_14007C802
0x14007c7f9  test    r8b, r8b
0x14007c7fc  jz      loc_14007CB35
0x14007c802  mov     qword ptr [rsp+88h+var_40], rbp
0x14007c807  lea     rax, WPP_24d325fae6053930807bc377bc068cf6_Traceguids
0x14007c80e  mov     dword ptr [rsp+88h+var_48], esi
0x14007c812  mov     [rsp+88h+var_50], rax
0x14007c817  mov     [rsp+88h+var_58], 0Fh
0x14007c81e  jmp     loc_14007CB14
0x14007c823  mov     rdx, [r12]
0x14007c827  mov     rcx, [r13+0]; ObjectBag
0x14007c82b  mov     [rsp+88h+Tag], 50444141h; Tag
0x14007c833  mov     r8d, [rdx+24h]
0x14007c837  imul    r8d, [rdx+20h]; NewSize
0x14007c83c  add     rdx, 28h ; '('; PointerToPointerToItem
0x14007c840  mov     r9d, r8d; OldSize
0x14007c843  call    cs:__imp__KsEdit
0x14007c84a  nop     dword ptr [rax+rax+00h]
0x14007c84f  mov     esi, eax
0x14007c851  test    eax, eax
0x14007c853  jns     short loc_14007C8C3
0x14007c855  mov     r10, cs:WPP_GLOBAL_Control
0x14007c85c  lea     rcx, WPP_GLOBAL_Control
0x14007c863  mov     edx, 10h
0x14007c868  cmp     r10, rcx
0x14007c86b  jz      short loc_14007C881
0x14007c86d  mov     ecx, [r10+2Ch]
0x14007c871  test    dl, cl
0x14007c873  jz      short loc_14007C881
0x14007c875  cmp     byte ptr [r10+29h], 2
0x14007c87a  jb      short loc_14007C881
0x14007c87c  lea     edi, [rdx-0Fh]
0x14007c87f  jmp     short loc_14007C884
0x14007c881  xor     dil, dil
0x14007c884  lea     rax, WPP_RECORDER_INITIALIZED
0x14007c88b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007c892  setnz   r8b
0x14007c896  test    dil, dil
0x14007c899  jnz     short loc_14007C8A4
0x14007c89b  test    r8b, r8b
0x14007c89e  jz      loc_14007CB35
0x14007c8a4  mov     qword ptr [rsp+88h+var_40], rbp
0x14007c8a9  lea     rax, WPP_24d325fae6053930807bc377bc068cf6_Traceguids
0x14007c8b0  mov     dword ptr [rsp+88h+var_48], esi
0x14007c8b4  mov     [rsp+88h+var_50], rax
0x14007c8b9  mov     [rsp+88h+var_58], dx
0x14007c8be  jmp     loc_14007CB14
0x14007c8c3  xor     esi, esi
0x14007c8c5  lea     edi, [rsi+1]
0x14007c8c8  mov     rdx, [r12]; struct _KSFILTER_DESCRIPTOR *
0x14007c8cc  cmp     esi, [rdx+20h]
0x14007c8cf  jnb     loc_14007CA64
0x14007c8d5  mov     rax, [rdx+28h]
0x14007c8d9  mov     ecx, esi
0x14007c8db  imul    ecx, [rdx+24h]
0x14007c8df  cmp     dword ptr [rcx+rax+44h], 4
0x14007c8e4  jz      short loc_14007C95C
0x14007c8e6  mov     r8d, [rcx+rax+30h]
0x14007c8eb  add     rax, 38h ; '8'
0x14007c8ef  add     rax, rcx
0x14007c8f2  shl     r8d, 3; NewSize
0x14007c8f6  mov     rcx, [r13+0]; ObjectBag
0x14007c8fa  mov     rdx, rax; PointerToPointerToItem
0x14007c8fd  mov     r9d, r8d; OldSize
0x14007c900  mov     [rsp+88h+arg_0], rax
0x14007c908  mov     [rsp+88h+Tag], 50444141h; Tag
0x14007c910  call    cs:__imp__KsEdit
0x14007c917  nop     dword ptr [rax+rax+00h]
0x14007c91c  mov     r15d, eax
0x14007c91f  test    eax, eax
0x14007c921  js      loc_14007C9CC
0x14007c927  mov     rdx, [rsp+88h+arg_0]
0x14007c92f  mov     eax, 58h ; 'X'
0x14007c934  mov     rcx, [r13+0]; ObjectBag
0x14007c938  mov     r9d, eax; OldSize
0x14007c93b  mov     r8d, eax; NewSize
0x14007c93e  mov     [rsp+88h+Tag], 50444141h; Tag
0x14007c946  mov     rdx, [rdx]; PointerToPointerToItem
0x14007c949  call    cs:__imp__KsEdit
0x14007c950  nop     dword ptr [rax+rax+00h]
0x14007c955  mov     r15d, eax
0x14007c958  test    eax, eax
0x14007c95a  js      short loc_14007C963
0x14007c95c  add     esi, edi
0x14007c95e  jmp     loc_14007C8C8
0x14007c963  mov     r10, cs:WPP_GLOBAL_Control
0x14007c96a  lea     rcx, WPP_GLOBAL_Control
0x14007c971  cmp     r10, rcx
0x14007c974  jz      short loc_14007C98A
0x14007c976  mov     eax, [r10+2Ch]
0x14007c97a  mov     edx, 10h
0x14007c97f  test    dl, al
0x14007c981  jz      short loc_14007C98A
0x14007c983  cmp     byte ptr [r10+29h], 2
0x14007c988  jnb     short loc_14007C98D
0x14007c98a  xor     dil, dil
0x14007c98d  lea     rax, WPP_RECORDER_INITIALIZED
0x14007c994  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007c99b  setnz   r8b
0x14007c99f  test    dil, dil
0x14007c9a2  jnz     short loc_14007C9AD
0x14007c9a4  test    r8b, r8b
0x14007c9a7  jz      loc_14007CA4C
0x14007c9ad  mov     qword ptr [rsp+88h+var_40], rbp
0x14007c9b2  lea     rax, WPP_24d325fae6053930807bc377bc068cf6_Traceguids
0x14007c9b9  mov     dword ptr [rsp+88h+var_48], r15d
0x14007c9be  mov     [rsp+88h+var_50], rax
0x14007c9c3  mov     [rsp+88h+var_58], 12h
0x14007c9ca  jmp     short loc_14007CA2F
0x14007c9cc  mov     r10, cs:WPP_GLOBAL_Control
0x14007c9d3  lea     rcx, WPP_GLOBAL_Control
0x14007c9da  cmp     r10, rcx
0x14007c9dd  jz      short loc_14007C9F3
0x14007c9df  mov     eax, [r10+2Ch]
0x14007c9e3  mov     edx, 10h
0x14007c9e8  test    dl, al
0x14007c9ea  jz      short loc_14007C9F3
0x14007c9ec  cmp     byte ptr [r10+29h], 2
0x14007c9f1  jnb     short loc_14007C9F6
0x14007c9f3  xor     dil, dil
0x14007c9f6  lea     rax, WPP_RECORDER_INITIALIZED
0x14007c9fd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007ca04  setnz   r8b
0x14007ca08  test    dil, dil
0x14007ca0b  jnz     short loc_14007CA12
0x14007ca0d  test    r8b, r8b
0x14007ca10  jz      short loc_14007CA4C
0x14007ca12  mov     qword ptr [rsp+88h+var_40], rbp
0x14007ca17  lea     rax, WPP_24d325fae6053930807bc377bc068cf6_Traceguids
0x14007ca1e  mov     dword ptr [rsp+88h+var_48], r15d
0x14007ca23  mov     [rsp+88h+var_50], rax
0x14007ca28  mov     [rsp+88h+var_58], 11h
0x14007ca2f  mov     r9, [r10+40h]
0x14007ca33  mov     dl, dil
0x14007ca36  mov     rcx, [r10+18h]
0x14007ca3a  mov     [rsp+88h+var_60], 5
0x14007ca42  mov     byte ptr [rsp+88h+Tag], 2
0x14007ca47  call    WPP_RECORDER_AND_TRACE_SF_dq
0x14007ca4c  mov     rcx, [rbx+8]; Device
0x14007ca50  call    cs:__imp_KsReleaseDevice
0x14007ca57  nop     dword ptr [rax+rax+00h]
0x14007ca5c  mov     eax, r15d
0x14007ca5f  jmp     loc_14007CB47
0x14007ca64  mov     rax, [r14]
0x14007ca67  sub     rax, qword ptr cs:AudioSinkServiceClass_UUID.Data1
0x14007ca6e  jnz     short loc_14007CA7B
0x14007ca70  mov     rax, [r14+8]
0x14007ca74  sub     rax, qword ptr cs:AudioSinkServiceClass_UUID.Data4
0x14007ca7b  test    rax, rax
0x14007ca7e  jnz     loc_14007CB33
0x14007ca84  mov     r8b, [rsp+88h+arg_10]; bool
0x14007ca8c  mov     rcx, rbp; this
0x14007ca8f  call    ?EditFilterDescriptorTopologyNodesConnectionsForSrc@A2dpInbandAudioDevice@@AEAAXPEAU_KSFILTER_DESCRIPTOR@@_N@Z; A2dpInbandAudioDevice::EditFilterDescriptorTopologyNodesConnectionsForSrc(_KSFILTER_DESCRIPTOR *,bool)
0x14007ca94  mov     r8, [rsp+88h+arg_18]; struct _GUID *
0x14007ca9c  mov     rcx, rbp; this
0x14007ca9f  mov     rdx, [r12]; struct _KSFILTER_DESCRIPTOR *
0x14007caa3  call    ?EditFilterDescriptorOutputPinCategoryForSrc@A2dpInbandAudioDevice@@AEAAJPEAU_KSFILTER_DESCRIPTOR@@PEBU_GUID@@@Z; A2dpInbandAudioDevice::EditFilterDescriptorOutputPinCategoryForSrc(_KSFILTER_DESCRIPTOR *,_GUID const *)
0x14007caa8  mov     esi, eax
0x14007caaa  test    eax, eax
0x14007caac  jns     loc_14007CB33
0x14007cab2  mov     r10, cs:WPP_GLOBAL_Control
0x14007cab9  lea     rcx, WPP_GLOBAL_Control
0x14007cac0  cmp     r10, rcx
0x14007cac3  jz      short loc_14007CAD9
0x14007cac5  mov     ecx, [r10+2Ch]
0x14007cac9  mov     edx, 10h
0x14007cace  test    dl, cl
0x14007cad0  jz      short loc_14007CAD9
0x14007cad2  cmp     byte ptr [r10+29h], 2
0x14007cad7  jnb     short loc_14007CADC
0x14007cad9  xor     dil, dil
0x14007cadc  lea     rax, WPP_RECORDER_INITIALIZED
0x14007cae3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007caea  setnz   r8b
0x14007caee  test    dil, dil
0x14007caf1  jnz     short loc_14007CAF8
0x14007caf3  test    r8b, r8b
0x14007caf6  jz      short loc_14007CB35
0x14007caf8  mov     qword ptr [rsp+88h+var_40], rbp
0x14007cafd  lea     rax, WPP_24d325fae6053930807bc377bc068cf6_Traceguids
0x14007cb04  mov     dword ptr [rsp+88h+var_48], esi
0x14007cb08  mov     [rsp+88h+var_50], rax
0x14007cb0d  mov     [rsp+88h+var_58], 13h
0x14007cb14  mov     r9, [r10+40h]
0x14007cb18  mov     dl, dil
0x14007cb1b  mov     rcx, [r10+18h]
0x14007cb1f  mov     [rsp+88h+var_60], 5
0x14007cb27  mov     byte ptr [rsp+88h+Tag], 2
0x14007cb2c  call    WPP_RECORDER_AND_TRACE_SF_dq
0x14007cb31  jmp     short loc_14007CB35
0x14007cb33  xor     esi, esi
0x14007cb35  mov     rcx, [rbx+8]; Device
0x14007cb39  call    cs:__imp_KsReleaseDevice
0x14007cb40  nop     dword ptr [rax+rax+00h]
0x14007cb45  mov     eax, esi
0x14007cb47  mov     rbx, [rsp+88h+arg_8]
0x14007cb4f  add     rsp, 50h
0x14007cb53  pop     r15
0x14007cb55  pop     r14
0x14007cb57  pop     r13
0x14007cb59  pop     r12
0x14007cb5b  pop     rdi
0x14007cb5c  pop     rsi
0x14007cb5d  pop     rbp
0x14007cb5e  retn
```
