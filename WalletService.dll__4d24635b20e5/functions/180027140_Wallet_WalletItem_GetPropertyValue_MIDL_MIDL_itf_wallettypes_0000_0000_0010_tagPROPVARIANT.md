# Wallet::WalletItem::GetPropertyValue(__MIDL___MIDL_itf_wallettypes_0000_0000_0010,tagPROPVARIANT *)

- ea: `0x180027140`
- end: `0x1800273ee`
- name: `?GetPropertyValue@WalletItem@Wallet@@UEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAUtagPROPVARIANT@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000d8d8`
- `0x18000d944`
- `0x18000dab0`
- `0x180013f78`
- `0x180016e78`
- `0x18001aa00`
- `0x18001aa30`
- `0x18001cc50`
- `0x180025ad4`
- `0x180027140`
- `0x1800290bc`
- `0x180039750`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180027330`
- `OLEAUT32!__imp_SysAllocString` at `0x180027330`
- `OLEAUT32!__imp_SysFreeString` at `0x180027325`
- `OLEAUT32!__imp_SysFreeString` at `0x180027325`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800273c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800273c5`
- `dsclient!DSCreateSharedFileToken` at `0x180027313`
- `dsclient!DSCreateSharedFileToken` at `0x180027313`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItem::GetPropertyValue(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int (__fastcall ***v4)(_QWORD); // r15
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rdx
  Wallet::Utils *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // eax
  BSTR v14; // rax
  int v15; // ebx
  OLECHAR *psz; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[16]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v19[5]; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v20[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h]
  __int64 v22; // [rsp+80h] [rbp-80h]
  _QWORD v23[7]; // [rsp+88h] [rbp-78h]
  _BYTE v24[256]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = (unsigned int (__fastcall ***)(_QWORD))(*(_QWORD *)(a1 + 16) + 104LL);
  OrderedLockBase<enum WalletLockOrder>::lock(v4);
  Wallet::WalletStorageAttach::WalletStorageAttach(
    (Wallet::WalletStorageAttach *)v18,
    *(struct Wallet::IWalletStorage **)(*(_QWORD *)(a1 + 16) + 56LL));
  if ( a3 )
  {
    if ( (Microsoft_Windows_WalletEnableBits & 1) != 0 )
      McTemplateU0iq_EventWriteTransfer(v7, Core_GetProperty_Start, *(_QWORD *)(a1 + 80), a2);
    v8 = Wallet::WalletItem::TGetPropertyValue<utl::unordered_map<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
           v7,
           a1 + 88,
           a2,
           a3);
    if ( v8 != -2143682560
      || (v9 = *(_QWORD *)(a1 + 80)) == 0
      || (v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 56LL)
                                                                           + 88LL))(
                 *(_QWORD *)(*(_QWORD *)(a1 + 16) + 56LL),
                 v9,
                 a2,
                 a3),
          v8 >= 0) )
    {
      if ( *(_WORD *)a3 )
      {
        v7 = 8;
        if ( a2 - 200 <= 8 )
        {
          psz = 0;
          if ( *(_WORD *)a3 != 8 )
            __fastfail(5u);
          v20[0] = 0;
          v23[0] = L"S-1-5-18";
          v23[2] = L"ID_CAP_WALLET_ADMIN";
          v23[6] = L"S-1-5-18";
          v23[4] = L"ID_CAP_EVERYONE";
          v20[1] = 1;
          v21 = 4;
          v22 = 0;
          v23[1] = 2;
          v23[3] = 2;
          v23[5] = 0;
          memset_0(v24, 0, sizeof(v24));
          if ( !Wallet::Utils::IsPhoneOS(v10) )
          {
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v19);
            if ( (int)Wallet::ServerUtils::GetCallerAppContainerSid(v19) >= 0 )
            {
              LODWORD(v21) = v21 + 1;
              v11 = v19[0];
              LODWORD(v23[2 * (unsigned int)(v21 - 1) - 1]) = 0;
              v23[2 * (unsigned int)(v21 - 1)] = v11;
            }
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v19);
          }
          v12 = tlx::replace<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>(&psz);
          v13 = DSCreateSharedFileToken(*(_QWORD *)(a3 + 8), v20, 0, 0, v12);
          if ( v13 >= 0 )
          {
            SysFreeString(*(BSTR *)(a3 + 8));
            v14 = SysAllocString(psz);
            *(_QWORD *)(a3 + 8) = v14;
            if ( !v14 )
              v8 = -2147024882;
          }
          else
          {
            v8 = v13;
          }
          tlx::unique_any<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>::~unique_any<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>(&psz);
        }
      }
      else
      {
        v8 = -2143682560;
      }
    }
  }
  else
  {
    v8 = -2147467261;
  }
  if ( (Microsoft_Windows_WalletEnableBits & 1) != 0 )
    McTemplateU0iq_EventWriteTransfer(v7, Core_GetProperty_Stop, *(_QWORD *)(a1 + 80), a2);
  Wallet::WalletStorageAttach::~WalletStorageAttach((Wallet::WalletStorageAttach *)v18);
  v15 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
  if ( (**v4)(v4) != v15 )
    __int2c();
  ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
  LeaveCriticalSection((LPCRITICAL_SECTION)((unsigned __int64)(v4 + 1) & -(__int64)(v4 != 0)));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180027140  push    rbp
0x180027142  push    rbx
0x180027143  push    rsi
0x180027144  push    rdi
0x180027145  push    r12
0x180027147  push    r14
0x180027149  push    r15
0x18002714b  lea     rbp, [rsp-0D0h]
0x180027153  sub     rsp, 1D0h
0x18002715a  mov     rax, cs:__security_cookie
0x180027161  xor     rax, rsp
0x180027164  mov     [rbp+100h+var_40], rax
0x18002716b  mov     r15, [rcx+10h]
0x18002716f  mov     rsi, rcx
0x180027172  add     r15, 68h ; 'h'
0x180027176  mov     rbx, r8
0x180027179  mov     rcx, r15
0x18002717c  mov     r14d, edx
0x18002717f  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180027184  mov     rdx, [rsi+10h]
0x180027188  lea     rcx, [rsp+200h+var_1C8]; this
0x18002718d  mov     rdx, [rdx+38h]; struct Wallet::IWalletStorage *
0x180027191  call    ??0WalletStorageAttach@Wallet@@QEAA@PEAUIWalletStorage@1@@Z; Wallet::WalletStorageAttach::WalletStorageAttach(Wallet::IWalletStorage *)
0x180027196  xor     r12d, r12d
0x180027199  test    rbx, rbx
0x18002719c  jnz     short loc_1800271A8
0x18002719e  mov     edi, 80004003h
0x1800271a3  jmp     loc_18002734E
0x1800271a8  test    cs:Microsoft_Windows_WalletEnableBits, 1
0x1800271af  jz      short loc_1800271C4
0x1800271b1  mov     r8, [rsi+50h]
0x1800271b5  lea     rdx, Core_GetProperty_Start
0x1800271bc  mov     r9d, r14d
0x1800271bf  call    McTemplateU0iq_EventWriteTransfer
0x1800271c4  lea     rdx, [rsi+58h]
0x1800271c8  mov     r9, rbx
0x1800271cb  mov     r8d, r14d
0x1800271ce  call    ??$TGetPropertyValue@V?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@WalletItem@Wallet@@QEBAJAEBV?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAUtagPROPVARIANT@@@Z; Wallet::WalletItem::TGetPropertyValue<utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>> const &,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,tagPROPVARIANT *)
0x1800271d3  mov     edi, eax
0x1800271d5  cmp     eax, 803A0000h
0x1800271da  jnz     short loc_180027209
0x1800271dc  mov     rdx, [rsi+50h]
0x1800271e0  test    rdx, rdx
0x1800271e3  jz      short loc_180027209
0x1800271e5  mov     rax, [rsi+10h]
0x1800271e9  mov     r9, rbx
0x1800271ec  mov     r8d, r14d
0x1800271ef  mov     rcx, [rax+38h]
0x1800271f3  mov     rax, [rcx]
0x1800271f6  mov     rax, [rax+58h]
0x1800271fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271ff  mov     edi, eax
0x180027201  test    eax, eax
0x180027203  js      loc_18002734E
0x180027209  cmp     [rbx], r12w
0x18002720d  jnz     short loc_180027219
0x18002720f  mov     edi, 803A0000h
0x180027214  jmp     loc_18002734E
0x180027219  lea     eax, [r14-0C8h]
0x180027220  mov     ecx, 8
0x180027225  cmp     eax, ecx
0x180027227  ja      loc_18002734E
0x18002722d  mov     [rsp+200h+psz], r12
0x180027232  cmp     [rbx], cx
0x180027235  jz      short loc_18002723E
0x180027237  mov     ecx, 5
0x18002723c  int     29h; Win8: RtlFailFast(ecx)
0x18002723e  lea     rdx, aS1518; "S-1-5-18"
0x180027245  mov     [rsp+200h+var_190], r12d
0x18002724a  lea     rax, aIdCapWalletAdm; "ID_CAP_WALLET_ADMIN"
0x180027251  mov     [rbp+100h+var_178], rdx
0x180027255  mov     [rbp+100h+var_168], rax
0x180027259  lea     rcx, [rbp+100h+var_140]; void *
0x18002725d  lea     rax, aIdCapEveryone; "ID_CAP_EVERYONE"
0x180027264  mov     [rbp+100h+var_148], rdx
0x180027268  xor     edx, edx; Val
0x18002726a  mov     [rbp+100h+var_158], rax
0x18002726e  mov     r8d, 100h; Size
0x180027274  mov     [rsp+200h+var_18C], 1
0x18002727c  mov     [rsp+200h+var_188], 4
0x180027285  mov     [rbp+100h+var_180], r12
0x180027289  mov     [rbp+100h+var_170], 2
0x180027291  mov     [rbp+100h+var_160], 2
0x180027299  mov     [rbp+100h+var_150], r12
0x18002729d  call    memset_0
0x1800272a2  call    ?IsPhoneOS@Utils@Wallet@@YA_NXZ; Wallet::Utils::IsPhoneOS(void)
0x1800272a7  test    al, al
0x1800272a9  jnz     short loc_1800272F5
0x1800272ab  lea     rcx, [rsp+200h+var_1B8]
0x1800272b0  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800272b5  lea     rcx, [rsp+200h+var_1B8]
0x1800272ba  call    ?GetCallerAppContainerSid@ServerUtils@Wallet@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::ServerUtils::GetCallerAppContainerSid(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800272bf  test    eax, eax
0x1800272c1  js      short loc_1800272EB
0x1800272c3  mov     eax, dword ptr [rsp+200h+var_188]
0x1800272c7  inc     eax
0x1800272c9  mov     dword ptr [rsp+200h+var_188], eax
0x1800272cd  lea     ecx, [rax-1]
0x1800272d0  mov     rax, [rsp+200h+var_1B8]
0x1800272d5  add     rcx, rcx
0x1800272d8  mov     dword ptr [rbp+rcx*8+100h+var_180], r12d
0x1800272dd  mov     ecx, dword ptr [rsp+200h+var_188]
0x1800272e1  dec     ecx
0x1800272e3  add     rcx, rcx
0x1800272e6  mov     [rbp+rcx*8+100h+var_178], rax
0x1800272eb  lea     rcx, [rsp+200h+var_1B8]
0x1800272f0  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800272f5  lea     rcx, [rsp+200h+psz]
0x1800272fa  call    ??$replace@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAGAEAV?$unique_any@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>(tlx::unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>> &)
0x1800272ff  mov     rcx, [rbx+8]
0x180027303  lea     rdx, [rsp+200h+var_190]
0x180027308  xor     r9d, r9d
0x18002730b  mov     [rsp+200h+var_1E0], rax
0x180027310  xor     r8d, r8d
0x180027313  call    cs:__imp_DSCreateSharedFileToken
0x180027319  test    eax, eax
0x18002731b  jns     short loc_180027321
0x18002731d  mov     edi, eax
0x18002731f  jmp     short loc_180027344
0x180027321  mov     rcx, [rbx+8]; bstrString
0x180027325  call    cs:__imp_SysFreeString
0x18002732b  mov     rcx, [rsp+200h+psz]; psz
0x180027330  call    cs:__imp_SysAllocString
0x180027336  mov     [rbx+8], rax
0x18002733a  test    rax, rax
0x18002733d  jnz     short loc_180027344
0x18002733f  mov     edi, 8007000Eh
0x180027344  lea     rcx, [rsp+200h+psz]
0x180027349  call    ??1?$unique_any@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>::~unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>(void)
0x18002734e  test    cs:Microsoft_Windows_WalletEnableBits, 1
0x180027355  jz      short loc_18002736A
0x180027357  mov     r8, [rsi+50h]
0x18002735b  lea     rdx, Core_GetProperty_Stop
0x180027362  mov     r9d, r14d
0x180027365  call    McTemplateU0iq_EventWriteTransfer
0x18002736a  lea     rcx, [rsp+200h+var_1C8]; this
0x18002736f  call    ??1WalletStorageAttach@Wallet@@QEAA@XZ; Wallet::WalletStorageAttach::~WalletStorageAttach(void)
0x180027374  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x18002737b  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180027382  mov     rax, [rax+8]
0x180027386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002738b  mov     rcx, [r15]
0x18002738e  mov     ebx, eax
0x180027390  mov     rax, [rcx]
0x180027393  mov     rcx, r15
0x180027396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002739b  cmp     eax, ebx
0x18002739d  jz      short loc_1800273A1
0x18002739f  int     2Ch; Windows NT - assertion failure
0x1800273a1  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x1800273a8  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x1800273af  mov     rax, [rax+10h]
0x1800273b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273b8  lea     rax, [r15+8]
0x1800273bc  neg     r15
0x1800273bf  sbb     rcx, rcx
0x1800273c2  and     rcx, rax; lpCriticalSection
0x1800273c5  call    cs:__imp_LeaveCriticalSection
0x1800273cb  mov     eax, edi
0x1800273cd  mov     rcx, [rbp+100h+var_40]
0x1800273d4  xor     rcx, rsp; StackCookie
0x1800273d7  call    __security_check_cookie
0x1800273dc  add     rsp, 1D0h
0x1800273e3  pop     r15
0x1800273e5  pop     r14
0x1800273e7  pop     r12
0x1800273e9  pop     rdi
0x1800273ea  pop     rsi
0x1800273eb  pop     rbx
0x1800273ec  pop     rbp
0x1800273ed  retn
```
