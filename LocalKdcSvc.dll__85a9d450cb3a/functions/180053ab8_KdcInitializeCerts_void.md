# KdcInitializeCerts(void)

- ea: `0x180053ab8`
- end: `0x180053cdd`
- name: `?KdcInitializeCerts@@YAJXZ`
- size: `549`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a5fc`

## callees

- `0x180010718`
- `0x1800107dc`
- `0x180037b04`
- `0x18004d854`
- `0x180053ab8`
- `0x1800569b8`
- `0x18005a060`
- `0x18005a090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180053c45`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180053c45`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x180053c81`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x180053c81`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053b94`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180053b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053ba6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053bb8`
- `CRYPT32!CertOpenStore` at `0x180053b3b`
- `CRYPT32!CertOpenStore` at `0x180053b3b`
- `CRYPT32!CertControlStore` at `0x180053c0e`
- `CRYPT32!CertControlStore` at `0x180053c0e`
- `ntdll!RtlInitializeCriticalSection` at `0x180053af1`
- `ntdll!RtlInitializeCriticalSection` at `0x180053af1`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180053be8`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180053be8`

## pseudocode

```c
__int64 KdcInitializeCerts(void)
{
  __int64 v0; // rax
  struct _RTL_RESOURCE *v1; // rcx
  NTSTATUS v2; // ebx
  HANDLE EventW; // rax
  unsigned int LastError; // eax
  char *v5; // rax
  char *v6; // rdi
  unsigned int v7; // esi
  const char *v8; // rcx
  const char *v9; // rbx
  __int64 v10; // r14
  _BYTE v12[40]; // [rsp+30h] [rbp-28h] BYREF
  char v13; // [rsp+60h] [rbp+8h] BYREF
  __int64 v14; // [rsp+68h] [rbp+10h] BYREF

  v13 = 1;
  v0 = lambda_2a70c627909d6c04886f368e19249c19_::_lambda_2a70c627909d6c04886f368e19249c19_(&v14, &v13);
  wil::scope_exit__lambda_2a70c627909d6c04886f368e19249c19___(v12, v0);
  v2 = RtlInitializeCriticalSection(&KdcGlobalCertCritSect);
  if ( v2 >= 0 )
  {
    KdcGlobalCertCritSectInitialized = 1;
    v2 = KdcInitializeResource(v1);
    if ( v2 >= 0 )
    {
      KdcGlobalDHParametersLockInitialized = 1;
      KdcCertStore = CertOpenStore((LPCSTR)0xA, 0, 0, 0x24001u, L"MY");
      if ( KdcCertStore )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        KdcCertStoreChangeEvent = EventW;
        if ( EventW
          && (KdcCertStoreWait = (void *)RegisterWaitForSingleObjectEx(EventW, KdcMyStoreWaitHandler, 0, 36000000, 0)) != 0
          && CertControlStore(KdcCertStore, 0, 2u, &KdcCertStoreChangeEvent) )
        {
          v5 = (char *)MIDL_user_allocate(0x15u);
          v6 = v5;
          if ( v5 )
          {
            v7 = 0;
            strcpy_s(v5, 0x15u, "1.2.840.113549.1.1.4");
            v8 = v6;
            v9 = v6;
            do
            {
              while ( *v9 && *v9 != 46 )
                ++v9;
              if ( *v9 == 46 )
                *v9++ = 0;
              else
                v9 = 0;
              v10 = 2LL * v7++;
              *((_DWORD *)&KdcSignatureAlg + 2 * v10 + 2) = (unsigned __int16)strtol(v8, 0, 0);
              *(&KdcSignatureAlg + v10) = (struct ASN1objectidentifier_s near *)(&KdcSignatureAlg + 2 * v7);
              v8 = v9;
            }
            while ( v9 );
            if ( v7 )
              *(&KdcSignatureAlg + v10) = 0;
            MIDL_user_free(v6);
            v2 = 0;
            v13 = 0;
          }
          else
          {
            v2 = -1073741670;
          }
        }
        else
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          v2 = LastError;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          GetLastError();
          WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2));
        }
        v2 = -1073741772;
      }
    }
  }
  wil::details::lambda_call__lambda_1761cddfefee5634a4b0112b78cfe4fa___::_lambda_call__lambda_1761cddfefee5634a4b0112b78cfe4fa___(v12);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180053ab8  mov     rax, rsp
0x180053abb  mov     [rax+18h], rbx
0x180053abf  mov     [rax+20h], rsi
0x180053ac3  push    rdi
0x180053ac4  push    r14
0x180053ac6  push    r15
0x180053ac8  sub     rsp, 40h
0x180053acc  lea     rdx, [rax+8]
0x180053ad0  mov     byte ptr [rax+8], 1
0x180053ad4  lea     rcx, [rax+10h]
0x180053ad8  call    _lambda_2a70c627909d6c04886f368e19249c19____lambda_2a70c627909d6c04886f368e19249c19_
0x180053add  mov     rdx, rax
0x180053ae0  lea     rcx, [rsp+58h+var_28]
0x180053ae5  call    wil__scope_exit__lambda_2a70c627909d6c04886f368e19249c19___
0x180053aea  lea     rcx, ?KdcGlobalCertCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180053af1  call    cs:__imp_RtlInitializeCriticalSection
0x180053af7  mov     ebx, eax
0x180053af9  test    eax, eax
0x180053afb  js      loc_180053CBD
0x180053b01  mov     cs:?KdcGlobalCertCritSectInitialized@@3EA, 1; uchar KdcGlobalCertCritSectInitialized
0x180053b08  call    ?KdcInitializeResource@@YAJPEAU_RTL_RESOURCE@@@Z; KdcInitializeResource(_RTL_RESOURCE *)
0x180053b0d  mov     ebx, eax
0x180053b0f  test    eax, eax
0x180053b11  js      loc_180053CBD
0x180053b17  xor     edx, edx; dwEncodingType
0x180053b19  mov     cs:?KdcGlobalDHParametersLockInitialized@@3KA, 1; ulong KdcGlobalDHParametersLockInitialized
0x180053b23  lea     rax, aMy; "MY"
0x180053b2a  mov     r9d, 24001h; dwFlags
0x180053b30  xor     r8d, r8d; hCryptProv
0x180053b33  mov     [rsp+58h+pvPara], rax; pvPara
0x180053b38  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180053b3b  call    cs:__imp_CertOpenStore
0x180053b41  mov     cs:?KdcCertStore@@3PEAXEA, rax; void * KdcCertStore
0x180053b48  test    rax, rax
0x180053b4b  jnz     short loc_180053B8A
0x180053b4d  mov     rax, cs:WPP_GLOBAL_Control
0x180053b54  lea     rcx, WPP_GLOBAL_Control
0x180053b5b  cmp     rax, rcx
0x180053b5e  jz      short loc_180053B80
0x180053b60  test    byte ptr [rax+1Ch], 1
0x180053b64  jz      short loc_180053B80
0x180053b66  call    cs:__imp_GetLastError
0x180053b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180053b73  mov     dword ptr [rsp+58h+pvPara], eax
0x180053b77  mov     rcx, [rcx+10h]
0x180053b7b  call    WPP_SF_SD
0x180053b80  mov     ebx, 0C0000034h
0x180053b85  jmp     loc_180053CBD
0x180053b8a  xor     r9d, r9d; lpName
0x180053b8d  xor     r8d, r8d; bInitialState
0x180053b90  xor     edx, edx; bManualReset
0x180053b92  xor     ecx, ecx; lpEventAttributes
0x180053b94  call    cs:__imp_CreateEventW
0x180053b9a  mov     cs:?KdcCertStoreChangeEvent@@3PEAXEA, rax; void * KdcCertStoreChangeEvent
0x180053ba1  test    rax, rax
0x180053ba4  jnz     short loc_180053BCD
0x180053ba6  call    cs:__imp_GetLastError
0x180053bac  test    eax, eax
0x180053bae  jg      short loc_180053BB8
0x180053bb0  call    cs:__imp_GetLastError
0x180053bb6  jmp     short loc_180053BC6
0x180053bb8  call    cs:__imp_GetLastError
0x180053bbe  movzx   eax, ax
0x180053bc1  or      eax, 0C0070000h
0x180053bc6  mov     ebx, eax
0x180053bc8  jmp     loc_180053CBD
0x180053bcd  mov     r9d, 2255100h
0x180053bd3  mov     dword ptr [rsp+58h+pvPara], 0
0x180053bdb  xor     r8d, r8d
0x180053bde  lea     rdx, ?KdcMyStoreWaitHandler@@YAXPEAXE@Z; KdcMyStoreWaitHandler(void *,uchar)
0x180053be5  mov     rcx, rax
0x180053be8  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180053bee  mov     cs:?KdcCertStoreWait@@3PEAXEA, rax; void * KdcCertStoreWait
0x180053bf5  test    rax, rax
0x180053bf8  jz      short loc_180053BA6
0x180053bfa  mov     rcx, cs:?KdcCertStore@@3PEAXEA; hCertStore
0x180053c01  lea     r9, ?KdcCertStoreChangeEvent@@3PEAXEA; pvCtrlPara
0x180053c08  xor     edx, edx; dwFlags
0x180053c0a  lea     r8d, [rdx+2]; dwCtrlType
0x180053c0e  call    cs:__imp_CertControlStore
0x180053c14  test    eax, eax
0x180053c16  jz      short loc_180053BA6
0x180053c18  mov     ebx, 15h
0x180053c1d  mov     ecx, ebx; size
0x180053c1f  call    MIDL_user_allocate
0x180053c24  mov     rdi, rax
0x180053c27  test    rax, rax
0x180053c2a  jnz     short loc_180053C36
0x180053c2c  mov     ebx, 0C000009Ah
0x180053c31  jmp     loc_180053CBD
0x180053c36  xor     esi, esi
0x180053c38  lea     r8, Source; "1.2.840.113549.1.1.4"
0x180053c3f  mov     rdx, rbx; SizeInBytes
0x180053c42  mov     rcx, rdi; Destination
0x180053c45  call    cs:__imp_strcpy_s
0x180053c4b  mov     rcx, rdi; String
0x180053c4e  lea     r15, ?KdcSignatureAlg@@3PAUASN1objectidentifier_s@@A; ASN1objectidentifier_s near * KdcSignatureAlg
0x180053c55  mov     rbx, rdi
0x180053c58  jmp     short loc_180053C61
0x180053c5a  cmp     al, 2Eh ; '.'
0x180053c5c  jz      short loc_180053C67
0x180053c5e  inc     rbx
0x180053c61  mov     al, [rbx]
0x180053c63  test    al, al
0x180053c65  jnz     short loc_180053C5A
0x180053c67  cmp     byte ptr [rbx], 2Eh ; '.'
0x180053c6a  jnz     short loc_180053C74
0x180053c6c  mov     byte ptr [rbx], 0
0x180053c6f  inc     rbx
0x180053c72  jmp     short loc_180053C76
0x180053c74  xor     ebx, ebx
0x180053c76  mov     r14d, esi
0x180053c79  xor     r8d, r8d; Radix
0x180053c7c  xor     edx, edx; EndPtr
0x180053c7e  add     r14, r14
0x180053c81  call    cs:__imp_strtol
0x180053c87  movzx   ecx, ax
0x180053c8a  inc     esi
0x180053c8c  mov     eax, esi
0x180053c8e  shl     rax, 4
0x180053c92  add     rax, r15
0x180053c95  mov     [r15+r14*8+8], ecx
0x180053c9a  mov     [r15+r14*8], rax
0x180053c9e  mov     rcx, rbx
0x180053ca1  test    rbx, rbx
0x180053ca4  jnz     short loc_180053C61
0x180053ca6  test    esi, esi
0x180053ca8  jz      short loc_180053CAE
0x180053caa  mov     [r15+r14*8], rbx
0x180053cae  mov     rcx, rdi; void *
0x180053cb1  call    MIDL_user_free
0x180053cb6  xor     ebx, ebx
0x180053cb8  mov     [rsp+58h+arg_0], 0
0x180053cbd  lea     rcx, [rsp+58h+var_28]
0x180053cc2  call    wil__details__lambda_call__lambda_1761cddfefee5634a4b0112b78cfe4fa______lambda_call__lambda_1761cddfefee5634a4b0112b78cfe4fa___
0x180053cc7  mov     rsi, [rsp+58h+arg_18]
0x180053ccc  mov     eax, ebx
0x180053cce  mov     rbx, [rsp+58h+arg_10]
0x180053cd3  add     rsp, 40h
0x180053cd7  pop     r15
0x180053cd9  pop     r14
0x180053cdb  pop     rdi
0x180053cdc  retn
```
