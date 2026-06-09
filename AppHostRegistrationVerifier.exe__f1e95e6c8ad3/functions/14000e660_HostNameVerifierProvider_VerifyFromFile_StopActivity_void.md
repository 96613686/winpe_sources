# HostNameVerifierProvider::VerifyFromFile::StopActivity(void)

- ea: `0x14000e660`
- end: `0x14000e882`
- name: `?StopActivity@VerifyFromFile@HostNameVerifierProvider@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(HostNameVerifierProvider::VerifyFromFile *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001010`
- `0x1400012cc`
- `0x140001b4c`
- `0x14000d438`
- `0x14000da38`
- `0x14000e660`
- `0x140010cf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e822`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e822`

## pseudocode

```c
void __fastcall HostNameVerifierProvider::VerifyFromFile::StopActivity(HostNameVerifierProvider::VerifyFromFile *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  int *v20; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v21; // [rsp+B0h] [rbp-9h] BYREF
  int *v22; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v23; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+Fh] BYREF
  int *v25; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v26; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v27; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v28; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v29[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v30; // [rsp+120h] [rbp+67h] BYREF
  int v31; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v32; // [rsp+130h] [rbp+77h] BYREF
  int v33; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = HostNameVerifierProvider::Provider(v5);
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7) )
    {
      v9 = (int *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v30 = v4[26];
      v22 = (int *)*((_QWORD *)v4 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v32) = v4[8];
      v25 = (int *)*((_QWORD *)v4 + 3);
      v33 = *v4;
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v18 = v4[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v19 = v4[2];
      v28 = 0x1000000;
      v29[0] = 0x1000000;
      v20 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)byte_140015C9D,
        v10 + 8,
        v8,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v19,
        &v27,
        (__int64)&v18,
        &v26,
        (__int64)&v33,
        &v25,
        (__int64)&v32,
        &v24,
        (__int64)&v31,
        &v23,
        &v22,
        (__int64)&v30,
        &v21,
        &v20);
    }
  }
  else
  {
    wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = HostNameVerifierProvider::Provider(v11);
    v14 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v16 + 72);
      v32 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (__int64)&word_140015C4E,
        v16 + 8,
        v17,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000e660  push    rbp
0x14000e662  push    rbx
0x14000e663  push    rdi
0x14000e664  lea     rbp, [rsp-47h]
0x14000e669  sub     rsp, 100h
0x14000e670  mov     rdi, [rcx+110h]
0x14000e677  mov     rbx, rcx
0x14000e67a  mov     eax, [rdi+48h]
0x14000e67d  test    eax, eax
0x14000e67f  jns     loc_14000E7F8
0x14000e685  add     rdi, 50h ; 'P'
0x14000e689  cmp     eax, [rdi+8]
0x14000e68c  jnz     loc_14000E7F8
0x14000e692  test    rdi, rdi
0x14000e695  jz      loc_14000E7F8
0x14000e69b  call    ?zInternalStop@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000e6a0  call    ?Provider@HostNameVerifierProvider@@SAPEBU_tlgProvider_t@@XZ; HostNameVerifierProvider::Provider(void)
0x14000e6a5  mov     r9, rax
0x14000e6a8  mov     ecx, [rax]
0x14000e6aa  cmp     ecx, 5
0x14000e6ad  jbe     loc_14000E870
0x14000e6b3  mov     rdx, 400000000000h
0x14000e6bd  mov     rcx, rax
0x14000e6c0  call    _tlgKeywordOn
0x14000e6c5  test    al, al
0x14000e6c7  jz      loc_14000E870
0x14000e6cd  mov     rax, [rdi+70h]
0x14000e6d1  lea     rdx, byte_140015C9D
0x14000e6d8  mov     rcx, [rdi+78h]
0x14000e6dc  mov     r8, [rbx+110h]
0x14000e6e3  mov     [rbp+57h+var_60], rax
0x14000e6e7  add     r8, 8
0x14000e6eb  mov     eax, [rdi+68h]
0x14000e6ee  mov     [rbp+57h+arg_0], eax
0x14000e6f1  mov     rax, [rdi+60h]
0x14000e6f5  mov     [rbp+57h+var_58], rax
0x14000e6f9  mov     rax, [rdi+58h]
0x14000e6fd  mov     [rbp+57h+var_50], rax
0x14000e701  mov     eax, [rdi+50h]
0x14000e704  mov     [rbp+57h+arg_8], eax
0x14000e707  mov     rax, [rdi+48h]
0x14000e70b  mov     [rbp+57h+var_48], rax
0x14000e70f  mov     eax, [rdi+20h]
0x14000e712  mov     dword ptr [rbp+57h+arg_10], eax
0x14000e715  mov     rax, [rdi+18h]
0x14000e719  mov     [rbp+57h+var_40], rax
0x14000e71d  mov     eax, [rdi]
0x14000e71f  mov     [rbp+57h+arg_18], eax
0x14000e722  mov     rax, [rdi+80h]
0x14000e729  mov     [rbp+57h+var_38], rax
0x14000e72d  mov     eax, [rdi+40h]
0x14000e730  mov     [rbp+57h+var_70], eax
0x14000e733  mov     rax, [rdi+38h]
0x14000e737  mov     [rbp+57h+var_30], rax
0x14000e73b  mov     eax, [rdi+8]
0x14000e73e  mov     [rbp+57h+var_6C], eax
0x14000e741  mov     eax, 1000000h
0x14000e746  mov     [rbp+57h+var_28], rax
0x14000e74a  mov     [rbp+57h+var_20], rax
0x14000e74e  lea     rax, [rbp+57h+var_68]
0x14000e752  mov     [rsp+110h+var_78], rax
0x14000e75a  lea     rax, [rbp+57h+var_60]
0x14000e75e  mov     [rsp+110h+var_80], rax
0x14000e766  lea     rax, [rbp+57h+arg_0]
0x14000e76a  mov     [rsp+110h+var_88], rax
0x14000e772  lea     rax, [rbp+57h+var_58]
0x14000e776  mov     [rsp+110h+var_90], rax
0x14000e77e  lea     rax, [rbp+57h+var_50]
0x14000e782  mov     [rsp+110h+var_98], rax
0x14000e787  lea     rax, [rbp+57h+arg_8]
0x14000e78b  mov     [rsp+110h+var_A0], rax
0x14000e790  lea     rax, [rbp+57h+var_48]
0x14000e794  mov     [rsp+110h+var_A8], rax
0x14000e799  lea     rax, [rbp+57h+arg_10]
0x14000e79d  mov     [rsp+110h+var_B0], rax
0x14000e7a2  lea     rax, [rbp+57h+var_40]
0x14000e7a6  mov     [rsp+110h+var_B8], rax
0x14000e7ab  lea     rax, [rbp+57h+arg_18]
0x14000e7af  mov     [rsp+110h+var_C0], rax
0x14000e7b4  lea     rax, [rbp+57h+var_38]
0x14000e7b8  mov     [rsp+110h+var_C8], rax
0x14000e7bd  lea     rax, [rbp+57h+var_70]
0x14000e7c1  mov     [rsp+110h+var_D0], rax
0x14000e7c6  lea     rax, [rbp+57h+var_30]
0x14000e7ca  mov     [rsp+110h+var_D8], rax
0x14000e7cf  lea     rax, [rbp+57h+var_6C]
0x14000e7d3  mov     [rsp+110h+var_E0], rax
0x14000e7d8  lea     rax, [rbp+57h+var_28]
0x14000e7dc  mov     [rsp+110h+var_E8], rax
0x14000e7e1  lea     rax, [rbp+57h+var_20]
0x14000e7e5  mov     [rbp+57h+var_68], rcx
0x14000e7e9  mov     rcx, r9
0x14000e7ec  mov     [rsp+110h+var_F0], rax
0x14000e7f1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000e7f6  jmp     short loc_14000E870
0x14000e7f8  call    ?zInternalStop@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000e7fd  call    ?Provider@HostNameVerifierProvider@@SAPEBU_tlgProvider_t@@XZ; HostNameVerifierProvider::Provider(void)
0x14000e802  mov     rdi, rax
0x14000e805  mov     ecx, [rax]
0x14000e807  cmp     ecx, 5
0x14000e80a  jbe     short loc_14000E870
0x14000e80c  mov     rdx, 400000000000h
0x14000e816  mov     rcx, rax
0x14000e819  call    _tlgKeywordOn
0x14000e81e  test    al, al
0x14000e820  jz      short loc_14000E870
0x14000e822  call    cs:__imp_GetCurrentThreadId
0x14000e828  mov     r8, [rbx+110h]
0x14000e82f  lea     rdx, word_140015C4E
0x14000e836  mov     [rbp+57h+arg_0], eax
0x14000e839  mov     rcx, rdi
0x14000e83c  mov     eax, [r8+48h]
0x14000e840  add     r8, 8
0x14000e844  mov     [rbp+57h+arg_8], eax
0x14000e847  mov     eax, 1000000h
0x14000e84c  mov     [rbp+57h+arg_10], rax
0x14000e850  lea     rax, [rbp+57h+arg_0]
0x14000e854  mov     [rsp+110h+var_E0], rax
0x14000e859  lea     rax, [rbp+57h+arg_8]
0x14000e85d  mov     [rsp+110h+var_E8], rax
0x14000e862  lea     rax, [rbp+57h+arg_10]
0x14000e866  mov     [rsp+110h+var_F0], rax
0x14000e86b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000e870  mov     rcx, rbx
0x14000e873  add     rsp, 100h
0x14000e87a  pop     rdi
0x14000e87b  pop     rbx
0x14000e87c  pop     rbp
0x14000e87d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
