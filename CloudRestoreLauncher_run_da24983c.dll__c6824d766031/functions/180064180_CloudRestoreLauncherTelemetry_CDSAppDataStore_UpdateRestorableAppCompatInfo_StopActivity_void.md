# CloudRestoreLauncherTelemetry::CDSAppDataStore_UpdateRestorableAppCompatInfo::StopActivity(void)

- ea: `0x180064180`
- end: `0x1800643af`
- name: `?StopActivity@CDSAppDataStore_UpdateRestorableAppCompatInfo@CloudRestoreLauncherTelemetry@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(CloudRestoreLauncherTelemetry::CDSAppDataStore_UpdateRestorableAppCompatInfo *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001314`
- `0x180001698`
- `0x180018674`
- `0x1800195cc`
- `0x18001e020`
- `0x180064180`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18006434d`
- `KERNEL32!GetCurrentThreadId` at `0x18006434d`

## pseudocode

```c
void __fastcall CloudRestoreLauncherTelemetry::CDSAppDataStore_UpdateRestorableAppCompatInfo::StopActivity(
        CloudRestoreLauncherTelemetry::CDSAppDataStore_UpdateRestorableAppCompatInfo *this)
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
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = CloudRestoreLauncherTelemetry::Provider();
    if ( *(_DWORD *)v7 > 5u )
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
        (unsigned int)&unk_180153C6D,
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
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = CloudRestoreLauncherTelemetry::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v13 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)&unk_180153DD5,
        v13 + 8,
        0,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x180064180  push    rbp
0x180064182  push    rbx
0x180064183  push    rdi
0x180064184  lea     rbp, [rsp+10h]
0x180064189  sub     rsp, 130h
0x180064190  mov     rdi, [rcx+110h]
0x180064197  mov     rbx, rcx
0x18006419a  mov     eax, [rdi+48h]
0x18006419d  test    eax, eax
0x18006419f  jns     loc_180064339
0x1800641a5  add     rdi, 50h ; 'P'
0x1800641a9  cmp     eax, [rdi+8]
0x1800641ac  jnz     loc_180064339
0x1800641b2  test    rdi, rdi
0x1800641b5  jz      loc_180064339
0x1800641bb  call    ?zInternalStop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800641c0  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x1800641c5  mov     r9, rax
0x1800641c8  mov     ecx, [rax]
0x1800641ca  cmp     ecx, 5
0x1800641cd  jbe     loc_18006439D
0x1800641d3  mov     rax, [rdi+70h]
0x1800641d7  lea     rdx, unk_180153C6D
0x1800641de  mov     rcx, [rdi+30h]
0x1800641e2  mov     [rbp+var_60], rax
0x1800641e6  mov     eax, [rdi+68h]
0x1800641e9  mov     r8, [rbx+110h]
0x1800641f0  mov     dword ptr [rbp+arg_10], eax
0x1800641f3  add     r8, 8
0x1800641f7  mov     rax, [rdi+60h]
0x1800641fb  mov     [rbp+var_58], rax
0x1800641ff  mov     rax, [rdi+58h]
0x180064203  mov     [rbp+var_50], rax
0x180064207  mov     eax, [rdi+50h]
0x18006420a  mov     [rbp+arg_18], eax
0x18006420d  mov     rax, [rdi+48h]
0x180064211  mov     [rbp+var_48], rax
0x180064215  mov     eax, [rdi+20h]
0x180064218  mov     [rbp+var_80], eax
0x18006421b  mov     rax, [rdi+18h]
0x18006421f  mov     [rbp+var_40], rax
0x180064223  mov     eax, [rdi]
0x180064225  mov     [rbp+var_7C], eax
0x180064228  mov     rax, [rdi+80h]
0x18006422f  mov     [rbp+var_38], rax
0x180064233  mov     eax, [rdi+40h]
0x180064236  mov     [rbp+var_78], eax
0x180064239  mov     rax, [rdi+38h]
0x18006423d  mov     [rbp+var_30], rax
0x180064241  mov     eax, [rdi+8]
0x180064244  mov     [rbp+var_74], eax
0x180064247  lea     rax, [rbp+var_70]
0x18006424b  mov     [rsp+140h+var_90], rax
0x180064253  lea     rax, [rbp+arg_0]
0x180064257  mov     [rsp+140h+var_98], rax
0x18006425f  lea     rax, [rbp+arg_8]
0x180064263  mov     [rsp+140h+var_A0], rax
0x18006426b  lea     rax, [rbp+var_68]
0x18006426f  mov     [rsp+140h+var_A8], rax
0x180064277  lea     rax, [rbp+var_60]
0x18006427b  mov     [rsp+140h+var_B0], rax
0x180064283  lea     rax, [rbp+arg_10]
0x180064287  mov     [rsp+140h+var_B8], rax
0x18006428f  lea     rax, [rbp+var_58]
0x180064293  mov     [rsp+140h+var_C0], rax
0x18006429b  lea     rax, [rbp+var_50]
0x18006429f  mov     [rsp+140h+var_C8], rax
0x1800642a4  lea     rax, [rbp+arg_18]
0x1800642a8  mov     [rsp+140h+var_D0], rax
0x1800642ad  lea     rax, [rbp+var_48]
0x1800642b1  mov     [rsp+140h+var_D8], rax
0x1800642b6  lea     rax, [rbp+var_80]
0x1800642ba  mov     [rsp+140h+var_E0], rax
0x1800642bf  lea     rax, [rbp+var_40]
0x1800642c3  mov     [rsp+140h+var_E8], rax
0x1800642c8  lea     rax, [rbp+var_7C]
0x1800642cc  mov     [rsp+140h+var_F0], rax
0x1800642d1  lea     rax, [rbp+var_38]
0x1800642d5  mov     [rsp+140h+var_F8], rax
0x1800642da  lea     rax, [rbp+var_78]
0x1800642de  mov     [rsp+140h+var_100], rax
0x1800642e3  lea     rax, [rbp+var_30]
0x1800642e7  mov     [rsp+140h+var_108], rax
0x1800642ec  lea     rax, [rbp+var_74]
0x1800642f0  mov     [rbp+var_70], rcx
0x1800642f4  mov     ecx, [rdi+44h]
0x1800642f7  mov     [rsp+140h+var_110], rax
0x1800642fc  lea     rax, [rbp+var_28]
0x180064300  mov     [rbp+arg_0], ecx
0x180064303  mov     ecx, [rdi+10h]
0x180064306  mov     [rbp+arg_8], ecx
0x180064309  mov     rcx, [rdi+78h]
0x18006430d  mov     [rsp+140h+var_118], rax
0x180064312  lea     rax, [rbp+var_20]
0x180064316  mov     [rbp+var_68], rcx
0x18006431a  mov     rcx, r9
0x18006431d  mov     [rsp+140h+var_120], rax
0x180064322  mov     [rbp+var_28], 1000000h
0x18006432a  mov     [rbp+var_20], 0
0x180064332  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180064337  jmp     short loc_18006439D
0x180064339  call    ?zInternalStop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18006433e  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x180064343  mov     rdi, rax
0x180064346  mov     ecx, [rax]
0x180064348  cmp     ecx, 5
0x18006434b  jbe     short loc_18006439D
0x18006434d  call    cs:__imp_GetCurrentThreadId
0x180064353  mov     r8, [rbx+110h]
0x18006435a  lea     rdx, unk_180153DD5
0x180064361  mov     [rbp+arg_0], eax
0x180064364  xor     r9d, r9d
0x180064367  lea     rax, [rbp+arg_0]
0x18006436b  mov     [rsp+140h+var_110], rax
0x180064370  lea     rax, [rbp+arg_8]
0x180064374  mov     ecx, [r8+48h]
0x180064378  add     r8, 8
0x18006437c  mov     [rsp+140h+var_118], rax
0x180064381  lea     rax, [rbp+arg_10]
0x180064385  mov     [rbp+arg_8], ecx
0x180064388  mov     rcx, rdi
0x18006438b  mov     [rsp+140h+var_120], rax
0x180064390  mov     [rbp+arg_10], 0
0x180064398  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006439d  mov     rcx, rbx
0x1800643a0  add     rsp, 130h
0x1800643a7  pop     rdi
0x1800643a8  pop     rbx
0x1800643a9  pop     rbp
0x1800643aa  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
