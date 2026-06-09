# Kerb3961::SSPICipherSuite<1,1,2>::SSPIWrap(Kerb3961::WrapBuffers const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x18001bec0`
- end: `0x18001c129`
- name: `?SSPIWrap@?$SSPICipherSuite@$00$00$01@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@_KIAEBUReadOnlyBinary@2@_N3PEA_K@Z`
- size: `617`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002fc0`
- `0x180004cf4`
- `0x180004fac`
- `0x1800190d0`
- `0x18001bec0`
- `0x18001d360`
- `0x18001e010`

## string_xrefs

- `0x18001bf22`: `combinedBuffer`
- `0x18001bf9b`: `combinedBuffer`

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
  void *v24; // rcx
  __int64 v25; // rdi
  char *v26; // r15
  __int64 v27; // rsi
  __int64 v29; // [rsp+68h] [rbp-49h] BYREF
  void *v30; // [rsp+70h] [rbp-41h]
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
    Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers((__int64)v32, a3);
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
                  memcpy_0(*(void **)(v25 + 8), v26, *(_QWORD *)v25);
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
            operator delete(v24, 0);
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
        operator delete(v36, 0);
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
    operator delete(v14, 0);
  return a2;
}

```

## disassembly

```asm
0x18001bec0  mov     rax, rsp
0x18001bec3  mov     [rax+10h], rbx
0x18001bec7  mov     [rax+20h], r9
0x18001becb  mov     [rax+8], rcx
0x18001becf  push    rbp
0x18001bed0  push    rsi
0x18001bed1  push    rdi
0x18001bed2  push    r12
0x18001bed4  push    r13
0x18001bed6  push    r14
0x18001bed8  push    r15
0x18001beda  lea     rbp, [rax-3Fh]
0x18001bede  sub     rsp, 0B0h
0x18001bee5  mov     r14, [rbp+37h+arg_40]
0x18001beec  xor     r15d, r15d
0x18001beef  mov     rsi, r8
0x18001bef2  mov     rbx, rdx
0x18001bef5  mov     r12, rcx
0x18001bef8  test    r14, r14
0x18001befb  jz      short loc_18001BF00
0x18001befd  mov     [r14], r15
0x18001bf00  mov     r13d, [rbp+37h+arg_20]
0x18001bf04  mov     rdx, rsi
0x18001bf07  cmp     r13d, 80000001h
0x18001bf0e  jnz     short loc_18001BF89
0x18001bf10  lea     rcx, [rbp+37h+var_50]
0x18001bf14  call    ?CoalescePlainWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,2>::CoalescePlainWrapBuffers(Kerb3961::WrapBuffers const &)
0x18001bf19  mov     edi, dword ptr [rbp+37h+var_40]
0x18001bf1c  test    edi, edi
0x18001bf1e  jns     short loc_18001BF41
0x18001bf20  mov     edx, edi; char *
0x18001bf22  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x18001bf29  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001bf2e  mov     [rbx], r15
0x18001bf31  mov     [rbx+8], r15
0x18001bf35  mov     [rbx+10h], edi
0x18001bf38  mov     rcx, [rbp+37h+var_48]
0x18001bf3c  jmp     loc_18001C0FF
0x18001bf41  mov     r15d, 0FFh
0x18001bf47  cmp     edi, r15d
0x18001bf4a  jnz     short loc_18001BF52
0x18001bf4c  mov     r8, [rsi+8]
0x18001bf50  jmp     short loc_18001BF56
0x18001bf52  lea     r8, [rbp+37h+var_50]
0x18001bf56  mov     cl, [rbp+37h+arg_38]
0x18001bf59  mov     rdx, rbx
0x18001bf5c  mov     rax, [r12]
0x18001bf60  mov     r9, [rbp+37h+arg_18]
0x18001bf64  mov     [rsp+0E0h+var_B0], cl
0x18001bf68  mov     cl, [rbp+37h+arg_30]
0x18001bf6b  mov     rax, [rax+160h]
0x18001bf72  mov     byte ptr [rsp+0E0h+var_B8], cl
0x18001bf76  mov     rcx, [rbp+37h+arg_28]
0x18001bf7a  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x18001bf7f  mov     rcx, r12
0x18001bf82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf87  jmp     short loc_18001BF38
0x18001bf89  lea     rcx, [rbp+37h+var_68]
0x18001bf8d  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x18001bf92  mov     edi, dword ptr [rbp+37h+var_58]
0x18001bf95  test    edi, edi
0x18001bf97  jns     short loc_18001BFB6
0x18001bf99  mov     edx, edi; char *
0x18001bf9b  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x18001bfa2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001bfa7  mov     [rbx], r15
0x18001bfaa  mov     [rbx+8], r15
0x18001bfae  mov     [rbx+10h], edi
0x18001bfb1  jmp     loc_18001C0FB
0x18001bfb6  mov     r15d, 0FFh
0x18001bfbc  cmp     edi, r15d
0x18001bfbf  jnz     short loc_18001BFC7
0x18001bfc1  mov     r12, [rsi+8]
0x18001bfc5  jmp     short loc_18001BFCB
0x18001bfc7  lea     r12, [rbp+37h+var_68]
0x18001bfcb  mov     r8, rsi
0x18001bfce  lea     rdx, [rbp+37h+var_50]
0x18001bfd2  call    ?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,2>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x18001bfd7  mov     edi, dword ptr [rbp+37h+var_40]
0x18001bfda  test    edi, edi
0x18001bfdc  jns     short loc_18001C003
0x18001bfde  mov     edx, edi; char *
0x18001bfe0  lea     rcx, aAuthbuffer; "authBuffer"
0x18001bfe7  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001bfec  mov     qword ptr [rbx], 0
0x18001bff3  mov     qword ptr [rbx+8], 0
0x18001bffb  mov     [rbx+10h], edi
0x18001bffe  jmp     loc_18001C0EB
0x18001c003  mov     cl, [rbp+37h+arg_38]
0x18001c006  lea     r9, [rbp+37h+var_50]
0x18001c00a  mov     r10, [rbp+37h+arg_0]
0x18001c00e  lea     rdx, [rbp+37h+var_80]
0x18001c012  mov     [rsp+48h], r14
0x18001c017  mov     r8, r12
0x18001c01a  mov     byte ptr [rsp+0E0h+var_A0], cl
0x18001c01e  mov     cl, [rbp+37h+arg_30]
0x18001c021  mov     rax, [r10]
0x18001c024  mov     [rsp+0E0h+var_A8], cl
0x18001c028  mov     rcx, [rbp+37h+arg_28]
0x18001c02c  mov     qword ptr [rsp+0E0h+var_B0], rcx
0x18001c031  mov     rcx, [rbp+37h+arg_18]
0x18001c035  mov     rax, [rax+158h]
0x18001c03c  mov     dword ptr [rsp+0E0h+var_B8], r13d
0x18001c041  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x18001c046  mov     rcx, r10
0x18001c049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c04e  mov     r14d, dword ptr [rbp+37h+var_70]
0x18001c052  xor     r12d, r12d
0x18001c055  test    r14d, r14d
0x18001c058  jns     short loc_18001C086
0x18001c05a  mov     edx, r14d; char *
0x18001c05d  lea     rcx, aResult; "result"
0x18001c064  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001c069  mov     rcx, [rbp+37h+var_78]; void *
0x18001c06d  mov     [rbx], r12
0x18001c070  mov     [rbx+8], r12
0x18001c074  mov     [rbx+10h], r14d
0x18001c078  test    rcx, rcx
0x18001c07b  jz      short loc_18001C0EB
0x18001c07d  xor     edx, edx; struct std::nothrow_t *
0x18001c07f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c084  jmp     short loc_18001C0EB
0x18001c086  cmp     dword ptr [rbp+37h+var_58], r15d
0x18001c08a  jz      short loc_18001C0C9
0x18001c08c  mov     rax, [rsi]
0x18001c08f  mov     rdi, [rsi+8]
0x18001c093  mov     r15, [rbp+37h+Src]
0x18001c097  lea     rcx, [rax+rax*2]
0x18001c09b  lea     rsi, [rdi+rcx*8]
0x18001c09f  cmp     rdi, rsi
0x18001c0a2  jz      short loc_18001C0C9
0x18001c0a4  cmp     [rdi+10h], r12b
0x18001c0a8  jz      short loc_18001C0BC
0x18001c0aa  mov     r8, [rdi]; Size
0x18001c0ad  mov     rdx, r15; Src
0x18001c0b0  mov     rcx, [rdi+8]; void *
0x18001c0b4  call    memcpy_0
0x18001c0b9  add     r15, [rdi]
0x18001c0bc  add     rdi, 18h
0x18001c0c0  cmp     rdi, rsi
0x18001c0c3  jnz     short loc_18001C0A4
0x18001c0c5  mov     r14d, dword ptr [rbp+37h+var_70]
0x18001c0c9  mov     rax, [rbp+37h+var_80]
0x18001c0cd  mov     [rbx], rax
0x18001c0d0  mov     rax, [rbp+37h+var_78]
0x18001c0d4  mov     [rbx+8], rax
0x18001c0d8  mov     [rbx+10h], r14d
0x18001c0dc  mov     dword ptr [rbp+37h+var_70], 0C0000001h
0x18001c0e3  mov     [rbp+37h+var_80], r12
0x18001c0e7  mov     [rbp+37h+var_78], r12
0x18001c0eb  mov     rcx, [rbp+37h+var_48]; void *
0x18001c0ef  test    rcx, rcx
0x18001c0f2  jz      short loc_18001C0FB
0x18001c0f4  xor     edx, edx; struct std::nothrow_t *
0x18001c0f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c0fb  mov     rcx, [rbp+37h+Src]; void *
0x18001c0ff  test    rcx, rcx
0x18001c102  jz      short loc_18001C10B
0x18001c104  xor     edx, edx; struct std::nothrow_t *
0x18001c106  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c10b  mov     rax, rbx
0x18001c10e  mov     rbx, [rsp+0E0h+arg_8]
0x18001c116  add     rsp, 0B0h
0x18001c11d  pop     r15
0x18001c11f  pop     r14
0x18001c121  pop     r13
0x18001c123  pop     r12
0x18001c125  pop     rdi
0x18001c126  pop     rsi
0x18001c127  pop     rbp
0x18001c128  retn
```
