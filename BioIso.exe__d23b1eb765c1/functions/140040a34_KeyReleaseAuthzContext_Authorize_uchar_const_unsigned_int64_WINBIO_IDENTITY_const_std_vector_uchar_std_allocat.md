# KeyReleaseAuthzContext::Authorize(uchar const *,unsigned __int64,_WINBIO_IDENTITY const *,std::vector<uchar,std::allocator<uchar>> *,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x140040a34`
- end: `0x140040b8b`
- name: `?Authorize@KeyReleaseAuthzContext@@QEAAJPEBE_KPEBU_WINBIO_IDENTITY@@PEAV?$vector@EV?$allocator@E@std@@@std@@3@Z`
- size: `343`
- prototype: `__int64 __fastcall(__int64, int, int, _DWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140054610`

## callees

- `0x14000a420`
- `0x14000ae0c`
- `0x14000d5d0`
- `0x140040504`
- `0x1400408d0`
- `0x140040a34`
- `0x14007ede0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x140040aa7`
- `ntdll!RtlEqualSid` at `0x140040aa7`

## string_xrefs

- `0x140040a64`: `onecore\ds\security\biometrics\service\trustlet\exe\authorizationcontext.cpp`
- `0x140040b14`: `onecore\ds\security\biometrics\service\trustlet\exe\authorizationcontext.cpp`

## pseudocode

```c
__int64 __fastcall KeyReleaseAuthzContext::Authorize(__int64 a1, int a2, int a3, _DWORD *a4, __int64 a5, __int64 a6)
{
  __int64 *v10; // r10
  __int64 v11; // rbx
  __int64 v12; // r14
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // [rsp+20h] [rbp-40h]
  int v18[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h]
  __int64 v20; // [rsp+48h] [rbp-18h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  if ( *a4 == 3 )
  {
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v20);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v18);
    v11 = *v10;
    v12 = v10[1];
    while ( v11 != v12 )
    {
      if ( RtlEqualSid(a4 + 2, *(PSID *)v11) )
      {
        if ( *(_QWORD *)(v11 + 24) == *(_QWORD *)(v11 + 32) )
        {
          v14 = -2147024891;
          v15 = 2147942405LL;
          v16 = 121;
          goto LABEL_10;
        }
        std::vector<unsigned char>::operator=(&v20, v11 + 24);
        std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(v11 + 24, 0, 0);
        v13 = VsmUtils::SignTrustletData(a2, a3, v20, (int)v21 - (int)v20, (__int64)v18);
        v14 = v13;
        if ( v13 < 0 )
        {
          v15 = (unsigned int)v13;
          v16 = 128;
LABEL_10:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\authorizationcontext.cpp",
            (const char *)v15,
            v17);
          goto LABEL_15;
        }
      }
      v11 += 48;
    }
    if ( *(_QWORD *)v18 == v19 )
    {
      v14 = -2146893807;
      v15 = 2148073489LL;
      v16 = 132;
      goto LABEL_10;
    }
    std::vector<unsigned char>::operator=(a5, &v20);
    std::vector<unsigned char>::operator=(a6, v18);
    v14 = 0;
LABEL_15:
    std::vector<unsigned char>::_Tidy(v18);
    std::vector<unsigned char>::_Tidy(&v20);
    return v14;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\authorizationcontext.cpp",
      (const char *)0x80070057LL,
      v17);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140040a34  push    rbp
0x140040a36  push    rbx
0x140040a37  push    rsi
0x140040a38  push    rdi
0x140040a39  push    r12
0x140040a3b  push    r14
0x140040a3d  push    r15
0x140040a3f  mov     rbp, rsp
0x140040a42  sub     rsp, 60h
0x140040a46  mov     rsi, r9
0x140040a49  mov     r15, r8
0x140040a4c  mov     r12, rdx
0x140040a4f  mov     r10, rcx
0x140040a52  cmp     dword ptr [r9], 3
0x140040a56  jz      short loc_140040A7C
0x140040a58  mov     rcx, [rbp+38h]; this
0x140040a5c  mov     ebx, 80070057h
0x140040a61  mov     r9d, ebx; char *
0x140040a64  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\biometrics\\serv"...
0x140040a6b  mov     edx, 70h ; 'p'; void *
0x140040a70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040a75  mov     eax, ebx
0x140040a77  jmp     loc_140040B7B
0x140040a7c  lea     rcx, [rbp+var_18]
0x140040a80  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140040a85  nop
0x140040a86  lea     rcx, [rbp+var_30]
0x140040a8a  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140040a8f  nop
0x140040a90  mov     rbx, [r10]
0x140040a93  mov     r14, [r10+8]
0x140040a97  cmp     rbx, r14
0x140040a9a  jz      loc_140040B31
0x140040aa0  lea     rcx, [rsi+8]; Sid1
0x140040aa4  mov     rdx, [rbx]; Sid2
0x140040aa7  call    cs:__imp_RtlEqualSid
0x140040aae  nop     dword ptr [rax+rax+00h]
0x140040ab3  test    al, al
0x140040ab5  jz      short loc_140040B02
0x140040ab7  lea     rdi, [rbx+18h]
0x140040abb  mov     rax, [rbx+20h]
0x140040abf  cmp     [rdi], rax
0x140040ac2  jz      short loc_140040B22
0x140040ac4  mov     rdx, rdi
0x140040ac7  lea     rcx, [rbp+var_18]
0x140040acb  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140040ad0  xor     r8d, r8d
0x140040ad3  xor     edx, edx
0x140040ad5  mov     rcx, rdi
0x140040ad8  call    ??$_Assign_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEBE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x140040add  mov     r9, [rbp+var_10]
0x140040ae1  mov     r8, [rbp+var_18]
0x140040ae5  sub     r9, r8
0x140040ae8  lea     rax, [rbp+var_30]
0x140040aec  mov     qword ptr [rsp+60h+var_40], rax; int
0x140040af1  mov     rdx, r15
0x140040af4  mov     rcx, r12
0x140040af7  call    ?SignTrustletData@VsmUtils@@YAJPEBE_K01PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; VsmUtils::SignTrustletData(uchar const *,unsigned __int64,uchar const *,unsigned __int64,std::vector<uchar> *)
0x140040afc  mov     edi, eax
0x140040afe  test    eax, eax
0x140040b00  js      short loc_140040B08
0x140040b02  add     rbx, 30h ; '0'
0x140040b06  jmp     short loc_140040A97
0x140040b08  mov     r9d, eax; char *
0x140040b0b  mov     edx, 80h; void *
0x140040b10  mov     rcx, [rbp+38h]; this
0x140040b14  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\biometrics\\serv"...
0x140040b1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040b20  jmp     short loc_140040B66
0x140040b22  mov     edi, 80070005h
0x140040b27  mov     r9d, edi
0x140040b2a  mov     edx, 79h ; 'y'
0x140040b2f  jmp     short loc_140040B10
0x140040b31  mov     rax, [rbp+var_28]
0x140040b35  cmp     qword ptr [rbp+var_30], rax
0x140040b39  jnz     short loc_140040B4A
0x140040b3b  mov     edi, 80090011h
0x140040b40  mov     r9d, edi
0x140040b43  mov     edx, 84h
0x140040b48  jmp     short loc_140040B10
0x140040b4a  lea     rdx, [rbp+var_18]
0x140040b4e  mov     rcx, [rbp+arg_20]
0x140040b52  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140040b57  lea     rdx, [rbp+var_30]
0x140040b5b  mov     rcx, [rbp+arg_28]
0x140040b5f  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140040b64  xor     edi, edi
0x140040b66  lea     rcx, [rbp+var_30]
0x140040b6a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140040b6f  nop
0x140040b70  lea     rcx, [rbp+var_18]
0x140040b74  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140040b79  mov     eax, edi
0x140040b7b  add     rsp, 60h
0x140040b7f  pop     r15
0x140040b81  pop     r14
0x140040b83  pop     r12
0x140040b85  pop     rdi
0x140040b86  pop     rsi
0x140040b87  pop     rbx
0x140040b88  pop     rbp
0x140040b89  retn
```
