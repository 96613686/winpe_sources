# DcaUtil::GenerateRandomCred

- ea: `0x180058c8c`
- end: `0x180058f33`
- name: `DcaUtil::GenerateRandomCred`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a5e58`

## callees

- `0x18000782c`
- `0x180047228`
- `0x18004826c`
- `0x180048434`
- `0x180058c8c`
- `0x180058f3c`
- `0x1800811ac`
- `0x18008fb14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058cd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058cd6`
- `bcrypt!BCryptGenRandom` at `0x180058d54`
- `bcrypt!BCryptGenRandom` at `0x180058d54`

## string_xrefs

- `0x180058cb2`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x180058d1c`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x180058d66`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x180058e94`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x180058ee1`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x180058f12`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DcaUtil::GenerateRandomCred(UCHAR *a1, _QWORD *a2)
{
  _WORD *v4; // rax
  _BYTE *v5; // rbx
  _WORD *v6; // rcx
  int v7; // eax
  void *v8; // rdx
  PUCHAR v9; // rdi
  NTSTATUS v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // esi
  __int64 v13; // r10
  __int64 v14; // r9
  __int64 v15; // rax
  UCHAR v16; // cl
  unsigned __int64 v17; // r8
  int v18; // ecx
  int v19; // ecx
  unsigned __int64 v20; // r8
  __int16 v21; // cx
  __int64 v22; // rsi
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // ebp
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // [rsp+20h] [rbp-48h]
  int v29; // [rsp+20h] [rbp-48h]
  char *v30; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  PUCHAR pbBuffer; // [rsp+70h] [rbp+8h] BYREF

  pbBuffer = a1;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F0,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
      (const char *)0x80004003LL,
      v28);
    return 2147500035LL;
  }
  *a2 = 0;
  v4 = CoTaskMemAlloc(0x40u);
  v5 = v4;
  if ( !v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F5,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
      (const char *)0x8007000ELL,
      v28);
    return 2147942414LL;
  }
  v6 = v4 + 32;
  do
    *v4++ = 0;
  while ( v4 != v6 );
  *(_WORD *)v5 = 0;
  v7 = DcaUtil::ValidatePassword(v6, v5);
  if ( v7 >= 0 )
  {
    *a2 = v5;
    return 0;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x4FA,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
    (const char *)(unsigned int)v7,
    v28);
  wil::make_unique_cotaskmem_secure_nothrow<unsigned char [0]>(&pbBuffer, v8);
  v9 = pbBuffer;
  if ( !pbBuffer )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x502,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
      (const char *)0x8007000ELL,
      v29);
    wil::cotaskmem_secure_deleter::operator()<unsigned short>(v27, v5);
    return 2147942414LL;
  }
  v10 = BCryptGenRandom(0, pbBuffer, 0x3Eu, 2u);
  if ( v10 >= 0 )
  {
    v13 = 0;
    v14 = 0;
    do
    {
      if ( (unsigned int)v14 < 8 )
      {
        v16 = v14;
      }
      else
      {
        v15 = (unsigned int)v13;
        v13 = (unsigned int)(v13 + 1);
        v16 = v9[v15];
      }
      v17 = v9[v13];
      v13 = (unsigned int)(v13 + 1);
      v18 = v16 & 3;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v20 = v17 % 0x1A;
          if ( v19 == 1 )
            v21 = word_1800E8D70[v20];
          else
            v21 = word_1800E8DD0[v20];
        }
        else
        {
          v21 = word_1800E8DA8[v17 & 3];
        }
      }
      else
      {
        v21 = word_1800E8E10[v17 % 0xA];
      }
      *(_WORD *)&v5[2 * v14] = v21;
      v14 = (unsigned int)(v14 + 1);
    }
    while ( (unsigned int)v14 < 0x1F );
    v22 = 0;
    while ( 1 )
    {
      v23 = (unsigned int)dword_1800E8DC0[v22];
      *(_WORD *)&v5[2 * v23] = 0;
      v25 = DcaUtil::ValidatePassword(v23, v5);
      if ( v25 != -2147022193 )
        break;
      v22 = (unsigned int)(v22 + 1);
      if ( (unsigned int)v22 >= 4 )
        goto LABEL_29;
    }
    if ( v25 < 0 )
    {
LABEL_29:
      LODWORD(v30) = dword_1800E8DC0[v22];
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x540,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
        (const char *)(unsigned int)v25,
        (int)"ValidatePassword length=%d",
        v30);
      if ( v9 )
        wil::cotaskmem_secure_deleter::operator()<unsigned short>(v26, v9);
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v26, v5);
      return (unsigned int)v25;
    }
    *a2 = v5;
    if ( v9 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v24, v9);
    return 0;
  }
  v12 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x507,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
          (const char *)(unsigned int)v10,
          v29);
  if ( v9 )
    wil::cotaskmem_secure_deleter::operator()<unsigned short>(v11, v9);
  wil::cotaskmem_secure_deleter::operator()<unsigned short>(v11, v5);
  return v12;
}

```

## disassembly

```asm
0x180058c8c  mov     [rsp+pbBuffer], rcx
0x180058c91  push    rbx
0x180058c92  push    rbp
0x180058c93  push    rsi
0x180058c94  push    rdi
0x180058c95  push    r14
0x180058c97  push    r15
0x180058c99  sub     rsp, 38h
0x180058c9d  mov     r14, rdx
0x180058ca0  test    rdx, rdx
0x180058ca3  jnz     short loc_180058CCA
0x180058ca5  mov     rcx, [rsp+68h]; this
0x180058caa  mov     ebx, 80004003h
0x180058caf  mov     r9d, ebx; char *
0x180058cb2  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x180058cb9  mov     edx, 4F0h; void *
0x180058cbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058cc3  mov     eax, ebx
0x180058cc5  jmp     loc_180058F26
0x180058cca  mov     qword ptr [rdx], 0
0x180058cd1  mov     ecx, 40h ; '@'; cb
0x180058cd6  call    cs:__imp_CoTaskMemAlloc
0x180058cdc  mov     rbx, rax
0x180058cdf  test    rax, rax
0x180058ce2  jz      loc_180058F05
0x180058ce8  lea     rcx, [rax+40h]
0x180058cec  cmp     rax, rcx
0x180058cef  jz      short loc_180058CFF
0x180058cf1  xor     edx, edx
0x180058cf3  mov     [rax], dx
0x180058cf6  add     rax, 2
0x180058cfa  cmp     rax, rcx
0x180058cfd  jnz     short loc_180058CF1
0x180058cff  xor     eax, eax
0x180058d01  mov     [rbx], ax
0x180058d04  mov     rdx, rbx
0x180058d07  call    DcaUtil__ValidatePassword
0x180058d0c  mov     rcx, [rsp+68h]; this
0x180058d11  test    eax, eax
0x180058d13  jns     loc_180058EFE
0x180058d19  mov     r9d, eax; char *
0x180058d1c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x180058d23  mov     edx, 4FAh; void *
0x180058d28  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180058d2d  lea     rcx, [rsp+68h+pbBuffer]
0x180058d32  call    ??$make_unique_cotaskmem_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUcotaskmem_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_secure_nothrow<uchar [0]>(unsigned __int64)
0x180058d37  mov     rdi, [rsp+68h+pbBuffer]
0x180058d3c  test    rdi, rdi
0x180058d3f  jz      loc_180058ED4
0x180058d45  mov     r9d, 2; dwFlags
0x180058d4b  lea     r8d, [r9+3Ch]; cbBuffer
0x180058d4f  mov     rdx, rdi; pbBuffer
0x180058d52  xor     ecx, ecx; hAlgorithm
0x180058d54  call    cs:__imp_BCryptGenRandom
0x180058d5a  test    eax, eax
0x180058d5c  jns     short loc_180058D97
0x180058d5e  mov     rcx, [rsp+68h]; this
0x180058d63  mov     r9d, eax; char *
0x180058d66  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x180058d6d  mov     edx, 507h; void *
0x180058d72  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180058d77  mov     esi, eax
0x180058d79  test    rdi, rdi
0x180058d7c  jz      short loc_180058D87
0x180058d7e  mov     rdx, rdi
0x180058d81  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180058d86  nop
0x180058d87  mov     rdx, rbx
0x180058d8a  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180058d8f  nop
0x180058d90  mov     eax, esi
0x180058d92  jmp     loc_180058F26
0x180058d97  xor     r10d, r10d
0x180058d9a  xor     r9d, r9d
0x180058d9d  mov     r11, 4EC4EC4EC4EC4EC5h
0x180058da7  lea     r15, __ImageBase
0x180058dae  cmp     r9d, 8
0x180058db2  jb      short loc_180058DC0
0x180058db4  mov     eax, r10d
0x180058db7  inc     r10d
0x180058dba  movzx   ecx, byte ptr [rax+rdi]
0x180058dbe  jmp     short loc_180058DC3
0x180058dc0  mov     ecx, r9d
0x180058dc3  movzx   r8d, byte ptr [r10+rdi]
0x180058dc8  inc     r10d
0x180058dcb  and     ecx, 3
0x180058dce  jz      short loc_180058E10
0x180058dd0  sub     ecx, 1
0x180058dd3  jz      short loc_180058E01
0x180058dd5  mov     rax, r11
0x180058dd8  mul     r8
0x180058ddb  shr     rdx, 3
0x180058ddf  imul    rax, rdx, 1Ah
0x180058de3  sub     r8, rax
0x180058de6  cmp     ecx, 1
0x180058de9  jz      short loc_180058DF6
0x180058deb  movzx   ecx, ds:rva word_1800E8DD0[r15+r8*2]
0x180058df4  jmp     short loc_180058E34
0x180058df6  movzx   ecx, ds:rva word_1800E8D70[r15+r8*2]
0x180058dff  jmp     short loc_180058E34
0x180058e01  and     r8d, 3
0x180058e05  movzx   ecx, ds:rva word_1800E8DA8[r15+r8*2]
0x180058e0e  jmp     short loc_180058E34
0x180058e10  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180058e1a  mul     r8
0x180058e1d  shr     rdx, 3
0x180058e21  lea     rax, [rdx+rdx*4]
0x180058e25  add     rax, rax
0x180058e28  sub     r8, rax
0x180058e2b  movzx   ecx, ds:rva word_1800E8E10[r15+r8*2]
0x180058e34  mov     [rbx+r9*2], cx
0x180058e39  inc     r9d
0x180058e3c  cmp     r9d, 1Fh
0x180058e40  jb      loc_180058DAE
0x180058e46  xor     esi, esi
0x180058e48  mov     ecx, ds:rva dword_1800E8DC0[r15+rsi*4]
0x180058e50  xor     eax, eax
0x180058e52  mov     [rbx+rcx*2], ax
0x180058e56  mov     rdx, rbx
0x180058e59  call    DcaUtil__ValidatePassword
0x180058e5e  mov     ebp, eax
0x180058e60  cmp     eax, 80070A8Fh
0x180058e65  jnz     short loc_180058E70
0x180058e67  inc     esi
0x180058e69  cmp     esi, 4
0x180058e6c  jb      short loc_180058E48
0x180058e6e  jmp     short loc_180058E74
0x180058e70  test    ebp, ebp
0x180058e72  jns     short loc_180058EC1
0x180058e74  mov     rcx, [rsp+68h]; this
0x180058e79  mov     eax, ds:rva dword_1800E8DC0[r15+rsi*4]
0x180058e81  mov     dword ptr [rsp+68h+var_40], eax; char *
0x180058e85  lea     rax, aValidatepasswo; "ValidatePassword length=%d"
0x180058e8c  mov     qword ptr [rsp+68h+var_48], rax; int
0x180058e91  mov     r9d, ebp; char *
0x180058e94  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x180058e9b  mov     edx, 540h; void *
0x180058ea0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180058ea5  nop
0x180058ea6  test    rdi, rdi
0x180058ea9  jz      short loc_180058EB4
0x180058eab  mov     rdx, rdi
0x180058eae  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180058eb3  nop
0x180058eb4  mov     rdx, rbx
0x180058eb7  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180058ebc  nop
0x180058ebd  mov     eax, ebp
0x180058ebf  jmp     short loc_180058F26
0x180058ec1  mov     [r14], rbx
0x180058ec4  test    rdi, rdi
0x180058ec7  jz      short loc_180058ED2
0x180058ec9  mov     rdx, rdi
0x180058ecc  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180058ed1  nop
0x180058ed2  jmp     short loc_180058F01
0x180058ed4  mov     rcx, [rsp+68h]; this
0x180058ed9  mov     edi, 8007000Eh
0x180058ede  mov     r9d, edi; char *
0x180058ee1  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x180058ee8  mov     edx, 502h; void *
0x180058eed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058ef2  nop
0x180058ef3  mov     rdx, rbx
0x180058ef6  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180058efb  nop
0x180058efc  jmp     short loc_180058F24
0x180058efe  mov     [r14], rbx
0x180058f01  xor     eax, eax
0x180058f03  jmp     short loc_180058F26
0x180058f05  mov     rcx, [rsp+68h]; this
0x180058f0a  mov     edi, 8007000Eh
0x180058f0f  mov     r9d, edi; char *
0x180058f12  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x180058f19  mov     edx, 4F5h; void *
0x180058f1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058f23  nop
0x180058f24  mov     eax, edi
0x180058f26  add     rsp, 38h
0x180058f2a  pop     r15
0x180058f2c  pop     r14
0x180058f2e  pop     rdi
0x180058f2f  pop     rsi
0x180058f30  pop     rbp
0x180058f31  pop     rbx
0x180058f32  retn
```
