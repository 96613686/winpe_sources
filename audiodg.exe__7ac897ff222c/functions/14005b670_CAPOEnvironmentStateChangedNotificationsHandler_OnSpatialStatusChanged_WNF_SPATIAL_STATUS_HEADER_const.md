# CAPOEnvironmentStateChangedNotificationsHandler::OnSpatialStatusChanged(WNF_SPATIAL_STATUS_HEADER const *)

- ea: `0x14005b670`
- end: `0x14005b879`
- name: `?OnSpatialStatusChanged@CAPOEnvironmentStateChangedNotificationsHandler@@UEAAJPEBUWNF_SPATIAL_STATUS_HEADER@@@Z`
- size: `521`
- prototype: `__int64 __fastcall(CAPOEnvironmentStateChangedNotificationsHandler *__hidden this, const struct WNF_SPATIAL_STATUS_HEADER *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400085bc`
- `0x14000c33c`
- `0x14000ec10`
- `0x14000f36c`
- `0x1400237ec`
- `0x14005b670`
- `0x14005d104`
- `0x14005d148`
- `0x14005e168`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005b846`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005b846`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14005b81d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14005b81d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14005b6c1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14005b6c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14005b804`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14005b850`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14005b804`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14005b850`

## pseudocode

```c
__int64 __fastcall CAPOEnvironmentStateChangedNotificationsHandler::OnSpatialStatusChanged(
        CAPOEnvironmentStateChangedNotificationsHandler *this,
        const struct WNF_SPATIAL_STATUS_HEADER *a2)
{
  unsigned int i; // ebx
  __int64 v5; // rsi
  __int16 v6; // si
  _DWORD *v7; // rbx
  _DWORD *v8; // rdi
  unsigned int v9; // ebx
  _QWORD *v10; // rsi
  int v11; // eax
  __int64 v12; // rdx
  __int64 **j; // rbx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  __int64 v16[2]; // [rsp+30h] [rbp-40h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+50h] [rbp-20h]
  _QWORD v19[2]; // [rsp+58h] [rbp-18h] BYREF
  char v20; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  char v22; // [rsp+A8h] [rbp+38h] BYREF

  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)a2 + 1) )
      return 0;
    v5 = 114LL * i;
    if ( CompareStringOrdinal(*((LPCWCH *)this + 11), -1, (LPCWCH)((char *)a2 + v5 + 8), -1, 1) == 2 )
      break;
  }
  v6 = *(_WORD *)((char *)a2 + v5 + 120);
  v7 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v19[0] = v7;
  v22 = 0;
  v19[1] = &v22;
  v8 = operator new(0x18u);
  v16[0] = (__int64)v7;
  v16[1] = (__int64)v8;
  v20 = 0;
  v8[2] = 1;
  v8[3] = 1;
  *(_QWORD *)v8 = off_1400BA9C0;
  *((_QWORD *)v8 + 2) = v7;
  std::_Temporary_owner_del_APO_NOTIFICATION____lambda_dfcad306b8fb141de82a0500d5a576ce___::__Temporary_owner_del_APO_NOTIFICATION____lambda_dfcad306b8fb141de82a0500d5a576ce___(v19);
  if ( !v7 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoenvironmentnotificationshandler.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
LABEL_14:
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v8);
    return v9;
  }
  v18 = 0;
  *(_OWORD *)pvar = 0;
  LOWORD(pvar[0]) = 11;
  LOWORD(pvar[1]) = -1;
  if ( !v6 )
    LOWORD(pvar[1]) = 0;
  memset_0(v7, 0, 0x48u);
  *v7 = 7;
  v10 = v7 + 2;
  *((_OWORD *)v7 + 1) = PKEY_AudioEnvironment_SpatialAudioActive;
  v7[8] = 2;
  v11 = wil::com_ptr_t<IPropertyStore,wil::err_returncode_policy>::query_to<IPropertyStore>((char *)this + 32, v7 + 2);
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = 104;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoenvironmentnotificationshandler.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
    PropVariantClear(pvar);
    goto LABEL_14;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, PROPVARIANT *))(*(_QWORD *)*v10 + 48LL))(
          *v10,
          &PKEY_AudioEnvironment_SpatialAudioActive,
          pvar);
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = 105;
    goto LABEL_13;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  for ( j = (__int64 **)*((_QWORD *)this + 12); j; j = (__int64 **)*j )
    CAPOProcessingHostObject::QueueNotification((struct _RTL_CRITICAL_SECTION *)j[1], v16);
  if ( this != (CAPOEnvironmentStateChangedNotificationsHandler *)-40LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  PropVariantClear(pvar);
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v8);
  return 0;
}

```

## disassembly

```asm
0x14005b670  mov     [rsp-28h+arg_0], rbx
0x14005b675  mov     [rsp-28h+arg_10], rsi
0x14005b67a  push    rbp
0x14005b67b  push    rdi
0x14005b67c  push    r13
0x14005b67e  push    r14
0x14005b680  push    r15
0x14005b682  mov     rbp, rsp
0x14005b685  sub     rsp, 70h
0x14005b689  xor     r15d, r15d
0x14005b68c  mov     rdi, rdx
0x14005b68f  mov     ebx, r15d
0x14005b692  or      r13d, 0FFFFFFFFh
0x14005b696  mov     r14, rcx
0x14005b699  cmp     ebx, [rdi+4]
0x14005b69c  jnb     loc_14005B85E
0x14005b6a2  mov     rcx, [r14+58h]; lpString1
0x14005b6a6  lea     r8, [rdi+8]
0x14005b6aa  mov     eax, ebx
0x14005b6ac  mov     r9d, r13d; cchCount2
0x14005b6af  imul    rsi, rax, 72h ; 'r'
0x14005b6b3  mov     edx, r13d; cchCount1
0x14005b6b6  mov     [rsp+70h+bIgnoreCase], 1; int
0x14005b6be  add     r8, rsi; lpString2
0x14005b6c1  call    cs:__imp_CompareStringOrdinal
0x14005b6c7  cmp     eax, 2
0x14005b6ca  jz      short loc_14005B6D0
0x14005b6cc  inc     ebx
0x14005b6ce  jmp     short loc_14005B699
0x14005b6d0  movzx   esi, word ptr [rsi+rdi+78h]
0x14005b6d5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14005b6dc  mov     ecx, 48h ; 'H'; unsigned __int64
0x14005b6e1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14005b6e6  mov     rbx, rax
0x14005b6e9  mov     [rbp+var_18], rax
0x14005b6ed  lea     rax, [rbp+arg_8]
0x14005b6f1  mov     [rbp+arg_8], r15b
0x14005b6f5  mov     ecx, 18h; Size
0x14005b6fa  mov     [rbp+var_10], rax
0x14005b6fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005b703  mov     rdi, rax
0x14005b706  mov     [rbp+var_40], rbx
0x14005b70a  lea     rcx, [rbp+var_18]
0x14005b70e  mov     [rbp+var_38], rdi
0x14005b712  mov     [rbp+var_8], r15b
0x14005b716  mov     dword ptr [rax+8], 1
0x14005b71d  mov     dword ptr [rax+0Ch], 1
0x14005b724  lea     rax, off_1400BA9C0
0x14005b72b  mov     [rdi], rax
0x14005b72e  mov     [rdi+10h], rbx
0x14005b732  call    std___Temporary_owner_del_APO_NOTIFICATION____lambda_dfcad306b8fb141de82a0500d5a576ce_______Temporary_owner_del_APO_NOTIFICATION____lambda_dfcad306b8fb141de82a0500d5a576ce___
0x14005b737  test    rbx, rbx
0x14005b73a  jnz     short loc_14005B75E
0x14005b73c  mov     rcx, [rbp+28h]; this
0x14005b740  lea     r8, aAvcoreAudiocor_60; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14005b747  mov     ebx, 8007000Eh
0x14005b74c  mov     edx, 5Ah ; 'Z'; void *
0x14005b751  mov     r9d, ebx; char *
0x14005b754  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005b759  jmp     loc_14005B80A
0x14005b75e  xor     eax, eax
0x14005b760  xorps   xmm0, xmm0
0x14005b763  mov     [rbp+var_20], rax
0x14005b767  mov     eax, 0Bh
0x14005b76c  movups  xmmword ptr [rbp+pvar], xmm0
0x14005b770  mov     word ptr [rbp+pvar], ax
0x14005b774  mov     word ptr [rbp+pvar+8], r13w
0x14005b779  test    si, si
0x14005b77c  jnz     short loc_14005B783
0x14005b77e  mov     word ptr [rbp+pvar+8], r15w
0x14005b783  xor     edx, edx; Val
0x14005b785  mov     rcx, rbx; void *
0x14005b788  lea     r8d, [rdx+48h]; Size
0x14005b78c  call    memset_0
0x14005b791  mov     dword ptr [rbx], 7
0x14005b797  lea     rsi, [rbx+8]
0x14005b79b  movups  xmm0, cs:PKEY_AudioEnvironment_SpatialAudioActive
0x14005b7a2  mov     eax, cs:dword_1400CB200
0x14005b7a8  lea     rcx, [r14+20h]
0x14005b7ac  mov     rdx, rsi
0x14005b7af  movups  xmmword ptr [rbx+10h], xmm0
0x14005b7b3  mov     [rbx+20h], eax
0x14005b7b6  call    ??$query_to@UIPropertyStore@@@?$com_ptr_t@UIPropertyStore@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAUIPropertyStore@@@Z; wil::com_ptr_t<IPropertyStore,wil::err_returncode_policy>::query_to<IPropertyStore>(IPropertyStore * *)
0x14005b7bb  mov     ebx, eax
0x14005b7bd  test    eax, eax
0x14005b7bf  jns     short loc_14005B7C8
0x14005b7c1  mov     edx, 68h ; 'h'
0x14005b7c6  jmp     short loc_14005B7ED
0x14005b7c8  mov     rcx, [rsi]
0x14005b7cb  lea     r8, [rbp+pvar]
0x14005b7cf  lea     rdx, PKEY_AudioEnvironment_SpatialAudioActive
0x14005b7d6  mov     rax, [rcx]
0x14005b7d9  mov     rax, [rax+30h]
0x14005b7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b7e2  mov     ebx, eax
0x14005b7e4  test    eax, eax
0x14005b7e6  jns     short loc_14005B816
0x14005b7e8  mov     edx, 69h ; 'i'; void *
0x14005b7ed  mov     rcx, [rbp+28h]; this
0x14005b7f1  lea     r8, aAvcoreAudiocor_60; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14005b7f8  mov     r9d, eax; char *
0x14005b7fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005b800  lea     rcx, [rbp+pvar]; pvar
0x14005b804  call    cs:__imp_PropVariantClear
0x14005b80a  mov     rcx, rdi; this
0x14005b80d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14005b812  mov     eax, ebx
0x14005b814  jmp     short loc_14005B860
0x14005b816  lea     rsi, [r14+28h]
0x14005b81a  mov     rcx, rsi; lpCriticalSection
0x14005b81d  call    cs:__imp_EnterCriticalSection
0x14005b823  mov     rbx, [r14+60h]
0x14005b827  test    rbx, rbx
0x14005b82a  jz      short loc_14005B83E
0x14005b82c  mov     rcx, [rbx+8]
0x14005b830  lea     rdx, [rbp+var_40]
0x14005b834  call    ?QueueNotification@CAPOProcessingHostObject@@QEAAXAEAV?$shared_ptr@UAPO_NOTIFICATION@@@std@@@Z; CAPOProcessingHostObject::QueueNotification(std::shared_ptr<APO_NOTIFICATION> &)
0x14005b839  mov     rbx, [rbx]
0x14005b83c  jmp     short loc_14005B827
0x14005b83e  test    rsi, rsi
0x14005b841  jz      short loc_14005B84C
0x14005b843  mov     rcx, rsi; lpCriticalSection
0x14005b846  call    cs:__imp_LeaveCriticalSection
0x14005b84c  lea     rcx, [rbp+pvar]; pvar
0x14005b850  call    cs:__imp_PropVariantClear
0x14005b856  mov     rcx, rdi; this
0x14005b859  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14005b85e  xor     eax, eax
0x14005b860  lea     r11, [rsp+70h+var_s0]
0x14005b865  mov     rbx, [r11+30h]
0x14005b869  mov     rsi, [r11+40h]
0x14005b86d  mov     rsp, r11
0x14005b870  pop     r15
0x14005b872  pop     r14
0x14005b874  pop     r13
0x14005b876  pop     rdi
0x14005b877  pop     rbp
0x14005b878  retn
```
