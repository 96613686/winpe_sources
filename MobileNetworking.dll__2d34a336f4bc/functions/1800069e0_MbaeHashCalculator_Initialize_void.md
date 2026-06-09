# MbaeHashCalculator::Initialize(void)

- ea: `0x1800069e0`
- end: `0x180006bde`
- name: `?Initialize@MbaeHashCalculator@@QEAAJXZ`
- size: `510`
- prototype: `__int64 __fastcall(MbaeHashCalculator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006340`

## callees

- `0x1800069e0`
- `0x180008070`
- `0x180008ff0`
- `0x18000a21c`
- `0x18000b6f4`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180006a2f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180006a2f`
- `bcrypt!BCryptGetProperty` at `0x180006a62`
- `bcrypt!BCryptGetProperty` at `0x180006ab1`
- `bcrypt!BCryptGetProperty` at `0x180006a62`
- `bcrypt!BCryptGetProperty` at `0x180006ab1`

## pseudocode

```c
__int64 __fastcall MbaeHashCalculator::Initialize(MbaeHashCalculator *this)
{
  PVOID *v2; // rcx
  NTSTATUS Property; // edi
  void *v4; // rax
  void *v5; // rax
  unsigned __int64 v6; // rax
  void *v7; // rax
  __int64 v9; // rdx
  ULONG pcbResult; // [rsp+50h] [rbp+8h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_feb619c85fea375a922233db6a92786b_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  pcbResult = 0;
  if ( *(_BYTE *)this )
  {
    if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 0x10) == 0 )
      return 0;
    v9 = 13;
    goto LABEL_16;
  }
  Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 9, (LPCWSTR)this + 1, 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(*((BCRYPT_HANDLE *)this + 9), L"ObjectLength", (PUCHAR)this + 80, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v4 = operator new[](*((unsigned int *)this + 20), (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)this + 11) = v4;
      if ( v4 )
      {
        Property = BCryptGetProperty(
                     *((BCRYPT_HANDLE *)this + 9),
                     L"HashDigestLength",
                     (PUCHAR)this + 96,
                     4u,
                     &pcbResult,
                     0);
        if ( Property < 0 )
          goto LABEL_23;
        v5 = operator new[](*((unsigned int *)this + 24), (const struct std::nothrow_t *)&std::nothrow);
        *((_QWORD *)this + 13) = v5;
        if ( v5 )
        {
          v6 = 2LL * (unsigned int)(2 * *((_DWORD *)this + 24) + 1);
          if ( !is_mul_ok((unsigned int)(2 * *((_DWORD *)this + 24) + 1), 2u) )
            v6 = -1;
          v7 = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
          *((_QWORD *)this + 14) = v7;
          if ( v7 )
          {
            *(_BYTE *)this = 1;
            v2 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
              return 0;
            v9 = 14;
LABEL_16:
            WPP_SF_d(v2[2], v9, WPP_feb619c85fea375a922233db6a92786b_Traceguids, 0);
            return 0;
          }
        }
      }
      Property = -1073741801;
    }
  }
LABEL_23:
  MbaeHashCalculator::Cleanup(this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_feb619c85fea375a922233db6a92786b_Traceguids,
      (unsigned int)Property);
  return Property | 0x10000000u;
}

```

## disassembly

```asm
0x1800069e0  push    rbx
0x1800069e2  push    rbp
0x1800069e3  push    r15
0x1800069e5  sub     rsp, 30h
0x1800069e9  mov     rbx, rcx
0x1800069ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069f3  lea     r15, WPP_GLOBAL_Control
0x1800069fa  cmp     rcx, r15
0x1800069fd  jnz     loc_180006B5F
0x180006a03  xor     ebp, ebp
0x180006a05  mov     [rsp+48h+arg_8], rsi
0x180006a0a  mov     [rsp+48h+arg_10], rdi
0x180006a0f  mov     [rsp+48h+arg_18], r14
0x180006a14  mov     [rsp+48h+arg_0], ebp
0x180006a18  cmp     [rbx], bpl
0x180006a1b  jnz     loc_180006B8A
0x180006a21  lea     rdx, [rbx+2]; pszAlgId
0x180006a25  xor     r9d, r9d; dwFlags
0x180006a28  xor     r8d, r8d; pszImplementation
0x180006a2b  lea     rcx, [rbx+48h]; phAlgorithm
0x180006a2f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180006a35  mov     edi, eax
0x180006a37  test    eax, eax
0x180006a39  js      loc_180006BA1
0x180006a3f  mov     rcx, [rbx+48h]; hObject
0x180006a43  lea     rax, [rsp+48h+arg_0]
0x180006a48  mov     [rsp+48h+dwFlags], ebp; dwFlags
0x180006a4c  lea     r8, [rbx+50h]; pbOutput
0x180006a50  mov     r9d, 4; cbOutput
0x180006a56  mov     [rsp+48h+pcbResult], rax; pcbResult
0x180006a5b  lea     rdx, pszProperty; "ObjectLength"
0x180006a62  call    cs:__imp_BCryptGetProperty
0x180006a68  mov     edi, eax
0x180006a6a  test    eax, eax
0x180006a6c  js      loc_180006BA1
0x180006a72  mov     ecx, [rbx+50h]; unsigned __int64
0x180006a75  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006a7c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006a81  mov     [rbx+58h], rax
0x180006a85  test    rax, rax
0x180006a88  jz      loc_180006B9C
0x180006a8e  mov     rcx, [rbx+48h]; hObject
0x180006a92  lea     rax, [rsp+48h+arg_0]
0x180006a97  mov     [rsp+48h+dwFlags], ebp; dwFlags
0x180006a9b  lea     r8, [rbx+60h]; pbOutput
0x180006a9f  mov     r9d, 4; cbOutput
0x180006aa5  mov     [rsp+48h+pcbResult], rax; pcbResult
0x180006aaa  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180006ab1  call    cs:__imp_BCryptGetProperty
0x180006ab7  mov     edi, eax
0x180006ab9  test    eax, eax
0x180006abb  js      loc_180006BA1
0x180006ac1  mov     ecx, [rbx+60h]; unsigned __int64
0x180006ac4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006acb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006ad0  mov     [rbx+68h], rax
0x180006ad4  test    rax, rax
0x180006ad7  jz      loc_180006B9C
0x180006add  mov     eax, [rbx+60h]
0x180006ae0  lea     ecx, ds:1[rax*2]
0x180006ae7  mov     eax, 2
0x180006aec  mul     rcx
0x180006aef  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006af6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006afd  cmovb   rax, rcx
0x180006b01  mov     rcx, rax; unsigned __int64
0x180006b04  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006b09  mov     [rbx+70h], rax
0x180006b0d  test    rax, rax
0x180006b10  jz      loc_180006B9C
0x180006b16  mov     byte ptr [rbx], 1
0x180006b19  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b20  cmp     rcx, r15
0x180006b23  jnz     short loc_180006B3F
0x180006b25  xor     eax, eax
0x180006b27  mov     r14, [rsp+48h+arg_18]
0x180006b2c  mov     rdi, [rsp+48h+arg_10]
0x180006b31  mov     rsi, [rsp+48h+arg_8]
0x180006b36  add     rsp, 30h
0x180006b3a  pop     r15
0x180006b3c  pop     rbp
0x180006b3d  pop     rbx
0x180006b3e  retn
0x180006b3f  test    byte ptr [rcx+1Ch], 10h
0x180006b43  jz      short loc_180006B25
0x180006b45  mov     edx, 0Eh
0x180006b4a  mov     rcx, [rcx+10h]
0x180006b4e  lea     r8, WPP_feb619c85fea375a922233db6a92786b_Traceguids
0x180006b55  xor     r9d, r9d
0x180006b58  call    WPP_SF_d
0x180006b5d  jmp     short loc_180006B25
0x180006b5f  test    byte ptr [rcx+1Ch], 10h
0x180006b63  jz      loc_180006A03
0x180006b69  mov     rcx, [rcx+10h]
0x180006b6d  lea     r8, WPP_feb619c85fea375a922233db6a92786b_Traceguids
0x180006b74  mov     edx, 0Ch
0x180006b79  call    WPP_SF_
0x180006b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b85  jmp     loc_180006A03
0x180006b8a  cmp     rcx, r15
0x180006b8d  jz      short loc_180006B25
0x180006b8f  test    byte ptr [rcx+1Ch], 10h
0x180006b93  jz      short loc_180006B25
0x180006b95  mov     edx, 0Dh
0x180006b9a  jmp     short loc_180006B4A
0x180006b9c  mov     edi, 0C0000017h
0x180006ba1  mov     rcx, rbx; this
0x180006ba4  call    ?Cleanup@MbaeHashCalculator@@AEAAXXZ; MbaeHashCalculator::Cleanup(void)
0x180006ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bb0  cmp     rcx, r15
0x180006bb3  jz      short loc_180006BD3
0x180006bb5  test    byte ptr [rcx+1Ch], 10h
0x180006bb9  jz      short loc_180006BD3
0x180006bbb  mov     rcx, [rcx+10h]
0x180006bbf  lea     r8, WPP_feb619c85fea375a922233db6a92786b_Traceguids
0x180006bc6  mov     edx, 0Fh
0x180006bcb  mov     r9d, edi
0x180006bce  call    WPP_SF_d
0x180006bd3  bts     edi, 1Ch
0x180006bd7  mov     eax, edi
0x180006bd9  jmp     loc_180006B27
```
