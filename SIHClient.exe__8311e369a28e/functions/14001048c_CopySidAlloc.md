# CopySidAlloc

- ea: `0x14001048c`
- end: `0x1400105a9`
- name: `CopySidAlloc`
- size: `285`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400105b0`
- `0x140010698`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x14000ce30`
- `0x14000ce9c`
- `0x14001048c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1400104dc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140010558`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1400104dc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140010558`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140010531`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140010531`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400104f5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400104f5`

## string_xrefs

- `0x1400104b3`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x140010540`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x140010571`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

## pseudocode

```c
__int64 __fastcall CopySidAlloc(PSID pSourceSid, _QWORD *a2)
{
  __int64 v4; // rdx
  void *v6; // rbx
  unsigned int LastError; // edi
  __int64 v8; // rdx
  DWORD LengthSid; // eax
  DWORD v10; // ebp
  const char *v11; // r9
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !pSourceSid )
  {
    v4 = 343;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)0x80004003LL,
      v12);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    v4 = 344;
    goto LABEL_3;
  }
  v6 = 0;
  if ( !IsValidSid(pSourceSid) )
  {
    LastError = -2147024809;
    v8 = 348;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
      (const char *)LastError,
      v12);
LABEL_16:
    if ( v6 )
      SusFree(v6);
    return LastError;
  }
  LengthSid = GetLengthSid(pSourceSid);
  v10 = LengthSid;
  if ( LengthSid )
  {
    v6 = SafeSusAllocArray(LengthSid, 1u);
    LastError = v6 == 0 ? 0x8007000E : 0;
    if ( !v6 )
    {
      v8 = 354;
      goto LABEL_15;
    }
  }
  if ( !CopySid(v10, v6, pSourceSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x163,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityUtil.cpp",
                  v11);
    goto LABEL_16;
  }
  if ( !IsValidSid(v6) )
  {
    LastError = -2145120257;
    v8 = 356;
    goto LABEL_15;
  }
  *a2 = v6;
  return 0;
}

```

## disassembly

```asm
0x14001048c  mov     [rsp+arg_10], rbx
0x140010491  mov     [rsp+arg_18], rbp
0x140010496  push    rsi
0x140010497  push    rdi
0x140010498  push    r14; int
0x14001049a  sub     rsp, 20h
0x14001049e  mov     r14, rdx
0x1400104a1  mov     rsi, rcx
0x1400104a4  test    rcx, rcx
0x1400104a7  jnz     short loc_1400104CE
0x1400104a9  mov     edx, 157h; void *
0x1400104ae  mov     rcx, [rsp+38h]; this
0x1400104b3  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400104ba  mov     ebx, 80004003h
0x1400104bf  mov     r9d, ebx; char *
0x1400104c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400104c7  mov     eax, ebx
0x1400104c9  jmp     loc_140010596
0x1400104ce  test    r14, r14
0x1400104d1  jnz     short loc_1400104DA
0x1400104d3  mov     edx, 158h
0x1400104d8  jmp     short loc_1400104AE
0x1400104da  xor     ebx, ebx
0x1400104dc  call    cs:__imp_IsValidSid
0x1400104e2  test    eax, eax
0x1400104e4  jnz     short loc_1400104F2
0x1400104e6  mov     edi, 80070057h
0x1400104eb  mov     edx, 15Ch
0x1400104f0  jmp     short loc_14001056C
0x1400104f2  mov     rcx, rsi; pSid
0x1400104f5  call    cs:__imp_GetLengthSid
0x1400104fb  mov     ebp, eax
0x1400104fd  test    eax, eax
0x1400104ff  jz      short loc_140010529
0x140010501  mov     ecx, ebp; unsigned __int64
0x140010503  mov     edx, 1; unsigned __int64
0x140010508  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14001050d  mov     rbx, rax
0x140010510  neg     rax
0x140010513  sbb     edi, edi
0x140010515  not     edi
0x140010517  and     edi, 8007000Eh
0x14001051d  test    rbx, rbx
0x140010520  jnz     short loc_140010529
0x140010522  mov     edx, 162h
0x140010527  jmp     short loc_14001056C
0x140010529  mov     r8, rsi; pSourceSid
0x14001052c  mov     rdx, rbx; pDestinationSid
0x14001052f  mov     ecx, ebp; nDestinationSidLength
0x140010531  call    cs:__imp_CopySid
0x140010537  test    eax, eax
0x140010539  jnz     short loc_140010555
0x14001053b  mov     rcx, [rsp+38h]; this
0x140010540  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140010547  mov     edx, 163h; void *
0x14001054c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140010551  mov     edi, eax
0x140010553  jmp     short loc_140010580
0x140010555  mov     rcx, rbx; pSid
0x140010558  call    cs:__imp_IsValidSid
0x14001055e  test    eax, eax
0x140010560  jnz     short loc_14001058F
0x140010562  mov     edi, 80240FFFh
0x140010567  mov     edx, 164h; void *
0x14001056c  mov     rcx, [rsp+38h]; this
0x140010571  lea     r8, aCW1SSrcClientL_23; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140010578  mov     r9d, edi; char *
0x14001057b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010580  test    rbx, rbx
0x140010583  jz      short loc_140010594
0x140010585  mov     rcx, rbx; lpMem
0x140010588  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14001058d  jmp     short loc_140010594
0x14001058f  mov     [r14], rbx
0x140010592  xor     edi, edi
0x140010594  mov     eax, edi
0x140010596  mov     rbx, [rsp+38h+arg_10]
0x14001059b  mov     rbp, [rsp+38h+arg_18]
0x1400105a0  add     rsp, 20h
0x1400105a4  pop     r14
0x1400105a6  pop     rdi
0x1400105a7  pop     rsi
0x1400105a8  retn
```
