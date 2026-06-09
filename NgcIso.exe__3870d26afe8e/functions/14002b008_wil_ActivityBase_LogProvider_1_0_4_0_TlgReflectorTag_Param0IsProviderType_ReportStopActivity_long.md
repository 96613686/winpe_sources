# wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x14002b008`
- end: `0x14002b24d`
- name: `?ReportStopActivity@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1400075a0`
- `0x14002e3fc`

## callees

- `0x140002544`
- `0x140002bb8`
- `0x14000330c`
- `0x14000c558`
- `0x14002b008`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002b1d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002b1d8`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
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
          (unsigned int)byte_14008C461,
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
          (unsigned int)&unk_14008C578,
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
0x14002b008  push    rbp
0x14002b00a  push    rbx
0x14002b00b  push    rsi
0x14002b00c  push    rdi
0x14002b00d  lea     rbp, [rsp-3Fh]
0x14002b012  sub     rsp, 0F8h
0x14002b019  mov     esi, edx
0x14002b01b  mov     rbx, rcx
0x14002b01e  test    edx, edx
0x14002b020  jns     loc_14002B233
0x14002b026  mov     rdi, [rcx+110h]
0x14002b02d  mov     eax, [rdi+48h]
0x14002b030  test    eax, eax
0x14002b032  jns     loc_14002B198
0x14002b038  add     rdi, 50h ; 'P'
0x14002b03c  cmp     eax, [rdi+8]
0x14002b03f  jnz     loc_14002B198
0x14002b045  test    rdi, rdi
0x14002b048  jz      loc_14002B198
0x14002b04e  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002b053  mov     r9, rax
0x14002b056  mov     ecx, [rax]
0x14002b058  cmp     ecx, 2
0x14002b05b  jbe     loc_14002B233
0x14002b061  mov     rdx, 200000000000h
0x14002b06b  mov     rcx, rax
0x14002b06e  call    _tlgKeywordOn
0x14002b073  test    al, al
0x14002b075  jz      loc_14002B233
0x14002b07b  mov     rax, [rdi+70h]
0x14002b07f  lea     rdx, byte_14008C461
0x14002b086  mov     rcx, [rdi+78h]
0x14002b08a  mov     r8, [rbx+110h]
0x14002b091  mov     [rbp+57h+var_58], rax
0x14002b095  add     r8, 8
0x14002b099  mov     eax, [rdi+68h]
0x14002b09c  mov     [rbp+57h+arg_8], eax
0x14002b09f  mov     rax, [rdi+60h]
0x14002b0a3  mov     [rbp+57h+var_50], rax
0x14002b0a7  mov     rax, [rdi+58h]
0x14002b0ab  mov     [rbp+57h+var_48], rax
0x14002b0af  mov     eax, [rdi+50h]
0x14002b0b2  mov     [rbp+57h+arg_0], eax
0x14002b0b5  mov     rax, [rdi+48h]
0x14002b0b9  mov     [rbp+57h+var_40], rax
0x14002b0bd  mov     eax, [rdi+20h]
0x14002b0c0  mov     dword ptr [rbp+57h+arg_10], eax
0x14002b0c3  mov     rax, [rdi+18h]
0x14002b0c7  mov     [rbp+57h+var_38], rax
0x14002b0cb  mov     eax, [rdi]
0x14002b0cd  mov     dword ptr [rbp+57h+arg_18], eax
0x14002b0d0  mov     rax, [rdi+80h]
0x14002b0d7  mov     [rbp+57h+var_30], rax
0x14002b0db  mov     eax, [rdi+40h]
0x14002b0de  mov     [rbp+57h+var_70], eax
0x14002b0e1  mov     rax, [rdi+38h]
0x14002b0e5  mov     [rbp+57h+var_28], rax
0x14002b0e9  mov     eax, [rdi+8]
0x14002b0ec  mov     [rbp+57h+var_6C], eax
0x14002b0ef  lea     rax, [rbp+57h+var_60]
0x14002b0f3  mov     [rsp+110h+var_80], rax
0x14002b0fb  lea     rax, [rbp+57h+var_58]
0x14002b0ff  mov     [rsp+110h+var_88], rax
0x14002b107  lea     rax, [rbp+57h+arg_8]
0x14002b10b  mov     [rsp+110h+var_90], rax
0x14002b113  lea     rax, [rbp+57h+var_50]
0x14002b117  mov     [rsp+110h+var_98], rax
0x14002b11c  lea     rax, [rbp+57h+var_48]
0x14002b120  mov     [rsp+110h+var_A0], rax
0x14002b125  lea     rax, [rbp+57h+arg_0]
0x14002b129  mov     [rsp+110h+var_A8], rax
0x14002b12e  lea     rax, [rbp+57h+var_40]
0x14002b132  mov     [rsp+110h+var_B0], rax
0x14002b137  lea     rax, [rbp+57h+arg_10]
0x14002b13b  mov     [rsp+110h+var_B8], rax
0x14002b140  lea     rax, [rbp+57h+var_38]
0x14002b144  mov     [rsp+110h+var_C0], rax
0x14002b149  lea     rax, [rbp+57h+arg_18]
0x14002b14d  mov     [rsp+110h+var_C8], rax
0x14002b152  lea     rax, [rbp+57h+var_30]
0x14002b156  mov     [rsp+110h+var_D0], rax
0x14002b15b  lea     rax, [rbp+57h+var_70]
0x14002b15f  mov     [rsp+110h+var_D8], rax
0x14002b164  lea     rax, [rbp+57h+var_28]
0x14002b168  mov     [rsp+110h+var_E0], rax
0x14002b16d  lea     rax, [rbp+57h+var_6C]
0x14002b171  mov     [rsp+110h+var_E8], rax
0x14002b176  lea     rax, [rbp+57h+var_68]
0x14002b17a  mov     [rbp+57h+var_60], rcx
0x14002b17e  mov     rcx, r9
0x14002b181  mov     [rsp+110h+var_F0], rax
0x14002b186  mov     [rbp+57h+var_68], 1000000h
0x14002b18e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14002b193  jmp     loc_14002B233
0x14002b198  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002b19d  mov     rdi, rax
0x14002b1a0  mov     ecx, [rax]
0x14002b1a2  cmp     ecx, 2
0x14002b1a5  jbe     loc_14002B233
0x14002b1ab  mov     rdx, 200000000000h
0x14002b1b5  mov     rcx, rax
0x14002b1b8  call    _tlgKeywordOn
0x14002b1bd  test    al, al
0x14002b1bf  jz      short loc_14002B233
0x14002b1c1  mov     rcx, [rbx+110h]
0x14002b1c8  mov     rax, [rcx+38h]
0x14002b1cc  mov     [rbp+57h+arg_10], rax
0x14002b1d0  mov     rax, [rcx+30h]
0x14002b1d4  mov     [rbp+57h+arg_18], rax
0x14002b1d8  call    cs:__imp_GetCurrentThreadId
0x14002b1de  mov     r8, [rbx+110h]
0x14002b1e5  lea     rdx, unk_14008C578
0x14002b1ec  mov     [rbp+57h+arg_8], eax
0x14002b1ef  add     r8, 8
0x14002b1f3  lea     rax, [rbp+57h+arg_10]
0x14002b1f7  mov     [rbp+57h+arg_0], esi
0x14002b1fa  mov     [rsp+110h+var_D0], rax
0x14002b1ff  mov     rcx, rdi
0x14002b202  lea     rax, [rbp+57h+arg_18]
0x14002b206  mov     [rbp+57h+var_68], 1000000h
0x14002b20e  mov     [rsp+110h+var_D8], rax
0x14002b213  lea     rax, [rbp+57h+arg_8]
0x14002b217  mov     [rsp+110h+var_E0], rax
0x14002b21c  lea     rax, [rbp+57h+arg_0]
0x14002b220  mov     [rsp+110h+var_E8], rax
0x14002b225  lea     rax, [rbp+57h+var_68]
0x14002b229  mov     [rsp+110h+var_F0], rax
0x14002b22e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14002b233  mov     rax, [rbx]
0x14002b236  mov     rcx, rbx
0x14002b239  mov     rax, [rax+8]
0x14002b23d  add     rsp, 0F8h
0x14002b244  pop     rdi
0x14002b245  pop     rsi
0x14002b246  pop     rbx
0x14002b247  pop     rbp
0x14002b248  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
