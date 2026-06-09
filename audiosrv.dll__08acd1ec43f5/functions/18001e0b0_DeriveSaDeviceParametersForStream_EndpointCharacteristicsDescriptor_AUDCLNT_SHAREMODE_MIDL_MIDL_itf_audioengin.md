# DeriveSaDeviceParametersForStream(EndpointCharacteristicsDescriptor *,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX *,__int64,SaDeviceParams * *)

- ea: `0x18001e0b0`
- end: `0x18001e301`
- name: `?DeriveSaDeviceParametersForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@3PEAUtWAVEFORMATEX@@4_JPEAPEAUSaDeviceParams@@@Z`
- size: `593`
- prototype: `__int64 __fastcall(struct EndpointCharacteristicsDescriptor *, enum _AUDCLNT_SHAREMODE, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct _GUID *, struct _GUID *, struct tWAVEFORMATEX *, struct tWAVEFORMATEX *Src, __int64, struct SaDeviceParams **)`
- caller_count: `6`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180073490`
- `0x1800b70d0`
- `0x1800c0154`
- `0x1800f7984`
- `0x1800f80b0`
- `0x1800f9a30`

## callees

- `0x18001e0b0`
- `0x18001f3a8`
- `0x18003896c`
- `0x1800cddac`
- `0x1800ce75c`
- `0x1800ce774`
- `0x1800e5370`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001e2b7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001e2b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e1c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e1f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e1c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e1f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e230`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e230`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e247`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeriveSaDeviceParametersForStream(
        EffectPack **a1,
        enum _AUDCLNT_SHAREMODE a2,
        unsigned int a3,
        struct _GUID *a4,
        struct _GUID *a5,
        struct tWAVEFORMATEX *a6,
        struct tWAVEFORMATEX *Src,
        __int64 a8,
        struct SaDeviceParams **a9)
{
  void *v11; // rbx
  int DeviceDefaults; // eax
  unsigned int v13; // edx
  signed int v14; // r14d
  void *v15; // rax
  void *v16; // rsi
  void *v17; // rdi
  struct SaDeviceParams *v18; // rcx
  __int64 cbSize; // r12
  void *v21; // rax
  __int64 v22; // r12
  void *v23; // rax
  void *v24; // r14
  void *v25; // r14
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // [rsp+40h] [rbp-38h] BYREF
  void *v29; // [rsp+48h] [rbp-30h]
  __int64 v30; // [rsp+50h] [rbp-28h]
  struct _GUID v31; // [rsp+60h] [rbp-18h] BYREF

  v11 = 0;
  v29 = 0;
  v28 = 0;
  v31 = *a4;
  if ( a2 == AUDCLNT_SHAREMODE_EXCLUSIVE )
    DeviceDefaults = GetDeviceDefaults(a1, a3, &v31, 0, 0, &a8, &v28);
  else
    DeviceDefaults = GetDeviceDefaults(a1, a3, &v31, 0, 0, 0, &v28);
  v14 = DeviceDefaults;
  if ( DeviceDefaults < 0 )
    goto LABEL_9;
  v15 = operator new[](0x70u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v15;
  if ( v15 )
    memset_0(v15, 0, 0x70u);
  else
    v11 = 0;
  v29 = v11;
  v14 = v11 == 0 ? 0x8007000E : 0;
  v16 = 0;
  v17 = 0;
  if ( v11 )
  {
    cbSize = Src->cbSize;
    v21 = CoTaskMemAlloc(cbSize + 18);
    v17 = v21;
    if ( v21 )
    {
      memcpy_0(v21, Src, cbSize + 18);
      v22 = a6->cbSize;
      v23 = CoTaskMemAlloc(v22 + 18);
      v16 = v23;
      if ( v23 )
      {
        memcpy_0(v23, a6, v22 + 18);
        v14 = 0;
        goto LABEL_16;
      }
    }
    else
    {
      v17 = 0;
    }
    v14 = -2147024882;
LABEL_16:
    if ( v14 >= 0 )
    {
      *((_DWORD *)v11 + 2) = a3;
      v24 = v16;
      v16 = 0;
      v30 = 0;
      CoTaskMemFree(*((LPVOID *)v11 + 2));
      *((_QWORD *)v11 + 2) = v24;
      v25 = v17;
      v17 = 0;
      *(_QWORD *)&v31.Data1 = 0;
      CoTaskMemFree(*((LPVOID *)v11 + 3));
      *((_QWORD *)v11 + 3) = v25;
      *((_QWORD *)v11 + 4) = a8;
      *((_QWORD *)v11 + 5) = v28;
      *((struct _GUID *)v11 + 4) = *a5;
      *((struct _GUID *)v11 + 3) = *a4;
      v14 = (*(__int64 (__fastcall **)(_QWORD, void *))(**((_QWORD **)*a1 + 5) + 40LL))(*((_QWORD *)*a1 + 5), v11);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_di(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, v27, a3, a8);
      }
      CoCreateGuid((GUID *)v11 + 5);
    }
  }
  CoTaskMemFree(v17);
  CoTaskMemFree(v16);
  if ( v14 >= 0 )
  {
    v18 = (struct SaDeviceParams *)v11;
    v11 = 0;
    *a9 = v18;
  }
LABEL_9:
  if ( v11 )
    SaDeviceParams::`scalar deleting destructor'((SaDeviceParams *)v11, v13);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001e0b0  mov     [rsp-40h+arg_0], rcx
0x18001e0b5  push    rbp
0x18001e0b6  push    rbx
0x18001e0b7  push    rsi
0x18001e0b8  push    rdi
0x18001e0b9  push    r12
0x18001e0bb  push    r13
0x18001e0bd  push    r14
0x18001e0bf  push    r15
0x18001e0c1  mov     rbp, rsp
0x18001e0c4  sub     rsp, 78h
0x18001e0c8  mov     r13, r9
0x18001e0cb  mov     r15d, r8d
0x18001e0ce  mov     rax, rcx
0x18001e0d1  xor     ebx, ebx
0x18001e0d3  mov     [rbp+var_30], rbx
0x18001e0d7  mov     [rbp+var_38], rbx
0x18001e0db  movaps  xmm0, xmmword ptr [r9]
0x18001e0df  lea     rcx, [rbp+var_38]
0x18001e0e3  lea     r8, [rbp+var_18]; struct _GUID
0x18001e0e7  movdqa  xmmword ptr [rbp+var_18.Data1], xmm0
0x18001e0ec  xor     r9d, r9d; struct tWAVEFORMATEX **
0x18001e0ef  mov     [rsp+78h+var_48], rcx; __int64 *
0x18001e0f4  cmp     edx, 1
0x18001e0f7  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001e0fa  jz      loc_18001E2CF
0x18001e100  mov     [rsp+78h+var_50], r9; __int64 *
0x18001e105  mov     [rsp+78h+var_58], 0; struct tWAVEFORMATEX **
0x18001e10e  mov     rcx, rax; struct EndpointCharacteristicsDescriptor *
0x18001e111  call    ?GetDeviceDefaults@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@3PEA_J4@Z; GetDeviceDefaults(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *,tWAVEFORMATEX * *,__int64 *,__int64 *)
0x18001e116  mov     r14d, eax
0x18001e119  test    eax, eax
0x18001e11b  js      short loc_18001E18C
0x18001e11d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e124  mov     edi, 70h ; 'p'
0x18001e129  mov     ecx, edi; unsigned __int64
0x18001e12b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001e130  mov     rbx, rax
0x18001e133  test    rax, rax
0x18001e136  jz      short loc_18001E1A5
0x18001e138  mov     r8d, edi; Size
0x18001e13b  xor     edx, edx; Val
0x18001e13d  mov     rcx, rax; void *
0x18001e140  call    memset_0
0x18001e145  mov     [rbp+var_30], rbx
0x18001e149  mov     rax, rbx
0x18001e14c  neg     rax
0x18001e14f  sbb     r14d, r14d
0x18001e152  not     r14d
0x18001e155  and     r14d, 8007000Eh
0x18001e15c  mov     esi, 0
0x18001e161  mov     edi, esi
0x18001e163  jge     short loc_18001E1B3
0x18001e165  mov     rcx, rdi; pv
0x18001e168  call    cs:__imp_CoTaskMemFree
0x18001e16e  nop
0x18001e16f  mov     rcx, rsi; pv
0x18001e172  call    cs:__imp_CoTaskMemFree
0x18001e178  test    r14d, r14d
0x18001e17b  js      short loc_18001E18C
0x18001e17d  mov     rcx, rbx
0x18001e180  xor     ebx, ebx
0x18001e182  mov     rax, [rbp+arg_40]
0x18001e189  mov     [rax], rcx
0x18001e18c  test    rbx, rbx
0x18001e18f  jnz     short loc_18001E1A9
0x18001e191  mov     eax, r14d
0x18001e194  add     rsp, 78h
0x18001e198  pop     r15
0x18001e19a  pop     r14
0x18001e19c  pop     r13
0x18001e19e  pop     r12
0x18001e1a0  pop     rdi
0x18001e1a1  pop     rsi
0x18001e1a2  pop     rbx
0x18001e1a3  pop     rbp
0x18001e1a4  retn
0x18001e1a5  xor     ebx, ebx
0x18001e1a7  jmp     short loc_18001E145
0x18001e1a9  mov     rcx, rbx; this
0x18001e1ac  call    ??_GSaDeviceParams@@QEAAPEAXI@Z; SaDeviceParams::`scalar deleting destructor'(uint)
0x18001e1b1  jmp     short loc_18001E191
0x18001e1b3  mov     r14, [rbp+Src]
0x18001e1b7  movzx   r12d, word ptr [r14+10h]
0x18001e1bc  lea     rcx, [r12+12h]; cb
0x18001e1c1  call    cs:__imp_CoTaskMemAlloc
0x18001e1c7  mov     rdi, rax
0x18001e1ca  test    rax, rax
0x18001e1cd  jz      loc_18001E2C2
0x18001e1d3  lea     r8, [r12+12h]; Size
0x18001e1d8  mov     rdx, r14; Src
0x18001e1db  mov     rcx, rax; void *
0x18001e1de  call    memcpy_0
0x18001e1e3  mov     r14, [rbp+arg_28]
0x18001e1e7  movzx   r12d, word ptr [r14+10h]
0x18001e1ec  lea     rcx, [r12+12h]; cb
0x18001e1f1  call    cs:__imp_CoTaskMemAlloc
0x18001e1f7  mov     rsi, rax
0x18001e1fa  test    rax, rax
0x18001e1fd  jz      loc_18001E2C4
0x18001e203  lea     r8, [r12+12h]; Size
0x18001e208  mov     rdx, r14; Src
0x18001e20b  mov     rcx, rax; void *
0x18001e20e  call    memcpy_0
0x18001e213  xor     r14d, r14d
0x18001e216  test    r14d, r14d
0x18001e219  js      loc_18001E165
0x18001e21f  mov     [rbx+8], r15d
0x18001e223  mov     r14, rsi
0x18001e226  xor     esi, esi
0x18001e228  mov     [rbp+var_28], rsi
0x18001e22c  mov     rcx, [rbx+10h]; pv
0x18001e230  call    cs:__imp_CoTaskMemFree
0x18001e236  mov     [rbx+10h], r14
0x18001e23a  mov     r14, rdi
0x18001e23d  xor     edi, edi
0x18001e23f  mov     qword ptr [rbp+var_18.Data1], rdi
0x18001e243  mov     rcx, [rbx+18h]; pv
0x18001e247  call    cs:__imp_CoTaskMemFree
0x18001e24d  mov     [rbx+18h], r14
0x18001e251  mov     rax, [rbp+arg_38]
0x18001e258  mov     [rbx+20h], rax
0x18001e25c  mov     rax, [rbp+var_38]
0x18001e260  mov     [rbx+28h], rax
0x18001e264  mov     rax, [rbp+arg_20]
0x18001e268  movaps  xmm0, xmmword ptr [rax]
0x18001e26b  movdqu  xmmword ptr [rbx+40h], xmm0
0x18001e270  movaps  xmm1, xmmword ptr [r13+0]
0x18001e275  movdqu  xmmword ptr [rbx+30h], xmm1
0x18001e27a  mov     rax, [rbp+arg_0]
0x18001e27e  mov     rax, [rax]
0x18001e281  mov     rcx, [rax+28h]
0x18001e285  mov     rax, [rcx]
0x18001e288  mov     rdx, rbx
0x18001e28b  mov     rax, [rax+28h]
0x18001e28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e294  mov     r14d, eax
0x18001e297  lea     rax, WPP_GLOBAL_Control
0x18001e29e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e2a5  cmp     rcx, rax
0x18001e2a8  jz      short loc_18001E2B3
0x18001e2aa  test    dword ptr [rcx+1Ch], 100h
0x18001e2b1  jnz     short loc_18001E2E0
0x18001e2b3  lea     rcx, [rbx+50h]; pguid
0x18001e2b7  call    cs:__imp_CoCreateGuid
0x18001e2bd  jmp     loc_18001E165
0x18001e2c2  xor     edi, edi
0x18001e2c4  mov     r14d, 8007000Eh
0x18001e2ca  jmp     loc_18001E216
0x18001e2cf  lea     rcx, [rbp+arg_38]
0x18001e2d6  mov     [rsp+78h+var_50], rcx
0x18001e2db  jmp     loc_18001E105
0x18001e2e0  cmp     byte ptr [rcx+19h], 4
0x18001e2e4  jb      short loc_18001E2B3
0x18001e2e6  mov     rax, [rbp+arg_38]
0x18001e2ed  mov     [rsp+78h+var_58], rax
0x18001e2f2  mov     r9d, r15d
0x18001e2f5  mov     rcx, [rcx+10h]
0x18001e2f9  call    WPP_SF_di
0x18001e2fe  jmp     short loc_18001E2B3
```
