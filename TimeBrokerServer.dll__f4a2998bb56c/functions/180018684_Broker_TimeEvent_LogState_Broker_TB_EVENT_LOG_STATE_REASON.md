# Broker::TimeEvent::LogState(Broker::_TB_EVENT_LOG_STATE_REASON)

- ea: `0x180018684`
- end: `0x180018894`
- name: `?LogState@TimeEvent@Broker@@QEAAXW4_TB_EVENT_LOG_STATE_REASON@2@@Z`
- size: `528`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001579c`

## callees

- `0x1800012f8`
- `0x18000ee60`
- `0x180018684`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Broker::TimeEvent::LogState(__int64 *a1)
{
  __int64 result; // rax
  __int16 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  _WORD v11[2]; // [rsp+B0h] [rbp-80h] BYREF
  int v12; // [rsp+B4h] [rbp-7Ch] BYREF
  int v13; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v14; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v15; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v16; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v17; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v18; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v19; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v20; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v21; // [rsp+F8h] [rbp-38h] BYREF
  unsigned __int64 v22; // [rsp+100h] [rbp-30h] BYREF
  int *v23; // [rsp+108h] [rbp-28h] BYREF
  int *v24; // [rsp+110h] [rbp-20h] BYREF
  __int64 v25; // [rsp+118h] [rbp-18h] BYREF
  __int64 v26; // [rsp+120h] [rbp-10h] BYREF
  __int16 v27; // [rsp+150h] [rbp+20h] BYREF
  __int16 v28; // [rsp+158h] [rbp+28h] BYREF

  result = (unsigned int)dword_180026058;
  if ( (unsigned int)dword_180026058 > 5 )
  {
    result = tlgKeywordOn(&dword_180026058, 2);
    if ( (_BYTE)result )
    {
      v27 = v3;
      v14 = a1[10] / 10000000;
      v4 = a1[7] / 10000000;
      v12 = *((unsigned __int8 *)a1 + 92);
      v16 = a1[4];
      v17 = v16;
      v18 = a1[3];
      v19 = a1[29];
      v20 = a1[28];
      v5 = *a1;
      v15 = v4;
      v13 = (*(unsigned __int8 (__fastcall **)(__int64 *))(v5 + 48))(a1);
      v6 = a1[31];
      v21 = a1[6] / 10000000;
      v7 = (unsigned __int128)(a1[8] * (__int128)(__int64)0xD6BF94D5E57A42BDuLL) >> 64;
      v25 = v6;
      v8 = (a1[8] + v7) >> 23;
      v28 = *((_WORD *)a1 + 36);
      v11[0] = *((_WORD *)a1 + 44);
      v23 = (int *)((char *)a1 + 94);
      v22 = (v8 >> 63) + v8;
      v24 = *(int **)(v6 + 24);
      v26 = v6;
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
               v6,
               (__int64)byte_180020CC5,
               v9,
               v10,
               (__int64)&v26,
               &v25,
               &v24,
               &v23,
               (__int64)v11,
               (__int64)&v28,
               (__int64)&v22,
               (__int64)&v21,
               (__int64)&v13,
               (__int64)&v27,
               (__int64)&v20,
               (__int64)&v19,
               (__int64)&v18,
               (__int64)&v17,
               (__int64)&v16,
               (__int64)&v12,
               (__int64)&v15,
               (__int64)&v14);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018684  mov     [rsp-8+arg_0], rbx
0x180018689  mov     [rsp-8+arg_8], rdi
0x18001868e  push    rbp
0x18001868f  mov     rbp, rsp
0x180018692  sub     rsp, 130h
0x180018699  mov     eax, cs:dword_180026058
0x18001869f  mov     r8d, edx
0x1800186a2  mov     rbx, rcx
0x1800186a5  cmp     eax, 5
0x1800186a8  jbe     loc_18001887F
0x1800186ae  mov     edx, 2
0x1800186b3  lea     rcx, dword_180026058
0x1800186ba  call    _tlgKeywordOn
0x1800186bf  test    al, al
0x1800186c1  jz      loc_18001887F
0x1800186c7  mov     rdi, 0D6BF94D5E57A42BDh
0x1800186d1  mov     [rbp+arg_10], r8w
0x1800186d6  mov     rax, rdi
0x1800186d9  mov     rcx, rbx
0x1800186dc  imul    qword ptr [rbx+50h]
0x1800186e0  add     rdx, [rbx+50h]
0x1800186e4  sar     rdx, 17h
0x1800186e8  mov     rax, rdx
0x1800186eb  shr     rax, 3Fh
0x1800186ef  add     rdx, rax
0x1800186f2  mov     rax, rdi
0x1800186f5  mov     [rbp+var_70], rdx
0x1800186f9  imul    qword ptr [rbx+38h]
0x1800186fd  add     rdx, [rbx+38h]
0x180018701  sar     rdx, 17h
0x180018705  mov     rax, rdx
0x180018708  shr     rax, 3Fh
0x18001870c  add     rdx, rax
0x18001870f  movzx   eax, byte ptr [rbx+5Ch]
0x180018713  mov     [rbp+var_7C], eax
0x180018716  mov     rax, [rbx+20h]
0x18001871a  mov     [rbp+var_60], rax
0x18001871e  mov     [rbp+var_58], rax
0x180018722  mov     rax, [rbx+18h]
0x180018726  mov     [rbp+var_50], rax
0x18001872a  mov     rax, [rbx+0E8h]
0x180018731  mov     [rbp+var_48], rax
0x180018735  mov     rax, [rbx+0E0h]
0x18001873c  mov     [rbp+var_40], rax
0x180018740  mov     rax, [rbx]
0x180018743  mov     [rbp+var_68], rdx
0x180018747  mov     rax, [rax+30h]
0x18001874b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018750  movzx   eax, al
0x180018753  mov     [rbp+var_78], eax
0x180018756  mov     rax, rdi
0x180018759  imul    qword ptr [rbx+30h]
0x18001875d  mov     rax, rdi
0x180018760  add     rdx, [rbx+30h]
0x180018764  sar     rdx, 17h
0x180018768  mov     rcx, rdx
0x18001876b  shr     rcx, 3Fh
0x18001876f  add     rdx, rcx
0x180018772  mov     rcx, [rbx+0F8h]
0x180018779  mov     [rbp+var_38], rdx
0x18001877d  imul    qword ptr [rbx+40h]
0x180018781  mov     [rbp+var_18], rcx
0x180018785  add     rdx, [rbx+40h]
0x180018789  sar     rdx, 17h
0x18001878d  mov     rax, rdx
0x180018790  shr     rax, 3Fh
0x180018794  add     rdx, rax
0x180018797  movzx   eax, word ptr [rbx+48h]
0x18001879b  mov     [rbp+arg_18], ax
0x18001879f  movzx   eax, word ptr [rbx+58h]
0x1800187a3  mov     [rbp+var_80], ax
0x1800187a7  lea     rax, [rbx+5Eh]
0x1800187ab  mov     [rbp+var_28], rax
0x1800187af  mov     [rbp+var_30], rdx
0x1800187b3  mov     rax, [rcx+18h]
0x1800187b7  mov     [rbp+var_20], rax
0x1800187bb  lea     rax, [rbp+var_70]
0x1800187bf  mov     [rsp+130h+var_88], rax
0x1800187c7  lea     rax, [rbp+var_68]
0x1800187cb  mov     [rsp+130h+var_90], rax
0x1800187d3  lea     rax, [rbp+var_7C]
0x1800187d7  mov     [rsp+130h+var_98], rax
0x1800187df  lea     rax, [rbp+var_60]
0x1800187e3  mov     [rsp+130h+var_A0], rax
0x1800187eb  lea     rax, [rbp+var_58]
0x1800187ef  mov     [rsp+130h+var_A8], rax
0x1800187f7  lea     rax, [rbp+var_50]
0x1800187fb  mov     [rsp+130h+var_B0], rax
0x180018803  lea     rax, [rbp+var_48]
0x180018807  mov     [rsp+130h+var_B8], rax
0x18001880c  lea     rax, [rbp+var_40]
0x180018810  mov     [rsp+130h+var_C0], rax
0x180018815  lea     rax, [rbp+arg_10]
0x180018819  mov     [rsp+130h+var_C8], rax
0x18001881e  lea     rax, [rbp+var_78]
0x180018822  mov     [rbp+var_10], rcx
0x180018826  mov     [rsp+130h+var_D0], rax
0x18001882b  lea     rdx, byte_180020CC5
0x180018832  lea     rax, [rbp+var_38]
0x180018836  mov     [rsp+130h+var_D8], rax
0x18001883b  lea     rax, [rbp+var_30]
0x18001883f  mov     [rsp+130h+var_E0], rax
0x180018844  lea     rax, [rbp+arg_18]
0x180018848  mov     [rsp+130h+var_E8], rax
0x18001884d  lea     rax, [rbp+var_80]
0x180018851  mov     [rsp+130h+var_F0], rax
0x180018856  lea     rax, [rbp+var_28]
0x18001885a  mov     [rsp+130h+var_F8], rax
0x18001885f  lea     rax, [rbp+var_20]
0x180018863  mov     [rsp+130h+var_100], rax
0x180018868  lea     rax, [rbp+var_18]
0x18001886c  mov     [rsp+130h+var_108], rax
0x180018871  lea     rax, [rbp+var_10]
0x180018875  mov     [rsp+130h+var_110], rax
0x18001887a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$01@@U4@U1@U1@U?$_tlgWrapperByVal@$03@@U4@U1@U1@U1@U1@U1@U5@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$01@@633AEBU?$_tlgWrapperByVal@$03@@633333733@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18001887f  lea     r11, [rsp+130h+var_s0]
0x180018887  mov     rbx, [r11+10h]
0x18001888b  mov     rdi, [r11+18h]
0x18001888f  mov     rsp, r11
0x180018892  pop     rbp
0x180018893  retn
```
