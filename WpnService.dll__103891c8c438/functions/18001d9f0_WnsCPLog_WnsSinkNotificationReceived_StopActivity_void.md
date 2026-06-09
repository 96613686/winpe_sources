# WnsCPLog::WnsSinkNotificationReceived::StopActivity(void)

- ea: `0x18001d9f0`
- end: `0x18001dc17`
- name: `?StopActivity@WnsSinkNotificationReceived@WnsCPLog@@MEAAXXZ`
- size: `551`
- prototype: `void __fastcall(WnsCPLog::WnsSinkNotificationReceived *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001e64`
- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180013130`
- `0x180018430`
- `0x18001d9f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dbb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dbb5`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkNotificationReceived::StopActivity(WnsCPLog::WnsSinkNotificationReceived *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v20; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = WnsCPTracelogger::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6, v5) )
    {
      v8 = *((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v19 = *((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)byte_180042761,
        v9 + 8,
        v7,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = WnsCPTracelogger::Provider();
    v13 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL, v11, v12) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v15 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned __int8 *)byte_180042705,
        (const GUID *)(v15 + 8),
        0,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001d9f0  push    rbp
0x18001d9f2  push    rbx
0x18001d9f3  push    rdi
0x18001d9f4  lea     rbp, [rsp-47h]
0x18001d9f9  sub     rsp, 100h
0x18001da00  mov     rdi, [rcx+110h]
0x18001da07  mov     rbx, rcx
0x18001da0a  mov     eax, [rdi+48h]
0x18001da0d  test    eax, eax
0x18001da0f  jns     loc_18001DB8B
0x18001da15  add     rdi, 50h ; 'P'
0x18001da19  cmp     eax, [rdi+8]
0x18001da1c  jnz     loc_18001DB8B
0x18001da22  test    rdi, rdi
0x18001da25  jz      loc_18001DB8B
0x18001da2b  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001da30  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001da35  mov     r9, rax
0x18001da38  mov     ecx, [rax]
0x18001da3a  cmp     ecx, 5
0x18001da3d  jbe     loc_18001DC05
0x18001da43  mov     rdx, 200000000000h
0x18001da4d  mov     rcx, rax
0x18001da50  call    _tlgKeywordOn
0x18001da55  test    al, al
0x18001da57  jz      loc_18001DC05
0x18001da5d  mov     rax, [rdi+70h]
0x18001da61  lea     rdx, byte_180042761
0x18001da68  mov     rcx, [rdi+78h]
0x18001da6c  mov     r8, [rbx+110h]
0x18001da73  mov     [rbp+57h+var_60], rax
0x18001da77  add     r8, 8
0x18001da7b  mov     eax, [rdi+68h]
0x18001da7e  mov     [rbp+57h+arg_0], eax
0x18001da81  mov     rax, [rdi+60h]
0x18001da85  mov     [rbp+57h+var_58], rax
0x18001da89  mov     rax, [rdi+58h]
0x18001da8d  mov     [rbp+57h+var_50], rax
0x18001da91  mov     eax, [rdi+50h]
0x18001da94  mov     [rbp+57h+arg_8], eax
0x18001da97  mov     rax, [rdi+48h]
0x18001da9b  mov     [rbp+57h+var_48], rax
0x18001da9f  mov     eax, [rdi+20h]
0x18001daa2  mov     dword ptr [rbp+57h+arg_10], eax
0x18001daa5  mov     rax, [rdi+18h]
0x18001daa9  mov     [rbp+57h+var_40], rax
0x18001daad  mov     eax, [rdi]
0x18001daaf  mov     [rbp+57h+arg_18], eax
0x18001dab2  mov     rax, [rdi+80h]
0x18001dab9  mov     [rbp+57h+var_38], rax
0x18001dabd  mov     eax, [rdi+40h]
0x18001dac0  mov     [rbp+57h+var_70], eax
0x18001dac3  mov     rax, [rdi+38h]
0x18001dac7  mov     [rbp+57h+var_30], rax
0x18001dacb  mov     eax, [rdi+8]
0x18001dace  mov     [rbp+57h+var_6C], eax
0x18001dad1  lea     rax, [rbp+57h+var_68]
0x18001dad5  mov     [rsp+110h+var_78], rax
0x18001dadd  lea     rax, [rbp+57h+var_60]
0x18001dae1  mov     [rsp+110h+var_80], rax
0x18001dae9  lea     rax, [rbp+57h+arg_0]
0x18001daed  mov     [rsp+110h+var_88], rax
0x18001daf5  lea     rax, [rbp+57h+var_58]
0x18001daf9  mov     [rsp+110h+var_90], rax
0x18001db01  lea     rax, [rbp+57h+var_50]
0x18001db05  mov     [rsp+110h+var_98], rax
0x18001db0a  lea     rax, [rbp+57h+arg_8]
0x18001db0e  mov     [rsp+110h+var_A0], rax
0x18001db13  lea     rax, [rbp+57h+var_48]
0x18001db17  mov     [rsp+110h+var_A8], rax
0x18001db1c  lea     rax, [rbp+57h+arg_10]
0x18001db20  mov     [rsp+110h+var_B0], rax
0x18001db25  lea     rax, [rbp+57h+var_40]
0x18001db29  mov     [rsp+110h+var_B8], rax
0x18001db2e  lea     rax, [rbp+57h+arg_18]
0x18001db32  mov     [rsp+110h+var_C0], rax
0x18001db37  lea     rax, [rbp+57h+var_38]
0x18001db3b  mov     [rsp+110h+var_C8], rax
0x18001db40  lea     rax, [rbp+57h+var_70]
0x18001db44  mov     [rsp+110h+var_D0], rax
0x18001db49  lea     rax, [rbp+57h+var_30]
0x18001db4d  mov     [rsp+110h+var_D8], rax
0x18001db52  lea     rax, [rbp+57h+var_6C]
0x18001db56  mov     [rsp+110h+var_E0], rax
0x18001db5b  lea     rax, [rbp+57h+var_28]
0x18001db5f  mov     [rsp+110h+var_E8], rax
0x18001db64  lea     rax, [rbp+57h+var_20]
0x18001db68  mov     [rbp+57h+var_68], rcx
0x18001db6c  mov     rcx, r9
0x18001db6f  mov     [rsp+110h+var_F0], rax
0x18001db74  mov     [rbp+57h+var_28], 1000000h
0x18001db7c  mov     [rbp+57h+var_20], 0
0x18001db84  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001db89  jmp     short loc_18001DC05
0x18001db8b  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001db90  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001db95  mov     rdi, rax
0x18001db98  mov     ecx, [rax]
0x18001db9a  cmp     ecx, 5
0x18001db9d  jbe     short loc_18001DC05
0x18001db9f  mov     rdx, 200000000000h
0x18001dba9  mov     rcx, rax
0x18001dbac  call    _tlgKeywordOn
0x18001dbb1  test    al, al
0x18001dbb3  jz      short loc_18001DC05
0x18001dbb5  call    cs:__imp_GetCurrentThreadId
0x18001dbbb  mov     r8, [rbx+110h]
0x18001dbc2  lea     rdx, byte_180042705
0x18001dbc9  mov     [rbp+57h+arg_0], eax
0x18001dbcc  xor     r9d, r9d
0x18001dbcf  mov     rcx, rdi
0x18001dbd2  mov     eax, [r8+48h]
0x18001dbd6  add     r8, 8
0x18001dbda  mov     [rbp+57h+arg_8], eax
0x18001dbdd  lea     rax, [rbp+57h+arg_0]
0x18001dbe1  mov     [rsp+110h+var_E0], rax
0x18001dbe6  lea     rax, [rbp+57h+arg_8]
0x18001dbea  mov     [rsp+110h+var_E8], rax
0x18001dbef  lea     rax, [rbp+57h+arg_10]
0x18001dbf3  mov     [rsp+110h+var_F0], rax
0x18001dbf8  mov     [rbp+57h+arg_10], 0
0x18001dc00  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001dc05  mov     rcx, rbx
0x18001dc08  add     rsp, 100h
0x18001dc0f  pop     rdi
0x18001dc10  pop     rbx
0x18001dc11  pop     rbp
0x18001dc12  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
