# CProviderRegistrationCache::LoadLsaSrv(void)

- ea: `0x180009960`
- end: `0x180009bda`
- name: `?LoadLsaSrv@CProviderRegistrationCache@@AEAAKXZ`
- size: `634`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003fb0`

## callees

- `0x180007da0`
- `0x180009960`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800099a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009b8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800099a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009b8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ab1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ade`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009b0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009b38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009b65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ba0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009a88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ab1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ade`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009b0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009b38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009b65`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a3b`

## string_xrefs

- `0x1800099a1`: `lsasrv.dll`
- `0x180009a22`: `LsarLookupSids`
- `0x180009a58`: `LsaIOpenPolicyTrusted`
- `0x180009b84`: `msv1_0.dll`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::LoadLsaSrv(CProviderRegistrationCache *this)
{
  unsigned int v1; // edi
  HMODULE ModuleHandleW; // rax
  int v4; // r8d
  FARPROC ProcAddress; // rax
  FARPROC v6; // rax
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  HMODULE v13; // rax
  FARPROC v14; // rax
  _BYTE v16[16]; // [rsp+30h] [rbp-28h] BYREF

  v1 = 0;
  if ( !*((_DWORD *)this + 50) )
  {
    *((_DWORD *)this + 50) = 1;
    if ( !*((_QWORD *)this + 24) )
    {
      ModuleHandleW = GetModuleHandleW(L"lsasrv.dll");
      if ( ModuleHandleW )
      {
        _InterlockedCompareExchange64((volatile signed __int64 *)this + 24, (signed __int64)ModuleHandleW, 0);
        if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(
            (_DWORD)ModuleHandleW,
            (unsigned int)Running_In_LSA,
            v4,
            1,
            (__int64)v16);
        if ( !*((_QWORD *)this + 26) )
        {
          ProcAddress = GetProcAddress(*((HMODULE *)this + 24), "LsarLookupSids");
          *((_QWORD *)this + 26) = ProcAddress;
          if ( !ProcAddress )
            return GetLastError();
        }
        if ( !*((_QWORD *)this + 27) )
        {
          v6 = GetProcAddress(*((HMODULE *)this + 24), "LsaIOpenPolicyTrusted");
          *((_QWORD *)this + 27) = v6;
          if ( !v6 )
            return GetLastError();
        }
        if ( !*((_QWORD *)this + 29) )
        {
          v7 = GetProcAddress(*((HMODULE *)this + 24), "LsaIFree_LSAPR_REFERENCED_DOMAIN_LIST");
          *((_QWORD *)this + 29) = v7;
          if ( !v7 )
            return GetLastError();
        }
        if ( !*((_QWORD *)this + 30) )
        {
          v8 = GetProcAddress(*((HMODULE *)this + 24), "LsaIFree_LSAPR_TRANSLATED_NAMES");
          *((_QWORD *)this + 30) = v8;
          if ( !v8 )
            return GetLastError();
        }
        if ( !*((_QWORD *)this + 28) )
        {
          v9 = GetProcAddress(*((HMODULE *)this + 24), "LsarClose");
          *((_QWORD *)this + 28) = v9;
          if ( !v9 )
            return GetLastError();
        }
        if ( !*((_QWORD *)this + 31) )
        {
          v10 = GetProcAddress(*((HMODULE *)this + 24), "LsaILookupUserAccountType");
          *((_QWORD *)this + 31) = v10;
          if ( !v10 )
            return GetLastError();
        }
        if ( (*((_QWORD *)this + 32)
           || (v11 = GetProcAddress(*((HMODULE *)this + 24), "LsaIRenewCertificate"), (*((_QWORD *)this + 32) = v11) != 0))
          && (*((_QWORD *)this + 33)
           || (v12 = GetProcAddress(*((HMODULE *)this + 24), "LsaIIsUserMSA"), (*((_QWORD *)this + 33) = v12) != 0))
          && (*((_QWORD *)this + 34)
           || (v13 = GetModuleHandleW(L"msv1_0.dll")) == 0
           || (v14 = GetProcAddress(v13, "MsvIsIpAddressLocal"), (*((_QWORD *)this + 34) = v14) != 0)) )
        {
          *((_DWORD *)this + 51) = 1;
        }
        else
        {
          return GetLastError();
        }
      }
      else if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      {
        McGenEventWrite_EtwEventWriteTransfer(0, (unsigned int)Not_Running_In_LSA, v4, 1, (__int64)v16);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180009960  mov     [rsp+arg_8], rbx
0x180009965  push    rdi
0x180009966  sub     rsp, 50h
0x18000996a  mov     rax, cs:__security_cookie
0x180009971  xor     rax, rsp
0x180009974  mov     [rsp+58h+var_18], rax
0x180009979  xor     edi, edi
0x18000997b  mov     rbx, rcx
0x18000997e  cmp     [rcx+0C8h], edi
0x180009984  jnz     loc_180009BC0
0x18000998a  mov     dword ptr [rcx+0C8h], 1
0x180009994  cmp     [rcx+0C0h], rdi
0x18000999b  jnz     loc_180009BC0
0x1800099a1  lea     rcx, ModuleName; "lsasrv.dll"
0x1800099a8  call    cs:__imp_GetModuleHandleW
0x1800099ae  mov     rcx, rax
0x1800099b1  test    rax, rax
0x1800099b4  jnz     short loc_1800099E2
0x1800099b6  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x1800099bd  jz      loc_180009BC0
0x1800099c3  lea     rax, [rsp+58h+var_28]
0x1800099c8  lea     r9d, [rdi+1]
0x1800099cc  mov     [rsp+58h+var_38], rax
0x1800099d1  lea     rdx, Not_Running_In_LSA
0x1800099d8  call    McGenEventWrite_EtwEventWriteTransfer
0x1800099dd  jmp     loc_180009BC0
0x1800099e2  xor     eax, eax
0x1800099e4  lock cmpxchg [rbx+0C0h], rcx
0x1800099ed  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x1800099f4  jz      short loc_180009A12
0x1800099f6  lea     rax, [rsp+58h+var_28]
0x1800099fb  mov     r9d, 1
0x180009a01  lea     rdx, Running_In_LSA
0x180009a08  mov     [rsp+58h+var_38], rax
0x180009a0d  call    McGenEventWrite_EtwEventWriteTransfer
0x180009a12  cmp     [rbx+0D0h], rdi
0x180009a19  jnz     short loc_180009A48
0x180009a1b  mov     rcx, [rbx+0C0h]; hModule
0x180009a22  lea     rdx, ProcName; "LsarLookupSids"
0x180009a29  call    cs:__imp_GetProcAddress
0x180009a2f  mov     [rbx+0D0h], rax
0x180009a36  test    rax, rax
0x180009a39  jnz     short loc_180009A48
0x180009a3b  call    cs:__imp_GetLastError
0x180009a41  mov     edi, eax
0x180009a43  jmp     loc_180009BC0
0x180009a48  cmp     [rbx+0D8h], rdi
0x180009a4f  jnz     short loc_180009A71
0x180009a51  mov     rcx, [rbx+0C0h]; hModule
0x180009a58  lea     rdx, aLsaiopenpolicy; "LsaIOpenPolicyTrusted"
0x180009a5f  call    cs:__imp_GetProcAddress
0x180009a65  mov     [rbx+0D8h], rax
0x180009a6c  test    rax, rax
0x180009a6f  jz      short loc_180009A3B
0x180009a71  cmp     [rbx+0E8h], rdi
0x180009a78  jnz     short loc_180009A9A
0x180009a7a  mov     rcx, [rbx+0C0h]; hModule
0x180009a81  lea     rdx, aLsaifreeLsaprR; "LsaIFree_LSAPR_REFERENCED_DOMAIN_LIST"
0x180009a88  call    cs:__imp_GetProcAddress
0x180009a8e  mov     [rbx+0E8h], rax
0x180009a95  test    rax, rax
0x180009a98  jz      short loc_180009A3B
0x180009a9a  cmp     [rbx+0F0h], rdi
0x180009aa1  jnz     short loc_180009AC7
0x180009aa3  mov     rcx, [rbx+0C0h]; hModule
0x180009aaa  lea     rdx, aLsaifreeLsaprT; "LsaIFree_LSAPR_TRANSLATED_NAMES"
0x180009ab1  call    cs:__imp_GetProcAddress
0x180009ab7  mov     [rbx+0F0h], rax
0x180009abe  test    rax, rax
0x180009ac1  jz      loc_180009A3B
0x180009ac7  cmp     [rbx+0E0h], rdi
0x180009ace  jnz     short loc_180009AF4
0x180009ad0  mov     rcx, [rbx+0C0h]; hModule
0x180009ad7  lea     rdx, aLsarclose; "LsarClose"
0x180009ade  call    cs:__imp_GetProcAddress
0x180009ae4  mov     [rbx+0E0h], rax
0x180009aeb  test    rax, rax
0x180009aee  jz      loc_180009A3B
0x180009af4  cmp     [rbx+0F8h], rdi
0x180009afb  jnz     short loc_180009B21
0x180009afd  mov     rcx, [rbx+0C0h]; hModule
0x180009b04  lea     rdx, aLsailookupuser; "LsaILookupUserAccountType"
0x180009b0b  call    cs:__imp_GetProcAddress
0x180009b11  mov     [rbx+0F8h], rax
0x180009b18  test    rax, rax
0x180009b1b  jz      loc_180009A3B
0x180009b21  cmp     [rbx+100h], rdi
0x180009b28  jnz     short loc_180009B4E
0x180009b2a  mov     rcx, [rbx+0C0h]; hModule
0x180009b31  lea     rdx, aLsairenewcerti; "LsaIRenewCertificate"
0x180009b38  call    cs:__imp_GetProcAddress
0x180009b3e  mov     [rbx+100h], rax
0x180009b45  test    rax, rax
0x180009b48  jz      loc_180009A3B
0x180009b4e  cmp     [rbx+108h], rdi
0x180009b55  jnz     short loc_180009B7B
0x180009b57  mov     rcx, [rbx+0C0h]; hModule
0x180009b5e  lea     rdx, aLsaiisusermsa; "LsaIIsUserMSA"
0x180009b65  call    cs:__imp_GetProcAddress
0x180009b6b  mov     [rbx+108h], rax
0x180009b72  test    rax, rax
0x180009b75  jz      loc_180009A3B
0x180009b7b  cmp     [rbx+110h], rdi
0x180009b82  jnz     short loc_180009BB6
0x180009b84  lea     rcx, aMsv10Dll; "msv1_0.dll"
0x180009b8b  call    cs:__imp_GetModuleHandleW
0x180009b91  test    rax, rax
0x180009b94  jz      short loc_180009BB6
0x180009b96  lea     rdx, aMsvisipaddress; "MsvIsIpAddressLocal"
0x180009b9d  mov     rcx, rax; hModule
0x180009ba0  call    cs:__imp_GetProcAddress
0x180009ba6  mov     [rbx+110h], rax
0x180009bad  test    rax, rax
0x180009bb0  jz      loc_180009A3B
0x180009bb6  mov     dword ptr [rbx+0CCh], 1
0x180009bc0  mov     eax, edi
0x180009bc2  mov     rcx, [rsp+58h+var_18]
0x180009bc7  xor     rcx, rsp; StackCookie
0x180009bca  call    __security_check_cookie
0x180009bcf  mov     rbx, [rsp+58h+arg_8]
0x180009bd4  add     rsp, 50h
0x180009bd8  pop     rdi
0x180009bd9  retn
```
