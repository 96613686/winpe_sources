# RadioInstance::SetRadioState(int)

- ea: `0x180015da0`
- end: `0x180016080`
- name: `?SetRadioState@RadioInstance@@UEAAJH@Z`
- size: `736`
- prototype: `__int64 __fastcall(RadioInstance *this, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180016090`

## callees

- `0x180001404`
- `0x1800042b0`
- `0x1800088e0`
- `0x18000b814`
- `0x18000be90`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x1800132c0`
- `0x180015da0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015dd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015dd5`

## string_xrefs

- `0x180015ffa`: `Updated Radio State`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall RadioInstance::SetRadioState(RadioInstance *this, unsigned int a2)
{
  char *v4; // rbx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  __int64 v9; // rcx
  char v10; // si
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  const char *v16; // rcx
  const char *v17; // rcx
  __int64 v18; // rcx
  int v20; // [rsp+20h] [rbp-59h]
  int v21; // [rsp+28h] [rbp-51h]
  _DWORD v22[2]; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v23[5]; // [rsp+68h] [rbp-11h] BYREF
  __int128 v24; // [rsp+90h] [rbp+17h] BYREF
  char *v25; // [rsp+A0h] [rbp+27h] BYREF
  const char *v26; // [rsp+A8h] [rbp+2Fh] BYREF

  v4 = (char *)this + 40;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v25 = v4;
  if ( !*((_BYTE *)this + 105) )
  {
    if ( (unsigned int)dword_180037050 > 4 )
    {
      v26 = "UI is disabled, not taking any action";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v5,
        (unsigned int)word_18002E5AA,
        v6,
        v7,
        (__int64)&v26);
    }
    v8 = -2147418113;
    goto LABEL_26;
  }
  *((_BYTE *)this + 106) = 0;
  v8 = -2147019873;
  v9 = *((_QWORD *)this + 10);
  if ( v9 )
  {
    v10 = a2 != 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, char *, bool, _DWORD))(*(_QWORD *)v9 + 24LL))(
           v9,
           3,
           *((_QWORD *)this + 14),
           *((_QWORD *)this + 4),
           (char *)this + 16,
           a2 != 0,
           0);
    if ( v8 >= 0 )
    {
      if ( (a2 != 0) == *((_BYTE *)this + 104) )
      {
        v10 = *((_BYTE *)this + 104);
      }
      else
      {
        *((_BYTE *)this + 104) = v10;
        v11 = *((_DWORD *)this + 22) & 6;
        if ( !a2 )
          v11 |= 1u;
        *((_DWORD *)this + 22) = v11;
      }
      *((_BYTE *)this + 105) = 0;
      ++*((_DWORD *)this + 23);
      LOBYTE(v21) = 0;
      LOBYTE(v20) = v10;
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int, int, int))(**((_QWORD **)this + 10) + 32LL))(
             *((_QWORD *)this + 10),
             2,
             0,
             *((_QWORD *)this + 14),
             v20,
             v21,
             1);
    }
    v22[0] = 0;
    RadioInstance::GetMediaType(this, (enum _RADIO_INSTANCE_MEDIA_TYPE *)v22);
    if ( ((v22[0] - 1) & 0xFFFFFFFD) == 0 )
    {
      v26 = 0;
      v12 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, const char **))this + 10))(
              *((_QWORD *)this + 10),
              &GUID_e1ca5ff8_f674_4a99_831e_727e1e31504b,
              &v26);
      v8 = v12;
      if ( v12 < 0 )
      {
        if ( v12 == -2147467262 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (unsigned int)dword_180037050 > 2 )
        {
          v22[0] = v8;
          v23[0] = "QueryInterface<IUIRadioManager2> failed, could not inform RadioManager of a power change";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned int)&unk_18002E568,
            v14,
            v15,
            (__int64)v23,
            (__int64)v22);
        }
        v16 = v26;
        if ( v26 )
        {
          v26 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v16 + 16LL))(v16);
        }
        goto LABEL_26;
      }
      v24 = *((_OWORD *)this + 8);
      (*(void (__fastcall **)(const char *, __int128 *, _QWORD))(*(_QWORD *)v26 + 72LL))(v26, &v24, a2);
      v17 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
  }
  if ( (unsigned int)dword_180037050 > 4 )
  {
    v22[0] = v8;
    v22[1] = a2;
    LODWORD(v23[0]) = *((_DWORD *)this + 23);
    v23[1] = *((_QWORD *)this + 15);
    v23[2] = RmGuidToMediaTypeString((const struct _GUID *)this + 8);
    v23[3] = v18;
    *(_QWORD *)&v24 = "Updated Radio State";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v18,
      &word_18002E4DE);
  }
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015da0  mov     [rsp-8+arg_10], rbx
0x180015da5  mov     [rsp-8+arg_18], rsi
0x180015daa  push    rbp
0x180015dab  push    rdi
0x180015dac  push    r14
0x180015dae  lea     rbp, [rsp-47h]
0x180015db3  sub     rsp, 0C0h
0x180015dba  mov     rax, cs:__security_cookie
0x180015dc1  xor     rax, rsp
0x180015dc4  mov     [rbp+57h+var_20], rax
0x180015dc8  mov     r14d, edx
0x180015dcb  mov     rdi, rcx
0x180015dce  lea     rbx, [rcx+28h]
0x180015dd2  mov     rcx, rbx; lpCriticalSection
0x180015dd5  call    cs:__imp_EnterCriticalSection
0x180015ddb  mov     [rbp+57h+var_30], rbx
0x180015ddf  cmp     byte ptr [rdi+69h], 0
0x180015de3  jnz     short loc_180015E1A
0x180015de5  mov     eax, cs:dword_180037050
0x180015deb  cmp     eax, 4
0x180015dee  jbe     short loc_180015E10
0x180015df0  lea     rax, aUiIsDisabledNo; "UI is disabled, not taking any action"
0x180015df7  mov     [rbp+57h+var_28], rax
0x180015dfb  lea     rax, [rbp+57h+var_28]
0x180015dff  mov     [rsp+0D0h+var_B0], rax
0x180015e04  lea     rdx, word_18002E5AA
0x180015e0b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180015e10  mov     ebx, 8000FFFFh
0x180015e15  jmp     loc_180016051
0x180015e1a  mov     byte ptr [rdi+6Ah], 0
0x180015e1e  mov     ebx, 8007139Fh
0x180015e23  mov     rcx, [rdi+50h]
0x180015e27  test    rcx, rcx
0x180015e2a  jz      loc_180015FC2
0x180015e30  test    r14d, r14d
0x180015e33  setnz   sil
0x180015e37  mov     rax, [rcx]
0x180015e3a  lea     rdx, [rdi+10h]
0x180015e3e  mov     dword ptr [rsp+0D0h+var_A0], 0
0x180015e46  mov     byte ptr [rsp+0D0h+var_A8], sil
0x180015e4b  mov     [rsp+0D0h+var_B0], rdx
0x180015e50  mov     r9, [rdi+20h]
0x180015e54  mov     r8, [rdi+70h]
0x180015e58  mov     edx, 3
0x180015e5d  mov     rax, [rax+18h]
0x180015e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e66  mov     ebx, eax
0x180015e68  test    eax, eax
0x180015e6a  js      short loc_180015ECE
0x180015e6c  movzx   ecx, byte ptr [rdi+68h]
0x180015e70  xor     eax, eax
0x180015e72  test    r14d, r14d
0x180015e75  setnz   al
0x180015e78  cmp     eax, ecx
0x180015e7a  jz      short loc_180015E95
0x180015e7c  mov     [rdi+68h], sil
0x180015e80  mov     eax, [rdi+58h]
0x180015e83  and     eax, 6
0x180015e86  test    r14d, r14d
0x180015e89  jz      short loc_180015E90
0x180015e8b  mov     [rdi+58h], eax
0x180015e8e  jmp     short loc_180015E98
0x180015e90  or      eax, 1
0x180015e93  jmp     short loc_180015E8B
0x180015e95  mov     sil, cl
0x180015e98  mov     byte ptr [rdi+69h], 0
0x180015e9c  inc     dword ptr [rdi+5Ch]
0x180015e9f  mov     rcx, [rdi+50h]
0x180015ea3  mov     rax, [rcx]
0x180015ea6  mov     dword ptr [rsp+0D0h+var_A0], 1
0x180015eae  mov     byte ptr [rsp+0D0h+var_A8], 0
0x180015eb3  mov     byte ptr [rsp+0D0h+var_B0], sil
0x180015eb8  mov     r9, [rdi+70h]
0x180015ebc  xor     r8d, r8d
0x180015ebf  lea     edx, [r8+2]
0x180015ec3  mov     rax, [rax+20h]
0x180015ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ecc  mov     ebx, eax
0x180015ece  mov     [rbp+57h+var_70], 0
0x180015ed5  lea     rdx, [rbp+57h+var_70]; enum _RADIO_INSTANCE_MEDIA_TYPE *
0x180015ed9  mov     rcx, rdi; this
0x180015edc  call    ?GetMediaType@RadioInstance@@UEAAJPEAW4_RADIO_INSTANCE_MEDIA_TYPE@@@Z; RadioInstance::GetMediaType(_RADIO_INSTANCE_MEDIA_TYPE *)
0x180015ee1  mov     eax, [rbp+57h+var_70]
0x180015ee4  dec     eax
0x180015ee6  test    eax, 0FFFFFFFDh
0x180015eeb  jnz     loc_180015FC2
0x180015ef1  mov     [rbp+57h+var_28], 0
0x180015ef9  mov     rcx, [rdi+50h]
0x180015efd  mov     rax, [rcx]
0x180015f00  lea     r8, [rbp+57h+var_28]
0x180015f04  lea     rdx, _GUID_e1ca5ff8_f674_4a99_831e_727e1e31504b
0x180015f0b  mov     rax, [rax]
0x180015f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f13  mov     ebx, eax
0x180015f15  test    eax, eax
0x180015f17  jns     short loc_180015F80
0x180015f19  cmp     eax, 80004002h
0x180015f1e  jnz     short loc_180015F25
0x180015f20  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015f25  mov     eax, cs:dword_180037050
0x180015f2b  cmp     eax, 2
0x180015f2e  jbe     short loc_180015F5D
0x180015f30  mov     [rbp+57h+var_70], ebx
0x180015f33  lea     rax, aQueryinterface; "QueryInterface<IUIRadioManager2> failed"...
0x180015f3a  mov     [rbp+57h+var_68], rax
0x180015f3e  lea     rax, [rbp+57h+var_70]
0x180015f42  mov     [rsp+0D0h+var_A8], rax
0x180015f47  lea     rax, [rbp+57h+var_68]
0x180015f4b  mov     [rsp+0D0h+var_B0], rax
0x180015f50  lea     rdx, unk_18002E568
0x180015f57  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180015f5c  nop
0x180015f5d  mov     rcx, [rbp+57h+var_28]
0x180015f61  test    rcx, rcx
0x180015f64  jz      short loc_180015F7B
0x180015f66  mov     [rbp+57h+var_28], 0
0x180015f6e  mov     rax, [rcx]
0x180015f71  mov     rax, [rax+10h]
0x180015f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f7a  nop
0x180015f7b  jmp     loc_180016051
0x180015f80  mov     rcx, [rbp+57h+var_28]
0x180015f84  movups  xmm0, xmmword ptr [rdi+80h]
0x180015f8b  movdqu  [rbp+57h+var_40], xmm0
0x180015f90  mov     rax, [rcx]
0x180015f93  mov     r8d, r14d
0x180015f96  lea     rdx, [rbp+57h+var_40]
0x180015f9a  mov     rax, [rax+48h]
0x180015f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fa3  nop
0x180015fa4  mov     rcx, [rbp+57h+var_28]
0x180015fa8  test    rcx, rcx
0x180015fab  jz      short loc_180015FC2
0x180015fad  mov     [rbp+57h+var_28], 0
0x180015fb5  mov     rax, [rcx]
0x180015fb8  mov     rax, [rax+10h]
0x180015fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fc1  nop
0x180015fc2  mov     eax, cs:dword_180037050
0x180015fc8  cmp     eax, 4
0x180015fcb  jbe     loc_180016051
0x180015fd1  mov     [rbp+57h+var_70], ebx
0x180015fd4  mov     [rbp+57h+var_6C], r14d
0x180015fd8  mov     eax, [rdi+5Ch]
0x180015fdb  mov     dword ptr [rbp+57h+var_68], eax
0x180015fde  mov     rax, [rdi+78h]
0x180015fe2  mov     [rbp+57h+var_60], rax
0x180015fe6  lea     rcx, [rdi+80h]; struct _GUID *
0x180015fed  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180015ff2  mov     [rbp+57h+var_58], rax
0x180015ff6  mov     [rbp+57h+var_50], rcx
0x180015ffa  lea     rax, aUpdatedRadioSt; "Updated Radio State"
0x180016001  mov     qword ptr [rbp+57h+var_40], rax
0x180016005  lea     rax, [rbp+57h+var_70]
0x180016009  mov     [rsp+0D0h+var_80], rax
0x18001600e  lea     rax, [rbp+57h+var_6C]
0x180016012  mov     [rsp+0D0h+var_88], rax
0x180016017  lea     rax, [rbp+57h+var_68]
0x18001601b  mov     [rsp+0D0h+var_90], rax
0x180016020  lea     rax, [rbp+57h+var_60]
0x180016024  mov     [rsp+0D0h+var_98], rax
0x180016029  lea     rax, [rbp+57h+var_58]
0x18001602d  mov     [rsp+0D0h+var_A0], rax
0x180016032  lea     rax, [rbp+57h+var_50]
0x180016036  mov     [rsp+0D0h+var_A8], rax
0x18001603b  lea     rax, [rbp+57h+var_40]
0x18001603f  mov     [rsp+0D0h+var_B0], rax
0x180016044  lea     rdx, word_18002E4DE
0x18001604b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016050  nop
0x180016051  lea     rcx, [rbp+57h+var_30]
0x180016055  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001605a  mov     eax, ebx
0x18001605c  mov     rcx, [rbp+57h+var_20]
0x180016060  xor     rcx, rsp; StackCookie
0x180016063  call    __security_check_cookie
0x180016068  lea     r11, [rsp+0D0h+var_10]
0x180016070  mov     rbx, [r11+30h]
0x180016074  mov     rsi, [r11+38h]
0x180016078  mov     rsp, r11
0x18001607b  pop     r14
0x18001607d  pop     rdi
0x18001607e  pop     rbp
0x18001607f  retn
```
