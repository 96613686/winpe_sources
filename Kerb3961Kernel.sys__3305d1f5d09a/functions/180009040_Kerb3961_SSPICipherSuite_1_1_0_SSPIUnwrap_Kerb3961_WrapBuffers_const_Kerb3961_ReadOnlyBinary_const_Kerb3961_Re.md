# Kerb3961::SSPICipherSuite<1,1,0>::SSPIUnwrap(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180009040`
- end: `0x1800092f6`
- name: `?SSPIUnwrap@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UVerifyMICResult@Kerb3961@@$1??$SingleGetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UVerifyMICResult@Kerb3961@@$0M@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@11_N2@Z`
- size: `694`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001ff4`
- `0x1800037e0`
- `0x180003a38`
- `0x180006f6c`
- `0x180009040`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`
- `0x180012300`

## string_xrefs

- `0x180009078`: `combinedBuffer`
- `0x1800090c0`: `completeWrapToken`
- `0x18000928f`: `result.outputMessage.length == effectiveInput.length + ((compatFixes == GssApiCompatibilityFixes::RC4) ? trailerBuffer.length : 0)`

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
  __int64 v20; // rcx
  const unsigned __int16 *v21; // rdx
  __int64 v22; // rdi
  int v23; // r8d
  char *v24; // rcx
  int v25; // eax
  __int64 v26; // rdi
  char *v27; // rsi
  __int64 v28; // r14
  char *v29; // rcx
  __int64 v31; // [rsp+40h] [rbp-99h]
  char *Src; // [rsp+48h] [rbp-91h]
  int v33; // [rsp+50h] [rbp-89h]
  __int64 v34; // [rsp+58h] [rbp-81h]
  unsigned int v35; // [rsp+60h] [rbp-79h]
  char v36; // [rsp+64h] [rbp-75h]
  char v37[8]; // [rsp+68h] [rbp-71h] BYREF
  __int64 v38; // [rsp+70h] [rbp-69h]
  char *v39; // [rsp+78h] [rbp-61h]
  char v40[8]; // [rsp+80h] [rbp-59h] BYREF
  __int64 v41; // [rsp+88h] [rbp-51h]
  char *v42; // [rsp+90h] [rbp-49h]
  char v43[8]; // [rsp+98h] [rbp-41h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-39h]
  char *v45; // [rsp+A8h] [rbp-31h]
  char v46[8]; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-21h]

  Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(v37, a3);
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
      Kerb3961Free(v20);
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
    Kerb3961Free(v47);
  if ( v44 )
    Kerb3961Free(v44);
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
        memmove(*(void **)(v26 + 8), v27, *(_QWORD *)v26);
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
  Kerb3961Free(v29);
LABEL_31:
  if ( v41 )
    Kerb3961Free(v41);
LABEL_33:
  if ( v38 )
    Kerb3961Free(v38);
  return a2;
}

```

## disassembly

```asm
0x180009040  push    rbp
0x180009042  push    rbx
0x180009043  push    rsi
0x180009044  push    rdi
0x180009045  push    r12
0x180009047  push    r14
0x180009049  push    r15
0x18000904b  lea     rbp, [rsp-7]
0x180009050  sub     rsp, 0E0h
0x180009057  mov     rbx, rdx
0x18000905a  mov     r12, rcx
0x18000905d  mov     rdx, r8
0x180009060  lea     rcx, [rbp+37h+var_A8]
0x180009064  mov     r15, r9
0x180009067  mov     r14, r8
0x18000906a  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x18000906f  mov     edi, dword ptr [rbp+37h+var_98]
0x180009072  test    edi, edi
0x180009074  jns     short loc_180009092
0x180009076  mov     edx, edi; char *
0x180009078  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x18000907f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009084  xorps   xmm0, xmm0
0x180009087  movups  xmmword ptr [rbx], xmm0
0x18000908a  mov     [rbx+0Ch], edi
0x18000908d  jmp     loc_1800092C5
0x180009092  cmp     edi, 0FFh
0x180009098  jnz     short loc_1800090A0
0x18000909a  mov     rsi, [r14+8]
0x18000909e  jmp     short loc_1800090A4
0x1800090a0  lea     rsi, [rbp+37h+var_A8]
0x1800090a4  mov     r9, [rbp+37h+arg_20]
0x1800090a8  lea     rcx, [rbp+37h+var_90]
0x1800090ac  mov     r8, rsi
0x1800090af  mov     rdx, r15
0x1800090b2  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800090b7  mov     edi, dword ptr [rbp+37h+var_80]
0x1800090ba  test    edi, edi
0x1800090bc  jns     short loc_1800090DA
0x1800090be  mov     edx, edi; char *
0x1800090c0  lea     rcx, aCompletewrapto; "completeWrapToken"
0x1800090c7  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800090cc  xorps   xmm0, xmm0
0x1800090cf  movups  xmmword ptr [rbx], xmm0
0x1800090d2  mov     [rbx+0Ch], edi
0x1800090d5  jmp     loc_1800092B7
0x1800090da  xorps   xmm0, xmm0
0x1800090dd  mov     [rbp+37h+var_AC], 0
0x1800090e4  mov     r15d, 0C0000001h
0x1800090ea  mov     [rsp+110h+var_D0], 0
0x1800090f3  mov     r8, r14
0x1800090f6  mov     dword ptr [rsp+110h+var_C0], r15d
0x1800090fb  lea     rdx, [rbp+37h+var_78]
0x1800090ff  mov     [rsp+110h+Src], 0
0x180009108  movdqu  xmmword ptr [rsp+110h+var_C0+4], xmm0
0x18000910e  call    ?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x180009113  mov     edi, dword ptr [rbp+37h+var_68]
0x180009116  test    edi, edi
0x180009118  jns     short loc_180009148
0x18000911a  mov     edx, edi; char *
0x18000911c  lea     rcx, aAuthbuffer; "authBuffer"
0x180009123  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009128  mov     rcx, [rbp+37h+var_70]
0x18000912c  xorps   xmm0, xmm0
0x18000912f  movups  xmmword ptr [rbx], xmm0
0x180009132  mov     [rbx+0Ch], edi
0x180009135  test    rcx, rcx
0x180009138  jz      loc_1800092A8
0x18000913e  call    Kerb3961Free
0x180009143  jmp     loc_1800092A8
0x180009148  mov     cl, [rbp+37h+arg_38]
0x18000914b  lea     r9, [rbp+37h+var_78]
0x18000914f  mov     rax, [r12]
0x180009153  lea     r8, [rbp+37h+var_90]
0x180009157  mov     [rsp+110h+var_E0], cl
0x18000915b  lea     rdx, [rbp+37h+var_60]
0x18000915f  mov     cl, [rbp+37h+arg_30]
0x180009162  mov     [rsp+110h+var_E8], cl
0x180009166  mov     rcx, [rbp+37h+arg_28]
0x18000916a  mov     rax, [rax+168h]
0x180009171  mov     [rsp+110h+var_F0], rcx
0x180009176  mov     rcx, r12
0x180009179  call    _guard_dispatch_icall
0x18000917e  mov     rcx, [rsp+110h+Src]
0x180009183  mov     rdi, rax
0x180009186  test    rcx, rcx
0x180009189  jz      short loc_180009190
0x18000918b  call    Kerb3961Free
0x180009190  mov     rcx, [rdi]
0x180009193  mov     [rsp+110h+var_D0], rcx
0x180009198  mov     rcx, [rdi+8]
0x18000919c  mov     qword ptr [rdi], 0
0x1800091a3  mov     [rsp+110h+Src], rcx
0x1800091a8  mov     eax, [rdi+10h]
0x1800091ab  mov     qword ptr [rdi+8], 0
0x1800091b3  mov     dword ptr [rsp+110h+var_C0], eax
0x1800091b7  mov     [rdi+10h], r15d
0x1800091bb  mov     rax, [rdi+18h]
0x1800091bf  mov     rcx, [rbp+37h+var_58]
0x1800091c3  mov     [rsp+58h], rax
0x1800091c8  mov     eax, [rdi+20h]
0x1800091cb  mov     [rbp-79h], eax
0x1800091ce  mov     al, [rdi+24h]
0x1800091d1  mov     byte ptr [rbp+37h+var_AC], al
0x1800091d4  test    rcx, rcx
0x1800091d7  jz      short loc_1800091DE
0x1800091d9  call    Kerb3961Free
0x1800091de  mov     rcx, [rbp+37h+var_70]
0x1800091e2  test    rcx, rcx
0x1800091e5  jz      short loc_1800091EC
0x1800091e7  call    Kerb3961Free
0x1800091ec  mov     edi, dword ptr [rsp+110h+var_C0]
0x1800091f0  test    edi, edi
0x1800091f2  jns     short loc_180009210
0x1800091f4  mov     edx, edi; char *
0x1800091f6  lea     rcx, aResult; "result"
0x1800091fd  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009202  xorps   xmm0, xmm0
0x180009205  movups  xmmword ptr [rbx], xmm0
0x180009208  mov     [rbx+0Ch], edi
0x18000920b  jmp     loc_1800092A8
0x180009210  cmp     byte ptr [rbp+37h+var_AC], 0
0x180009214  jnz     short loc_180009227
0x180009216  cmp     dword ptr [rbp-79h], 0
0x18000921a  jnz     loc_1800092E9
0x180009220  mov     dword ptr [rbp-79h], 80000001h
0x180009227  mov     rax, [rsi]
0x18000922a  cmp     [rsp+110h+var_D0], rax
0x18000922f  jnz     short loc_18000928F
0x180009231  mov     rax, [r14]
0x180009234  mov     rdi, [r14+8]
0x180009238  mov     rsi, [rsp+110h+Src]
0x18000923d  lea     rcx, [rax+rax*2]
0x180009241  lea     r14, [rdi+rcx*8]
0x180009245  cmp     rdi, r14
0x180009248  jz      short loc_180009270
0x18000924a  cmp     byte ptr [rdi+10h], 0
0x18000924e  jz      short loc_180009262
0x180009250  mov     r8, [rdi]; Size
0x180009253  mov     rdx, rsi; Src
0x180009256  mov     rcx, [rdi+8]; void *
0x18000925a  call    memmove
0x18000925f  add     rsi, [rdi]
0x180009262  add     rdi, 18h
0x180009266  cmp     rdi, r14
0x180009269  jnz     short loc_18000924A
0x18000926b  mov     rsi, [rsp+110h+Src]
0x180009270  mov     rax, [rsp+58h]
0x180009275  mov     [rbx], rax
0x180009278  mov     eax, [rbp-79h]
0x18000927b  mov     [rbx+8], eax
0x18000927e  mov     dword ptr [rbx+0Ch], 0
0x180009285  test    rsi, rsi
0x180009288  jz      short loc_1800092B7
0x18000928a  mov     rcx, rsi
0x18000928d  jmp     short loc_1800092B2
0x18000928f  lea     rcx, aResultOutputme; "result.outputMessage.length == effectiv"...
0x180009296  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000929b  xorps   xmm0, xmm0
0x18000929e  movups  xmmword ptr [rbx], xmm0
0x1800092a1  mov     dword ptr [rbx+0Ch], 8009030Fh
0x1800092a8  mov     rcx, [rsp+110h+Src]
0x1800092ad  test    rcx, rcx
0x1800092b0  jz      short loc_1800092B7
0x1800092b2  call    Kerb3961Free
0x1800092b7  mov     rcx, [rbp+37h+var_88]
0x1800092bb  test    rcx, rcx
0x1800092be  jz      short loc_1800092C5
0x1800092c0  call    Kerb3961Free
0x1800092c5  mov     rcx, [rbp+37h+var_A0]
0x1800092c9  test    rcx, rcx
0x1800092cc  jz      short loc_1800092D3
0x1800092ce  call    Kerb3961Free
0x1800092d3  mov     rax, rbx
0x1800092d6  add     rsp, 0E0h
0x1800092dd  pop     r15
0x1800092df  pop     r14
0x1800092e1  pop     r12
0x1800092e3  pop     rdi
0x1800092e4  pop     rsi
0x1800092e5  pop     rbx
0x1800092e6  pop     rbp
0x1800092e7  retn
0x1800092e9  lea     rcx, aGssApiCannotHa; "GSS-API cannot have a QOP when conf = f"...
0x1800092f0  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
