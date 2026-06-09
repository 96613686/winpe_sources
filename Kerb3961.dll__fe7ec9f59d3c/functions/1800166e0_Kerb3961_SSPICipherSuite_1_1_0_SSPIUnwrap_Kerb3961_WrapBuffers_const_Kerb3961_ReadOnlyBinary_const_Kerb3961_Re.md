# Kerb3961::SSPICipherSuite<1,1,0>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800166e0`
- end: `0x1800169a3`
- name: `?SSPIUnwrap@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@11_N2@Z`
- size: `707`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180004cf4`
- `0x180006ee0`
- `0x180010f4c`
- `0x1800166e0`
- `0x18001d360`
- `0x18001e010`

## string_xrefs

- `0x180016718`: `combinedBuffer`
- `0x180016760`: `completeWrapToken`
- `0x180016937`: `result.outputMessage.length == effectiveInput.length + ((compatFixes == GssApiCompatibilityFixes::RC4) ? trailerBuffer.length : 0)`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,0>::SSPIUnwrap(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        char a8)
{
  int v12; // r8d
  int v13; // edi
  char *v14; // rsi
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // edi
  int v18; // r8d
  int v19; // edi
  void *v20; // rcx
  const unsigned __int16 *v21; // rdx
  __int64 v22; // rdi
  int v23; // r8d
  char *v24; // rcx
  int v25; // eax
  __int64 v26; // rdi
  char *v27; // rsi
  __int64 v28; // r14
  void *v29; // rcx
  __int64 v31; // [rsp+40h] [rbp-99h]
  char *Src; // [rsp+48h] [rbp-91h]
  int v33; // [rsp+50h] [rbp-89h]
  __int64 v34; // [rsp+58h] [rbp-81h]
  unsigned int v35; // [rsp+60h] [rbp-79h]
  char v36; // [rsp+64h] [rbp-75h]
  char v37[8]; // [rsp+68h] [rbp-71h] BYREF
  void *v38; // [rsp+70h] [rbp-69h]
  char *v39; // [rsp+78h] [rbp-61h]
  char v40[8]; // [rsp+80h] [rbp-59h] BYREF
  void *v41; // [rsp+88h] [rbp-51h]
  char *v42; // [rsp+90h] [rbp-49h]
  char v43[8]; // [rsp+98h] [rbp-41h] BYREF
  void *v44; // [rsp+A0h] [rbp-39h]
  char *v45; // [rsp+A8h] [rbp-31h]
  char v46[8]; // [rsp+B0h] [rbp-29h] BYREF
  void *v47; // [rsp+B8h] [rbp-21h]

  Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers((__int64)v37, a3);
  v13 = (int)v39;
  if ( (int)v39 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"combinedBuffer",
      (const char *)(unsigned int)v39,
      v12);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = v13;
    goto LABEL_33;
  }
  if ( (_DWORD)v39 == 255 )
    v14 = (char *)a3[1];
  else
    v14 = v37;
  Kerb3961::Concatenate(v40, a4, v14, a5);
  v17 = (int)v42;
  if ( (int)v42 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"completeWrapToken",
      (const char *)(unsigned int)v42,
      v16);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = v17;
    goto LABEL_31;
  }
  Src = 0;
  Kerb3961::SSPICipherSuite<1,1,0>::CoalesceAuthWrapBuffers(v15, v43, a3);
  v19 = (int)v45;
  if ( (int)v45 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"authBuffer",
      (const char *)(unsigned int)v45,
      v18);
    v20 = v44;
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = v19;
    if ( v20 )
      operator delete(v20, 0);
LABEL_29:
    v29 = Src;
    if ( !Src )
      goto LABEL_31;
    goto LABEL_30;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, char *, char *, char *, __int64, char, char))(*(_QWORD *)a1 + 360LL))(
          a1,
          v46,
          v40,
          v43,
          a6,
          a7,
          a8);
  v31 = *(_QWORD *)v22;
  v24 = *(char **)(v22 + 8);
  *(_QWORD *)v22 = 0;
  Src = v24;
  v25 = *(_DWORD *)(v22 + 16);
  *(_QWORD *)(v22 + 8) = 0;
  v33 = v25;
  *(_DWORD *)(v22 + 16) = -1073741823;
  v34 = *(_QWORD *)(v22 + 24);
  v35 = *(_DWORD *)(v22 + 32);
  v36 = *(_BYTE *)(v22 + 36);
  if ( v47 )
    operator delete(v47, 0);
  if ( v44 )
    operator delete(v44, 0);
  if ( v33 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"result", (const char *)(unsigned int)v33, v23);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = v33;
    goto LABEL_29;
  }
  if ( !v36 )
  {
    if ( v35 )
      Kerb3961::ConsistencyFail((Kerb3961 *)L"GSS-API cannot have a QOP when conf = false", v21);
    v35 = -2147483647;
  }
  if ( v31 != *(_QWORD *)v14 )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"result.outputMessage.length == effectiveInput.length + ((compatFixes == GssApiCompati"
                                   "bilityFixes::RC4) ? trailerBuffer.length : 0)",
      (const char *)v21);
    *(_OWORD *)a2 = 0;
    *(_DWORD *)(a2 + 12) = -2146893041;
    goto LABEL_29;
  }
  v26 = a3[1];
  v27 = Src;
  v28 = v26 + 24LL * *a3;
  if ( v26 != v28 )
  {
    do
    {
      if ( *(_BYTE *)(v26 + 16) )
      {
        memcpy_0(*(void **)(v26 + 8), v27, *(_QWORD *)v26);
        v27 += *(_QWORD *)v26;
      }
      v26 += 24;
    }
    while ( v26 != v28 );
    v27 = Src;
  }
  *(_QWORD *)a2 = v34;
  *(_QWORD *)(a2 + 8) = v35;
  if ( !v27 )
    goto LABEL_31;
  v29 = v27;
LABEL_30:
  operator delete(v29, 0);
LABEL_31:
  if ( v41 )
    operator delete(v41, 0);
LABEL_33:
  if ( v38 )
    operator delete(v38, 0);
  return a2;
}

```

## disassembly

```asm
0x1800166e0  push    rbp
0x1800166e2  push    rbx
0x1800166e3  push    rsi
0x1800166e4  push    rdi
0x1800166e5  push    r12
0x1800166e7  push    r14
0x1800166e9  push    r15
0x1800166eb  lea     rbp, [rsp-7]
0x1800166f0  sub     rsp, 0E0h
0x1800166f7  mov     rbx, rdx
0x1800166fa  mov     r12, rcx
0x1800166fd  mov     rdx, r8
0x180016700  lea     rcx, [rbp+37h+var_A8]
0x180016704  mov     r15, r9
0x180016707  mov     r14, r8
0x18001670a  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x18001670f  mov     edi, dword ptr [rbp+37h+var_98]
0x180016712  test    edi, edi
0x180016714  jns     short loc_180016732
0x180016716  mov     edx, edi; char *
0x180016718  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x18001671f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180016724  xorps   xmm0, xmm0
0x180016727  movups  xmmword ptr [rbx], xmm0
0x18001672a  mov     [rbx+0Ch], edi
0x18001672d  jmp     loc_180016971
0x180016732  cmp     edi, 0FFh
0x180016738  jnz     short loc_180016740
0x18001673a  mov     rsi, [r14+8]
0x18001673e  jmp     short loc_180016744
0x180016740  lea     rsi, [rbp+37h+var_A8]
0x180016744  mov     r9, [rbp+37h+arg_20]
0x180016748  lea     rcx, [rbp+37h+var_90]
0x18001674c  mov     r8, rsi
0x18001674f  mov     rdx, r15
0x180016752  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180016757  mov     edi, dword ptr [rbp+37h+var_80]
0x18001675a  test    edi, edi
0x18001675c  jns     short loc_18001677A
0x18001675e  mov     edx, edi; char *
0x180016760  lea     rcx, aCompletewrapto; "completeWrapToken"
0x180016767  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001676c  xorps   xmm0, xmm0
0x18001676f  movups  xmmword ptr [rbx], xmm0
0x180016772  mov     [rbx+0Ch], edi
0x180016775  jmp     loc_180016961
0x18001677a  xorps   xmm0, xmm0
0x18001677d  mov     [rbp+37h+var_AC], 0
0x180016784  mov     r15d, 0C0000001h
0x18001678a  mov     [rsp+110h+var_D0], 0
0x180016793  mov     r8, r14
0x180016796  mov     dword ptr [rsp+110h+var_C0], r15d
0x18001679b  lea     rdx, [rbp+37h+var_78]
0x18001679f  mov     [rsp+110h+Src], 0
0x1800167a8  movdqu  xmmword ptr [rsp+110h+var_C0+4], xmm0
0x1800167ae  call    ?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x1800167b3  mov     edi, dword ptr [rbp+37h+var_68]
0x1800167b6  test    edi, edi
0x1800167b8  jns     short loc_1800167EA
0x1800167ba  mov     edx, edi; char *
0x1800167bc  lea     rcx, aAuthbuffer; "authBuffer"
0x1800167c3  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800167c8  mov     rcx, [rbp+37h+var_70]; void *
0x1800167cc  xorps   xmm0, xmm0
0x1800167cf  movups  xmmword ptr [rbx], xmm0
0x1800167d2  mov     [rbx+0Ch], edi
0x1800167d5  test    rcx, rcx
0x1800167d8  jz      loc_180016950
0x1800167de  xor     edx, edx; struct std::nothrow_t *
0x1800167e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800167e5  jmp     loc_180016950
0x1800167ea  mov     cl, [rbp+37h+arg_38]
0x1800167ed  lea     r9, [rbp+37h+var_78]
0x1800167f1  mov     rax, [r12]
0x1800167f5  lea     r8, [rbp+37h+var_90]
0x1800167f9  mov     [rsp+110h+var_E0], cl
0x1800167fd  lea     rdx, [rbp+37h+var_60]
0x180016801  mov     cl, [rbp+37h+arg_30]
0x180016804  mov     [rsp+110h+var_E8], cl
0x180016808  mov     rcx, [rbp+37h+arg_28]
0x18001680c  mov     rax, [rax+168h]
0x180016813  mov     [rsp+110h+var_F0], rcx
0x180016818  mov     rcx, r12
0x18001681b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016820  mov     rcx, [rsp+110h+Src]; void *
0x180016825  mov     rdi, rax
0x180016828  test    rcx, rcx
0x18001682b  jz      short loc_180016834
0x18001682d  xor     edx, edx; struct std::nothrow_t *
0x18001682f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016834  mov     rcx, [rdi]
0x180016837  mov     [rsp+110h+var_D0], rcx
0x18001683c  mov     rcx, [rdi+8]
0x180016840  mov     qword ptr [rdi], 0
0x180016847  mov     [rsp+110h+Src], rcx
0x18001684c  mov     eax, [rdi+10h]
0x18001684f  mov     qword ptr [rdi+8], 0
0x180016857  mov     dword ptr [rsp+110h+var_C0], eax
0x18001685b  mov     [rdi+10h], r15d
0x18001685f  mov     rax, [rdi+18h]
0x180016863  mov     rcx, [rbp+37h+var_58]; void *
0x180016867  mov     [rsp+58h], rax
0x18001686c  mov     eax, [rdi+20h]
0x18001686f  mov     [rbp-79h], eax
0x180016872  mov     al, [rdi+24h]
0x180016875  mov     byte ptr [rbp+37h+var_AC], al
0x180016878  test    rcx, rcx
0x18001687b  jz      short loc_180016884
0x18001687d  xor     edx, edx; struct std::nothrow_t *
0x18001687f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016884  mov     rcx, [rbp+37h+var_70]; void *
0x180016888  test    rcx, rcx
0x18001688b  jz      short loc_180016894
0x18001688d  xor     edx, edx; struct std::nothrow_t *
0x18001688f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016894  mov     edi, dword ptr [rsp+110h+var_C0]
0x180016898  test    edi, edi
0x18001689a  jns     short loc_1800168B8
0x18001689c  mov     edx, edi; char *
0x18001689e  lea     rcx, aResult; "result"
0x1800168a5  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800168aa  xorps   xmm0, xmm0
0x1800168ad  movups  xmmword ptr [rbx], xmm0
0x1800168b0  mov     [rbx+0Ch], edi
0x1800168b3  jmp     loc_180016950
0x1800168b8  cmp     byte ptr [rbp+37h+var_AC], 0
0x1800168bc  jnz     short loc_1800168CF
0x1800168be  cmp     dword ptr [rbp-79h], 0
0x1800168c2  jnz     loc_180016996
0x1800168c8  mov     dword ptr [rbp-79h], 80000001h
0x1800168cf  mov     rax, [rsi]
0x1800168d2  cmp     [rsp+110h+var_D0], rax
0x1800168d7  jnz     short loc_180016937
0x1800168d9  mov     rax, [r14]
0x1800168dc  mov     rdi, [r14+8]
0x1800168e0  mov     rsi, [rsp+110h+Src]
0x1800168e5  lea     rcx, [rax+rax*2]
0x1800168e9  lea     r14, [rdi+rcx*8]
0x1800168ed  cmp     rdi, r14
0x1800168f0  jz      short loc_180016918
0x1800168f2  cmp     byte ptr [rdi+10h], 0
0x1800168f6  jz      short loc_18001690A
0x1800168f8  mov     r8, [rdi]; Size
0x1800168fb  mov     rdx, rsi; Src
0x1800168fe  mov     rcx, [rdi+8]; void *
0x180016902  call    memcpy_0
0x180016907  add     rsi, [rdi]
0x18001690a  add     rdi, 18h
0x18001690e  cmp     rdi, r14
0x180016911  jnz     short loc_1800168F2
0x180016913  mov     rsi, [rsp+110h+Src]
0x180016918  mov     rax, [rsp+58h]
0x18001691d  mov     [rbx], rax
0x180016920  mov     eax, [rbp-79h]
0x180016923  mov     [rbx+8], eax
0x180016926  mov     dword ptr [rbx+0Ch], 0
0x18001692d  test    rsi, rsi
0x180016930  jz      short loc_180016961
0x180016932  mov     rcx, rsi
0x180016935  jmp     short loc_18001695A
0x180016937  lea     rcx, aResultOutputme; "result.outputMessage.length == effectiv"...
0x18001693e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180016943  xorps   xmm0, xmm0
0x180016946  movups  xmmword ptr [rbx], xmm0
0x180016949  mov     dword ptr [rbx+0Ch], 8009030Fh
0x180016950  mov     rcx, [rsp+110h+Src]; void *
0x180016955  test    rcx, rcx
0x180016958  jz      short loc_180016961
0x18001695a  xor     edx, edx; struct std::nothrow_t *
0x18001695c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016961  mov     rcx, [rbp+37h+var_88]; void *
0x180016965  test    rcx, rcx
0x180016968  jz      short loc_180016971
0x18001696a  xor     edx, edx; struct std::nothrow_t *
0x18001696c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016971  mov     rcx, [rbp+37h+var_A0]; void *
0x180016975  test    rcx, rcx
0x180016978  jz      short loc_180016981
0x18001697a  xor     edx, edx; struct std::nothrow_t *
0x18001697c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016981  mov     rax, rbx
0x180016984  add     rsp, 0E0h
0x18001698b  pop     r15
0x18001698d  pop     r14
0x18001698f  pop     r12
0x180016991  pop     rdi
0x180016992  pop     rsi
0x180016993  pop     rbx
0x180016994  pop     rbp
0x180016995  retn
0x180016996  lea     rcx, aGssApiCannotHa; "GSS-API cannot have a QOP when conf = f"...
0x18001699d  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
