# CopySidAlloc

- ea: `0x180009e60`
- end: `0x180009f7d`
- name: `CopySidAlloc`
- size: `285`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009f84`
- `0x18000a06c`

## callees

- `0x180002214`
- `0x180003180`
- `0x180009e60`
- `0x18000dce4`
- `0x18000dd60`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009f05`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009f05`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009ec9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180009ec9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009eb0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009f2c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009eb0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009f2c`

## string_xrefs

- `0x180009e87`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x180009f14`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`
- `0x180009f45`: `C:\__w\1\s\src\Client\lib\util\SecurityUtil.cpp`

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
0x180009e60  mov     [rsp+arg_10], rbx
0x180009e65  mov     [rsp+arg_18], rbp
0x180009e6a  push    rsi
0x180009e6b  push    rdi
0x180009e6c  push    r14; int
0x180009e6e  sub     rsp, 20h
0x180009e72  mov     r14, rdx
0x180009e75  mov     rsi, rcx
0x180009e78  test    rcx, rcx
0x180009e7b  jnz     short loc_180009EA2
0x180009e7d  mov     edx, 157h; void *
0x180009e82  mov     rcx, [rsp+38h]; this
0x180009e87  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180009e8e  mov     ebx, 80004003h
0x180009e93  mov     r9d, ebx; char *
0x180009e96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e9b  mov     eax, ebx
0x180009e9d  jmp     loc_180009F6A
0x180009ea2  test    r14, r14
0x180009ea5  jnz     short loc_180009EAE
0x180009ea7  mov     edx, 158h
0x180009eac  jmp     short loc_180009E82
0x180009eae  xor     ebx, ebx
0x180009eb0  call    cs:__imp_IsValidSid
0x180009eb6  test    eax, eax
0x180009eb8  jnz     short loc_180009EC6
0x180009eba  mov     edi, 80070057h
0x180009ebf  mov     edx, 15Ch
0x180009ec4  jmp     short loc_180009F40
0x180009ec6  mov     rcx, rsi; pSid
0x180009ec9  call    cs:__imp_GetLengthSid
0x180009ecf  mov     ebp, eax
0x180009ed1  test    eax, eax
0x180009ed3  jz      short loc_180009EFD
0x180009ed5  mov     ecx, ebp; unsigned __int64
0x180009ed7  mov     edx, 1; unsigned __int64
0x180009edc  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180009ee1  mov     rbx, rax
0x180009ee4  neg     rax
0x180009ee7  sbb     edi, edi
0x180009ee9  not     edi
0x180009eeb  and     edi, 8007000Eh
0x180009ef1  test    rbx, rbx
0x180009ef4  jnz     short loc_180009EFD
0x180009ef6  mov     edx, 162h
0x180009efb  jmp     short loc_180009F40
0x180009efd  mov     r8, rsi; pSourceSid
0x180009f00  mov     rdx, rbx; pDestinationSid
0x180009f03  mov     ecx, ebp; nDestinationSidLength
0x180009f05  call    cs:__imp_CopySid
0x180009f0b  test    eax, eax
0x180009f0d  jnz     short loc_180009F29
0x180009f0f  mov     rcx, [rsp+38h]; this
0x180009f14  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180009f1b  mov     edx, 163h; void *
0x180009f20  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009f25  mov     edi, eax
0x180009f27  jmp     short loc_180009F54
0x180009f29  mov     rcx, rbx; pSid
0x180009f2c  call    cs:__imp_IsValidSid
0x180009f32  test    eax, eax
0x180009f34  jnz     short loc_180009F63
0x180009f36  mov     edi, 80240FFFh
0x180009f3b  mov     edx, 164h; void *
0x180009f40  mov     rcx, [rsp+38h]; this
0x180009f45  lea     r8, aCW1SSrcClientL_17; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180009f4c  mov     r9d, edi; char *
0x180009f4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f54  test    rbx, rbx
0x180009f57  jz      short loc_180009F68
0x180009f59  mov     rcx, rbx; lpMem
0x180009f5c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180009f61  jmp     short loc_180009F68
0x180009f63  mov     [r14], rbx
0x180009f66  xor     edi, edi
0x180009f68  mov     eax, edi
0x180009f6a  mov     rbx, [rsp+38h+arg_10]
0x180009f6f  mov     rbp, [rsp+38h+arg_18]
0x180009f74  add     rsp, 20h
0x180009f78  pop     r14
0x180009f7a  pop     rdi
0x180009f7b  pop     rsi
0x180009f7c  retn
```
