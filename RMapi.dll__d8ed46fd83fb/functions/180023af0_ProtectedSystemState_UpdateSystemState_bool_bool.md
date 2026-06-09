# ProtectedSystemState::UpdateSystemState(bool,bool)

- ea: `0x180023af0`
- end: `0x180023c32`
- name: `?UpdateSystemState@ProtectedSystemState@@QEAAX_N0@Z`
- size: `322`
- prototype: `void __fastcall(ProtectedSystemState *__hidden this, bool, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002036c`

## callees

- `0x180002ec0`
- `0x180006a0c`
- `0x180006c2c`
- `0x180008278`
- `0x18000970c`
- `0x18000a6a0`
- `0x18000aec8`
- `0x18000c0e0`
- `0x18000c15c`
- `0x18000c2a4`
- `0x18002378c`
- `0x180023af0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023b12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023b12`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180023bed`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180023bed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall ProtectedSystemState::UpdateSystemState(ProtectedSystemState *this, unsigned __int8 a2, char a3)
{
  int v4; // r15d
  const wchar_t *v6; // rdx
  char v7; // al
  HKEY *v8; // rbx
  __int64 PersistentRegPathRMRadioState; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  HKEY *KeyRW; // rax
  HKEY *v13; // rsi
  unsigned int v14; // esi
  RMAPI *v15; // rcx
  char v16[8]; // [rsp+20h] [rbp-58h] BYREF
  ProtectedSystemState *v17; // [rsp+28h] [rbp-50h]
  char *v18; // [rsp+30h] [rbp-48h]
  ProtectedSystemState *v19; // [rsp+38h] [rbp-40h] BYREF
  __int64 v20[3]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int64 v21; // [rsp+58h] [rbp-20h]

  v4 = a2;
  v17 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v19 = this;
  v18 = (char *)this + 48;
  v7 = *((_BYTE *)this + 48);
  *((_BYTE *)this + 48) = v4;
  *((_BYTE *)this + 50) = a3;
  *((_BYTE *)this + 51) = 1;
  if ( (_BYTE)v4 != v7 )
  {
    v8 = (HKEY *)((char *)this + 112);
    if ( !*((_QWORD *)this + 14) )
    {
      PersistentRegPathRMRadioState = RMAPI::GetPersistentRegPathRMRadioState(v20);
      v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(PersistentRegPathRMRadioState);
      KeyRW = (HKEY *)WcmCommon::Registry::CreateKeyRW(v16, v11, v10);
      v13 = KeyRW;
      if ( v8 != KeyRW )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          (char *)this + 112,
          *KeyRW);
        *v13 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v16);
      v6 = (const wchar_t *)v21;
      if ( v21 > 7 )
        std::_Deallocate<16>(v20[0], 2 * v21 + 2);
    }
    v14 = v4 ^ 1;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids, v14);
    WcmCommon::Registry::Key::SetDwordValue((HKEY *)this + 14, v6, v14);
    RegFlushKey(*v8);
    LOBYTE(v15) = *((_BYTE *)this + 48);
    RMAPI::RefreshHID(v15);
  }
  ProtectedSystemState::RefreshSysUIEnabled(this);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v19);
}

```

## disassembly

```asm
0x180023af0  mov     [rsp+arg_8], rbx
0x180023af5  mov     [rsp+arg_10], rsi
0x180023afa  push    rdi
0x180023afb  push    r14
0x180023afd  push    r15
0x180023aff  sub     rsp, 60h
0x180023b03  mov     bl, r8b
0x180023b06  movzx   r15d, dl
0x180023b0a  mov     rdi, rcx
0x180023b0d  mov     [rsp+78h+var_50], rcx
0x180023b12  call    cs:__imp_EnterCriticalSection
0x180023b18  mov     [rsp+78h+var_40], rdi
0x180023b1d  lea     r14, [rdi+30h]
0x180023b21  mov     [rsp+78h+var_48], r14
0x180023b26  mov     al, [r14]
0x180023b29  mov     [r14], r15b
0x180023b2c  mov     [rdi+32h], bl
0x180023b2f  mov     byte ptr [rdi+33h], 1
0x180023b33  cmp     r15b, al
0x180023b36  jz      loc_180023C08
0x180023b3c  lea     rbx, [rdi+70h]
0x180023b40  cmp     qword ptr [rbx], 0
0x180023b44  jnz     short loc_180023BA8
0x180023b46  lea     rcx, [rsp+78h+var_38]
0x180023b4b  call    ?GetPersistentRegPathRMRadioState@RMAPI@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RMAPI::GetPersistentRegPathRMRadioState(void)
0x180023b50  nop
0x180023b51  mov     rcx, rax
0x180023b54  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180023b59  mov     r8, rax
0x180023b5c  lea     rcx, [rsp+78h+var_58]
0x180023b61  call    ?CreateKeyRW@Registry@WcmCommon@@YA?AVKey@12@QEAUHKEY__@@QEB_W@Z; WcmCommon::Registry::CreateKeyRW(HKEY__ * const,wchar_t const * const)
0x180023b66  mov     rsi, rax
0x180023b69  cmp     rbx, rax
0x180023b6c  jz      short loc_180023B80
0x180023b6e  mov     rdx, [rax]
0x180023b71  mov     rcx, rbx
0x180023b74  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180023b79  mov     qword ptr [rsi], 0
0x180023b80  lea     rcx, [rsp+78h+var_58]
0x180023b85  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180023b8a  nop
0x180023b8b  mov     rdx, [rsp+78h+var_20]
0x180023b90  cmp     rdx, 7
0x180023b94  jbe     short loc_180023BA8
0x180023b96  lea     rdx, ds:2[rdx*2]
0x180023b9e  mov     rcx, [rsp+78h+var_38]
0x180023ba3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180023ba8  mov     esi, r15d
0x180023bab  xor     esi, 1
0x180023bae  lea     rax, WPP_GLOBAL_Control
0x180023bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180023bbc  cmp     rcx, rax
0x180023bbf  jz      short loc_180023BDF
0x180023bc1  test    byte ptr [rcx+1Ch], 4
0x180023bc5  jz      short loc_180023BDF
0x180023bc7  mov     edx, 0Eh
0x180023bcc  mov     r9d, esi
0x180023bcf  lea     r8, WPP_690cbe3f8c3d3ba27be350898e12e7bc_Traceguids
0x180023bd6  mov     rcx, [rcx+10h]
0x180023bda  call    WPP_SF_d
0x180023bdf  mov     r8d, esi; unsigned int
0x180023be2  mov     rcx, rbx; this
0x180023be5  call    ?SetDwordValue@Key@Registry@WcmCommon@@QEAAXQEB_WK@Z; WcmCommon::Registry::Key::SetDwordValue(wchar_t const * const,ulong)
0x180023bea  mov     rcx, [rbx]; hKey
0x180023bed  call    cs:__imp_RegFlushKey
0x180023bf3  nop
0x180023bf4  jmp     short loc_180023C00
0x180023bf6  mov     rdi, [rsp+78h+var_50]
0x180023bfb  mov     r14, [rsp+78h+var_48]
0x180023c00  mov     cl, [r14]; this
0x180023c03  call    ?RefreshHID@RMAPI@@YAX_N@Z; RMAPI::RefreshHID(bool)
0x180023c08  mov     rcx, rdi; this
0x180023c0b  call    ?RefreshSysUIEnabled@ProtectedSystemState@@AEAAXXZ; ProtectedSystemState::RefreshSysUIEnabled(void)
0x180023c10  nop
0x180023c11  lea     rcx, [rsp+78h+var_40]
0x180023c16  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180023c1b  nop
0x180023c1c  lea     r11, [rsp+78h+var_18]
0x180023c21  mov     rbx, [r11+28h]
0x180023c25  mov     rsi, [r11+30h]
0x180023c29  mov     rsp, r11
0x180023c2c  pop     r15
0x180023c2e  pop     r14
0x180023c30  pop     rdi
0x180023c31  retn
```
