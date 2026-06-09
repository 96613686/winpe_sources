# wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x180007140`
- end: `0x1800074af`
- name: `?NotifyFailure@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `879`
- prototype: `char __fastcall(_QWORD *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18000134c`
- `0x1800015f0`
- `0x180006fcc`
- `0x180007088`
- `0x180007140`
- `0x180007cc0`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007495`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007495`

## pseudocode

```c
char __fastcall wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r9
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // r8
  _DWORD *v10; // rax
  int v11; // edx
  int v13; // [rsp+B0h] [rbp-80h] BYREF
  int v14; // [rsp+B4h] [rbp-7Ch] BYREF
  const unsigned __int16 *v15; // [rsp+B8h] [rbp-78h] BYREF
  const unsigned __int16 *v16; // [rsp+C0h] [rbp-70h] BYREF
  const unsigned __int16 *v17; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v18; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v19; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v20; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v21; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v22; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v24; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v25; // [rsp+108h] [rbp-28h] BYREF
  __int64 v26[4]; // [rsp+110h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+140h] [rbp+10h] BYREF
  int v28; // [rsp+148h] [rbp+18h] BYREF
  int v29; // [rsp+150h] [rbp+20h] BYREF
  int v30; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v7 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
      if ( *(_DWORD *)v7 > 2u
        && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
      {
        v23 = *((_QWORD *)a2 + 6);
        LODWORD(SRWLock) = a2[17];
        v28 = a2[4];
        v22 = (const unsigned __int16 *)*((_QWORD *)a2 + 15);
        v9 = a1[34];
        v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        v29 = a2[26];
        v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 12);
        v19 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v30 = a2[20];
        v18 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v14 = a2[8];
        v17 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
        v13 = *a2;
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        LODWORD(v15) = a2[16];
        v25 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        LODWORD(v16) = a2[2];
        v26[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v7,
          (__int64)byte_180042A09,
          v9 + 8,
          v8,
          (__int64)v26,
          (__int64)&v16,
          &v25,
          (__int64)&v15,
          &v24,
          (__int64)&v13,
          &v17,
          (__int64)&v14,
          &v18,
          (__int64)&v30,
          &v19,
          &v20,
          (__int64)&v29,
          &v21,
          &v22,
          (__int64)&v28,
          (__int64)&SRWLock,
          (const unsigned __int16 **)&v23);
      }
    }
    else
    {
      v4 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
      if ( *(_DWORD *)v4 > 2u
        && (*(_QWORD *)(v4 + 16) & 0x600000000000LL) != 0
        && (*(_QWORD *)(v4 + 24) & 0x600000000000LL) == *(_QWORD *)(v4 + 24) )
      {
        v6 = a1[34];
        v16 = (const unsigned __int16 *)*((_QWORD *)a2 + 15);
        v15 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        LODWORD(SRWLock) = a2[26];
        v17 = (const unsigned __int16 *)*((_QWORD *)a2 + 12);
        v18 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v28 = a2[20];
        v19 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v29 = a2[8];
        v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
        v30 = *a2;
        v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        v13 = a2[16];
        v22 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        v14 = a2[2];
        v23 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v4,
          (__int64)byte_180042EBD,
          v6 + 8,
          v5,
          (__int64)&v23,
          (__int64)&v14,
          &v22,
          (__int64)&v13,
          &v21,
          (__int64)&v30,
          &v20,
          (__int64)&v29,
          &v19,
          (__int64)&v28,
          &v18,
          &v17,
          (__int64)&SRWLock,
          &v15,
          &v16);
      }
    }
  }
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v10 = (_DWORD *)a1[34];
  v11 = a2[2];
  if ( v11 != v10[22] && (v11 != v10[18] || (int)v10[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v10 + 20), (const struct wil::FailureInfo *)a2);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 1;
}

```

## disassembly

```asm
0x180007140  push    rbp
0x180007142  push    rbx
0x180007143  push    rdi
0x180007144  lea     rbp, [rsp+10h]
0x180007149  sub     rsp, 120h
0x180007150  test    byte ptr [rdx+4], 2
0x180007154  mov     rbx, rdx
0x180007157  mov     rdi, rcx
0x18000715a  jnz     loc_18000745A
0x180007160  mov     rax, [rcx]
0x180007163  mov     edx, [rdx+10h]
0x180007166  mov     rax, [rax+10h]
0x18000716a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000716f  test    al, al
0x180007171  jnz     loc_1800072CF
0x180007177  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18000717c  mov     rcx, [rax+8]
0x180007180  mov     eax, [rcx]
0x180007182  cmp     eax, 2
0x180007185  jbe     loc_18000745A
0x18000718b  mov     rdx, [rcx+18h]
0x18000718f  mov     r8, 600000000000h
0x180007199  mov     rax, [rcx+10h]
0x18000719d  test    r8, rax
0x1800071a0  jz      loc_18000745A
0x1800071a6  mov     rax, rdx
0x1800071a9  and     rax, r8
0x1800071ac  cmp     rax, rdx
0x1800071af  jnz     loc_18000745A
0x1800071b5  mov     rax, [rbx+78h]
0x1800071b9  lea     rdx, byte_180042EBD
0x1800071c0  mov     r8, [rdi+110h]
0x1800071c7  mov     [rbp+var_70], rax
0x1800071cb  add     r8, 8
0x1800071cf  mov     rax, [rbx+70h]
0x1800071d3  mov     [rbp+var_78], rax
0x1800071d7  mov     eax, [rbx+68h]
0x1800071da  mov     dword ptr [rbp+SRWLock], eax
0x1800071dd  mov     rax, [rbx+60h]
0x1800071e1  mov     [rbp+var_68], rax
0x1800071e5  mov     rax, [rbx+58h]
0x1800071e9  mov     [rbp+var_60], rax
0x1800071ed  mov     eax, [rbx+50h]
0x1800071f0  mov     [rbp+arg_8], eax
0x1800071f3  mov     rax, [rbx+48h]
0x1800071f7  mov     [rbp+var_58], rax
0x1800071fb  mov     eax, [rbx+20h]
0x1800071fe  mov     [rbp+arg_10], eax
0x180007201  mov     rax, [rbx+18h]
0x180007205  mov     [rbp+var_50], rax
0x180007209  mov     eax, [rbx]
0x18000720b  mov     [rbp+arg_18], eax
0x18000720e  mov     rax, [rbx+80h]
0x180007215  mov     [rbp+var_48], rax
0x180007219  mov     eax, [rbx+40h]
0x18000721c  mov     [rbp+var_80], eax
0x18000721f  mov     rax, [rbx+38h]
0x180007223  mov     [rbp+var_40], rax
0x180007227  mov     eax, [rbx+8]
0x18000722a  mov     [rbp+var_7C], eax
0x18000722d  lea     rax, [rbp+var_70]
0x180007231  mov     [rsp+130h+var_A0], rax
0x180007239  lea     rax, [rbp+var_78]
0x18000723d  mov     [rsp+130h+var_A8], rax
0x180007245  lea     rax, [rbp+SRWLock]
0x180007249  mov     [rsp+130h+var_B0], rax
0x180007251  lea     rax, [rbp+var_68]
0x180007255  mov     [rsp+130h+var_B8], rax
0x18000725a  lea     rax, [rbp+var_60]
0x18000725e  mov     [rsp+130h+var_C0], rax
0x180007263  lea     rax, [rbp+arg_8]
0x180007267  mov     [rsp+130h+var_C8], rax
0x18000726c  lea     rax, [rbp+var_58]
0x180007270  mov     [rsp+130h+var_D0], rax
0x180007275  lea     rax, [rbp+arg_10]
0x180007279  mov     [rsp+130h+var_D8], rax
0x18000727e  lea     rax, [rbp+var_50]
0x180007282  mov     [rsp+130h+var_E0], rax
0x180007287  lea     rax, [rbp+arg_18]
0x18000728b  mov     [rsp+130h+var_E8], rax
0x180007290  lea     rax, [rbp+var_48]
0x180007294  mov     [rsp+130h+var_F0], rax
0x180007299  lea     rax, [rbp+var_80]
0x18000729d  mov     [rsp+130h+var_F8], rax
0x1800072a2  lea     rax, [rbp+var_40]
0x1800072a6  mov     [rsp+130h+var_100], rax
0x1800072ab  lea     rax, [rbp+var_7C]
0x1800072af  mov     [rsp+130h+var_108], rax
0x1800072b4  lea     rax, [rbp+var_38]
0x1800072b8  mov     [rsp+130h+var_110], rax
0x1800072bd  mov     [rbp+var_38], 1000000h
0x1800072c5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800072ca  jmp     loc_18000745A
0x1800072cf  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x1800072d4  mov     rcx, [rax+8]
0x1800072d8  mov     eax, [rcx]
0x1800072da  cmp     eax, 2
0x1800072dd  jbe     loc_18000745A
0x1800072e3  mov     rdx, [rcx+18h]
0x1800072e7  mov     r8, 400000000000h
0x1800072f1  mov     rax, [rcx+10h]
0x1800072f5  test    r8, rax
0x1800072f8  jz      loc_18000745A
0x1800072fe  mov     rax, rdx
0x180007301  and     rax, r8
0x180007304  cmp     rax, rdx
0x180007307  jnz     loc_18000745A
0x18000730d  mov     rax, [rbx+30h]
0x180007311  lea     rdx, byte_180042A09
0x180007318  mov     [rbp+var_38], rax
0x18000731c  mov     eax, [rbx+44h]
0x18000731f  mov     dword ptr [rbp+SRWLock], eax
0x180007322  mov     eax, [rbx+10h]
0x180007325  mov     [rbp+arg_8], eax
0x180007328  mov     rax, [rbx+78h]
0x18000732c  mov     [rbp+var_40], rax
0x180007330  mov     rax, [rbx+70h]
0x180007334  mov     r8, [rdi+110h]
0x18000733b  mov     [rbp+var_48], rax
0x18000733f  add     r8, 8
0x180007343  mov     eax, [rbx+68h]
0x180007346  mov     [rbp+arg_10], eax
0x180007349  mov     rax, [rbx+60h]
0x18000734d  mov     [rbp+var_50], rax
0x180007351  mov     rax, [rbx+58h]
0x180007355  mov     [rbp+var_58], rax
0x180007359  mov     eax, [rbx+50h]
0x18000735c  mov     [rbp+arg_18], eax
0x18000735f  mov     rax, [rbx+48h]
0x180007363  mov     [rbp+var_60], rax
0x180007367  mov     eax, [rbx+20h]
0x18000736a  mov     [rbp+var_7C], eax
0x18000736d  mov     rax, [rbx+18h]
0x180007371  mov     [rbp+var_68], rax
0x180007375  mov     eax, [rbx]
0x180007377  mov     [rbp+var_80], eax
0x18000737a  mov     rax, [rbx+80h]
0x180007381  mov     [rbp+var_30], rax
0x180007385  mov     eax, [rbx+40h]
0x180007388  mov     dword ptr [rbp+var_78], eax
0x18000738b  mov     rax, [rbx+38h]
0x18000738f  mov     [rbp+var_28], rax
0x180007393  mov     eax, [rbx+8]
0x180007396  mov     dword ptr [rbp+var_70], eax
0x180007399  lea     rax, [rbp+var_38]
0x18000739d  mov     [rsp+130h+var_88], rax
0x1800073a5  lea     rax, [rbp+SRWLock]
0x1800073a9  mov     [rsp+130h+var_90], rax
0x1800073b1  lea     rax, [rbp+arg_8]
0x1800073b5  mov     [rsp+130h+var_98], rax
0x1800073bd  lea     rax, [rbp+var_40]
0x1800073c1  mov     [rsp+130h+var_A0], rax
0x1800073c9  lea     rax, [rbp+var_48]
0x1800073cd  mov     [rsp+130h+var_A8], rax
0x1800073d5  lea     rax, [rbp+arg_10]
0x1800073d9  mov     [rsp+130h+var_B0], rax
0x1800073e1  lea     rax, [rbp+var_50]
0x1800073e5  mov     [rsp+130h+var_B8], rax
0x1800073ea  lea     rax, [rbp+var_58]
0x1800073ee  mov     [rsp+130h+var_C0], rax
0x1800073f3  lea     rax, [rbp+arg_18]
0x1800073f7  mov     [rsp+130h+var_C8], rax
0x1800073fc  lea     rax, [rbp+var_60]
0x180007400  mov     [rsp+130h+var_D0], rax
0x180007405  lea     rax, [rbp+var_7C]
0x180007409  mov     [rsp+130h+var_D8], rax
0x18000740e  lea     rax, [rbp+var_68]
0x180007412  mov     [rsp+130h+var_E0], rax
0x180007417  lea     rax, [rbp+var_80]
0x18000741b  mov     [rsp+130h+var_E8], rax
0x180007420  lea     rax, [rbp+var_30]
0x180007424  mov     [rsp+130h+var_F0], rax
0x180007429  lea     rax, [rbp+var_78]
0x18000742d  mov     [rsp+130h+var_F8], rax
0x180007432  lea     rax, [rbp+var_28]
0x180007436  mov     [rsp+130h+var_100], rax
0x18000743b  lea     rax, [rbp+var_70]
0x18000743f  mov     [rsp+130h+var_108], rax
0x180007444  lea     rax, [rbp+var_20]
0x180007448  mov     [rsp+130h+var_110], rax
0x18000744d  mov     [rbp+var_20], 1000000h
0x180007455  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000745a  lea     rdx, [rbp+SRWLock]
0x18000745e  mov     rcx, rdi
0x180007461  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180007466  mov     rax, [rdi+110h]
0x18000746d  mov     edx, [rbx+8]
0x180007470  lea     rcx, [rax+50h]; this
0x180007474  cmp     edx, [rcx+8]
0x180007477  jz      short loc_18000748C
0x180007479  cmp     edx, [rax+48h]
0x18000747c  jnz     short loc_180007484
0x18000747e  cmp     dword ptr [rax+48h], 0
0x180007482  jl      short loc_18000748C
0x180007484  mov     rdx, rbx; struct wil::FailureInfo *
0x180007487  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18000748c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180007490  test    rcx, rcx
0x180007493  jz      short loc_1800074A1
0x180007495  call    cs:__imp_ReleaseSRWLockExclusive
0x18000749c  nop     dword ptr [rax+rax+00h]
0x1800074a1  mov     al, 1
0x1800074a3  add     rsp, 120h
0x1800074aa  pop     rdi
0x1800074ab  pop     rbx
0x1800074ac  pop     rbp
0x1800074ad  retn
```
