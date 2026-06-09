# UnionFs::UfsPathCachePayload::MarkRenamed(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::StackEventTracer &)

- ea: `0x140042b30`
- end: `0x140042f4d`
- name: `?MarkRenamed@UfsPathCachePayload@UnionFs@@QEAAJ$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `1053`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002ca90`

## callees

- `0x140001b64`
- `0x140002500`
- `0x14000f81c`
- `0x140042b30`
- `0x140056c44`
- `0x14005f2a4`
- `0x140079cc4`
- `0x140079f68`
- `0x14007b2b0`
- `0x14007baf0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140042e0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042e0a`
- `ntoskrnl!KeSetEvent` at `0x140042e66`
- `ntoskrnl!KeSetEvent` at `0x140042ebf`
- `ntoskrnl!KeSetEvent` at `0x140042e66`
- `ntoskrnl!KeSetEvent` at `0x140042ebf`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042ed5`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042f17`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042ed5`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042f17`

## string_xrefs

- `0x140042b9c`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140042ce9`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140042e28`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x140042ba3`: `UnionFs::UfsPathCachePayload::MarkRenamed`
- `0x140042c5e`: `Marking Renamed tombstone`
- `0x140042ee5`: `ORIGIN: Marking renamed from non-soft tombstone`

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

  FsFltWil::AcquireFastMutex(&FastMutex, *(_QWORD *)(a1 + 144));
  if ( *(_BYTE *)(a1 + 173) )
    v9 = *(_BYTE *)(a1 + 172) == 0;
  else
    v9 = 1;
  v10 = *(__int128 **)(a1 + 208);
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
    v24 = 1067;
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
    tlgWriteTransfer_EtwWriteTransfer(&dword_14009E178, byte_140097425, 0, 0, 11);
  }
  if ( _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 168), *(_WORD *)(a1 + 168), 1) == 1 )
  {
    *(_WORD *)(a1 + 170) = 1;
    _mm_mfence();
    *(_BYTE *)(a1 + 173) = *(_BYTE *)(a1 + 172);
    *(_BYTE *)(a1 + 172) = 0;
    *(_DWORD *)(a1 + 176) = 0;
    _mm_mfence();
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v28 = a1;
      v31 = "SoftCount zeroed";
      v25 = 1086;
      v29 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      v30 = "UnionFs::UfsPathCachePayload::MarkRenamed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)byte_1400973DB,
        v7,
        v8,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v25,
        (__int64)&v28);
    }
    *(_DWORD *)(a1 + 180) = 0;
    *(_QWORD *)(a1 + 184) = 0;
    *(_WORD *)(a1 + 168) = 4;
    v15 = *a2;
    *a2 = 0;
    v16 = *(_QWORD *)(a1 + 216);
    *(_QWORD *)(a1 + 216) = v15;
    if ( v16 )
    {
      if ( !*(_BYTE *)(v16 + 16) )
        *(_OWORD *)v16 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v16, v6);
      ExFreePoolWithTag((PVOID)v16, 0);
    }
    if ( !*(_QWORD *)(a1 + 192) || !*(_QWORD *)(a1 + 208) )
      MicrosoftTelemetryAssertTriggeredMsgKM("m_Tombstone.OwningUnion && m_Tombstone.ScratchPath");
    v17 = *(_QWORD *)(a1 + 192);
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
    KeSetEvent((PRKEVENT)(*(_QWORD *)(a1 + 144) + 56LL), 0, 0);
    if ( FastMutex )
      ExReleaseFastMutex(FastMutex);
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED0004LL,
      a3,
      (struct UnionFs::StackEventTracer *)0x5FD0012045DLL,
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
0x140042b30  mov     [rsp-8+arg_18], rbx
0x140042b35  push    rbp
0x140042b36  push    rsi
0x140042b37  push    rdi
0x140042b38  push    r12
0x140042b3a  push    r13
0x140042b3c  push    r14
0x140042b3e  push    r15
0x140042b40  lea     rbp, [rsp-70h]
0x140042b45  sub     rsp, 170h
0x140042b4c  mov     rax, cs:__security_cookie
0x140042b53  xor     rax, rsp
0x140042b56  mov     [rbp+0A0h+var_40], rax
0x140042b5a  mov     rdi, rdx
0x140042b5d  mov     rbx, rcx
0x140042b60  mov     rdx, [rcx+90h]
0x140042b67  mov     r15, r8
0x140042b6a  lea     rcx, [rsp+1A0h+FastMutex]
0x140042b6f  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140042b74  mov     al, [rbx+0ADh]
0x140042b7a  xor     r12d, r12d
0x140042b7d  nop
0x140042b7e  mov     esi, 1
0x140042b83  test    al, al
0x140042b85  jnz     short loc_140042B8C
0x140042b87  mov     r14b, sil
0x140042b8a  jmp     short loc_140042B99
0x140042b8c  mov     al, [rbx+0ACh]
0x140042b92  nop
0x140042b93  test    al, al
0x140042b95  setz    r14b
0x140042b99  mov     rax, [rdi]
0x140042b9c  lea     r10, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140042ba3  lea     r13, aUnionfsUfspath_51; "UnionFs::UfsPathCachePayload::MarkRenam"...
0x140042baa  movups  xmm0, xmmword ptr [rax]
0x140042bad  mov     rax, [rbx+0D0h]
0x140042bb4  movdqu  [rsp+1A0h+var_138], xmm0
0x140042bba  movups  xmm0, xmmword ptr [rax]
0x140042bbd  mov     eax, cs:dword_14009E178
0x140042bc3  movdqu  [rbp+0A0h+var_108], xmm0
0x140042bc8  cmp     eax, 5
0x140042bcb  jbe     loc_140042CF0
0x140042bd1  mov     rcx, cs:qword_14009E190
0x140042bd8  mov     rax, cs:qword_14009E188
0x140042bdf  test    al, 40h
0x140042be1  jz      loc_140042CF0
0x140042be7  mov     rax, rcx
0x140042bea  and     eax, 40h
0x140042bed  cmp     rax, rcx
0x140042bf0  jnz     loc_140042CF0
0x140042bf6  mov     rax, qword ptr [rbp+0A0h+var_108+8]
0x140042bfa  mov     rdx, cs:off_14007EDA0
0x140042c01  mov     [rsp+1A0h+var_150], r14b
0x140042c06  test    rax, rax
0x140042c09  jz      short loc_140042C12
0x140042c0b  movzx   r9d, word ptr [rbp+0A0h+var_108]
0x140042c10  jmp     short loc_140042C18
0x140042c12  mov     r9d, r12d
0x140042c15  mov     rax, rdx
0x140042c18  mov     rcx, qword ptr [rsp+1A0h+var_138+8]
0x140042c1d  test    rcx, rcx
0x140042c20  jz      short loc_140042C2A
0x140042c22  movzx   r8d, word ptr [rsp+1A0h+var_138]
0x140042c28  jmp     short loc_140042C30
0x140042c2a  mov     r8d, r12d
0x140042c2d  mov     rcx, rdx
0x140042c30  mov     [rbp+0A0h+var_60], rax
0x140042c34  lea     rdx, [rsp+1A0h+var_150]
0x140042c39  movzx   eax, r9w
0x140042c3d  xor     r9d, r9d
0x140042c40  mov     [rbp+0A0h+var_58], eax
0x140042c43  lea     rax, [rbp+0A0h+var_78]
0x140042c47  mov     [rbp+0A0h+var_90], rax
0x140042c4b  movzx   eax, r8w
0x140042c4f  xor     r8d, r8d
0x140042c52  mov     [rbp+0A0h+var_78], eax
0x140042c55  lea     rax, [rsp+1A0h+var_14C]
0x140042c5a  mov     [rbp+0A0h+var_A0], rax
0x140042c5e  lea     rax, aMarkingRenamed; "Marking Renamed tombstone"
0x140042c65  mov     [rbp+0A0h+var_50], rdx
0x140042c69  lea     rdx, [rbp+0A0h+var_58]
0x140042c6d  mov     [rbp+0A0h+var_D0], rax
0x140042c71  lea     rax, [rbp+0A0h+var_F0]
0x140042c75  mov     [rbp+0A0h+var_70], rdx
0x140042c79  lea     rdx, byte_140097425
0x140042c80  mov     [rbp+0A0h+var_80], rcx
0x140042c84  lea     rcx, dword_14009E178
0x140042c8b  mov     [rsp+1A0h+var_178], rax; char *
0x140042c90  mov     dword ptr [rsp+1A0h+var_180], 0Bh
0x140042c98  mov     [rsp+1A0h+var_14C], 42Bh
0x140042ca0  mov     [rbp+0A0h+var_48], rsi
0x140042ca4  mov     [rbp+0A0h+var_68], 2
0x140042cac  mov     [rbp+0A0h+var_54], r12d
0x140042cb0  mov     [rbp+0A0h+var_88], 2
0x140042cb8  mov     [rbp+0A0h+var_74], r12d
0x140042cbc  mov     [rbp+0A0h+var_98], 4
0x140042cc4  mov     [rbp+0A0h+var_B0], r10
0x140042cc8  mov     [rbp+0A0h+var_A8], 31h ; '1'
0x140042cd0  mov     [rbp+0A0h+var_C0], r13
0x140042cd4  mov     [rbp+0A0h+var_B8], 2Ah ; '*'
0x140042cdc  mov     [rbp+0A0h+var_C8], 1Ah
0x140042ce4  call    _tlgWriteTransfer_EtwWriteTransfer
0x140042ce9  lea     r10, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140042cf0  movzx   ecx, word ptr [rbx+0A8h]
0x140042cf7  mov     eax, esi
0x140042cf9  nop
0x140042cfa  nop
0x140042cfb  lock cmpxchg [rbx+0A8h], cx
0x140042d04  nop
0x140042d05  cmp     ax, si
0x140042d08  jnz     loc_140042EE5
0x140042d0e  nop
0x140042d0f  mov     [rbx+0AAh], ax
0x140042d16  mfence
0x140042d19  mov     al, [rbx+0ACh]
0x140042d1f  nop
0x140042d20  nop
0x140042d21  mov     [rbx+0ADh], al
0x140042d27  nop
0x140042d28  mov     [rbx+0ACh], r12b
0x140042d2f  nop
0x140042d30  mov     [rbx+0B0h], r12d
0x140042d37  mfence
0x140042d3a  mov     eax, cs:dword_14009E178
0x140042d40  cmp     eax, 5
0x140042d43  jbe     short loc_140042DBD
0x140042d45  mov     rcx, cs:qword_14009E190
0x140042d4c  mov     rax, cs:qword_14009E188
0x140042d53  test    al, 40h
0x140042d55  jz      short loc_140042DBD
0x140042d57  mov     rax, rcx
0x140042d5a  and     eax, 40h
0x140042d5d  cmp     rax, rcx
0x140042d60  jnz     short loc_140042DBD
0x140042d62  lea     rax, aSoftcountZeroe; "SoftCount zeroed"
0x140042d69  mov     [rsp+1A0h+var_128], rbx
0x140042d6e  mov     [rbp+0A0h+var_110], rax
0x140042d72  lea     rdx, byte_1400973DB
0x140042d79  lea     rax, [rsp+1A0h+var_128]
0x140042d7e  mov     [rsp+1A0h+var_148], 43Eh
0x140042d86  mov     [rsp+1A0h+var_160], rax
0x140042d8b  lea     rax, [rsp+1A0h+var_148]
0x140042d90  mov     [rsp+1A0h+var_168], rax
0x140042d95  lea     rax, [rbp+0A0h+var_120]
0x140042d99  mov     [rsp+1A0h+var_170], rax
0x140042d9e  lea     rax, [rbp+0A0h+var_118]
0x140042da2  mov     [rsp+1A0h+var_178], rax
0x140042da7  lea     rax, [rbp+0A0h+var_110]
0x140042dab  mov     [rsp+1A0h+var_180], rax
0x140042db0  mov     [rbp+0A0h+var_120], r10
0x140042db4  mov     [rbp+0A0h+var_118], r13
0x140042db8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140042dbd  mov     [rbx+0B4h], r12d
0x140042dc4  mov     eax, 4
0x140042dc9  mov     [rbx+0B8h], r12
0x140042dd0  nop
0x140042dd1  mov     [rbx+0A8h], ax
0x140042dd8  mov     rax, [rdi]
0x140042ddb  mov     [rdi], r12
0x140042dde  mov     rdi, [rbx+0D8h]
0x140042de5  mov     [rbx+0D8h], rax
0x140042dec  test    rdi, rdi
0x140042def  jz      short loc_140042E16
0x140042df1  cmp     [rdi+10h], r12b
0x140042df5  jnz     short loc_140042DFD
0x140042df7  xorps   xmm0, xmm0
0x140042dfa  movups  xmmword ptr [rdi], xmm0
0x140042dfd  mov     rcx, rdi; UnicodeString
0x140042e00  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140042e05  xor     edx, edx; Tag
0x140042e07  mov     rcx, rdi; P
0x140042e0a  call    cs:__imp_ExFreePoolWithTag
0x140042e11  nop     dword ptr [rax+rax+00h]
0x140042e16  cmp     [rbx+0C0h], r12
0x140042e1d  jz      short loc_140042E28
0x140042e1f  cmp     [rbx+0D0h], r12
0x140042e26  jnz     short loc_140042E34
0x140042e28  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x140042e2f  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140042e34  mov     rcx, [rbx+0C0h]
0x140042e3b  test    r14b, r14b
0x140042e3e  jz      short loc_140042E74
0x140042e40  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140042e47  mov     [rcx+0D0h], sil
0x140042e4e  mov     rcx, [rax+78h]
0x140042e52  nop
0x140042e53  lock xadd [rcx+8], esi
0x140042e58  nop
0x140042e59  test    esi, esi
0x140042e5b  jnz     short loc_140042EAF
0x140042e5d  add     rcx, 10h; Event
0x140042e61  xor     r8d, r8d; Wait
0x140042e64  xor     edx, edx; Increment
0x140042e66  call    cs:__imp_KeSetEvent
0x140042e6d  nop     dword ptr [rax+rax+00h]
0x140042e72  jmp     short loc_140042EAF
0x140042e74  lea     r8, [rbx+18h]
0x140042e78  mov     rax, [r8]
0x140042e7b  lock inc dword ptr [rax+8]
0x140042e7f  mov     rdi, [r8]
0x140042e82  mov     rax, r8
0x140042e85  neg     rax
0x140042e88  mov     qword ptr [rsp+1A0h+var_138+8], rdi
0x140042e8d  sbb     rdx, rdx
0x140042e90  and     rdx, rbx
0x140042e93  mov     qword ptr [rsp+1A0h+var_138], rdx
0x140042e98  lea     rdx, [rsp+1A0h+var_138]
0x140042e9d  call    ?AddTombstoneToList@UfsUnionCtx@UnionFs@@QEAAX$$QEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@Z; UnionFs::UfsUnionCtx::AddTombstoneToList(utl::shared_ptr<UnionFs::UfsPathCachePayload> &&)
0x140042ea2  test    rdi, rdi
0x140042ea5  jz      short loc_140042EAF
0x140042ea7  mov     rcx, rdi; this
0x140042eaa  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140042eaf  mov     rcx, [rbx+90h]
0x140042eb6  xor     r8d, r8d; Wait
0x140042eb9  add     rcx, 38h ; '8'; Event
0x140042ebd  xor     edx, edx; Increment
0x140042ebf  call    cs:__imp_KeSetEvent
0x140042ec6  nop     dword ptr [rax+rax+00h]
0x140042ecb  mov     rcx, [rsp+1A0h+FastMutex]; FastMutex
0x140042ed0  test    rcx, rcx
0x140042ed3  jz      short loc_140042EE1
0x140042ed5  call    cs:__imp_ExReleaseFastMutex
0x140042edc  nop     dword ptr [rax+rax+00h]
0x140042ee1  xor     eax, eax
0x140042ee3  jmp     short loc_140042F25
0x140042ee5  lea     rax, aOriginMarkingR_0; "ORIGIN: Marking renamed from non-soft t"...
0x140042eec  mov     ebx, 0C0ED0004h
0x140042ef1  mov     ecx, ebx; this
0x140042ef3  mov     [rsp+1A0h+var_180], rax; char *
0x140042ef8  mov     r9, r13; unsigned __int64
0x140042efb  mov     r8, 5FD0012045Dh; struct UnionFs::StackEventTracer *
0x140042f05  mov     rdx, r15; int
0x140042f08  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140042f0d  mov     rcx, [rsp+1A0h+FastMutex]; FastMutex
0x140042f12  test    rcx, rcx
0x140042f15  jz      short loc_140042F23
0x140042f17  call    cs:__imp_ExReleaseFastMutex
0x140042f1e  nop     dword ptr [rax+rax+00h]
0x140042f23  mov     eax, ebx
0x140042f25  mov     rcx, [rbp+0A0h+var_40]
0x140042f29  xor     rcx, rsp; StackCookie
0x140042f2c  call    __security_check_cookie
0x140042f31  mov     rbx, [rsp+1A0h+arg_18]
0x140042f39  add     rsp, 170h
0x140042f40  pop     r15
0x140042f42  pop     r14
0x140042f44  pop     r13
0x140042f46  pop     r12
0x140042f48  pop     rdi
0x140042f49  pop     rsi
0x140042f4a  pop     rbp
0x140042f4b  retn
```
