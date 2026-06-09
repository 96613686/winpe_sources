# _anonymous_namespace_::StartHash

- ea: `0x1400753a4`
- end: `0x140075633`
- name: `_anonymous_namespace_::StartHash`
- size: `655`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE *phAlgorithm)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400743a8`
- `0x14007594c`

## callees

- `0x1400413a8`
- `0x14004519c`
- `0x1400753a4`
- `0x140075a34`
- `0x140075bdc`
- `0x140379070`
- `0x140380bd0`
- `0x140380f90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007541c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007555f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007541c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007555f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140075407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007554c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140075407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007554c`
- `bcrypt!BCryptDestroyHash` at `0x140075557`
- `bcrypt!BCryptDestroyHash` at `0x140075557`
- `bcrypt!BCryptCreateHash` at `0x140075584`
- `bcrypt!BCryptCreateHash` at `0x140075584`
- `bcrypt!BCryptGetProperty` at `0x140075471`
- `bcrypt!BCryptGetProperty` at `0x140075471`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140075435`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140075435`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140075414`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140075414`

## string_xrefs

- `0x1400755c7`: `C:\__w\1\s\src\orchestrator\system\windows\common\Hash.cpp`
- `0x1400755e4`: `C:\__w\1\s\src\orchestrator\system\windows\common\Hash.cpp`
- `0x140075601`: `C:\__w\1\s\src\orchestrator\system\windows\common\Hash.cpp`
- `0x140075621`: `C:\__w\1\s\src\orchestrator\system\windows\common\Hash.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BCRYPT_ALG_HANDLE *__fastcall anonymous_namespace_::StartHash(BCRYPT_ALG_HANDLE *phAlgorithm)
{
  BCRYPT_ALG_HANDLE *v2; // r12
  BCRYPT_ALG_HANDLE *v3; // r14
  BCRYPT_ALG_HANDLE v4; // rdi
  DWORD LastError; // ebx
  NTSTATUS v6; // eax
  NTSTATUS Property; // eax
  ULONG v8; // ebp
  __int64 v9; // rdi
  _BYTE *v10; // rax
  _BYTE *v11; // rbx
  unsigned __int64 v12; // r15
  char *v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 v16; // rbp
  char *v17; // rbx
  UCHAR *v18; // r14
  BCRYPT_HASH_HANDLE v19; // rdi
  DWORD v20; // ebx
  NTSTATUS Hash; // eax
  int pcbResult; // [rsp+20h] [rbp-68h]
  int pcbResulta; // [rsp+20h] [rbp-68h]
  int pcbResultb; // [rsp+20h] [rbp-68h]
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-38h] BYREF
  ULONG v27; // [rsp+54h] [rbp-34h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *phAlgorithm = 0;
  v2 = phAlgorithm + 1;
  phAlgorithm[1] = 0;
  v3 = phAlgorithm + 2;
  phAlgorithm[2] = 0;
  phAlgorithm[3] = 0;
  phAlgorithm[4] = 0;
  v4 = *phAlgorithm;
  if ( *phAlgorithm )
  {
    LastError = GetLastError();
    BCryptCloseAlgorithmProvider(v4, 0);
    SetLastError(LastError);
  }
  *phAlgorithm = 0;
  v6 = BCryptOpenAlgorithmProvider(phAlgorithm, L"SHA256", 0, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Hash.cpp",
      (const char *)(unsigned int)v6,
      pcbResult);
  *(_DWORD *)pbOutput = 0;
  v27 = 0;
  Property = BCryptGetProperty(*phAlgorithm, L"ObjectLength", pbOutput, 4u, &v27, 0);
  if ( Property < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x51,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Hash.cpp",
      (const char *)(unsigned int)Property,
      pcbResulta);
  v8 = *(_DWORD *)pbOutput;
  if ( !*(_DWORD *)pbOutput )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Hash.cpp",
      (const char *)0x8000FFFFLL,
      pcbResulta);
  v9 = *(unsigned int *)pbOutput;
  v10 = *v3;
  v11 = v3[1];
  v12 = v11 - (_BYTE *)*v3;
  if ( *(unsigned int *)pbOutput < v12 )
  {
    v13 = &v10[*(unsigned int *)pbOutput];
LABEL_15:
    v3[1] = v13;
    goto LABEL_16;
  }
  if ( *(unsigned int *)pbOutput <= v12 )
    goto LABEL_16;
  v14 = (_BYTE *)v3[2] - v10;
  if ( *(unsigned int *)pbOutput <= v14 )
  {
    memset(v3[1], 0, *(unsigned int *)pbOutput - v12);
    v13 = &v11[v8 - v12];
    v8 = *(_DWORD *)pbOutput;
    goto LABEL_15;
  }
  v15 = v14 >> 1;
  v16 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v14 <= 0x7FFFFFFFFFFFFFFFLL - (v14 >> 1) )
  {
    v16 = v14 + v15;
    if ( v14 + v15 < *(unsigned int *)pbOutput )
      v16 = *(unsigned int *)pbOutput;
  }
  v17 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v16);
  memset(&v17[v12], 0, v9 - v12);
  memmove(v17, *v3, (_BYTE *)v3[1] - (_BYTE *)*v3);
  std::vector<unsigned char>::_Change_array(v3, v17, v9, v16);
  v8 = *(_DWORD *)pbOutput;
LABEL_16:
  v18 = (UCHAR *)*v3;
  v19 = *v2;
  if ( *v2 )
  {
    v20 = GetLastError();
    BCryptDestroyHash(v19);
    SetLastError(v20);
  }
  *v2 = 0;
  Hash = BCryptCreateHash(*phAlgorithm, v2, v18, v8, 0, 0, 0);
  if ( Hash < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x55,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Hash.cpp",
      (const char *)(unsigned int)Hash,
      pcbResultb);
  return phAlgorithm;
}

```

## disassembly

```asm
0x1400753a4  mov     r11, rsp
0x1400753a7  mov     [r11+10h], rbx
0x1400753ab  mov     [r11+18h], rbp
0x1400753af  mov     [r11+20h], rsi
0x1400753b3  push    rdi
0x1400753b4  push    r12
0x1400753b6  push    r13
0x1400753b8  push    r14
0x1400753ba  push    r15
0x1400753bc  sub     rsp, 60h
0x1400753c0  mov     rax, cs:__security_cookie
0x1400753c7  xor     rax, rsp
0x1400753ca  mov     [rsp+88h+var_30], rax
0x1400753cf  mov     rsi, rcx
0x1400753d2  mov     [r11-40h], rcx
0x1400753d6  xor     r13d, r13d
0x1400753d9  mov     [r11-48h], r13d
0x1400753dd  mov     [rcx], r13
0x1400753e0  lea     r12, [rcx+8]
0x1400753e4  mov     [r12], r13
0x1400753e8  lea     r14, [rcx+10h]
0x1400753ec  mov     [r14], r13
0x1400753ef  mov     [r14+8], r13
0x1400753f3  mov     [r14+10h], r13
0x1400753f7  mov     [rsp+88h+var_48], 1
0x1400753ff  mov     rdi, [rcx]
0x140075402  test    rdi, rdi
0x140075405  jz      short loc_140075422
0x140075407  call    cs:__imp_GetLastError
0x14007540d  mov     ebx, eax
0x14007540f  xor     edx, edx; dwFlags
0x140075411  mov     rcx, rdi; hAlgorithm
0x140075414  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14007541a  mov     ecx, ebx; dwErrCode
0x14007541c  call    cs:__imp_SetLastError
0x140075422  mov     [rsi], r13
0x140075425  xor     r9d, r9d; dwFlags
0x140075428  xor     r8d, r8d; pszImplementation
0x14007542b  lea     rdx, pszAlgId; "SHA256"
0x140075432  mov     rcx, rsi; phAlgorithm
0x140075435  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14007543b  test    eax, eax
0x14007543d  js      loc_1400755D9
0x140075443  mov     dword ptr [rsp+88h+pbOutput], r13d
0x140075448  mov     [rsp+88h+var_34], r13d
0x14007544d  mov     [rsp+88h+dwFlags], r13d; dwFlags
0x140075452  lea     rax, [rsp+88h+var_34]
0x140075457  mov     [rsp+88h+pcbResult], rax; int
0x14007545c  mov     r9d, 4; cbOutput
0x140075462  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x140075467  lea     rdx, pszProperty; "ObjectLength"
0x14007546e  mov     rcx, [rsi]; hObject
0x140075471  call    cs:__imp_BCryptGetProperty
0x140075477  test    eax, eax
0x140075479  js      loc_1400755F6
0x14007547f  mov     ebp, dword ptr [rsp+88h+pbOutput]
0x140075483  test    ebp, ebp
0x140075485  jz      loc_140075613
0x14007548b  mov     edi, ebp
0x14007548d  mov     rax, [r14]
0x140075490  mov     rbx, [r14+8]
0x140075494  mov     r15, rbx
0x140075497  sub     r15, rax
0x14007549a  cmp     rbp, r15
0x14007549d  jnb     short loc_1400754A7
0x14007549f  add     rax, rbp
0x1400754a2  jmp     loc_14007553C
0x1400754a7  jbe     loc_140075540
0x1400754ad  mov     rcx, [r14+10h]
0x1400754b1  sub     rcx, rax
0x1400754b4  cmp     rdi, rcx
0x1400754b7  jbe     short loc_140075524
0x1400754b9  mov     rdx, rcx
0x1400754bc  shr     rdx, 1
0x1400754bf  mov     rbp, 7FFFFFFFFFFFFFFFh
0x1400754c9  mov     rax, rbp
0x1400754cc  sub     rax, rdx
0x1400754cf  cmp     rcx, rax
0x1400754d2  ja      short loc_1400754DF
0x1400754d4  lea     rbp, [rcx+rdx]
0x1400754d8  cmp     rbp, rdi
0x1400754db  cmovb   rbp, rdi
0x1400754df  mov     rcx, rbp
0x1400754e2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1400754e7  mov     rbx, rax
0x1400754ea  mov     r8, rdi
0x1400754ed  sub     r8, r15; Size
0x1400754f0  lea     rcx, [r15+rax]; void *
0x1400754f4  xor     edx, edx; Val
0x1400754f6  call    memset
0x1400754fb  mov     r8, [r14+8]
0x1400754ff  sub     r8, [r14]; Size
0x140075502  mov     rdx, [r14]; Src
0x140075505  mov     rcx, rbx; void *
0x140075508  call    memmove
0x14007550d  mov     r9, rbp
0x140075510  mov     r8, rdi
0x140075513  mov     rdx, rbx
0x140075516  mov     rcx, r14
0x140075519  call    ?_Change_array@?$vector@EV?$allocator@E@std@@@std@@AEAAXQEAE_K1@Z; std::vector<uchar>::_Change_array(uchar * const,unsigned __int64,unsigned __int64)
0x14007551e  mov     ebp, dword ptr [rsp+88h+pbOutput]
0x140075522  jmp     short loc_140075540
0x140075524  sub     rdi, r15
0x140075527  mov     r8, rdi; Size
0x14007552a  xor     edx, edx; Val
0x14007552c  mov     rcx, rbx; void *
0x14007552f  call    memset
0x140075534  lea     rax, [rdi+rbx]
0x140075538  mov     ebp, dword ptr [rsp+88h+pbOutput]
0x14007553c  mov     [r14+8], rax
0x140075540  mov     r14, [r14]
0x140075543  mov     rdi, [r12]
0x140075547  test    rdi, rdi
0x14007554a  jz      short loc_140075565
0x14007554c  call    cs:__imp_GetLastError
0x140075552  mov     ebx, eax
0x140075554  mov     rcx, rdi; hHash
0x140075557  call    cs:__imp_BCryptDestroyHash
0x14007555d  mov     ecx, ebx; dwErrCode
0x14007555f  call    cs:__imp_SetLastError
0x140075565  mov     [r12], r13
0x140075569  mov     [rsp+88h+var_58], r13d; dwFlags
0x14007556e  mov     [rsp+88h+dwFlags], r13d; cbSecret
0x140075573  mov     [rsp+88h+pcbResult], r13; int
0x140075578  mov     r9d, ebp; cbHashObject
0x14007557b  mov     r8, r14; pbHashObject
0x14007557e  mov     rdx, r12; phHash
0x140075581  mov     rcx, [rsi]; hAlgorithm
0x140075584  call    cs:__imp_BCryptCreateHash
0x14007558a  test    eax, eax
0x14007558c  js      short loc_1400755BC
0x14007558e  mov     rax, rsi
0x140075591  mov     rcx, [rsp+88h+var_30]
0x140075596  xor     rcx, rsp; StackCookie
0x140075599  call    __security_check_cookie
0x14007559e  lea     r11, [rsp+88h+var_28]
0x1400755a3  mov     rbx, [r11+38h]
0x1400755a7  mov     rbp, [r11+40h]
0x1400755ab  mov     rsi, [r11+48h]
0x1400755af  mov     rsp, r11
0x1400755b2  pop     r15
0x1400755b4  pop     r14
0x1400755b6  pop     r13
0x1400755b8  pop     r12
0x1400755ba  pop     rdi
0x1400755bb  retn
0x1400755bc  mov     rcx, [rsp+88h]; this
0x1400755c4  mov     r9d, eax; char *
0x1400755c7  lea     r8, aCW1SSrcOrchest_16; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1400755ce  mov     edx, 55h ; 'U'; void *
0x1400755d3  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400755d9  mov     rcx, [rsp+88h]; this
0x1400755e1  mov     r9d, eax; char *
0x1400755e4  lea     r8, aCW1SSrcOrchest_16; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1400755eb  mov     edx, 4Dh ; 'M'; void *
0x1400755f0  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400755f6  mov     rcx, [rsp+88h]; this
0x1400755fe  mov     r9d, eax; char *
0x140075601  lea     r8, aCW1SSrcOrchest_16; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140075608  mov     edx, 51h ; 'Q'; void *
0x14007560d  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140075613  mov     rcx, [rsp+88h]; this
0x14007561b  mov     r9d, 8000FFFFh; char *
0x140075621  lea     r8, aCW1SSrcOrchest_16; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140075628  mov     edx, 52h ; 'R'; void *
0x14007562d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
