# Kerb3961::SSPICipherSuite<1,1,1>::SSPIWrap(Kerb3961::WrapBuffers const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool,unsigned __int64 *)

- ea: `0x1800099c0`
- end: `0x180009c3d`
- name: `?SSPIWrap@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@_KIAEBUReadOnlyBinary@2@_N3PEA_K@Z`
- size: `637`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002fc0`
- `0x180004b40`
- `0x180004cf4`
- `0x180004fac`
- `0x1800099c0`
- `0x18001d360`
- `0x18001e010`

## string_xrefs

- `0x180009a22`: `combinedBuffer`
- `0x180009a9b`: `combinedBuffer`

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
  void *v24; // rcx
  __int64 v25; // rdi
  char *v26; // r15
  __int64 v27; // rsi
  _QWORD v29[2]; // [rsp+68h] [rbp-59h] BYREF
  __int64 v30; // [rsp+78h] [rbp-49h] BYREF
  void *v31; // [rsp+80h] [rbp-41h]
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
    Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers((__int64)v33, a3);
    v18 = (int)v35;
    if ( (int)v35 >= 0 )
    {
      if ( (_DWORD)v35 == 255 )
        v19 = (_BYTE *)a3[1];
      else
        v19 = v33;
      v29[0] = 0;
      v29[1] = 0;
      Kerb3961::SSPICipherSuite<1,1,1>::CoalesceAuthWrapBuffers(v16, (__int64)v36, a3, (__int64)v29);
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
                  memcpy_0(*(void **)(v25 + 8), v26, *(_QWORD *)v25);
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
            operator delete(v24, 0);
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
        operator delete(v37, 0);
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
    operator delete(v14, 0);
  return a2;
}

```

## disassembly

```asm
0x1800099c0  mov     rax, rsp
0x1800099c3  mov     [rax+10h], rbx
0x1800099c7  mov     [rax+20h], r9
0x1800099cb  mov     [rax+8], rcx
0x1800099cf  push    rbp
0x1800099d0  push    rsi
0x1800099d1  push    rdi
0x1800099d2  push    r12
0x1800099d4  push    r13
0x1800099d6  push    r14
0x1800099d8  push    r15
0x1800099da  lea     rbp, [rax-3Fh]
0x1800099de  sub     rsp, 0C0h
0x1800099e5  mov     r14, [rbp+37h+arg_40]
0x1800099ec  xor     r15d, r15d
0x1800099ef  mov     rsi, r8
0x1800099f2  mov     rbx, rdx
0x1800099f5  mov     r12, rcx
0x1800099f8  test    r14, r14
0x1800099fb  jz      short loc_180009A00
0x1800099fd  mov     [r14], r15
0x180009a00  mov     r13d, [rbp+37h+arg_20]
0x180009a04  mov     rdx, rsi
0x180009a07  cmp     r13d, 80000001h
0x180009a0e  jnz     short loc_180009A89
0x180009a10  lea     rcx, [rbp+37h+var_50]
0x180009a14  call    ?CoalescePlainWrapBuffers@?$SSPICipherSuite@$00$00$01@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,2>::CoalescePlainWrapBuffers(Kerb3961::WrapBuffers const &)
0x180009a19  mov     edi, dword ptr [rbp+37h+var_40]
0x180009a1c  test    edi, edi
0x180009a1e  jns     short loc_180009A41
0x180009a20  mov     edx, edi; char *
0x180009a22  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x180009a29  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009a2e  mov     [rbx], r15
0x180009a31  mov     [rbx+8], r15
0x180009a35  mov     [rbx+10h], edi
0x180009a38  mov     rcx, [rbp+37h+var_48]
0x180009a3c  jmp     loc_180009C13
0x180009a41  mov     r15d, 0FFh
0x180009a47  cmp     edi, r15d
0x180009a4a  jnz     short loc_180009A52
0x180009a4c  mov     r8, [rsi+8]
0x180009a50  jmp     short loc_180009A56
0x180009a52  lea     r8, [rbp+37h+var_50]
0x180009a56  mov     cl, [rbp+37h+arg_38]
0x180009a59  mov     rdx, rbx
0x180009a5c  mov     rax, [r12]
0x180009a60  mov     r9, [rbp+37h+arg_18]
0x180009a64  mov     [rsp+0F0h+var_C0], cl
0x180009a68  mov     cl, [rbp+37h+arg_30]
0x180009a6b  mov     rax, [rax+160h]
0x180009a72  mov     byte ptr [rsp+0F0h+var_C8], cl
0x180009a76  mov     rcx, [rbp+37h+arg_28]
0x180009a7a  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x180009a7f  mov     rcx, r12
0x180009a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a87  jmp     short loc_180009A38
0x180009a89  lea     rcx, [rbp+37h+var_68]
0x180009a8d  call    ?CoalesceEncryptedWrapBuffers@?$SSPICipherSuite@$00$00$0A@@Kerb3961@@KA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@@Z; Kerb3961::SSPICipherSuite<1,1,0>::CoalesceEncryptedWrapBuffers(Kerb3961::WrapBuffers const &)
0x180009a92  mov     edi, dword ptr [rbp+37h+var_58]
0x180009a95  test    edi, edi
0x180009a97  jns     short loc_180009AB6
0x180009a99  mov     edx, edi; char *
0x180009a9b  lea     rcx, aCombinedbuffer; "combinedBuffer"
0x180009aa2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009aa7  mov     [rbx], r15
0x180009aaa  mov     [rbx+8], r15
0x180009aae  mov     [rbx+10h], edi
0x180009ab1  jmp     loc_180009C0F
0x180009ab6  mov     r15d, 0FFh
0x180009abc  cmp     edi, r15d
0x180009abf  jnz     short loc_180009AC7
0x180009ac1  mov     r12, [rsi+8]
0x180009ac5  jmp     short loc_180009ACB
0x180009ac7  lea     r12, [rbp+37h+var_68]
0x180009acb  lea     r9, [rbp+37h+var_90]
0x180009acf  mov     [rbp+37h+var_90], 0
0x180009ad7  mov     r8, rsi
0x180009ada  mov     [rbp+37h+var_88], 0
0x180009ae2  lea     rdx, [rbp+37h+var_50]
0x180009ae6  call    ?CoalesceAuthWrapBuffers@?$SSPICipherSuite@$00$00$00@Kerb3961@@IEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUWrapBuffers@2@AEBUReadOnlyBinary@2@@Z; Kerb3961::SSPICipherSuite<1,1,1>::CoalesceAuthWrapBuffers(Kerb3961::WrapBuffers const &,Kerb3961::ReadOnlyBinary const &)
0x180009aeb  mov     edi, dword ptr [rbp+37h+var_40]
0x180009aee  test    edi, edi
0x180009af0  jns     short loc_180009B17
0x180009af2  mov     edx, edi; char *
0x180009af4  lea     rcx, aAuthbuffer; "authBuffer"
0x180009afb  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009b00  mov     qword ptr [rbx], 0
0x180009b07  mov     qword ptr [rbx+8], 0
0x180009b0f  mov     [rbx+10h], edi
0x180009b12  jmp     loc_180009BFF
0x180009b17  mov     cl, [rbp+37h+arg_38]
0x180009b1a  lea     r9, [rbp+37h+var_50]
0x180009b1e  mov     r10, [rbp+37h+arg_0]
0x180009b22  lea     rdx, [rbp+37h+var_80]
0x180009b26  mov     [rsp+48h], r14
0x180009b2b  mov     r8, r12
0x180009b2e  mov     byte ptr [rsp+0F0h+var_B0], cl
0x180009b32  mov     cl, [rbp+37h+arg_30]
0x180009b35  mov     rax, [r10]
0x180009b38  mov     [rsp+0F0h+var_B8], cl
0x180009b3c  mov     rcx, [rbp+37h+arg_28]
0x180009b40  mov     qword ptr [rsp+0F0h+var_C0], rcx
0x180009b45  mov     rcx, [rbp+37h+arg_18]
0x180009b49  mov     rax, [rax+158h]
0x180009b50  mov     dword ptr [rsp+0F0h+var_C8], r13d
0x180009b55  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x180009b5a  mov     rcx, r10
0x180009b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b62  mov     r14d, dword ptr [rbp+37h+var_70]
0x180009b66  xor     r12d, r12d
0x180009b69  test    r14d, r14d
0x180009b6c  jns     short loc_180009B9A
0x180009b6e  mov     edx, r14d; char *
0x180009b71  lea     rcx, aResult; "result"
0x180009b78  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009b7d  mov     rcx, [rbp+37h+var_78]; void *
0x180009b81  mov     [rbx], r12
0x180009b84  mov     [rbx+8], r12
0x180009b88  mov     [rbx+10h], r14d
0x180009b8c  test    rcx, rcx
0x180009b8f  jz      short loc_180009BFF
0x180009b91  xor     edx, edx; struct std::nothrow_t *
0x180009b93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009b98  jmp     short loc_180009BFF
0x180009b9a  cmp     dword ptr [rbp+37h+var_58], r15d
0x180009b9e  jz      short loc_180009BDD
0x180009ba0  mov     rax, [rsi]
0x180009ba3  mov     rdi, [rsi+8]
0x180009ba7  mov     r15, [rbp+37h+Src]
0x180009bab  lea     rcx, [rax+rax*2]
0x180009baf  lea     rsi, [rdi+rcx*8]
0x180009bb3  cmp     rdi, rsi
0x180009bb6  jz      short loc_180009BDD
0x180009bb8  cmp     [rdi+10h], r12b
0x180009bbc  jz      short loc_180009BD0
0x180009bbe  mov     r8, [rdi]; Size
0x180009bc1  mov     rdx, r15; Src
0x180009bc4  mov     rcx, [rdi+8]; void *
0x180009bc8  call    memcpy_0
0x180009bcd  add     r15, [rdi]
0x180009bd0  add     rdi, 18h
0x180009bd4  cmp     rdi, rsi
0x180009bd7  jnz     short loc_180009BB8
0x180009bd9  mov     r14d, dword ptr [rbp+37h+var_70]
0x180009bdd  mov     rax, [rbp+37h+var_80]
0x180009be1  mov     [rbx], rax
0x180009be4  mov     rax, [rbp+37h+var_78]
0x180009be8  mov     [rbx+8], rax
0x180009bec  mov     [rbx+10h], r14d
0x180009bf0  mov     dword ptr [rbp+37h+var_70], 0C0000001h
0x180009bf7  mov     [rbp+37h+var_80], r12
0x180009bfb  mov     [rbp+37h+var_78], r12
0x180009bff  mov     rcx, [rbp+37h+var_48]; void *
0x180009c03  test    rcx, rcx
0x180009c06  jz      short loc_180009C0F
0x180009c08  xor     edx, edx; struct std::nothrow_t *
0x180009c0a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009c0f  mov     rcx, [rbp+37h+Src]; void *
0x180009c13  test    rcx, rcx
0x180009c16  jz      short loc_180009C1F
0x180009c18  xor     edx, edx; struct std::nothrow_t *
0x180009c1a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009c1f  mov     rax, rbx
0x180009c22  mov     rbx, [rsp+0F0h+arg_8]
0x180009c2a  add     rsp, 0C0h
0x180009c31  pop     r15
0x180009c33  pop     r14
0x180009c35  pop     r13
0x180009c37  pop     r12
0x180009c39  pop     rdi
0x180009c3a  pop     rsi
0x180009c3b  pop     rbp
0x180009c3c  retn
```
