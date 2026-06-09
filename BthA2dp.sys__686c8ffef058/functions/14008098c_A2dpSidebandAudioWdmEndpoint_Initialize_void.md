# A2dpSidebandAudioWdmEndpoint::Initialize(void)

- ea: `0x14008098c`
- end: `0x140080ebc`
- name: `?Initialize@A2dpSidebandAudioWdmEndpoint@@QEAAJXZ`
- size: `1328`
- prototype: `__int64 __fastcall(A2dpSidebandAudioWdmEndpoint *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x14007d8b0`

## callees

- `0x14000e690`
- `0x14001cc7c`
- `0x14001e0dc`
- `0x14001f80c`
- `0x1400205f4`
- `0x14002b8e0`
- `0x14002bf48`
- `0x140036b48`
- `0x1400374f4`
- `0x140037648`
- `0x140037778`
- `0x1400379f4`
- `0x140037ac0`
- `0x14003d2e8`
- `0x14005ce00`
- `0x14008098c`

## import_xrefs

- `ntoskrnl!IoGetDevicePropertyData` at `0x140080b32`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140080b32`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140080d0a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140080d0a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140080a83`
- `ntoskrnl!RtlInitUnicodeString` at `0x140080a83`

## pseudocode

```c
__int64 __fastcall A2dpSidebandAudioWdmEndpoint::Initialize(A2dpSidebandAudioWdmEndpoint *this, __int16 a2)
{
  __int64 v2; // r8
  bool v4; // cl
  NTSTATUS DevicePropertyData; // ebx
  __int64 v6; // r8
  const unsigned __int16 *AudioControllerInterfacePath; // rax
  __int64 v8; // rdx
  __int16 v9; // bx
  __int64 v10; // rdx
  __int64 v11; // rax
  _DWORD *v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  PDEVICE_OBJECT v18; // r10
  bool v19; // cl
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int16 RequiredSize; // [rsp+30h] [rbp-50h]
  char v25; // [rsp+40h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  void *Src; // [rsp+60h] [rbp-20h] BYREF
  __int64 v28; // [rsp+68h] [rbp-18h]
  ULONG Type; // [rsp+A0h] [rbp+20h] BYREF
  ULONG v30; // [rsp+A8h] [rbp+28h] BYREF
  char v31; // [rsp+B0h] [rbp+30h] BYREF

  v2 = *((_QWORD *)this + 79);
  if ( v2 )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&Src);
    AudioControllerInterfacePath = A2dpRole::GetAudioControllerInterfacePath(*(A2dpRole **)(v6 + 8));
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
      &Src,
      AudioControllerInterfacePath);
    v8 = *((_QWORD *)this + 79);
    DestinationString = 0;
    v9 = 2 * (((v28 - (__int64)Src) >> 1) + 25);
    RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v8 + 3496));
    v10 = (unsigned __int16)(DestinationString.MaximumLength + v9 + 96);
    *((_WORD *)this + 320) = v10;
    v11 = utl::make_unique<unsigned char [0],0>(&v31, v10);
    utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::operator=((char *)this + 648, v11);
    utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(&v31);
    v12 = (_DWORD *)*((_QWORD *)this + 81);
    v13 = *((unsigned __int16 *)this + 320);
    *((_QWORD *)this + 82) = v12;
    *v12 = v13;
    v14 = *((_QWORD *)this + 79);
    v15 = *((_QWORD *)this + 82);
    v30 = 0;
    Type = 0;
    DevicePropertyData = IoGetDevicePropertyData(
                           *(PDEVICE_OBJECT *)(*(_QWORD *)(v14 + 368) + 32LL),
                           &DEVPKEY_Device_ContainerId,
                           0,
                           0,
                           0x10u,
                           (PVOID)(v15 + 4),
                           &v30,
                           &Type);
    if ( DevicePropertyData >= 0 )
    {
      if ( Type == 13 )
      {
        *(_OWORD *)(*((_QWORD *)this + 82) + 20LL) = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 79) + 8LL)
                                                                          + 176LL);
        *(_DWORD *)(*((_QWORD *)this + 82) + 36LL) = 2
                                                   - (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 79) + 8LL) + 89LL) != 0);
        *(_DWORD *)(*((_QWORD *)this + 82) + 40LL) = A2dpRole::IsVolumeSupported(*(A2dpRole **)(*((_QWORD *)this + 79)
                                                                                              + 8LL));
        *(_DWORD *)(*((_QWORD *)this + 82) + 44LL) = A2dpRole::IsVolumeSupported(*(A2dpRole **)(*((_QWORD *)this + 79)
                                                                                              + 8LL));
        *(_DWORD *)(*((_QWORD *)this + 82) + 52LL) = 0;
        *(_DWORD *)(*((_QWORD *)this + 82) + 48LL) = 0;
        *(_QWORD *)(*((_QWORD *)this + 82) + 64LL) = *((_QWORD *)this + 82) + 96LL;
        *(_WORD *)(*((_QWORD *)this + 82) + 56LL) = 0;
        *(_WORD *)(*((_QWORD *)this + 82) + 58LL) = DestinationString.MaximumLength;
        RtlCopyUnicodeString((PUNICODE_STRING)(*((_QWORD *)this + 82) + 56LL), &DestinationString);
        *(_DWORD *)(*((_QWORD *)this + 82) + 72LL) = AVFilter::GetVolumePropertyDescriptionSize();
        *(_DWORD *)(*((_QWORD *)this + 82) + 80LL) = AVFilter::GetVolumePropertyDescriptionSize();
        *(_DWORD *)(*((_QWORD *)this + 82) + 76LL) = 0;
        *(_DWORD *)(*((_QWORD *)this + 82) + 84LL) = 1;
        *(_QWORD *)(*((_QWORD *)this + 82) + 88LL) = *(_QWORD *)(*((_QWORD *)this + 82) + 64LL)
                                                   + *(unsigned __int16 *)(*((_QWORD *)this + 82) + 58LL);
        v20 = *(_QWORD *)(*((_QWORD *)this + 82) + 88LL);
        *(_OWORD *)v20 = DEVPKEY_KsAudio_Controller_DeviceInterface_Path;
        *(_DWORD *)(v20 + 16) = 3;
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 82) + 88LL) + 24LL) = 0;
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 82) + 88LL) + 20LL) = 0;
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 82) + 88LL) + 32LL) = 18;
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 82) + 88LL) + 36LL) = 2 * ((v28 - (__int64)Src) >> 1) + 2;
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 82) + 88LL) + 40LL) = *(_QWORD *)(*((_QWORD *)this + 82) + 88LL)
                                                                       + 48LL;
        memmove(*(void **)(*(_QWORD *)(*((_QWORD *)this + 82) + 88LL) + 40LL), Src, 2 * ((v28 - (__int64)Src) >> 1) + 2);
        v21 = utl::make_unique<SiopStoreMap,,0>(&v31);
        utl::unique_ptr<SiopStore,utl::default_delete<SiopStore>>::operator=<SiopStoreMap,utl::default_delete<SiopStoreMap>,0>(
          (char *)this + 24,
          v21);
        utl::unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>>::~unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>>(&v31);
        v22 = utl::make_unique<SiopStoreMap,,0>(&v31);
        utl::unique_ptr<SiopStore,utl::default_delete<SiopStore>>::operator=<SiopStoreMap,utl::default_delete<SiopStoreMap>,0>(
          (char *)this + 664,
          v22);
        utl::unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>>::~unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>>(&v31);
        IoQueue_InitEx((char *)this + 808, (char *)this + 824, A2dpSidebandAudioWdmEndpoint::HandleSiopUpdateCancel);
        IoQueue_InitEx((char *)this + 888, (char *)this + 904, A2dpSidebandAudioWdmEndpoint::HandleSiopUpdateCancel);
        IoQueue_InitEx((char *)this + 968, (char *)this + 984, A2dpSidebandAudioWdmEndpoint::HandleSiopUpdateCancel);
        DevicePropertyData = 0;
        goto LABEL_30;
      }
      v18 = WPP_GLOBAL_Control;
      v19 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      DevicePropertyData = -1073741436;
      LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v19 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_30;
      v25 = -124;
      RequiredSize = 16;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      v19 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v19 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_30;
      v25 = DevicePropertyData;
      RequiredSize = 15;
    }
    LOBYTE(v16) = v19;
    WPP_RECORDER_AND_TRACE_SF_d(
      v18->AttachedDevice,
      (_WORD)v16,
      v17,
      v18->DeviceExtension,
      2,
      18,
      RequiredSize,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      v25);
LABEL_30:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(
      &Src,
      v16,
      v17);
    return (unsigned int)DevicePropertyData;
  }
  v4 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  DevicePropertyData = -1073741436;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = v4;
    LOBYTE(v2) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      v2,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      18,
      14,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      132);
  }
  return (unsigned int)DevicePropertyData;
}

```

## disassembly

```asm
0x14008098c  mov     [rsp-18h+arg_18], rbx
0x140080991  push    rbp
0x140080992  push    rdi
0x140080993  push    r14
0x140080995  mov     rbp, rsp
0x140080998  sub     rsp, 80h
0x14008099f  mov     r8, [rcx+278h]
0x1400809a6  mov     rdi, rcx
0x1400809a9  test    r8, r8
0x1400809ac  jnz     loc_140080A3A
0x1400809b2  mov     r10, cs:WPP_GLOBAL_Control
0x1400809b9  lea     rax, WPP_GLOBAL_Control
0x1400809c0  cmp     r10, rax
0x1400809c3  jz      short loc_1400809DC
0x1400809c5  test    dword ptr [r10+2Ch], 20000h
0x1400809cd  jz      short loc_1400809DC
0x1400809cf  cmp     byte ptr [r10+29h], 2
0x1400809d4  jb      short loc_1400809DC
0x1400809d6  lea     ecx, [r8+1]
0x1400809da  jmp     short loc_1400809DE
0x1400809dc  xor     cl, cl
0x1400809de  lea     rax, WPP_RECORDER_INITIALIZED
0x1400809e5  mov     ebx, 0C0000184h
0x1400809ea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400809f1  setnz   r8b
0x1400809f5  test    cl, cl
0x1400809f7  jnz     short loc_140080A02
0x1400809f9  test    r8b, r8b
0x1400809fc  jz      loc_140080EA5
0x140080a02  mov     r9, [r10+40h]
0x140080a06  lea     rax, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140080a0d  mov     dword ptr [rsp+80h+var_40], ebx
0x140080a11  mov     dl, cl
0x140080a13  mov     rcx, [r10+18h]
0x140080a17  mov     [rsp+80h+Type], rax
0x140080a1c  mov     word ptr [rsp+80h+RequiredSize], 0Eh
0x140080a23  mov     dword ptr [rsp+80h+Data], 12h
0x140080a2b  mov     byte ptr [rsp+80h+Size], 2
0x140080a30  call    WPP_RECORDER_AND_TRACE_SF_d
0x140080a35  jmp     loc_140080EA5
0x140080a3a  lea     rcx, [rbp+Src]
0x140080a3e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x140080a43  mov     rcx, [r8+8]; this
0x140080a47  call    ?GetAudioControllerInterfacePath@A2dpRole@@QEBAPEBGXZ; A2dpRole::GetAudioControllerInterfacePath(void)
0x140080a4c  mov     rdx, rax
0x140080a4f  lea     rcx, [rbp+Src]
0x140080a53  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x140080a58  mov     rbx, [rbp+var_18]
0x140080a5c  lea     rcx, [rbp+DestinationString]; DestinationString
0x140080a60  sub     rbx, [rbp+Src]
0x140080a64  xorps   xmm0, xmm0
0x140080a67  mov     rdx, [rdi+278h]
0x140080a6e  sar     rbx, 1
0x140080a71  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140080a75  add     bx, 19h
0x140080a79  mov     rdx, [rdx+0DA8h]; SourceString
0x140080a80  add     bx, bx
0x140080a83  call    cs:__imp_RtlInitUnicodeString
0x140080a8a  nop     dword ptr [rax+rax+00h]
0x140080a8f  add     bx, 60h ; '`'
0x140080a93  lea     rcx, [rbp+arg_10]
0x140080a97  add     bx, [rbp+DestinationString.MaximumLength]
0x140080a9b  movzx   edx, bx
0x140080a9e  lea     rbx, [rdi+288h]
0x140080aa5  mov     [rdi+280h], dx
0x140080aac  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x140080ab1  mov     rdx, rax
0x140080ab4  mov     rcx, rbx
0x140080ab7  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::operator=(utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &&)
0x140080abc  lea     rcx, [rbp+arg_10]
0x140080ac0  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x140080ac5  mov     rcx, [rbx]
0x140080ac8  mov     r14d, 10h
0x140080ace  movzx   eax, word ptr [rdi+280h]
0x140080ad5  xor     r9d, r9d; Flags
0x140080ad8  mov     [rdi+290h], rcx
0x140080adf  xor     r8d, r8d; Lcid
0x140080ae2  mov     [rcx], eax
0x140080ae4  mov     rax, [rdi+278h]
0x140080aeb  mov     rdx, [rdi+290h]
0x140080af2  mov     [rbp+arg_8], 0
0x140080af9  add     rdx, 4
0x140080afd  mov     [rbp+arg_0], 0
0x140080b04  mov     rcx, [rax+170h]
0x140080b0b  lea     rax, [rbp+arg_0]
0x140080b0f  mov     [rsp+80h+Type], rax; Type
0x140080b14  lea     rax, [rbp+arg_8]
0x140080b18  mov     [rsp+80h+RequiredSize], rax; RequiredSize
0x140080b1d  mov     [rsp+80h+Data], rdx; Data
0x140080b22  lea     rdx, DEVPKEY_Device_ContainerId; PropertyKey
0x140080b29  mov     rcx, [rcx+20h]; Pdo
0x140080b2d  mov     [rsp+80h+Size], r14d; Size
0x140080b32  call    cs:__imp_IoGetDevicePropertyData
0x140080b39  nop     dword ptr [rax+rax+00h]
0x140080b3e  mov     ebx, eax
0x140080b40  test    eax, eax
0x140080b42  jns     short loc_140080BA8
0x140080b44  mov     r10, cs:WPP_GLOBAL_Control
0x140080b4b  lea     rax, WPP_GLOBAL_Control
0x140080b52  cmp     r10, rax
0x140080b55  jz      short loc_140080B6E
0x140080b57  test    dword ptr [r10+2Ch], 20000h
0x140080b5f  jz      short loc_140080B6E
0x140080b61  cmp     byte ptr [r10+29h], 2
0x140080b66  jb      short loc_140080B6E
0x140080b68  lea     ecx, [r14-0Fh]
0x140080b6c  jmp     short loc_140080B70
0x140080b6e  xor     cl, cl
0x140080b70  lea     rax, WPP_RECORDER_INITIALIZED
0x140080b77  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140080b7e  setnz   r8b
0x140080b82  test    cl, cl
0x140080b84  jnz     short loc_140080B8F
0x140080b86  test    r8b, r8b
0x140080b89  jz      loc_140080E9C
0x140080b8f  mov     dword ptr [rsp+80h+var_40], ebx
0x140080b93  lea     rax, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140080b9a  mov     [rsp+80h+Type], rax
0x140080b9f  mov     word ptr [rsp+80h+RequiredSize], 0Fh
0x140080ba6  jmp     short loc_140080C19
0x140080ba8  cmp     [rbp+arg_0], 0Dh
0x140080bac  jz      loc_140080C3A
0x140080bb2  mov     r10, cs:WPP_GLOBAL_Control
0x140080bb9  lea     rax, WPP_GLOBAL_Control
0x140080bc0  cmp     r10, rax
0x140080bc3  jz      short loc_140080BDD
0x140080bc5  test    dword ptr [r10+2Ch], 20000h
0x140080bcd  jz      short loc_140080BDD
0x140080bcf  cmp     byte ptr [r10+29h], 2
0x140080bd4  jb      short loc_140080BDD
0x140080bd6  mov     ecx, 1
0x140080bdb  jmp     short loc_140080BDF
0x140080bdd  xor     cl, cl
0x140080bdf  lea     rax, WPP_RECORDER_INITIALIZED
0x140080be6  mov     ebx, 0C0000184h
0x140080beb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140080bf2  setnz   r8b
0x140080bf6  test    cl, cl
0x140080bf8  jnz     short loc_140080C03
0x140080bfa  test    r8b, r8b
0x140080bfd  jz      loc_140080E9C
0x140080c03  mov     dword ptr [rsp+80h+var_40], ebx
0x140080c07  lea     rax, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140080c0e  mov     [rsp+80h+Type], rax
0x140080c13  mov     word ptr [rsp+80h+RequiredSize], r14w
0x140080c19  mov     r9, [r10+40h]
0x140080c1d  mov     dl, cl
0x140080c1f  mov     rcx, [r10+18h]
0x140080c23  mov     dword ptr [rsp+80h+Data], 12h
0x140080c2b  mov     byte ptr [rsp+80h+Size], 2
0x140080c30  call    WPP_RECORDER_AND_TRACE_SF_d
0x140080c35  jmp     loc_140080E9C
0x140080c3a  mov     rax, [rdi+278h]
0x140080c41  mov     rcx, [rax+8]
0x140080c45  mov     rax, [rcx+0B0h]
0x140080c4c  movups  xmm0, xmmword ptr [rax]
0x140080c4f  mov     rax, [rdi+290h]
0x140080c56  movdqu  xmmword ptr [rax+14h], xmm0
0x140080c5b  mov     rax, [rdi+278h]
0x140080c62  mov     rcx, [rax+8]
0x140080c66  mov     al, [rcx+59h]
0x140080c69  neg     al
0x140080c6b  mov     rax, [rdi+290h]
0x140080c72  sbb     ecx, ecx
0x140080c74  add     ecx, 2
0x140080c77  mov     [rax+24h], ecx
0x140080c7a  mov     rcx, [rdi+278h]
0x140080c81  mov     rcx, [rcx+8]; this
0x140080c85  call    ?IsVolumeSupported@A2dpRole@@QEBA_NXZ; A2dpRole::IsVolumeSupported(void)
0x140080c8a  movzx   ecx, al
0x140080c8d  mov     rax, [rdi+290h]
0x140080c94  mov     [rax+28h], ecx
0x140080c97  mov     rcx, [rdi+278h]
0x140080c9e  mov     rcx, [rcx+8]; this
0x140080ca2  call    ?IsVolumeSupported@A2dpRole@@QEBA_NXZ; A2dpRole::IsVolumeSupported(void)
0x140080ca7  movzx   ecx, al
0x140080caa  lea     rdx, [rbp+DestinationString]; SourceString
0x140080cae  mov     rax, [rdi+290h]
0x140080cb5  mov     [rax+2Ch], ecx
0x140080cb8  mov     rax, [rdi+290h]
0x140080cbf  mov     dword ptr [rax+34h], 0
0x140080cc6  mov     rax, [rdi+290h]
0x140080ccd  mov     dword ptr [rax+30h], 0
0x140080cd4  mov     rcx, [rdi+290h]
0x140080cdb  lea     rax, [rcx+60h]
0x140080cdf  mov     [rcx+40h], rax
0x140080ce3  xor     eax, eax
0x140080ce5  mov     rcx, [rdi+290h]
0x140080cec  mov     [rcx+38h], ax
0x140080cf0  mov     rcx, [rdi+290h]
0x140080cf7  movzx   eax, [rbp+DestinationString.MaximumLength]
0x140080cfb  mov     [rcx+3Ah], ax
0x140080cff  mov     rcx, [rdi+290h]
0x140080d06  add     rcx, 38h ; '8'; DestinationString
0x140080d0a  call    cs:__imp_RtlCopyUnicodeString
0x140080d11  nop     dword ptr [rax+rax+00h]
0x140080d16  call    ?GetVolumePropertyDescriptionSize@AVFilter@@SAGXZ; AVFilter::GetVolumePropertyDescriptionSize(void)
0x140080d1b  movzx   ecx, ax
0x140080d1e  mov     rax, [rdi+290h]
0x140080d25  mov     [rax+48h], ecx
0x140080d28  call    ?GetVolumePropertyDescriptionSize@AVFilter@@SAGXZ; AVFilter::GetVolumePropertyDescriptionSize(void)
0x140080d2d  movzx   ecx, ax
0x140080d30  mov     rax, [rdi+290h]
0x140080d37  mov     [rax+50h], ecx
0x140080d3a  mov     rax, [rdi+290h]
0x140080d41  mov     dword ptr [rax+4Ch], 0
0x140080d48  mov     rax, [rdi+290h]
0x140080d4f  mov     dword ptr [rax+54h], 1
0x140080d56  mov     rcx, [rdi+290h]
0x140080d5d  movzx   eax, word ptr [rcx+3Ah]
0x140080d61  add     rax, [rcx+40h]
0x140080d65  mov     [rcx+58h], rax
0x140080d69  mov     rax, [rdi+290h]
0x140080d70  movups  xmm0, cs:DEVPKEY_KsAudio_Controller_DeviceInterface_Path
0x140080d77  mov     rcx, [rax+58h]
0x140080d7b  movups  xmmword ptr [rcx], xmm0
0x140080d7e  mov     eax, cs:dword_140066970
0x140080d84  mov     [rcx+10h], eax
0x140080d87  mov     rax, [rdi+290h]
0x140080d8e  mov     rcx, [rax+58h]
0x140080d92  mov     qword ptr [rcx+18h], 0
0x140080d9a  mov     rax, [rdi+290h]
0x140080da1  mov     rcx, [rax+58h]
0x140080da5  mov     dword ptr [rcx+14h], 0
0x140080dac  mov     rax, [rdi+290h]
0x140080db3  mov     rcx, [rax+58h]
0x140080db7  mov     dword ptr [rcx+20h], 12h
0x140080dbe  mov     rdx, [rbp+var_18]
0x140080dc2  sub     rdx, [rbp+Src]
0x140080dc6  mov     rax, [rdi+290h]
0x140080dcd  sar     rdx, 1
0x140080dd0  mov     rcx, [rax+58h]
0x140080dd4  lea     edx, ds:2[rdx*2]
0x140080ddb  mov     [rcx+24h], edx
0x140080dde  mov     rax, [rdi+290h]
0x140080de5  mov     rcx, [rax+58h]
0x140080de9  lea     rax, [rcx+30h]
0x140080ded  mov     [rcx+28h], rax
0x140080df1  mov     rax, [rdi+290h]
0x140080df8  mov     r8, [rbp+var_18]
0x140080dfc  mov     rdx, [rbp+Src]; Src
0x140080e00  sub     r8, rdx
0x140080e03  mov     rcx, [rax+58h]
0x140080e07  sar     r8, 1
0x140080e0a  mov     rcx, [rcx+28h]; void *
0x140080e0e  lea     r8, ds:2[r8*2]; Size
0x140080e16  call    memmove
0x140080e1b  lea     rcx, [rbp+arg_10]
0x140080e1f  call    ??$make_unique@VSiopStoreMap@@$$V$0A@@utl@@YA?AV?$unique_ptr@VSiopStoreMap@@U?$default_delete@VSiopStoreMap@@@utl@@@0@XZ; utl::make_unique<SiopStoreMap,,0>(void)
0x140080e24  mov     rdx, rax
0x140080e27  lea     rcx, [rdi+18h]
0x140080e2b  call    ??$?4VSiopStoreMap@@U?$default_delete@VSiopStoreMap@@@utl@@$0A@@?$unique_ptr@VSiopStore@@U?$default_delete@VSiopStore@@@utl@@@utl@@QEAAAEAV01@$$QEAV?$unique_ptr@VSiopStoreMap@@U?$default_delete@VSiopStoreMap@@@utl@@@1@@Z; utl::unique_ptr<SiopStore,utl::default_delete<SiopStore>>::operator=<SiopStoreMap,utl::default_delete<SiopStoreMap>,0>(utl::unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>> &&)
0x140080e30  lea     rcx, [rbp+arg_10]
0x140080e34  call    ??1?$unique_ptr@VSiopStoreMap@@U?$default_delete@VSiopStoreMap@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>>::~unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>>(void)
0x140080e39  lea     rcx, [rbp+arg_10]
0x140080e3d  call    ??$make_unique@VSiopStoreMap@@$$V$0A@@utl@@YA?AV?$unique_ptr@VSiopStoreMap@@U?$default_delete@VSiopStoreMap@@@utl@@@0@XZ; utl::make_unique<SiopStoreMap,,0>(void)
0x140080e42  mov     rdx, rax
0x140080e45  lea     rcx, [rdi+298h]
0x140080e4c  call    ??$?4VSiopStoreMap@@U?$default_delete@VSiopStoreMap@@@utl@@$0A@@?$unique_ptr@VSiopStore@@U?$default_delete@VSiopStore@@@utl@@@utl@@QEAAAEAV01@$$QEAV?$unique_ptr@VSiopStoreMap@@U?$default_delete@VSiopStoreMap@@@utl@@@1@@Z; utl::unique_ptr<SiopStore,utl::default_delete<SiopStore>>::operator=<SiopStoreMap,utl::default_delete<SiopStoreMap>,0>(utl::unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>> &&)
0x140080e51  lea     rcx, [rbp+arg_10]
0x140080e55  call    ??1?$unique_ptr@VSiopStoreMap@@U?$default_delete@VSiopStoreMap@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>>::~unique_ptr<SiopStoreMap,utl::default_delete<SiopStoreMap>>(void)
0x140080e5a  lea     rcx, [rdi+328h]
0x140080e61  lea     rbx, ?HandleSiopUpdateCancel@A2dpSidebandAudioWdmEndpoint@@CAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; A2dpSidebandAudioWdmEndpoint::HandleSiopUpdateCancel(_DEVICE_OBJECT *,_IRP *)
0x140080e68  lea     rdx, [rcx+10h]
0x140080e6c  mov     r8, rbx
0x140080e6f  call    IoQueue_InitEx
0x140080e74  lea     rcx, [rdi+378h]
0x140080e7b  mov     r8, rbx
0x140080e7e  lea     rdx, [rcx+10h]
0x140080e82  call    IoQueue_InitEx
0x140080e87  lea     rcx, [rdi+3C8h]
0x140080e8e  mov     r8, rbx
0x140080e91  lea     rdx, [rcx+10h]
0x140080e95  call    IoQueue_InitEx
0x140080e9a  xor     ebx, ebx
0x140080e9c  lea     rcx, [rbp+Src]
0x140080ea0  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x140080ea5  mov     eax, ebx
0x140080ea7  mov     rbx, [rsp+80h+arg_18]
0x140080eaf  add     rsp, 80h
0x140080eb6  pop     r14
0x140080eb8  pop     rdi
0x140080eb9  pop     rbp
0x140080eba  retn
```
