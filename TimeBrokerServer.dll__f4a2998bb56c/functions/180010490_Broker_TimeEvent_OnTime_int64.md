# Broker::TimeEvent::OnTime(__int64)

- ea: `0x180010490`
- end: `0x180010904`
- name: `?OnTime@TimeEvent@Broker@@QEAA?AW4_TimeEventStatus@2@_J@Z`
- size: `1140`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000fe70`

## callees

- `0x1800011b0`
- `0x180001500`
- `0x180009710`
- `0x180009ea0`
- `0x18000c500`
- `0x18000ee60`
- `0x180010490`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Broker::TimeEvent::OnTime(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v5; // rcx
  unsigned int v6; // esi
  unsigned __int8 v7; // al
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // kr00_8
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 *v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  unsigned __int8 v22; // al
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // kr08_8
  __int64 v26; // r8
  __int64 v27; // r9
  int v29; // [rsp+70h] [rbp-9h] BYREF
  __int64 v30; // [rsp+78h] [rbp-1h] BYREF
  __int64 v31; // [rsp+80h] [rbp+7h] BYREF
  int *v32; // [rsp+88h] [rbp+Fh] BYREF
  int *v33; // [rsp+90h] [rbp+17h] BYREF
  __int64 v34; // [rsp+98h] [rbp+1Fh] BYREF
  _QWORD v35[6]; // [rsp+A0h] [rbp+27h] BYREF
  __int16 v36; // [rsp+E0h] [rbp+67h] BYREF
  int v37; // [rsp+F0h] [rbp+77h] BYREF
  int v38; // [rsp+F8h] [rbp+7Fh] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, a3, *(_QWORD *)(a1 + 248));
    v5 = WPP_GLOBAL_Control;
  }
  v6 = 1;
  if ( *(_DWORD *)(a1 + 88) == 1 )
  {
    if ( a2 < *(_QWORD *)(a1 + 24) )
    {
      if ( (unsigned int)dword_180026058 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180026058, 0x200000000004LL) )
      {
        v38 = (unsigned __int8)Broker::TimeEvent::GetOnLockScreen((Broker::TimeEvent *)a1);
        v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
        v8 = *(_QWORD *)(a1 + 248);
        v29 = v7;
        v9 = (unsigned __int128)(*(__int64 *)(a1 + 48) * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64;
        v34 = v8;
        v30 = ((unsigned __int64)(*(_QWORD *)(a1 + 48) + v9) >> 63) + ((*(_QWORD *)(a1 + 48) + v9) >> 23);
        v10 = *(_QWORD *)(a1 + 64);
        v36 = *(_WORD *)(a1 + 72);
        LOWORD(v37) = -1;
        v32 = (int *)(a1 + 94);
        v31 = v10 / 10000000;
        v33 = *(int **)(v8 + 24);
        v35[0] = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v8,
          (__int64)byte_180020B11,
          v11,
          v12,
          (__int64)v35,
          &v34,
          &v33,
          &v32,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&v38);
      }
      v5 = WPP_GLOBAL_Control;
    }
    v13 = *(_QWORD *)(a1 + 32);
    v14 = (__int64 *)(a1 + 48);
    if ( a2 < v13 )
    {
      v6 = 0;
      goto LABEL_13;
    }
    if ( a2 < *v14 + v13 )
    {
LABEL_13:
      if ( (unsigned int)dword_180026058 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180026058, 4) )
      {
        v38 = (unsigned __int8)Broker::TimeEvent::GetOnLockScreen((Broker::TimeEvent *)a1);
        v29 = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
        v15 = (unsigned __int128)(*v14 * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64;
        LOWORD(v37) = v6;
        v16 = *(_QWORD *)(a1 + 248);
        v35[0] = ((unsigned __int64)(*v14 + v15) >> 63) + ((*v14 + v15) >> 23);
        v17 = (unsigned __int128)(*(__int64 *)(a1 + 64) * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64;
        v31 = v16;
        v18 = (*(_QWORD *)(a1 + 64) + v17) >> 23;
        v36 = *(_WORD *)(a1 + 72);
        v33 = (int *)(a1 + 94);
        v34 = (v18 >> 63) + v18;
        v32 = *(int **)(v16 + 24);
        v30 = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v16,
          (__int64)&dword_180020C24,
          v19,
          v20,
          (__int64)&v30,
          &v31,
          &v32,
          &v33,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v34,
          (__int64)v35,
          (__int64)&v29,
          (__int64)&v38);
      }
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 64LL))(a1, a2);
      v21 = 2;
      goto LABEL_26;
    }
    v6 = 2;
    if ( (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 3u )
      WPP_SF__guid_(v5[2], 16, a3, *(_QWORD *)(a1 + 248));
    if ( (unsigned int)dword_180026058 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180026058, 0x400000000004LL) )
    {
      v37 = (unsigned __int8)Broker::TimeEvent::GetOnLockScreen((Broker::TimeEvent *)a1);
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 48LL))(a1);
      v23 = *(_QWORD *)(a1 + 248);
      v38 = v22;
      v24 = (unsigned __int128)(*v14 * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64;
      v31 = v23;
      v35[0] = ((unsigned __int64)(*v14 + v24) >> 63) + ((*v14 + v24) >> 23);
      v25 = *(_QWORD *)(a1 + 64);
      v36 = *(_WORD *)(a1 + 72);
      v33 = (int *)(a1 + 94);
      v34 = v25 / 10000000;
      v32 = *(int **)(v23 + 24);
      v30 = v23;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v23,
        (__int64)&byte_180020A7F,
        v26,
        v27,
        (__int64)&v30,
        &v31,
        &v32,
        &v33,
        (__int64)&v36,
        (__int64)&v34,
        (__int64)v35,
        (__int64)&v38,
        (__int64)&v37);
    }
    *(_QWORD *)(a1 + 40) = a2;
    Broker::TimeEvent::SetState(a1, 2);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 72LL))(a1, a2);
  }
  else
  {
    v6 = -1;
    if ( *(_DWORD *)(a1 + 88) == 2 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 64LL))(a1, a2);
      v21 = 5;
LABEL_26:
      Broker::TimeEvent::SetState(a1, v21);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180010490  mov     [rsp-8+arg_8], rbx
0x180010495  push    rbp
0x180010496  push    rsi
0x180010497  push    rdi
0x180010498  push    r13
0x18001049a  push    r14
0x18001049c  lea     rbp, [rsp-37h]
0x1800104a1  sub     rsp, 0B0h
0x1800104a8  mov     rdi, rdx
0x1800104ab  mov     rbx, rcx
0x1800104ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104b5  test    byte ptr [rcx+1Ch], 40h
0x1800104b9  jz      short loc_1800104DD
0x1800104bb  cmp     byte ptr [rcx+19h], 5
0x1800104bf  jb      short loc_1800104DD
0x1800104c1  mov     r9, [rbx+0F8h]
0x1800104c8  mov     edx, 0Fh
0x1800104cd  mov     rcx, [rcx+10h]
0x1800104d1  call    WPP_SF__guid_
0x1800104d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104dd  mov     esi, 1
0x1800104e2  cmp     [rbx+58h], esi
0x1800104e5  jnz     loc_1800108C5
0x1800104eb  mov     r13, 0D6BF94D5E57A42BDh
0x1800104f5  cmp     rdi, [rbx+18h]
0x1800104f9  jge     loc_180010626
0x1800104ff  mov     eax, cs:dword_180026058
0x180010505  cmp     eax, 5
0x180010508  jbe     loc_18001061F
0x18001050e  mov     rdx, 200000000004h
0x180010518  lea     rcx, dword_180026058
0x18001051f  call    _tlgKeywordOn
0x180010524  test    al, al
0x180010526  jz      loc_18001061F
0x18001052c  mov     rcx, rbx; this
0x18001052f  call    ?GetOnLockScreen@TimeEvent@Broker@@QEAA_NXZ; Broker::TimeEvent::GetOnLockScreen(void)
0x180010534  movzx   eax, al
0x180010537  mov     rcx, rbx
0x18001053a  mov     [rbp+57h+arg_18], eax
0x18001053d  mov     rax, [rbx]
0x180010540  mov     rax, [rax+30h]
0x180010544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010549  mov     rcx, [rbx+0F8h]
0x180010550  movzx   eax, al
0x180010553  mov     [rbp+57h+var_60], eax
0x180010556  mov     rax, r13
0x180010559  imul    qword ptr [rbx+30h]
0x18001055d  mov     [rbp+57h+var_38], rcx
0x180010561  add     rdx, [rbx+30h]
0x180010565  sar     rdx, 17h
0x180010569  mov     rax, rdx
0x18001056c  shr     rax, 3Fh
0x180010570  add     rdx, rax
0x180010573  mov     rax, r13
0x180010576  mov     [rbp+57h+var_58], rdx
0x18001057a  imul    qword ptr [rbx+40h]
0x18001057e  add     rdx, [rbx+40h]
0x180010582  sar     rdx, 17h
0x180010586  mov     rax, rdx
0x180010589  shr     rax, 3Fh
0x18001058d  add     rdx, rax
0x180010590  movzx   eax, word ptr [rbx+48h]
0x180010594  mov     [rbp+57h+arg_0], ax
0x180010598  mov     eax, 0FFFFh
0x18001059d  mov     word ptr [rbp+57h+arg_10], ax
0x1800105a1  lea     rax, [rbx+5Eh]
0x1800105a5  mov     [rbp+57h+var_48], rax
0x1800105a9  mov     [rbp+57h+var_50], rdx
0x1800105ad  lea     rdx, byte_180020B11
0x1800105b4  mov     rax, [rcx+18h]
0x1800105b8  mov     [rbp+57h+var_40], rax
0x1800105bc  lea     rax, [rbp+57h+arg_18]
0x1800105c0  mov     [rsp+0D0h+var_68], rax
0x1800105c5  lea     rax, [rbp+57h+var_60]
0x1800105c9  mov     [rsp+0D0h+var_70], rax
0x1800105ce  lea     rax, [rbp+57h+var_58]
0x1800105d2  mov     [rsp+0D0h+var_78], rax
0x1800105d7  lea     rax, [rbp+57h+var_50]
0x1800105db  mov     [rsp+0D0h+var_80], rax
0x1800105e0  lea     rax, [rbp+57h+arg_0]
0x1800105e4  mov     [rsp+0D0h+var_88], rax
0x1800105e9  lea     rax, [rbp+57h+arg_10]
0x1800105ed  mov     [rsp+0D0h+var_90], rax
0x1800105f2  lea     rax, [rbp+57h+var_48]
0x1800105f6  mov     [rsp+0D0h+var_98], rax
0x1800105fb  lea     rax, [rbp+57h+var_40]
0x1800105ff  mov     [rsp+0D0h+var_A0], rax
0x180010604  lea     rax, [rbp+57h+var_38]
0x180010608  mov     [rsp+0D0h+var_A8], rax
0x18001060d  lea     rax, [rbp+57h+var_30]
0x180010611  mov     [rsp+0D0h+var_B0], rax
0x180010616  mov     [rbp+57h+var_30], rcx
0x18001061a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$01@@U4@U1@U1@U?$_tlgWrapperByVal@$03@@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$01@@633AEBU?$_tlgWrapperByVal@$03@@7@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001061f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010626  mov     rdx, [rbx+20h]
0x18001062a  lea     r14, [rbx+30h]
0x18001062e  cmp     rdi, rdx
0x180010631  jge     short loc_180010637
0x180010633  xor     esi, esi
0x180010635  jmp     short loc_180010643
0x180010637  add     rdx, [r14]
0x18001063a  cmp     rdi, rdx
0x18001063d  jge     loc_180010773
0x180010643  mov     eax, cs:dword_180026058
0x180010649  cmp     eax, 5
0x18001064c  jbe     loc_180010757
0x180010652  mov     edx, 4
0x180010657  lea     rcx, dword_180026058
0x18001065e  call    _tlgKeywordOn
0x180010663  test    al, al
0x180010665  jz      loc_180010757
0x18001066b  mov     rcx, rbx; this
0x18001066e  call    ?GetOnLockScreen@TimeEvent@Broker@@QEAA_NXZ; Broker::TimeEvent::GetOnLockScreen(void)
0x180010673  movzx   eax, al
0x180010676  mov     rcx, rbx
0x180010679  mov     [rbp+57h+arg_18], eax
0x18001067c  mov     rax, [rbx]
0x18001067f  mov     rax, [rax+30h]
0x180010683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010688  movzx   eax, al
0x18001068b  mov     [rbp+57h+var_60], eax
0x18001068e  mov     rax, r13
0x180010691  imul    qword ptr [r14]
0x180010694  mov     word ptr [rbp+57h+arg_10], si
0x180010698  mov     rax, r13
0x18001069b  add     rdx, [r14]
0x18001069e  sar     rdx, 17h
0x1800106a2  mov     rcx, rdx
0x1800106a5  shr     rcx, 3Fh
0x1800106a9  add     rdx, rcx
0x1800106ac  mov     rcx, [rbx+0F8h]
0x1800106b3  mov     [rbp+57h+var_30], rdx
0x1800106b7  imul    qword ptr [rbx+40h]
0x1800106bb  mov     [rbp+57h+var_50], rcx
0x1800106bf  add     rdx, [rbx+40h]
0x1800106c3  sar     rdx, 17h
0x1800106c7  mov     rax, rdx
0x1800106ca  shr     rax, 3Fh
0x1800106ce  add     rdx, rax
0x1800106d1  movzx   eax, word ptr [rbx+48h]
0x1800106d5  mov     [rbp+57h+arg_0], ax
0x1800106d9  lea     rax, [rbx+5Eh]
0x1800106dd  mov     [rbp+57h+var_40], rax
0x1800106e1  mov     [rbp+57h+var_38], rdx
0x1800106e5  lea     rdx, dword_180020C24
0x1800106ec  mov     rax, [rcx+18h]
0x1800106f0  mov     [rbp+57h+var_48], rax
0x1800106f4  lea     rax, [rbp+57h+arg_18]
0x1800106f8  mov     [rsp+0D0h+var_68], rax
0x1800106fd  lea     rax, [rbp+57h+var_60]
0x180010701  mov     [rsp+0D0h+var_70], rax
0x180010706  lea     rax, [rbp+57h+var_30]
0x18001070a  mov     [rsp+0D0h+var_78], rax
0x18001070f  lea     rax, [rbp+57h+var_38]
0x180010713  mov     [rsp+0D0h+var_80], rax
0x180010718  lea     rax, [rbp+57h+arg_0]
0x18001071c  mov     [rsp+0D0h+var_88], rax
0x180010721  lea     rax, [rbp+57h+arg_10]
0x180010725  mov     [rsp+0D0h+var_90], rax
0x18001072a  lea     rax, [rbp+57h+var_40]
0x18001072e  mov     [rsp+0D0h+var_98], rax
0x180010733  lea     rax, [rbp+57h+var_48]
0x180010737  mov     [rsp+0D0h+var_A0], rax
0x18001073c  lea     rax, [rbp+57h+var_50]
0x180010740  mov     [rsp+0D0h+var_A8], rax
0x180010745  lea     rax, [rbp+57h+var_58]
0x180010749  mov     [rsp+0D0h+var_B0], rax
0x18001074e  mov     [rbp+57h+var_58], rcx
0x180010752  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$01@@U4@U1@U1@U?$_tlgWrapperByVal@$03@@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$01@@633AEBU?$_tlgWrapperByVal@$03@@7@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010757  mov     rax, [rbx]
0x18001075a  mov     rdx, rdi
0x18001075d  mov     rcx, rbx
0x180010760  mov     rax, [rax+40h]
0x180010764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010769  mov     edx, 2
0x18001076e  jmp     loc_1800108E3
0x180010773  mov     esi, 2
0x180010778  test    byte ptr [rcx+1Ch], 40h
0x18001077c  jz      short loc_180010797
0x18001077e  cmp     byte ptr [rcx+19h], 3
0x180010782  jb      short loc_180010797
0x180010784  mov     r9, [rbx+0F8h]
0x18001078b  lea     edx, [rsi+0Eh]
0x18001078e  mov     rcx, [rcx+10h]
0x180010792  call    WPP_SF__guid_
0x180010797  mov     eax, cs:dword_180026058
0x18001079d  cmp     eax, 5
0x1800107a0  jbe     loc_1800108A3
0x1800107a6  mov     rdx, 400000000004h
0x1800107b0  lea     rcx, dword_180026058
0x1800107b7  call    _tlgKeywordOn
0x1800107bc  test    al, al
0x1800107be  jz      loc_1800108A3
0x1800107c4  mov     rcx, rbx; this
0x1800107c7  call    ?GetOnLockScreen@TimeEvent@Broker@@QEAA_NXZ; Broker::TimeEvent::GetOnLockScreen(void)
0x1800107cc  movzx   eax, al
0x1800107cf  mov     rcx, rbx
0x1800107d2  mov     [rbp+57h+arg_10], eax
0x1800107d5  mov     rax, [rbx]
0x1800107d8  mov     rax, [rax+30h]
0x1800107dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107e1  mov     rcx, [rbx+0F8h]
0x1800107e8  movzx   eax, al
0x1800107eb  mov     [rbp+57h+arg_18], eax
0x1800107ee  mov     rax, r13
0x1800107f1  imul    qword ptr [r14]
0x1800107f4  mov     [rbp+57h+var_50], rcx
0x1800107f8  add     rdx, [r14]
0x1800107fb  sar     rdx, 17h
0x1800107ff  mov     rax, rdx
0x180010802  shr     rax, 3Fh
0x180010806  add     rdx, rax
0x180010809  mov     rax, r13
0x18001080c  mov     [rbp+57h+var_30], rdx
0x180010810  imul    qword ptr [rbx+40h]
0x180010814  add     rdx, [rbx+40h]
0x180010818  sar     rdx, 17h
0x18001081c  mov     rax, rdx
0x18001081f  shr     rax, 3Fh
0x180010823  add     rdx, rax
0x180010826  movzx   eax, word ptr [rbx+48h]
0x18001082a  mov     [rbp+57h+arg_0], ax
0x18001082e  lea     rax, [rbx+5Eh]
0x180010832  mov     [rbp+57h+var_40], rax
0x180010836  mov     [rbp+57h+var_38], rdx
0x18001083a  lea     rdx, byte_180020A7F
0x180010841  mov     rax, [rcx+18h]
0x180010845  mov     [rbp+57h+var_48], rax
0x180010849  lea     rax, [rbp+57h+arg_10]
0x18001084d  mov     [rsp+0D0h+var_70], rax
0x180010852  lea     rax, [rbp+57h+arg_18]
0x180010856  mov     [rsp+0D0h+var_78], rax
0x18001085b  lea     rax, [rbp+57h+var_30]
0x18001085f  mov     [rsp+0D0h+var_80], rax
0x180010864  lea     rax, [rbp+57h+var_38]
0x180010868  mov     [rsp+0D0h+var_88], rax
0x18001086d  lea     rax, [rbp+57h+arg_0]
0x180010871  mov     [rsp+0D0h+var_90], rax
0x180010876  lea     rax, [rbp+57h+var_40]
0x18001087a  mov     [rsp+0D0h+var_98], rax
0x18001087f  lea     rax, [rbp+57h+var_48]
0x180010883  mov     [rsp+0D0h+var_A0], rax
0x180010888  lea     rax, [rbp+57h+var_50]
0x18001088c  mov     [rsp+0D0h+var_A8], rax
0x180010891  lea     rax, [rbp+57h+var_58]
0x180010895  mov     [rsp+0D0h+var_B0], rax
0x18001089a  mov     [rbp+57h+var_58], rcx
0x18001089e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$01@@U1@U1@U?$_tlgWrapperByVal@$03@@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$01@@33AEBU?$_tlgWrapperByVal@$03@@7@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800108a3  mov     edx, esi
0x1800108a5  mov     [rbx+28h], rdi
0x1800108a9  mov     rcx, rbx
0x1800108ac  call    ?SetState@TimeEvent@Broker@@IEAAXW4States@12@@Z; Broker::TimeEvent::SetState(Broker::TimeEvent::States)
0x1800108b1  mov     rax, [rbx]
0x1800108b4  mov     rdx, rdi
0x1800108b7  mov     rcx, rbx
0x1800108ba  mov     rax, [rax+48h]
0x1800108be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108c3  jmp     short loc_1800108EB
0x1800108c5  or      esi, 0FFFFFFFFh
0x1800108c8  cmp     dword ptr [rbx+58h], 2
0x1800108cc  jnz     short loc_1800108EB
0x1800108ce  mov     rcx, [rbx]
0x1800108d1  mov     rdx, rdi
0x1800108d4  mov     rax, [rcx+40h]
0x1800108d8  mov     rcx, rbx
0x1800108db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108e0  lea     edx, [rsi+6]
0x1800108e3  mov     rcx, rbx
0x1800108e6  call    ?SetState@TimeEvent@Broker@@IEAAXW4States@12@@Z; Broker::TimeEvent::SetState(Broker::TimeEvent::States)
0x1800108eb  mov     rbx, [rsp+0D0h+arg_8]
0x1800108f3  mov     eax, esi
0x1800108f5  add     rsp, 0B0h
0x1800108fc  pop     r14
0x1800108fe  pop     r13
0x180010900  pop     rdi
0x180010901  pop     rsi
0x180010902  pop     rbp
0x180010903  retn
```
