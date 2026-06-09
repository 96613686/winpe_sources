# Windows::System::TimeZoneSettingsImpl::PopulateTimeZones(void)

- ea: `0x1800161bc`
- end: `0x180016468`
- name: `?PopulateTimeZones@TimeZoneSettingsImpl@System@Windows@@AEAAJXZ`
- size: `684`
- prototype: `__int64 __fastcall(Windows::System::TimeZoneSettingsImpl *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a808`

## callees

- `0x180002dc0`
- `0x1800032ec`
- `0x18000399c`
- `0x18000af1c`
- `0x180013758`
- `0x180013780`
- `0x180013eb4`
- `0x180015d04`
- `0x180016080`
- `0x1800161bc`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016443`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001622b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016425`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001622b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016425`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001639d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800163eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800163fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001639d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800163eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800163fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016221`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016221`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001626a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001626a`
- `api-ms-win-core-timezone-l1-1-0!EnumDynamicTimeZoneInformation` at `0x18001628e`
- `api-ms-win-core-timezone-l1-1-0!EnumDynamicTimeZoneInformation` at `0x18001628e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::System::TimeZoneSettingsImpl::PopulateTimeZones(
        Windows::System::TimeZoneSettingsImpl *this)
{
  signed int LastError; // eax
  signed int TimeZoneDisplayName; // edi
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  HSTRING v6; // rax
  _OWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 *v9; // rcx
  __int64 v10; // rdx
  struct _TIME_DYNAMIC_ZONE_INFORMATION *const *i; // rbx
  Windows::System::TimeZoneSettingsImpl *v12; // rcx
  int v13; // eax
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  void **v16; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[432]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+200h] [rbp+100h] BYREF

  v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable';
  phkResult = 0;
  memset_0(v18, 0, sizeof(v18));
  Buffer[0] = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    v4 = 0;
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones",
           0,
           1u,
           &phkResult);
    TimeZoneDisplayName = v5;
    if ( v5 > 0 )
      TimeZoneDisplayName = (unsigned __int16)v5 | 0x80070000;
    if ( TimeZoneDisplayName >= 0 )
    {
      while ( !(unsigned int)EnumDynamicTimeZoneInformation(v4, v18) )
      {
        v6 = (HSTRING)operator new(0x1B0u, (const struct std::nothrow_t *)&std::nothrow);
        string = v6;
        if ( !v6 )
        {
          TimeZoneDisplayName = -2147024882;
          std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>::~unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>((void **)&string);
          goto LABEL_21;
        }
        ++v4;
        v7 = v18;
        v8 = 3;
        do
        {
          *(_OWORD *)v6 = *v7;
          *((_OWORD *)v6 + 1) = v7[1];
          *((_OWORD *)v6 + 2) = v7[2];
          *((_OWORD *)v6 + 3) = v7[3];
          *((_OWORD *)v6 + 4) = v7[4];
          *((_OWORD *)v6 + 5) = v7[5];
          *((_OWORD *)v6 + 6) = v7[6];
          *((_OWORD *)v6 + 7) = v7[7];
          v6 += 32;
          v7 += 8;
          --v8;
        }
        while ( v8 );
        *(_OWORD *)v6 = *v7;
        *((_OWORD *)v6 + 1) = v7[1];
        *((_OWORD *)v6 + 2) = v7[2];
        v9 = (__int64 *)((char *)this + 112);
        v10 = *((_QWORD *)this + 15);
        if ( v10 == *((_QWORD *)this + 16) )
          std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::_Emplace_reallocate<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(
            v9,
            v10,
            (__int64 *)&string);
        else
          std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::_Emplace_back_with_unused_capacity<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(
            (__int64)v9,
            (__int64 *)&string);
        std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>::~unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>((void **)&string);
      }
      std::_Sort_unchecked<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> *,bool (*)(std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> &,std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> &)>(
        *((void ***)this + 14),
        *((void ***)this + 15),
        (__int64)(*((_QWORD *)this + 15) - *((_QWORD *)this + 14)) >> 3,
        (unsigned __int8 (__fastcall *)(void **, void **))DynamicTimeZoneCompare);
      for ( i = (struct _TIME_DYNAMIC_ZONE_INFORMATION *const *)*((_QWORD *)this + 14);
            (unsigned __int64)i < *((_QWORD *)this + 15);
            ++i )
      {
        WindowsDeleteString(0);
        string = 0;
        TimeZoneDisplayName = Windows::System::TimeZoneSettingsImpl::GetTimeZoneDisplayName(
                                v12,
                                phkResult,
                                Buffer,
                                *i,
                                &string);
        if ( TimeZoneDisplayName < 0 )
        {
          WindowsDeleteString(string);
          break;
        }
        (*(void (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)this + 13) + 104LL))(*((_QWORD *)this + 13), string);
        WindowsDeleteString(string);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    TimeZoneDisplayName = LastError;
    if ( LastError > 0 )
      TimeZoneDisplayName = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_21:
  v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable';
  if ( phkResult
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::InternalClose(&v16) )
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    RaiseException(v13, 1u, 0, 0);
    __debugbreak();
  }
  return (unsigned int)TimeZoneDisplayName;
}

```

## disassembly

```asm
0x1800161bc  push    rbp
0x1800161be  push    rbx
0x1800161bf  push    rdi
0x1800161c0  push    r14
0x1800161c2  lea     rbp, [rsp-328h]
0x1800161ca  sub     rsp, 428h
0x1800161d1  mov     rax, cs:__security_cookie
0x1800161d8  xor     rax, rsp
0x1800161db  mov     [rbp+340h+var_30], rax
0x1800161e2  mov     r14, rcx
0x1800161e5  lea     rax, ??_7?$HandleT@URegistryKeyTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable'
0x1800161ec  mov     [rsp+440h+var_408], rax
0x1800161f1  mov     [rsp+440h+var_400], 0
0x1800161fa  xor     edx, edx; Val
0x1800161fc  mov     r8d, 1B0h; Size
0x180016202  lea     rcx, [rsp+440h+var_3F0]; void *
0x180016207  call    memset_0
0x18001620c  xor     eax, eax
0x18001620e  mov     [rbp+340h+Buffer], ax
0x180016215  mov     edx, 104h; uSize
0x18001621a  lea     rcx, [rbp+340h+Buffer]; lpBuffer
0x180016221  call    cs:__imp_GetSystemDirectoryW
0x180016227  test    eax, eax
0x180016229  jnz     short loc_180016249
0x18001622b  call    cs:__imp_GetLastError
0x180016231  mov     edi, eax
0x180016233  test    eax, eax
0x180016235  jle     loc_180016403
0x18001623b  movzx   edi, ax
0x18001623e  or      edi, 80070000h
0x180016244  jmp     loc_180016403
0x180016249  xor     ebx, ebx
0x18001624b  lea     rax, [rsp+440h+var_400]
0x180016250  mov     [rsp+440h+phkResult], rax; phkResult
0x180016255  lea     r9d, [rbx+1]; samDesired
0x180016259  xor     r8d, r8d; ulOptions
0x18001625c  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180016263  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001626a  call    cs:__imp_RegOpenKeyExW
0x180016270  mov     edi, eax
0x180016272  test    eax, eax
0x180016274  jle     short loc_18001627F
0x180016276  movzx   edi, ax
0x180016279  or      edi, 80070000h
0x18001627f  test    edi, edi
0x180016281  js      loc_180016403
0x180016287  lea     rdx, [rsp+440h+var_3F0]
0x18001628c  mov     ecx, ebx
0x18001628e  call    cs:__imp_EnumDynamicTimeZoneInformation
0x180016294  test    eax, eax
0x180016296  jnz     loc_180016373
0x18001629c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800162a3  mov     ecx, 1B0h; unsigned __int64
0x1800162a8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800162ad  mov     [rsp+440h+string], rax
0x1800162b2  test    rax, rax
0x1800162b5  jz      loc_18001635F
0x1800162bb  inc     ebx
0x1800162bd  lea     rcx, [rsp+440h+var_3F0]
0x1800162c2  mov     edx, 3
0x1800162c7  lea     r8d, [rdx+7Dh]
0x1800162cb  movups  xmm0, xmmword ptr [rcx]
0x1800162ce  movups  xmmword ptr [rax], xmm0
0x1800162d1  movups  xmm1, xmmword ptr [rcx+10h]
0x1800162d5  movups  xmmword ptr [rax+10h], xmm1
0x1800162d9  movups  xmm0, xmmword ptr [rcx+20h]
0x1800162dd  movups  xmmword ptr [rax+20h], xmm0
0x1800162e1  movups  xmm1, xmmword ptr [rcx+30h]
0x1800162e5  movups  xmmword ptr [rax+30h], xmm1
0x1800162e9  movups  xmm0, xmmword ptr [rcx+40h]
0x1800162ed  movups  xmmword ptr [rax+40h], xmm0
0x1800162f1  movups  xmm1, xmmword ptr [rcx+50h]
0x1800162f5  movups  xmmword ptr [rax+50h], xmm1
0x1800162f9  movups  xmm0, xmmword ptr [rcx+60h]
0x1800162fd  movups  xmmword ptr [rax+60h], xmm0
0x180016301  movups  xmm1, xmmword ptr [rcx+70h]
0x180016305  movups  xmmword ptr [rax+70h], xmm1
0x180016309  add     rax, r8
0x18001630c  add     rcx, r8
0x18001630f  sub     rdx, 1
0x180016313  jnz     short loc_1800162CB
0x180016315  movups  xmm0, xmmword ptr [rcx]
0x180016318  movups  xmmword ptr [rax], xmm0
0x18001631b  movups  xmm1, xmmword ptr [rcx+10h]
0x18001631f  movups  xmmword ptr [rax+10h], xmm1
0x180016323  movups  xmm0, xmmword ptr [rcx+20h]
0x180016327  movups  xmmword ptr [rax+20h], xmm0
0x18001632b  lea     rcx, [r14+70h]
0x18001632f  mov     rdx, [rcx+8]
0x180016333  cmp     rdx, [rcx+10h]
0x180016337  jz      short loc_180016345
0x180016339  lea     rdx, [rsp+440h+string]
0x18001633e  call    ??$_Emplace_back_with_unused_capacity@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@@?$vector@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@V?$allocator@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@@2@@std@@AEAAAEAV?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::_Emplace_back_with_unused_capacity<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> &&)
0x180016343  jmp     short loc_180016350
0x180016345  lea     r8, [rsp+440h+string]
0x18001634a  call    ??$_Emplace_reallocate@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@@?$vector@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@V?$allocator@V?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>::_Emplace_reallocate<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>>(std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> * const,std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> &&)
0x18001634f  nop
0x180016350  lea     rcx, [rsp+440h+string]
0x180016355  call    ??1?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@QEAA@XZ; std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>::~unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>(void)
0x18001635a  jmp     loc_180016287
0x18001635f  mov     edi, 8007000Eh
0x180016364  lea     rcx, [rsp+440h+string]
0x180016369  call    ??1?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@QEAA@XZ; std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>::~unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION>(void)
0x18001636e  jmp     loc_180016403
0x180016373  mov     rdx, [r14+78h]
0x180016377  mov     rcx, [r14+70h]
0x18001637b  mov     r8, rdx
0x18001637e  sub     r8, rcx
0x180016381  sar     r8, 3
0x180016385  lea     r9, ?DynamicTimeZoneCompare@@YA_NAEAV?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@0@Z; DynamicTimeZoneCompare(std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> &,std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> &)
0x18001638c  call    ??$_Sort_unchecked@PEAV?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@std@@P6A_NAEAV12@0@Z@std@@YAXPEAV?$unique_ptr@U_TIME_DYNAMIC_ZONE_INFORMATION@@U?$default_delete@U_TIME_DYNAMIC_ZONE_INFORMATION@@@std@@@0@0_JP6A_NAEAV10@2@Z@Z; std::_Sort_unchecked<std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> *,bool (*)(std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> &,std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> &)>(std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> *,std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> *,__int64,bool (*)(std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> &,std::unique_ptr<_TIME_DYNAMIC_ZONE_INFORMATION> &))
0x180016391  mov     rbx, [r14+70h]
0x180016395  cmp     rbx, [r14+78h]
0x180016399  jnb     short loc_180016403
0x18001639b  xor     ecx, ecx; string
0x18001639d  call    cs:__imp_WindowsDeleteString
0x1800163a3  mov     [rsp+440h+string], 0
0x1800163ac  lea     rax, [rsp+440h+string]
0x1800163b1  mov     [rsp+440h+phkResult], rax; HSTRING *
0x1800163b6  mov     r9, [rbx]; struct _TIME_DYNAMIC_ZONE_INFORMATION *
0x1800163b9  lea     r8, [rbp+340h+Buffer]; unsigned __int16 *
0x1800163c0  mov     rdx, [rsp+440h+var_400]; HKEY
0x1800163c5  call    ?GetTimeZoneDisplayName@TimeZoneSettingsImpl@System@Windows@@AEAAJPEAUHKEY__@@PEBGQEAU_TIME_DYNAMIC_ZONE_INFORMATION@@PEAPEAUHSTRING__@@@Z; Windows::System::TimeZoneSettingsImpl::GetTimeZoneDisplayName(HKEY__ *,ushort const *,_TIME_DYNAMIC_ZONE_INFORMATION * const,HSTRING__ * *)
0x1800163ca  mov     edi, eax
0x1800163cc  test    eax, eax
0x1800163ce  js      short loc_1800163F7
0x1800163d0  mov     rcx, [r14+68h]
0x1800163d4  mov     rdx, [rcx]
0x1800163d7  mov     rax, [rdx+68h]
0x1800163db  mov     rdx, [rsp+440h+string]
0x1800163e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163e5  nop
0x1800163e6  mov     rcx, [rsp+440h+string]; string
0x1800163eb  call    cs:__imp_WindowsDeleteString
0x1800163f1  add     rbx, 8
0x1800163f5  jmp     short loc_180016395
0x1800163f7  mov     rcx, [rsp+440h+string]; string
0x1800163fc  call    cs:__imp_WindowsDeleteString
0x180016402  nop
0x180016403  lea     rax, ??_7?$HandleT@URegistryKeyTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable'
0x18001640a  mov     [rsp+440h+var_408], rax
0x18001640f  cmp     [rsp+440h+var_400], 0
0x180016415  jz      short loc_18001644A
0x180016417  lea     rcx, [rsp+440h+var_408]
0x18001641c  call    ?InternalClose@?$HandleT@URegistryKeyTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::InternalClose(void)
0x180016421  test    al, al
0x180016423  jnz     short loc_18001644A
0x180016425  call    cs:__imp_GetLastError
0x18001642b  test    eax, eax
0x18001642d  jle     short loc_180016437
0x18001642f  movzx   eax, ax
0x180016432  or      eax, 80070000h
0x180016437  xor     r9d, r9d; lpArguments
0x18001643a  xor     r8d, r8d; nNumberOfArguments
0x18001643d  lea     edx, [r9+1]; dwExceptionFlags
0x180016441  mov     ecx, eax; dwExceptionCode
0x180016443  call    cs:__imp_RaiseException
0x180016449  int     3; Trap to Debugger
0x18001644a  mov     eax, edi
0x18001644c  mov     rcx, [rbp+340h+var_30]
0x180016453  xor     rcx, rsp; StackCookie
0x180016456  call    __security_check_cookie
0x18001645b  add     rsp, 428h
0x180016462  pop     r14
0x180016464  pop     rdi
0x180016465  pop     rbx
0x180016466  pop     rbp
0x180016467  retn
```
