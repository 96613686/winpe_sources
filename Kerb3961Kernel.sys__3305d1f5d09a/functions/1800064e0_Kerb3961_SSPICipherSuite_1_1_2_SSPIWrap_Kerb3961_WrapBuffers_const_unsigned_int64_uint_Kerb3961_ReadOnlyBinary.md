# Kerb3961::SSPICipherSuite<1,1,2>::SSPIWrap(Kerb3961::WrapBuffers const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x1800064e0`
- end: `0x180006744`
- name: `?SSPIWrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@_KIAEBUReadOnlyBinary@2@_N3PEA_K@Z`
- size: `612`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001e7c`
- `0x180001ff4`
- `0x1800022a8`
- `0x1800064e0`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`
- `0x180012300`

## string_xrefs

- `0x180006542`: `combinedBuffer`
- `0x1800065bb`: `combinedBuffer`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,2>::SSPIWrap(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        char a7,
        char a8,
        _QWORD *a9)
{
  int v12; // r8d
  int v13; // edi
  void *v14; // rcx
  _BYTE *v15; // r8
  __int64 v16; // rcx
  int v17; // r8d
  int v18; // edi
  _BYTE *v19; // r12
  int v20; // r8d
  int v21; // edi
  int v22; // r8d
  int v23; // r14d
  __int64 v24; // rcx
  __int64 v25; // rdi
  char *v26; // r15
  __int64 v27; // rsi
  __int64 v29; // [rsp+68h] [rbp-49h] BYREF
  __int64 v30; // [rsp+70h] [rbp-41h]
  char *v31; // [rsp+78h] [rbp-39h]
  _BYTE v32[8]; // [rsp+80h] [rbp-31h] BYREF
  void *Src; // [rsp+88h] [rbp-29h]
  char *v34; // [rsp+90h] [rbp-21h]
  _BYTE v35[8]; // [rsp+98h] [rbp-19h] BYREF
  void *v36; // [rsp+A0h] [rbp-11h]
  char *v37; // [rsp+A8h] [rbp-9h]

  if ( a9 )
    *a9 = 0;
  if ( a5 == -2147483647 )
  {
    Kerb3961::SSPICipherSuite<1,1,2>::CoalescePlainWrapBuffers(v35, a3);
    v13 = (int)v37;
    if ( (int)v37 >= 0 )
    {
      if ( (_DWORD)v37 == 255 )
        v15 = (_BYTE *)a3[1];
      else
        v15 = v35;
      (*(void (__fastcall **)(__int64, __int64, _BYTE *, __int64, __int64, char, char))(*(_QWORD *)a1 + 352LL))(
        a1,
        a2,
        v15,
        a4,
        a6,
        a7,
        a8);
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"combinedBuffer",
        (const char *)(unsigned int)v37,
        v12);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v13;
    }
    v14 = v36;
  }
  else
  {
    Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(v32, a3);
    v18 = (int)v34;
    if ( (int)v34 >= 0 )
    {
      if ( (_DWORD)v34 == 255 )
        v19 = (_BYTE *)a3[1];
      else
        v19 = v32;
      Kerb3961::SSPICipherSuite<1,1,2>::CoalesceAuthWrapBuffers(v16, v35, a3);
      v21 = (int)v37;
      if ( (int)v37 >= 0 )
      {
        (*(void (__fastcall **)(__int64, __int64 *, _BYTE *, _BYTE *, __int64, int, __int64, char, char, _QWORD *))(*(_QWORD *)a1 + 344LL))(
          a1,
          &v29,
          v19,
          v35,
          a4,
          a5,
          a6,
          a7,
          a8,
          a9);
        v23 = (int)v31;
        if ( (int)v31 >= 0 )
        {
          if ( (_DWORD)v34 != 255 )
          {
            v25 = a3[1];
            v26 = (char *)Src;
            v27 = v25 + 24LL * *a3;
            if ( v25 != v27 )
            {
              do
              {
                if ( *(_BYTE *)(v25 + 16) )
                {
                  memmove(*(void **)(v25 + 8), v26, *(_QWORD *)v25);
                  v26 += *(_QWORD *)v25;
                }
                v25 += 24;
              }
              while ( v25 != v27 );
              v23 = (int)v31;
            }
          }
          *(_QWORD *)a2 = v29;
          *(_QWORD *)(a2 + 8) = v30;
          *(_DWORD *)(a2 + 16) = v23;
          LODWORD(v31) = -1073741823;
          v29 = 0;
          v30 = 0;
        }
        else
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"result",
            (const char *)(unsigned int)v31,
            v22);
          v24 = v30;
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v23;
          if ( v24 )
            Kerb3961Free(v24);
        }
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"authBuffer",
          (const char *)(unsigned int)v37,
          v20);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v21;
      }
      if ( v36 )
        Kerb3961Free(v36);
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"combinedBuffer",
        (const char *)(unsigned int)v34,
        v17);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v18;
    }
    v14 = Src;
  }
  if ( v14 )
    Kerb3961Free(v14);
  return a2;
}

```

## disassembly

```asm
0x1800064e0  mov     rax, rsp
0x1800064e3  mov     [rax+10h], rbx
0x1800064e7  mov     [rax+20h], r9
0x1800064eb  mov     [rax+8], rcx
0x1800064ef  push    rbp
0x1800064f0  push    rsi
0x1800064f1  push    rdi
0x1800064f2  push    r12
0x1800064f4  push    r13
0x1800064f6  push    r14
0x1800064f8  push    r15
0x1800064fa  lea     rbp, [rax-3Fh]
0x1800064fe  sub     rsp, 0B0h
0x180006505  mov     r14, [rbp+37h+arg_40]
0x18000650c  xor     r15d, r15d
0x18000650f  mov     rsi, r8
0x180006512  mov     rbx, rdx
0x180006515  mov     r12, rcx
0x180006518  test    r14, r14
0x18000651b  jz      short loc_180006520
0x18000651d  mov     [r14], r15
0x180006520  mov     r13d, [rbp+37h+arg_20]
0x180006524  mov     rdx, rsi
0x180006527  cmp     r13d, 80000001h
0x18000652e  jnz     short loc_1800065A9
0x180006530  lea     rcx, [rbp+37h+var_50]
0x180006534  call    ?CoalescePlainWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,2>::CoalescePlainWrapBuffers(Kerb3961::WrapBuffers const &)
0x180006539  mov     edi, dword ptr [rbp+37h+var_40]
0x18000653c  test    edi, edi
0x18000653e  jns     short loc_180006561
0x180006540  mov     edx, edi; char *
0x180006542  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x180006549  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000654e  mov     [rbx], r15
0x180006551  mov     [rbx+8], r15
0x180006555  mov     [rbx+10h], edi
0x180006558  mov     rcx, [rbp+37h+var_48]
0x18000655c  jmp     loc_18000671B
0x180006561  mov     r15d, 0FFh
0x180006567  cmp     edi, r15d
0x18000656a  jnz     short loc_180006572
0x18000656c  mov     r8, [rsi+8]
0x180006570  jmp     short loc_180006576
0x180006572  lea     r8, [rbp+37h+var_50]
0x180006576  mov     cl, [rbp+37h+arg_38]
0x180006579  mov     rdx, rbx
0x18000657c  mov     rax, [r12]
0x180006580  mov     r9, [rbp+37h+arg_18]
0x180006584  mov     [rsp+0E0h+var_B0], cl
0x180006588  mov     cl, [rbp+37h+arg_30]
0x18000658b  mov     rax, [rax+160h]
0x180006592  mov     byte ptr [rsp+0E0h+var_B8], cl
0x180006596  mov     rcx, [rbp+37h+arg_28]
0x18000659a  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x18000659f  mov     rcx, r12
0x1800065a2  call    _guard_dispatch_icall
0x1800065a7  jmp     short loc_180006558
0x1800065a9  lea     rcx, [rbp+37h+var_68]
0x1800065ad  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x1800065b2  mov     edi, dword ptr [rbp+37h+var_58]
0x1800065b5  test    edi, edi
0x1800065b7  jns     short loc_1800065D6
0x1800065b9  mov     edx, edi; char *
0x1800065bb  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x1800065c2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800065c7  mov     [rbx], r15
0x1800065ca  mov     [rbx+8], r15
0x1800065ce  mov     [rbx+10h], edi
0x1800065d1  jmp     loc_180006717
0x1800065d6  mov     r15d, 0FFh
0x1800065dc  cmp     edi, r15d
0x1800065df  jnz     short loc_1800065E7
0x1800065e1  mov     r12, [rsi+8]
0x1800065e5  jmp     short loc_1800065EB
0x1800065e7  lea     r12, [rbp+37h+var_68]
0x1800065eb  mov     r8, rsi
0x1800065ee  lea     rdx, [rbp+37h+var_50]
0x1800065f2  call    ?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,2>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x1800065f7  mov     edi, dword ptr [rbp+37h+var_40]
0x1800065fa  test    edi, edi
0x1800065fc  jns     short loc_180006623
0x1800065fe  mov     edx, edi; char *
0x180006600  lea     rcx, aAuthbuffer; "authBuffer"
0x180006607  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000660c  mov     qword ptr [rbx], 0
0x180006613  mov     qword ptr [rbx+8], 0
0x18000661b  mov     [rbx+10h], edi
0x18000661e  jmp     loc_180006709
0x180006623  mov     cl, [rbp+37h+arg_38]
0x180006626  lea     r9, [rbp+37h+var_50]
0x18000662a  mov     r10, [rbp+37h+arg_0]
0x18000662e  lea     rdx, [rbp+37h+var_80]
0x180006632  mov     [rsp+48h], r14
0x180006637  mov     r8, r12
0x18000663a  mov     byte ptr [rsp+0E0h+var_A0], cl
0x18000663e  mov     cl, [rbp+37h+arg_30]
0x180006641  mov     rax, [r10]
0x180006644  mov     [rsp+0E0h+var_A8], cl
0x180006648  mov     rcx, [rbp+37h+arg_28]
0x18000664c  mov     qword ptr [rsp+0E0h+var_B0], rcx
0x180006651  mov     rcx, [rbp+37h+arg_18]
0x180006655  mov     rax, [rax+158h]
0x18000665c  mov     dword ptr [rsp+0E0h+var_B8], r13d
0x180006661  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x180006666  mov     rcx, r10
0x180006669  call    _guard_dispatch_icall
0x18000666e  mov     r14d, dword ptr [rbp+37h+var_70]
0x180006672  xor     r12d, r12d
0x180006675  test    r14d, r14d
0x180006678  jns     short loc_1800066A4
0x18000667a  mov     edx, r14d; char *
0x18000667d  lea     rcx, aResult; "result"
0x180006684  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006689  mov     rcx, [rbp+37h+var_78]
0x18000668d  mov     [rbx], r12
0x180006690  mov     [rbx+8], r12
0x180006694  mov     [rbx+10h], r14d
0x180006698  test    rcx, rcx
0x18000669b  jz      short loc_180006709
0x18000669d  call    Kerb3961Free
0x1800066a2  jmp     short loc_180006709
0x1800066a4  cmp     dword ptr [rbp+37h+var_58], r15d
0x1800066a8  jz      short loc_1800066E7
0x1800066aa  mov     rax, [rsi]
0x1800066ad  mov     rdi, [rsi+8]
0x1800066b1  mov     r15, [rbp+37h+Src]
0x1800066b5  lea     rcx, [rax+rax*2]
0x1800066b9  lea     rsi, [rdi+rcx*8]
0x1800066bd  cmp     rdi, rsi
0x1800066c0  jz      short loc_1800066E7
0x1800066c2  cmp     [rdi+10h], r12b
0x1800066c6  jz      short loc_1800066DA
0x1800066c8  mov     r8, [rdi]; Size
0x1800066cb  mov     rdx, r15; Src
0x1800066ce  mov     rcx, [rdi+8]; void *
0x1800066d2  call    memmove
0x1800066d7  add     r15, [rdi]
0x1800066da  add     rdi, 18h
0x1800066de  cmp     rdi, rsi
0x1800066e1  jnz     short loc_1800066C2
0x1800066e3  mov     r14d, dword ptr [rbp+37h+var_70]
0x1800066e7  mov     rax, [rbp+37h+var_80]
0x1800066eb  mov     [rbx], rax
0x1800066ee  mov     rax, [rbp+37h+var_78]
0x1800066f2  mov     [rbx+8], rax
0x1800066f6  mov     [rbx+10h], r14d
0x1800066fa  mov     dword ptr [rbp+37h+var_70], 0C0000001h
0x180006701  mov     [rbp+37h+var_80], r12
0x180006705  mov     [rbp+37h+var_78], r12
0x180006709  mov     rcx, [rbp+37h+var_48]
0x18000670d  test    rcx, rcx
0x180006710  jz      short loc_180006717
0x180006712  call    Kerb3961Free
0x180006717  mov     rcx, [rbp+37h+Src]
0x18000671b  test    rcx, rcx
0x18000671e  jz      short loc_180006725
0x180006720  call    Kerb3961Free
0x180006725  mov     rax, rbx
0x180006728  mov     rbx, [rsp+0E0h+arg_8]
0x180006730  add     rsp, 0B0h
0x180006737  pop     r15
0x180006739  pop     r14
0x18000673b  pop     r13
0x18000673d  pop     r12
0x18000673f  pop     rdi
0x180006740  pop     rsi
0x180006741  pop     rbp
0x180006742  retn
```
