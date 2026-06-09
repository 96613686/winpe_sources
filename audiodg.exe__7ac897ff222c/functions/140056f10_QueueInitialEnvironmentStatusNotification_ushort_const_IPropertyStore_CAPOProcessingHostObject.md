# QueueInitialEnvironmentStatusNotification(ushort const *,IPropertyStore *,CAPOProcessingHostObject *)

- ea: `0x140056f10`
- end: `0x1400571ae`
- name: `?QueueInitialEnvironmentStatusNotification@@YAJPEBGPEAUIPropertyStore@@PEAVCAPOProcessingHostObject@@@Z`
- size: `670`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IPropertyStore *, struct CAPOProcessingHostObject *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003d3b0`

## callees

- `0x140008124`
- `0x1400085bc`
- `0x14000c33c`
- `0x14000ec10`
- `0x14000f36c`
- `0x1400237ec`
- `0x140056f10`
- `0x14005d0e0`
- `0x14005d104`
- `0x14005d148`
- `0x14005e168`
- `0x140064c88`
- `0x1400ad1f0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140056fcf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140056fcf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140057122`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140057165`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140057122`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140057165`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall QueueInitialEnvironmentStatusNotification(
        const unsigned __int16 *a1,
        struct IPropertyStore *a2,
        struct _RTL_CRITICAL_SECTION *a3)
{
  BOOL v6; // esi
  __int64 v7; // rcx
  unsigned int i; // ebx
  _DWORD *v9; // rbx
  _DWORD *v10; // rdi
  unsigned int v11; // ebx
  _QWORD *v12; // rsi
  int v13; // eax
  __int64 v14; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  _BYTE v16[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct IPropertyStore *v17; // [rsp+38h] [rbp-C8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h]
  __int64 v20[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v21[2]; // [rsp+68h] [rbp-98h] BYREF
  char v22; // [rsp+78h] [rbp-88h]
  _BYTE v23[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v24; // [rsp+84h] [rbp-7Ch]
  _WORD v25[2044]; // [rsp+88h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10B8h] [rbp+FB8h]

  if ( !a2 )
    return 2147942487LL;
  v17 = a2;
  ((void (__fastcall *)(struct IPropertyStore *))a2->lpVtbl->AddRef)(a2);
  memset_0(v23, 0, 0x1000u);
  v6 = 0;
  v16[0] = 0;
  if ( (int)wil::wnf_query_nothrow__QueueInitialEnvironmentStatusNotification_::_2_::WnfPayload4k_(v7, v16, v23) >= 0
    && v16[0] )
  {
    for ( i = 0; i < v24; ++i )
    {
      if ( CompareStringOrdinal(a1, -1, &v25[57 * i], -1, 1) == 2 )
      {
        v6 = v25[57 * i + 56] != 0;
        break;
      }
    }
  }
  v9 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v16[0] = 0;
  v21[0] = v9;
  v21[1] = v16;
  v22 = 1;
  v10 = operator new(0x18u);
  *(_OWORD *)v10 = 0;
  v10[2] = 1;
  v10[3] = 1;
  *(_QWORD *)v10 = off_1400BA740;
  *((_QWORD *)v10 + 2) = v9;
  v20[0] = (__int64)v9;
  v20[1] = (__int64)v10;
  v22 = 0;
  std::_Temporary_owner_del_APO_NOTIFICATION____lambda_dfcad306b8fb141de82a0500d5a576ce___::__Temporary_owner_del_APO_NOTIFICATION____lambda_dfcad306b8fb141de82a0500d5a576ce___(v21);
  if ( v9 )
  {
    memset_0(v9, 0, 0x48u);
    *v9 = 7;
    *(_OWORD *)pvar = 0;
    v19 = 0;
    LOWORD(pvar[0]) = 11;
    if ( v6 )
      LOWORD(pvar[1]) = -1;
    else
      LOWORD(pvar[1]) = 0;
    *((_OWORD *)v9 + 1) = PKEY_AudioEnvironment_SpatialAudioActive;
    v9[8] = 2;
    v12 = v9 + 2;
    v13 = wil::com_ptr_t<IPropertyStore,wil::err_returncode_policy>::query_to<IPropertyStore>(&v17, v9 + 2);
    v11 = v13;
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, PROPVARIANT *))(*(_QWORD *)*v12 + 48LL))(
              *v12,
              &PKEY_AudioEnvironment_SpatialAudioActive,
              pvar);
      v11 = v13;
      if ( v13 >= 0 )
      {
        CAPOProcessingHostObject::QueueNotification(a3, v20);
        PropVariantClear(pvar);
        v11 = 0;
        goto LABEL_21;
      }
      v14 = 498;
    }
    else
    {
      v14 = 497;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
    PropVariantClear(pvar);
  }
  else
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
  }
LABEL_21:
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  return v11;
}

```

## disassembly

```asm
0x140056f10  mov     [rsp-8+arg_8], rbx
0x140056f15  mov     [rsp-8+arg_18], rsi
0x140056f1a  push    rbp
0x140056f1b  push    rdi
0x140056f1c  push    r12
0x140056f1e  push    r14
0x140056f20  push    r15
0x140056f22  lea     rbp, [rsp-0F90h]
0x140056f2a  mov     eax, 1090h
0x140056f2f  call    _alloca_probe
0x140056f34  sub     rsp, rax
0x140056f37  mov     rax, cs:__security_cookie
0x140056f3e  xor     rax, rsp
0x140056f41  mov     [rbp+0FB0h+var_30], rax
0x140056f48  mov     r15, r8
0x140056f4b  mov     r14, rcx
0x140056f4e  xor     r12d, r12d
0x140056f51  test    rdx, rdx
0x140056f54  jnz     short loc_140056F60
0x140056f56  mov     eax, 80070057h
0x140056f5b  jmp     loc_140057183
0x140056f60  mov     [rsp+10B0h+var_1078], rdx
0x140056f65  mov     rax, [rdx]
0x140056f68  mov     rcx, rdx
0x140056f6b  mov     rax, [rax+8]
0x140056f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056f74  nop
0x140056f75  xor     edx, edx; Val
0x140056f77  mov     r8d, 1000h; Size
0x140056f7d  lea     rcx, [rbp+0FB0h+var_1030]; void *
0x140056f81  call    memset_0
0x140056f86  mov     esi, r12d
0x140056f89  mov     [rsp+10B0h+var_1080], r12b
0x140056f8e  lea     r8, [rbp+0FB0h+var_1030]
0x140056f92  lea     rdx, [rsp+10B0h+var_1080]
0x140056f97  call    wil__wnf_query_nothrow__QueueInitialEnvironmentStatusNotification____2___WnfPayload4k_
0x140056f9c  or      ecx, 0FFFFFFFFh
0x140056f9f  test    eax, eax
0x140056fa1  js      short loc_140056FEE
0x140056fa3  cmp     [rsp+10B0h+var_1080], r12b
0x140056fa8  jz      short loc_140056FEE
0x140056faa  mov     ebx, r12d
0x140056fad  cmp     ebx, [rbp+0FB0h+var_102C]
0x140056fb0  jnb     short loc_140056FEE
0x140056fb2  mov     eax, ebx
0x140056fb4  imul    rdi, rax, 72h ; 'r'
0x140056fb8  lea     r8, [rbp+0FB0h+var_1028]
0x140056fbc  add     r8, rdi; lpString2
0x140056fbf  mov     [rsp+10B0h+bIgnoreCase], 1; int
0x140056fc7  mov     r9d, ecx; cchCount2
0x140056fca  mov     edx, ecx; cchCount1
0x140056fcc  mov     rcx, r14; lpString1
0x140056fcf  call    cs:__imp_CompareStringOrdinal
0x140056fd5  cmp     eax, 2
0x140056fd8  jz      short loc_140056FE1
0x140056fda  inc     ebx
0x140056fdc  or      ecx, 0FFFFFFFFh
0x140056fdf  jmp     short loc_140056FAD
0x140056fe1  mov     esi, r12d
0x140056fe4  cmp     [rbp+rdi+0FB0h+var_FB8], r12w
0x140056fea  setnz   sil
0x140056fee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140056ff5  mov     r14d, 48h ; 'H'
0x140056ffb  mov     ecx, r14d; unsigned __int64
0x140056ffe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140057003  mov     rbx, rax
0x140057006  mov     [rsp+10B0h+var_1080], r12b
0x14005700b  mov     [rsp+10B0h+var_1048], rax
0x140057010  lea     rax, [rsp+10B0h+var_1080]
0x140057015  mov     [rsp+10B0h+var_1040], rax
0x14005701a  mov     [rsp+10B0h+var_1038], 1
0x14005701f  lea     ecx, [r14-30h]; Size
0x140057023  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140057028  mov     rdi, rax
0x14005702b  mov     [rsp+10B0h+var_1058], rax
0x140057030  xorps   xmm0, xmm0
0x140057033  movups  xmmword ptr [rax], xmm0
0x140057036  mov     dword ptr [rax+8], 1
0x14005703d  mov     dword ptr [rax+0Ch], 1
0x140057044  lea     rax, off_1400BA740
0x14005704b  mov     [rdi], rax
0x14005704e  mov     [rdi+10h], rbx
0x140057052  mov     [rsp+10B0h+var_1058], rbx
0x140057057  mov     [rsp+10B0h+var_1050], rdi
0x14005705c  mov     [rsp+10B0h+var_1038], r12b
0x140057061  lea     rcx, [rsp+10B0h+var_1048]
0x140057066  call    std___Temporary_owner_del_APO_NOTIFICATION____lambda_dfcad306b8fb141de82a0500d5a576ce_______Temporary_owner_del_APO_NOTIFICATION____lambda_dfcad306b8fb141de82a0500d5a576ce___
0x14005706b  nop
0x14005706c  test    rbx, rbx
0x14005706f  jnz     short loc_140057096
0x140057071  mov     rcx, [rbp+0FB8h]; this
0x140057078  mov     ebx, 8007000Eh
0x14005707d  mov     r9d, ebx; char *
0x140057080  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140057087  mov     edx, 1E3h; void *
0x14005708c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140057091  jmp     loc_14005716E
0x140057096  mov     r8, r14; Size
0x140057099  xor     edx, edx; Val
0x14005709b  mov     rcx, rbx; void *
0x14005709e  call    memset_0
0x1400570a3  mov     dword ptr [rbx], 7
0x1400570a9  xorps   xmm0, xmm0
0x1400570ac  xor     eax, eax
0x1400570ae  movups  xmmword ptr [rsp+10B0h+pvar], xmm0
0x1400570b3  mov     [rsp+10B0h+var_1060], rax
0x1400570b8  mov     eax, 0Bh
0x1400570bd  mov     word ptr [rsp+10B0h+pvar], ax
0x1400570c2  test    esi, esi
0x1400570c4  jz      short loc_1400570D0
0x1400570c6  or      eax, 0FFFFFFFFh
0x1400570c9  mov     word ptr [rsp+10B0h+pvar+8], ax
0x1400570ce  jmp     short loc_1400570D6
0x1400570d0  mov     word ptr [rsp+10B0h+pvar+8], r12w
0x1400570d6  movups  xmm0, cs:PKEY_AudioEnvironment_SpatialAudioActive
0x1400570dd  mov     eax, cs:dword_1400CB200
0x1400570e3  movups  xmmword ptr [rbx+10h], xmm0
0x1400570e7  mov     [rbx+20h], eax
0x1400570ea  lea     rsi, [rbx+8]
0x1400570ee  mov     rdx, rsi
0x1400570f1  lea     rcx, [rsp+10B0h+var_1078]
0x1400570f6  call    ??$query_to@UIPropertyStore@@@?$com_ptr_t@UIPropertyStore@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAUIPropertyStore@@@Z; wil::com_ptr_t<IPropertyStore,wil::err_returncode_policy>::query_to<IPropertyStore>(IPropertyStore * *)
0x1400570fb  mov     ebx, eax
0x1400570fd  test    eax, eax
0x1400570ff  jns     short loc_14005712A
0x140057101  mov     edx, 1F1h; void *
0x140057106  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14005710d  mov     r9d, eax; char *
0x140057110  mov     rcx, [rbp+0FB8h]; this
0x140057117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005711c  nop
0x14005711d  lea     rcx, [rsp+10B0h+pvar]; pvar
0x140057122  call    cs:__imp_PropVariantClear
0x140057128  jmp     short loc_14005716E
0x14005712a  mov     rcx, [rsi]
0x14005712d  mov     rax, [rcx]
0x140057130  lea     r8, [rsp+10B0h+pvar]
0x140057135  lea     rdx, PKEY_AudioEnvironment_SpatialAudioActive
0x14005713c  mov     rax, [rax+30h]
0x140057140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057145  mov     ebx, eax
0x140057147  test    eax, eax
0x140057149  jns     short loc_140057152
0x14005714b  mov     edx, 1F2h
0x140057150  jmp     short loc_140057106
0x140057152  lea     rdx, [rsp+10B0h+var_1058]
0x140057157  mov     rcx, r15
0x14005715a  call    ?QueueNotification@CAPOProcessingHostObject@@QEAAXAEAV?$shared_ptr@UAPO_NOTIFICATION@@@std@@@Z; CAPOProcessingHostObject::QueueNotification(std::shared_ptr<APO_NOTIFICATION> &)
0x14005715f  nop
0x140057160  lea     rcx, [rsp+10B0h+pvar]; pvar
0x140057165  call    cs:__imp_PropVariantClear
0x14005716b  mov     ebx, r12d
0x14005716e  mov     rcx, rdi; this
0x140057171  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140057176  nop
0x140057177  lea     rcx, [rsp+10B0h+var_1078]
0x14005717c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140057181  mov     eax, ebx
0x140057183  mov     rcx, [rbp+0FB0h+var_30]
0x14005718a  xor     rcx, rsp; StackCookie
0x14005718d  call    __security_check_cookie
0x140057192  lea     r11, [rsp+10B0h+var_20]
0x14005719a  mov     rbx, [r11+38h]
0x14005719e  mov     rsi, [r11+48h]
0x1400571a2  mov     rsp, r11
0x1400571a5  pop     r15
0x1400571a7  pop     r14
0x1400571a9  pop     r12
0x1400571ab  pop     rdi
0x1400571ac  pop     rbp
0x1400571ad  retn
```
