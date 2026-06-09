# CheckAndGetCapability(WELL_KNOWN_SID_TYPE,void *,int *,void * *)

- ea: `0x1800d5060`
- end: `0x1800d519f`
- name: `?CheckAndGetCapability@@YAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAHPEAPEAX@Z`
- size: `319`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void *, int *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800c8d04`
- `0x1800d4f6c`

## callees

- `0x180027d9c`
- `0x18002be34`
- `0x18003aa84`
- `0x1800d5060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d511d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d511d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d5107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d5107`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d50c2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d50c2`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800d514e`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800d514e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800d513b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800d513b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d5099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d5099`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800d50e4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800d50e4`

## pseudocode

```c
__int64 __fastcall CheckAndGetCapability(WELL_KNOWN_SID_TYPE WellKnownSidType, void *a2, int *a3, void **a4)
{
  void *v7; // rax
  void *v8; // rbp
  int Error; // ebx
  HRESULT v10; // edi
  void *v11; // r14
  HANDLE CurrentThread; // rax
  void *cbSid; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF
  void *v16; // [rsp+68h] [rbp+20h] BYREF

  cbSid = a2;
  if ( a4 )
    *a4 = 0;
  *a3 = 0;
  LODWORD(cbSid) = 68;
  v7 = CoTaskMemAlloc(0x44u);
  v16 = v7;
  v8 = v7;
  if ( !v7 )
  {
    Error = -2147024882;
    goto LABEL_22;
  }
  if ( CreateWellKnownSid(WellKnownSidType, 0, v7, (DWORD *)&cbSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    TokenHandle = 0;
    v10 = CoImpersonateClient();
    if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147417833 )
    {
      Error = v10;
LABEL_21:
      CAutoHandle<void *>::~CAutoHandle<void *>(&TokenHandle);
      goto LABEL_22;
    }
    v11 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    if ( v10 >= 0 )
    {
      v11 = TokenHandle;
      CoRevertToSelf();
    }
    if ( Error < 0 )
      goto LABEL_21;
    if ( (unsigned int)CheckTokenCapability(v11, v8, a3) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_21;
    }
    if ( a4 )
    {
      v16 = 0;
      *a4 = v8;
    }
    goto LABEL_21;
  }
LABEL_22:
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v16);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800d5060  mov     [rsp+arg_0], rbx
0x1800d5065  mov     [rsp+cbSid], rdx
0x1800d506a  push    rbp
0x1800d506b  push    rsi
0x1800d506c  push    rdi
0x1800d506d  push    r14
0x1800d506f  push    r15
0x1800d5071  sub     rsp, 20h
0x1800d5075  mov     rsi, r9
0x1800d5078  mov     r15, r8
0x1800d507b  mov     ebx, ecx
0x1800d507d  test    r9, r9
0x1800d5080  jz      short loc_1800D5089
0x1800d5082  mov     qword ptr [r9], 0
0x1800d5089  mov     ecx, 44h ; 'D'; cb
0x1800d508e  mov     dword ptr [r8], 0
0x1800d5095  mov     dword ptr [rsp+48h+cbSid], ecx
0x1800d5099  call    cs:__imp_CoTaskMemAlloc
0x1800d509f  mov     [rsp+48h+arg_18], rax
0x1800d50a4  mov     rbp, rax
0x1800d50a7  test    rax, rax
0x1800d50aa  jnz     short loc_1800D50B6
0x1800d50ac  mov     ebx, 8007000Eh
0x1800d50b1  jmp     loc_1800D5182
0x1800d50b6  lea     r9, [rsp+48h+cbSid]; cbSid
0x1800d50bb  mov     r8, rbp; pSid
0x1800d50be  xor     edx, edx; DomainSid
0x1800d50c0  mov     ecx, ebx; WellKnownSidType
0x1800d50c2  call    cs:__imp_CreateWellKnownSid
0x1800d50c8  test    eax, eax
0x1800d50ca  jnz     short loc_1800D50DB
0x1800d50cc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d50d1  mov     ebx, eax
0x1800d50d3  test    eax, eax
0x1800d50d5  js      loc_1800D5182
0x1800d50db  mov     [rsp+48h+TokenHandle], 0
0x1800d50e4  call    cs:__imp_CoImpersonateClient
0x1800d50ea  mov     edi, eax
0x1800d50ec  mov     eax, 80000000h
0x1800d50f1  lea     ecx, [rdi+rax]
0x1800d50f4  test    eax, ecx
0x1800d50f6  jnz     short loc_1800D5104
0x1800d50f8  cmp     edi, 80010117h
0x1800d50fe  jz      short loc_1800D5104
0x1800d5100  mov     ebx, edi
0x1800d5102  jmp     short loc_1800D5178
0x1800d5104  xor     r14d, r14d
0x1800d5107  call    cs:__imp_GetCurrentThread
0x1800d510d  mov     rcx, rax; ThreadHandle
0x1800d5110  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800d5115  lea     edx, [r14+8]; DesiredAccess
0x1800d5119  lea     r8d, [r14+1]; OpenAsSelf
0x1800d511d  call    cs:__imp_OpenThreadToken
0x1800d5123  test    eax, eax
0x1800d5125  jz      short loc_1800D512B
0x1800d5127  xor     ebx, ebx
0x1800d5129  jmp     short loc_1800D5132
0x1800d512b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d5130  mov     ebx, eax
0x1800d5132  test    edi, edi
0x1800d5134  js      short loc_1800D5141
0x1800d5136  mov     r14, [rsp+48h+TokenHandle]
0x1800d513b  call    cs:__imp_CoRevertToSelf
0x1800d5141  test    ebx, ebx
0x1800d5143  js      short loc_1800D5178
0x1800d5145  mov     r8, r15
0x1800d5148  mov     rdx, rbp
0x1800d514b  mov     rcx, r14
0x1800d514e  call    cs:__imp_CheckTokenCapability
0x1800d5154  test    eax, eax
0x1800d5156  jz      short loc_1800D515C
0x1800d5158  xor     ebx, ebx
0x1800d515a  jmp     short loc_1800D5167
0x1800d515c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d5161  mov     ebx, eax
0x1800d5163  test    eax, eax
0x1800d5165  js      short loc_1800D5178
0x1800d5167  test    rsi, rsi
0x1800d516a  jz      short loc_1800D5178
0x1800d516c  mov     [rsp+48h+arg_18], 0
0x1800d5175  mov     [rsi], rbp
0x1800d5178  lea     rcx, [rsp+48h+TokenHandle]
0x1800d517d  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1800d5182  lea     rcx, [rsp+48h+arg_18]
0x1800d5187  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800d518c  mov     eax, ebx
0x1800d518e  mov     rbx, [rsp+48h+arg_0]
0x1800d5193  add     rsp, 20h
0x1800d5197  pop     r15
0x1800d5199  pop     r14
0x1800d519b  pop     rdi
0x1800d519c  pop     rsi
0x1800d519d  pop     rbp
0x1800d519e  retn
```
