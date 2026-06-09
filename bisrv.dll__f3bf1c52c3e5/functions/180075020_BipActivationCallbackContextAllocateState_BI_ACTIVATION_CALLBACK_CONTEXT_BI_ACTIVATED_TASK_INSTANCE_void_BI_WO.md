# BipActivationCallbackContextAllocateState(_BI_ACTIVATION_CALLBACK_CONTEXT *,_BI_ACTIVATED_TASK_INSTANCE *,void *,_BI_WORK_ITEM *,_GUID,_GUID const *,void *,ulong)

- ea: `0x180075020`
- end: `0x1800753fb`
- name: `?BipActivationCallbackContextAllocateState@@YAJPEAU_BI_ACTIVATION_CALLBACK_CONTEXT@@PEAU_BI_ACTIVATED_TASK_INSTANCE@@PEAXPEAU_BI_WORK_ITEM@@U_GUID@@PEBU4@2K@Z`
- size: `987`
- prototype: `__int64 __fastcall(struct _BI_ACTIVATION_CALLBACK_CONTEXT *, struct _BI_ACTIVATED_TASK_INSTANCE *, void *, struct _BI_WORK_ITEM *, struct _GUID *, const struct _GUID *, void *, SIZE_T cb)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013890`

## callees

- `0x180010c5c`
- `0x180013d20`
- `0x1800347a0`
- `0x180034dbc`
- `0x18004113c`
- `0x18004305c`
- `0x18004af00`
- `0x180053100`
- `0x18006d364`
- `0x180075020`
- `0x180094662`
- `0x18009467a`
- `0x180095010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18007515a`
- `ntdll!RtlCopySid` at `0x18007517c`
- `ntdll!RtlCopySid` at `0x18007515a`
- `ntdll!RtlCopySid` at `0x18007517c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007530f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007530f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180075230`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180075271`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180075230`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180075271`

## string_xrefs

- `0x18007526a`: `Windows.BackgroundTasks`

## pseudocode

```c
__int64 __fastcall BipActivationCallbackContextAllocateState(
        struct _BI_ACTIVATION_CALLBACK_CONTEXT *a1,
        struct _BI_ACTIVATED_TASK_INSTANCE *a2,
        void *a3,
        struct _BI_WORK_ITEM *a4,
        struct _GUID *a5,
        const struct _GUID *a6,
        void *a7,
        SIZE_T cb)
{
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // edx
  int v15; // eax
  int v16; // eax
  int AumidFromWorkItem; // ebx
  __int64 v18; // r8
  void *v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // eax
  _QWORD *v24; // rsi
  int Instance; // eax
  unsigned int v26; // eax
  unsigned __int16 *EntryPoint; // rax
  BSTR v28; // rax
  const OLECHAR *v29; // rcx
  UINT v30; // edx
  BSTR v31; // rax
  int v32; // r14d
  GUID v33; // xmm6
  void *v34; // rbx
  void *v35; // rax
  __int64 v36; // rax
  struct _GUID v37; // xmm1
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  void *Src; // [rsp+40h] [rbp-30h] BYREF
  struct _BI_ACTIVATED_TASK_INSTANCE *v43; // [rsp+48h] [rbp-28h] BYREF
  struct _GUID *v44; // [rsp+50h] [rbp-20h] BYREF
  const unsigned __int16 *v45; // [rsp+58h] [rbp-18h] BYREF

  Src = a7;
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, a3) )
  {
    v43 = a2;
    v44 = a5;
    v45 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
      (__int64)&dword_1800C3098,
      (unsigned __int8 *)byte_1800AE15B,
      v12,
      v13,
      &v45,
      (__int64 *)&v44,
      (__int64 *)&v43);
  }
  *((_DWORD *)a1 + 14) = 0;
  if ( !(unsigned __int8)BipUtilActTypeIsResourceTimerSupported(*((unsigned int *)a4 + 100)) )
    goto LABEL_13;
  v15 = BipGetActivationType(a4) - 1;
  if ( !v15 )
  {
    v14 = 4;
    goto LABEL_12;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    v14 = 1;
LABEL_12:
    *((_DWORD *)a1 + 14) = v14;
    goto LABEL_13;
  }
  if ( v16 != 1 )
  {
    AumidFromWorkItem = -1073741811;
    v18 = 4096;
    goto LABEL_49;
  }
  *((_DWORD *)a1 + 14) = 2;
  v14 = 2;
LABEL_13:
  *((_DWORD *)a1 + 6) = *((_DWORD *)a4 + 100);
  *((_QWORD *)a1 + 8) = *((_QWORD *)a2 + 40);
  *((_DWORD *)a1 + 18) = *((_DWORD *)a2 + 35);
  if ( (*(_DWORD *)(*((_QWORD *)a4 + 9) + 24LL) & 0x40000) == 0 )
    *((_DWORD *)a1 + 14) = v14 | 8;
  RtlCopySid(0x44u, (char *)a1 + 76, *(PSID *)(*(_QWORD *)(*((_QWORD *)a2 + 8) + 80LL) + 24LL));
  v19 = *(void **)(*((_QWORD *)a4 + 9) + 176LL);
  if ( v19 )
    RtlCopySid(0x44u, (char *)a1 + 144, v19);
  else
    memset_0((char *)a1 + 144, 0, 0x44u);
  AumidFromWorkItem = BipGetAumidFromWorkItem(a4, (char *)a1 + 16);
  if ( AumidFromWorkItem < 0 )
  {
    v18 = 0x2000;
    goto LABEL_49;
  }
  v23 = *((_DWORD *)a4 + 100);
  if ( v23 )
  {
    if ( v23 != 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v21, v20, v22);
      v18 = 0x100000;
      AumidFromWorkItem = -1073741811;
      goto LABEL_49;
    }
    *(_OWORD *)((char *)a1 + 212) = *((_OWORD *)a4 + 26);
  }
  else
  {
    EntryPoint = (unsigned __int16 *)BipWorkItemGetEntryPoint(a4);
    v28 = SysAllocStringLen(*((const OLECHAR **)EntryPoint + 1), *EntryPoint >> 1);
    *(_QWORD *)a1 = v28;
    if ( !v28 )
    {
      AumidFromWorkItem = -1073741801;
      v18 = 12288;
      goto LABEL_49;
    }
    v29 = (const OLECHAR *)*((_QWORD *)a4 + 55);
    if ( v29 )
    {
      v30 = *((unsigned __int16 *)a4 + 216) >> 1;
    }
    else
    {
      v30 = 23;
      v29 = L"Windows.BackgroundTasks";
    }
    v31 = SysAllocStringLen(v29, v30);
    *((_QWORD *)a1 + 1) = v31;
    if ( !v31 )
    {
      AumidFromWorkItem = -1073741801;
      v18 = 0x4000;
      goto LABEL_49;
    }
  }
  *((_QWORD *)a1 + 6) = a3;
  (*(void (__fastcall **)(void *))(*(_QWORD *)a3 + 8LL))(a3);
  v24 = (_QWORD *)((char *)a1 + 40);
  Instance = ATL::CComObject<CBackgroundWorkItemInstanceRemote>::CreateInstance((char *)a1 + 40);
  if ( Instance < 0 )
  {
    v18 = 20480;
    goto LABEL_26;
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 8LL))(*v24);
  Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v24)(
               *v24,
               &GUID_0166231b_fd21_4e33_a713_75eb3207a138,
               (char *)a1 + 32);
  if ( Instance < 0 )
  {
    v18 = 24576;
LABEL_26:
    AumidFromWorkItem = (unsigned __int16)Instance;
    v26 = (unsigned __int16)Instance | 0xC0070000;
    if ( AumidFromWorkItem )
      AumidFromWorkItem = v26;
    goto LABEL_49;
  }
  v32 = 0;
  v33 = GUID_NULL;
  v34 = 0;
  if ( a6
    && (*(_QWORD *)&a6->Data1 != *(_QWORD *)&GUID_NULL.Data1
     || *(_QWORD *)a6->Data4 != _mm_srli_si128((__m128i)GUID_NULL, 8).m128i_u64[0]) )
  {
    v33 = *a6;
    if ( (_DWORD)cb )
    {
      if ( Src )
      {
        v35 = CoTaskMemAlloc((unsigned int)cb);
        v34 = v35;
        if ( !v35 )
        {
          AumidFromWorkItem = -1073741801;
          v18 = 28672;
          goto LABEL_49;
        }
        v32 = cb;
        memcpy_0(v35, Src, (unsigned int)cb);
      }
    }
  }
  v36 = *v24;
  if ( *(_BYTE *)(*v24 + 72LL) )
  {
    AumidFromWorkItem = -1073278049;
    v18 = 0x8000;
  }
  else
  {
    *(_OWORD *)(v36 + 76) = *(_OWORD *)a2;
    v37 = *a5;
    *(_DWORD *)(v36 + 136) = v32;
    *(GUID *)(v36 + 120) = v33;
    *(_QWORD *)(v36 + 144) = v34;
    *(struct _GUID *)(v36 + 92) = v37;
    v18 = 0;
    AumidFromWorkItem = 0;
  }
LABEL_49:
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, v18) )
  {
    LODWORD(v43) = v39;
    v45 = (const unsigned __int16 *)a2;
    v44 = a5;
    LODWORD(Src) = AumidFromWorkItem;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v38,
      (unsigned __int8 *)word_1800AE4CA,
      v39,
      v40,
      (__int64)&Src,
      (__int64 *)&v44,
      (__int64 *)&v45,
      (__int64)&v43);
  }
  return (unsigned int)AumidFromWorkItem;
}

```

## disassembly

```asm
0x180075020  mov     [rsp-38h+arg_10], rbx
0x180075025  push    rbp
0x180075026  push    rsi
0x180075027  push    rdi
0x180075028  push    r12
0x18007502a  push    r13
0x18007502c  push    r14
0x18007502e  push    r15
0x180075030  mov     rbp, rsp
0x180075033  sub     rsp, 70h
0x180075037  mov     rax, [rbp+arg_30]
0x18007503b  mov     rsi, r9
0x18007503e  mov     r12d, dword ptr [rbp+cb]
0x180075042  mov     r14, r8
0x180075045  mov     r13, [rbp+arg_20]
0x180075049  mov     r15, rdx
0x18007504c  mov     [rbp+Src], rax
0x180075050  mov     rdi, rcx
0x180075053  mov     eax, cs:dword_1800C3098
0x180075059  movaps  [rsp+70h+var_10], xmm6
0x18007505e  cmp     eax, 5
0x180075061  jbe     short loc_1800750B6
0x180075063  mov     edx, 2
0x180075068  lea     rcx, dword_1800C3098
0x18007506f  call    _tlgKeywordOn
0x180075074  test    al, al
0x180075076  jz      short loc_1800750B6
0x180075078  lea     rax, [rbp+var_28]
0x18007507c  mov     [rbp+var_28], r15
0x180075080  mov     [rsp+70h+var_40], rax
0x180075085  lea     rdx, byte_1800AE15B
0x18007508c  lea     rax, [rbp+var_20]
0x180075090  mov     [rbp+var_20], r13
0x180075094  mov     [rsp+70h+var_48], rax
0x180075099  lea     rcx, dword_1800C3098
0x1800750a0  lea     rax, [rbp+var_18]
0x1800750a4  mov     [rbp+var_18], 0
0x1800750ac  mov     [rsp+70h+var_50], rax
0x1800750b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)
0x1800750b6  mov     dword ptr [rdi+38h], 0
0x1800750bd  xor     edx, edx
0x1800750bf  mov     ecx, [rsi+190h]
0x1800750c5  call    BipUtilActTypeIsResourceTimerSupported
0x1800750ca  test    al, al
0x1800750cc  jz      short loc_180075112
0x1800750ce  mov     rcx, rsi
0x1800750d1  call    BipGetActivationType
0x1800750d6  sub     eax, 1
0x1800750d9  jz      short loc_18007510A
0x1800750db  sub     eax, 1
0x1800750de  jz      short loc_180075103
0x1800750e0  cmp     eax, 1
0x1800750e3  jz      short loc_1800750F5
0x1800750e5  mov     ebx, 0C000000Dh
0x1800750ea  mov     r8d, 1000h
0x1800750f0  jmp     loc_18007537D
0x1800750f5  mov     dword ptr [rdi+38h], 2
0x1800750fc  mov     edx, 2
0x180075101  jmp     short loc_180075112
0x180075103  mov     edx, 1
0x180075108  jmp     short loc_18007510F
0x18007510a  mov     edx, 4
0x18007510f  mov     [rdi+38h], edx
0x180075112  mov     eax, [rsi+190h]
0x180075118  mov     [rdi+18h], eax
0x18007511b  mov     rax, [r15+140h]
0x180075122  mov     [rdi+40h], rax
0x180075126  mov     eax, [r15+8Ch]
0x18007512d  mov     [rdi+48h], eax
0x180075130  mov     rax, [rsi+48h]
0x180075134  test    dword ptr [rax+18h], 40000h
0x18007513b  jnz     short loc_180075143
0x18007513d  or      edx, 8
0x180075140  mov     [rdi+38h], edx
0x180075143  mov     rax, [r15+40h]
0x180075147  lea     rdx, [rdi+4Ch]; DestinationSid
0x18007514b  mov     ebx, 44h ; 'D'
0x180075150  mov     ecx, ebx; DestinationSidLength
0x180075152  mov     r8, [rax+50h]
0x180075156  mov     r8, [r8+18h]; SourceSid
0x18007515a  call    cs:__imp_RtlCopySid
0x180075160  mov     rax, [rsi+48h]
0x180075164  lea     rcx, [rdi+90h]; void *
0x18007516b  mov     r8, [rax+0B0h]; SourceSid
0x180075172  test    r8, r8
0x180075175  jz      short loc_180075184
0x180075177  mov     rdx, rcx; DestinationSid
0x18007517a  mov     ecx, ebx; DestinationSidLength
0x18007517c  call    cs:__imp_RtlCopySid
0x180075182  jmp     short loc_18007518E
0x180075184  mov     r8, rbx; Size
0x180075187  xor     edx, edx; Val
0x180075189  call    memset_0
0x18007518e  lea     rdx, [rdi+10h]
0x180075192  mov     rcx, rsi
0x180075195  call    BipGetAumidFromWorkItem
0x18007519a  mov     ebx, eax
0x18007519c  test    eax, eax
0x18007519e  jns     short loc_1800751AB
0x1800751a0  mov     r8d, 2000h
0x1800751a6  jmp     loc_18007537D
0x1800751ab  mov     eax, [rsi+190h]
0x1800751b1  test    eax, eax
0x1800751b3  jz      short loc_18007521F
0x1800751b5  cmp     eax, 2
0x1800751b8  jz      short loc_1800751CF
0x1800751ba  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800751bf  mov     r8d, 100000h
0x1800751c5  mov     ebx, 0C000000Dh
0x1800751ca  jmp     loc_18007537D
0x1800751cf  movups  xmm0, xmmword ptr [rsi+1A0h]
0x1800751d6  movdqu  xmmword ptr [rdi+0D4h], xmm0
0x1800751de  mov     [rdi+30h], r14
0x1800751e2  mov     rcx, r14
0x1800751e5  mov     rax, [r14]
0x1800751e8  mov     rax, [rax+8]
0x1800751ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800751f1  lea     rsi, [rdi+28h]
0x1800751f5  mov     rcx, rsi
0x1800751f8  call    ?CreateInstance@?$CComObject@VCBackgroundWorkItemInstanceRemote@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CBackgroundWorkItemInstanceRemote>::CreateInstance(ATL::CComObject<CBackgroundWorkItemInstanceRemote> * *)
0x1800751fd  test    eax, eax
0x1800751ff  jns     loc_180075294
0x180075205  mov     r8d, 5000h
0x18007520b  movzx   ebx, ax
0x18007520e  mov     eax, ebx
0x180075210  or      eax, 0C0070000h
0x180075215  test    ebx, ebx
0x180075217  cmovnz  ebx, eax
0x18007521a  jmp     loc_18007537D
0x18007521f  mov     rcx, rsi
0x180075222  call    BipWorkItemGetEntryPoint
0x180075227  movzx   edx, word ptr [rax]
0x18007522a  mov     rcx, [rax+8]; strIn
0x18007522e  shr     edx, 1; ui
0x180075230  call    cs:__imp_SysAllocStringLen
0x180075236  mov     [rdi], rax
0x180075239  test    rax, rax
0x18007523c  jnz     short loc_18007524E
0x18007523e  mov     ebx, 0C0000017h
0x180075243  mov     r8d, 3000h
0x180075249  jmp     loc_18007537D
0x18007524e  mov     rcx, [rsi+1B8h]
0x180075255  test    rcx, rcx
0x180075258  jz      short loc_180075265
0x18007525a  movzx   edx, word ptr [rsi+1B0h]
0x180075261  shr     edx, 1
0x180075263  jmp     short loc_180075271
0x180075265  mov     edx, 17h; ui
0x18007526a  lea     rcx, strIn; "Windows.BackgroundTasks"
0x180075271  call    cs:__imp_SysAllocStringLen
0x180075277  mov     [rdi+8], rax
0x18007527b  test    rax, rax
0x18007527e  jnz     loc_1800751DE
0x180075284  mov     ebx, 0C0000017h
0x180075289  mov     r8d, 4000h
0x18007528f  jmp     loc_18007537D
0x180075294  mov     rcx, [rsi]
0x180075297  mov     rax, [rcx]
0x18007529a  mov     rax, [rax+8]
0x18007529e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800752a3  mov     rcx, [rsi]
0x1800752a6  lea     r8, [rdi+20h]
0x1800752aa  lea     rdx, _GUID_0166231b_fd21_4e33_a713_75eb3207a138
0x1800752b1  mov     rax, [rcx]
0x1800752b4  mov     rax, [rax]
0x1800752b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800752bc  test    eax, eax
0x1800752be  jns     short loc_1800752CB
0x1800752c0  mov     r8d, 6000h
0x1800752c6  jmp     loc_18007520B
0x1800752cb  mov     rcx, [rbp+arg_28]
0x1800752cf  xor     r14d, r14d
0x1800752d2  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1800752d9  xor     ebx, ebx
0x1800752db  test    rcx, rcx
0x1800752de  jz      short loc_18007533C
0x1800752e0  movq    rax, xmm6
0x1800752e5  cmp     [rcx], rax
0x1800752e8  jnz     short loc_1800752FE
0x1800752ea  movdqa  xmm0, xmm6
0x1800752ee  psrldq  xmm0, 8
0x1800752f3  movq    rax, xmm0
0x1800752f8  cmp     [rcx+8], rax
0x1800752fc  jz      short loc_18007533C
0x1800752fe  movups  xmm6, xmmword ptr [rcx]
0x180075301  test    r12d, r12d
0x180075304  jz      short loc_18007533C
0x180075306  cmp     [rbp+Src], rbx
0x18007530a  jz      short loc_18007533C
0x18007530c  mov     rcx, r12; cb
0x18007530f  call    cs:__imp_CoTaskMemAlloc
0x180075315  mov     rbx, rax
0x180075318  test    rax, rax
0x18007531b  jnz     short loc_18007532A
0x18007531d  mov     ebx, 0C0000017h
0x180075322  mov     r8d, 7000h
0x180075328  jmp     short loc_18007537D
0x18007532a  mov     rdx, [rbp+Src]; Src
0x18007532e  mov     r8, r12; Size
0x180075331  mov     rcx, rax; void *
0x180075334  mov     r14d, r12d
0x180075337  call    memcpy_0
0x18007533c  mov     rax, [rsi]
0x18007533f  cmp     byte ptr [rax+48h], 0
0x180075343  jnz     short loc_180075372
0x180075345  movups  xmm0, xmmword ptr [r15]
0x180075349  movdqu  xmmword ptr [rax+4Ch], xmm0
0x18007534e  movups  xmm1, xmmword ptr [r13+0]
0x180075353  mov     [rax+88h], r14d
0x18007535a  movdqu  xmmword ptr [rax+78h], xmm6
0x18007535f  mov     [rax+90h], rbx
0x180075366  movdqu  xmmword ptr [rax+5Ch], xmm1
0x18007536b  xor     r8d, r8d
0x18007536e  xor     ebx, ebx
0x180075370  jmp     short loc_18007537D
0x180075372  mov     ebx, 0C007139Fh
0x180075377  mov     r8d, 8000h
0x18007537d  mov     eax, cs:dword_1800C3098
0x180075383  cmp     eax, 5
0x180075386  jbe     short loc_1800753DC
0x180075388  mov     edx, 2
0x18007538d  lea     rcx, dword_1800C3098
0x180075394  call    _tlgKeywordOn
0x180075399  test    al, al
0x18007539b  jz      short loc_1800753DC
0x18007539d  lea     rax, [rbp+var_28]
0x1800753a1  mov     dword ptr [rbp+var_28], r8d
0x1800753a5  mov     [rsp+70h+var_38], rax
0x1800753aa  lea     rdx, word_1800AE4CA
0x1800753b1  lea     rax, [rbp+var_18]
0x1800753b5  mov     [rbp+var_18], r15
0x1800753b9  mov     [rsp+70h+var_40], rax
0x1800753be  lea     rax, [rbp+var_20]
0x1800753c2  mov     [rsp+70h+var_48], rax
0x1800753c7  lea     rax, [rbp+Src]
0x1800753cb  mov     [rsp+70h+var_50], rax
0x1800753d0  mov     [rbp+var_20], r13
0x1800753d4  mov     dword ptr [rbp+Src], ebx
0x1800753d7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800753dc  movaps  xmm6, [rsp+70h+var_10]
0x1800753e1  mov     eax, ebx
0x1800753e3  mov     rbx, [rsp+70h+arg_10]
0x1800753eb  add     rsp, 70h
0x1800753ef  pop     r15
0x1800753f1  pop     r14
0x1800753f3  pop     r13
0x1800753f5  pop     r12
0x1800753f7  pop     rdi
0x1800753f8  pop     rsi
0x1800753f9  pop     rbp
0x1800753fa  retn
```
