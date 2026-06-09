# KspDebugProvider::KspDebugActivity::StopActivity(void)

- ea: `0x18005d000`
- end: `0x18005d28b`
- name: `?StopActivity@KspDebugActivity@KspDebugProvider@@MEAAXXZ`
- size: `651`
- prototype: `void __fastcall(KspDebugProvider::KspDebugActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800018e4`
- `0x18003d040`
- `0x18004c940`
- `0x18004d1ac`
- `0x18004d488`
- `0x18005d000`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d1e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d1e5`

## pseudocode

```c
void __fastcall KspDebugProvider::KspDebugActivity::StopActivity(KspDebugProvider::KspDebugActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  int v11; // ecx
  int v12; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v13; // [rsp+C4h] [rbp-7Ch] BYREF
  int v14; // [rsp+C8h] [rbp-78h] BYREF
  int v15; // [rsp+CCh] [rbp-74h] BYREF
  int v16; // [rsp+D0h] [rbp-70h] BYREF
  int v17; // [rsp+D4h] [rbp-6Ch] BYREF
  int v18; // [rsp+D8h] [rbp-68h] BYREF
  int v19; // [rsp+DCh] [rbp-64h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  __int64 v28; // [rsp+120h] [rbp-20h] BYREF
  __int64 v29; // [rsp+128h] [rbp-18h] BYREF
  __int64 v30; // [rsp+130h] [rbp-10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+140h] [rbp+0h] BYREF
  __int64 *v32; // [rsp+160h] [rbp+20h]
  __int64 v33; // [rsp+168h] [rbp+28h]
  int *v34; // [rsp+170h] [rbp+30h]
  __int64 v35; // [rsp+178h] [rbp+38h]
  DWORD *v36; // [rsp+180h] [rbp+40h]
  __int64 v37; // [rsp+188h] [rbp+48h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = KspDebugProvider::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = *((_QWORD *)v4 + 6);
      v23 = *((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      v16 = v4[26];
      v24 = *((_QWORD *)v4 + 12);
      v25 = *((_QWORD *)v4 + 11);
      v17 = v4[20];
      v26 = *((_QWORD *)v4 + 9);
      v18 = v4[8];
      v27 = *((_QWORD *)v4 + 3);
      v19 = *v4;
      v28 = *((_QWORD *)v4 + 16);
      v12 = v4[16];
      v29 = *((_QWORD *)v4 + 7);
      v13 = v4[2];
      v21 = v6;
      v14 = v4[17];
      v15 = v4[4];
      v22 = *((_QWORD *)v4 + 15);
      v30 = 0x1000000;
      v20 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v5,
        (unsigned int)word_1800F650A,
        v7 + 8,
        (_DWORD)v5,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v13,
        (__int64)&v29,
        (__int64)&v12,
        (__int64)&v28,
        (__int64)&v19,
        (__int64)&v27,
        (__int64)&v18,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v16,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v21);
    }
  }
  else
  {
    wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = KspDebugProvider::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v13 = CurrentThreadId;
      v37 = 4;
      v36 = &v13;
      v11 = *(_DWORD *)(v10 + 72);
      v34 = &v12;
      v32 = &v20;
      v12 = v11;
      v20 = 0;
      v35 = 4;
      v33 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)v8,
        (unsigned __int8 *)byte_1800F6655,
        (const GUID *)(v10 + 8),
        0,
        5u,
        &v31);
    }
  }
  wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18005d000  mov     [rsp-8+arg_8], rbx
0x18005d005  mov     [rsp-8+arg_10], rdi
0x18005d00a  push    rbp
0x18005d00b  lea     rbp, [rsp-60h]
0x18005d010  sub     rsp, 1A0h
0x18005d017  mov     rax, cs:__security_cookie
0x18005d01e  xor     rax, rsp
0x18005d021  mov     [rbp+60h+var_10], rax
0x18005d025  mov     rdi, [rcx+110h]
0x18005d02c  mov     rbx, rcx
0x18005d02f  mov     eax, [rdi+48h]
0x18005d032  test    eax, eax
0x18005d034  jns     loc_18005D1D1
0x18005d03a  add     rdi, 50h ; 'P'
0x18005d03e  cmp     eax, [rdi+8]
0x18005d041  jnz     loc_18005D1D1
0x18005d047  test    rdi, rdi
0x18005d04a  jz      loc_18005D1D1
0x18005d050  call    ?zInternalStop@?$ActivityBase@VKspDebugProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18005d055  call    ?Provider@KspDebugProvider@@SAPEBU_tlgProvider_t@@XZ; KspDebugProvider::Provider(void)
0x18005d05a  mov     r9, rax
0x18005d05d  mov     ecx, [rax]
0x18005d05f  cmp     ecx, 5
0x18005d062  jbe     loc_18005D261
0x18005d068  mov     rax, [rdi+70h]
0x18005d06c  lea     rdx, word_1800F650A
0x18005d073  mov     rcx, [rdi+30h]
0x18005d077  mov     [rbp+60h+var_A8], rax
0x18005d07b  mov     eax, [rdi+68h]
0x18005d07e  mov     r8, [rbx+110h]
0x18005d085  mov     [rbp+60h+var_D0], eax
0x18005d088  add     r8, 8
0x18005d08c  mov     rax, [rdi+60h]
0x18005d090  mov     [rbp+60h+var_A0], rax
0x18005d094  mov     rax, [rdi+58h]
0x18005d098  mov     [rbp+60h+var_98], rax
0x18005d09c  mov     eax, [rdi+50h]
0x18005d09f  mov     [rbp+60h+var_CC], eax
0x18005d0a2  mov     rax, [rdi+48h]
0x18005d0a6  mov     [rbp+60h+var_90], rax
0x18005d0aa  mov     eax, [rdi+20h]
0x18005d0ad  mov     [rbp+60h+var_C8], eax
0x18005d0b0  mov     rax, [rdi+18h]
0x18005d0b4  mov     [rbp+60h+var_88], rax
0x18005d0b8  mov     eax, [rdi]
0x18005d0ba  mov     [rbp+60h+var_C4], eax
0x18005d0bd  mov     rax, [rdi+80h]
0x18005d0c4  mov     [rbp+60h+var_80], rax
0x18005d0c8  mov     eax, [rdi+40h]
0x18005d0cb  mov     [rbp+60h+var_E0], eax
0x18005d0ce  mov     rax, [rdi+38h]
0x18005d0d2  mov     [rbp+60h+var_78], rax
0x18005d0d6  mov     eax, [rdi+8]
0x18005d0d9  mov     [rbp+60h+var_DC], eax
0x18005d0dc  lea     rax, [rbp+60h+var_B8]
0x18005d0e0  mov     [rsp+1A0h+var_F0], rax
0x18005d0e8  lea     rax, [rbp+60h+var_D8]
0x18005d0ec  mov     [rsp+1A0h+var_F8], rax
0x18005d0f4  lea     rax, [rbp+60h+var_D4]
0x18005d0f8  mov     [rsp+1A0h+var_100], rax
0x18005d100  lea     rax, [rbp+60h+var_B0]
0x18005d104  mov     [rsp+1A0h+var_108], rax
0x18005d10c  lea     rax, [rbp+60h+var_A8]
0x18005d110  mov     [rsp+1A0h+var_110], rax
0x18005d118  lea     rax, [rbp+60h+var_D0]
0x18005d11c  mov     [rsp+1A0h+var_118], rax
0x18005d124  lea     rax, [rbp+60h+var_A0]
0x18005d128  mov     [rsp+1A0h+var_120], rax
0x18005d130  lea     rax, [rbp+60h+var_98]
0x18005d134  mov     [rsp+1A0h+var_128], rax
0x18005d139  lea     rax, [rbp+60h+var_CC]
0x18005d13d  mov     [rsp+1A0h+var_130], rax
0x18005d142  lea     rax, [rbp+60h+var_90]
0x18005d146  mov     [rsp+1A0h+var_138], rax
0x18005d14b  lea     rax, [rbp+60h+var_C8]
0x18005d14f  mov     [rsp+1A0h+var_140], rax
0x18005d154  lea     rax, [rbp+60h+var_88]
0x18005d158  mov     [rsp+1A0h+var_148], rax
0x18005d15d  lea     rax, [rbp+60h+var_C4]
0x18005d161  mov     [rsp+1A0h+var_150], rax
0x18005d166  lea     rax, [rbp+60h+var_80]
0x18005d16a  mov     [rsp+1A0h+var_158], rax
0x18005d16f  lea     rax, [rbp+60h+var_E0]
0x18005d173  mov     [rsp+1A0h+var_160], rax
0x18005d178  lea     rax, [rbp+60h+var_78]
0x18005d17c  mov     [rsp+1A0h+var_168], rax
0x18005d181  lea     rax, [rbp+60h+var_DC]
0x18005d185  mov     [rbp+60h+var_B8], rcx
0x18005d189  mov     ecx, [rdi+44h]
0x18005d18c  mov     [rsp+1A0h+var_170], rax
0x18005d191  lea     rax, [rbp+60h+var_70]
0x18005d195  mov     [rbp+60h+var_D8], ecx
0x18005d198  mov     ecx, [rdi+10h]
0x18005d19b  mov     [rbp+60h+var_D4], ecx
0x18005d19e  mov     rcx, [rdi+78h]
0x18005d1a2  mov     [rsp+1A0h+var_178], rax
0x18005d1a7  lea     rax, [rbp+60h+var_C0]
0x18005d1ab  mov     [rbp+60h+var_B0], rcx
0x18005d1af  mov     rcx, r9
0x18005d1b2  mov     [rsp+1A0h+var_180], rax
0x18005d1b7  mov     [rbp+60h+var_70], 1000000h
0x18005d1bf  mov     [rbp+60h+var_C0], 0
0x18005d1c7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005d1cc  jmp     loc_18005D261
0x18005d1d1  call    ?zInternalStop@?$ActivityBase@VKspDebugProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18005d1d6  call    ?Provider@KspDebugProvider@@SAPEBU_tlgProvider_t@@XZ; KspDebugProvider::Provider(void)
0x18005d1db  mov     rdi, rax
0x18005d1de  mov     ecx, [rax]
0x18005d1e0  cmp     ecx, 5
0x18005d1e3  jbe     short loc_18005D261
0x18005d1e5  call    cs:__imp_GetCurrentThreadId
0x18005d1ec  nop     dword ptr [rax+rax+00h]
0x18005d1f1  mov     r8, [rbx+110h]
0x18005d1f8  lea     rdx, byte_1800F6655
0x18005d1ff  mov     [rbp+60h+var_DC], eax
0x18005d202  xor     r9d, r9d
0x18005d205  lea     rax, [rbp+60h+var_DC]
0x18005d209  mov     [rbp+60h+var_18], 4
0x18005d211  mov     [rbp+60h+var_20], rax
0x18005d215  lea     rax, [rbp+60h+var_E0]
0x18005d219  mov     ecx, [r8+48h]
0x18005d21d  add     r8, 8
0x18005d221  mov     [rbp+60h+var_30], rax
0x18005d225  lea     rax, [rbp+60h+var_C0]
0x18005d229  mov     [rbp+60h+var_40], rax
0x18005d22d  lea     rax, [rbp+60h+var_60]
0x18005d231  mov     [rbp+60h+var_E0], ecx
0x18005d234  mov     rcx, rdi
0x18005d237  mov     [rsp+1A0h+var_178], rax
0x18005d23c  mov     dword ptr [rsp+1A0h+var_180], 5
0x18005d244  mov     [rbp+60h+var_C0], 0
0x18005d24c  mov     [rbp+60h+var_28], 4
0x18005d254  mov     [rbp+60h+var_38], 8
0x18005d25c  call    _tlgWriteTransfer_EventWriteTransfer
0x18005d261  mov     rcx, rbx
0x18005d264  call    ?IgnoreCurrentThread@?$ActivityBase@VKspDebugProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<KspDebugProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18005d269  mov     rcx, [rbp+60h+var_10]
0x18005d26d  xor     rcx, rsp; StackCookie
0x18005d270  call    __security_check_cookie
0x18005d275  lea     r11, [rsp+1A0h+var_s0]
0x18005d27d  mov     rbx, [r11+18h]
0x18005d281  mov     rdi, [r11+20h]
0x18005d285  mov     rsp, r11
0x18005d288  pop     rbp
0x18005d289  retn
```
