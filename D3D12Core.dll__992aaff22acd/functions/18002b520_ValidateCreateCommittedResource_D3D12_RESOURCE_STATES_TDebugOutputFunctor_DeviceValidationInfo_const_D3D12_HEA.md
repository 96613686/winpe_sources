# ValidateCreateCommittedResource<D3D12_RESOURCE_STATES>(TDebugOutputFunctor &,DeviceValidationInfo const &,D3D12_HEAP_PROPERTIES const *,D3D12_HEAP_FLAGS,D3D12_RESOURCE_DESC2 const *,D3D12_RESOURCE_STATES,D3D12_CLEAR_VALUE const *,uint,uint,DXGI_FORMAT const *,unsigned __int64)

- ea: `0x18002b520`
- end: `0x18002b793`
- name: `??$ValidateCreateCommittedResource@W4D3D12_RESOURCE_STATES@@@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@PEBUD3D12_HEAP_PROPERTIES@@W4D3D12_HEAP_FLAGS@@PEBUD3D12_RESOURCE_DESC2@@W4D3D12_RESOURCE_STATES@@PEBUD3D12_CLEAR_VALUE@@IIPEBW4DXGI_FORMAT@@_K@Z`
- size: `627`
- prototype: `__int64 __usercall@<rax>(struct TDebugOutputFunctor *@<rcx>, struct DeviceValidationInfo *@<rdx>, struct D3D12_HEAP_PROPERTIES *@<r8>, enum D3D12_RESOURCE_DIMENSION *, enum D3D12_RESOURCE_STATES, struct D3D12_CLEAR_VALUE *, unsigned int, int, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002b448`
- `0x18002c4e0`

## callees

- `0x18002b520`
- `0x18002ef50`
- `0x18006a598`
- `0x180079d58`
- `0x18007de6c`
- `0x180093e5c`
- `0x1800bb480`
- `0x180262020`

## string_xrefs

- `0x18002b70e`: `When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource format must be displayable (D3D12_FORMAT_SUPPORT1_DISPLAY).  To use other formats, use CreatePlacedResource instead.`
- `0x18002b724`: `When D3D12_HEAP_FLAG_ALLOW_SHADER_ATOMICS is set in CreateCommittedResource, the resource flags must contain D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS. Otherwise, it suggests a waste of a constrained system resource.`
- `0x18002b660`: `D3D12_RESOURCE_FLAG_ALLOW_CROSS_ADAPTER is not supported for committed resources with D3D12_TEXTURE_LAYOUT_GUID. Use CreatePlacedResource on a cross-adapter shared heap instead.`
- `0x18002b679`: `When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource dimension must be D3D12_RESOURCE_DIMENSION_TEXTURE2D.`
- `0x18002b68d`: `When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource layout must be D3D12_TEXTURE_LAYOUT_ROW_MAJOR.`
- `0x18002b6ef`: `When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource format must be displayable (D3D12_FORMAT_SUPPORT1_DISPLAY or D3D12_FORMAT_SUPPORT2_DISPLAYABLE).  To use other formats, use CreatePlacedResource instead.`

## pseudocode

```c
__int64 __fastcall ValidateCreateCommittedResource<enum D3D12_RESOURCE_STATES>(
        struct TDebugOutputFunctor *a1,
        struct DeviceValidationInfo *a2,
        struct D3D12_HEAP_PROPERTIES *a3,
        enum D3D12_HEAP_FLAGS a4,
        enum D3D12_RESOURCE_DIMENSION *a5,
        enum D3D12_RESOURCE_STATES a6,
        struct D3D12_CLEAR_VALUE *a7,
        unsigned int a8,
        int a9,
        int a10,
        unsigned __int64 a11)
{
  __int64 result; // rax
  struct TDebugOutputFunctor *v16; // rcx
  const char *v17; // r8
  __int64 v18; // rdx
  int v19; // r14d
  unsigned __int64 v20; // r9
  int v21; // [rsp+50h] [rbp-49h] BYREF
  __int64 v22; // [rsp+54h] [rbp-45h]
  _BYTE v23[24]; // [rsp+60h] [rbp-39h] BYREF
  unsigned int VisibleNodeMask; // [rsp+78h] [rbp-21h]
  __int64 v25; // [rsp+80h] [rbp-19h]
  enum D3D12_HEAP_FLAGS v26; // [rsp+88h] [rbp-11h]

  *(__m128i *)v23 = _mm_load_si128((const __m128i *)&_xmm);
  *(_DWORD *)&v23[16] = 638;
  *(_DWORD *)&v23[20] = 640;
  VisibleNodeMask = 1363;
  result = ValidateHeapPropertiesAndFlags(a1, a2, a3, a4, (const struct HeapValidationIDs *)v23, 1, a8);
  if ( (int)result >= 0 )
  {
    v16 = a1;
    if ( !a5 )
    {
      v17 = "pResourceDesc is NULL!";
      v18 = 700;
LABEL_4:
      TDebugOutputFunctor::operator()(v16, v18, v17);
      return 2147942487LL;
    }
    *(_QWORD *)v23 = 0;
    *(_OWORD *)&v23[8] = *(_OWORD *)&a3->Type;
    VisibleNodeMask = a3->VisibleNodeMask;
    v25 = 0;
    v26 = a4;
    result = ValidateHeapAndResourceCreation(
               a1,
               (enum D3D_FEATURE_LEVEL *)a2,
               (const struct CD3DX12_HEAP_DESC *)v23,
               0,
               a5,
               a7,
               0,
               0,
               a11);
    if ( (int)result >= 0 )
    {
      result = ValidateInitialResourceState(
                 a1,
                 a6,
                 *a5,
                 *((_DWORD *)a5 + 9),
                 (enum D3D12_RESOURCE_FLAGS)*((_DWORD *)a5 + 12),
                 a2,
                 a3->Type,
                 a3);
      if ( (int)result >= 0 )
      {
        if ( (a4 & 0x20) != 0 )
        {
          if ( *((_DWORD *)a5 + 11) == 4 )
          {
            v17 = "D3D12_RESOURCE_FLAG_ALLOW_CROSS_ADAPTER is not supported for committed resources with D3D12_TEXTURE_LA"
                  "YOUT_GUID. Use CreatePlacedResource on a cross-adapter shared heap instead.";
LABEL_10:
            v18 = 724;
LABEL_11:
            v16 = a1;
            goto LABEL_4;
          }
          if ( *a5 != D3D12_RESOURCE_DIMENSION_TEXTURE2D )
          {
            v17 = "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource dimension mu"
                  "st be D3D12_RESOURCE_DIMENSION_TEXTURE2D.";
            v18 = 720;
            goto LABEL_11;
          }
          if ( *((_DWORD *)a5 + 11) != 1 )
          {
            v17 = "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource layout must "
                  "be D3D12_TEXTURE_LAYOUT_ROW_MAJOR.";
            goto LABEL_10;
          }
          v22 = 0;
          v21 = *((_DWORD *)a5 + 8);
          v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)a2 + 83) + 104LL))(
                  *((_QWORD *)a2 + 83),
                  3,
                  &v21);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) )
          {
            if ( v19 < 0 || (v22 & 0x80000) == 0 && (v22 & 0x1000000000000LL) == 0 )
            {
              v17 = "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource format mus"
                    "t be displayable (D3D12_FORMAT_SUPPORT1_DISPLAY or D3D12_FORMAT_SUPPORT2_DISPLAYABLE).  To use other"
                    " formats, use CreatePlacedResource instead.";
LABEL_21:
              v18 = 738;
              goto LABEL_11;
            }
          }
          else if ( v19 < 0 || (v22 & 0x80000) == 0 )
          {
            v17 = "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource format must "
                  "be displayable (D3D12_FORMAT_SUPPORT1_DISPLAY).  To use other formats, use CreatePlacedResource instead.";
            goto LABEL_21;
          }
        }
        if ( (a4 & 0x400) != 0 && (a5[12] & 4) == 0 )
        {
          v17 = "When D3D12_HEAP_FLAG_ALLOW_SHADER_ATOMICS is set in CreateCommittedResource, the resource flags must con"
                "tain D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS. Otherwise, it suggests a waste of a constrained system resource.";
          v18 = 640;
          goto LABEL_11;
        }
        if ( *a5 == D3D12_RESOURCE_DIMENSION_BUFFER )
        {
          v20 = *((_QWORD *)a5 + 2);
          if ( v20 > 0xFFFF0000
            && a3->Type != D3D12_HEAP_TYPE_DEFAULT
            && (a3->Type != D3D12_HEAP_TYPE_CUSTOM || a3->CPUPageProperty != D3D12_CPU_PAGE_PROPERTY_NOT_AVAILABLE) )
          {
            TDebugOutputFunctor::operator()(
              a1,
              1342,
              "D3D12_RESOURCE_DESC::Width is invalid for a CPU-visible buffer. The size is %I64u, and it must be less than %I64u.",
              v20,
              4294901760LL);
          }
        }
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b520  push    rbp
0x18002b522  push    rbx
0x18002b523  push    rsi
0x18002b524  push    rdi
0x18002b525  push    r12
0x18002b527  push    r14
0x18002b529  push    r15
0x18002b52b  lea     rbp, [rsp-7]
0x18002b530  sub     rsp, 0A0h
0x18002b537  mov     rax, cs:__security_cookie
0x18002b53e  xor     rax, rsp
0x18002b541  mov     [rbp+37h+var_40], rax
0x18002b545  mov     r15d, r9d
0x18002b548  mov     rsi, r8
0x18002b54b  mov     r14, rdx
0x18002b54e  mov     rbx, rcx
0x18002b551  mov     rdi, [rbp+37h+arg_20]
0x18002b555  mov     r12, [rbp+37h+arg_30]
0x18002b559  movdqa  xmm0, cs:__xmm@0000027f0000027d0000027c0000027b
0x18002b561  movdqu  [rbp+37h+var_70], xmm0
0x18002b566  mov     [rbp+37h+var_60], 27Eh
0x18002b56d  mov     [rbp+37h+var_5C], 280h
0x18002b574  mov     [rbp+37h+var_58], 553h
0x18002b57b  mov     eax, [rbp+37h+arg_38]
0x18002b57e  mov     [rsp+0D0h+var_A0], eax; unsigned int
0x18002b582  mov     byte ptr [rsp+0D0h+var_A8], 1; bool
0x18002b587  lea     rax, [rbp+37h+var_70]
0x18002b58b  mov     qword ptr [rsp+0D0h+var_B0], rax; struct HeapValidationIDs *
0x18002b590  call    ?ValidateHeapPropertiesAndFlags@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@PEBUD3D12_HEAP_PROPERTIES@@W4D3D12_HEAP_FLAGS@@AEBUHeapValidationIDs@@_NI@Z; ValidateHeapPropertiesAndFlags(TDebugOutputFunctor &,DeviceValidationInfo const &,D3D12_HEAP_PROPERTIES const *,D3D12_HEAP_FLAGS,HeapValidationIDs const &,bool,uint)
0x18002b595  test    eax, eax
0x18002b597  js      loc_18002B775
0x18002b59d  mov     rcx, rbx; struct TDebugOutputFunctor *
0x18002b5a0  test    rdi, rdi
0x18002b5a3  jnz     short loc_18002B5C0
0x18002b5a5  lea     r8, aPresourcedescI; "pResourceDesc is NULL!"
0x18002b5ac  mov     edx, 2BCh
0x18002b5b1  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18002b5b6  mov     eax, 80070057h
0x18002b5bb  jmp     loc_18002B775
0x18002b5c0  mov     qword ptr [rbp+37h+var_70], 0
0x18002b5c8  movups  xmm0, xmmword ptr [rsi]
0x18002b5cb  movups  [rbp+37h+var_70+8], xmm0
0x18002b5cf  mov     eax, [rsi+10h]
0x18002b5d2  mov     [rbp+37h+var_58], eax
0x18002b5d5  mov     [rbp+37h+var_50], 0
0x18002b5dd  mov     [rbp+37h+var_48], r15d
0x18002b5e1  mov     rax, [rbp+37h+arg_50]
0x18002b5e8  mov     [rsp+0D0h+var_90], rax; unsigned __int64
0x18002b5ed  mov     [rsp+0D0h+var_98], 0; enum DXGI_FORMAT *
0x18002b5f6  mov     [rsp+0D0h+var_A0], 0; unsigned int
0x18002b5fe  mov     [rsp+0D0h+var_A8], r12; struct D3D12_CLEAR_VALUE *
0x18002b603  mov     qword ptr [rsp+0D0h+var_B0], rdi; enum D3D12_RESOURCE_DIMENSION *
0x18002b608  xor     r9d, r9d; unsigned __int64
0x18002b60b  lea     r8, [rbp+37h+var_70]; struct CD3DX12_HEAP_DESC *
0x18002b60f  mov     rdx, r14; struct DeviceValidationInfo *
0x18002b612  call    ?ValidateHeapAndResourceCreation@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@AEBUCD3DX12_HEAP_DESC@@_KAEBUCD3DX12_RESOURCE_DESC2@@PEBUD3D12_CLEAR_VALUE@@IPEBW4DXGI_FORMAT@@3@Z; ValidateHeapAndResourceCreation(TDebugOutputFunctor &,DeviceValidationInfo const &,CD3DX12_HEAP_DESC const &,unsigned __int64,CD3DX12_RESOURCE_DESC2 const &,D3D12_CLEAR_VALUE const *,uint,DXGI_FORMAT const *,unsigned __int64)
0x18002b617  test    eax, eax
0x18002b619  js      loc_18002B775
0x18002b61f  mov     [rsp+0D0h+var_98], rsi; struct D3D12_HEAP_PROPERTIES *
0x18002b624  mov     eax, [rsi]
0x18002b626  mov     [rsp+0D0h+var_A0], eax; enum D3D12_HEAP_TYPE
0x18002b62a  mov     [rsp+0D0h+var_A8], r14; struct DeviceValidationInfo *
0x18002b62f  mov     eax, [rdi+30h]
0x18002b632  mov     [rsp+0D0h+var_B0], eax; enum D3D12_RESOURCE_FLAGS
0x18002b636  mov     r9d, [rdi+24h]; unsigned int
0x18002b63a  mov     r8d, [rdi]; enum D3D12_RESOURCE_DIMENSION
0x18002b63d  mov     edx, [rbp+37h+arg_28]; enum D3D12_RESOURCE_STATES
0x18002b640  mov     rcx, rbx; struct TDebugOutputFunctor *
0x18002b643  call    ?ValidateInitialResourceState@@YAJAEAUTDebugOutputFunctor@@W4D3D12_RESOURCE_STATES@@W4D3D12_RESOURCE_DIMENSION@@IW4D3D12_RESOURCE_FLAGS@@AEBUDeviceValidationInfo@@W4D3D12_HEAP_TYPE@@PEBUD3D12_HEAP_PROPERTIES@@@Z; ValidateInitialResourceState(TDebugOutputFunctor &,D3D12_RESOURCE_STATES,D3D12_RESOURCE_DIMENSION,uint,D3D12_RESOURCE_FLAGS,DeviceValidationInfo const &,D3D12_HEAP_TYPE,D3D12_HEAP_PROPERTIES const *)
0x18002b648  test    eax, eax
0x18002b64a  js      loc_18002B775
0x18002b650  test    r15b, 20h
0x18002b654  jz      loc_18002B717
0x18002b65a  cmp     dword ptr [rdi+2Ch], 4
0x18002b65e  jnz     short loc_18002B674
0x18002b660  lea     r8, aD3d12ResourceF_11; "D3D12_RESOURCE_FLAG_ALLOW_CROSS_ADAPTER"...
0x18002b667  mov     edx, 2D4h
0x18002b66c  mov     rcx, rbx
0x18002b66f  jmp     loc_18002B5B1
0x18002b674  cmp     dword ptr [rdi], 3
0x18002b677  jz      short loc_18002B687
0x18002b679  lea     r8, aWhenD3d12HeapF_3; "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPT"...
0x18002b680  mov     edx, 2D0h
0x18002b685  jmp     short loc_18002B66C
0x18002b687  cmp     dword ptr [rdi+2Ch], 1
0x18002b68b  jz      short loc_18002B696
0x18002b68d  lea     r8, aWhenD3d12HeapF_4; "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPT"...
0x18002b694  jmp     short loc_18002B667
0x18002b696  mov     [rbp+37h+var_7C], 0
0x18002b69e  mov     eax, [rdi+20h]
0x18002b6a1  mov     [rbp+37h+var_80], eax
0x18002b6a4  mov     rcx, [r14+298h]
0x18002b6ab  mov     rax, [rcx]
0x18002b6ae  mov     r9d, 0Ch
0x18002b6b4  lea     r8, [rbp+37h+var_80]
0x18002b6b8  lea     edx, [r9-9]
0x18002b6bc  mov     rax, [rax+68h]
0x18002b6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6c5  mov     r14d, eax
0x18002b6c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12Displayable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable> `wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl(void)'::`2'::impl
0x18002b6cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(void)
0x18002b6d4  test    al, al
0x18002b6d6  jz      short loc_18002B700
0x18002b6d8  test    r14d, r14d
0x18002b6db  js      short loc_18002B6EF
0x18002b6dd  test    dword ptr [rbp+37h+var_7C], 80000h
0x18002b6e4  jnz     short loc_18002B717
0x18002b6e6  test    dword ptr [rbp+37h+var_7C+4], 10000h
0x18002b6ed  jnz     short loc_18002B717
0x18002b6ef  lea     r8, aWhenD3d12HeapF_0; "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPT"...
0x18002b6f6  mov     edx, 2E2h
0x18002b6fb  jmp     loc_18002B66C
0x18002b700  test    r14d, r14d
0x18002b703  js      short loc_18002B70E
0x18002b705  test    dword ptr [rbp+37h+var_7C], 80000h
0x18002b70c  jnz     short loc_18002B717
0x18002b70e  lea     r8, aWhenD3d12HeapF; "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPT"...
0x18002b715  jmp     short loc_18002B6F6
0x18002b717  bt      r15d, 0Ah
0x18002b71c  jnb     short loc_18002B735
0x18002b71e  test    byte ptr [rdi+30h], 4
0x18002b722  jnz     short loc_18002B735
0x18002b724  lea     r8, aWhenD3d12HeapF_1; "When D3D12_HEAP_FLAG_ALLOW_SHADER_ATOMI"...
0x18002b72b  mov     edx, 280h
0x18002b730  jmp     loc_18002B66C
0x18002b735  cmp     dword ptr [rdi], 1
0x18002b738  jnz     short loc_18002B773
0x18002b73a  mov     r9, [rdi+10h]
0x18002b73e  mov     edx, 0FFFF0000h
0x18002b743  cmp     r9, rdx
0x18002b746  jbe     short loc_18002B773
0x18002b748  mov     ecx, [rsi]
0x18002b74a  sub     ecx, 1
0x18002b74d  jz      short loc_18002B773
0x18002b74f  cmp     ecx, 3
0x18002b752  jnz     short loc_18002B75A
0x18002b754  cmp     dword ptr [rsi+4], 1
0x18002b758  jz      short loc_18002B773
0x18002b75a  mov     qword ptr [rsp+0D0h+var_B0], rdx
0x18002b75f  lea     r8, aD3d12ResourceD_21; "D3D12_RESOURCE_DESC::Width is invalid f"...
0x18002b766  mov     edx, 53Eh
0x18002b76b  mov     rcx, rbx
0x18002b76e  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18002b773  xor     eax, eax
0x18002b775  mov     rcx, [rbp+37h+var_40]
0x18002b779  xor     rcx, rsp; StackCookie
0x18002b77c  call    __security_check_cookie
0x18002b781  add     rsp, 0A0h
0x18002b788  pop     r15
0x18002b78a  pop     r14
0x18002b78c  pop     r12
0x18002b78e  pop     rdi
0x18002b78f  pop     rsi
0x18002b790  pop     rbx
0x18002b791  pop     rbp
0x18002b792  retn
```
