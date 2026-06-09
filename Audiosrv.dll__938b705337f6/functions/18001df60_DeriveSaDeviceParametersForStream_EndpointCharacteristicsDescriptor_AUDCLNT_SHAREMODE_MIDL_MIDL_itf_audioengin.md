# DeriveSaDeviceParametersForStream(EndpointCharacteristicsDescriptor *,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX *,__int64,SaDeviceParams * *)

- ea: `0x18001df60`
- end: `0x18001e1b1`
- name: `?DeriveSaDeviceParametersForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@3PEAUtWAVEFORMATEX@@4_JPEAPEAUSaDeviceParams@@@Z`
- size: `593`
- prototype: `__int64 __fastcall(struct EndpointCharacteristicsDescriptor *, enum _AUDCLNT_SHAREMODE, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct _GUID *, struct _GUID *, struct tWAVEFORMATEX *, struct tWAVEFORMATEX *Src, __int64, struct SaDeviceParams **)`
- caller_count: `6`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180073990`
- `0x1800b8c20`
- `0x1800c1ca4`
- `0x1800f76f4`
- `0x1800f7e20`
- `0x1800f97a0`

## callees

- `0x18001df60`
- `0x18001f258`
- `0x18003880c`
- `0x1800cfd9c`
- `0x1800d074c`
- `0x1800d0764`
- `0x1800e5af0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001e167`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001e167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e0a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e0a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e018`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0f7`

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
0x18001df60  mov     [rsp-40h+arg_0], rcx
0x18001df65  push    rbp
0x18001df66  push    rbx
0x18001df67  push    rsi
0x18001df68  push    rdi
0x18001df69  push    r12
0x18001df6b  push    r13
0x18001df6d  push    r14
0x18001df6f  push    r15
0x18001df71  mov     rbp, rsp
0x18001df74  sub     rsp, 78h
0x18001df78  mov     r13, r9
0x18001df7b  mov     r15d, r8d
0x18001df7e  mov     rax, rcx
0x18001df81  xor     ebx, ebx
0x18001df83  mov     [rbp+var_30], rbx
0x18001df87  mov     [rbp+var_38], rbx
0x18001df8b  movaps  xmm0, xmmword ptr [r9]
0x18001df8f  lea     rcx, [rbp+var_38]
0x18001df93  lea     r8, [rbp+var_18]; struct _GUID
0x18001df97  movdqa  xmmword ptr [rbp+var_18.Data1], xmm0
0x18001df9c  xor     r9d, r9d; struct tWAVEFORMATEX **
0x18001df9f  mov     [rsp+78h+var_48], rcx; __int64 *
0x18001dfa4  cmp     edx, 1
0x18001dfa7  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001dfaa  jz      loc_18001E17F
0x18001dfb0  mov     [rsp+78h+var_50], r9; __int64 *
0x18001dfb5  mov     [rsp+78h+var_58], 0; struct tWAVEFORMATEX **
0x18001dfbe  mov     rcx, rax; struct EndpointCharacteristicsDescriptor *
0x18001dfc1  call    ?GetDeviceDefaults@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@3PEA_J4@Z; GetDeviceDefaults(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *,tWAVEFORMATEX * *,__int64 *,__int64 *)
0x18001dfc6  mov     r14d, eax
0x18001dfc9  test    eax, eax
0x18001dfcb  js      short loc_18001E03C
0x18001dfcd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001dfd4  mov     edi, 70h ; 'p'
0x18001dfd9  mov     ecx, edi; unsigned __int64
0x18001dfdb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001dfe0  mov     rbx, rax
0x18001dfe3  test    rax, rax
0x18001dfe6  jz      short loc_18001E055
0x18001dfe8  mov     r8d, edi; Size
0x18001dfeb  xor     edx, edx; Val
0x18001dfed  mov     rcx, rax; void *
0x18001dff0  call    memset_0
0x18001dff5  mov     [rbp+var_30], rbx
0x18001dff9  mov     rax, rbx
0x18001dffc  neg     rax
0x18001dfff  sbb     r14d, r14d
0x18001e002  not     r14d
0x18001e005  and     r14d, 8007000Eh
0x18001e00c  mov     esi, 0
0x18001e011  mov     edi, esi
0x18001e013  jge     short loc_18001E063
0x18001e015  mov     rcx, rdi; pv
0x18001e018  call    cs:__imp_CoTaskMemFree
0x18001e01e  nop
0x18001e01f  mov     rcx, rsi; pv
0x18001e022  call    cs:__imp_CoTaskMemFree
0x18001e028  test    r14d, r14d
0x18001e02b  js      short loc_18001E03C
0x18001e02d  mov     rcx, rbx
0x18001e030  xor     ebx, ebx
0x18001e032  mov     rax, [rbp+arg_40]
0x18001e039  mov     [rax], rcx
0x18001e03c  test    rbx, rbx
0x18001e03f  jnz     short loc_18001E059
0x18001e041  mov     eax, r14d
0x18001e044  add     rsp, 78h
0x18001e048  pop     r15
0x18001e04a  pop     r14
0x18001e04c  pop     r13
0x18001e04e  pop     r12
0x18001e050  pop     rdi
0x18001e051  pop     rsi
0x18001e052  pop     rbx
0x18001e053  pop     rbp
0x18001e054  retn
0x18001e055  xor     ebx, ebx
0x18001e057  jmp     short loc_18001DFF5
0x18001e059  mov     rcx, rbx; this
0x18001e05c  call    ??_GSaDeviceParams@@QEAAPEAXI@Z; SaDeviceParams::`scalar deleting destructor'(uint)
0x18001e061  jmp     short loc_18001E041
0x18001e063  mov     r14, [rbp+Src]
0x18001e067  movzx   r12d, word ptr [r14+10h]
0x18001e06c  lea     rcx, [r12+12h]; cb
0x18001e071  call    cs:__imp_CoTaskMemAlloc
0x18001e077  mov     rdi, rax
0x18001e07a  test    rax, rax
0x18001e07d  jz      loc_18001E172
0x18001e083  lea     r8, [r12+12h]; Size
0x18001e088  mov     rdx, r14; Src
0x18001e08b  mov     rcx, rax; void *
0x18001e08e  call    memcpy_0
0x18001e093  mov     r14, [rbp+arg_28]
0x18001e097  movzx   r12d, word ptr [r14+10h]
0x18001e09c  lea     rcx, [r12+12h]; cb
0x18001e0a1  call    cs:__imp_CoTaskMemAlloc
0x18001e0a7  mov     rsi, rax
0x18001e0aa  test    rax, rax
0x18001e0ad  jz      loc_18001E174
0x18001e0b3  lea     r8, [r12+12h]; Size
0x18001e0b8  mov     rdx, r14; Src
0x18001e0bb  mov     rcx, rax; void *
0x18001e0be  call    memcpy_0
0x18001e0c3  xor     r14d, r14d
0x18001e0c6  test    r14d, r14d
0x18001e0c9  js      loc_18001E015
0x18001e0cf  mov     [rbx+8], r15d
0x18001e0d3  mov     r14, rsi
0x18001e0d6  xor     esi, esi
0x18001e0d8  mov     [rbp+var_28], rsi
0x18001e0dc  mov     rcx, [rbx+10h]; pv
0x18001e0e0  call    cs:__imp_CoTaskMemFree
0x18001e0e6  mov     [rbx+10h], r14
0x18001e0ea  mov     r14, rdi
0x18001e0ed  xor     edi, edi
0x18001e0ef  mov     qword ptr [rbp+var_18.Data1], rdi
0x18001e0f3  mov     rcx, [rbx+18h]; pv
0x18001e0f7  call    cs:__imp_CoTaskMemFree
0x18001e0fd  mov     [rbx+18h], r14
0x18001e101  mov     rax, [rbp+arg_38]
0x18001e108  mov     [rbx+20h], rax
0x18001e10c  mov     rax, [rbp+var_38]
0x18001e110  mov     [rbx+28h], rax
0x18001e114  mov     rax, [rbp+arg_20]
0x18001e118  movaps  xmm0, xmmword ptr [rax]
0x18001e11b  movdqu  xmmword ptr [rbx+40h], xmm0
0x18001e120  movaps  xmm1, xmmword ptr [r13+0]
0x18001e125  movdqu  xmmword ptr [rbx+30h], xmm1
0x18001e12a  mov     rax, [rbp+arg_0]
0x18001e12e  mov     rax, [rax]
0x18001e131  mov     rcx, [rax+28h]
0x18001e135  mov     rax, [rcx]
0x18001e138  mov     rdx, rbx
0x18001e13b  mov     rax, [rax+28h]
0x18001e13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e144  mov     r14d, eax
0x18001e147  lea     rax, WPP_GLOBAL_Control
0x18001e14e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e155  cmp     rcx, rax
0x18001e158  jz      short loc_18001E163
0x18001e15a  test    dword ptr [rcx+1Ch], 100h
0x18001e161  jnz     short loc_18001E190
0x18001e163  lea     rcx, [rbx+50h]; pguid
0x18001e167  call    cs:__imp_CoCreateGuid
0x18001e16d  jmp     loc_18001E015
0x18001e172  xor     edi, edi
0x18001e174  mov     r14d, 8007000Eh
0x18001e17a  jmp     loc_18001E0C6
0x18001e17f  lea     rcx, [rbp+arg_38]
0x18001e186  mov     [rsp+78h+var_50], rcx
0x18001e18b  jmp     loc_18001DFB5
0x18001e190  cmp     byte ptr [rcx+19h], 4
0x18001e194  jb      short loc_18001E163
0x18001e196  mov     rax, [rbp+arg_38]
0x18001e19d  mov     [rsp+78h+var_58], rax
0x18001e1a2  mov     r9d, r15d
0x18001e1a5  mov     rcx, [rcx+10h]
0x18001e1a9  call    WPP_SF_di
0x18001e1ae  jmp     short loc_18001E163
```
