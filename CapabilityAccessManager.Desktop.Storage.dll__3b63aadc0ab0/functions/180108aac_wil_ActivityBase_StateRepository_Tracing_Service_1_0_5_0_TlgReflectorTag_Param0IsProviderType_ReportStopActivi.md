# wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x180108aac`
- end: `0x180108d0d`
- name: `?ReportStopActivity@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `609`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180107bc8`
- `0x180108e8c`

## callees

- `0x180001efc`
- `0x180001ff8`
- `0x1800fb134`
- `0x180108aac`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180108c98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180108c98`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v19; // [rsp+A0h] [rbp-19h] BYREF
  int v20; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v21; // [rsp+A8h] [rbp-11h] BYREF
  int *v22; // [rsp+B0h] [rbp-9h] BYREF
  const char *v23; // [rsp+B8h] [rbp-1h] BYREF
  int *v24; // [rsp+C0h] [rbp+7h] BYREF
  const char *v25; // [rsp+C8h] [rbp+Fh] BYREF
  const char *v26; // [rsp+D0h] [rbp+17h] BYREF
  int *v27; // [rsp+D8h] [rbp+1Fh] BYREF
  const char *v28; // [rsp+E0h] [rbp+27h] BYREF
  const char *v29; // [rsp+E8h] [rbp+2Fh] BYREF
  int v30; // [rsp+120h] [rbp+67h] BYREF
  DWORD v31; // [rsp+128h] [rbp+6Fh] BYREF
  int *v32; // [rsp+130h] [rbp+77h] BYREF
  const char *v33; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = StateRepository::Tracing::Service::Provider();
      v8 = (__int64)v7;
      if ( *(_DWORD *)v7 > 2u )
      {
        v9 = *((_QWORD *)v7 + 3);
        if ( (*(_QWORD *)(v8 + 16) & 0x200000000000LL) != 0 && (v9 & 0x200000000000LL) == v9 )
        {
          v10 = a1[34];
          v22 = *(int **)(v6 + 120);
          v23 = *(const char **)(v6 + 112);
          v31 = *(_DWORD *)(v6 + 104);
          v24 = *(int **)(v6 + 96);
          v25 = *(const char **)(v6 + 88);
          v30 = *(_DWORD *)(v6 + 80);
          v26 = *(const char **)(v6 + 72);
          LODWORD(v32) = *(_DWORD *)(v6 + 32);
          v27 = *(int **)(v6 + 24);
          LODWORD(v33) = *(_DWORD *)v6;
          v28 = *(const char **)(v6 + 128);
          v19 = *(_DWORD *)(v6 + 64);
          v29 = *(const char **)(v6 + 56);
          v20 = *(_DWORD *)(v6 + 8);
          v21 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
            v8,
            (__int64)&word_18012AA46,
            v10 + 8,
            v8,
            (__int64)&v21,
            (__int64)&v20,
            &v29,
            (__int64)&v19,
            &v28,
            (__int64)&v33,
            &v27,
            (__int64)&v32,
            &v26,
            (__int64)&v30,
            &v25,
            &v24,
            (__int64)&v31,
            &v23,
            &v22);
        }
      }
    }
    else
    {
      v11 = StateRepository::Tracing::Service::Provider();
      v12 = (__int64)v11;
      if ( *(_DWORD *)v11 > 2u )
      {
        v13 = *((_QWORD *)v11 + 3);
        if ( (*(_QWORD *)(v12 + 16) & 0x200000000000LL) != 0 && (v13 & 0x200000000000LL) == v13 )
        {
          v14 = a1[34];
          v32 = *(int **)(v14 + 56);
          v33 = *(const char **)(v14 + 48);
          CurrentThreadId = GetCurrentThreadId();
          v16 = a1[34];
          v31 = CurrentThreadId;
          v30 = a2;
          v21 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
            v12,
            (__int64)byte_18012AB5D,
            v16 + 8,
            v17,
            (__int64)&v21,
            (__int64)&v30,
            (__int64)&v31,
            &v33,
            &v32);
        }
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x180108aac  push    rbp
0x180108aae  push    rbx
0x180108aaf  push    rsi
0x180108ab0  push    rdi
0x180108ab1  lea     rbp, [rsp-3Fh]
0x180108ab6  sub     rsp, 0F8h
0x180108abd  mov     esi, edx
0x180108abf  mov     rbx, rcx
0x180108ac2  test    edx, edx
0x180108ac4  jns     loc_180108CF3
0x180108aca  mov     rdi, [rcx+110h]
0x180108ad1  mov     eax, [rdi+48h]
0x180108ad4  test    eax, eax
0x180108ad6  jns     loc_180108C4C
0x180108adc  add     rdi, 50h ; 'P'
0x180108ae0  cmp     eax, [rdi+8]
0x180108ae3  jnz     loc_180108C4C
0x180108ae9  test    rdi, rdi
0x180108aec  jz      loc_180108C4C
0x180108af2  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x180108af7  mov     r9, rax
0x180108afa  mov     ecx, [rax]
0x180108afc  cmp     ecx, 2
0x180108aff  jbe     loc_180108CF3
0x180108b05  mov     rax, [rax+18h]
0x180108b09  mov     rdx, 200000000000h
0x180108b13  mov     rcx, [r9+10h]
0x180108b17  test    rdx, rcx
0x180108b1a  jz      loc_180108CF3
0x180108b20  mov     rcx, rax
0x180108b23  and     rcx, rdx
0x180108b26  cmp     rcx, rax
0x180108b29  jnz     loc_180108CF3
0x180108b2f  mov     rax, [rdi+78h]
0x180108b33  lea     rdx, word_18012AA46
0x180108b3a  mov     r8, [rbx+110h]
0x180108b41  mov     rcx, r9
0x180108b44  mov     [rbp+57h+var_60], rax
0x180108b48  add     r8, 8
0x180108b4c  mov     rax, [rdi+70h]
0x180108b50  mov     [rbp+57h+var_58], rax
0x180108b54  mov     eax, [rdi+68h]
0x180108b57  mov     [rbp+57h+arg_8], eax
0x180108b5a  mov     rax, [rdi+60h]
0x180108b5e  mov     [rbp+57h+var_50], rax
0x180108b62  mov     rax, [rdi+58h]
0x180108b66  mov     [rbp+57h+var_48], rax
0x180108b6a  mov     eax, [rdi+50h]
0x180108b6d  mov     [rbp+57h+arg_0], eax
0x180108b70  mov     rax, [rdi+48h]
0x180108b74  mov     [rbp+57h+var_40], rax
0x180108b78  mov     eax, [rdi+20h]
0x180108b7b  mov     dword ptr [rbp+57h+arg_10], eax
0x180108b7e  mov     rax, [rdi+18h]
0x180108b82  mov     [rbp+57h+var_38], rax
0x180108b86  mov     eax, [rdi]
0x180108b88  mov     dword ptr [rbp+57h+arg_18], eax
0x180108b8b  mov     rax, [rdi+80h]
0x180108b92  mov     [rbp+57h+var_30], rax
0x180108b96  mov     eax, [rdi+40h]
0x180108b99  mov     [rbp+57h+var_70], eax
0x180108b9c  mov     rax, [rdi+38h]
0x180108ba0  mov     [rbp+57h+var_28], rax
0x180108ba4  mov     eax, [rdi+8]
0x180108ba7  mov     [rbp+57h+var_6C], eax
0x180108baa  lea     rax, [rbp+57h+var_60]
0x180108bae  mov     [rsp+110h+var_80], rax
0x180108bb6  lea     rax, [rbp+57h+var_58]
0x180108bba  mov     [rsp+110h+var_88], rax
0x180108bc2  lea     rax, [rbp+57h+arg_8]
0x180108bc6  mov     [rsp+110h+var_90], rax
0x180108bce  lea     rax, [rbp+57h+var_50]
0x180108bd2  mov     [rsp+110h+var_98], rax
0x180108bd7  lea     rax, [rbp+57h+var_48]
0x180108bdb  mov     [rsp+110h+var_A0], rax
0x180108be0  lea     rax, [rbp+57h+arg_0]
0x180108be4  mov     [rsp+110h+var_A8], rax
0x180108be9  lea     rax, [rbp+57h+var_40]
0x180108bed  mov     [rsp+110h+var_B0], rax
0x180108bf2  lea     rax, [rbp+57h+arg_10]
0x180108bf6  mov     [rsp+110h+var_B8], rax
0x180108bfb  lea     rax, [rbp+57h+var_38]
0x180108bff  mov     [rsp+110h+var_C0], rax
0x180108c04  lea     rax, [rbp+57h+arg_18]
0x180108c08  mov     [rsp+110h+var_C8], rax
0x180108c0d  lea     rax, [rbp+57h+var_30]
0x180108c11  mov     [rsp+110h+var_D0], rax
0x180108c16  lea     rax, [rbp+57h+var_70]
0x180108c1a  mov     [rsp+110h+var_D8], rax
0x180108c1f  lea     rax, [rbp+57h+var_28]
0x180108c23  mov     [rsp+110h+var_E0], rax
0x180108c28  lea     rax, [rbp+57h+var_6C]
0x180108c2c  mov     [rsp+110h+var_E8], rax
0x180108c31  lea     rax, [rbp+57h+var_68]
0x180108c35  mov     [rsp+110h+var_F0], rax
0x180108c3a  mov     [rbp+57h+var_68], 1000000h
0x180108c42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180108c47  jmp     loc_180108CF3
0x180108c4c  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x180108c51  mov     rdi, rax
0x180108c54  mov     ecx, [rax]
0x180108c56  cmp     ecx, 2
0x180108c59  jbe     loc_180108CF3
0x180108c5f  mov     rax, [rax+18h]
0x180108c63  mov     rdx, 200000000000h
0x180108c6d  mov     rcx, [rdi+10h]
0x180108c71  test    rdx, rcx
0x180108c74  jz      short loc_180108CF3
0x180108c76  mov     rcx, rax
0x180108c79  and     rcx, rdx
0x180108c7c  cmp     rcx, rax
0x180108c7f  jnz     short loc_180108CF3
0x180108c81  mov     rcx, [rbx+110h]
0x180108c88  mov     rax, [rcx+38h]
0x180108c8c  mov     [rbp+57h+arg_10], rax
0x180108c90  mov     rax, [rcx+30h]
0x180108c94  mov     [rbp+57h+arg_18], rax
0x180108c98  call    cs:__imp_GetCurrentThreadId
0x180108c9e  mov     r8, [rbx+110h]
0x180108ca5  lea     rdx, byte_18012AB5D
0x180108cac  mov     [rbp+57h+arg_8], eax
0x180108caf  add     r8, 8
0x180108cb3  lea     rax, [rbp+57h+arg_10]
0x180108cb7  mov     [rbp+57h+arg_0], esi
0x180108cba  mov     [rsp+110h+var_D0], rax
0x180108cbf  mov     rcx, rdi
0x180108cc2  lea     rax, [rbp+57h+arg_18]
0x180108cc6  mov     [rbp+57h+var_68], 1000000h
0x180108cce  mov     [rsp+110h+var_D8], rax
0x180108cd3  lea     rax, [rbp+57h+arg_8]
0x180108cd7  mov     [rsp+110h+var_E0], rax
0x180108cdc  lea     rax, [rbp+57h+arg_0]
0x180108ce0  mov     [rsp+110h+var_E8], rax
0x180108ce5  lea     rax, [rbp+57h+var_68]
0x180108ce9  mov     [rsp+110h+var_F0], rax
0x180108cee  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180108cf3  mov     rax, [rbx]
0x180108cf6  mov     rcx, rbx
0x180108cf9  mov     rax, [rax+8]
0x180108cfd  add     rsp, 0F8h
0x180108d04  pop     rdi
0x180108d05  pop     rsi
0x180108d06  pop     rbx
0x180108d07  pop     rbp
0x180108d08  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
