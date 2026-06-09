# Kerb3961::SSPICipherSuite<1,1,1>::SSPIWrap(Kerb3961::WrapBuffers const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x180010760`
- end: `0x1800109d8`
- name: `?SSPIWrap@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@_KIAEBUReadOnlyBinary@2@_N3PEA_K@Z`
- size: `632`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001ff4`
- `0x1800022a8`
- `0x18000d3c0`
- `0x180010760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`
- `0x180012300`

## string_xrefs

- `0x1800107c2`: `combinedBuffer`
- `0x18001083b`: `combinedBuffer`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,1>::SSPIWrap(
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
  _QWORD v29[2]; // [rsp+68h] [rbp-59h] BYREF
  __int64 v30; // [rsp+78h] [rbp-49h] BYREF
  __int64 v31; // [rsp+80h] [rbp-41h]
  char *v32; // [rsp+88h] [rbp-39h]
  _BYTE v33[8]; // [rsp+90h] [rbp-31h] BYREF
  void *Src; // [rsp+98h] [rbp-29h]
  char *v35; // [rsp+A0h] [rbp-21h]
  _BYTE v36[8]; // [rsp+A8h] [rbp-19h] BYREF
  void *v37; // [rsp+B0h] [rbp-11h]
  char *v38; // [rsp+B8h] [rbp-9h]

  if ( a9 )
    *a9 = 0;
  if ( a5 == -2147483647 )
  {
    Kerb3961::SSPICipherSuite<1,1,2>::CoalescePlainWrapBuffers(v36, a3);
    v13 = (int)v38;
    if ( (int)v38 >= 0 )
    {
      if ( (_DWORD)v38 == 255 )
        v15 = (_BYTE *)a3[1];
      else
        v15 = v36;
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
        (const char *)(unsigned int)v38,
        v12);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v13;
    }
    v14 = v37;
  }
  else
  {
    Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(v33, a3);
    v18 = (int)v35;
    if ( (int)v35 >= 0 )
    {
      if ( (_DWORD)v35 == 255 )
        v19 = (_BYTE *)a3[1];
      else
        v19 = v33;
      v29[0] = 0;
      v29[1] = 0;
      Kerb3961::SSPICipherSuite<1,1,1>::CoalesceAuthWrapBuffers(v16, v36, a3, v29);
      v21 = (int)v38;
      if ( (int)v38 >= 0 )
      {
        (*(void (__fastcall **)(__int64, __int64 *, _BYTE *, _BYTE *, __int64, int, __int64, char, char, _QWORD *))(*(_QWORD *)a1 + 344LL))(
          a1,
          &v30,
          v19,
          v36,
          a4,
          a5,
          a6,
          a7,
          a8,
          a9);
        v23 = (int)v32;
        if ( (int)v32 >= 0 )
        {
          if ( (_DWORD)v35 != 255 )
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
              v23 = (int)v32;
            }
          }
          *(_QWORD *)a2 = v30;
          *(_QWORD *)(a2 + 8) = v31;
          *(_DWORD *)(a2 + 16) = v23;
          LODWORD(v32) = -1073741823;
          v30 = 0;
          v31 = 0;
        }
        else
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"result",
            (const char *)(unsigned int)v32,
            v22);
          v24 = v31;
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
          (const char *)(unsigned int)v38,
          v20);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v21;
      }
      if ( v37 )
        Kerb3961Free(v37);
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"combinedBuffer",
        (const char *)(unsigned int)v35,
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
0x180010760  mov     rax, rsp
0x180010763  mov     [rax+10h], rbx
0x180010767  mov     [rax+20h], r9
0x18001076b  mov     [rax+8], rcx
0x18001076f  push    rbp
0x180010770  push    rsi
0x180010771  push    rdi
0x180010772  push    r12
0x180010774  push    r13
0x180010776  push    r14
0x180010778  push    r15
0x18001077a  lea     rbp, [rax-3Fh]
0x18001077e  sub     rsp, 0C0h
0x180010785  mov     r14, [rbp+37h+arg_40]
0x18001078c  xor     r15d, r15d
0x18001078f  mov     rsi, r8
0x180010792  mov     rbx, rdx
0x180010795  mov     r12, rcx
0x180010798  test    r14, r14
0x18001079b  jz      short loc_1800107A0
0x18001079d  mov     [r14], r15
0x1800107a0  mov     r13d, [rbp+37h+arg_20]
0x1800107a4  mov     rdx, rsi
0x1800107a7  cmp     r13d, 80000001h
0x1800107ae  jnz     short loc_180010829
0x1800107b0  lea     rcx, [rbp+37h+var_50]
0x1800107b4  call    ?CoalescePlainWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,2>::CoalescePlainWrapBuffers(Kerb3961::WrapBuffers const &)
0x1800107b9  mov     edi, dword ptr [rbp+37h+var_40]
0x1800107bc  test    edi, edi
0x1800107be  jns     short loc_1800107E1
0x1800107c0  mov     edx, edi; char *
0x1800107c2  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x1800107c9  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800107ce  mov     [rbx], r15
0x1800107d1  mov     [rbx+8], r15
0x1800107d5  mov     [rbx+10h], edi
0x1800107d8  mov     rcx, [rbp+37h+var_48]
0x1800107dc  jmp     loc_1800109AF
0x1800107e1  mov     r15d, 0FFh
0x1800107e7  cmp     edi, r15d
0x1800107ea  jnz     short loc_1800107F2
0x1800107ec  mov     r8, [rsi+8]
0x1800107f0  jmp     short loc_1800107F6
0x1800107f2  lea     r8, [rbp+37h+var_50]
0x1800107f6  mov     cl, [rbp+37h+arg_38]
0x1800107f9  mov     rdx, rbx
0x1800107fc  mov     rax, [r12]
0x180010800  mov     r9, [rbp+37h+arg_18]
0x180010804  mov     [rsp+0F0h+var_C0], cl
0x180010808  mov     cl, [rbp+37h+arg_30]
0x18001080b  mov     rax, [rax+160h]
0x180010812  mov     byte ptr [rsp+0F0h+var_C8], cl
0x180010816  mov     rcx, [rbp+37h+arg_28]
0x18001081a  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x18001081f  mov     rcx, r12
0x180010822  call    _guard_dispatch_icall
0x180010827  jmp     short loc_1800107D8
0x180010829  lea     rcx, [rbp+37h+var_68]
0x18001082d  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x180010832  mov     edi, dword ptr [rbp+37h+var_58]
0x180010835  test    edi, edi
0x180010837  jns     short loc_180010856
0x180010839  mov     edx, edi; char *
0x18001083b  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x180010842  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180010847  mov     [rbx], r15
0x18001084a  mov     [rbx+8], r15
0x18001084e  mov     [rbx+10h], edi
0x180010851  jmp     loc_1800109AB
0x180010856  mov     r15d, 0FFh
0x18001085c  cmp     edi, r15d
0x18001085f  jnz     short loc_180010867
0x180010861  mov     r12, [rsi+8]
0x180010865  jmp     short loc_18001086B
0x180010867  lea     r12, [rbp+37h+var_68]
0x18001086b  lea     r9, [rbp+37h+var_90]
0x18001086f  mov     [rbp+37h+var_90], 0
0x180010877  mov     r8, rsi
0x18001087a  mov     [rbp+37h+var_88], 0
0x180010882  lea     rdx, [rbp+37h+var_50]
0x180010886  call    ?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$00@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,1>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x18001088b  mov     edi, dword ptr [rbp+37h+var_40]
0x18001088e  test    edi, edi
0x180010890  jns     short loc_1800108B7
0x180010892  mov     edx, edi; char *
0x180010894  lea     rcx, aAuthbuffer; "authBuffer"
0x18001089b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800108a0  mov     qword ptr [rbx], 0
0x1800108a7  mov     qword ptr [rbx+8], 0
0x1800108af  mov     [rbx+10h], edi
0x1800108b2  jmp     loc_18001099D
0x1800108b7  mov     cl, [rbp+37h+arg_38]
0x1800108ba  lea     r9, [rbp+37h+var_50]
0x1800108be  mov     r10, [rbp+37h+arg_0]
0x1800108c2  lea     rdx, [rbp+37h+var_80]
0x1800108c6  mov     [rsp+48h], r14
0x1800108cb  mov     r8, r12
0x1800108ce  mov     byte ptr [rsp+0F0h+var_B0], cl
0x1800108d2  mov     cl, [rbp+37h+arg_30]
0x1800108d5  mov     rax, [r10]
0x1800108d8  mov     [rsp+0F0h+var_B8], cl
0x1800108dc  mov     rcx, [rbp+37h+arg_28]
0x1800108e0  mov     qword ptr [rsp+0F0h+var_C0], rcx
0x1800108e5  mov     rcx, [rbp+37h+arg_18]
0x1800108e9  mov     rax, [rax+158h]
0x1800108f0  mov     dword ptr [rsp+0F0h+var_C8], r13d
0x1800108f5  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x1800108fa  mov     rcx, r10
0x1800108fd  call    _guard_dispatch_icall
0x180010902  mov     r14d, dword ptr [rbp+37h+var_70]
0x180010906  xor     r12d, r12d
0x180010909  test    r14d, r14d
0x18001090c  jns     short loc_180010938
0x18001090e  mov     edx, r14d; char *
0x180010911  lea     rcx, aResult; "result"
0x180010918  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001091d  mov     rcx, [rbp+37h+var_78]
0x180010921  mov     [rbx], r12
0x180010924  mov     [rbx+8], r12
0x180010928  mov     [rbx+10h], r14d
0x18001092c  test    rcx, rcx
0x18001092f  jz      short loc_18001099D
0x180010931  call    Kerb3961Free
0x180010936  jmp     short loc_18001099D
0x180010938  cmp     dword ptr [rbp+37h+var_58], r15d
0x18001093c  jz      short loc_18001097B
0x18001093e  mov     rax, [rsi]
0x180010941  mov     rdi, [rsi+8]
0x180010945  mov     r15, [rbp+37h+Src]
0x180010949  lea     rcx, [rax+rax*2]
0x18001094d  lea     rsi, [rdi+rcx*8]
0x180010951  cmp     rdi, rsi
0x180010954  jz      short loc_18001097B
0x180010956  cmp     [rdi+10h], r12b
0x18001095a  jz      short loc_18001096E
0x18001095c  mov     r8, [rdi]; Size
0x18001095f  mov     rdx, r15; Src
0x180010962  mov     rcx, [rdi+8]; void *
0x180010966  call    memmove
0x18001096b  add     r15, [rdi]
0x18001096e  add     rdi, 18h
0x180010972  cmp     rdi, rsi
0x180010975  jnz     short loc_180010956
0x180010977  mov     r14d, dword ptr [rbp+37h+var_70]
0x18001097b  mov     rax, [rbp+37h+var_80]
0x18001097f  mov     [rbx], rax
0x180010982  mov     rax, [rbp+37h+var_78]
0x180010986  mov     [rbx+8], rax
0x18001098a  mov     [rbx+10h], r14d
0x18001098e  mov     dword ptr [rbp+37h+var_70], 0C0000001h
0x180010995  mov     [rbp+37h+var_80], r12
0x180010999  mov     [rbp+37h+var_78], r12
0x18001099d  mov     rcx, [rbp+37h+var_48]
0x1800109a1  test    rcx, rcx
0x1800109a4  jz      short loc_1800109AB
0x1800109a6  call    Kerb3961Free
0x1800109ab  mov     rcx, [rbp+37h+Src]
0x1800109af  test    rcx, rcx
0x1800109b2  jz      short loc_1800109B9
0x1800109b4  call    Kerb3961Free
0x1800109b9  mov     rax, rbx
0x1800109bc  mov     rbx, [rsp+0F0h+arg_8]
0x1800109c4  add     rsp, 0C0h
0x1800109cb  pop     r15
0x1800109cd  pop     r14
0x1800109cf  pop     r13
0x1800109d1  pop     r12
0x1800109d3  pop     rdi
0x1800109d4  pop     rsi
0x1800109d5  pop     rbp
0x1800109d6  retn
```
