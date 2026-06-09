# OSIntegration::Tools::GetUserSID(void *,void * *)

- ea: `0x18008fc9c`
- end: `0x18008fe54`
- name: `?GetUserSID@Tools@OSIntegration@@YAJPEAXPEAPEAX@Z`
- size: `440`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18007d844`
- `0x18008fc04`

## callees

- `0x18000669c`
- `0x18001adb4`
- `0x18008fc9c`
- `0x1800af1bc`
- `0x1800af6f8`
- `0x1800af918`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fcfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fcfa`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008fdc3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008fdc3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008fcea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008fd6a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008fcea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008fd6a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008fd95`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008fd95`

## string_xrefs

- `0x18008fd10`: `onecore\admin\appmodel\osim\src\deh\appx\common\usertoken.cpp`
- `0x18008fd7f`: `onecore\admin\appmodel\osim\src\deh\appx\common\usertoken.cpp`
- `0x18008fdd8`: `onecore\admin\appmodel\osim\src\deh\appx\common\usertoken.cpp`
- `0x18008fe1c`: `onecore\admin\appmodel\osim\src\deh\appx\common\usertoken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSIntegration::Tools::GetUserSID(HANDLE TokenHandle, _QWORD *a2, void **a3)
{
  PSID *v5; // rbx
  const char *v6; // r9
  unsigned int v7; // ebx
  const char *v8; // r9
  unsigned int LastError; // edi
  void *v10; // rbp
  const char *v11; // r9
  void *v12; // rcx
  int ReturnLength; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  size_t Size; // [rsp+60h] [rbp+8h] BYREF
  PSID *v17; // [rsp+70h] [rbp+18h]
  __int64 v18; // [rsp+78h] [rbp+20h]

  LODWORD(Size) = 0;
  v5 = 0;
  v17 = 0;
  v18 = 0;
  if ( TokenHandle == (HANDLE)-1LL || !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\usertoken.cpp",
      (const char *)0x80070057LL,
      ReturnLength);
    goto LABEL_15;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&Size) )
  {
LABEL_7:
    if ( GetTokenInformation(TokenHandle, TokenUser, v5, Size, (PDWORD)&Size) )
    {
      LODWORD(Size) = GetLengthSid(*v5);
      v10 = operator new[]((unsigned int)Size);
      operator delete(0, (const struct std::nothrow_t *)1);
      if ( !CopySid(Size, v10, *v5) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x48,
                      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\usertoken.cpp",
                      v11);
        v12 = v10;
LABEL_13:
        operator delete(v12, (const struct std::nothrow_t *)1);
        operator delete(v5, (const struct std::nothrow_t *)0x10);
        return LastError;
      }
      *a2 = v10;
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x42,
                    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\usertoken.cpp",
                    v8);
    }
    v12 = 0;
    goto LABEL_13;
  }
  if ( GetLastError() == 122 )
  {
    v5 = (PSID *)operator new[]((unsigned int)Size);
    operator delete(0, (const struct std::nothrow_t *)0x10);
    v17 = v5;
    memset_0(v5, 0, (unsigned int)Size);
    goto LABEL_7;
  }
  v7 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0x33,
         (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\usertoken.cpp",
         v6);
LABEL_15:
  operator delete(0, (const struct std::nothrow_t *)1);
  operator delete(0, (const struct std::nothrow_t *)0x10);
  return v7;
}

```

## disassembly

```asm
0x18008fc9c  mov     rax, rsp
0x18008fc9f  push    rbx
0x18008fca0  push    rbp
0x18008fca1  push    rdi
0x18008fca2  push    r14
0x18008fca4  push    r15
0x18008fca6  sub     rsp, 30h
0x18008fcaa  mov     r14, rdx
0x18008fcad  mov     rdi, rcx
0x18008fcb0  mov     dword ptr [rax+8], 0
0x18008fcb7  xor     ebx, ebx
0x18008fcb9  mov     [rax+18h], rbx
0x18008fcbd  mov     [rax+20h], rbx
0x18008fcc1  lea     r15d, [rbx+1]
0x18008fcc5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18008fcc9  jz      loc_18008FE0F
0x18008fccf  test    rdx, rdx
0x18008fcd2  jz      loc_18008FE0F
0x18008fcd8  lea     rax, [rax+8]
0x18008fcdc  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x18008fce1  xor     r9d, r9d; TokenInformationLength
0x18008fce4  xor     r8d, r8d; TokenInformation
0x18008fce7  mov     edx, r15d; TokenInformationClass
0x18008fcea  call    cs:__imp_GetTokenInformation
0x18008fcf1  nop     dword ptr [rax+rax+00h]
0x18008fcf6  test    eax, eax
0x18008fcf8  jnz     short loc_18008FD52
0x18008fcfa  call    cs:__imp_GetLastError
0x18008fd01  nop     dword ptr [rax+rax+00h]
0x18008fd06  cmp     eax, 7Ah ; 'z'
0x18008fd09  jz      short loc_18008FD26
0x18008fd0b  mov     rcx, [rsp+58h]; this
0x18008fd10  lea     r8, aOnecoreAdminAp_98; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008fd17  lea     edx, [rbx+33h]; void *
0x18008fd1a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008fd1f  mov     ebx, eax
0x18008fd21  jmp     loc_18008FE2E
0x18008fd26  mov     ecx, dword ptr [rsp+58h+Size]; unsigned __int64
0x18008fd2a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008fd2f  mov     rbx, rax
0x18008fd32  mov     edx, 10h; struct std::nothrow_t *
0x18008fd37  xor     ecx, ecx; void *
0x18008fd39  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008fd3e  mov     [rsp+58h+arg_10], rbx
0x18008fd43  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x18008fd48  xor     edx, edx; Val
0x18008fd4a  mov     rcx, rbx; void *
0x18008fd4d  call    memset_0
0x18008fd52  lea     rax, [rsp+58h+Size]
0x18008fd57  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x18008fd5c  mov     r9d, dword ptr [rsp+58h+Size]; TokenInformationLength
0x18008fd61  mov     r8, rbx; TokenInformation
0x18008fd64  mov     edx, r15d; TokenInformationClass
0x18008fd67  mov     rcx, rdi; TokenHandle
0x18008fd6a  call    cs:__imp_GetTokenInformation
0x18008fd71  nop     dword ptr [rax+rax+00h]
0x18008fd76  test    eax, eax
0x18008fd78  jnz     short loc_18008FD92
0x18008fd7a  mov     rcx, [rsp+58h]; this
0x18008fd7f  lea     r8, aOnecoreAdminAp_98; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008fd86  lea     edx, [rax+42h]; void *
0x18008fd89  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008fd8e  mov     edi, eax
0x18008fd90  jmp     short loc_18008FDF3
0x18008fd92  mov     rcx, [rbx]; pSid
0x18008fd95  call    cs:__imp_GetLengthSid
0x18008fd9c  nop     dword ptr [rax+rax+00h]
0x18008fda1  mov     ecx, eax; unsigned __int64
0x18008fda3  mov     dword ptr [rsp+58h+Size], ecx
0x18008fda7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008fdac  mov     rbp, rax
0x18008fdaf  mov     rdx, r15; struct std::nothrow_t *
0x18008fdb2  xor     ecx, ecx; void *
0x18008fdb4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008fdb9  mov     r8, [rbx]; pSourceSid
0x18008fdbc  mov     rdx, rbp; pDestinationSid
0x18008fdbf  mov     ecx, dword ptr [rsp+58h+Size]; nDestinationSidLength
0x18008fdc3  call    cs:__imp_CopySid
0x18008fdca  nop     dword ptr [rax+rax+00h]
0x18008fdcf  test    eax, eax
0x18008fdd1  jnz     short loc_18008FDEE
0x18008fdd3  mov     rcx, [rsp+58h]; this
0x18008fdd8  lea     r8, aOnecoreAdminAp_98; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008fddf  lea     edx, [rax+48h]; void *
0x18008fde2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008fde7  mov     edi, eax
0x18008fde9  mov     rcx, rbp
0x18008fdec  jmp     short loc_18008FDF5
0x18008fdee  mov     [r14], rbp
0x18008fdf1  xor     edi, edi
0x18008fdf3  xor     ecx, ecx; void *
0x18008fdf5  mov     rdx, r15; struct std::nothrow_t *
0x18008fdf8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008fdfd  nop
0x18008fdfe  mov     edx, 10h; struct std::nothrow_t *
0x18008fe03  mov     rcx, rbx; void *
0x18008fe06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008fe0b  mov     eax, edi
0x18008fe0d  jmp     short loc_18008FE47
0x18008fe0f  mov     rcx, [rsp+58h]; this
0x18008fe14  mov     ebx, 80070057h
0x18008fe19  mov     r9d, ebx; char *
0x18008fe1c  lea     r8, aOnecoreAdminAp_98; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008fe23  mov     edx, 26h ; '&'; void *
0x18008fe28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008fe2d  nop
0x18008fe2e  mov     rdx, r15; struct std::nothrow_t *
0x18008fe31  xor     ecx, ecx; void *
0x18008fe33  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008fe38  nop
0x18008fe39  mov     edx, 10h; struct std::nothrow_t *
0x18008fe3e  xor     ecx, ecx; void *
0x18008fe40  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008fe45  mov     eax, ebx
0x18008fe47  add     rsp, 30h
0x18008fe4b  pop     r15
0x18008fe4d  pop     r14
0x18008fe4f  pop     rdi
0x18008fe50  pop     rbp
0x18008fe51  pop     rbx
0x18008fe52  retn
```
