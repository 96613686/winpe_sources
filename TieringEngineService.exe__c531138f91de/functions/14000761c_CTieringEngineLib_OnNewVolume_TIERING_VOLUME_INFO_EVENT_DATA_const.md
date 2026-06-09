# CTieringEngineLib::OnNewVolume(_TIERING_VOLUME_INFO_EVENT_DATA const *)

- ea: `0x14000761c`
- end: `0x14000794e`
- name: `?OnNewVolume@CTieringEngineLib@@AEAAXPEBU_TIERING_VOLUME_INFO_EVENT_DATA@@@Z`
- size: `818`
- prototype: `void __fastcall(CTieringEngineLib *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140007954`

## callees

- `0x14000108c`
- `0x140001a00`
- `0x140001a18`
- `0x140004a40`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x14000761c`
- `0x140008aa0`
- `0x140008b50`
- `0x140009e20`
- `0x140009f5c`
- `0x14000b960`
- `0x14000bf3c`
- `0x1400104f4`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1400076bf`
- `ntdll!RtlCompareMemory` at `0x1400076bf`

## pseudocode

```c
void __fastcall CTieringEngineLib::OnNewVolume(CTieringEngineLib *this, struct _GUID *a2)
{
  __int64 v4; // r8
  CTieredVolume *v5; // rax
  CTieredVolume *v6; // rbx
  int v7; // eax
  CTieringEngineLib **v8; // rcx
  __int64 v9; // r8
  int v10; // ecx
  CTieredVolume *v11; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C0h] BYREF
  int v13; // [rsp+40h] [rbp-B8h]
  CTieredVolume *v14; // [rsp+48h] [rbp-B0h] BYREF
  _QWORD v15[6]; // [rsp+50h] [rbp-A8h] BYREF
  _BYTE v16[32]; // [rsp+80h] [rbp-78h] BYREF
  struct _GUID *v17; // [rsp+A0h] [rbp-58h]
  __int64 v18; // [rsp+A8h] [rbp-50h]
  _DWORD *v19; // [rsp+B0h] [rbp-48h]
  __int64 v20; // [rsp+B8h] [rbp-40h]
  __int64 v21; // [rsp+C0h] [rbp-38h]
  _DWORD v22[2]; // [rsp+C8h] [rbp-30h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieringEngineLib::OnNewVolume";
  CHResultImp::CHResultImp((CHResultImp *)v12);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, v4, this, a2[1].Data1);
  }
  if ( *((_BYTE *)this + 192) )
    goto LABEL_32;
  if ( RtlCompareMemory(a2, &NullGuid, 0x10u) == 16 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids);
    }
LABEL_32:
    CHResultImp::~CHResultImp((CHResultImp *)v12);
    return;
  }
  v5 = (CTieredVolume *)operator new(0x6D0u);
  v11 = v5;
  if ( v5 )
    v6 = CTieredVolume::CTieredVolume(v5, this);
  else
    v6 = 0;
  v15[2] = v6;
  v7 = CTieredVolume::Initialize(v6, this, a2, a2[1].Data1, *((void **)this + 26));
  v13 = v7;
  if ( v7 >= 0 )
  {
    v8 = (CTieringEngineLib **)*((_QWORD *)this + 29);
    if ( *v8 != (CTieringEngineLib *)((char *)this + 224) )
      __fastfail(3u);
    *(_QWORD *)v6 = (char *)this + 224;
    *((_QWORD *)v6 + 1) = v8;
    *v8 = v6;
    *((_QWORD *)this + 29) = v6;
    v14 = v6;
    v15[3] = &v14;
    v11 = v6;
    v15[0] = ATL::CAtlMap<_GUID,CTieredVolume *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CTieredVolume *>>::SetAt(
               (char *)this + 240,
               a2,
               &v11);
    v15[1] = this;
    v15[4] = v15;
    v11 = v6;
    ATL::CAtlMap<unsigned long,CTieredVolume *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CTieredVolume *>>::SetAt(
      (char *)this + 312,
      a2[1].Data1,
      &v11);
    if ( (unsigned int)dword_14004C098 > 5
      && (qword_14004C0A8 & 0x200000000000LL) != 0
      && (qword_14004C0B0 & 0x200000000000LL) == qword_14004C0B0 )
    {
      v19 = v22;
      v20 = 2;
      v10 = *((unsigned __int16 *)v6 + 348);
      v21 = *((_QWORD *)v6 + 88);
      v22[0] = v10;
      v22[1] = 0;
      v17 = a2;
      v18 = 16;
      tlgWriteTransfer_EventWriteTransfer(&dword_14004C098, byte_140045B49, 0, 0, 5, v16, (_DWORD)v11);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF__guid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, v9, a2, a2[1].Data1);
    }
    goto LABEL_32;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids,
      (unsigned int)v7);
  }
  if ( v6 )
  {
    CTieredVolume::~CTieredVolume((JET_API_PTR)v6);
    operator delete(v6);
  }
  CHResultImp::~CHResultImp((CHResultImp *)v12);
}

```

## disassembly

```asm
0x14000761c  mov     [rsp+arg_10], rbx
0x140007621  push    rsi
0x140007622  push    rdi
0x140007623  push    r15
0x140007625  sub     rsp, 0E0h
0x14000762c  mov     rax, cs:__security_cookie
0x140007633  xor     rax, rsp
0x140007636  mov     [rsp+0F8h+var_28], rax
0x14000763e  mov     rsi, rdx
0x140007641  mov     rdi, rcx
0x140007644  mov     ecx, 8
0x140007649  mov     rax, gs:58h
0x140007652  mov     rdx, [rax]
0x140007655  lea     rax, aCtieringengine_12; "CTieringEngineLib::OnNewVolume"
0x14000765c  mov     [rcx+rdx], rax
0x140007660  lea     rcx, [rsp+0F8h+var_C0]; this
0x140007665  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14000766a  nop
0x14000766b  lea     r15, WPP_GLOBAL_Control
0x140007672  mov     rcx, cs:WPP_GLOBAL_Control
0x140007679  cmp     rcx, r15
0x14000767c  jz      short loc_1400076A2
0x14000767e  test    byte ptr [rcx+1Ch], 1
0x140007682  jz      short loc_1400076A2
0x140007684  cmp     byte ptr [rcx+19h], 4
0x140007688  jb      short loc_1400076A2
0x14000768a  mov     edx, 49h ; 'I'
0x14000768f  mov     eax, [rsi+10h]
0x140007692  mov     dword ptr [rsp+0F8h+var_D8], eax
0x140007696  mov     r9, rdi
0x140007699  mov     rcx, [rcx+10h]
0x14000769d  call    WPP_SF_qD
0x1400076a2  cmp     byte ptr [rdi+0C0h], 0
0x1400076a9  jnz     loc_140007920
0x1400076af  mov     r8d, 10h; Length
0x1400076b5  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x1400076bc  mov     rcx, rsi; Source1
0x1400076bf  call    cs:__imp_RtlCompareMemory
0x1400076c5  cmp     rax, 10h
0x1400076c9  jnz     short loc_140007707
0x1400076cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400076d2  cmp     rcx, r15
0x1400076d5  jz      loc_140007920
0x1400076db  test    byte ptr [rcx+1Ch], 1
0x1400076df  jz      loc_140007920
0x1400076e5  cmp     byte ptr [rcx+19h], 2
0x1400076e9  jb      loc_140007920
0x1400076ef  lea     edx, [rax+3Ah]
0x1400076f2  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x1400076f9  mov     rcx, [rcx+10h]
0x1400076fd  call    WPP_SF_
0x140007702  jmp     loc_140007920
0x140007707  mov     ecx, 6D0h; Size
0x14000770c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007711  mov     [rsp+0F8h+var_C8], rax
0x140007716  test    rax, rax
0x140007719  jz      short loc_14000772B
0x14000771b  mov     rdx, rdi; struct CTieringEngineLib *
0x14000771e  mov     rcx, rax; this
0x140007721  call    ??0CTieredVolume@@QEAA@PEAVCTieringEngineLib@@@Z; CTieredVolume::CTieredVolume(CTieringEngineLib *)
0x140007726  mov     rbx, rax
0x140007729  jmp     short loc_14000772D
0x14000772b  xor     ebx, ebx
0x14000772d  mov     [rsp+0F8h+var_98], rbx
0x140007732  mov     rax, [rdi+0D0h]
0x140007739  mov     [rsp+0F8h+var_D8], rax; void *
0x14000773e  mov     r9d, [rsi+10h]; unsigned int
0x140007742  mov     r8, rsi; struct _GUID *
0x140007745  mov     rdx, rdi; struct CTieringEngineLib *
0x140007748  mov     rcx, rbx; pv
0x14000774b  call    ?Initialize@CTieredVolume@@QEAAJPEAVCTieringEngineLib@@PEBU_GUID@@KPEAX@Z; CTieredVolume::Initialize(CTieringEngineLib *,_GUID const *,ulong,void *)
0x140007750  mov     [rsp+0F8h+var_B8], eax
0x140007754  test    eax, eax
0x140007756  jns     short loc_1400077AE
0x140007758  mov     rcx, cs:WPP_GLOBAL_Control
0x14000775f  cmp     rcx, r15
0x140007762  jz      short loc_140007789
0x140007764  test    byte ptr [rcx+1Ch], 1
0x140007768  jz      short loc_140007789
0x14000776a  cmp     byte ptr [rcx+19h], 2
0x14000776e  jb      short loc_140007789
0x140007770  mov     edx, 4Bh ; 'K'
0x140007775  mov     r9d, eax
0x140007778  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x14000777f  mov     rcx, [rcx+10h]
0x140007783  call    WPP_SF_d
0x140007788  nop
0x140007789  test    rbx, rbx
0x14000778c  jz      short loc_14000779F
0x14000778e  mov     rcx, rbx; ulContext
0x140007791  call    ??1CTieredVolume@@QEAA@XZ; CTieredVolume::~CTieredVolume(void)
0x140007796  mov     rcx, rbx; Block
0x140007799  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000779e  nop
0x14000779f  lea     rcx, [rsp+0F8h+var_C0]; this
0x1400077a4  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1400077a9  jmp     loc_14000792A
0x1400077ae  lea     rax, [rdi+0E0h]
0x1400077b5  mov     rcx, [rax+8]
0x1400077b9  cmp     [rcx], rax
0x1400077bc  jz      short loc_1400077C5
0x1400077be  mov     ecx, 3
0x1400077c3  int     29h; Win8: RtlFailFast(ecx)
0x1400077c5  mov     [rbx], rax
0x1400077c8  mov     [rbx+8], rcx
0x1400077cc  mov     [rcx], rbx
0x1400077cf  mov     [rax+8], rbx
0x1400077d3  mov     [rsp+0F8h+var_B0], rbx
0x1400077d8  lea     rax, [rsp+0F8h+var_B0]
0x1400077dd  mov     [rsp+0F8h+var_90], rax
0x1400077e2  mov     [rsp+0F8h+var_C8], rbx
0x1400077e7  lea     rcx, [rdi+0F0h]
0x1400077ee  lea     r8, [rsp+0F8h+var_C8]
0x1400077f3  mov     rdx, rsi
0x1400077f6  call    ?SetAt@?$CAtlMap@U_GUID@@PEAVCTieredVolume@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAVCTieredVolume@@@4@@ATL@@QEAAPEAU__POSITION@@AEBU_GUID@@AEBQEAVCTieredVolume@@@Z; ATL::CAtlMap<_GUID,CTieredVolume *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CTieredVolume *>>::SetAt(_GUID const &,CTieredVolume * const &)
0x1400077fb  mov     [rsp+0F8h+var_A8], rax
0x140007800  mov     [rsp+0F8h+var_A0], rdi
0x140007805  lea     rax, [rsp+0F8h+var_A8]
0x14000780a  mov     [rsp+0F8h+var_88], rax
0x14000780f  mov     [rsp+0F8h+var_C8], rbx
0x140007814  lea     rcx, [rdi+138h]
0x14000781b  lea     r8, [rsp+0F8h+var_C8]
0x140007820  mov     edx, [rsi+10h]
0x140007823  call    ?SetAt@?$CAtlMap@KPEAVCTieredVolume@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCTieredVolume@@@3@@ATL@@QEAAPEAU__POSITION@@KAEBQEAVCTieredVolume@@@Z; ATL::CAtlMap<ulong,CTieredVolume *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CTieredVolume *>>::SetAt(ulong,CTieredVolume * const &)
0x140007828  mov     eax, cs:dword_14004C098
0x14000782e  cmp     eax, 5
0x140007831  jbe     loc_1400078EE
0x140007837  mov     rcx, cs:qword_14004C0B0
0x14000783e  mov     rax, cs:qword_14004C0A8
0x140007845  mov     rdx, 200000000000h
0x14000784f  test    rdx, rax
0x140007852  jz      loc_1400078EE
0x140007858  mov     rax, rcx
0x14000785b  and     rax, rdx
0x14000785e  cmp     rax, rcx
0x140007861  jnz     loc_1400078EE
0x140007867  lea     rax, [rsp+0F8h+var_30]
0x14000786f  mov     [rsp+0F8h+var_48], rax
0x140007877  mov     [rsp+0F8h+var_40], 2
0x140007883  movzx   ecx, word ptr [rbx+2B8h]
0x14000788a  mov     rax, [rbx+2C0h]
0x140007891  mov     [rsp+0F8h+var_38], rax
0x140007899  mov     [rsp+0F8h+var_30], ecx
0x1400078a0  mov     [rsp+0F8h+var_2C], 0
0x1400078ab  mov     [rsp+0F8h+var_58], rsi
0x1400078b3  mov     [rsp+0F8h+var_50], 10h
0x1400078bf  lea     rax, [rsp+0F8h+var_78]
0x1400078c7  mov     [rsp+0F8h+var_D0], rax
0x1400078cc  mov     dword ptr [rsp+0F8h+var_D8], 5
0x1400078d4  xor     r9d, r9d
0x1400078d7  xor     r8d, r8d
0x1400078da  lea     rdx, byte_140045B49
0x1400078e1  lea     rcx, dword_14004C098
0x1400078e8  call    _tlgWriteTransfer_EventWriteTransfer
0x1400078ed  nop
0x1400078ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400078f5  cmp     rcx, r15
0x1400078f8  jz      short loc_140007920
0x1400078fa  test    byte ptr [rcx+1Ch], 1
0x1400078fe  jz      short loc_140007920
0x140007900  cmp     byte ptr [rcx+19h], 4
0x140007904  jb      short loc_140007920
0x140007906  mov     edx, 4Eh ; 'N'
0x14000790b  mov     eax, [rsi+10h]
0x14000790e  mov     dword ptr [rsp+0F8h+var_D8], eax
0x140007912  mov     r9, rsi
0x140007915  mov     rcx, [rcx+10h]
0x140007919  call    WPP_SF__guid_D
0x14000791e  jmp     short $+2
0x140007920  lea     rcx, [rsp+0F8h+var_C0]; this
0x140007925  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14000792a  mov     rcx, [rsp+0F8h+var_28]
0x140007932  xor     rcx, rsp; StackCookie
0x140007935  call    __security_check_cookie
0x14000793a  mov     rbx, [rsp+0F8h+arg_10]
0x140007942  add     rsp, 0E0h
0x140007949  pop     r15
0x14000794b  pop     rdi
0x14000794c  pop     rsi
0x14000794d  retn
```
