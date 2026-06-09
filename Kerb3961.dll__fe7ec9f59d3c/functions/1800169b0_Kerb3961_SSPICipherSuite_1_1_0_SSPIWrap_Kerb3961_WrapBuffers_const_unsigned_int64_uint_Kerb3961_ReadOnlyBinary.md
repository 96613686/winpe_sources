# Kerb3961::SSPICipherSuite<1,1,0>::SSPIWrap(Kerb3961::WrapBuffers const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x1800169b0`
- end: `0x180016c19`
- name: `?SSPIWrap@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@_KIAEBUReadOnlyBinary@2@_N3PEA_K@Z`
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
- `0x180010f4c`
- `0x1800169b0`
- `0x18001d360`
- `0x18001e010`

## string_xrefs

- `0x180016a12`: `combinedBuffer`
- `0x180016a8b`: `combinedBuffer`

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
0x1800169b0  mov     rax, rsp
0x1800169b3  mov     [rax+10h], rbx
0x1800169b7  mov     [rax+20h], r9
0x1800169bb  mov     [rax+8], rcx
0x1800169bf  push    rbp
0x1800169c0  push    rsi
0x1800169c1  push    rdi
0x1800169c2  push    r12
0x1800169c4  push    r13
0x1800169c6  push    r14
0x1800169c8  push    r15
0x1800169ca  lea     rbp, [rax-3Fh]
0x1800169ce  sub     rsp, 0B0h
0x1800169d5  mov     r14, [rbp+37h+arg_40]
0x1800169dc  xor     r15d, r15d
0x1800169df  mov     rsi, r8
0x1800169e2  mov     rbx, rdx
0x1800169e5  mov     r12, rcx
0x1800169e8  test    r14, r14
0x1800169eb  jz      short loc_1800169F0
0x1800169ed  mov     [r14], r15
0x1800169f0  mov     r13d, [rbp+37h+arg_20]
0x1800169f4  mov     rdx, rsi
0x1800169f7  cmp     r13d, 80000001h
0x1800169fe  jnz     short loc_180016A79
0x180016a00  lea     rcx, [rbp+37h+var_50]
0x180016a04  call    ?CoalescePlainWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,2>::CoalescePlainWrapBuffers(Kerb3961::WrapBuffers const &)
0x180016a09  mov     edi, dword ptr [rbp+37h+var_40]
0x180016a0c  test    edi, edi
0x180016a0e  jns     short loc_180016A31
0x180016a10  mov     edx, edi; char *
0x180016a12  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x180016a19  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180016a1e  mov     [rbx], r15
0x180016a21  mov     [rbx+8], r15
0x180016a25  mov     [rbx+10h], edi
0x180016a28  mov     rcx, [rbp+37h+var_48]
0x180016a2c  jmp     loc_180016BEF
0x180016a31  mov     r15d, 0FFh
0x180016a37  cmp     edi, r15d
0x180016a3a  jnz     short loc_180016A42
0x180016a3c  mov     r8, [rsi+8]
0x180016a40  jmp     short loc_180016A46
0x180016a42  lea     r8, [rbp+37h+var_50]
0x180016a46  mov     cl, [rbp+37h+arg_38]
0x180016a49  mov     rdx, rbx
0x180016a4c  mov     rax, [r12]
0x180016a50  mov     r9, [rbp+37h+arg_18]
0x180016a54  mov     [rsp+0E0h+var_B0], cl
0x180016a58  mov     cl, [rbp+37h+arg_30]
0x180016a5b  mov     rax, [rax+160h]
0x180016a62  mov     byte ptr [rsp+0E0h+var_B8], cl
0x180016a66  mov     rcx, [rbp+37h+arg_28]
0x180016a6a  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x180016a6f  mov     rcx, r12
0x180016a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a77  jmp     short loc_180016A28
0x180016a79  lea     rcx, [rbp+37h+var_68]
0x180016a7d  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x180016a82  mov     edi, dword ptr [rbp+37h+var_58]
0x180016a85  test    edi, edi
0x180016a87  jns     short loc_180016AA6
0x180016a89  mov     edx, edi; char *
0x180016a8b  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x180016a92  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180016a97  mov     [rbx], r15
0x180016a9a  mov     [rbx+8], r15
0x180016a9e  mov     [rbx+10h], edi
0x180016aa1  jmp     loc_180016BEB
0x180016aa6  mov     r15d, 0FFh
0x180016aac  cmp     edi, r15d
0x180016aaf  jnz     short loc_180016AB7
0x180016ab1  mov     r12, [rsi+8]
0x180016ab5  jmp     short loc_180016ABB
0x180016ab7  lea     r12, [rbp+37h+var_68]
0x180016abb  mov     r8, rsi
0x180016abe  lea     rdx, [rbp+37h+var_50]
0x180016ac2  call    ?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x180016ac7  mov     edi, dword ptr [rbp+37h+var_40]
0x180016aca  test    edi, edi
0x180016acc  jns     short loc_180016AF3
0x180016ace  mov     edx, edi; char *
0x180016ad0  lea     rcx, aAuthbuffer; "authBuffer"
0x180016ad7  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180016adc  mov     qword ptr [rbx], 0
0x180016ae3  mov     qword ptr [rbx+8], 0
0x180016aeb  mov     [rbx+10h], edi
0x180016aee  jmp     loc_180016BDB
0x180016af3  mov     cl, [rbp+37h+arg_38]
0x180016af6  lea     r9, [rbp+37h+var_50]
0x180016afa  mov     r10, [rbp+37h+arg_0]
0x180016afe  lea     rdx, [rbp+37h+var_80]
0x180016b02  mov     [rsp+48h], r14
0x180016b07  mov     r8, r12
0x180016b0a  mov     byte ptr [rsp+0E0h+var_A0], cl
0x180016b0e  mov     cl, [rbp+37h+arg_30]
0x180016b11  mov     rax, [r10]
0x180016b14  mov     [rsp+0E0h+var_A8], cl
0x180016b18  mov     rcx, [rbp+37h+arg_28]
0x180016b1c  mov     qword ptr [rsp+0E0h+var_B0], rcx
0x180016b21  mov     rcx, [rbp+37h+arg_18]
0x180016b25  mov     rax, [rax+158h]
0x180016b2c  mov     dword ptr [rsp+0E0h+var_B8], r13d
0x180016b31  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x180016b36  mov     rcx, r10
0x180016b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b3e  mov     r14d, dword ptr [rbp+37h+var_70]
0x180016b42  xor     r12d, r12d
0x180016b45  test    r14d, r14d
0x180016b48  jns     short loc_180016B76
0x180016b4a  mov     edx, r14d; char *
0x180016b4d  lea     rcx, aResult; "result"
0x180016b54  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180016b59  mov     rcx, [rbp+37h+var_78]; void *
0x180016b5d  mov     [rbx], r12
0x180016b60  mov     [rbx+8], r12
0x180016b64  mov     [rbx+10h], r14d
0x180016b68  test    rcx, rcx
0x180016b6b  jz      short loc_180016BDB
0x180016b6d  xor     edx, edx; struct std::nothrow_t *
0x180016b6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016b74  jmp     short loc_180016BDB
0x180016b76  cmp     dword ptr [rbp+37h+var_58], r15d
0x180016b7a  jz      short loc_180016BB9
0x180016b7c  mov     rax, [rsi]
0x180016b7f  mov     rdi, [rsi+8]
0x180016b83  mov     r15, [rbp+37h+Src]
0x180016b87  lea     rcx, [rax+rax*2]
0x180016b8b  lea     rsi, [rdi+rcx*8]
0x180016b8f  cmp     rdi, rsi
0x180016b92  jz      short loc_180016BB9
0x180016b94  cmp     [rdi+10h], r12b
0x180016b98  jz      short loc_180016BAC
0x180016b9a  mov     r8, [rdi]; Size
0x180016b9d  mov     rdx, r15; Src
0x180016ba0  mov     rcx, [rdi+8]; void *
0x180016ba4  call    memcpy_0
0x180016ba9  add     r15, [rdi]
0x180016bac  add     rdi, 18h
0x180016bb0  cmp     rdi, rsi
0x180016bb3  jnz     short loc_180016B94
0x180016bb5  mov     r14d, dword ptr [rbp+37h+var_70]
0x180016bb9  mov     rax, [rbp+37h+var_80]
0x180016bbd  mov     [rbx], rax
0x180016bc0  mov     rax, [rbp+37h+var_78]
0x180016bc4  mov     [rbx+8], rax
0x180016bc8  mov     [rbx+10h], r14d
0x180016bcc  mov     dword ptr [rbp+37h+var_70], 0C0000001h
0x180016bd3  mov     [rbp+37h+var_80], r12
0x180016bd7  mov     [rbp+37h+var_78], r12
0x180016bdb  mov     rcx, [rbp+37h+var_48]; void *
0x180016bdf  test    rcx, rcx
0x180016be2  jz      short loc_180016BEB
0x180016be4  xor     edx, edx; struct std::nothrow_t *
0x180016be6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016beb  mov     rcx, [rbp+37h+Src]; void *
0x180016bef  test    rcx, rcx
0x180016bf2  jz      short loc_180016BFB
0x180016bf4  xor     edx, edx; struct std::nothrow_t *
0x180016bf6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016bfb  mov     rax, rbx
0x180016bfe  mov     rbx, [rsp+0E0h+arg_8]
0x180016c06  add     rsp, 0B0h
0x180016c0d  pop     r15
0x180016c0f  pop     r14
0x180016c11  pop     r13
0x180016c13  pop     r12
0x180016c15  pop     rdi
0x180016c16  pop     rsi
0x180016c17  pop     rbp
0x180016c18  retn
```
