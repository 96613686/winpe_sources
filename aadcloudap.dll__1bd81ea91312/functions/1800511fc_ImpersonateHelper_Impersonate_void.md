# ImpersonateHelper::Impersonate(void *)

- ea: `0x1800511fc`
- end: `0x180051292`
- name: `?Impersonate@ImpersonateHelper@@QEAAJPEAX@Z`
- size: `150`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle, HANDLE Token)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800513d0`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x1800511fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051258`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005124e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005124e`
- `ntdll!NtOpenThreadToken` at `0x180051243`
- `ntdll!NtOpenThreadToken` at `0x180051243`

## string_xrefs

- `0x180051219`: `ImpersonateHelper::Impersonate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ImpersonateHelper::Impersonate(PHANDLE TokenHandle, HANDLE Token)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  const char *v7[7]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v8; // [rsp+70h] [rbp+8h] BYREF

  v8 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v7,
    (int)"lsalogon.cpp",
    (int)"ImpersonateHelper::Impersonate",
    (int)&v8);
  NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, TokenHandle);
  if ( SetThreadToken(0, Token) )
  {
    *((_BYTE *)TokenHandle + 8) = 1;
    v5 = v8;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v8 = v5;
  }
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v7);
  return v5;
}

```

## disassembly

```asm
0x1800511fc  mov     rax, rsp
0x1800511ff  mov     [rax+10h], rbx
0x180051203  push    rdi
0x180051204  sub     rsp, 60h
0x180051208  mov     rbx, rdx
0x18005120b  mov     rdi, rcx
0x18005120e  mov     dword ptr [rax+8], 0
0x180051215  lea     r9, [rax+8]
0x180051219  lea     r8, aImpersonatehel; "ImpersonateHelper::Impersonate"
0x180051220  lea     rdx, aOnecoreuapDsEx_54+21h; "lsalogon.cpp"
0x180051227  lea     rcx, [rax-38h]
0x18005122b  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180051230  nop
0x180051231  mov     r9, rdi; TokenHandle
0x180051234  mov     r8b, 1; OpenAsSelf
0x180051237  mov     edx, 0Ch; DesiredAccess
0x18005123c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180051243  call    cs:__imp_NtOpenThreadToken
0x180051249  mov     rdx, rbx; Token
0x18005124c  xor     ecx, ecx; Thread
0x18005124e  call    cs:__imp_SetThreadToken
0x180051254  test    eax, eax
0x180051256  jnz     short loc_180051273
0x180051258  call    cs:__imp_GetLastError
0x18005125e  mov     ebx, eax
0x180051260  test    eax, eax
0x180051262  jle     short loc_18005126D
0x180051264  movzx   ebx, ax
0x180051267  or      ebx, 80070000h
0x18005126d  mov     [rsp+68h+arg_0], ebx
0x180051271  jmp     short loc_18005127B
0x180051273  mov     byte ptr [rdi+8], 1
0x180051277  mov     ebx, [rsp+68h+arg_0]
0x18005127b  lea     rcx, [rsp+68h+var_38]
0x180051280  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180051285  mov     eax, ebx
0x180051287  mov     rbx, [rsp+68h+arg_8]
0x18005128c  add     rsp, 60h
0x180051290  pop     rdi
0x180051291  retn
```
