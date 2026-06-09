# Kerb3961::SSPICipherSuite<1,1,0>::SSPIWrap(Kerb3961::WrapBuffers const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x180009300`
- end: `0x180009564`
- name: `?SSPIWrap@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@_KIAEBUReadOnlyBinary@2@_N3PEA_K@Z`
- size: `612`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001ff4`
- `0x1800022a8`
- `0x180006f6c`
- `0x180009300`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`
- `0x180012300`

## string_xrefs

- `0x180009362`: `combinedBuffer`
- `0x1800093db`: `combinedBuffer`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,0>::SSPIWrap(
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
      Kerb3961::SSPICipherSuite<1,1,0>::CoalesceAuthWrapBuffers(v16, v35, a3);
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
0x180009300  mov     rax, rsp
0x180009303  mov     [rax+10h], rbx
0x180009307  mov     [rax+20h], r9
0x18000930b  mov     [rax+8], rcx
0x18000930f  push    rbp
0x180009310  push    rsi
0x180009311  push    rdi
0x180009312  push    r12
0x180009314  push    r13
0x180009316  push    r14
0x180009318  push    r15
0x18000931a  lea     rbp, [rax-3Fh]
0x18000931e  sub     rsp, 0B0h
0x180009325  mov     r14, [rbp+37h+arg_40]
0x18000932c  xor     r15d, r15d
0x18000932f  mov     rsi, r8
0x180009332  mov     rbx, rdx
0x180009335  mov     r12, rcx
0x180009338  test    r14, r14
0x18000933b  jz      short loc_180009340
0x18000933d  mov     [r14], r15
0x180009340  mov     r13d, [rbp+37h+arg_20]
0x180009344  mov     rdx, rsi
0x180009347  cmp     r13d, 80000001h
0x18000934e  jnz     short loc_1800093C9
0x180009350  lea     rcx, [rbp+37h+var_50]
0x180009354  call    ?CoalescePlainWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,2>::CoalescePlainWrapBuffers(Kerb3961::WrapBuffers const &)
0x180009359  mov     edi, dword ptr [rbp+37h+var_40]
0x18000935c  test    edi, edi
0x18000935e  jns     short loc_180009381
0x180009360  mov     edx, edi; char *
0x180009362  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x180009369  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000936e  mov     [rbx], r15
0x180009371  mov     [rbx+8], r15
0x180009375  mov     [rbx+10h], edi
0x180009378  mov     rcx, [rbp+37h+var_48]
0x18000937c  jmp     loc_18000953B
0x180009381  mov     r15d, 0FFh
0x180009387  cmp     edi, r15d
0x18000938a  jnz     short loc_180009392
0x18000938c  mov     r8, [rsi+8]
0x180009390  jmp     short loc_180009396
0x180009392  lea     r8, [rbp+37h+var_50]
0x180009396  mov     cl, [rbp+37h+arg_38]
0x180009399  mov     rdx, rbx
0x18000939c  mov     rax, [r12]
0x1800093a0  mov     r9, [rbp+37h+arg_18]
0x1800093a4  mov     [rsp+0E0h+var_B0], cl
0x1800093a8  mov     cl, [rbp+37h+arg_30]
0x1800093ab  mov     rax, [rax+160h]
0x1800093b2  mov     byte ptr [rsp+0E0h+var_B8], cl
0x1800093b6  mov     rcx, [rbp+37h+arg_28]
0x1800093ba  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x1800093bf  mov     rcx, r12
0x1800093c2  call    _guard_dispatch_icall
0x1800093c7  jmp     short loc_180009378
0x1800093c9  lea     rcx, [rbp+37h+var_68]
0x1800093cd  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x1800093d2  mov     edi, dword ptr [rbp+37h+var_58]
0x1800093d5  test    edi, edi
0x1800093d7  jns     short loc_1800093F6
0x1800093d9  mov     edx, edi; char *
0x1800093db  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x1800093e2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800093e7  mov     [rbx], r15
0x1800093ea  mov     [rbx+8], r15
0x1800093ee  mov     [rbx+10h], edi
0x1800093f1  jmp     loc_180009537
0x1800093f6  mov     r15d, 0FFh
0x1800093fc  cmp     edi, r15d
0x1800093ff  jnz     short loc_180009407
0x180009401  mov     r12, [rsi+8]
0x180009405  jmp     short loc_18000940B
0x180009407  lea     r12, [rbp+37h+var_68]
0x18000940b  mov     r8, rsi
0x18000940e  lea     rdx, [rbp+37h+var_50]
0x180009412  call    ?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x180009417  mov     edi, dword ptr [rbp+37h+var_40]
0x18000941a  test    edi, edi
0x18000941c  jns     short loc_180009443
0x18000941e  mov     edx, edi; char *
0x180009420  lea     rcx, aAuthbuffer; "authBuffer"
0x180009427  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000942c  mov     qword ptr [rbx], 0
0x180009433  mov     qword ptr [rbx+8], 0
0x18000943b  mov     [rbx+10h], edi
0x18000943e  jmp     loc_180009529
0x180009443  mov     cl, [rbp+37h+arg_38]
0x180009446  lea     r9, [rbp+37h+var_50]
0x18000944a  mov     r10, [rbp+37h+arg_0]
0x18000944e  lea     rdx, [rbp+37h+var_80]
0x180009452  mov     [rsp+48h], r14
0x180009457  mov     r8, r12
0x18000945a  mov     byte ptr [rsp+0E0h+var_A0], cl
0x18000945e  mov     cl, [rbp+37h+arg_30]
0x180009461  mov     rax, [r10]
0x180009464  mov     [rsp+0E0h+var_A8], cl
0x180009468  mov     rcx, [rbp+37h+arg_28]
0x18000946c  mov     qword ptr [rsp+0E0h+var_B0], rcx
0x180009471  mov     rcx, [rbp+37h+arg_18]
0x180009475  mov     rax, [rax+158h]
0x18000947c  mov     dword ptr [rsp+0E0h+var_B8], r13d
0x180009481  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x180009486  mov     rcx, r10
0x180009489  call    _guard_dispatch_icall
0x18000948e  mov     r14d, dword ptr [rbp+37h+var_70]
0x180009492  xor     r12d, r12d
0x180009495  test    r14d, r14d
0x180009498  jns     short loc_1800094C4
0x18000949a  mov     edx, r14d; char *
0x18000949d  lea     rcx, aResult; "result"
0x1800094a4  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800094a9  mov     rcx, [rbp+37h+var_78]
0x1800094ad  mov     [rbx], r12
0x1800094b0  mov     [rbx+8], r12
0x1800094b4  mov     [rbx+10h], r14d
0x1800094b8  test    rcx, rcx
0x1800094bb  jz      short loc_180009529
0x1800094bd  call    Kerb3961Free
0x1800094c2  jmp     short loc_180009529
0x1800094c4  cmp     dword ptr [rbp+37h+var_58], r15d
0x1800094c8  jz      short loc_180009507
0x1800094ca  mov     rax, [rsi]
0x1800094cd  mov     rdi, [rsi+8]
0x1800094d1  mov     r15, [rbp+37h+Src]
0x1800094d5  lea     rcx, [rax+rax*2]
0x1800094d9  lea     rsi, [rdi+rcx*8]
0x1800094dd  cmp     rdi, rsi
0x1800094e0  jz      short loc_180009507
0x1800094e2  cmp     [rdi+10h], r12b
0x1800094e6  jz      short loc_1800094FA
0x1800094e8  mov     r8, [rdi]; Size
0x1800094eb  mov     rdx, r15; Src
0x1800094ee  mov     rcx, [rdi+8]; void *
0x1800094f2  call    memmove
0x1800094f7  add     r15, [rdi]
0x1800094fa  add     rdi, 18h
0x1800094fe  cmp     rdi, rsi
0x180009501  jnz     short loc_1800094E2
0x180009503  mov     r14d, dword ptr [rbp+37h+var_70]
0x180009507  mov     rax, [rbp+37h+var_80]
0x18000950b  mov     [rbx], rax
0x18000950e  mov     rax, [rbp+37h+var_78]
0x180009512  mov     [rbx+8], rax
0x180009516  mov     [rbx+10h], r14d
0x18000951a  mov     dword ptr [rbp+37h+var_70], 0C0000001h
0x180009521  mov     [rbp+37h+var_80], r12
0x180009525  mov     [rbp+37h+var_78], r12
0x180009529  mov     rcx, [rbp+37h+var_48]
0x18000952d  test    rcx, rcx
0x180009530  jz      short loc_180009537
0x180009532  call    Kerb3961Free
0x180009537  mov     rcx, [rbp+37h+Src]
0x18000953b  test    rcx, rcx
0x18000953e  jz      short loc_180009545
0x180009540  call    Kerb3961Free
0x180009545  mov     rax, rbx
0x180009548  mov     rbx, [rsp+0E0h+arg_8]
0x180009550  add     rsp, 0B0h
0x180009557  pop     r15
0x180009559  pop     r14
0x18000955b  pop     r13
0x18000955d  pop     r12
0x18000955f  pop     rdi
0x180009560  pop     rsi
0x180009561  pop     rbp
0x180009562  retn
```
