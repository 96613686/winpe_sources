# wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x140017098`
- end: `0x1400172e3`
- name: `?ReportStopActivity@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `587`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140016740`
- `0x140017878`

## callees

- `0x14000172c`
- `0x140001828`
- `0x140001f30`
- `0x140017078`
- `0x140017098`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017268`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017268`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
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
      v7 = MDMPushProvider::Provider();
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
          (unsigned int)&byte_140020B37,
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
      v11 = MDMPushProvider::Provider();
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
          (unsigned int)&word_140020C4E,
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
0x140017098  push    rbp
0x14001709a  push    rbx
0x14001709b  push    rsi
0x14001709c  push    rdi
0x14001709d  lea     rbp, [rsp-3Fh]
0x1400170a2  sub     rsp, 0F8h
0x1400170a9  mov     esi, edx
0x1400170ab  mov     rbx, rcx
0x1400170ae  test    edx, edx
0x1400170b0  jns     loc_1400172C9
0x1400170b6  mov     rdi, [rcx+110h]
0x1400170bd  mov     eax, [rdi+48h]
0x1400170c0  test    eax, eax
0x1400170c2  jns     loc_140017228
0x1400170c8  add     rdi, 50h ; 'P'
0x1400170cc  cmp     eax, [rdi+8]
0x1400170cf  jnz     loc_140017228
0x1400170d5  test    rdi, rdi
0x1400170d8  jz      loc_140017228
0x1400170de  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x1400170e3  mov     r9, rax
0x1400170e6  mov     ecx, [rax]
0x1400170e8  cmp     ecx, 2
0x1400170eb  jbe     loc_1400172C9
0x1400170f1  mov     rdx, 200000000000h
0x1400170fb  mov     rcx, rax
0x1400170fe  call    _tlgKeywordOn
0x140017103  test    al, al
0x140017105  jz      loc_1400172C9
0x14001710b  mov     rax, [rdi+70h]
0x14001710f  lea     rdx, byte_140020B37
0x140017116  mov     rcx, [rdi+78h]
0x14001711a  mov     r8, [rbx+110h]
0x140017121  mov     [rbp+57h+var_58], rax
0x140017125  add     r8, 8
0x140017129  mov     eax, [rdi+68h]
0x14001712c  mov     [rbp+57h+arg_8], eax
0x14001712f  mov     rax, [rdi+60h]
0x140017133  mov     [rbp+57h+var_50], rax
0x140017137  mov     rax, [rdi+58h]
0x14001713b  mov     [rbp+57h+var_48], rax
0x14001713f  mov     eax, [rdi+50h]
0x140017142  mov     [rbp+57h+arg_0], eax
0x140017145  mov     rax, [rdi+48h]
0x140017149  mov     [rbp+57h+var_40], rax
0x14001714d  mov     eax, [rdi+20h]
0x140017150  mov     dword ptr [rbp+57h+arg_10], eax
0x140017153  mov     rax, [rdi+18h]
0x140017157  mov     [rbp+57h+var_38], rax
0x14001715b  mov     eax, [rdi]
0x14001715d  mov     dword ptr [rbp+57h+arg_18], eax
0x140017160  mov     rax, [rdi+80h]
0x140017167  mov     [rbp+57h+var_30], rax
0x14001716b  mov     eax, [rdi+40h]
0x14001716e  mov     [rbp+57h+var_70], eax
0x140017171  mov     rax, [rdi+38h]
0x140017175  mov     [rbp+57h+var_28], rax
0x140017179  mov     eax, [rdi+8]
0x14001717c  mov     [rbp+57h+var_6C], eax
0x14001717f  lea     rax, [rbp+57h+var_60]
0x140017183  mov     [rsp+110h+var_80], rax
0x14001718b  lea     rax, [rbp+57h+var_58]
0x14001718f  mov     [rsp+110h+var_88], rax
0x140017197  lea     rax, [rbp+57h+arg_8]
0x14001719b  mov     [rsp+110h+var_90], rax
0x1400171a3  lea     rax, [rbp+57h+var_50]
0x1400171a7  mov     [rsp+110h+var_98], rax
0x1400171ac  lea     rax, [rbp+57h+var_48]
0x1400171b0  mov     [rsp+110h+var_A0], rax
0x1400171b5  lea     rax, [rbp+57h+arg_0]
0x1400171b9  mov     [rsp+110h+var_A8], rax
0x1400171be  lea     rax, [rbp+57h+var_40]
0x1400171c2  mov     [rsp+110h+var_B0], rax
0x1400171c7  lea     rax, [rbp+57h+arg_10]
0x1400171cb  mov     [rsp+110h+var_B8], rax
0x1400171d0  lea     rax, [rbp+57h+var_38]
0x1400171d4  mov     [rsp+110h+var_C0], rax
0x1400171d9  lea     rax, [rbp+57h+arg_18]
0x1400171dd  mov     [rsp+110h+var_C8], rax
0x1400171e2  lea     rax, [rbp+57h+var_30]
0x1400171e6  mov     [rsp+110h+var_D0], rax
0x1400171eb  lea     rax, [rbp+57h+var_70]
0x1400171ef  mov     [rsp+110h+var_D8], rax
0x1400171f4  lea     rax, [rbp+57h+var_28]
0x1400171f8  mov     [rsp+110h+var_E0], rax
0x1400171fd  lea     rax, [rbp+57h+var_6C]
0x140017201  mov     [rsp+110h+var_E8], rax
0x140017206  lea     rax, [rbp+57h+var_68]
0x14001720a  mov     [rbp+57h+var_60], rcx
0x14001720e  mov     rcx, r9
0x140017211  mov     [rsp+110h+var_F0], rax
0x140017216  mov     [rbp+57h+var_68], 1000000h
0x14001721e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140017223  jmp     loc_1400172C9
0x140017228  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x14001722d  mov     rdi, rax
0x140017230  mov     ecx, [rax]
0x140017232  cmp     ecx, 2
0x140017235  jbe     loc_1400172C9
0x14001723b  mov     rdx, 200000000000h
0x140017245  mov     rcx, rax
0x140017248  call    _tlgKeywordOn
0x14001724d  test    al, al
0x14001724f  jz      short loc_1400172C9
0x140017251  mov     rcx, [rbx+110h]
0x140017258  mov     rax, [rcx+38h]
0x14001725c  mov     [rbp+57h+arg_10], rax
0x140017260  mov     rax, [rcx+30h]
0x140017264  mov     [rbp+57h+arg_18], rax
0x140017268  call    cs:__imp_GetCurrentThreadId
0x14001726f  nop     dword ptr [rax+rax+00h]
0x140017274  mov     r8, [rbx+110h]
0x14001727b  lea     rdx, word_140020C4E
0x140017282  mov     [rbp+57h+arg_8], eax
0x140017285  add     r8, 8
0x140017289  lea     rax, [rbp+57h+arg_10]
0x14001728d  mov     [rbp+57h+arg_0], esi
0x140017290  mov     [rsp+110h+var_D0], rax
0x140017295  mov     rcx, rdi
0x140017298  lea     rax, [rbp+57h+arg_18]
0x14001729c  mov     [rbp+57h+var_68], 1000000h
0x1400172a4  mov     [rsp+110h+var_D8], rax
0x1400172a9  lea     rax, [rbp+57h+arg_8]
0x1400172ad  mov     [rsp+110h+var_E0], rax
0x1400172b2  lea     rax, [rbp+57h+arg_0]
0x1400172b6  mov     [rsp+110h+var_E8], rax
0x1400172bb  lea     rax, [rbp+57h+var_68]
0x1400172bf  mov     [rsp+110h+var_F0], rax
0x1400172c4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1400172c9  mov     rax, [rbx]
0x1400172cc  mov     rcx, rbx
0x1400172cf  mov     rax, [rax+8]
0x1400172d3  add     rsp, 0F8h
0x1400172da  pop     rdi
0x1400172db  pop     rsi
0x1400172dc  pop     rbx
0x1400172dd  pop     rbp
0x1400172de  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
