# wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x14002b254`
- end: `0x14002b499`
- name: `?ReportStopActivity@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140020444`
- `0x14002e4cc`

## callees

- `0x140002544`
- `0x140002bb8`
- `0x14000330c`
- `0x14000c558`
- `0x14002b254`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002b424`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002b424`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  int v8; // r9d
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  __int64 v13; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v20; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v21; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v22; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v23; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v24; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v26; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v27; // [rsp+E0h] [rbp+27h] BYREF
  _QWORD v28[5]; // [rsp+E8h] [rbp+2Fh] BYREF
  int v29; // [rsp+120h] [rbp+67h] BYREF
  DWORD v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  __int64 v32; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = LogProvider::Provider();
      if ( *(_DWORD *)v7 > 2u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL) )
      {
        v9 = *(_QWORD *)(v6 + 120);
        v10 = a1[34];
        v22 = *(_QWORD *)(v6 + 112);
        v30 = *(_DWORD *)(v6 + 104);
        v23 = *(_QWORD *)(v6 + 96);
        v24 = *(_QWORD *)(v6 + 88);
        v29 = *(_DWORD *)(v6 + 80);
        v25 = *(_QWORD *)(v6 + 72);
        LODWORD(v31) = *(_DWORD *)(v6 + 32);
        v26 = *(_QWORD *)(v6 + 24);
        LODWORD(v32) = *(_DWORD *)v6;
        v27 = *(_QWORD *)(v6 + 128);
        v18 = *(_DWORD *)(v6 + 64);
        v28[0] = *(_QWORD *)(v6 + 56);
        v19 = *(_DWORD *)(v6 + 8);
        v21 = v9;
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v8,
          (unsigned int)&byte_14008CA67,
          v10 + 8,
          v8,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)v28,
          (__int64)&v18,
          (__int64)&v27,
          (__int64)&v32,
          (__int64)&v26,
          (__int64)&v31,
          (__int64)&v25,
          (__int64)&v29,
          (__int64)&v24,
          (__int64)&v23,
          (__int64)&v30,
          (__int64)&v22,
          (__int64)&v21);
      }
    }
    else
    {
      v11 = LogProvider::Provider();
      v12 = (int)v11;
      if ( *(_DWORD *)v11 > 2u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
      {
        v13 = a1[34];
        v31 = *(_QWORD *)(v13 + 56);
        v32 = *(_QWORD *)(v13 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v15 = a1[34];
        v30 = CurrentThreadId;
        v29 = a2;
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned int)&word_14008CB7E,
          v15 + 8,
          v16,
          (__int64)&v20,
          (__int64)&v29,
          (__int64)&v30,
          (__int64)&v32,
          (__int64)&v31);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x14002b254  push    rbp
0x14002b256  push    rbx
0x14002b257  push    rsi
0x14002b258  push    rdi
0x14002b259  lea     rbp, [rsp-3Fh]
0x14002b25e  sub     rsp, 0F8h
0x14002b265  mov     esi, edx
0x14002b267  mov     rbx, rcx
0x14002b26a  test    edx, edx
0x14002b26c  jns     loc_14002B47F
0x14002b272  mov     rdi, [rcx+110h]
0x14002b279  mov     eax, [rdi+48h]
0x14002b27c  test    eax, eax
0x14002b27e  jns     loc_14002B3E4
0x14002b284  add     rdi, 50h ; 'P'
0x14002b288  cmp     eax, [rdi+8]
0x14002b28b  jnz     loc_14002B3E4
0x14002b291  test    rdi, rdi
0x14002b294  jz      loc_14002B3E4
0x14002b29a  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002b29f  mov     r9, rax
0x14002b2a2  mov     ecx, [rax]
0x14002b2a4  cmp     ecx, 2
0x14002b2a7  jbe     loc_14002B47F
0x14002b2ad  mov     rdx, 200000000000h
0x14002b2b7  mov     rcx, rax
0x14002b2ba  call    _tlgKeywordOn
0x14002b2bf  test    al, al
0x14002b2c1  jz      loc_14002B47F
0x14002b2c7  mov     rax, [rdi+70h]
0x14002b2cb  lea     rdx, byte_14008CA67
0x14002b2d2  mov     rcx, [rdi+78h]
0x14002b2d6  mov     r8, [rbx+110h]
0x14002b2dd  mov     [rbp+57h+var_58], rax
0x14002b2e1  add     r8, 8
0x14002b2e5  mov     eax, [rdi+68h]
0x14002b2e8  mov     [rbp+57h+arg_8], eax
0x14002b2eb  mov     rax, [rdi+60h]
0x14002b2ef  mov     [rbp+57h+var_50], rax
0x14002b2f3  mov     rax, [rdi+58h]
0x14002b2f7  mov     [rbp+57h+var_48], rax
0x14002b2fb  mov     eax, [rdi+50h]
0x14002b2fe  mov     [rbp+57h+arg_0], eax
0x14002b301  mov     rax, [rdi+48h]
0x14002b305  mov     [rbp+57h+var_40], rax
0x14002b309  mov     eax, [rdi+20h]
0x14002b30c  mov     dword ptr [rbp+57h+arg_10], eax
0x14002b30f  mov     rax, [rdi+18h]
0x14002b313  mov     [rbp+57h+var_38], rax
0x14002b317  mov     eax, [rdi]
0x14002b319  mov     dword ptr [rbp+57h+arg_18], eax
0x14002b31c  mov     rax, [rdi+80h]
0x14002b323  mov     [rbp+57h+var_30], rax
0x14002b327  mov     eax, [rdi+40h]
0x14002b32a  mov     [rbp+57h+var_70], eax
0x14002b32d  mov     rax, [rdi+38h]
0x14002b331  mov     [rbp+57h+var_28], rax
0x14002b335  mov     eax, [rdi+8]
0x14002b338  mov     [rbp+57h+var_6C], eax
0x14002b33b  lea     rax, [rbp+57h+var_60]
0x14002b33f  mov     [rsp+110h+var_80], rax
0x14002b347  lea     rax, [rbp+57h+var_58]
0x14002b34b  mov     [rsp+110h+var_88], rax
0x14002b353  lea     rax, [rbp+57h+arg_8]
0x14002b357  mov     [rsp+110h+var_90], rax
0x14002b35f  lea     rax, [rbp+57h+var_50]
0x14002b363  mov     [rsp+110h+var_98], rax
0x14002b368  lea     rax, [rbp+57h+var_48]
0x14002b36c  mov     [rsp+110h+var_A0], rax
0x14002b371  lea     rax, [rbp+57h+arg_0]
0x14002b375  mov     [rsp+110h+var_A8], rax
0x14002b37a  lea     rax, [rbp+57h+var_40]
0x14002b37e  mov     [rsp+110h+var_B0], rax
0x14002b383  lea     rax, [rbp+57h+arg_10]
0x14002b387  mov     [rsp+110h+var_B8], rax
0x14002b38c  lea     rax, [rbp+57h+var_38]
0x14002b390  mov     [rsp+110h+var_C0], rax
0x14002b395  lea     rax, [rbp+57h+arg_18]
0x14002b399  mov     [rsp+110h+var_C8], rax
0x14002b39e  lea     rax, [rbp+57h+var_30]
0x14002b3a2  mov     [rsp+110h+var_D0], rax
0x14002b3a7  lea     rax, [rbp+57h+var_70]
0x14002b3ab  mov     [rsp+110h+var_D8], rax
0x14002b3b0  lea     rax, [rbp+57h+var_28]
0x14002b3b4  mov     [rsp+110h+var_E0], rax
0x14002b3b9  lea     rax, [rbp+57h+var_6C]
0x14002b3bd  mov     [rsp+110h+var_E8], rax
0x14002b3c2  lea     rax, [rbp+57h+var_68]
0x14002b3c6  mov     [rbp+57h+var_60], rcx
0x14002b3ca  mov     rcx, r9
0x14002b3cd  mov     [rsp+110h+var_F0], rax
0x14002b3d2  mov     [rbp+57h+var_68], 1000000h
0x14002b3da  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14002b3df  jmp     loc_14002B47F
0x14002b3e4  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002b3e9  mov     rdi, rax
0x14002b3ec  mov     ecx, [rax]
0x14002b3ee  cmp     ecx, 2
0x14002b3f1  jbe     loc_14002B47F
0x14002b3f7  mov     rdx, 200000000000h
0x14002b401  mov     rcx, rax
0x14002b404  call    _tlgKeywordOn
0x14002b409  test    al, al
0x14002b40b  jz      short loc_14002B47F
0x14002b40d  mov     rcx, [rbx+110h]
0x14002b414  mov     rax, [rcx+38h]
0x14002b418  mov     [rbp+57h+arg_10], rax
0x14002b41c  mov     rax, [rcx+30h]
0x14002b420  mov     [rbp+57h+arg_18], rax
0x14002b424  call    cs:__imp_GetCurrentThreadId
0x14002b42a  mov     r8, [rbx+110h]
0x14002b431  lea     rdx, word_14008CB7E
0x14002b438  mov     [rbp+57h+arg_8], eax
0x14002b43b  add     r8, 8
0x14002b43f  lea     rax, [rbp+57h+arg_10]
0x14002b443  mov     [rbp+57h+arg_0], esi
0x14002b446  mov     [rsp+110h+var_D0], rax
0x14002b44b  mov     rcx, rdi
0x14002b44e  lea     rax, [rbp+57h+arg_18]
0x14002b452  mov     [rbp+57h+var_68], 1000000h
0x14002b45a  mov     [rsp+110h+var_D8], rax
0x14002b45f  lea     rax, [rbp+57h+arg_8]
0x14002b463  mov     [rsp+110h+var_E0], rax
0x14002b468  lea     rax, [rbp+57h+arg_0]
0x14002b46c  mov     [rsp+110h+var_E8], rax
0x14002b471  lea     rax, [rbp+57h+var_68]
0x14002b475  mov     [rsp+110h+var_F0], rax
0x14002b47a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14002b47f  mov     rax, [rbx]
0x14002b482  mov     rcx, rbx
0x14002b485  mov     rax, [rax+8]
0x14002b489  add     rsp, 0F8h
0x14002b490  pop     rdi
0x14002b491  pop     rsi
0x14002b492  pop     rbx
0x14002b493  pop     rbp
0x14002b494  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
