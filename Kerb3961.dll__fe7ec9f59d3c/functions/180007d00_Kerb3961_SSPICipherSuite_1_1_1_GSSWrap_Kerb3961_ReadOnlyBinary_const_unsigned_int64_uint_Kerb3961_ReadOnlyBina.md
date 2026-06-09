# Kerb3961::SSPICipherSuite<1,1,1>::GSSWrap(Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180007d00`
- end: `0x180007ecd`
- name: `?GSSWrap@?$SSPICipherSuite@$00$00$00@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@_KI0_N2@Z`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18000700c`
- `0x18000712c`
- `0x180007d00`
- `0x18001e010`

## string_xrefs

- `0x180007de5`: `inputCopy`

## pseudocode

```c
__int64 __fastcall Kerb3961::SSPICipherSuite<1,1,1>::GSSWrap(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        char a7,
        char a8)
{
  int v12; // r8d
  int v13; // r14d
  int v14; // r8d
  int v15; // esi
  void (__fastcall *v16)(__int64, _BYTE *, _BYTE *, _QWORD *, __int64, int, __int64, char, char, _QWORD); // rax
  int v17; // r8d
  int v18; // esi
  _QWORD v20[2]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v21[8]; // [rsp+70h] [rbp-29h] BYREF
  void *v22; // [rsp+78h] [rbp-21h]
  char *v23; // [rsp+80h] [rbp-19h]
  _BYTE v24[8]; // [rsp+88h] [rbp-11h] BYREF
  void *v25; // [rsp+90h] [rbp-9h]
  char *v26; // [rsp+98h] [rbp-1h]

  if ( *a3 <= 0xFFFFFFFFFFFF0000uLL )
  {
    if ( a5 == -2147483647 )
    {
      (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 352LL))(a1, v21);
      v13 = (int)v23;
      if ( (int)v23 >= 0 )
      {
        Kerb3961::Concatenate(a2, v21, a3);
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"header",
          (const char *)(unsigned int)v23,
          v12);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v13;
      }
    }
    else
    {
      Kerb3961::CopyBuffer(v21, a3);
      v15 = (int)v23;
      if ( (int)v23 >= 0 )
      {
        v16 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, _QWORD *, __int64, int, __int64, char, char, _QWORD))(*(_QWORD *)a1 + 344LL);
        v20[0] = 0;
        v20[1] = 0;
        v16(a1, v24, v21, v20, a4, a5, a6, a7, a8, 0);
        v18 = (int)v26;
        if ( (int)v26 >= 0 )
        {
          Kerb3961::Concatenate(a2, v24, v21);
        }
        else
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"header",
            (const char *)(unsigned int)v26,
            v17);
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v18;
        }
        if ( v25 )
          operator delete(v25, 0);
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"inputCopy",
          (const char *)(unsigned int)v23,
          v14);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v15;
      }
    }
    if ( v22 )
      operator delete(v22, 0);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"inputMessage.length <= MessageLimit",
      (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
  }
  return a2;
}

```

## disassembly

```asm
0x180007d00  push    rbp
0x180007d02  push    rsi
0x180007d03  push    rdi
0x180007d04  push    r12
0x180007d06  push    r14
0x180007d08  push    r15
0x180007d0a  lea     rbp, [rsp-0Fh]
0x180007d0f  sub     rsp, 0A8h
0x180007d16  cmp     qword ptr [r8], 0FFFFFFFFFFFF0000h
0x180007d1d  mov     r12, r9
0x180007d20  mov     rsi, r8
0x180007d23  mov     rdi, rdx
0x180007d26  mov     r15, rcx
0x180007d29  jbe     short loc_180007D52
0x180007d2b  lea     rcx, aInputmessageLe_0; "inputMessage.length <= MessageLimit"
0x180007d32  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007d37  mov     qword ptr [rdi], 0
0x180007d3e  mov     qword ptr [rdi+8], 0
0x180007d46  mov     dword ptr [rdi+10h], 0C0000095h
0x180007d4d  jmp     loc_180007EB9
0x180007d52  mov     r14d, [rbp+37h+arg_20]
0x180007d56  cmp     r14d, 80000001h
0x180007d5d  jnz     short loc_180007DD0
0x180007d5f  mov     rax, [rcx]
0x180007d62  lea     rdx, [rbp+37h+var_60]
0x180007d66  mov     cl, [rbp+37h+arg_38]
0x180007d69  mov     byte ptr [rsp+0D0h+var_A0], cl
0x180007d6d  mov     cl, [rbp+37h+arg_30]
0x180007d70  mov     rax, [rax+160h]
0x180007d77  mov     byte ptr [rsp+0D0h+var_A8], cl
0x180007d7b  mov     rcx, [rbp+37h+arg_28]
0x180007d7f  mov     [rsp+0D0h+var_B0], rcx
0x180007d84  mov     rcx, r15
0x180007d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d8c  mov     r14d, dword ptr [rbp+37h+var_50]
0x180007d90  test    r14d, r14d
0x180007d93  jns     short loc_180007DBC
0x180007d95  mov     edx, r14d; char *
0x180007d98  lea     rcx, aHeader; "header"
0x180007d9f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007da4  mov     qword ptr [rdi], 0
0x180007dab  mov     qword ptr [rdi+8], 0
0x180007db3  mov     [rdi+10h], r14d
0x180007db7  jmp     loc_180007EA9
0x180007dbc  mov     r8, rsi
0x180007dbf  lea     rdx, [rbp+37h+var_60]
0x180007dc3  mov     rcx, rdi
0x180007dc6  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180007dcb  jmp     loc_180007EA9
0x180007dd0  mov     rdx, rsi
0x180007dd3  lea     rcx, [rbp+37h+var_60]
0x180007dd7  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180007ddc  mov     esi, dword ptr [rbp+37h+var_50]
0x180007ddf  test    esi, esi
0x180007de1  jns     short loc_180007E08
0x180007de3  mov     edx, esi; char *
0x180007de5  lea     rcx, aInputcopy; "inputCopy"
0x180007dec  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007df1  mov     qword ptr [rdi], 0
0x180007df8  mov     qword ptr [rdi+8], 0
0x180007e00  mov     [rdi+10h], esi
0x180007e03  jmp     loc_180007EA9
0x180007e08  mov     cl, [rbp+37h+arg_38]
0x180007e0b  lea     r9, [rbp+37h+var_70]
0x180007e0f  mov     rax, [r15]
0x180007e12  lea     r8, [rbp+37h+var_60]
0x180007e16  mov     [rsp+0D0h+var_88], 0
0x180007e1f  lea     rdx, [rbp+37h+var_48]
0x180007e23  mov     [rsp+0D0h+var_90], cl
0x180007e27  mov     cl, [rbp+37h+arg_30]
0x180007e2a  mov     rax, [rax+158h]
0x180007e31  mov     [rsp+0D0h+var_98], cl
0x180007e35  mov     rcx, [rbp+37h+arg_28]
0x180007e39  mov     [rsp+0D0h+var_A0], rcx
0x180007e3e  mov     rcx, r15
0x180007e41  mov     [rsp+0D0h+var_A8], r14d
0x180007e46  mov     [rsp+0D0h+var_B0], r12
0x180007e4b  mov     [rbp+37h+var_70], 0
0x180007e53  mov     [rbp+37h+var_68], 0
0x180007e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e60  mov     esi, dword ptr [rbp+37h+var_38]
0x180007e63  test    esi, esi
0x180007e65  jns     short loc_180007E89
0x180007e67  mov     edx, esi; char *
0x180007e69  lea     rcx, aHeader; "header"
0x180007e70  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007e75  mov     qword ptr [rdi], 0
0x180007e7c  mov     qword ptr [rdi+8], 0
0x180007e84  mov     [rdi+10h], esi
0x180007e87  jmp     short loc_180007E99
0x180007e89  lea     r8, [rbp+37h+var_60]
0x180007e8d  mov     rcx, rdi
0x180007e90  lea     rdx, [rbp+37h+var_48]
0x180007e94  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180007e99  mov     rcx, [rbp+37h+var_40]; void *
0x180007e9d  test    rcx, rcx
0x180007ea0  jz      short loc_180007EA9
0x180007ea2  xor     edx, edx; struct std::nothrow_t *
0x180007ea4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007ea9  mov     rcx, [rbp+37h+var_58]; void *
0x180007ead  test    rcx, rcx
0x180007eb0  jz      short loc_180007EB9
0x180007eb2  xor     edx, edx; struct std::nothrow_t *
0x180007eb4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007eb9  mov     rax, rdi
0x180007ebc  add     rsp, 0A8h
0x180007ec3  pop     r15
0x180007ec5  pop     r14
0x180007ec7  pop     r12
0x180007ec9  pop     rdi
0x180007eca  pop     rsi
0x180007ecb  pop     rbp
0x180007ecc  retn
```
