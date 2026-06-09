# AVFilter::CreateFilterFactory(_KSDEVICE *,_KSFILTER_DESCRIPTOR * const,ushort const *,A2dpRole *,_KSFILTERFACTORY * *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x14008b6b0`
- end: `0x14008b9b3`
- name: `?CreateFilterFactory@AVFilter@@SAJPEAU_KSDEVICE@@QEAU_KSFILTER_DESCRIPTOR@@PEBGPEAVA2dpRole@@PEAPEAU_KSFILTERFACTORY@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `771`
- prototype: `__int64 __usercall@<rax>(PKSDEVICE Device@<rcx>, KSFILTER_DESCRIPTOR *Descriptor@<rdx>, PWSTR RefString@<r8>, PKSFILTERFACTORY *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x14007ba50`
- `0x14007cdb0`

## callees

- `0x14000e690`
- `0x14000f570`
- `0x14001e0dc`
- `0x14003479c`
- `0x14003dec8`
- `0x14008b6b0`

## import_xrefs

- `ks!KsFilterFactoryGetSymbolicLink` at `0x14008b895`
- `ks!KsFilterFactoryGetSymbolicLink` at `0x14008b895`
- `ks!KsFilterFactoryUpdateCacheData` at `0x14008b803`
- `ks!KsFilterFactoryUpdateCacheData` at `0x14008b803`
- `ks!KsCreateFilterFactory` at `0x14008b778`
- `ks!KsCreateFilterFactory` at `0x14008b778`
- `ks!KsReleaseDevice` at `0x14008b995`
- `ks!KsReleaseDevice` at `0x14008b995`
- `ks!KsAcquireDevice` at `0x14008b730`
- `ks!KsAcquireDevice` at `0x14008b730`

## pseudocode

```c
__int64 __fastcall AVFilter::CreateFilterFactory(
        PKSDEVICE Device,
        KSFILTER_DESCRIPTOR *Descriptor,
        PWSTR RefString,
        void *a4,
        PKSFILTERFACTORY *FilterFactory,
        __int64 a6)
{
  WCHAR *v7; // rdi
  const KSFILTER_DESCRIPTOR *v8; // rbp
  char v10; // bl
  int IsEnabledDeviceUsageNoInline; // eax
  struct _DEVICE_OBJECT *FunctionalDeviceObject; // rcx
  NTSTATUS v13; // eax
  int v14; // edx
  int v15; // r8d
  NTSTATUS updated; // edi
  int v17; // edx
  int v18; // r8d
  PUNICODE_STRING SymbolicLink; // rax
  int v20; // edx
  int v21; // r8d
  char v22; // al

  v7 = RefString;
  v8 = Descriptor;
  v10 = 1;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || (LOBYTE(Descriptor) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
  {
    LOBYTE(Descriptor) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (LOBYTE(RefString) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(RefString) = 0;
  }
  if ( (_BYTE)Descriptor || (_BYTE)RefString )
    WPP_RECORDER_AND_TRACE_SF_S(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)Descriptor,
      (_DWORD)RefString,
      WPP_GLOBAL_Control->DeviceExtension);
  KsAcquireDevice(Device);
  IsEnabledDeviceUsageNoInline = Feature_53100197__private_IsEnabledDeviceUsageNoInline();
  FunctionalDeviceObject = Device->FunctionalDeviceObject;
  if ( IsEnabledDeviceUsageNoInline )
    v13 = KsCreateFilterFactory(FunctionalDeviceObject, v8, v7, 0, 0, 0, 0, FilterFactory);
  else
    v13 = KsCreateFilterFactory(FunctionalDeviceObject, v8, v7, 0, 8u, 0, 0, FilterFactory);
  updated = v13;
  if ( v13 >= 0 )
  {
    (*FilterFactory)->Context = a4;
    updated = KsFilterFactoryUpdateCacheData(*FilterFactory, 0);
    if ( updated < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || (LOBYTE(v17) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      {
        LOBYTE(v17) = 0;
      }
      if ( (_BYTE)v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v17,
          v18,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          5,
          40,
          (__int64)WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids,
          updated);
      }
    }
    SymbolicLink = KsFilterFactoryGetSymbolicLink(*FilterFactory);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             a6,
                             SymbolicLink->Buffer) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || (LOBYTE(v20) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      {
        LOBYTE(v20) = 0;
      }
      if ( (_BYTE)v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v20,
          v21,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          5,
          41,
          (__int64)WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids);
      }
      updated = -1073741670;
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || (v22 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      v22 = 0;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (LOBYTE(v20) = 1, !v22) )
      LOBYTE(v20) = 0;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      v10 = 0;
    if ( (_BYTE)v20 || v10 )
    {
      LOBYTE(v21) = v10;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v20,
        v21,
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        5,
        42,
        (__int64)WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids,
        updated);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v10 = 0;
    }
    if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = v10;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v14,
        v15,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        39,
        (__int64)WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids,
        v13);
    }
  }
  KsReleaseDevice(Device);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14008b6b0  push    rbx
0x14008b6b2  push    rbp
0x14008b6b3  push    rsi
0x14008b6b4  push    rdi
0x14008b6b5  push    r12
0x14008b6b7  push    r14
0x14008b6b9  push    r15
0x14008b6bb  sub     rsp, 50h
0x14008b6bf  mov     r14, r9
0x14008b6c2  mov     rdi, r8
0x14008b6c5  mov     rbp, rdx
0x14008b6c8  mov     r15, rcx
0x14008b6cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b6d2  lea     rax, WPP_GLOBAL_Control
0x14008b6d9  xor     r12d, r12d
0x14008b6dc  mov     bl, 1
0x14008b6de  cmp     rcx, rax
0x14008b6e1  jz      short loc_14008B6F2
0x14008b6e3  mov     eax, [rcx+2Ch]
0x14008b6e6  test    al, 10h
0x14008b6e8  jz      short loc_14008B6F2
0x14008b6ea  cmp     byte ptr [rcx+29h], 5
0x14008b6ee  mov     dl, bl
0x14008b6f0  jnb     short loc_14008B6F5
0x14008b6f2  mov     dl, r12b
0x14008b6f5  lea     rax, WPP_RECORDER_INITIALIZED
0x14008b6fc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008b703  jz      short loc_14008B70F
0x14008b705  mov     r8b, bl
0x14008b708  cmp     [rcx+48h], r12w
0x14008b70d  jnz     short loc_14008B712
0x14008b70f  mov     r8b, r12b
0x14008b712  test    dl, dl
0x14008b714  jnz     short loc_14008B71B
0x14008b716  test    r8b, r8b
0x14008b719  jz      short loc_14008B72D
0x14008b71b  mov     r9, [rcx+40h]
0x14008b71f  mov     rcx, [rcx+18h]
0x14008b723  mov     [rsp+88h+var_48], rdi
0x14008b728  call    WPP_RECORDER_AND_TRACE_SF_S
0x14008b72d  mov     rcx, r15; Device
0x14008b730  call    cs:__imp_KsAcquireDevice
0x14008b737  nop     dword ptr [rax+rax+00h]
0x14008b73c  call    Feature_53100197__private_IsEnabledDeviceUsageNoInline
0x14008b741  mov     rsi, [rsp+88h+arg_20]
0x14008b749  xor     r9d, r9d; SecurityDescriptor
0x14008b74c  mov     rcx, [r15+18h]; DeviceObject
0x14008b750  mov     r8, rdi; RefString
0x14008b753  mov     [rsp+88h+FilterFactory], rsi; FilterFactory
0x14008b758  mov     rdx, rbp; Descriptor
0x14008b75b  mov     [rsp+88h+WakeCallback], r12; WakeCallback
0x14008b760  mov     [rsp+88h+SleepCallback], r12; SleepCallback
0x14008b765  test    eax, eax
0x14008b767  jz      short loc_14008B770
0x14008b769  mov     [rsp+88h+CreateItemFlags], r12d
0x14008b76e  jmp     short loc_14008B778
0x14008b770  mov     [rsp+88h+CreateItemFlags], 8; CreateItemFlags
0x14008b778  call    cs:__imp_KsCreateFilterFactory
0x14008b77f  nop     dword ptr [rax+rax+00h]
0x14008b784  mov     edi, eax
0x14008b786  test    eax, eax
0x14008b788  jns     short loc_14008B7F7
0x14008b78a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b791  lea     r14, WPP_GLOBAL_Control
0x14008b798  cmp     rcx, r14
0x14008b79b  jz      short loc_14008B7AA
0x14008b79d  mov     eax, [rcx+2Ch]
0x14008b7a0  test    al, 10h
0x14008b7a2  jz      short loc_14008B7AA
0x14008b7a4  cmp     byte ptr [rcx+29h], 2
0x14008b7a8  jnb     short loc_14008B7AD
0x14008b7aa  mov     bl, r12b
0x14008b7ad  lea     rax, WPP_RECORDER_INITIALIZED
0x14008b7b4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008b7bb  setnz   r8b
0x14008b7bf  test    bl, bl
0x14008b7c1  jnz     short loc_14008B7CC
0x14008b7c3  test    r8b, r8b
0x14008b7c6  jz      loc_14008B992
0x14008b7cc  mov     dword ptr [rsp+88h+var_48], edi
0x14008b7d0  lea     rbp, WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids
0x14008b7d7  mov     [rsp+88h+FilterFactory], rbp
0x14008b7dc  mov     dl, bl
0x14008b7de  mov     word ptr [rsp+88h+WakeCallback], 27h ; '''
0x14008b7e5  mov     dword ptr [rsp+88h+SleepCallback], 5
0x14008b7ed  mov     byte ptr [rsp+88h+CreateItemFlags], 2
0x14008b7f2  jmp     loc_14008B985
0x14008b7f7  mov     rax, [rsi]
0x14008b7fa  xor     edx, edx; FilterDescriptor
0x14008b7fc  mov     [rax+10h], r14
0x14008b800  mov     rcx, [rsi]; FilterFactory
0x14008b803  call    cs:__imp_KsFilterFactoryUpdateCacheData
0x14008b80a  nop     dword ptr [rax+rax+00h]
0x14008b80f  lea     rbp, WPP_6c4f75d1f4a33ce04ed2e3eb893acb24_Traceguids
0x14008b816  mov     edi, eax
0x14008b818  test    eax, eax
0x14008b81a  jns     short loc_14008B88B
0x14008b81c  mov     r10, cs:WPP_GLOBAL_Control
0x14008b823  lea     r14, WPP_GLOBAL_Control
0x14008b82a  cmp     r10, r14
0x14008b82d  jz      short loc_14008B841
0x14008b82f  mov     ecx, [r10+2Ch]
0x14008b833  test    cl, 10h
0x14008b836  jz      short loc_14008B841
0x14008b838  cmp     byte ptr [r10+29h], 2
0x14008b83d  mov     dl, bl
0x14008b83f  jnb     short loc_14008B844
0x14008b841  mov     dl, r12b
0x14008b844  lea     rax, WPP_RECORDER_INITIALIZED
0x14008b84b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008b852  setnz   r8b
0x14008b856  test    dl, dl
0x14008b858  jnz     short loc_14008B85F
0x14008b85a  test    r8b, r8b
0x14008b85d  jz      short loc_14008B892
0x14008b85f  mov     r9, [r10+40h]
0x14008b863  mov     rcx, [r10+18h]
0x14008b867  mov     dword ptr [rsp+88h+var_48], edi
0x14008b86b  mov     [rsp+88h+FilterFactory], rbp
0x14008b870  mov     word ptr [rsp+88h+WakeCallback], 28h ; '('
0x14008b877  mov     dword ptr [rsp+88h+SleepCallback], 5
0x14008b87f  mov     byte ptr [rsp+88h+CreateItemFlags], 2
0x14008b884  call    WPP_RECORDER_AND_TRACE_SF_d
0x14008b889  jmp     short loc_14008B892
0x14008b88b  lea     r14, WPP_GLOBAL_Control
0x14008b892  mov     rcx, [rsi]; FilterFactory
0x14008b895  call    cs:__imp_KsFilterFactoryGetSymbolicLink
0x14008b89c  nop     dword ptr [rax+rax+00h]
0x14008b8a1  mov     rcx, [rsp+88h+arg_28]
0x14008b8a9  mov     rdx, [rax+8]
0x14008b8ad  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x14008b8b2  test    al, al
0x14008b8b4  jnz     short loc_14008B91C
0x14008b8b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b8bd  cmp     rcx, r14
0x14008b8c0  jz      short loc_14008B8D1
0x14008b8c2  mov     eax, [rcx+2Ch]
0x14008b8c5  test    al, 10h
0x14008b8c7  jz      short loc_14008B8D1
0x14008b8c9  cmp     byte ptr [rcx+29h], 2
0x14008b8cd  mov     dl, bl
0x14008b8cf  jnb     short loc_14008B8D4
0x14008b8d1  mov     dl, r12b
0x14008b8d4  lea     rsi, WPP_RECORDER_INITIALIZED
0x14008b8db  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14008b8e2  setnz   r8b
0x14008b8e6  test    dl, dl
0x14008b8e8  jnz     short loc_14008B8EF
0x14008b8ea  test    r8b, r8b
0x14008b8ed  jz      short loc_14008B915
0x14008b8ef  mov     r9, [rcx+40h]
0x14008b8f3  mov     rcx, [rcx+18h]
0x14008b8f7  mov     [rsp+88h+FilterFactory], rbp
0x14008b8fc  mov     word ptr [rsp+88h+WakeCallback], 29h ; ')'
0x14008b903  mov     dword ptr [rsp+88h+SleepCallback], 5
0x14008b90b  mov     byte ptr [rsp+88h+CreateItemFlags], 2
0x14008b910  call    WPP_RECORDER_AND_TRACE_SF_
0x14008b915  mov     edi, 0C000009Ah
0x14008b91a  jmp     short loc_14008B923
0x14008b91c  lea     rsi, WPP_RECORDER_INITIALIZED
0x14008b923  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b92a  mov     eax, [rcx+2Ch]
0x14008b92d  test    al, 10h
0x14008b92f  jz      short loc_14008B939
0x14008b931  cmp     byte ptr [rcx+29h], 5
0x14008b935  mov     al, bl
0x14008b937  jnb     short loc_14008B93C
0x14008b939  mov     al, r12b
0x14008b93c  cmp     rcx, r14
0x14008b93f  jz      short loc_14008B947
0x14008b941  mov     dl, bl
0x14008b943  test    al, al
0x14008b945  jnz     short loc_14008B94A
0x14008b947  mov     dl, r12b
0x14008b94a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14008b951  jz      short loc_14008B95A
0x14008b953  cmp     [rcx+48h], r12w
0x14008b958  jnz     short loc_14008B95D
0x14008b95a  mov     bl, r12b
0x14008b95d  test    dl, dl
0x14008b95f  jnz     short loc_14008B965
0x14008b961  test    bl, bl
0x14008b963  jz      short loc_14008B992
0x14008b965  mov     dword ptr [rsp+88h+var_48], edi
0x14008b969  mov     r8b, bl
0x14008b96c  mov     [rsp+88h+FilterFactory], rbp
0x14008b971  mov     word ptr [rsp+88h+WakeCallback], 2Ah ; '*'
0x14008b978  mov     dword ptr [rsp+88h+SleepCallback], 5
0x14008b980  mov     byte ptr [rsp+88h+CreateItemFlags], 5
0x14008b985  mov     r9, [rcx+40h]
0x14008b989  mov     rcx, [rcx+18h]
0x14008b98d  call    WPP_RECORDER_AND_TRACE_SF_d
0x14008b992  mov     rcx, r15; Device
0x14008b995  call    cs:__imp_KsReleaseDevice
0x14008b99c  nop     dword ptr [rax+rax+00h]
0x14008b9a1  mov     eax, edi
0x14008b9a3  add     rsp, 50h
0x14008b9a7  pop     r15
0x14008b9a9  pop     r14
0x14008b9ab  pop     r12
0x14008b9ad  pop     rdi
0x14008b9ae  pop     rsi
0x14008b9af  pop     rbp
0x14008b9b0  pop     rbx
0x14008b9b1  retn
```
