# Broker::TimeEvent::SignalEvent(__int64)

- ea: `0x1800188a0`
- end: `0x180018b03`
- name: `?SignalEvent@TimeEvent@Broker@@MEAAX_J@Z`
- size: `611`
- prototype: `void __fastcall(Broker::TimeEvent *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000a0b0`
- `0x18000ba98`
- `0x18000c500`
- `0x18000c9b8`
- `0x18000ee60`
- `0x1800188a0`
- `0x18001c010`

## import_xrefs

- `BrokerLib!BrSignalBrokerEvent2` at `0x180018996`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180018996`

## pseudocode

```c
void __fastcall Broker::TimeEvent::SignalEvent(Broker::TimeEvent *this, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v3; // r14
  int v4; // r15d
  __int128 v7; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rax
  int v10; // eax
  int v11; // esi
  unsigned __int8 v12; // al
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned __int64 v16; // [rsp+60h] [rbp-9h]
  __int64 v17; // [rsp+68h] [rbp-1h] BYREF
  int *v18; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int64 v19; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v20[8]; // [rsp+80h] [rbp+17h] BYREF
  int v21; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v22; // [rsp+D8h] [rbp+6Fh] BYREF
  int v23; // [rsp+E0h] [rbp+77h] BYREF
  int *v24; // [rsp+E8h] [rbp+7Fh] BYREF

  v22 = a2;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v7 = (__int64)(*((_QWORD *)this + 3) + *((_QWORD *)this + 4));
    WPP_SF__guid_Lidd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((_QWORD *)&v7 + 1),
      *((_QWORD *)this + 7) / 10000000LL,
      *((_QWORD *)this + 31),
      *((_DWORD *)this + 18),
      (__int64)v7 / 2,
      *((_QWORD *)this + 7) / 10000000LL,
      (int)*((_QWORD *)this + 6) / 600000000);
  }
  *((_QWORD *)this + 5) = a2;
  v8 = *((_QWORD *)this + 32);
  v9 = *((_QWORD *)this + 33) - v8;
  if ( v9 > 0x10 )
  {
    v2 = *((_QWORD *)this + 32);
    v3 = v8 + 16;
    v4 = v9 - 16;
  }
  v10 = BrSignalBrokerEvent2(*((_QWORD *)this + 30), *((_QWORD *)this + 31), 0, v2, v4, v3);
  v11 = v10;
  if ( v10 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids,
      *((_QWORD *)this + 31),
      v10);
  if ( !*((_DWORD *)this + 18) && *((_QWORD *)this + 6) != 25920000000000LL )
  {
    v24 = (int *)*((_QWORD *)this + 4);
    v17 = *((_QWORD *)this + 3);
    v16 = __PAIR64__(HIDWORD(v22), a2);
    if ( (unsigned int)dword_180026058 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180026058, 0x400000000000LL) )
      {
        LODWORD(v22) = v11;
        v21 = (unsigned __int8)Broker::TimeEvent::GetOnLockScreen(this);
        v12 = (*(__int64 (__fastcall **)(Broker::TimeEvent *))(*(_QWORD *)this + 48LL))(this);
        v13 = *((_QWORD *)this + 31);
        v23 = v12;
        v18 = v24;
        v19 = v16;
        v20[0] = v17;
        v24 = *(int **)(v13 + 24);
        v17 = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v13,
          (__int64)&byte_180020BAF,
          v14,
          v15,
          &v17,
          &v24,
          (__int64)v20,
          (__int64)&v19,
          (__int64)&v18,
          (__int64)&v23,
          (__int64)&v21,
          (__int64)&v22);
      }
    }
  }
}

```

## disassembly

```asm
0x1800188a0  mov     [rsp-8+arg_8], rdx
0x1800188a5  push    rbp
0x1800188a6  push    rbx
0x1800188a7  push    rsi
0x1800188a8  push    rdi
0x1800188a9  push    r14
0x1800188ab  push    r15
0x1800188ad  lea     rbp, [rsp-2Fh]
0x1800188b2  sub     rsp, 98h
0x1800188b9  xor     esi, esi
0x1800188bb  xor     r14d, r14d
0x1800188be  xor     r15d, r15d
0x1800188c1  mov     rdi, rdx
0x1800188c4  mov     rbx, rcx
0x1800188c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800188ce  test    byte ptr [rcx+1Ch], 40h
0x1800188d2  jz      short loc_180018952
0x1800188d4  cmp     byte ptr [rcx+19h], 5
0x1800188d8  jb      short loc_180018952
0x1800188da  mov     rcx, [rcx+10h]
0x1800188de  mov     rax, 1CA213D840BAF7D5h
0x1800188e8  imul    qword ptr [rbx+30h]
0x1800188ec  mov     r9, rdx
0x1800188ef  sar     r9, 1Ah
0x1800188f3  mov     rax, r9
0x1800188f6  shr     rax, 3Fh
0x1800188fa  add     r9, rax
0x1800188fd  mov     rax, 0D6BF94D5E57A42BDh
0x180018907  imul    qword ptr [rbx+38h]
0x18001890b  mov     dword ptr [rsp+0C0h+var_88], r9d
0x180018910  mov     r9, [rbx+0F8h]
0x180018917  mov     r8, rdx
0x18001891a  add     r8, [rbx+38h]
0x18001891e  sar     r8, 17h
0x180018922  mov     rax, r8
0x180018925  shr     rax, 3Fh
0x180018929  add     r8, rax
0x18001892c  mov     rax, [rbx+20h]
0x180018930  add     rax, [rbx+18h]
0x180018934  cqo
0x180018936  mov     dword ptr [rsp+0C0h+var_90], r8d
0x18001893b  sub     rax, rdx
0x18001893e  sar     rax, 1
0x180018941  mov     [rsp+0C0h+var_98], rax
0x180018946  mov     eax, [rbx+48h]
0x180018949  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18001894d  call    WPP_SF__guid_Lidd
0x180018952  mov     [rbx+28h], rdi
0x180018956  mov     rcx, [rbx+100h]
0x18001895d  mov     rax, [rbx+108h]
0x180018964  sub     rax, rcx
0x180018967  cmp     rax, 10h
0x18001896b  jbe     short loc_180018978
0x18001896d  mov     rsi, rcx
0x180018970  lea     r14, [rcx+10h]
0x180018974  lea     r15d, [rax-10h]
0x180018978  mov     rdx, [rbx+0F8h]
0x18001897f  mov     r9, rsi
0x180018982  mov     rcx, [rbx+0F0h]
0x180018989  xor     r8d, r8d
0x18001898c  mov     [rsp+0C0h+var_98], r14
0x180018991  mov     dword ptr [rsp+0C0h+var_A0], r15d
0x180018996  call    cs:__imp_BrSignalBrokerEvent2
0x18001899c  mov     esi, eax
0x18001899e  test    eax, eax
0x1800189a0  jz      short loc_1800189D5
0x1800189a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189a9  test    byte ptr [rcx+1Ch], 40h
0x1800189ad  jz      short loc_1800189D5
0x1800189af  cmp     byte ptr [rcx+19h], 5
0x1800189b3  jb      short loc_1800189D5
0x1800189b5  mov     r9, [rbx+0F8h]
0x1800189bc  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x1800189c3  mov     rcx, [rcx+10h]
0x1800189c7  mov     edx, 16h
0x1800189cc  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800189d0  call    WPP_SF__guid_d
0x1800189d5  cmp     dword ptr [rbx+48h], 0
0x1800189d9  jnz     loc_180018AF3
0x1800189df  mov     rax, 1792F8648000h
0x1800189e9  cmp     [rbx+30h], rax
0x1800189ed  jz      loc_180018AF3
0x1800189f3  mov     rax, [rbx+20h]
0x1800189f7  mov     rcx, rax
0x1800189fa  mov     dword ptr [rbp+57h+arg_18], eax
0x1800189fd  mov     rax, [rbx+18h]
0x180018a01  shr     rcx, 20h
0x180018a05  mov     dword ptr [rbp+57h+arg_18+4], ecx
0x180018a0b  mov     rcx, rax
0x180018a0e  mov     dword ptr [rbp+57h+var_58], eax
0x180018a11  mov     eax, dword ptr [rbp+57h+arg_8+4]
0x180018a14  shr     rcx, 20h
0x180018a18  mov     dword ptr [rbp+57h+var_60+4], eax
0x180018a1b  mov     eax, cs:dword_180026058
0x180018a21  mov     dword ptr [rbp+57h+var_58+4], ecx
0x180018a24  mov     dword ptr [rbp+57h+var_60], edi
0x180018a27  cmp     eax, 5
0x180018a2a  jbe     loc_180018AF3
0x180018a30  mov     rdx, 400000000000h
0x180018a3a  lea     rcx, dword_180026058
0x180018a41  call    _tlgKeywordOn
0x180018a46  test    al, al
0x180018a48  jz      loc_180018AF3
0x180018a4e  mov     rcx, rbx; this
0x180018a51  mov     dword ptr [rbp+57h+arg_8], esi
0x180018a54  call    ?GetOnLockScreen@TimeEvent@Broker@@QEAA_NXZ; Broker::TimeEvent::GetOnLockScreen(void)
0x180018a59  movzx   eax, al
0x180018a5c  mov     rcx, rbx
0x180018a5f  mov     [rbp+57h+arg_0], eax
0x180018a62  mov     rax, [rbx]
0x180018a65  mov     rax, [rax+30h]
0x180018a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a6e  mov     rcx, [rbx+0F8h]
0x180018a75  lea     rdx, byte_180020BAF
0x180018a7c  movzx   eax, al
0x180018a7f  mov     [rbp+57h+arg_10], eax
0x180018a82  mov     rax, [rbp+57h+arg_18]
0x180018a86  mov     [rbp+57h+var_50], rax
0x180018a8a  mov     rax, [rbp+57h+var_60]
0x180018a8e  mov     [rbp+57h+var_48], rax
0x180018a92  mov     rax, [rbp+57h+var_58]
0x180018a96  mov     [rbp+57h+var_40], rax
0x180018a9a  mov     rax, [rcx+18h]
0x180018a9e  mov     [rbp+57h+arg_18], rax
0x180018aa2  lea     rax, [rbp+57h+arg_8]
0x180018aa6  mov     [rsp+0C0h+var_68], rax
0x180018aab  lea     rax, [rbp+57h+arg_0]
0x180018aaf  mov     [rsp+0C0h+var_70], rax
0x180018ab4  lea     rax, [rbp+57h+arg_10]
0x180018ab8  mov     [rsp+0C0h+var_78], rax
0x180018abd  lea     rax, [rbp+57h+var_50]
0x180018ac1  mov     [rsp+0C0h+var_80], rax
0x180018ac6  lea     rax, [rbp+57h+var_48]
0x180018aca  mov     [rsp+0C0h+var_88], rax
0x180018acf  lea     rax, [rbp+57h+var_40]
0x180018ad3  mov     [rsp+0C0h+var_90], rax
0x180018ad8  lea     rax, [rbp+57h+arg_18]
0x180018adc  mov     [rsp+0C0h+var_98], rax
0x180018ae1  lea     rax, [rbp+57h+var_58]
0x180018ae5  mov     [rsp+0C0h+var_A0], rax
0x180018aea  mov     [rbp+57h+var_58], rcx
0x180018aee  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U3@U3@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@55AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018af3  add     rsp, 98h
0x180018afa  pop     r15
0x180018afc  pop     r14
0x180018afe  pop     rdi
0x180018aff  pop     rsi
0x180018b00  pop     rbx
0x180018b01  pop     rbp
0x180018b02  retn
```
