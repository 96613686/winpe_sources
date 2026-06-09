# ValidateCreateCompatibleSharedResource<D3D12_RESOURCE_STATES>(TDebugOutputFunctor &,DeviceValidationInfo const &,D3D12_HEAP_PROPERTIES const *,D3D12_HEAP_FLAGS,D3D12_RESOURCE_DESC const *,D3D12_RESOURCE_STATES,D3D12_CLEAR_VALUE const *,D3D11_RESOURCE_FLAGS const *,D3D12_COMPATIBILITY_SHARED_FLAGS,uint)

- ea: `0x18002b448`
- end: `0x18002b517`
- name: `??$ValidateCreateCompatibleSharedResource@W4D3D12_RESOURCE_STATES@@@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@PEBUD3D12_HEAP_PROPERTIES@@W4D3D12_HEAP_FLAGS@@PEBUD3D12_RESOURCE_DESC@@W4D3D12_RESOURCE_STATES@@PEBUD3D12_CLEAR_VALUE@@PEBUD3D11_RESOURCE_FLAGS@@W4D3D12_COMPATIBILITY_SHARED_FLAGS@@I@Z`
- size: `207`
- prototype: `__int64 __fastcall(struct TDebugOutputFunctor *, struct DeviceValidationInfo *, struct D3D12_HEAP_PROPERTIES *, enum D3D12_HEAP_FLAGS, struct D3D12_RESOURCE_DESC *, enum D3D12_RESOURCE_STATES, __int64, __int64, int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002b200`

## callees

- `0x18002b448`
- `0x18002b520`
- `0x18002ba38`
- `0x18002ef50`
- `0x1800abc10`
- `0x1800bb480`
- `0x1800ed4f4`
- `0x180151190`

## string_xrefs

- `0x18002b50b`: `When ID3D12CompatibilityDevice::CreateSharedResource is invoked, the heap flags must contain D3D12_HEAP_MISC_SHARED.`
- `0x18023360f`: `When ID3D12CompatibilityDevice::CreateSharedResource is invoked with heap flags containing D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER, no compatibility shared flags may be used.`
- `0x1802336d7`: `D3D11 bind flags (0x%x) were provided to ID3D12CompatibilityDevice::CreateSharedResource which are not supported by the D3D12 resource desc.`
- `0x1802336e0`: `D3D11 CPU access flags (0x%x) were provided to ID3D12CompatibilityDevice::CreateSharedResource which are not supported by the D3D12 heap properties.`
- `0x180233621`: `Invalid compatibility flags provided to ID3D12CompatibilityDevice::CreateSharedResource.`
- `0x18023364b`: `When D3D11 flags are passed to ID3D12CompatibilityDevice::CreateSharedResource, the keyed mutex property must match between the D3D11 flags and D3D12 compatibility flags.`
- `0x180233669`: `When D3D11 flags are passed to ID3D12CompatibilityDevice::CreateSharedResource, the NT handle flag may not be set in the D3D11 flags if a non-NT handle is requested.`
- `0x1802335c0`: `When D3D11 flags are passed to ID3D12CompatibilityDevice::CreateSharedResource, they must contain either D3D11_RESOURCE_MISC_SHARED or D3D11_RESOURCE_MISC_SHARED_KEYEDMUTEX.`

## pseudocode

```c
__int64 __fastcall ValidateCreateCompatibleSharedResource<enum D3D12_RESOURCE_STATES>(
        struct TDebugOutputFunctor *a1,
        struct DeviceValidationInfo *a2,
        struct D3D12_HEAP_PROPERTIES *a3,
        enum D3D12_HEAP_FLAGS a4,
        struct D3D12_RESOURCE_DESC *a5,
        enum D3D12_RESOURCE_STATES a6,
        __int64 a7,
        _DWORD *a8,
        int a9,
        unsigned int a10)
{
  struct D3D12_CLEAR_VALUE *v14; // r10
  __int64 result; // rax
  const char *Name; // rax
  __int64 v17; // rdx
  char v18; // r11
  int v19; // r9d
  __int64 v20; // r9
  bool v21; // dl
  enum DXGI_FORMAT v22; // ecx
  int v23; // [rsp+40h] [rbp-C8h]
  int v24; // [rsp+48h] [rbp-C0h]
  _BYTE v25[80]; // [rsp+60h] [rbp-A8h] BYREF
  enum D3D12_RESOURCE_DIMENSION *v26; // [rsp+B0h] [rbp-58h]

  ResourceDesc0ToDesc2Helper::ResourceDesc0ToDesc2Helper((ResourceDesc0ToDesc2Helper *)v25, a5);
  result = ValidateCreateCommittedResource<enum D3D12_RESOURCE_STATES>(a1, a2, a3, v26, a6, v14, a10, v23, v24, 0);
  if ( (int)result >= 0 )
  {
    if ( (a4 & 1) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        911,
        "When ID3D12CompatibilityDevice::CreateSharedResource is invoked, the heap flags must contain D3D12_HEAP_MISC_SHARED.");
      return 2147942487LL;
    }
    if ( (a4 & 0x20) != 0 )
    {
      if ( a9 )
      {
        TDebugOutputFunctor::operator()(
          a1,
          911,
          "When ID3D12CompatibilityDevice::CreateSharedResource is invoked with heap flags containing D3D12_HEAP_FLAG_SHA"
          "RED_CROSS_ADAPTER, no compatibility shared flags may be used.");
        return 2147942487LL;
      }
    }
    else if ( (a9 & 0xFFFFFFF8) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        911,
        "Invalid compatibility flags provided to ID3D12CompatibilityDevice::CreateSharedResource.");
      return 2147942487LL;
    }
    if ( !a8 )
      return 0;
    if ( ((a9 & 2) != 0) != ((a8[1] & 0x100) != 0) )
    {
      TDebugOutputFunctor::operator()(
        a1,
        911,
        "When D3D11 flags are passed to ID3D12CompatibilityDevice::CreateSharedResource, the keyed mutex property must ma"
        "tch between the D3D11 flags and D3D12 compatibility flags.");
      return 2147942487LL;
    }
    if ( (((unsigned __int8)~(_BYTE)a9 ^ (unsigned __int8)(a8[1] >> 11)) & 1) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        911,
        "When D3D11 flags are passed to ID3D12CompatibilityDevice::CreateSharedResource, the NT handle flag may not be se"
        "t in the D3D11 flags if a non-NT handle is requested.");
      return 2147942487LL;
    }
    if ( (a8[1] & 0x100) == 0 && (a8[1] & 2) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        911,
        "When D3D11 flags are passed to ID3D12CompatibilityDevice::CreateSharedResource, they must contain either D3D11_R"
        "ESOURCE_MISC_SHARED or D3D11_RESOURCE_MISC_SHARED_KEYEDMUTEX.");
      return 2147942487LL;
    }
    v17 = *a8 & ~ConvertPossibleBindFlags(a5, a4, a2);
    if ( a3->Type == D3D12_HEAP_TYPE_DEFAULT )
    {
      v19 = 0;
    }
    else
    {
      if ( a3->Type != D3D12_HEAP_TYPE_UPLOAD )
      {
        if ( a3->Type == D3D12_HEAP_TYPE_READBACK )
        {
LABEL_26:
          v19 = 196608;
          goto LABEL_29;
        }
        if ( a3->Type != D3D12_HEAP_TYPE_GPU_UPLOAD )
        {
          v19 = 0;
          if ( a3->CPUPageProperty != D3D12_CPU_PAGE_PROPERTY_WRITE_COMBINE )
          {
            if ( a3->CPUPageProperty != D3D12_CPU_PAGE_PROPERTY_WRITE_BACK )
              goto LABEL_29;
            goto LABEL_26;
          }
        }
      }
      v19 = 0x10000;
    }
LABEL_29:
    if ( (_DWORD)v17 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        911,
        "D3D11 bind flags (0x%x) were provided to ID3D12CompatibilityDevice::CreateSharedResource which are not supported"
        " by the D3D12 resource desc.",
        (unsigned int)v17);
      return 2147942487LL;
    }
    v20 = a8[2] & (unsigned int)~v19;
    if ( (_DWORD)v20 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        911,
        "D3D11 CPU access flags (0x%x) were provided to ID3D12CompatibilityDevice::CreateSharedResource which are not sup"
        "ported by the D3D12 heap properties.",
        v20);
      return 2147942487LL;
    }
    if ( a5->Dimension != D3D12_RESOURCE_DIMENSION_BUFFER
      && (v18 & 4) == 0
      && !(unsigned __int8)CD3D11FormatHelper::ValidD3D11SharedResourceFormat(
                             (unsigned int)a5->Format,
                             v17,
                             *((unsigned int *)a2 + 165)) )
    {
      Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v22, v21);
      TDebugOutputFunctor::operator()(
        a1,
        912,
        "Invalid format specified (%s) for sharing with D3D11. To check if a format is valid, query a D3D11 device for D3"
        "D11_FORMAT_SUPPORT2_SHAREABLE.",
        Name);
      return 2147942487LL;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002b448  push    rbx
0x18002b44a  push    rbp
0x18002b44b  push    rsi
0x18002b44c  push    rdi
0x18002b44d  push    r14
0x18002b44f  push    r15
0x18002b451  sub     rsp, 0D8h
0x18002b458  mov     rax, cs:__security_cookie
0x18002b45f  xor     rax, rsp
0x18002b462  mov     [rsp+108h+var_48], rax
0x18002b46a  mov     r14, [rsp+108h+arg_20]
0x18002b472  mov     rbx, rcx
0x18002b475  mov     rbp, [rsp+108h+arg_38]
0x18002b47d  lea     rcx, [rsp+108h+var_A8]; this
0x18002b482  mov     r10, [rsp+108h+arg_30]
0x18002b48a  mov     r15, rdx
0x18002b48d  mov     rdx, r14; struct D3D12_RESOURCE_DESC *
0x18002b490  mov     esi, r9d
0x18002b493  mov     rdi, r8
0x18002b496  call    ??0ResourceDesc0ToDesc2Helper@@QEAA@PEBUD3D12_RESOURCE_DESC@@@Z; ResourceDesc0ToDesc2Helper::ResourceDesc0ToDesc2Helper(D3D12_RESOURCE_DESC const *)
0x18002b49b  mov     eax, [rsp+108h+arg_48]
0x18002b4a2  mov     r9d, esi
0x18002b4a5  mov     rdx, [rsp+108h+var_58]
0x18002b4ad  mov     r8, rdi; struct D3D12_HEAP_PROPERTIES *
0x18002b4b0  mov     [rsp+108h+var_B8], 0; unsigned __int64
0x18002b4b9  mov     rcx, rbx; struct TDebugOutputFunctor *
0x18002b4bc  mov     [rsp+108h+var_D0], eax; unsigned int
0x18002b4c0  mov     eax, [rsp+108h+arg_28]
0x18002b4c7  mov     [rsp+108h+var_D8], r10; struct D3D12_CLEAR_VALUE *
0x18002b4cc  mov     [rsp+108h+var_E0], eax; enum D3D12_RESOURCE_STATES
0x18002b4d0  mov     [rsp+108h+var_E8], rdx; enum D3D12_RESOURCE_DIMENSION *
0x18002b4d5  mov     rdx, r15; struct DeviceValidationInfo *
0x18002b4d8  call    ??$ValidateCreateCommittedResource@W4D3D12_RESOURCE_STATES@@@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@PEBUD3D12_HEAP_PROPERTIES@@W4D3D12_HEAP_FLAGS@@PEBUD3D12_RESOURCE_DESC2@@W4D3D12_RESOURCE_STATES@@PEBUD3D12_CLEAR_VALUE@@IIPEBW4DXGI_FORMAT@@_K@Z; ValidateCreateCommittedResource<D3D12_RESOURCE_STATES>(TDebugOutputFunctor &,DeviceValidationInfo const &,D3D12_HEAP_PROPERTIES const *,D3D12_HEAP_FLAGS,D3D12_RESOURCE_DESC2 const *,D3D12_RESOURCE_STATES,D3D12_CLEAR_VALUE const *,uint,uint,DXGI_FORMAT const *,unsigned __int64)
0x18002b4dd  test    eax, eax
0x18002b4df  jns     short loc_18002B501
0x18002b4e1  mov     rcx, [rsp+108h+var_48]
0x18002b4e9  xor     rcx, rsp; StackCookie
0x18002b4ec  call    __security_check_cookie
0x18002b4f1  add     rsp, 0D8h
0x18002b4f8  pop     r15
0x18002b4fa  pop     r14
0x18002b4fc  pop     rdi
0x18002b4fd  pop     rsi
0x18002b4fe  pop     rbp
0x18002b4ff  pop     rbx
0x18002b500  retn
0x18002b501  test    sil, 1
0x18002b505  jnz     loc_1802335FC
0x18002b50b  lea     r8, aWhenId3d12comp_2; "When ID3D12CompatibilityDevice::CreateS"...
0x18002b512  jmp     loc_1802335C7
0x1802335c0  lea     r8, aWhenD3d11Flags; "When D3D11 flags are passed to ID3D12Co"...
0x1802335c7  mov     edx, 38Fh
0x1802335cc  mov     rcx, rbx
0x1802335cf  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802335d4  jmp     short loc_1802335F2
0x1802335d6  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x1802335db  mov     r9, rax
0x1802335de  lea     r8, aInvalidFormatS; "Invalid format specified (%s) for shari"...
0x1802335e5  mov     edx, 390h
0x1802335ea  mov     rcx, rbx
0x1802335ed  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802335f2  mov     eax, 80070057h
0x1802335f7  jmp     loc_18002B4E1
0x1802335fc  mov     r11d, [rsp+108h+arg_40]
0x180233604  test    sil, 20h
0x180233608  jz      short loc_180233618
0x18023360a  test    r11d, r11d
0x18023360d  jz      short loc_18023362A
0x18023360f  lea     r8, aWhenId3d12comp_0; "When ID3D12CompatibilityDevice::CreateS"...
0x180233616  jmp     short loc_1802335C7
0x180233618  test    r11d, 0FFFFFFF8h
0x18023361f  jz      short loc_18023362A
0x180233621  lea     r8, aInvalidCompati; "Invalid compatibility flags provided to"...
0x180233628  jmp     short loc_1802335C7
0x18023362a  test    rbp, rbp
0x18023362d  jz      loc_180233726
0x180233633  mov     edx, [rbp+4]
0x180233636  mov     ecx, r11d
0x180233639  shr     ecx, 1
0x18023363b  and     cl, 1
0x18023363e  and     edx, 100h
0x180233644  setnz   al
0x180233647  cmp     cl, al
0x180233649  jz      short loc_180233657
0x18023364b  lea     r8, aWhenD3d11Flags_1; "When D3D11 flags are passed to ID3D12Co"...
0x180233652  jmp     loc_1802335C7
0x180233657  mov     ecx, [rbp+4]
0x18023365a  mov     al, r11b
0x18023365d  shr     ecx, 0Bh
0x180233660  not     al
0x180233662  xor     cl, al
0x180233664  test    cl, 1
0x180233667  jz      short loc_180233675
0x180233669  lea     r8, aWhenD3d11Flags_0; "When D3D11 flags are passed to ID3D12Co"...
0x180233670  jmp     loc_1802335C7
0x180233675  test    edx, edx
0x180233677  jnz     short loc_180233683
0x180233679  test    byte ptr [rbp+4], 2
0x18023367d  jz      loc_1802335C0
0x180233683  mov     r8, r15; struct DeviceValidationInfo *
0x180233686  mov     edx, esi; enum D3D12_HEAP_FLAGS
0x180233688  mov     rcx, r14; struct D3D12_RESOURCE_DESC *
0x18023368b  call    ?ConvertPossibleBindFlags@@YAIAEBUD3D12_RESOURCE_DESC@@W4D3D12_HEAP_FLAGS@@AEBUDeviceValidationInfo@@@Z; ConvertPossibleBindFlags(D3D12_RESOURCE_DESC const &,D3D12_HEAP_FLAGS,DeviceValidationInfo const &)
0x180233690  mov     ecx, [rdi]
0x180233692  mov     edx, eax
0x180233694  not     edx
0x180233696  and     edx, [rbp+0]
0x180233699  sub     ecx, 1
0x18023369c  jz      short loc_1802336CD
0x18023369e  sub     ecx, 1
0x1802336a1  jz      short loc_1802336C5
0x1802336a3  sub     ecx, 1
0x1802336a6  jz      short loc_1802336BD
0x1802336a8  cmp     ecx, 2
0x1802336ab  jz      short loc_1802336C5
0x1802336ad  mov     ecx, [rdi+4]
0x1802336b0  xor     r9d, r9d
0x1802336b3  sub     ecx, 2
0x1802336b6  jz      short loc_1802336C5
0x1802336b8  cmp     ecx, 1
0x1802336bb  jnz     short loc_1802336D0
0x1802336bd  mov     r9d, 30000h
0x1802336c3  jmp     short loc_1802336D0
0x1802336c5  mov     r9d, 10000h
0x1802336cb  jmp     short loc_1802336D0
0x1802336cd  xor     r9d, r9d
0x1802336d0  test    edx, edx
0x1802336d2  jz      short loc_1802336F9
0x1802336d4  mov     r9d, edx
0x1802336d7  lea     r8, aD3d11BindFlags; "D3D11 bind flags (0x%x) were provided t"...
0x1802336de  jmp     short loc_1802336E7
0x1802336e0  lea     r8, aD3d11CpuAccess; "D3D11 CPU access flags (0x%x) were prov"...
0x1802336e7  mov     edx, 38Fh
0x1802336ec  mov     rcx, rbx
0x1802336ef  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802336f4  jmp     loc_1802335F2
0x1802336f9  not     r9d
0x1802336fc  and     r9d, [rbp+8]
0x180233700  jnz     short loc_1802336E0
0x180233702  cmp     dword ptr [r14], 1
0x180233706  jz      short loc_180233726
0x180233708  test    r11b, 4
0x18023370c  jnz     short loc_180233726
0x18023370e  mov     ecx, [r14+20h]
0x180233712  mov     r8d, [r15+294h]
0x180233719  call    ?ValidD3D11SharedResourceFormat@CD3D11FormatHelper@@SA_NW4DXGI_FORMAT@@W4D3D_FEATURE_LEVEL@@W4eExtendedFormatFeatures@1@@Z; CD3D11FormatHelper::ValidD3D11SharedResourceFormat(DXGI_FORMAT,D3D_FEATURE_LEVEL,CD3D11FormatHelper::eExtendedFormatFeatures)
0x18023371e  test    al, al
0x180233720  jz      loc_1802335D6
0x180233726  xor     eax, eax
0x180233728  jmp     loc_18002B4E1
```
