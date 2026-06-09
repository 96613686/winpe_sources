# ValidateCreateCommittedResource<D3D12_BARRIER_LAYOUT>(TDebugOutputFunctor &,DeviceValidationInfo const &,D3D12_HEAP_PROPERTIES const *,D3D12_HEAP_FLAGS,D3D12_RESOURCE_DESC2 const *,D3D12_BARRIER_LAYOUT,D3D12_CLEAR_VALUE const *,uint,uint,DXGI_FORMAT const *,unsigned __int64)

- ea: `0x1800e674c`
- end: `0x1800e69d2`
- name: `??$ValidateCreateCommittedResource@W4D3D12_BARRIER_LAYOUT@@@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@PEBUD3D12_HEAP_PROPERTIES@@W4D3D12_HEAP_FLAGS@@PEBUD3D12_RESOURCE_DESC2@@W4D3D12_BARRIER_LAYOUT@@PEBUD3D12_CLEAR_VALUE@@IIPEBW4DXGI_FORMAT@@_K@Z`
- size: `646`
- prototype: `__int64 __usercall@<rax>(struct TDebugOutputFunctor *@<rcx>, struct DeviceValidationInfo *@<rdx>, enum D3D12_RESOURCE_DIMENSION *, int, struct D3D12_CLEAR_VALUE *, unsigned int, unsigned int, enum DXGI_FORMAT *, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800cd9fc`

## callees

- `0x18002ef50`
- `0x18006a598`
- `0x180079d58`
- `0x18007de6c`
- `0x1800bb480`
- `0x1800e674c`
- `0x180100048`
- `0x180262020`

## string_xrefs

- `0x1800e694b`: `When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource format must be displayable (D3D12_FORMAT_SUPPORT1_DISPLAY).  To use other formats, use CreatePlacedResource instead.`
- `0x1800e6961`: `When D3D12_HEAP_FLAG_ALLOW_SHADER_ATOMICS is set in CreateCommittedResource, the resource flags must contain D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS. Otherwise, it suggests a waste of a constrained system resource.`
- `0x1800e6895`: `D3D12_RESOURCE_FLAG_ALLOW_CROSS_ADAPTER is not supported for committed resources with D3D12_TEXTURE_LAYOUT_GUID. Use CreatePlacedResource on a cross-adapter shared heap instead.`
- `0x1800e68b6`: `When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource dimension must be D3D12_RESOURCE_DIMENSION_TEXTURE2D.`
- `0x1800e68ca`: `When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource layout must be D3D12_TEXTURE_LAYOUT_ROW_MAJOR.`
- `0x1800e692c`: `When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource format must be displayable (D3D12_FORMAT_SUPPORT1_DISPLAY or D3D12_FORMAT_SUPPORT2_DISPLAYABLE).  To use other formats, use CreatePlacedResource instead.`

## pseudocode

```c
__int64 __fastcall ValidateCreateCommittedResource<enum D3D12_BARRIER_LAYOUT>(
        struct TDebugOutputFunctor *a1,
        struct DeviceValidationInfo *a2,
        __int64 a3,
        enum D3D12_HEAP_FLAGS a4,
        enum D3D12_RESOURCE_DIMENSION *a5,
        unsigned int a6,
        struct D3D12_CLEAR_VALUE *a7,
        unsigned int a8,
        unsigned int a9,
        enum DXGI_FORMAT *a10,
        unsigned __int64 a11)
{
  __int64 result; // rax
  struct TDebugOutputFunctor *v16; // rcx
  const char *v17; // r8
  __int64 v18; // rdx
  int v19; // eax
  bool v20; // zf
  int v21; // r14d
  unsigned __int64 v22; // r9
  int v23; // [rsp+50h] [rbp-51h] BYREF
  __int64 v24; // [rsp+54h] [rbp-4Dh]
  _BYTE v25[24]; // [rsp+60h] [rbp-41h] BYREF
  int v26; // [rsp+78h] [rbp-29h]
  __int64 v27; // [rsp+80h] [rbp-21h]
  enum D3D12_HEAP_FLAGS v28; // [rsp+88h] [rbp-19h]

  *(__m128i *)v25 = _mm_load_si128((const __m128i *)&_xmm);
  *(_DWORD *)&v25[16] = 638;
  *(_DWORD *)&v25[20] = 640;
  v26 = 1363;
  result = ValidateHeapPropertiesAndFlags(
             a1,
             a2,
             (const struct D3D12_HEAP_PROPERTIES *)a3,
             a4,
             (const struct HeapValidationIDs *)v25,
             1,
             a8);
  if ( (int)result < 0 )
    return result;
  v16 = a1;
  if ( !a5 )
  {
    v17 = "pResourceDesc is NULL!";
    v18 = 700;
LABEL_4:
    TDebugOutputFunctor::operator()(v16, v18, v17);
    return 2147942487LL;
  }
  *(_QWORD *)v25 = 0;
  *(_OWORD *)&v25[8] = *(_OWORD *)a3;
  v26 = *(_DWORD *)(a3 + 16);
  v27 = 0;
  v28 = a4;
  result = ValidateHeapAndResourceCreation(
             a1,
             (enum D3D_FEATURE_LEVEL *)a2,
             (const struct CD3DX12_HEAP_DESC *)v25,
             0,
             a5,
             a7,
             a9,
             a10,
             a11);
  if ( (int)result < 0 )
    return result;
  v19 = *((_DWORD *)a5 + 12);
  if ( *a5 == D3D12_RESOURCE_DIMENSION_BUFFER )
  {
    v20 = a6 == -1;
  }
  else
  {
    if ( (v19 & 0x20) == 0 )
      goto LABEL_10;
    v20 = a6 == 0;
  }
  if ( !v20 )
    return 2147942487LL;
LABEL_10:
  result = ValidateResourceStateCore(a1, a6, *(unsigned int *)a5, *((unsigned int *)a5 + 9), v19, a2);
  if ( (int)result >= 0 )
  {
    if ( (a4 & 0x20) != 0 )
    {
      if ( *((_DWORD *)a5 + 11) == 4 )
      {
        v17 = "D3D12_RESOURCE_FLAG_ALLOW_CROSS_ADAPTER is not supported for committed resources with D3D12_TEXTURE_LAYOUT"
              "_GUID. Use CreatePlacedResource on a cross-adapter shared heap instead.";
LABEL_14:
        v18 = 724;
LABEL_15:
        v16 = a1;
        goto LABEL_4;
      }
      if ( *a5 != D3D12_RESOURCE_DIMENSION_TEXTURE2D )
      {
        v17 = "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource dimension must b"
              "e D3D12_RESOURCE_DIMENSION_TEXTURE2D.";
        v18 = 720;
        goto LABEL_15;
      }
      if ( *((_DWORD *)a5 + 11) != 1 )
      {
        v17 = "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource layout must be D"
              "3D12_TEXTURE_LAYOUT_ROW_MAJOR.";
        goto LABEL_14;
      }
      v24 = 0;
      v23 = *((_DWORD *)a5 + 8);
      v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *))(**((_QWORD **)a2 + 83) + 104LL))(
              *((_QWORD *)a2 + 83),
              3,
              &v23);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) )
      {
        if ( v21 < 0 || (v24 & 0x80000) == 0 && (v24 & 0x1000000000000LL) == 0 )
        {
          v17 = "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource format must be"
                " displayable (D3D12_FORMAT_SUPPORT1_DISPLAY or D3D12_FORMAT_SUPPORT2_DISPLAYABLE).  To use other formats"
                ", use CreatePlacedResource instead.";
LABEL_27:
          v18 = 738;
          goto LABEL_15;
        }
      }
      else if ( v21 < 0 || (v24 & 0x80000) == 0 )
      {
        v17 = "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPTER is set in CreateCommittedResource, the resource format must be d"
              "isplayable (D3D12_FORMAT_SUPPORT1_DISPLAY).  To use other formats, use CreatePlacedResource instead.";
        goto LABEL_27;
      }
    }
    if ( (a4 & 0x400) != 0 && (a5[12] & 4) == 0 )
    {
      v17 = "When D3D12_HEAP_FLAG_ALLOW_SHADER_ATOMICS is set in CreateCommittedResource, the resource flags must contain"
            " D3D12_RESOURCE_FLAG_ALLOW_UNORDERED_ACCESS. Otherwise, it suggests a waste of a constrained system resource.";
      v18 = 640;
      goto LABEL_15;
    }
    if ( *a5 == D3D12_RESOURCE_DIMENSION_BUFFER )
    {
      v22 = *((_QWORD *)a5 + 2);
      if ( v22 > 0xFFFF0000 && *(_DWORD *)a3 != 1 && (*(_DWORD *)a3 != 4 || *(_DWORD *)(a3 + 4) != 1) )
        TDebugOutputFunctor::operator()(
          a1,
          1342,
          "D3D12_RESOURCE_DESC::Width is invalid for a CPU-visible buffer. The size is %I64u, and it must be less than %I64u.",
          v22,
          4294901760LL);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800e674c  push    rbp
0x1800e674e  push    rbx
0x1800e674f  push    rsi
0x1800e6750  push    rdi
0x1800e6751  push    r12
0x1800e6753  push    r13
0x1800e6755  push    r14
0x1800e6757  push    r15
0x1800e6759  lea     rbp, [rsp-7]
0x1800e675e  sub     rsp, 0A8h
0x1800e6765  mov     rax, cs:__security_cookie
0x1800e676c  xor     rax, rsp
0x1800e676f  mov     [rbp+3Fh+var_50], rax
0x1800e6773  mov     r15d, r9d
0x1800e6776  mov     rsi, r8
0x1800e6779  mov     r14, rdx
0x1800e677c  mov     rbx, rcx
0x1800e677f  mov     rdi, [rbp+3Fh+arg_20]
0x1800e6783  mov     r12, [rbp+3Fh+arg_30]
0x1800e6787  mov     r13, [rbp+3Fh+arg_48]
0x1800e678e  movdqa  xmm0, cs:__xmm@0000027f0000027d0000027c0000027b
0x1800e6796  movdqu  [rbp+3Fh+var_80], xmm0
0x1800e679b  mov     [rbp+3Fh+var_70], 27Eh
0x1800e67a2  mov     [rbp+3Fh+var_6C], 280h
0x1800e67a9  mov     [rbp+3Fh+var_68], 553h
0x1800e67b0  mov     eax, [rbp+3Fh+arg_38]
0x1800e67b6  mov     [rsp+0E0h+var_B0], eax; unsigned int
0x1800e67ba  mov     byte ptr [rsp+0E0h+var_B8], 1; bool
0x1800e67bf  lea     rax, [rbp+3Fh+var_80]
0x1800e67c3  mov     [rsp+0E0h+var_C0], rax; struct HeapValidationIDs *
0x1800e67c8  call    ?ValidateHeapPropertiesAndFlags@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@PEBUD3D12_HEAP_PROPERTIES@@W4D3D12_HEAP_FLAGS@@AEBUHeapValidationIDs@@_NI@Z; ValidateHeapPropertiesAndFlags(TDebugOutputFunctor &,DeviceValidationInfo const &,D3D12_HEAP_PROPERTIES const *,D3D12_HEAP_FLAGS,HeapValidationIDs const &,bool,uint)
0x1800e67cd  test    eax, eax
0x1800e67cf  js      loc_1800E69B2
0x1800e67d5  mov     rcx, rbx; struct TDebugOutputFunctor *
0x1800e67d8  test    rdi, rdi
0x1800e67db  jnz     short loc_1800E67F8
0x1800e67dd  lea     r8, aPresourcedescI; "pResourceDesc is NULL!"
0x1800e67e4  mov     edx, 2BCh
0x1800e67e9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800e67ee  mov     eax, 80070057h
0x1800e67f3  jmp     loc_1800E69B2
0x1800e67f8  mov     qword ptr [rbp+3Fh+var_80], 0
0x1800e6800  movups  xmm0, xmmword ptr [rsi]
0x1800e6803  movups  [rbp+3Fh+var_80+8], xmm0
0x1800e6807  mov     eax, [rsi+10h]
0x1800e680a  mov     [rbp+3Fh+var_68], eax
0x1800e680d  mov     [rbp+3Fh+var_60], 0
0x1800e6815  mov     [rbp+3Fh+var_58], r15d
0x1800e6819  mov     rax, [rbp+3Fh+arg_50]
0x1800e6820  mov     [rsp+0E0h+var_A0], rax; unsigned __int64
0x1800e6825  mov     [rsp+0E0h+var_A8], r13; enum DXGI_FORMAT *
0x1800e682a  mov     eax, [rbp+3Fh+arg_40]
0x1800e6830  mov     [rsp+0E0h+var_B0], eax; unsigned int
0x1800e6834  mov     [rsp+0E0h+var_B8], r12; struct D3D12_CLEAR_VALUE *
0x1800e6839  mov     [rsp+0E0h+var_C0], rdi; enum D3D12_RESOURCE_DIMENSION *
0x1800e683e  xor     r9d, r9d; unsigned __int64
0x1800e6841  lea     r8, [rbp+3Fh+var_80]; struct CD3DX12_HEAP_DESC *
0x1800e6845  mov     rdx, r14; struct DeviceValidationInfo *
0x1800e6848  call    ?ValidateHeapAndResourceCreation@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@AEBUCD3DX12_HEAP_DESC@@_KAEBUCD3DX12_RESOURCE_DESC2@@PEBUD3D12_CLEAR_VALUE@@IPEBW4DXGI_FORMAT@@3@Z; ValidateHeapAndResourceCreation(TDebugOutputFunctor &,DeviceValidationInfo const &,CD3DX12_HEAP_DESC const &,unsigned __int64,CD3DX12_RESOURCE_DESC2 const &,D3D12_CLEAR_VALUE const *,uint,DXGI_FORMAT const *,unsigned __int64)
0x1800e684d  test    eax, eax
0x1800e684f  js      loc_1800E69B2
0x1800e6855  mov     eax, [rdi+30h]
0x1800e6858  mov     edx, [rbp+3Fh+arg_28]
0x1800e685b  cmp     dword ptr [rdi], 1
0x1800e685e  jnz     short loc_1800E68A9
0x1800e6860  cmp     edx, 0FFFFFFFFh
0x1800e6863  jnz     short loc_1800E67EE
0x1800e6865  mov     [rsp+0E0h+var_B8], r14
0x1800e686a  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800e686e  mov     r9d, [rdi+24h]
0x1800e6872  mov     r8d, [rdi]
0x1800e6875  mov     rcx, rbx
0x1800e6878  call    ?ValidateResourceStateCore@@YAJAEAUTDebugOutputFunctor@@W4D3D12_BARRIER_LAYOUT@@W4D3D12_RESOURCE_DIMENSION@@IW4D3D12_RESOURCE_FLAGS@@AEBUDeviceValidationInfo@@W4D3D12_HEAP_TYPE@@@Z; ValidateResourceStateCore(TDebugOutputFunctor &,D3D12_BARRIER_LAYOUT,D3D12_RESOURCE_DIMENSION,uint,D3D12_RESOURCE_FLAGS,DeviceValidationInfo const &,D3D12_HEAP_TYPE)
0x1800e687d  test    eax, eax
0x1800e687f  js      loc_1800E69B2
0x1800e6885  test    r15b, 20h
0x1800e6889  jz      loc_1800E6954
0x1800e688f  cmp     dword ptr [rdi+2Ch], 4
0x1800e6893  jnz     short loc_1800E68B1
0x1800e6895  lea     r8, aD3d12ResourceF_11; "D3D12_RESOURCE_FLAG_ALLOW_CROSS_ADAPTER"...
0x1800e689c  mov     edx, 2D4h
0x1800e68a1  mov     rcx, rbx
0x1800e68a4  jmp     loc_1800E67E9
0x1800e68a9  test    al, 20h
0x1800e68ab  jz      short loc_1800E6865
0x1800e68ad  test    edx, edx
0x1800e68af  jmp     short loc_1800E6863
0x1800e68b1  cmp     dword ptr [rdi], 3
0x1800e68b4  jz      short loc_1800E68C4
0x1800e68b6  lea     r8, aWhenD3d12HeapF_3; "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPT"...
0x1800e68bd  mov     edx, 2D0h
0x1800e68c2  jmp     short loc_1800E68A1
0x1800e68c4  cmp     dword ptr [rdi+2Ch], 1
0x1800e68c8  jz      short loc_1800E68D3
0x1800e68ca  lea     r8, aWhenD3d12HeapF_4; "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPT"...
0x1800e68d1  jmp     short loc_1800E689C
0x1800e68d3  mov     [rbp+3Fh+var_8C], 0
0x1800e68db  mov     eax, [rdi+20h]
0x1800e68de  mov     [rbp+3Fh+var_90], eax
0x1800e68e1  mov     rcx, [r14+298h]
0x1800e68e8  mov     rax, [rcx]
0x1800e68eb  mov     r9d, 0Ch
0x1800e68f1  lea     r8, [rbp+3Fh+var_90]
0x1800e68f5  lea     edx, [r9-9]
0x1800e68f9  mov     rax, [rax+68h]
0x1800e68fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6902  mov     r14d, eax
0x1800e6905  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12Displayable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable> `wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl(void)'::`2'::impl
0x1800e690c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(void)
0x1800e6911  test    al, al
0x1800e6913  jz      short loc_1800E693D
0x1800e6915  test    r14d, r14d
0x1800e6918  js      short loc_1800E692C
0x1800e691a  test    dword ptr [rbp+3Fh+var_8C], 80000h
0x1800e6921  jnz     short loc_1800E6954
0x1800e6923  test    dword ptr [rbp+3Fh+var_8C+4], 10000h
0x1800e692a  jnz     short loc_1800E6954
0x1800e692c  lea     r8, aWhenD3d12HeapF_0; "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPT"...
0x1800e6933  mov     edx, 2E2h
0x1800e6938  jmp     loc_1800E68A1
0x1800e693d  test    r14d, r14d
0x1800e6940  js      short loc_1800E694B
0x1800e6942  test    dword ptr [rbp+3Fh+var_8C], 80000h
0x1800e6949  jnz     short loc_1800E6954
0x1800e694b  lea     r8, aWhenD3d12HeapF; "When D3D12_HEAP_FLAG_SHARED_CROSS_ADAPT"...
0x1800e6952  jmp     short loc_1800E6933
0x1800e6954  bt      r15d, 0Ah
0x1800e6959  jnb     short loc_1800E6972
0x1800e695b  test    byte ptr [rdi+30h], 4
0x1800e695f  jnz     short loc_1800E6972
0x1800e6961  lea     r8, aWhenD3d12HeapF_1; "When D3D12_HEAP_FLAG_ALLOW_SHADER_ATOMI"...
0x1800e6968  mov     edx, 280h
0x1800e696d  jmp     loc_1800E68A1
0x1800e6972  cmp     dword ptr [rdi], 1
0x1800e6975  jnz     short loc_1800E69B0
0x1800e6977  mov     r9, [rdi+10h]
0x1800e697b  mov     edx, 0FFFF0000h
0x1800e6980  cmp     r9, rdx
0x1800e6983  jbe     short loc_1800E69B0
0x1800e6985  mov     ecx, [rsi]
0x1800e6987  sub     ecx, 1
0x1800e698a  jz      short loc_1800E69B0
0x1800e698c  cmp     ecx, 3
0x1800e698f  jnz     short loc_1800E6997
0x1800e6991  cmp     dword ptr [rsi+4], 1
0x1800e6995  jz      short loc_1800E69B0
0x1800e6997  mov     [rsp+0E0h+var_C0], rdx
0x1800e699c  lea     r8, aD3d12ResourceD_21; "D3D12_RESOURCE_DESC::Width is invalid f"...
0x1800e69a3  mov     edx, 53Eh
0x1800e69a8  mov     rcx, rbx
0x1800e69ab  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1800e69b0  xor     eax, eax
0x1800e69b2  mov     rcx, [rbp+3Fh+var_50]
0x1800e69b6  xor     rcx, rsp; StackCookie
0x1800e69b9  call    __security_check_cookie
0x1800e69be  add     rsp, 0A8h
0x1800e69c5  pop     r15
0x1800e69c7  pop     r14
0x1800e69c9  pop     r13
0x1800e69cb  pop     r12
0x1800e69cd  pop     rdi
0x1800e69ce  pop     rsi
0x1800e69cf  pop     rbx
0x1800e69d0  pop     rbp
0x1800e69d1  retn
```
