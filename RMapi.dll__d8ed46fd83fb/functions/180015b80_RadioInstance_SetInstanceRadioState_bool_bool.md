# RadioInstance::SetInstanceRadioState(bool,bool)

- ea: `0x180015b80`
- end: `0x180015d8f`
- name: `?SetInstanceRadioState@RadioInstance@@UEAAJ_N0@Z`
- size: `527`
- prototype: `__int64 __fastcall(unsigned __int64 this, char, unsigned __int8)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callees

- `0x18000154c`
- `0x1800042b0`
- `0x1800088e0`
- `0x18000b814`
- `0x18000c2a4`
- `0x180015b80`
- `0x180016940`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015ba7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015ba7`

## string_xrefs

- `0x180015d4c`: `Radio state is already at desired state`

## pseudocode

```c
__int64 __fastcall RadioInstance::SetInstanceRadioState(unsigned __int64 this, char a2, unsigned __int8 a3)
{
  int v3; // r15d
  char *v6; // rbx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int v10; // ebx
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // edx
  const char *v16; // rax
  __int64 v17; // rcx
  const char *v18; // rax
  char *v19; // rdx
  _QWORD *v21; // [rsp+20h] [rbp-60h]
  const char **v22; // [rsp+28h] [rbp-58h]
  __int64 *v23; // [rsp+30h] [rbp-50h]
  int v24; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v25[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v26; // [rsp+68h] [rbp-18h] BYREF
  const char *v27; // [rsp+70h] [rbp-10h] BYREF
  char *v28; // [rsp+78h] [rbp-8h] BYREF

  v3 = a3;
  v6 = (char *)(this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 24));
  v28 = v6;
  if ( a2 == *(_BYTE *)(this + 88) )
  {
    v10 = 0;
    if ( (unsigned int)dword_180037050 > 4 )
    {
      v25[0] = "Radio state is already at desired state";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v7,
        (unsigned int)&word_18002E106,
        v8,
        v9,
        (__int64)v25);
    }
  }
  else
  {
    v10 = -2147019873;
    v11 = *(_QWORD *)(this + 64);
    if ( v11 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned __int64, char, _DWORD))(*(_QWORD *)v11 + 24LL))(
              v11,
              3,
              *(_QWORD *)(this + 96),
              *(_QWORD *)(this + 16),
              this & -(__int64)(this != 16),
              a2,
              0);
      if ( v10 < 0 )
      {
        if ( (unsigned int)dword_180037050 > 2 )
        {
          v18 = "IUIRadioManagerInternal::InsertJob(RM_JOB::SET_INSTANCE_RADIO) failed";
          v19 = &byte_18002E147;
          goto LABEL_15;
        }
      }
      else
      {
        *(_BYTE *)(this + 88) = a2;
        v15 = *(_DWORD *)(this + 72) & 6;
        if ( !a2 )
          v15 = *(_DWORD *)(this + 72) & 6 | 1;
        *(_DWORD *)(this + 72) = v15;
        *(_BYTE *)(this + 90) = 0;
        ++*(_DWORD *)(this + 76);
        RadioInstance::_UpdateUIEnabled((RadioInstance *)(this - 16));
        if ( (unsigned int)dword_180037050 > 4 )
        {
          v24 = *(_DWORD *)(this + 76);
          v16 = "enabled";
          if ( !a2 )
            v16 = "disabled";
          v25[1] = v16;
          v26 = *(_QWORD *)(this + 104);
          v27 = RmGuidToMediaTypeString((const struct _GUID *)(this + 112));
          v25[0] = v17;
          v23 = &v26;
          v22 = &v27;
          v21 = v25;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v17,
            byte_18002E1DB);
        }
        LODWORD(v23) = v3;
        LOBYTE(v22) = *(_BYTE *)(this + 89);
        LOBYTE(v21) = *(_BYTE *)(this + 88);
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD *, const char **, __int64 *))(**(_QWORD **)(this + 64) + 32LL))(
                *(_QWORD *)(this + 64),
                2,
                0,
                *(_QWORD *)(this + 96),
                v21,
                v22,
                v23);
        if ( v10 < 0 && (unsigned int)dword_180037050 > 2 )
        {
          v18 = "IUIRadioManagerInternal::NotifySinkListeners(RM_NOTIFY::INSTANCE_RADIO_CHANGE) failed";
          v19 = byte_18002E191;
LABEL_15:
          v25[0] = v18;
          v24 = v10;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v12,
            (_DWORD)v19,
            v13,
            v14,
            (__int64)v25,
            (__int64)&v24);
        }
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180015b80  mov     [rsp-28h+arg_10], rbx
0x180015b85  push    rbp
0x180015b86  push    rsi
0x180015b87  push    rdi
0x180015b88  push    r14
0x180015b8a  push    r15
0x180015b8c  mov     rbp, rsp
0x180015b8f  sub     rsp, 80h
0x180015b96  movzx   r15d, r8b
0x180015b9a  mov     sil, dl
0x180015b9d  mov     rdi, rcx
0x180015ba0  lea     rbx, [rcx+18h]
0x180015ba4  mov     rcx, rbx; lpCriticalSection
0x180015ba7  call    cs:__imp_EnterCriticalSection
0x180015bad  mov     [rbp+var_8], rbx
0x180015bb1  cmp     sil, [rdi+58h]
0x180015bb5  jz      loc_180015D3F
0x180015bbb  mov     ebx, 8007139Fh
0x180015bc0  mov     rcx, [rdi+40h]
0x180015bc4  test    rcx, rcx
0x180015bc7  jz      loc_180015D6D
0x180015bcd  mov     rdx, [rcx]
0x180015bd0  lea     rax, [rdi-10h]
0x180015bd4  neg     rax
0x180015bd7  sbb     r8, r8
0x180015bda  and     r8, rdi
0x180015bdd  mov     rax, [rdx+18h]
0x180015be1  mov     dword ptr [rsp+80h+var_50], 0
0x180015be9  mov     byte ptr [rsp+80h+var_58], sil
0x180015bee  mov     [rsp+80h+var_60], r8
0x180015bf3  mov     r9, [rdi+10h]
0x180015bf7  mov     r8, [rdi+60h]
0x180015bfb  mov     edx, 3
0x180015c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c05  mov     ebx, eax
0x180015c07  test    eax, eax
0x180015c09  js      loc_180015D06
0x180015c0f  mov     [rdi+58h], sil
0x180015c13  mov     edx, [rdi+48h]
0x180015c16  and     edx, 6
0x180015c19  mov     eax, edx
0x180015c1b  or      eax, 1
0x180015c1e  test    sil, sil
0x180015c21  cmovz   edx, eax
0x180015c24  mov     [rdi+48h], edx
0x180015c27  mov     byte ptr [rdi+5Ah], 0
0x180015c2b  inc     dword ptr [rdi+4Ch]
0x180015c2e  lea     rcx, [rdi-10h]; this
0x180015c32  call    ?_UpdateUIEnabled@RadioInstance@@AEAAXXZ; RadioInstance::_UpdateUIEnabled(void)
0x180015c37  mov     eax, cs:dword_180037050
0x180015c3d  cmp     eax, 4
0x180015c40  jbe     short loc_180015CB3
0x180015c42  mov     eax, [rdi+4Ch]
0x180015c45  mov     [rbp+var_30], eax
0x180015c48  lea     rcx, aDisabled_0; "disabled"
0x180015c4f  lea     rax, aEnabled; "enabled"
0x180015c56  test    sil, sil
0x180015c59  cmovz   rax, rcx
0x180015c5d  mov     [rbp+var_20], rax
0x180015c61  mov     rax, [rdi+68h]
0x180015c65  mov     [rbp+var_18], rax
0x180015c69  lea     rcx, [rdi+70h]; struct _GUID *
0x180015c6d  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180015c72  mov     [rbp+var_10], rax
0x180015c76  mov     [rbp+var_28], rcx
0x180015c7a  lea     rax, [rbp+var_30]
0x180015c7e  mov     [rsp+80h+var_40], rax
0x180015c83  lea     rax, [rbp+var_20]
0x180015c87  mov     [rsp+80h+var_48], rax
0x180015c8c  lea     rax, [rbp+var_18]
0x180015c90  mov     [rsp+80h+var_50], rax
0x180015c95  lea     rax, [rbp+var_10]
0x180015c99  mov     [rsp+80h+var_58], rax
0x180015c9e  lea     rax, [rbp+var_28]
0x180015ca2  mov     [rsp+80h+var_60], rax
0x180015ca7  lea     rdx, byte_18002E1DB
0x180015cae  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@_W@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@_W@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180015cb3  mov     rcx, [rdi+40h]
0x180015cb7  mov     rax, [rcx]
0x180015cba  mov     dword ptr [rsp+80h+var_50], r15d
0x180015cbf  mov     dl, [rdi+59h]
0x180015cc2  mov     byte ptr [rsp+80h+var_58], dl
0x180015cc6  mov     dl, [rdi+58h]
0x180015cc9  mov     byte ptr [rsp+80h+var_60], dl
0x180015ccd  mov     r9, [rdi+60h]
0x180015cd1  xor     r8d, r8d
0x180015cd4  lea     edx, [r8+2]
0x180015cd8  mov     rax, [rax+20h]
0x180015cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ce1  mov     ebx, eax
0x180015ce3  test    eax, eax
0x180015ce5  jns     loc_180015D6D
0x180015ceb  mov     eax, cs:dword_180037050
0x180015cf1  cmp     eax, 2
0x180015cf4  jbe     short loc_180015D6D
0x180015cf6  lea     rax, aIuiradiomanage_0; "IUIRadioManagerInternal::NotifySinkList"...
0x180015cfd  lea     rdx, byte_18002E191
0x180015d04  jmp     short loc_180015D1F
0x180015d06  mov     eax, cs:dword_180037050
0x180015d0c  cmp     eax, 2
0x180015d0f  jbe     short loc_180015D6D
0x180015d11  lea     rax, aIuiradiomanage_1; "IUIRadioManagerInternal::InsertJob(RM_J"...
0x180015d18  lea     rdx, byte_18002E147
0x180015d1f  mov     [rbp+var_28], rax
0x180015d23  lea     rax, [rbp+var_30]
0x180015d27  mov     [rsp+80h+var_58], rax
0x180015d2c  lea     rax, [rbp+var_28]
0x180015d30  mov     [rsp+80h+var_60], rax
0x180015d35  mov     [rbp+var_30], ebx
0x180015d38  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180015d3d  jmp     short loc_180015D6D
0x180015d3f  xor     ebx, ebx
0x180015d41  mov     eax, cs:dword_180037050
0x180015d47  cmp     eax, 4
0x180015d4a  jbe     short loc_180015D6D
0x180015d4c  lea     rax, aRadioStateIsAl; "Radio state is already at desired state"
0x180015d53  mov     [rbp+var_28], rax
0x180015d57  lea     rax, [rbp+var_28]
0x180015d5b  mov     [rsp+80h+var_60], rax
0x180015d60  lea     rdx, word_18002E106
0x180015d67  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180015d6c  nop
0x180015d6d  lea     rcx, [rbp+var_8]
0x180015d71  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180015d76  mov     eax, ebx
0x180015d78  mov     rbx, [rsp+80h+arg_10]
0x180015d80  add     rsp, 80h
0x180015d87  pop     r15
0x180015d89  pop     r14
0x180015d8b  pop     rdi
0x180015d8c  pop     rsi
0x180015d8d  pop     rbp
0x180015d8e  retn
```
