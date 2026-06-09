# UnionFs::Utils::CheckShareAccess(ulong,ulong,_FILE_OBJECT &,UnionFs::UfsFsContext &,UnionFs::Utils::IoShareAccessFlags,UnionFs::ShareAccessCaller,UnionFs::StackEventTracer &,bool)

- ea: `0x14006a0dc`
- end: `0x14006a5b5`
- name: `?CheckShareAccess@Utils@UnionFs@@YAJKKAEAU_FILE_OBJECT@@AEAVUfsFsContext@2@W4IoShareAccessFlags@12@W4ShareAccessCaller@2@AEAVStackEventTracer@2@_N@Z`
- size: `1241`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1400114e4`
- `0x14005913c`

## callees

- `0x140003ef4`
- `0x140004080`
- `0x140056bd0`
- `0x140057cc0`
- `0x14005a460`
- `0x1400679dc`
- `0x14006a0dc`
- `0x14006f70c`
- `0x140079d8c`
- `0x140079dd4`

## import_xrefs

- `ntoskrnl!IoCheckLinkShareAccess` at `0x14006a1fb`
- `ntoskrnl!IoCheckLinkShareAccess` at `0x14006a1fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a16a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a3e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a550`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a58b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a16a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a3e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a550`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a58b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006a52e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006a569`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006a52e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006a569`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006a53a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006a575`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006a53a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006a575`

## string_xrefs

- `0x14006a28e`: `API: CheckShareAccess`
- `0x14006a501`: `API: IoCheckLinkShareAccess`
- `0x14006a299`: `UnionFs::Utils::CheckShareAccess`
- `0x14006a508`: `UnionFs::Utils::CheckShareAccess`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CheckShareAccess(
        unsigned int a1,
        unsigned int a2,
        struct _ERESOURCE *a3,
        __int64 a4,
        char *a5,
        char a6,
        int a7,
        __int16 a8)
{
  char *v8; // rdi
  int IsEnabledDeviceUsageNoInline; // eax
  int v13; // r14d
  PVOID *v14; // rax
  struct _ERESOURCE *v15; // rbx
  __int64 v16; // rdx
  _OWORD *v17; // rsi
  __int128 v18; // xmm1
  int v19; // r14d
  __int128 v20; // xmm1
  struct _UNICODE_STRING *v21; // r12
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  const struct _UNICODE_STRING *v25; // rax
  bool v26; // zf
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  char *v31; // [rsp+30h] [rbp-F8h]
  struct _ERESOURCE *v32; // [rsp+A8h] [rbp-80h] BYREF
  int v33; // [rsp+B0h] [rbp-78h] BYREF
  unsigned int v34; // [rsp+B4h] [rbp-74h] BYREF
  unsigned int v35; // [rsp+B8h] [rbp-70h] BYREF
  int v36; // [rsp+BCh] [rbp-6Ch] BYREF
  int v37; // [rsp+C0h] [rbp-68h] BYREF
  int v38; // [rsp+C4h] [rbp-64h] BYREF
  int v39; // [rsp+C8h] [rbp-60h] BYREF
  unsigned int v40; // [rsp+CCh] [rbp-5Ch] BYREF
  PVOID P; // [rsp+D0h] [rbp-58h] BYREF
  const char *v42; // [rsp+D8h] [rbp-50h] BYREF
  const char *v43; // [rsp+E0h] [rbp-48h] BYREF
  const struct _UNICODE_STRING *v44; // [rsp+E8h] [rbp-40h] BYREF
  _OWORD v45[5]; // [rsp+F0h] [rbp-38h]
  unsigned int v46; // [rsp+158h] [rbp+30h] BYREF
  unsigned int v47; // [rsp+160h] [rbp+38h] BYREF
  PVOID v48; // [rsp+170h] [rbp+48h] BYREF

  v47 = a2;
  v46 = a1;
  v8 = 0;
  v48 = 0;
  IsEnabledDeviceUsageNoInline = Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline();
  v13 = (int)a5;
  if ( IsEnabledDeviceUsageNoInline )
  {
    v32 = a3;
    LODWORD(v48) = ((unsigned __int8)a5 & 1) + 1;
    v14 = (PVOID *)utl::make_unique<UnionFs::ShareAccessDbg,_FILE_OBJECT *,enum UnionFs::ShareAccessCaller &,enum UnionFs::ShareAccessOperation,unsigned long &,unsigned long &,0>(
                     (unsigned int)&P,
                     (unsigned int)&v32,
                     (unsigned int)&a6,
                     (unsigned int)&v48,
                     (__int64)&v46,
                     (__int64)&v47);
    v8 = (char *)*v14;
    *v14 = 0;
    v48 = v8;
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( !v8 )
      _InterlockedIncrement((volatile signed __int32 *)(a4 + 204));
  }
  v15 = 0;
  if ( (_BYTE)a8 )
  {
    v16 = *(_QWORD *)(a4 + 120) + 56LL;
    if ( (v13 & 3) == 2 )
      FsFltWil::AcquireResourceShared(&v32, v16);
    else
      FsFltWil::AcquireResourceExclusive(&v32, v16);
    v15 = v32;
  }
  v17 = (_OWORD *)(a4 + 152);
  if ( (unsigned int)Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline() && v8 )
  {
    v18 = *(_OWORD *)(a4 + 164);
    v45[0] = *v17;
    *(_OWORD *)((char *)v45 + 12) = v18;
    *(_OWORD *)(v8 + 24) = v45[0];
    *(_OWORD *)(v8 + 36) = v18;
  }
  LODWORD(v31) = v13;
  v19 = IoCheckLinkShareAccess(v46, a2, a3, a4 + 152, 0);
  if ( (unsigned int)Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v8 )
    {
      *((_DWORD *)v8 + 70) = v19;
      v20 = *(_OWORD *)(a4 + 164);
      v45[0] = *v17;
      *(_OWORD *)((char *)v45 + 12) = v20;
      *((_OWORD *)v8 + 4) = v45[0];
      *(_OWORD *)(v8 + 76) = v20;
      v8[104] = BYTE2(a3->NumberOfSharedWaiters);
      v8[105] = HIBYTE(a3->NumberOfSharedWaiters);
      v8[106] = a3->NumberOfExclusiveWaiters;
      v8[107] = BYTE1(a3->NumberOfExclusiveWaiters);
      v8[108] = BYTE2(a3->NumberOfExclusiveWaiters);
      v8[109] = HIBYTE(a3->NumberOfExclusiveWaiters);
      UnionFs::UfsFsContext::AddShareAccessDbgEntry(a4, &v48);
      v8 = (char *)v48;
    }
    if ( v19 < 0 )
    {
      UnionFs::Utils::GetProcessImageFileName(&v48);
      v21 = (struct _UNICODE_STRING *)v48;
      if ( v48 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v19,
          a7,
          (struct UnionFs::StackEventTracer *)0x61B00210AD2LL,
          (unsigned __int64)"UnionFs::Utils::CheckShareAccess",
          "API: CheckShareAccess",
          v31);
        if ( (unsigned int)dword_14009E178 > 2 )
        {
          LODWORD(v48) = *(_DWORD *)(a4 + 176);
          v33 = *(_DWORD *)(a4 + 172);
          v34 = *(_DWORD *)(a4 + 168);
          v35 = *(_DWORD *)(a4 + 164);
          v36 = *(_DWORD *)(a4 + 160);
          v37 = *(_DWORD *)(a4 + 156);
          v38 = *(_DWORD *)v17;
          v39 = (int)a5;
          v40 = v47;
          LODWORD(P) = v46;
          v25 = &FsTlEmptyUnicodeString;
          v26 = v21->Buffer == 0;
          v42 = (const char *)a4;
          if ( !v26 )
            v25 = v21;
          LODWORD(v32) = 1563;
          v44 = v25;
          a8 = 2770;
          v43 = "UnionFs::Utils::CheckShareAccess";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)&word_14009A4AE,
            v23,
            v24,
            (__int64)&v43,
            (__int64)&v32,
            (__int64)&a8,
            (__int64)&v42,
            (__int64)&v44,
            (__int64)&P,
            (__int64)&v40,
            (__int64)&v39,
            (__int64)&v38,
            (__int64)&v37,
            (__int64)&v36,
            (__int64)&v35,
            (__int64)&v34,
            (__int64)&v33,
            (__int64)&v48);
        }
        if ( v21 )
          ExFreePoolWithTag(v21, 0);
      }
      else
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v19,
          a7,
          (struct UnionFs::StackEventTracer *)0x61E00210AE7LL,
          (unsigned __int64)"UnionFs::Utils::CheckShareAccess",
          "API: CheckShareAccess",
          v31);
        if ( (unsigned int)dword_14009E178 > 2 )
        {
          LODWORD(v48) = *(_DWORD *)(a4 + 176);
          LODWORD(v32) = *(_DWORD *)(a4 + 172);
          LODWORD(P) = *(_DWORD *)(a4 + 168);
          v40 = *(_DWORD *)(a4 + 164);
          v39 = *(_DWORD *)(a4 + 160);
          v38 = *(_DWORD *)(a4 + 156);
          v37 = *(_DWORD *)v17;
          v36 = (int)a5;
          v35 = v47;
          v34 = v46;
          a8 = 2791;
          v43 = (const char *)a4;
          v33 = 1566;
          v42 = "UnionFs::Utils::CheckShareAccess";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v27,
            (unsigned int)&dword_140099D8C,
            v28,
            v29,
            (__int64)&v42,
            (__int64)&v33,
            (__int64)&a8,
            (__int64)&v43,
            (__int64)&v34,
            (__int64)&v35,
            (__int64)&v36,
            (__int64)&v37,
            (__int64)&v38,
            (__int64)&v39,
            (__int64)&v40,
            (__int64)&P,
            (__int64)&v32,
            (__int64)&v48);
        }
      }
      goto LABEL_29;
    }
  }
  else if ( v19 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v19,
      a7,
      (struct UnionFs::StackEventTracer *)0x22D00210AEDLL,
      (unsigned __int64)"UnionFs::Utils::CheckShareAccess",
      "API: IoCheckLinkShareAccess",
      v31);
LABEL_29:
    if ( v15 )
    {
      ExReleaseResourceLite(v15);
      KeLeaveCriticalRegion();
    }
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
    return (unsigned int)v19;
  }
  if ( v15 )
  {
    ExReleaseResourceLite(v15);
    KeLeaveCriticalRegion();
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  return 0;
}

```

## disassembly

```asm
0x14006a0dc  mov     rax, rsp
0x14006a0df  mov     [rax+18h], rbx
0x14006a0e3  mov     [rax+10h], edx
0x14006a0e6  mov     [rax+8], ecx
0x14006a0e9  push    rbp
0x14006a0ea  push    rsi
0x14006a0eb  push    rdi
0x14006a0ec  push    r12
0x14006a0ee  push    r13
0x14006a0f0  push    r14
0x14006a0f2  push    r15
0x14006a0f4  lea     rbp, [rax-28h]
0x14006a0f8  sub     rsp, 110h
0x14006a0ff  xor     edi, edi
0x14006a101  mov     r13, r9
0x14006a104  mov     [rbp+20h+arg_18], rdi
0x14006a108  mov     r15, r8
0x14006a10b  mov     r12d, edx
0x14006a10e  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x14006a113  mov     r14d, dword ptr [rbp+20h+arg_20]
0x14006a117  test    eax, eax
0x14006a119  jz      short loc_14006A185
0x14006a11b  mov     eax, r14d
0x14006a11e  mov     [rbp+20h+var_A0], r15
0x14006a122  and     eax, 1
0x14006a125  lea     r9, [rbp+20h+arg_18]
0x14006a129  inc     eax
0x14006a12b  lea     r8, [rbp+20h+arg_28]
0x14006a12f  mov     dword ptr [rbp+20h+arg_18], eax
0x14006a132  lea     rdx, [rbp+20h+var_A0]
0x14006a136  lea     rax, [rbp+20h+arg_8]
0x14006a13a  mov     [rsp+140h+var_118], rax
0x14006a13f  lea     rcx, [rbp+20h+P]
0x14006a143  lea     rax, [rbp+20h+arg_0]
0x14006a147  mov     [rsp+140h+var_120], rax
0x14006a14c  call    ??$make_unique@UShareAccessDbg@UnionFs@@PEAU_FILE_OBJECT@@AEAW4ShareAccessCaller@2@W4ShareAccessOperation@2@AEAKAEAK$0A@@utl@@YA?AV?$unique_ptr@UShareAccessDbg@UnionFs@@U?$default_delete@UShareAccessDbg@UnionFs@@@utl@@@0@$$QEAPEAU_FILE_OBJECT@@AEAW4ShareAccessCaller@UnionFs@@$$QEAW4ShareAccessOperation@4@AEAK3@Z; utl::make_unique<UnionFs::ShareAccessDbg,_FILE_OBJECT *,UnionFs::ShareAccessCaller &,UnionFs::ShareAccessOperation,ulong &,ulong &,0>(_FILE_OBJECT * &&,UnionFs::ShareAccessCaller &,UnionFs::ShareAccessOperation &&,ulong &,ulong &)
0x14006a151  mov     rdi, [rax]
0x14006a154  mov     qword ptr [rax], 0
0x14006a15b  mov     rcx, [rbp+20h+P]; P
0x14006a15f  mov     [rbp+20h+arg_18], rdi
0x14006a163  test    rcx, rcx
0x14006a166  jz      short loc_14006A176
0x14006a168  xor     edx, edx; Tag
0x14006a16a  call    cs:__imp_ExFreePoolWithTag
0x14006a171  nop     dword ptr [rax+rax+00h]
0x14006a176  test    rdi, rdi
0x14006a179  jnz     short loc_14006A185
0x14006a17b  nop
0x14006a17c  lock inc dword ptr [r13+0CCh]
0x14006a184  nop
0x14006a185  xor     ebx, ebx
0x14006a187  cmp     byte ptr [rbp+20h+arg_38], bl
0x14006a18a  jz      short loc_14006A1B1
0x14006a18c  mov     rdx, [r13+78h]
0x14006a190  lea     rcx, [rbp+20h+var_A0]
0x14006a194  mov     eax, r14d
0x14006a197  add     rdx, 38h ; '8'
0x14006a19b  and     al, 3
0x14006a19d  cmp     al, 2
0x14006a19f  jnz     short loc_14006A1A8
0x14006a1a1  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x14006a1a6  jmp     short loc_14006A1AD
0x14006a1a8  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x14006a1ad  mov     rbx, [rbp+20h+var_A0]
0x14006a1b1  lea     rsi, [r13+98h]
0x14006a1b8  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x14006a1bd  test    eax, eax
0x14006a1bf  jz      short loc_14006A1E1
0x14006a1c1  test    rdi, rdi
0x14006a1c4  jz      short loc_14006A1E1
0x14006a1c6  movups  xmm0, xmmword ptr [rsi]
0x14006a1c9  movups  xmm1, xmmword ptr [rsi+0Ch]
0x14006a1cd  movups  [rbp+20h+var_58], xmm0
0x14006a1d1  movups  [rbp+20h+var_58+0Ch], xmm1
0x14006a1d5  movups  xmm0, [rbp+20h+var_58]
0x14006a1d9  movups  xmmword ptr [rdi+18h], xmm0
0x14006a1dd  movups  xmmword ptr [rdi+24h], xmm1
0x14006a1e1  mov     ecx, [rbp+20h+arg_0]
0x14006a1e4  mov     r9, rsi
0x14006a1e7  mov     dword ptr [rsp+140h+var_118], r14d; char *
0x14006a1ec  mov     r8, r15
0x14006a1ef  mov     edx, r12d
0x14006a1f2  mov     [rsp+140h+var_120], 0
0x14006a1fb  call    cs:__imp_IoCheckLinkShareAccess
0x14006a202  nop     dword ptr [rax+rax+00h]
0x14006a207  mov     r14d, eax
0x14006a20a  call    Feature_UnionFS_SharingDiagnostics__private_IsEnabledDeviceUsageNoInline
0x14006a20f  test    eax, eax
0x14006a211  jz      loc_14006A4F8
0x14006a217  test    rdi, rdi
0x14006a21a  jz      short loc_14006A278
0x14006a21c  mov     [rdi+118h], r14d
0x14006a223  lea     rdx, [rbp+20h+arg_18]
0x14006a227  movups  xmm0, xmmword ptr [rsi]
0x14006a22a  mov     rcx, r13
0x14006a22d  movups  xmm1, xmmword ptr [rsi+0Ch]
0x14006a231  movups  [rbp+20h+var_58], xmm0
0x14006a235  movups  [rbp+20h+var_58+0Ch], xmm1
0x14006a239  movups  xmm0, [rbp+20h+var_58]
0x14006a23d  movups  xmmword ptr [rdi+40h], xmm0
0x14006a241  movups  xmmword ptr [rdi+4Ch], xmm1
0x14006a245  mov     al, [r15+4Ah]
0x14006a249  mov     [rdi+68h], al
0x14006a24c  mov     al, [r15+4Bh]
0x14006a250  mov     [rdi+69h], al
0x14006a253  mov     al, [r15+4Ch]
0x14006a257  mov     [rdi+6Ah], al
0x14006a25a  mov     al, [r15+4Dh]
0x14006a25e  mov     [rdi+6Bh], al
0x14006a261  mov     al, [r15+4Eh]
0x14006a265  mov     [rdi+6Ch], al
0x14006a268  mov     al, [r15+4Fh]
0x14006a26c  mov     [rdi+6Dh], al
0x14006a26f  call    ?AddShareAccessDbgEntry@UfsFsContext@UnionFs@@QEAAX$$QEAV?$unique_ptr@UShareAccessDbg@UnionFs@@U?$default_delete@UShareAccessDbg@UnionFs@@@utl@@@utl@@@Z; UnionFs::UfsFsContext::AddShareAccessDbgEntry(utl::unique_ptr<UnionFs::ShareAccessDbg,utl::default_delete<UnionFs::ShareAccessDbg>> &&)
0x14006a274  mov     rdi, [rbp+20h+arg_18]
0x14006a278  test    r14d, r14d
0x14006a27b  jns     loc_14006A561
0x14006a281  lea     rcx, [rbp+20h+arg_18]
0x14006a285  call    ?GetProcessImageFileName@Utils@UnionFs@@YA?AV?$unique_ptr@U_UNICODE_STRING@@U?$default_delete@U_UNICODE_STRING@@@utl@@@utl@@PEAU_KPROCESS@@@Z; UnionFs::Utils::GetProcessImageFileName(_KPROCESS *)
0x14006a28a  mov     r12, [rbp+20h+arg_18]
0x14006a28e  lea     rax, aApiChecksharea; "API: CheckShareAccess"
0x14006a295  mov     rdx, qword ptr [rbp+20h+arg_30]; int
0x14006a299  lea     r15, aUnionfsUtilsCh_0; "UnionFs::Utils::CheckShareAccess"
0x14006a2a0  mov     [rsp+140h+var_120], rax; char *
0x14006a2a5  mov     ecx, r14d; this
0x14006a2a8  mov     r9, r15; unsigned __int64
0x14006a2ab  test    r12, r12
0x14006a2ae  jz      loc_14006A3F5
0x14006a2b4  mov     r8, 61B00210AD2h; struct UnionFs::StackEventTracer *
0x14006a2be  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a2c3  mov     eax, cs:dword_14009E178
0x14006a2c9  cmp     eax, 2
0x14006a2cc  jbe     loc_14006A3D6
0x14006a2d2  mov     eax, [rsi+18h]
0x14006a2d5  lea     rdx, word_14009A4AE
0x14006a2dc  mov     dword ptr [rbp+20h+arg_18], eax
0x14006a2df  mov     eax, [rsi+14h]
0x14006a2e2  mov     [rbp+20h+var_98], eax
0x14006a2e5  mov     eax, [rsi+10h]
0x14006a2e8  mov     [rbp+20h+var_94], eax
0x14006a2eb  mov     eax, [rsi+0Ch]
0x14006a2ee  mov     [rbp+20h+var_90], eax
0x14006a2f1  mov     eax, [rsi+8]
0x14006a2f4  mov     [rbp+20h+var_8C], eax
0x14006a2f7  mov     eax, [rsi+4]
0x14006a2fa  mov     [rbp+20h+var_88], eax
0x14006a2fd  mov     eax, [rsi]
0x14006a2ff  mov     [rbp+20h+var_84], eax
0x14006a302  mov     eax, dword ptr [rbp+20h+arg_20]
0x14006a305  mov     [rbp+20h+var_80], eax
0x14006a308  mov     eax, [rbp+20h+arg_8]
0x14006a30b  mov     [rbp+20h+var_7C], eax
0x14006a30e  mov     eax, [rbp+20h+arg_0]
0x14006a311  mov     dword ptr [rbp+20h+P], eax
0x14006a314  lea     rax, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x14006a31b  cmp     qword ptr [r12+8], 0
0x14006a321  mov     [rbp+20h+var_70], r13
0x14006a325  cmovnz  rax, r12
0x14006a329  mov     dword ptr [rbp+20h+var_A0], 61Bh
0x14006a330  mov     [rbp+20h+var_60], rax
0x14006a334  mov     eax, 0AD2h
0x14006a339  mov     [rbp+20h+arg_38], ax
0x14006a33d  lea     rax, [rbp+20h+arg_18]
0x14006a341  mov     [rsp+90h], rax
0x14006a349  lea     rax, [rbp+20h+var_98]
0x14006a34d  mov     [rsp+140h+var_B8], rax
0x14006a355  lea     rax, [rbp+20h+var_94]
0x14006a359  mov     [rsp+140h+var_C0], rax
0x14006a361  lea     rax, [rbp+20h+var_90]
0x14006a365  mov     [rsp+140h+var_C8], rax
0x14006a36a  lea     rax, [rbp+20h+var_8C]
0x14006a36e  mov     [rsp+140h+var_D0], rax
0x14006a373  lea     rax, [rbp+20h+var_88]
0x14006a377  mov     [rsp+140h+var_D8], rax
0x14006a37c  lea     rax, [rbp+20h+var_84]
0x14006a380  mov     [rsp+140h+var_E0], rax
0x14006a385  lea     rax, [rbp+20h+var_80]
0x14006a389  mov     [rsp+140h+var_E8], rax
0x14006a38e  lea     rax, [rbp+20h+var_7C]
0x14006a392  mov     [rsp+140h+var_F0], rax
0x14006a397  lea     rax, [rbp+20h+P]
0x14006a39b  mov     [rsp+140h+var_F8], rax
0x14006a3a0  lea     rax, [rbp+20h+var_60]
0x14006a3a4  mov     [rsp+140h+var_100], rax
0x14006a3a9  lea     rax, [rbp+20h+var_70]
0x14006a3ad  mov     [rsp+140h+var_108], rax
0x14006a3b2  lea     rax, [rbp+20h+arg_38]
0x14006a3b6  mov     [rsp+140h+var_110], rax
0x14006a3bb  lea     rax, [rbp+20h+var_A0]
0x14006a3bf  mov     [rsp+140h+var_118], rax
0x14006a3c4  lea     rax, [rbp+20h+var_68]
0x14006a3c8  mov     [rsp+140h+var_120], rax
0x14006a3cd  mov     [rbp+20h+var_68], r15
0x14006a3d1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@4444444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14006a3d6  test    r12, r12
0x14006a3d9  jz      loc_14006A526
0x14006a3df  xor     edx, edx; Tag
0x14006a3e1  mov     rcx, r12; P
0x14006a3e4  call    cs:__imp_ExFreePoolWithTag
0x14006a3eb  nop     dword ptr [rax+rax+00h]
0x14006a3f0  jmp     loc_14006A526
0x14006a3f5  mov     r8, 61E00210AE7h; struct UnionFs::StackEventTracer *
0x14006a3ff  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a404  mov     eax, cs:dword_14009E178
0x14006a40a  cmp     eax, 2
0x14006a40d  jbe     loc_14006A526
0x14006a413  mov     eax, [rsi+18h]
0x14006a416  lea     rdx, dword_140099D8C
0x14006a41d  mov     dword ptr [rbp+20h+arg_18], eax
0x14006a420  mov     eax, [rsi+14h]
0x14006a423  mov     dword ptr [rbp+20h+var_A0], eax
0x14006a426  mov     eax, [rsi+10h]
0x14006a429  mov     dword ptr [rbp+20h+P], eax
0x14006a42c  mov     eax, [rsi+0Ch]
0x14006a42f  mov     [rbp+20h+var_7C], eax
0x14006a432  mov     eax, [rsi+8]
0x14006a435  mov     [rbp+20h+var_80], eax
0x14006a438  mov     eax, [rsi+4]
0x14006a43b  mov     [rbp+20h+var_84], eax
0x14006a43e  mov     eax, [rsi]
0x14006a440  mov     [rbp+20h+var_88], eax
0x14006a443  mov     eax, dword ptr [rbp+20h+arg_20]
0x14006a446  mov     [rbp+20h+var_8C], eax
0x14006a449  mov     eax, [rbp+20h+arg_8]
0x14006a44c  mov     [rbp+20h+var_90], eax
0x14006a44f  mov     eax, [rbp+20h+arg_0]
0x14006a452  mov     [rbp+20h+var_94], eax
0x14006a455  mov     eax, 0AE7h
0x14006a45a  mov     [rbp+20h+arg_38], ax
0x14006a45e  lea     rax, [rbp+20h+arg_18]
0x14006a462  mov     [rsp+140h+var_B8], rax
0x14006a46a  lea     rax, [rbp+20h+var_A0]
0x14006a46e  mov     [rsp+140h+var_C0], rax
0x14006a476  lea     rax, [rbp+20h+P]
0x14006a47a  mov     [rsp+140h+var_C8], rax
0x14006a47f  lea     rax, [rbp+20h+var_7C]
0x14006a483  mov     [rsp+140h+var_D0], rax
0x14006a488  lea     rax, [rbp+20h+var_80]
0x14006a48c  mov     [rsp+140h+var_D8], rax
0x14006a491  lea     rax, [rbp+20h+var_84]
0x14006a495  mov     [rsp+140h+var_E0], rax
0x14006a49a  lea     rax, [rbp+20h+var_88]
0x14006a49e  mov     [rsp+140h+var_E8], rax
0x14006a4a3  lea     rax, [rbp+20h+var_8C]
0x14006a4a7  mov     [rsp+140h+var_F0], rax
0x14006a4ac  lea     rax, [rbp+20h+var_90]
0x14006a4b0  mov     [rsp+140h+var_F8], rax
0x14006a4b5  lea     rax, [rbp+20h+var_94]
0x14006a4b9  mov     [rsp+140h+var_100], rax
0x14006a4be  lea     rax, [rbp+20h+var_68]
0x14006a4c2  mov     [rsp+140h+var_108], rax
0x14006a4c7  lea     rax, [rbp+20h+arg_38]
0x14006a4cb  mov     [rsp+140h+var_110], rax
0x14006a4d0  lea     rax, [rbp+20h+var_98]
0x14006a4d4  mov     [rsp+140h+var_118], rax
0x14006a4d9  lea     rax, [rbp+20h+var_70]
0x14006a4dd  mov     [rsp+140h+var_120], rax
0x14006a4e2  mov     [rbp+20h+var_68], r13
0x14006a4e6  mov     [rbp+20h+var_98], 61Eh
0x14006a4ed  mov     [rbp+20h+var_70], r15
0x14006a4f1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$07@@4444444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14006a4f6  jmp     short loc_14006A526
0x14006a4f8  test    r14d, r14d
0x14006a4fb  jns     short loc_14006A561
0x14006a4fd  mov     rdx, qword ptr [rbp+20h+arg_30]; int
0x14006a501  lea     rax, aApiIochecklink; "API: IoCheckLinkShareAccess"
0x14006a508  lea     r9, aUnionfsUtilsCh_0; "UnionFs::Utils::CheckShareAccess"
0x14006a50f  mov     [rsp+140h+var_120], rax; char *
0x14006a514  mov     r8, 22D00210AEDh; struct UnionFs::StackEventTracer *
0x14006a51e  mov     ecx, r14d; this
0x14006a521  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a526  test    rbx, rbx
0x14006a529  jz      short loc_14006A546
0x14006a52b  mov     rcx, rbx; Resource
0x14006a52e  call    cs:__imp_ExReleaseResourceLite
0x14006a535  nop     dword ptr [rax+rax+00h]
0x14006a53a  call    cs:__imp_KeLeaveCriticalRegion
0x14006a541  nop     dword ptr [rax+rax+00h]
0x14006a546  test    rdi, rdi
0x14006a549  jz      short loc_14006A55C
0x14006a54b  xor     edx, edx; Tag
0x14006a54d  mov     rcx, rdi; P
0x14006a550  call    cs:__imp_ExFreePoolWithTag
0x14006a557  nop     dword ptr [rax+rax+00h]
0x14006a55c  mov     eax, r14d
0x14006a55f  jmp     short loc_14006A599
0x14006a561  test    rbx, rbx
0x14006a564  jz      short loc_14006A581
0x14006a566  mov     rcx, rbx; Resource
0x14006a569  call    cs:__imp_ExReleaseResourceLite
0x14006a570  nop     dword ptr [rax+rax+00h]
0x14006a575  call    cs:__imp_KeLeaveCriticalRegion
0x14006a57c  nop     dword ptr [rax+rax+00h]
0x14006a581  test    rdi, rdi
0x14006a584  jz      short loc_14006A597
0x14006a586  xor     edx, edx; Tag
0x14006a588  mov     rcx, rdi; P
0x14006a58b  call    cs:__imp_ExFreePoolWithTag
0x14006a592  nop     dword ptr [rax+rax+00h]
0x14006a597  xor     eax, eax
  ... truncated ...
```
