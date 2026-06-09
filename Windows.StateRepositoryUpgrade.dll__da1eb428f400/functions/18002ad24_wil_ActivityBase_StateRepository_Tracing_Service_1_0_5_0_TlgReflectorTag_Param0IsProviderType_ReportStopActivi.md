# wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x18002ad24`
- end: `0x18002af69`
- name: `?ReportStopActivity@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002a898`
- `0x18002b0c0`

## callees

- `0x180001010`
- `0x180001aac`
- `0x1800021f0`
- `0x18000c984`
- `0x18002ad24`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aef4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aef4`

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
  __int64 v8; // r8
  int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  int v14; // edi
  __int64 v15; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  int v18; // r9d
  int v20; // [rsp+A0h] [rbp-19h] BYREF
  int v21; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v22; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v23; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v24; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v25; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v26; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v28; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v29; // [rsp+E0h] [rbp+27h] BYREF
  _QWORD v30[5]; // [rsp+E8h] [rbp+2Fh] BYREF
  int v31; // [rsp+120h] [rbp+67h] BYREF
  DWORD v32; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v33; // [rsp+130h] [rbp+77h] BYREF
  __int64 v34; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = StateRepository::Tracing::Service::Provider();
      if ( *(_DWORD *)v7 > 2u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL, v8) )
      {
        v10 = *(_QWORD *)(v6 + 120);
        v11 = a1[34];
        v24 = *(_QWORD *)(v6 + 112);
        v32 = *(_DWORD *)(v6 + 104);
        v25 = *(_QWORD *)(v6 + 96);
        v26 = *(_QWORD *)(v6 + 88);
        v31 = *(_DWORD *)(v6 + 80);
        v27 = *(_QWORD *)(v6 + 72);
        LODWORD(v33) = *(_DWORD *)(v6 + 32);
        v28 = *(_QWORD *)(v6 + 24);
        LODWORD(v34) = *(_DWORD *)v6;
        v29 = *(_QWORD *)(v6 + 128);
        v20 = *(_DWORD *)(v6 + 64);
        v30[0] = *(_QWORD *)(v6 + 56);
        v21 = *(_DWORD *)(v6 + 8);
        v23 = v10;
        v22 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v9,
          (unsigned int)byte_1800464A1,
          v11 + 8,
          v9,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)v30,
          (__int64)&v20,
          (__int64)&v29,
          (__int64)&v34,
          (__int64)&v28,
          (__int64)&v33,
          (__int64)&v27,
          (__int64)&v31,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v32,
          (__int64)&v24,
          (__int64)&v23);
      }
    }
    else
    {
      v12 = StateRepository::Tracing::Service::Provider();
      v14 = (int)v12;
      if ( *(_DWORD *)v12 > 2u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL, v13) )
      {
        v15 = a1[34];
        v33 = *(_QWORD *)(v15 + 56);
        v34 = *(_QWORD *)(v15 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v17 = a1[34];
        v32 = CurrentThreadId;
        v31 = a2;
        v22 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v14,
          (unsigned int)&unk_1800465B8,
          v17 + 8,
          v18,
          (__int64)&v22,
          (__int64)&v31,
          (__int64)&v32,
          (__int64)&v34,
          (__int64)&v33);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x18002ad24  push    rbp
0x18002ad26  push    rbx
0x18002ad27  push    rsi
0x18002ad28  push    rdi
0x18002ad29  lea     rbp, [rsp-3Fh]
0x18002ad2e  sub     rsp, 0F8h
0x18002ad35  mov     esi, edx
0x18002ad37  mov     rbx, rcx
0x18002ad3a  test    edx, edx
0x18002ad3c  jns     loc_18002AF4F
0x18002ad42  mov     rdi, [rcx+110h]
0x18002ad49  mov     eax, [rdi+48h]
0x18002ad4c  test    eax, eax
0x18002ad4e  jns     loc_18002AEB4
0x18002ad54  add     rdi, 50h ; 'P'
0x18002ad58  cmp     eax, [rdi+8]
0x18002ad5b  jnz     loc_18002AEB4
0x18002ad61  test    rdi, rdi
0x18002ad64  jz      loc_18002AEB4
0x18002ad6a  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x18002ad6f  mov     r9, rax
0x18002ad72  mov     ecx, [rax]
0x18002ad74  cmp     ecx, 2
0x18002ad77  jbe     loc_18002AF4F
0x18002ad7d  mov     rdx, 200000000000h
0x18002ad87  mov     rcx, rax
0x18002ad8a  call    _tlgKeywordOn
0x18002ad8f  test    al, al
0x18002ad91  jz      loc_18002AF4F
0x18002ad97  mov     rax, [rdi+70h]
0x18002ad9b  lea     rdx, byte_1800464A1
0x18002ada2  mov     rcx, [rdi+78h]
0x18002ada6  mov     r8, [rbx+110h]
0x18002adad  mov     [rbp+57h+var_58], rax
0x18002adb1  add     r8, 8
0x18002adb5  mov     eax, [rdi+68h]
0x18002adb8  mov     [rbp+57h+arg_8], eax
0x18002adbb  mov     rax, [rdi+60h]
0x18002adbf  mov     [rbp+57h+var_50], rax
0x18002adc3  mov     rax, [rdi+58h]
0x18002adc7  mov     [rbp+57h+var_48], rax
0x18002adcb  mov     eax, [rdi+50h]
0x18002adce  mov     [rbp+57h+arg_0], eax
0x18002add1  mov     rax, [rdi+48h]
0x18002add5  mov     [rbp+57h+var_40], rax
0x18002add9  mov     eax, [rdi+20h]
0x18002addc  mov     dword ptr [rbp+57h+arg_10], eax
0x18002addf  mov     rax, [rdi+18h]
0x18002ade3  mov     [rbp+57h+var_38], rax
0x18002ade7  mov     eax, [rdi]
0x18002ade9  mov     dword ptr [rbp+57h+arg_18], eax
0x18002adec  mov     rax, [rdi+80h]
0x18002adf3  mov     [rbp+57h+var_30], rax
0x18002adf7  mov     eax, [rdi+40h]
0x18002adfa  mov     [rbp+57h+var_70], eax
0x18002adfd  mov     rax, [rdi+38h]
0x18002ae01  mov     [rbp+57h+var_28], rax
0x18002ae05  mov     eax, [rdi+8]
0x18002ae08  mov     [rbp+57h+var_6C], eax
0x18002ae0b  lea     rax, [rbp+57h+var_60]
0x18002ae0f  mov     [rsp+110h+var_80], rax
0x18002ae17  lea     rax, [rbp+57h+var_58]
0x18002ae1b  mov     [rsp+110h+var_88], rax
0x18002ae23  lea     rax, [rbp+57h+arg_8]
0x18002ae27  mov     [rsp+110h+var_90], rax
0x18002ae2f  lea     rax, [rbp+57h+var_50]
0x18002ae33  mov     [rsp+110h+var_98], rax
0x18002ae38  lea     rax, [rbp+57h+var_48]
0x18002ae3c  mov     [rsp+110h+var_A0], rax
0x18002ae41  lea     rax, [rbp+57h+arg_0]
0x18002ae45  mov     [rsp+110h+var_A8], rax
0x18002ae4a  lea     rax, [rbp+57h+var_40]
0x18002ae4e  mov     [rsp+110h+var_B0], rax
0x18002ae53  lea     rax, [rbp+57h+arg_10]
0x18002ae57  mov     [rsp+110h+var_B8], rax
0x18002ae5c  lea     rax, [rbp+57h+var_38]
0x18002ae60  mov     [rsp+110h+var_C0], rax
0x18002ae65  lea     rax, [rbp+57h+arg_18]
0x18002ae69  mov     [rsp+110h+var_C8], rax
0x18002ae6e  lea     rax, [rbp+57h+var_30]
0x18002ae72  mov     [rsp+110h+var_D0], rax
0x18002ae77  lea     rax, [rbp+57h+var_70]
0x18002ae7b  mov     [rsp+110h+var_D8], rax
0x18002ae80  lea     rax, [rbp+57h+var_28]
0x18002ae84  mov     [rsp+110h+var_E0], rax
0x18002ae89  lea     rax, [rbp+57h+var_6C]
0x18002ae8d  mov     [rsp+110h+var_E8], rax
0x18002ae92  lea     rax, [rbp+57h+var_68]
0x18002ae96  mov     [rbp+57h+var_60], rcx
0x18002ae9a  mov     rcx, r9
0x18002ae9d  mov     [rsp+110h+var_F0], rax
0x18002aea2  mov     [rbp+57h+var_68], 1000000h
0x18002aeaa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002aeaf  jmp     loc_18002AF4F
0x18002aeb4  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x18002aeb9  mov     rdi, rax
0x18002aebc  mov     ecx, [rax]
0x18002aebe  cmp     ecx, 2
0x18002aec1  jbe     loc_18002AF4F
0x18002aec7  mov     rdx, 200000000000h
0x18002aed1  mov     rcx, rax
0x18002aed4  call    _tlgKeywordOn
0x18002aed9  test    al, al
0x18002aedb  jz      short loc_18002AF4F
0x18002aedd  mov     rcx, [rbx+110h]
0x18002aee4  mov     rax, [rcx+38h]
0x18002aee8  mov     [rbp+57h+arg_10], rax
0x18002aeec  mov     rax, [rcx+30h]
0x18002aef0  mov     [rbp+57h+arg_18], rax
0x18002aef4  call    cs:__imp_GetCurrentThreadId
0x18002aefa  mov     r8, [rbx+110h]
0x18002af01  lea     rdx, unk_1800465B8
0x18002af08  mov     [rbp+57h+arg_8], eax
0x18002af0b  add     r8, 8
0x18002af0f  lea     rax, [rbp+57h+arg_10]
0x18002af13  mov     [rbp+57h+arg_0], esi
0x18002af16  mov     [rsp+110h+var_D0], rax
0x18002af1b  mov     rcx, rdi
0x18002af1e  lea     rax, [rbp+57h+arg_18]
0x18002af22  mov     [rbp+57h+var_68], 1000000h
0x18002af2a  mov     [rsp+110h+var_D8], rax
0x18002af2f  lea     rax, [rbp+57h+arg_8]
0x18002af33  mov     [rsp+110h+var_E0], rax
0x18002af38  lea     rax, [rbp+57h+arg_0]
0x18002af3c  mov     [rsp+110h+var_E8], rax
0x18002af41  lea     rax, [rbp+57h+var_68]
0x18002af45  mov     [rsp+110h+var_F0], rax
0x18002af4a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002af4f  mov     rax, [rbx]
0x18002af52  mov     rcx, rbx
0x18002af55  mov     rax, [rax+8]
0x18002af59  add     rsp, 0F8h
0x18002af60  pop     rdi
0x18002af61  pop     rsi
0x18002af62  pop     rbx
0x18002af63  pop     rbp
0x18002af64  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
