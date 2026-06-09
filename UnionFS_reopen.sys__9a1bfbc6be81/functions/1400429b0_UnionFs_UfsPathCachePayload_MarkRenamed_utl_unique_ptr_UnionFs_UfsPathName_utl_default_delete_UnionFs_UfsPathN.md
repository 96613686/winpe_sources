# UnionFs::UfsPathCachePayload::MarkRenamed(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::StackEventTracer &)

- ea: `0x1400429b0`
- end: `0x140042dcd`
- name: `?MarkRenamed@UfsPathCachePayload@UnionFs@@QEAAJ$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `1053`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002c9f0`

## callees

- `0x140001b64`
- `0x140002500`
- `0x14000f7fc`
- `0x1400429b0`
- `0x140056ac4`
- `0x14005f124`
- `0x1400799a4`
- `0x140079c48`
- `0x14007af90`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140042c8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042c8a`
- `ntoskrnl!KeSetEvent` at `0x140042ce6`
- `ntoskrnl!KeSetEvent` at `0x140042d3f`
- `ntoskrnl!KeSetEvent` at `0x140042ce6`
- `ntoskrnl!KeSetEvent` at `0x140042d3f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042d55`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042d97`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042d55`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042d97`

## string_xrefs

- `0x140042a1c`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140042b69`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140042ca8`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x140042a23`: `UnionFs::UfsPathCachePayload::MarkRenamed`
- `0x140042ade`: `Marking Renamed tombstone`
- `0x140042d65`: `ORIGIN: Marking renamed from non-soft tombstone`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::MarkRenamed(__int64 a1, __int128 **a2, int a3)
{
  struct _UNICODE_STRING *v6; // rdx
  int v7; // r8d
  int v8; // r9d
  bool v9; // r14
  __int128 *v10; // rax
  int *v11; // rax
  unsigned __int16 v12; // r9
  int *v13; // rcx
  unsigned __int16 v14; // r8
  __int128 *v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  utl::_RefCountBase *v20; // rdi
  const char *v22; // [rsp+28h] [rbp-D8h]
  bool v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  PFAST_MUTEX FastMutex; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v27; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  const char *v29; // [rsp+80h] [rbp-80h] BYREF
  const char *v30; // [rsp+88h] [rbp-78h] BYREF
  const char *v31; // [rsp+90h] [rbp-70h] BYREF
  __int128 v32; // [rsp+98h] [rbp-68h]
  char v33; // [rsp+B0h] [rbp-50h] BYREF
  const char *v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  const char *v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  const char *v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]
  int *v40; // [rsp+100h] [rbp+0h]
  __int64 v41; // [rsp+108h] [rbp+8h]
  _DWORD *v42; // [rsp+110h] [rbp+10h]
  __int64 v43; // [rsp+118h] [rbp+18h]
  int *v44; // [rsp+120h] [rbp+20h]
  _DWORD v45[2]; // [rsp+128h] [rbp+28h] BYREF
  _DWORD *v46; // [rsp+130h] [rbp+30h]
  __int64 v47; // [rsp+138h] [rbp+38h]
  int *v48; // [rsp+140h] [rbp+40h]
  _DWORD v49[2]; // [rsp+148h] [rbp+48h] BYREF
  bool *v50; // [rsp+150h] [rbp+50h]
  __int64 v51; // [rsp+158h] [rbp+58h]

  FsFltWil::AcquireFastMutex(&FastMutex, *(_QWORD *)(a1 + 136));
  if ( *(_BYTE *)(a1 + 165) )
    v9 = *(_BYTE *)(a1 + 164) == 0;
  else
    v9 = 1;
  v10 = *(__int128 **)(a1 + 200);
  v27 = **a2;
  v32 = *v10;
  if ( (unsigned int)dword_14009E178 > 5 && (qword_14009E188 & 0x40) != 0 && (qword_14009E190 & 0x40) == qword_14009E190 )
  {
    v11 = (int *)*((_QWORD *)&v32 + 1);
    v23 = v9;
    if ( *((_QWORD *)&v32 + 1) )
    {
      v12 = v32;
    }
    else
    {
      v12 = 0;
      v11 = &dword_14007EEC4;
    }
    v13 = (int *)*((_QWORD *)&v27 + 1);
    if ( *((_QWORD *)&v27 + 1) )
    {
      v14 = v27;
    }
    else
    {
      v14 = 0;
      v13 = &dword_14007EEC4;
    }
    v48 = v11;
    v49[0] = v12;
    v42 = v45;
    v45[0] = v14;
    v40 = &v24;
    v50 = &v23;
    v34 = "Marking Renamed tombstone";
    v46 = v49;
    v44 = v13;
    v22 = &v33;
    v24 = 1042;
    v51 = 1;
    v47 = 2;
    v49[1] = 0;
    v43 = 2;
    v45[1] = 0;
    v41 = 4;
    v38 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
    v39 = 49;
    v36 = "UnionFs::UfsPathCachePayload::MarkRenamed";
    v37 = 42;
    v35 = 26;
    tlgWriteTransfer_EtwWriteTransfer(&dword_14009E178, &unk_140097338, 0, 0, 11);
  }
  if ( _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 160), *(_WORD *)(a1 + 160), 1) == 1 )
  {
    *(_WORD *)(a1 + 162) = 1;
    _mm_mfence();
    *(_BYTE *)(a1 + 165) = *(_BYTE *)(a1 + 164);
    *(_BYTE *)(a1 + 164) = 0;
    *(_DWORD *)(a1 + 168) = 0;
    _mm_mfence();
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v28 = a1;
      v31 = "SoftCount zeroed";
      v25 = 1061;
      v29 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      v30 = "UnionFs::UfsPathCachePayload::MarkRenamed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)&word_1400972EE,
        v7,
        v8,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v25,
        (__int64)&v28);
    }
    *(_DWORD *)(a1 + 172) = 0;
    *(_QWORD *)(a1 + 176) = 0;
    *(_WORD *)(a1 + 160) = 4;
    v15 = *a2;
    *a2 = 0;
    v16 = *(_QWORD *)(a1 + 208);
    *(_QWORD *)(a1 + 208) = v15;
    if ( v16 )
    {
      if ( !*(_BYTE *)(v16 + 16) )
        *(_OWORD *)v16 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v16, v6);
      ExFreePoolWithTag((PVOID)v16, 0);
    }
    if ( !*(_QWORD *)(a1 + 184) || !*(_QWORD *)(a1 + 200) )
      MicrosoftTelemetryAssertTriggeredMsgKM("m_Tombstone.OwningUnion && m_Tombstone.ScratchPath");
    v17 = *(_QWORD *)(a1 + 184);
    if ( v9 )
    {
      v18 = UnionFs::g_FilterState;
      *(_BYTE *)(v17 + 208) = 1;
      v19 = v18[15];
      if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 8), 1u) )
        KeSetEvent((PRKEVENT)(v19 + 16), 0, 0);
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 24) + 8LL));
      *((_QWORD *)&v27 + 1) = *(_QWORD *)(a1 + 24);
      v20 = (utl::_RefCountBase *)*((_QWORD *)&v27 + 1);
      *(_QWORD *)&v27 = a1 & ((unsigned __int128)-(__int128)(unsigned __int64)(a1 + 24) >> 64);
      UnionFs::UfsUnionCtx::AddTombstoneToList(v17, &v27);
      if ( v20 )
        utl::_RefCountBase::_DecStrong(v20);
    }
    KeSetEvent((PRKEVENT)(*(_QWORD *)(a1 + 136) + 56LL), 0, 0);
    if ( FastMutex )
      ExReleaseFastMutex(FastMutex);
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED0004LL,
      a3,
      (struct UnionFs::StackEventTracer *)0x5FD00120444LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::MarkRenamed",
      "ORIGIN: Marking renamed from non-soft tombstone",
      v22);
    if ( FastMutex )
      ExReleaseFastMutex(FastMutex);
    return 3236757508LL;
  }
}

```

## disassembly

```asm
0x1400429b0  mov     [rsp-8+arg_18], rbx
0x1400429b5  push    rbp
0x1400429b6  push    rsi
0x1400429b7  push    rdi
0x1400429b8  push    r12
0x1400429ba  push    r13
0x1400429bc  push    r14
0x1400429be  push    r15
0x1400429c0  lea     rbp, [rsp-70h]
0x1400429c5  sub     rsp, 170h
0x1400429cc  mov     rax, cs:__security_cookie
0x1400429d3  xor     rax, rsp
0x1400429d6  mov     [rbp+0A0h+var_40], rax
0x1400429da  mov     rdi, rdx
0x1400429dd  mov     rbx, rcx
0x1400429e0  mov     rdx, [rcx+88h]
0x1400429e7  mov     r15, r8
0x1400429ea  lea     rcx, [rsp+1A0h+FastMutex]
0x1400429ef  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x1400429f4  mov     al, [rbx+0A5h]
0x1400429fa  xor     r12d, r12d
0x1400429fd  nop
0x1400429fe  mov     esi, 1
0x140042a03  test    al, al
0x140042a05  jnz     short loc_140042A0C
0x140042a07  mov     r14b, sil
0x140042a0a  jmp     short loc_140042A19
0x140042a0c  mov     al, [rbx+0A4h]
0x140042a12  nop
0x140042a13  test    al, al
0x140042a15  setz    r14b
0x140042a19  mov     rax, [rdi]
0x140042a1c  lea     r10, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140042a23  lea     r13, aUnionfsUfspath_51; "UnionFs::UfsPathCachePayload::MarkRenam"...
0x140042a2a  movups  xmm0, xmmword ptr [rax]
0x140042a2d  mov     rax, [rbx+0C8h]
0x140042a34  movdqu  [rsp+1A0h+var_138], xmm0
0x140042a3a  movups  xmm0, xmmword ptr [rax]
0x140042a3d  mov     eax, cs:dword_14009E178
0x140042a43  movdqu  [rbp+0A0h+var_108], xmm0
0x140042a48  cmp     eax, 5
0x140042a4b  jbe     loc_140042B70
0x140042a51  mov     rcx, cs:qword_14009E190
0x140042a58  mov     rax, cs:qword_14009E188
0x140042a5f  test    al, 40h
0x140042a61  jz      loc_140042B70
0x140042a67  mov     rax, rcx
0x140042a6a  and     eax, 40h
0x140042a6d  cmp     rax, rcx
0x140042a70  jnz     loc_140042B70
0x140042a76  mov     rax, qword ptr [rbp+0A0h+var_108+8]
0x140042a7a  mov     rdx, cs:off_14007ED98
0x140042a81  mov     [rsp+1A0h+var_150], r14b
0x140042a86  test    rax, rax
0x140042a89  jz      short loc_140042A92
0x140042a8b  movzx   r9d, word ptr [rbp+0A0h+var_108]
0x140042a90  jmp     short loc_140042A98
0x140042a92  mov     r9d, r12d
0x140042a95  mov     rax, rdx
0x140042a98  mov     rcx, qword ptr [rsp+1A0h+var_138+8]
0x140042a9d  test    rcx, rcx
0x140042aa0  jz      short loc_140042AAA
0x140042aa2  movzx   r8d, word ptr [rsp+1A0h+var_138]
0x140042aa8  jmp     short loc_140042AB0
0x140042aaa  mov     r8d, r12d
0x140042aad  mov     rcx, rdx
0x140042ab0  mov     [rbp+0A0h+var_60], rax
0x140042ab4  lea     rdx, [rsp+1A0h+var_150]
0x140042ab9  movzx   eax, r9w
0x140042abd  xor     r9d, r9d
0x140042ac0  mov     [rbp+0A0h+var_58], eax
0x140042ac3  lea     rax, [rbp+0A0h+var_78]
0x140042ac7  mov     [rbp+0A0h+var_90], rax
0x140042acb  movzx   eax, r8w
0x140042acf  xor     r8d, r8d
0x140042ad2  mov     [rbp+0A0h+var_78], eax
0x140042ad5  lea     rax, [rsp+1A0h+var_14C]
0x140042ada  mov     [rbp+0A0h+var_A0], rax
0x140042ade  lea     rax, aMarkingRenamed; "Marking Renamed tombstone"
0x140042ae5  mov     [rbp+0A0h+var_50], rdx
0x140042ae9  lea     rdx, [rbp+0A0h+var_58]
0x140042aed  mov     [rbp+0A0h+var_D0], rax
0x140042af1  lea     rax, [rbp+0A0h+var_F0]
0x140042af5  mov     [rbp+0A0h+var_70], rdx
0x140042af9  lea     rdx, unk_140097338
0x140042b00  mov     [rbp+0A0h+var_80], rcx
0x140042b04  lea     rcx, dword_14009E178
0x140042b0b  mov     [rsp+1A0h+var_178], rax; char *
0x140042b10  mov     dword ptr [rsp+1A0h+var_180], 0Bh
0x140042b18  mov     [rsp+1A0h+var_14C], 412h
0x140042b20  mov     [rbp+0A0h+var_48], rsi
0x140042b24  mov     [rbp+0A0h+var_68], 2
0x140042b2c  mov     [rbp+0A0h+var_54], r12d
0x140042b30  mov     [rbp+0A0h+var_88], 2
0x140042b38  mov     [rbp+0A0h+var_74], r12d
0x140042b3c  mov     [rbp+0A0h+var_98], 4
0x140042b44  mov     [rbp+0A0h+var_B0], r10
0x140042b48  mov     [rbp+0A0h+var_A8], 31h ; '1'
0x140042b50  mov     [rbp+0A0h+var_C0], r13
0x140042b54  mov     [rbp+0A0h+var_B8], 2Ah ; '*'
0x140042b5c  mov     [rbp+0A0h+var_C8], 1Ah
0x140042b64  call    _tlgWriteTransfer_EtwWriteTransfer
0x140042b69  lea     r10, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140042b70  movzx   ecx, word ptr [rbx+0A0h]
0x140042b77  mov     eax, esi
0x140042b79  nop
0x140042b7a  nop
0x140042b7b  lock cmpxchg [rbx+0A0h], cx
0x140042b84  nop
0x140042b85  cmp     ax, si
0x140042b88  jnz     loc_140042D65
0x140042b8e  nop
0x140042b8f  mov     [rbx+0A2h], ax
0x140042b96  mfence
0x140042b99  mov     al, [rbx+0A4h]
0x140042b9f  nop
0x140042ba0  nop
0x140042ba1  mov     [rbx+0A5h], al
0x140042ba7  nop
0x140042ba8  mov     [rbx+0A4h], r12b
0x140042baf  nop
0x140042bb0  mov     [rbx+0A8h], r12d
0x140042bb7  mfence
0x140042bba  mov     eax, cs:dword_14009E178
0x140042bc0  cmp     eax, 5
0x140042bc3  jbe     short loc_140042C3D
0x140042bc5  mov     rcx, cs:qword_14009E190
0x140042bcc  mov     rax, cs:qword_14009E188
0x140042bd3  test    al, 40h
0x140042bd5  jz      short loc_140042C3D
0x140042bd7  mov     rax, rcx
0x140042bda  and     eax, 40h
0x140042bdd  cmp     rax, rcx
0x140042be0  jnz     short loc_140042C3D
0x140042be2  lea     rax, aSoftcountZeroe; "SoftCount zeroed"
0x140042be9  mov     [rsp+1A0h+var_128], rbx
0x140042bee  mov     [rbp+0A0h+var_110], rax
0x140042bf2  lea     rdx, word_1400972EE
0x140042bf9  lea     rax, [rsp+1A0h+var_128]
0x140042bfe  mov     [rsp+1A0h+var_148], 425h
0x140042c06  mov     [rsp+1A0h+var_160], rax
0x140042c0b  lea     rax, [rsp+1A0h+var_148]
0x140042c10  mov     [rsp+1A0h+var_168], rax
0x140042c15  lea     rax, [rbp+0A0h+var_120]
0x140042c19  mov     [rsp+1A0h+var_170], rax
0x140042c1e  lea     rax, [rbp+0A0h+var_118]
0x140042c22  mov     [rsp+1A0h+var_178], rax
0x140042c27  lea     rax, [rbp+0A0h+var_110]
0x140042c2b  mov     [rsp+1A0h+var_180], rax
0x140042c30  mov     [rbp+0A0h+var_120], r10
0x140042c34  mov     [rbp+0A0h+var_118], r13
0x140042c38  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140042c3d  mov     [rbx+0ACh], r12d
0x140042c44  mov     eax, 4
0x140042c49  mov     [rbx+0B0h], r12
0x140042c50  nop
0x140042c51  mov     [rbx+0A0h], ax
0x140042c58  mov     rax, [rdi]
0x140042c5b  mov     [rdi], r12
0x140042c5e  mov     rdi, [rbx+0D0h]
0x140042c65  mov     [rbx+0D0h], rax
0x140042c6c  test    rdi, rdi
0x140042c6f  jz      short loc_140042C96
0x140042c71  cmp     [rdi+10h], r12b
0x140042c75  jnz     short loc_140042C7D
0x140042c77  xorps   xmm0, xmm0
0x140042c7a  movups  xmmword ptr [rdi], xmm0
0x140042c7d  mov     rcx, rdi; UnicodeString
0x140042c80  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140042c85  xor     edx, edx; Tag
0x140042c87  mov     rcx, rdi; P
0x140042c8a  call    cs:__imp_ExFreePoolWithTag
0x140042c91  nop     dword ptr [rax+rax+00h]
0x140042c96  cmp     [rbx+0B8h], r12
0x140042c9d  jz      short loc_140042CA8
0x140042c9f  cmp     [rbx+0C8h], r12
0x140042ca6  jnz     short loc_140042CB4
0x140042ca8  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x140042caf  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140042cb4  mov     rcx, [rbx+0B8h]
0x140042cbb  test    r14b, r14b
0x140042cbe  jz      short loc_140042CF4
0x140042cc0  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140042cc7  mov     [rcx+0D0h], sil
0x140042cce  mov     rcx, [rax+78h]
0x140042cd2  nop
0x140042cd3  lock xadd [rcx+8], esi
0x140042cd8  nop
0x140042cd9  test    esi, esi
0x140042cdb  jnz     short loc_140042D2F
0x140042cdd  add     rcx, 10h; Event
0x140042ce1  xor     r8d, r8d; Wait
0x140042ce4  xor     edx, edx; Increment
0x140042ce6  call    cs:__imp_KeSetEvent
0x140042ced  nop     dword ptr [rax+rax+00h]
0x140042cf2  jmp     short loc_140042D2F
0x140042cf4  lea     r8, [rbx+18h]
0x140042cf8  mov     rax, [r8]
0x140042cfb  lock inc dword ptr [rax+8]
0x140042cff  mov     rdi, [r8]
0x140042d02  mov     rax, r8
0x140042d05  neg     rax
0x140042d08  mov     qword ptr [rsp+1A0h+var_138+8], rdi
0x140042d0d  sbb     rdx, rdx
0x140042d10  and     rdx, rbx
0x140042d13  mov     qword ptr [rsp+1A0h+var_138], rdx
0x140042d18  lea     rdx, [rsp+1A0h+var_138]
0x140042d1d  call    ?AddTombstoneToList@UfsUnionCtx@UnionFs@@QEAAX$$QEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@Z; UnionFs::UfsUnionCtx::AddTombstoneToList(utl::shared_ptr<UnionFs::UfsPathCachePayload> &&)
0x140042d22  test    rdi, rdi
0x140042d25  jz      short loc_140042D2F
0x140042d27  mov     rcx, rdi; this
0x140042d2a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140042d2f  mov     rcx, [rbx+88h]
0x140042d36  xor     r8d, r8d; Wait
0x140042d39  add     rcx, 38h ; '8'; Event
0x140042d3d  xor     edx, edx; Increment
0x140042d3f  call    cs:__imp_KeSetEvent
0x140042d46  nop     dword ptr [rax+rax+00h]
0x140042d4b  mov     rcx, [rsp+1A0h+FastMutex]; FastMutex
0x140042d50  test    rcx, rcx
0x140042d53  jz      short loc_140042D61
0x140042d55  call    cs:__imp_ExReleaseFastMutex
0x140042d5c  nop     dword ptr [rax+rax+00h]
0x140042d61  xor     eax, eax
0x140042d63  jmp     short loc_140042DA5
0x140042d65  lea     rax, aOriginMarkingR_0; "ORIGIN: Marking renamed from non-soft t"...
0x140042d6c  mov     ebx, 0C0ED0004h
0x140042d71  mov     ecx, ebx; this
0x140042d73  mov     [rsp+1A0h+var_180], rax; char *
0x140042d78  mov     r9, r13; unsigned __int64
0x140042d7b  mov     r8, 5FD00120444h; struct UnionFs::StackEventTracer *
0x140042d85  mov     rdx, r15; int
0x140042d88  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140042d8d  mov     rcx, [rsp+1A0h+FastMutex]; FastMutex
0x140042d92  test    rcx, rcx
0x140042d95  jz      short loc_140042DA3
0x140042d97  call    cs:__imp_ExReleaseFastMutex
0x140042d9e  nop     dword ptr [rax+rax+00h]
0x140042da3  mov     eax, ebx
0x140042da5  mov     rcx, [rbp+0A0h+var_40]
0x140042da9  xor     rcx, rsp; StackCookie
0x140042dac  call    __security_check_cookie
0x140042db1  mov     rbx, [rsp+1A0h+arg_18]
0x140042db9  add     rsp, 170h
0x140042dc0  pop     r15
0x140042dc2  pop     r14
0x140042dc4  pop     r13
0x140042dc6  pop     r12
0x140042dc8  pop     rdi
0x140042dc9  pop     rsi
0x140042dca  pop     rbp
0x140042dcb  retn
```
