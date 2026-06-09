# GetEffectPackDevNodeId(_GUID,ushort * *)

- ea: `0x140018340`
- end: `0x1400184c0`
- name: `?GetEffectPackDevNodeId@@YAJU_GUID@@PEAPEAG@Z`
- size: `384`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140052090`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x140018340`
- `0x1400184c8`
- `0x14001d630`
- `0x14005d0e0`
- `0x1400b5010`

## import_xrefs

- `MMDevAPI!__imp_MMDeviceCreateRegistryPropertyStore` at `0x1400183cb`
- `MMDevAPI!__imp_MMDeviceCreateRegistryPropertyStore` at `0x1400183cb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14001844a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140018488`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14001844a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140018488`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetEffectPackDevNodeId(struct _GUID *a1, unsigned __int16 **a2)
{
  int EffectPackRegistryPath; // eax
  unsigned int v4; // ebx
  int RegistryPropertyStore; // eax
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  int v12[2]; // [rsp+20h] [rbp-E0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h]
  struct _GUID v15; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v16[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  v15 = *a1;
  EffectPackRegistryPath = GetEffectPackRegistryPath(&v15, (unsigned __int64)a2, v16);
  v4 = EffectPackRegistryPath;
  if ( EffectPackRegistryPath >= 0 )
  {
    *(_QWORD *)v12 = 0;
    RegistryPropertyStore = MMDeviceCreateRegistryPropertyStore(v16, 131097, v12);
    v4 = RegistryPropertyStore;
    if ( RegistryPropertyStore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\effectpackutil.cpp",
        (const char *)(unsigned int)RegistryPropertyStore,
        v12[0]);
LABEL_14:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v12);
      return v4;
    }
    *(_OWORD *)pvar = 0;
    v14 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, PROPVARIANT *))(**(_QWORD **)v12 + 40LL))(
           *(_QWORD *)v12,
           PKEY_FX_ObjectId,
           pvar);
    v4 = v6;
    if ( v6 >= 0 )
    {
      if ( LOWORD(pvar[0]) != 31 )
      {
        v4 = -2147467259;
        v10 = 2147500037LL;
        v9 = 29;
        goto LABEL_8;
      }
      v6 = _AllocString<CTCoAllocPolicy>(v8, v7, (__int64 *)pvar[1], a2);
      v4 = v6;
      if ( v6 >= 0 )
      {
        PropVariantClear(pvar);
        v4 = 0;
        goto LABEL_14;
      }
      v9 = 30;
    }
    else
    {
      v9 = 28;
    }
    v10 = (unsigned int)v6;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\effectpackutil.cpp",
      (const char *)v10,
      v12[0]);
    PropVariantClear(pvar);
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\effectpackutil.cpp",
    (const char *)(unsigned int)EffectPackRegistryPath,
    v12[0]);
  return v4;
}

```

## disassembly

```asm
0x140018340  mov     [rsp-8+arg_10], rbx
0x140018345  mov     [rsp-8+arg_18], rdi
0x14001834a  push    rbp
0x14001834b  lea     rbp, [rsp-170h]
0x140018353  sub     rsp, 270h
0x14001835a  mov     rax, cs:__security_cookie
0x140018361  xor     rax, rsp
0x140018364  mov     [rbp+170h+var_10], rax
0x14001836b  mov     rdi, rdx
0x14001836e  mov     qword ptr [rdx], 0
0x140018375  movaps  xmm0, xmmword ptr [rcx]
0x140018378  movdqa  xmmword ptr [rsp+270h+var_230.Data1], xmm0
0x14001837e  lea     r8, [rsp+270h+var_220]; unsigned __int16 *
0x140018383  lea     rcx, [rsp+270h+var_230]; struct _GUID
0x140018388  call    ?GetEffectPackRegistryPath@@YAJU_GUID@@_KPEAG@Z; GetEffectPackRegistryPath(_GUID,unsigned __int64,ushort *)
0x14001838d  mov     ebx, eax
0x14001838f  test    eax, eax
0x140018391  jns     short loc_1400183B3
0x140018393  mov     rcx, [rbp+178h]; this
0x14001839a  mov     r9d, eax; char *
0x14001839d  lea     r8, aAvcoreAudiocor_72; "avcore\\audiocore\\server\\lib\\audioen"...
0x1400183a4  mov     edx, 16h; void *
0x1400183a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400183ae  jmp     loc_14001849A
0x1400183b3  mov     qword ptr [rsp+270h+var_250], 0; int
0x1400183bc  lea     r8, [rsp+270h+var_250]
0x1400183c1  mov     edx, 20019h
0x1400183c6  lea     rcx, [rsp+270h+var_220]
0x1400183cb  call    cs:__imp_MMDeviceCreateRegistryPropertyStore
0x1400183d1  mov     ebx, eax
0x1400183d3  test    eax, eax
0x1400183d5  jns     short loc_1400183F7
0x1400183d7  mov     rcx, [rbp+178h]; this
0x1400183de  mov     r9d, eax; char *
0x1400183e1  lea     r8, aAvcoreAudiocor_72; "avcore\\audiocore\\server\\lib\\audioen"...
0x1400183e8  mov     edx, 19h; void *
0x1400183ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400183f2  jmp     loc_140018490
0x1400183f7  xorps   xmm0, xmm0
0x1400183fa  xor     eax, eax
0x1400183fc  movups  xmmword ptr [rsp+270h+pvar], xmm0
0x140018401  mov     [rsp+270h+var_238], rax
0x140018406  mov     rcx, qword ptr [rsp+270h+var_250]
0x14001840b  mov     rax, [rcx]
0x14001840e  lea     r8, [rsp+270h+pvar]
0x140018413  lea     rdx, PKEY_FX_ObjectId
0x14001841a  mov     rax, [rax+28h]
0x14001841e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018423  mov     ebx, eax
0x140018425  test    eax, eax
0x140018427  jns     short loc_140018452
0x140018429  mov     edx, 1Ch; void *
0x14001842e  mov     r9d, eax; char *
0x140018431  mov     rcx, [rbp+178h]; this
0x140018438  lea     r8, aAvcoreAudiocor_72; "avcore\\audiocore\\server\\lib\\audioen"...
0x14001843f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018444  nop
0x140018445  lea     rcx, [rsp+270h+pvar]; pvar
0x14001844a  call    cs:__imp_PropVariantClear
0x140018450  jmp     short loc_140018490
0x140018452  cmp     word ptr [rsp+270h+pvar], 1Fh
0x140018458  jz      short loc_140018469
0x14001845a  mov     ebx, 80004005h
0x14001845f  mov     r9d, ebx
0x140018462  mov     edx, 1Dh
0x140018467  jmp     short loc_140018431
0x140018469  mov     r9, rdi
0x14001846c  mov     r8, [rsp+270h+pvar+8]
0x140018471  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x140018476  mov     ebx, eax
0x140018478  test    eax, eax
0x14001847a  jns     short loc_140018483
0x14001847c  mov     edx, 1Eh
0x140018481  jmp     short loc_14001842E
0x140018483  lea     rcx, [rsp+270h+pvar]; pvar
0x140018488  call    cs:__imp_PropVariantClear
0x14001848e  xor     ebx, ebx
0x140018490  lea     rcx, [rsp+270h+var_250]
0x140018495  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14001849a  mov     eax, ebx
0x14001849c  mov     rcx, [rbp+170h+var_10]
0x1400184a3  xor     rcx, rsp; StackCookie
0x1400184a6  call    __security_check_cookie
0x1400184ab  lea     r11, [rsp+270h+var_s0]
0x1400184b3  mov     rbx, [r11+20h]
0x1400184b7  mov     rdi, [r11+28h]
0x1400184bb  mov     rsp, r11
0x1400184be  pop     rbp
0x1400184bf  retn
```
