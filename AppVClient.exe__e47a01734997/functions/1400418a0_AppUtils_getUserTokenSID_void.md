# AppUtils::getUserTokenSID(void *)

- ea: `0x1400418a0`
- end: `0x140041a5a`
- name: `?getUserTokenSID@AppUtils@@SA?AV?$extended_string@_W@shared@softricity@@PEAX@Z`
- size: `442`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400173c4`
- `0x140051330`

## callees

- `0x140004280`
- `0x140006061`
- `0x1400060e8`
- `0x140006304`
- `0x140007404`
- `0x14004054c`
- `0x1400414b0`
- `0x1400418a0`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x1400418ef`
- `ADVAPI32!GetTokenInformation` at `0x140041944`
- `ADVAPI32!GetTokenInformation` at `0x1400418ef`
- `ADVAPI32!GetTokenInformation` at `0x140041944`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140041989`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140041989`
- `KERNEL32!LocalFree` at `0x1400419f1`
- `KERNEL32!LocalFree` at `0x1400419f1`
- `KERNEL32!GetLastError` at `0x1400418f5`
- `KERNEL32!GetLastError` at `0x1400418f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppUtils::getUserTokenSID(__int64 a1, void *a2)
{
  PSID *v4; // rbx
  __int64 v5; // r8
  LPWSTR v6; // r9
  unsigned __int64 v7; // rdx
  void **v8; // rdi
  __int64 v9; // rbx
  void **v10; // rdx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-19h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-11h] BYREF
  LPVOID TokenInformation[3]; // [rsp+48h] [rbp-1h] BYREF
  void *v15[2]; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int64 v16; // [rsp+70h] [rbp+27h]
  unsigned __int64 v17; // [rsp+78h] [rbp+2Fh]

  StringSid = (LPWSTR)a1;
  TokenInformationLength = 0;
  GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() == 122 )
  {
    std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength);
    v4 = (PSID *)TokenInformation[0];
    if ( GetTokenInformation(a2, TokenUser, TokenInformation[0], TokenInformationLength, &TokenInformationLength) )
    {
      *(_OWORD *)v15 = 0;
      v16 = 0;
      v17 = 7;
      LOWORD(v15[0]) = 0;
      StringSid = 0;
      if ( ConvertSidToStringSidW(*v4, &StringSid) )
      {
        v6 = (LPWSTR)&qword_140088C88;
        if ( StringSid )
          v6 = StringSid;
        v7 = -1;
        do
          ++v7;
        while ( v6[v7] );
        if ( v7 > v17 )
        {
          std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
            (char **)v15,
            v7,
            v5,
            v6);
        }
        else
        {
          v8 = v15;
          if ( v17 > 7 )
            v8 = (void **)v15[0];
          v16 = v7;
          v9 = 2 * v7;
          memmove_0(v8, v6, 2 * v7);
          *(_WORD *)((char *)v8 + v9) = 0;
        }
        LocalFree(StringSid);
      }
      *(_OWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      v10 = v15;
      if ( v17 > 7 )
        v10 = (void **)v15[0];
      std::wstring::_Construct<1,wchar_t const *>((char **)a1, v10, v16);
      std::wstring::~wstring((char **)v15);
    }
    else
    {
      *(_OWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 7;
      *(_WORD *)a1 = 0;
    }
    std::vector<char>::~vector<char>(TokenInformation);
  }
  else
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 7;
    *(_WORD *)a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1400418a0  mov     [rsp-8+arg_10], rbx
0x1400418a5  mov     [rsp-8+arg_18], rsi
0x1400418aa  push    rbp
0x1400418ab  push    rdi
0x1400418ac  push    r14
0x1400418ae  lea     rbp, [rsp-47h]
0x1400418b3  sub     rsp, 90h
0x1400418ba  mov     rax, cs:__security_cookie
0x1400418c1  xor     rax, rsp
0x1400418c4  mov     [rbp+57h+var_20], rax
0x1400418c8  mov     rdi, rdx
0x1400418cb  mov     rsi, rcx
0x1400418ce  mov     [rbp+57h+StringSid], rcx
0x1400418d2  xor     r14d, r14d
0x1400418d5  mov     [rbp+57h+TokenInformationLength], r14d
0x1400418d9  lea     rax, [rbp+57h+TokenInformationLength]
0x1400418dd  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x1400418e2  xor     r9d, r9d; TokenInformationLength
0x1400418e5  xor     r8d, r8d; TokenInformation
0x1400418e8  lea     edx, [r14+1]; TokenInformationClass
0x1400418ec  mov     rcx, rdi; TokenHandle
0x1400418ef  call    cs:__imp_GetTokenInformation
0x1400418f5  call    cs:__imp_GetLastError
0x1400418fb  cmp     eax, 7Ah ; 'z'
0x1400418fe  jz      short loc_14004191B
0x140041900  xorps   xmm0, xmm0
0x140041903  movups  xmmword ptr [rsi], xmm0
0x140041906  mov     [rsi+10h], r14
0x14004190a  mov     qword ptr [rsi+18h], 7
0x140041912  mov     [rsi], r14w
0x140041916  jmp     loc_140041A33
0x14004191b  mov     edx, [rbp+57h+TokenInformationLength]
0x14004191e  lea     rcx, [rbp+57h+TokenInformation]
0x140041922  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140041927  nop
0x140041928  mov     rbx, [rbp+57h+TokenInformation]
0x14004192c  lea     rax, [rbp+57h+TokenInformationLength]
0x140041930  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x140041935  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x140041939  mov     r8, rbx; TokenInformation
0x14004193c  mov     edx, 1; TokenInformationClass
0x140041941  mov     rcx, rdi; TokenHandle
0x140041944  call    cs:__imp_GetTokenInformation
0x14004194a  xorps   xmm0, xmm0
0x14004194d  test    eax, eax
0x14004194f  jnz     short loc_140041969
0x140041951  movups  xmmword ptr [rsi], xmm0
0x140041954  mov     [rsi+10h], r14
0x140041958  mov     qword ptr [rsi+18h], 7
0x140041960  mov     [rsi], r14w
0x140041964  jmp     loc_140041A2A
0x140041969  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x14004196d  mov     [rbp+57h+var_30], r14
0x140041971  mov     [rbp+57h+var_28], 7
0x140041979  mov     word ptr [rbp+57h+var_40], r14w
0x14004197e  mov     [rbp+57h+StringSid], r14
0x140041982  lea     rdx, [rbp+57h+StringSid]; StringSid
0x140041986  mov     rcx, [rbx]; Sid
0x140041989  call    cs:__imp_ConvertSidToStringSidW
0x14004198f  test    eax, eax
0x140041991  jz      short loc_1400419F7
0x140041993  mov     rax, [rbp+57h+StringSid]
0x140041997  lea     r9, qword_140088C88
0x14004199e  test    rax, rax
0x1400419a1  cmovnz  r9, rax
0x1400419a5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400419a9  inc     rdx
0x1400419ac  cmp     [r9+rdx*2], r14w
0x1400419b1  jnz     short loc_1400419A9
0x1400419b3  cmp     rdx, [rbp+57h+var_28]
0x1400419b7  ja      short loc_1400419E4
0x1400419b9  lea     rdi, [rbp+57h+var_40]
0x1400419bd  cmp     [rbp+57h+var_28], 7
0x1400419c2  cmova   rdi, [rbp+57h+var_40]
0x1400419c7  mov     [rbp+57h+var_30], rdx
0x1400419cb  lea     rbx, [rdx+rdx]
0x1400419cf  mov     r8, rbx; Size
0x1400419d2  mov     rdx, r9; Src
0x1400419d5  mov     rcx, rdi; void *
0x1400419d8  call    memmove_0
0x1400419dd  mov     [rbx+rdi], r14w
0x1400419e2  jmp     short loc_1400419ED
0x1400419e4  lea     rcx, [rbp+57h+var_40]
0x1400419e8  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x1400419ed  mov     rcx, [rbp+57h+StringSid]; hMem
0x1400419f1  call    cs:__imp_LocalFree
0x1400419f7  xorps   xmm0, xmm0
0x1400419fa  movups  xmmword ptr [rsi], xmm0
0x1400419fd  mov     [rsi+10h], r14
0x140041a01  mov     [rsi+18h], r14
0x140041a05  lea     rdx, [rbp+57h+var_40]
0x140041a09  cmp     [rbp+57h+var_28], 7
0x140041a0e  cmova   rdx, [rbp+57h+var_40]
0x140041a13  mov     r8, [rbp+57h+var_30]
0x140041a17  mov     rcx, rsi
0x140041a1a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140041a1f  nop
0x140041a20  lea     rcx, [rbp+57h+var_40]
0x140041a24  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140041a29  nop
0x140041a2a  lea     rcx, [rbp+57h+TokenInformation]
0x140041a2e  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x140041a33  mov     rax, rsi
0x140041a36  mov     rcx, [rbp+57h+var_20]
0x140041a3a  xor     rcx, rsp; StackCookie
0x140041a3d  call    __security_check_cookie
0x140041a42  lea     r11, [rsp+0A0h+var_10]
0x140041a4a  mov     rbx, [r11+30h]
0x140041a4e  mov     rsi, [r11+38h]
0x140041a52  mov     rsp, r11
0x140041a55  pop     r14
0x140041a57  pop     rdi
0x140041a58  pop     rbp
0x140041a59  retn
```
