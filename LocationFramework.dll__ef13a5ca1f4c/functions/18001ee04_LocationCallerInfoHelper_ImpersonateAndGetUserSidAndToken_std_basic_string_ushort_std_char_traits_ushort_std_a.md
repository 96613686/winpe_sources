# LocationCallerInfoHelper::ImpersonateAndGetUserSidAndToken(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ATL::CAccessToken &)

- ea: `0x18001ee04`
- end: `0x18001efda`
- name: `?ImpersonateAndGetUserSidAndToken@LocationCallerInfoHelper@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVCAccessToken@ATL@@@Z`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180079f30`

## callees

- `0x18001ecbc`
- `0x18001ee04`
- `0x18001efe0`
- `0x18001f09c`
- `0x18001f334`
- `0x1800208b0`
- `0x18008f888`
- `0x18009cc18`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee8c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ee7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ee7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ee9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ee9d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001eeb4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001eeb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ee5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ee5f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001ee32`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001ee32`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001ef3d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001ef78`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001efa9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001efc1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001ef3d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001ef78`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001efa9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001efc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LocationCallerInfoHelper::ImpersonateAndGetUserSidAndToken(__int64 a1, _QWORD *a2)
{
  HRESULT v4; // esi
  char v5; // r14
  HANDLE CurrentThread; // rax
  wil::details *v7; // rcx
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int LastErrorFailHr; // edi
  void *TokenHandle; // [rsp+28h] [rbp-61h] BYREF
  _BYTE v15[128]; // [rsp+30h] [rbp-59h] BYREF

  v4 = CoImpersonateClient();
  v5 = 1;
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417833 )
  {
    if ( v4 >= 0 )
      CoRevertToSelf();
    return (unsigned int)v4;
  }
  CurrentThread = GetCurrentThread();
  TokenHandle = 0;
  if ( OpenThreadToken(CurrentThread, 0x8Cu, 1, &TokenHandle) )
  {
    (*(void (__fastcall **)(_QWORD *))(*a2 + 8LL))(a2);
    a2[1] = TokenHandle;
    goto LABEL_7;
  }
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    TokenHandle = 0;
    if ( OpenProcessToken(CurrentProcess, 0x8Cu, &TokenHandle) )
    {
      (*(void (__fastcall **)(_QWORD *))(*a2 + 8LL))(a2);
      a2[1] = TokenHandle;
    }
    else
    {
      v5 = 0;
    }
    if ( v5 )
    {
LABEL_7:
      memset_0(v15, 0, 0x78u);
      ATL::CSid::CSid((ATL::CSid *)v15);
      if ( ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>((__int64)a2, (__int64)v15) )
      {
        v9 = ATL::CSid::Sid((ATL::CSid *)v15);
        v10 = std::_WChar_traits<unsigned short>::length(v9);
        std::wstring::_Assign<unsigned short>(a1, v11, v10);
        ATL::CSid::~CSid((ATL::CSid *)v15);
        if ( v4 >= 0 )
          CoRevertToSelf();
        return 0;
      }
      else
      {
        ATL::CSid::~CSid((ATL::CSid *)v15);
        if ( v4 >= 0 )
          CoRevertToSelf();
        return 2147943709LL;
      }
    }
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v7);
  if ( v4 >= 0 )
    CoRevertToSelf();
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18001ee04  mov     [rsp-8+arg_10], rbx
0x18001ee09  push    rbp
0x18001ee0a  push    rsi
0x18001ee0b  push    rdi
0x18001ee0c  push    r14
0x18001ee0e  push    r15
0x18001ee10  lea     rbp, [rsp-37h]
0x18001ee15  sub     rsp, 0C0h
0x18001ee1c  mov     rax, cs:__security_cookie
0x18001ee23  xor     rax, rsp
0x18001ee26  mov     [rbp+57h+var_30], rax
0x18001ee2a  mov     rdi, rdx
0x18001ee2d  mov     r15, rcx
0x18001ee30  xor     bl, bl
0x18001ee32  call    cs:__imp_CoImpersonateClient
0x18001ee38  mov     esi, eax
0x18001ee3a  mov     [rbp+57h+var_BC], eax
0x18001ee3d  movzx   ebx, bl
0x18001ee40  mov     r14d, 1
0x18001ee46  test    eax, eax
0x18001ee48  cmovns  ebx, r14d
0x18001ee4c  mov     [rbp+57h+var_C0], bl
0x18001ee4f  mov     eax, 80000000h
0x18001ee54  lea     ecx, [rsi+rax]
0x18001ee57  test    eax, ecx
0x18001ee59  jz      loc_18001EF68
0x18001ee5f  call    cs:__imp_GetCurrentThread
0x18001ee65  mov     [rbp+57h+TokenHandle], 0
0x18001ee6d  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001ee71  mov     r8d, r14d; OpenAsSelf
0x18001ee74  mov     esi, 8Ch
0x18001ee79  mov     edx, esi; DesiredAccess
0x18001ee7b  mov     rcx, rax; ThreadHandle
0x18001ee7e  call    cs:__imp_OpenThreadToken
0x18001ee84  test    eax, eax
0x18001ee86  jnz     loc_18001EF82
0x18001ee8c  call    cs:__imp_GetLastError
0x18001ee92  cmp     eax, 3F0h
0x18001ee97  jnz     loc_18001EF9E
0x18001ee9d  call    cs:__imp_GetCurrentProcess
0x18001eea3  mov     [rbp+57h+TokenHandle], 0
0x18001eeab  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18001eeaf  mov     edx, esi; DesiredAccess
0x18001eeb1  mov     rcx, rax; ProcessHandle
0x18001eeb4  call    cs:__imp_OpenProcessToken
0x18001eeba  test    eax, eax
0x18001eebc  jz      loc_18001EFD1
0x18001eec2  mov     rax, [rdi]
0x18001eec5  mov     rcx, rdi
0x18001eec8  mov     rax, [rax+8]
0x18001eecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eed1  mov     rax, [rbp+57h+TokenHandle]
0x18001eed5  mov     [rdi+8], rax
0x18001eed9  test    r14b, r14b
0x18001eedc  jz      loc_18001EF9E
0x18001eee2  xor     edx, edx; Val
0x18001eee4  lea     r8d, [rdx+78h]; Size
0x18001eee8  lea     rcx, [rbp+57h+var_B0]; void *
0x18001eeec  call    memset_0
0x18001eef1  lea     rcx, [rbp+57h+var_B0]; this
0x18001eef5  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x18001eefa  nop
0x18001eefb  lea     rdx, [rbp+57h+var_B0]
0x18001eeff  mov     rcx, rdi
0x18001ef02  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x18001ef07  test    al, al
0x18001ef09  jz      loc_18001EFB3
0x18001ef0f  lea     rcx, [rbp+57h+var_B0]; this
0x18001ef13  call    ?Sid@CSid@ATL@@QEBAPEBGXZ; ATL::CSid::Sid(void)
0x18001ef18  mov     rcx, rax
0x18001ef1b  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001ef20  mov     r8, rax
0x18001ef23  mov     rdx, rcx
0x18001ef26  mov     rcx, r15
0x18001ef29  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001ef2e  nop
0x18001ef2f  lea     rcx, [rbp+57h+var_B0]; this
0x18001ef33  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18001ef38  nop
0x18001ef39  test    bl, bl
0x18001ef3b  jz      short loc_18001EF43
0x18001ef3d  call    cs:__imp_CoRevertToSelf
0x18001ef43  xor     eax, eax
0x18001ef45  mov     rcx, [rbp+57h+var_30]
0x18001ef49  xor     rcx, rsp; StackCookie
0x18001ef4c  call    __security_check_cookie
0x18001ef51  mov     rbx, [rsp+0E0h+arg_10]
0x18001ef59  add     rsp, 0C0h
0x18001ef60  pop     r15
0x18001ef62  pop     r14
0x18001ef64  pop     rdi
0x18001ef65  pop     rsi
0x18001ef66  pop     rbp
0x18001ef67  retn
0x18001ef68  cmp     esi, 80010117h
0x18001ef6e  jz      loc_18001EE5F
0x18001ef74  test    bl, bl
0x18001ef76  jz      short loc_18001EF7E
0x18001ef78  call    cs:__imp_CoRevertToSelf
0x18001ef7e  mov     eax, esi
0x18001ef80  jmp     short loc_18001EF45
0x18001ef82  mov     rax, [rdi]
0x18001ef85  mov     rcx, rdi
0x18001ef88  mov     rax, [rax+8]
0x18001ef8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef91  mov     rax, [rbp+57h+TokenHandle]
0x18001ef95  mov     [rdi+8], rax
0x18001ef99  jmp     loc_18001EEE2
0x18001ef9e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001efa3  mov     edi, eax
0x18001efa5  test    bl, bl
0x18001efa7  jz      short loc_18001EFAF
0x18001efa9  call    cs:__imp_CoRevertToSelf
0x18001efaf  mov     eax, edi
0x18001efb1  jmp     short loc_18001EF45
0x18001efb3  lea     rcx, [rbp+57h+var_B0]; this
0x18001efb7  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18001efbc  nop
0x18001efbd  test    bl, bl
0x18001efbf  jz      short loc_18001EFC7
0x18001efc1  call    cs:__imp_CoRevertToSelf
0x18001efc7  mov     eax, 8007051Dh
0x18001efcc  jmp     loc_18001EF45
0x18001efd1  xor     r14b, r14b
0x18001efd4  jmp     loc_18001EED9
```
