# CheckCapabilityByPackageFullName(ushort const *,ushort const *)

- ea: `0x180064af0`
- end: `0x180064da4`
- name: `?CheckCapabilityByPackageFullName@@YAJPEBG0@Z`
- size: `692`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c2a4`
- `0x18007ff20`
- `0x180093020`

## callees

- `0x1800049a0`
- `0x18000c964`
- `0x180064af0`
- `0x180065a0c`
- `0x18009d010`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180064bf5`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180064bf5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180064cd0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180064cd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064c30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064c8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064b77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064c30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064c4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064c8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064caa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d93`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180064b4a`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x180064b4a`

## string_xrefs

- `0x180064b5d`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`
- `0x180064c0a`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`
- `0x180064c65`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`
- `0x180064cf3`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\accesscontrolhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckCapabilityByPackageFullName(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // edi
  __int64 v6; // rcx
  const unsigned __int16 *v7; // rax
  __int16 v8; // cx
  int v9; // eax
  unsigned int v10; // esi
  HLOCAL *v11; // rbx
  HLOCAL *v12; // rdi
  HLOCAL *v13; // rdi
  PSID *v14; // rbx
  PSID *v15; // rdi
  HLOCAL *v16; // rdi
  HLOCAL *v17; // rbx
  HLOCAL *v18; // rdi
  int v19; // [rsp+50h] [rbp-49h] BYREF
  HLOCAL *v20; // [rsp+58h] [rbp-41h] BYREF
  __int128 v21; // [rsp+60h] [rbp-39h] BYREF
  _BYTE pSid2[48]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v23[48]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v19 = 0;
  v20 = 0;
  v3 = QueryApplicationCapabilities(a1, &v20, &v19, 0);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v21 = 0;
    if ( a2 )
    {
      v6 = 0x7FFF;
      v7 = a2;
      do
      {
        if ( !*v7 )
          break;
        ++v7;
        --v6;
      }
      while ( v6 );
      if ( !v6 )
      {
        v10 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xFC,
                (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
                (const char *)0xC000000DLL,
                0);
        v11 = v20;
        v13 = &v20[v19];
        if ( v20 != v13 )
        {
          do
            LocalFree(*v11++);
          while ( v11 != v13 );
          v11 = v20;
        }
        if ( !v11 )
          return v10;
        goto LABEL_30;
      }
      v8 = 2 * v6;
      LOWORD(v21) = -2 - v8;
      WORD1(v21) = -v8;
      *((_QWORD *)&v21 + 1) = a2;
    }
    v9 = RtlDeriveCapabilitySidsFromName(&v21, v23, pSid2);
    if ( v9 >= 0 )
    {
      v14 = v20;
      v15 = &v20[v19];
      while ( v14 != v15 )
      {
        if ( EqualSid(*v14, pSid2) )
        {
          v17 = v20;
          v18 = &v20[v19];
          if ( v20 != v18 )
          {
            do
              LocalFree(*v17++);
            while ( v17 != v18 );
            v17 = v20;
          }
          if ( v17 )
            ((void (__fastcall *)(HLOCAL *))LocalFree)(v17);
          return 0;
        }
        ++v14;
      }
      v10 = -2147024891;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
        (const char *)0x80070005LL,
        0);
      v11 = v20;
      v16 = &v20[v19];
      if ( v20 != v16 )
      {
        do
          LocalFree(*v11++);
        while ( v11 != v16 );
        v11 = v20;
      }
      if ( !v11 )
        return v10;
    }
    else
    {
      v10 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xFD,
              (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
              (const char *)(unsigned int)v9,
              0);
      v11 = v20;
      v12 = &v20[v19];
      if ( v20 != v12 )
      {
        do
          LocalFree(*v11++);
        while ( v11 != v12 );
        v11 = v20;
      }
      if ( !v11 )
        return v10;
    }
LABEL_30:
    ((void (__fastcall *)(HLOCAL *))LocalFree)(v11);
    return v10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xEF,
    (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\accesscontrolhelper.cpp",
    (const char *)(unsigned int)v3,
    0);
  if ( v20 )
    ((void (*)(void))LocalFree)();
  return v4;
}

```

## disassembly

```asm
0x180064af0  mov     [rsp-8+arg_8], rbx
0x180064af5  mov     [rsp-8+arg_10], rsi
0x180064afa  push    rbp
0x180064afb  push    rdi
0x180064afc  push    r14
0x180064afe  lea     rbp, [rsp-47h]
0x180064b03  sub     rsp, 0E0h
0x180064b0a  mov     rax, cs:__security_cookie
0x180064b11  xor     rax, rsp
0x180064b14  mov     [rbp+57h+var_20], rax
0x180064b18  mov     rbx, rdx
0x180064b1b  xor     r14d, r14d
0x180064b1e  mov     [rbp+57h+var_A0], r14d
0x180064b22  mov     [rbp+57h+var_98], r14
0x180064b26  mov     [rsp+0F0h+var_B0], r14
0x180064b2b  mov     [rsp+0F0h+var_B8], r14
0x180064b30  mov     [rsp+0F0h+var_C0], r14
0x180064b35  mov     [rsp+0F0h+var_C8], r14
0x180064b3a  mov     qword ptr [rsp+0F0h+var_D0], r14; int
0x180064b3f  xor     r9d, r9d
0x180064b42  lea     r8, [rbp+57h+var_A0]
0x180064b46  lea     rdx, [rbp+57h+var_98]
0x180064b4a  call    cs:__imp_QueryApplicationCapabilities
0x180064b50  mov     edi, eax
0x180064b52  test    eax, eax
0x180064b54  jns     short loc_180064B8B
0x180064b56  mov     rcx, [rbp+5Fh]; this
0x180064b5a  mov     r9d, eax; char *
0x180064b5d  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180064b64  mov     edx, 0EFh; void *
0x180064b69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064b6e  mov     rcx, [rbp+57h+var_98]
0x180064b72  test    rcx, rcx
0x180064b75  jz      short loc_180064B84
0x180064b77  mov     rax, cs:__imp_LocalFree
0x180064b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b83  nop
0x180064b84  mov     eax, edi
0x180064b86  jmp     loc_180064D41
0x180064b8b  xorps   xmm0, xmm0
0x180064b8e  movups  [rbp+57h+var_90], xmm0
0x180064b92  test    rbx, rbx
0x180064b95  jz      short loc_180064BE9
0x180064b97  mov     ecx, 7FFFh
0x180064b9c  mov     rax, rbx
0x180064b9f  mov     edx, 2
0x180064ba4  cmp     [rax], r14w
0x180064ba8  jz      short loc_180064BB3
0x180064baa  add     rax, rdx
0x180064bad  sub     rcx, 1
0x180064bb1  jnz     short loc_180064BA4
0x180064bb3  mov     rax, rcx
0x180064bb6  neg     rax
0x180064bb9  sbb     r9d, r9d
0x180064bbc  not     r9d
0x180064bbf  and     r9d, 0C000000Dh; char *
0x180064bc6  test    rcx, rcx
0x180064bc9  jz      loc_180064C61
0x180064bcf  add     cx, cx
0x180064bd2  mov     eax, 0FFFEh
0x180064bd7  sub     ax, cx
0x180064bda  mov     word ptr [rbp+57h+var_90], ax
0x180064bde  add     ax, dx
0x180064be1  mov     word ptr [rbp+57h+var_90+2], ax
0x180064be5  mov     qword ptr [rbp+57h+var_90+8], rbx
0x180064be9  lea     r8, [rbp+57h+pSid2]
0x180064bed  lea     rdx, [rbp+57h+var_50]
0x180064bf1  lea     rcx, [rbp+57h+var_90]
0x180064bf5  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180064bfb  test    eax, eax
0x180064bfd  jns     loc_180064CBC
0x180064c03  mov     rcx, [rbp+5Fh]; this
0x180064c07  mov     r9d, eax; char *
0x180064c0a  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180064c11  mov     edx, 0FDh; void *
0x180064c16  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180064c1b  mov     esi, eax
0x180064c1d  mov     rbx, [rbp+57h+var_98]
0x180064c21  mov     ecx, [rbp+57h+var_A0]
0x180064c24  lea     rdi, [rbx+rcx*8]
0x180064c28  cmp     rbx, rdi
0x180064c2b  jz      short loc_180064C43
0x180064c2d  mov     rcx, [rbx]; hMem
0x180064c30  call    cs:__imp_LocalFree
0x180064c36  add     rbx, 8
0x180064c3a  cmp     rbx, rdi
0x180064c3d  jnz     short loc_180064C2D
0x180064c3f  mov     rbx, [rbp+57h+var_98]
0x180064c43  test    rbx, rbx
0x180064c46  jz      loc_180064D3F
0x180064c4c  mov     rcx, rbx
0x180064c4f  mov     rax, cs:__imp_LocalFree
0x180064c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c5b  nop
0x180064c5c  jmp     loc_180064D3F
0x180064c61  mov     rcx, [rbp+5Fh]; this
0x180064c65  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180064c6c  mov     edx, 0FCh; void *
0x180064c71  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180064c76  mov     esi, eax
0x180064c78  mov     rbx, [rbp+57h+var_98]
0x180064c7c  mov     ecx, [rbp+57h+var_A0]
0x180064c7f  lea     rdi, [rbx+rcx*8]
0x180064c83  cmp     rbx, rdi
0x180064c86  jz      short loc_180064C9E
0x180064c88  mov     rcx, [rbx]; hMem
0x180064c8b  call    cs:__imp_LocalFree
0x180064c91  add     rbx, 8
0x180064c95  cmp     rbx, rdi
0x180064c98  jnz     short loc_180064C88
0x180064c9a  mov     rbx, [rbp+57h+var_98]
0x180064c9e  test    rbx, rbx
0x180064ca1  jz      loc_180064D3F
0x180064ca7  mov     rcx, rbx
0x180064caa  mov     rax, cs:__imp_LocalFree
0x180064cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064cb6  nop
0x180064cb7  jmp     loc_180064D3F
0x180064cbc  mov     rbx, [rbp+57h+var_98]
0x180064cc0  mov     eax, [rbp+57h+var_A0]
0x180064cc3  lea     rdi, [rbx+rax*8]
0x180064cc7  jmp     short loc_180064CE2
0x180064cc9  lea     rdx, [rbp+57h+pSid2]; pSid2
0x180064ccd  mov     rcx, [rbx]; pSid1
0x180064cd0  call    cs:__imp_EqualSid
0x180064cd6  test    eax, eax
0x180064cd8  jnz     loc_180064D65
0x180064cde  add     rbx, 8
0x180064ce2  cmp     rbx, rdi
0x180064ce5  jnz     short loc_180064CC9
0x180064ce7  mov     rcx, [rbp+5Fh]; this
0x180064ceb  mov     esi, 80070005h
0x180064cf0  mov     r9d, esi; char *
0x180064cf3  lea     r8, aOnecoreuapDsNf_6; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180064cfa  mov     edx, 10Ah; void *
0x180064cff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064d04  mov     rbx, [rbp+57h+var_98]
0x180064d08  mov     eax, [rbp+57h+var_A0]
0x180064d0b  lea     rdi, [rbx+rax*8]
0x180064d0f  cmp     rbx, rdi
0x180064d12  jz      short loc_180064D2A
0x180064d14  mov     rcx, [rbx]; hMem
0x180064d17  call    cs:__imp_LocalFree
0x180064d1d  add     rbx, 8
0x180064d21  cmp     rbx, rdi
0x180064d24  jnz     short loc_180064D14
0x180064d26  mov     rbx, [rbp+57h+var_98]
0x180064d2a  test    rbx, rbx
0x180064d2d  jz      short loc_180064D3F
0x180064d2f  mov     rcx, rbx
0x180064d32  mov     rax, cs:__imp_LocalFree
0x180064d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d3e  nop
0x180064d3f  mov     eax, esi
0x180064d41  mov     rcx, [rbp+57h+var_20]
0x180064d45  xor     rcx, rsp; StackCookie
0x180064d48  call    __security_check_cookie
0x180064d4d  lea     r11, [rsp+0F0h+var_10]
0x180064d55  mov     rbx, [r11+28h]
0x180064d59  mov     rsi, [r11+30h]
0x180064d5d  mov     rsp, r11
0x180064d60  pop     r14
0x180064d62  pop     rdi
0x180064d63  pop     rbp
0x180064d64  retn
0x180064d65  mov     rbx, [rbp+57h+var_98]
0x180064d69  mov     eax, [rbp+57h+var_A0]
0x180064d6c  lea     rdi, [rbx+rax*8]
0x180064d70  cmp     rbx, rdi
0x180064d73  jz      short loc_180064D8B
0x180064d75  mov     rcx, [rbx]; hMem
0x180064d78  call    cs:__imp_LocalFree
0x180064d7e  add     rbx, 8
0x180064d82  cmp     rbx, rdi
0x180064d85  jnz     short loc_180064D75
0x180064d87  mov     rbx, [rbp+57h+var_98]
0x180064d8b  test    rbx, rbx
0x180064d8e  jz      short loc_180064DA0
0x180064d90  mov     rcx, rbx
0x180064d93  mov     rax, cs:__imp_LocalFree
0x180064d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d9f  nop
0x180064da0  xor     eax, eax
0x180064da2  jmp     short loc_180064D41
```
