# LogProvider::NgcIsoGetUpdatedKey::StopActivity(void)

- ea: `0x1400349a0`
- end: `0x140034bcf`
- name: `?StopActivity@NgcIsoGetUpdatedKey@LogProvider@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(LogProvider::NgcIsoGetUpdatedKey *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140001008`
- `0x140003124`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x1400349a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140034b6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140034b6d`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoGetUpdatedKey::StopActivity(LogProvider::NgcIsoGetUpdatedKey *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v29; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = LogProvider::Provider();
    if ( *(_DWORD *)v7 > 4u )
    {
      v8 = *((_QWORD *)v4 + 6);
      v20 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v29 = v4[17];
      v30 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (unsigned int)byte_140088759,
        v9 + 8,
        (_DWORD)v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = LogProvider::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 4u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v13 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)&byte_1400888A7,
        v13 + 8,
        0,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x1400349a0  push    rbp
0x1400349a2  push    rbx
0x1400349a3  push    rdi
0x1400349a4  lea     rbp, [rsp+10h]
0x1400349a9  sub     rsp, 130h
0x1400349b0  mov     rdi, [rcx+110h]
0x1400349b7  mov     rbx, rcx
0x1400349ba  mov     eax, [rdi+48h]
0x1400349bd  test    eax, eax
0x1400349bf  jns     loc_140034B59
0x1400349c5  add     rdi, 50h ; 'P'
0x1400349c9  cmp     eax, [rdi+8]
0x1400349cc  jnz     loc_140034B59
0x1400349d2  test    rdi, rdi
0x1400349d5  jz      loc_140034B59
0x1400349db  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400349e0  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x1400349e5  mov     r9, rax
0x1400349e8  mov     ecx, [rax]
0x1400349ea  cmp     ecx, 4
0x1400349ed  jbe     loc_140034BBD
0x1400349f3  mov     rax, [rdi+70h]
0x1400349f7  lea     rdx, byte_140088759
0x1400349fe  mov     rcx, [rdi+30h]
0x140034a02  mov     [rbp+var_60], rax
0x140034a06  mov     eax, [rdi+68h]
0x140034a09  mov     r8, [rbx+110h]
0x140034a10  mov     dword ptr [rbp+arg_10], eax
0x140034a13  add     r8, 8
0x140034a17  mov     rax, [rdi+60h]
0x140034a1b  mov     [rbp+var_58], rax
0x140034a1f  mov     rax, [rdi+58h]
0x140034a23  mov     [rbp+var_50], rax
0x140034a27  mov     eax, [rdi+50h]
0x140034a2a  mov     [rbp+arg_18], eax
0x140034a2d  mov     rax, [rdi+48h]
0x140034a31  mov     [rbp+var_48], rax
0x140034a35  mov     eax, [rdi+20h]
0x140034a38  mov     [rbp+var_80], eax
0x140034a3b  mov     rax, [rdi+18h]
0x140034a3f  mov     [rbp+var_40], rax
0x140034a43  mov     eax, [rdi]
0x140034a45  mov     [rbp+var_7C], eax
0x140034a48  mov     rax, [rdi+80h]
0x140034a4f  mov     [rbp+var_38], rax
0x140034a53  mov     eax, [rdi+40h]
0x140034a56  mov     [rbp+var_78], eax
0x140034a59  mov     rax, [rdi+38h]
0x140034a5d  mov     [rbp+var_30], rax
0x140034a61  mov     eax, [rdi+8]
0x140034a64  mov     [rbp+var_74], eax
0x140034a67  lea     rax, [rbp+var_70]
0x140034a6b  mov     [rsp+140h+var_90], rax
0x140034a73  lea     rax, [rbp+arg_0]
0x140034a77  mov     [rsp+140h+var_98], rax
0x140034a7f  lea     rax, [rbp+arg_8]
0x140034a83  mov     [rsp+140h+var_A0], rax
0x140034a8b  lea     rax, [rbp+var_68]
0x140034a8f  mov     [rsp+140h+var_A8], rax
0x140034a97  lea     rax, [rbp+var_60]
0x140034a9b  mov     [rsp+140h+var_B0], rax
0x140034aa3  lea     rax, [rbp+arg_10]
0x140034aa7  mov     [rsp+140h+var_B8], rax
0x140034aaf  lea     rax, [rbp+var_58]
0x140034ab3  mov     [rsp+140h+var_C0], rax
0x140034abb  lea     rax, [rbp+var_50]
0x140034abf  mov     [rsp+140h+var_C8], rax
0x140034ac4  lea     rax, [rbp+arg_18]
0x140034ac8  mov     [rsp+140h+var_D0], rax
0x140034acd  lea     rax, [rbp+var_48]
0x140034ad1  mov     [rsp+140h+var_D8], rax
0x140034ad6  lea     rax, [rbp+var_80]
0x140034ada  mov     [rsp+140h+var_E0], rax
0x140034adf  lea     rax, [rbp+var_40]
0x140034ae3  mov     [rsp+140h+var_E8], rax
0x140034ae8  lea     rax, [rbp+var_7C]
0x140034aec  mov     [rsp+140h+var_F0], rax
0x140034af1  lea     rax, [rbp+var_38]
0x140034af5  mov     [rsp+140h+var_F8], rax
0x140034afa  lea     rax, [rbp+var_78]
0x140034afe  mov     [rsp+140h+var_100], rax
0x140034b03  lea     rax, [rbp+var_30]
0x140034b07  mov     [rsp+140h+var_108], rax
0x140034b0c  lea     rax, [rbp+var_74]
0x140034b10  mov     [rbp+var_70], rcx
0x140034b14  mov     ecx, [rdi+44h]
0x140034b17  mov     [rsp+140h+var_110], rax
0x140034b1c  lea     rax, [rbp+var_28]
0x140034b20  mov     [rbp+arg_0], ecx
0x140034b23  mov     ecx, [rdi+10h]
0x140034b26  mov     [rbp+arg_8], ecx
0x140034b29  mov     rcx, [rdi+78h]
0x140034b2d  mov     [rsp+140h+var_118], rax
0x140034b32  lea     rax, [rbp+var_20]
0x140034b36  mov     [rbp+var_68], rcx
0x140034b3a  mov     rcx, r9
0x140034b3d  mov     [rsp+140h+var_120], rax
0x140034b42  mov     [rbp+var_28], 1000000h
0x140034b4a  mov     [rbp+var_20], 0
0x140034b52  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140034b57  jmp     short loc_140034BBD
0x140034b59  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140034b5e  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140034b63  mov     rdi, rax
0x140034b66  mov     ecx, [rax]
0x140034b68  cmp     ecx, 4
0x140034b6b  jbe     short loc_140034BBD
0x140034b6d  call    cs:__imp_GetCurrentThreadId
0x140034b73  mov     r8, [rbx+110h]
0x140034b7a  lea     rdx, byte_1400888A7
0x140034b81  mov     [rbp+arg_0], eax
0x140034b84  xor     r9d, r9d
0x140034b87  lea     rax, [rbp+arg_0]
0x140034b8b  mov     [rsp+140h+var_110], rax
0x140034b90  lea     rax, [rbp+arg_8]
0x140034b94  mov     ecx, [r8+48h]
0x140034b98  add     r8, 8
0x140034b9c  mov     [rsp+140h+var_118], rax
0x140034ba1  lea     rax, [rbp+arg_10]
0x140034ba5  mov     [rbp+arg_8], ecx
0x140034ba8  mov     rcx, rdi
0x140034bab  mov     [rsp+140h+var_120], rax
0x140034bb0  mov     [rbp+arg_10], 0
0x140034bb8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140034bbd  mov     rcx, rbx
0x140034bc0  add     rsp, 130h
0x140034bc7  pop     rdi
0x140034bc8  pop     rbx
0x140034bc9  pop     rbp
0x140034bca  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
