# CLocationUserRegistryHelper::Initialize(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004e94c`
- end: `0x18004eb4f`
- name: `?Initialize@CLocationUserRegistryHelper@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(ATL::CRegKey *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009a798`

## callees

- `0x1800208b0`
- `0x1800208d4`
- `0x180020994`
- `0x180020c64`
- `0x18004e94c`
- `0x18004eb58`
- `0x18008fa98`
- `0x18009cc78`
- `0x1800a98c0`
- `0x1800aa5ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004ea18`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004eaf1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004ea18`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004eaf1`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004e9b2`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004e9b2`

## string_xrefs

- `0x18004e9a4`: `SYSTEM\CurrentControlSet\Services\lfsvc\`
- `0x18004eb39`: `onecoreuap\drivers\MobilePC\Location\Product\idk\LocationRegistryHelper.h`
- `0x18004eb11`: `Path is too long. buff len: %zu. subPath len: %zu`
- `0x18004eb32`: `CLocationPersistedRegPathHelper::GetPersistedRegPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLocationUserRegistryHelper::Initialize(ATL::CRegKey *this, __int64 a2)
{
  int PersistedRegistryLocationW; // eax
  signed int v5; // ebx
  __int64 v6; // rdx
  int v7; // r8d
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rdx
  const unsigned __int16 *v12; // rax
  HKEY v13; // rdx
  unsigned __int16 *v14; // r9
  int v15; // eax
  unsigned int v17; // [rsp+20h] [rbp-E0h]
  wil::details *v18; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v19; // [rsp+30h] [rbp-D0h]
  unsigned int *v20; // [rsp+38h] [rbp-C8h]
  __int128 v21; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+60h] [rbp-A0h]
  _WORD v23[256]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+298h] [rbp+198h]

  memset_0(v23, 0, 0x1FEu);
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"LfSvc",
                                 L"SYSTEM\\CurrentControlSet\\Services\\lfsvc\\",
                                 v23,
                                 510,
                                 0);
  v5 = PersistedRegistryLocationW;
  if ( !PersistedRegistryLocationW )
  {
    v6 = -1;
    do
      ++v6;
    while ( v23[v6] );
    if ( (unsigned __int64)(v6 + 20) >= 0xFF )
    {
      v5 = -2147418113;
      LODWORD(v18) = -2147418113;
      wil::details::in1diag5::Return_HrMsg(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\idk\\LocationRegistryHelper.h",
        "CLocationPersistedRegPathHelper::GetPersistedRegPath",
        "E_UNEXPECTED",
        v18,
        (__int64)"Path is too long. buff len: %zu. subPath len: %zu",
        (const char *)v6,
        19);
      return (unsigned int)v5;
    }
    v7 = (unsigned __int16)v23[v6 - 1] - 92;
    if ( v23[v6 - 1] == 92 )
      v7 = (unsigned __int16)v23[v6];
    if ( v7 )
      _o_wcscat_s(v23, 255, L"\\");
    _o_wcscat_s(v23, 255, L"Migrated\\UserStore\\");
    goto LABEL_10;
  }
  if ( PersistedRegistryLocationW > 0 )
    v5 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_10:
    v21 = 0;
    v22 = 0;
    v8 = std::_WChar_traits<unsigned short>::length(v23);
    std::wstring::_Construct<1,unsigned short const *>(&v21, v23, v8);
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v9);
    std::wstring::_Append<unsigned short>(&v21, v10, *(_QWORD *)(a2 + 16));
    v12 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v21, v11);
    v15 = ATL::CRegKey::Create(this, v13, v12, v14, v17, 0x2001Fu, v19, v20);
    v5 = v15;
    if ( v15 > 0 )
      v5 = (unsigned __int16)v15 | 0x80070000;
    if ( v5 >= 0 )
      v5 = 0;
    std::wstring::_Tidy_deallocate(&v21);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004e94c  mov     [rsp-8+arg_10], rbx
0x18004e951  mov     [rsp-8+arg_18], rsi
0x18004e956  push    rbp
0x18004e957  push    rdi
0x18004e958  push    r14
0x18004e95a  lea     rbp, [rsp-180h]
0x18004e962  sub     rsp, 280h
0x18004e969  mov     rax, cs:__security_cookie
0x18004e970  xor     rax, rsp
0x18004e973  mov     [rbp+190h+var_20], rax
0x18004e97a  mov     rdi, rdx
0x18004e97d  mov     rsi, rcx
0x18004e980  mov     ebx, 1FEh
0x18004e985  mov     r8d, ebx; Size
0x18004e988  xor     edx, edx; Val
0x18004e98a  lea     rcx, [rsp+290h+var_220]; void *
0x18004e98f  call    memset_0
0x18004e994  xor     r14d, r14d
0x18004e997  mov     [rsp+290h+var_270], r14; unsigned int
0x18004e99c  mov     r9d, ebx
0x18004e99f  lea     r8, [rsp+290h+var_220]
0x18004e9a4  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\lf"...
0x18004e9ab  lea     rcx, aLfsvc_1; "LfSvc"
0x18004e9b2  call    cs:__imp_GetPersistedRegistryLocationW
0x18004e9b8  mov     ebx, eax
0x18004e9ba  test    eax, eax
0x18004e9bc  jnz     loc_18004EAD5
0x18004e9c2  lea     rax, [rsp+290h+var_220]
0x18004e9c7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004e9cb  inc     rdx
0x18004e9ce  cmp     [rax+rdx*2], r14w
0x18004e9d3  jnz     short loc_18004E9CB
0x18004e9d5  lea     rax, [rdx+14h]
0x18004e9d9  mov     ebx, 0FFh
0x18004e9de  cmp     rax, rbx
0x18004e9e1  jnb     loc_18004EAFC
0x18004e9e7  movzx   r8d, [rsp+rdx*2+290h+var_222]
0x18004e9ed  sub     r8d, 5Ch ; '\'
0x18004e9f1  jnz     short loc_18004EA00
0x18004e9f3  movzx   r8d, [rsp+rdx*2+290h+var_220]
0x18004e9f9  movzx   ecx, r14w
0x18004e9fd  sub     r8d, ecx
0x18004ea00  test    r8d, r8d
0x18004ea03  jnz     loc_18004EAE2
0x18004ea09  lea     r8, aMigratedUserst; "Migrated\\UserStore\\"
0x18004ea10  mov     rdx, rbx
0x18004ea13  lea     rcx, [rsp+290h+var_220]
0x18004ea18  call    cs:__imp__o_wcscat_s
0x18004ea1e  xorps   xmm0, xmm0
0x18004ea21  movups  [rsp+290h+var_240], xmm0
0x18004ea26  xorps   xmm1, xmm1
0x18004ea29  movdqu  xmmword ptr [rsp+60h], xmm1
0x18004ea2f  lea     rcx, [rsp+290h+var_220]
0x18004ea34  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004ea39  mov     r8, rax
0x18004ea3c  lea     rdx, [rsp+290h+var_220]
0x18004ea41  lea     rcx, [rsp+290h+var_240]
0x18004ea46  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004ea4b  nop
0x18004ea4c  mov     rcx, rdi
0x18004ea4f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ea54  mov     r8, [rdi+10h]
0x18004ea58  mov     rdx, rax
0x18004ea5b  lea     rcx, [rsp+290h+var_240]
0x18004ea60  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004ea65  lea     rcx, [rsp+290h+var_240]
0x18004ea6a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ea6f  mov     r8, rax; unsigned __int16 *
0x18004ea72  mov     dword ptr [rsp+290h+var_268], 2001Fh; unsigned int
0x18004ea7a  mov     rcx, rsi; this
0x18004ea7d  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18004ea82  mov     ebx, eax
0x18004ea84  test    eax, eax
0x18004ea86  jle     short loc_18004EA91
0x18004ea88  movzx   ebx, ax
0x18004ea8b  or      ebx, 80070000h
0x18004ea91  test    ebx, ebx
0x18004ea93  js      short loc_18004EA98
0x18004ea95  mov     ebx, r14d
0x18004ea98  lea     rcx, [rsp+290h+var_240]
0x18004ea9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004eaa2  mov     eax, ebx
0x18004eaa4  mov     rcx, [rbp+190h+var_20]
0x18004eaab  xor     rcx, rsp; StackCookie
0x18004eaae  call    __security_check_cookie
0x18004eab3  lea     r11, [rsp+290h+var_10]
0x18004eabb  mov     rbx, [r11+30h]
0x18004eabf  mov     rsi, [r11+38h]
0x18004eac3  mov     rsp, r11
0x18004eac6  pop     r14
0x18004eac8  pop     rdi
0x18004eac9  pop     rbp
0x18004eaca  retn
0x18004eacb  test    ebx, ebx
0x18004eacd  jns     loc_18004EA1E
0x18004ead3  jmp     short loc_18004EAA2
0x18004ead5  jle     short loc_18004EACB
0x18004ead7  movzx   ebx, ax
0x18004eada  or      ebx, 80070000h
0x18004eae0  jmp     short loc_18004EACB
0x18004eae2  lea     r8, asc_18016EDDC; "\\"
0x18004eae9  mov     rdx, rbx
0x18004eaec  lea     rcx, [rsp+290h+var_220]
0x18004eaf1  call    cs:__imp__o_wcscat_s
0x18004eaf7  jmp     loc_18004EA09
0x18004eafc  mov     rcx, [rbp+198h]; this
0x18004eb03  mov     [rsp+290h+var_250], 13h
0x18004eb0c  mov     [rsp+290h+var_258], rdx; char *
0x18004eb11  lea     rax, aPathIsTooLongB; "Path is too long. buff len: %zu. subPat"...
0x18004eb18  mov     [rsp+290h+var_260], rax; __int64
0x18004eb1d  mov     ebx, 8000FFFFh
0x18004eb22  mov     dword ptr [rsp+290h+var_268], ebx; wil::details *
0x18004eb26  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x18004eb2d  mov     [rsp+290h+var_270], rax; char *
0x18004eb32  lea     r9, aClocationpersi; "CLocationPersistedRegPathHelper::GetPer"...
0x18004eb39  lea     r8, aOnecoreuapDriv_0; "onecoreuap\\drivers\\MobilePC\\Location"...
0x18004eb40  mov     edx, 35h ; '5'; void *
0x18004eb45  call    ?Return_HrMsg@in1diag5@details@wil@@YAXPEAXIPEBD11J1ZZ; wil::details::in1diag5::Return_HrMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x18004eb4a  jmp     loc_18004EAA2
```
