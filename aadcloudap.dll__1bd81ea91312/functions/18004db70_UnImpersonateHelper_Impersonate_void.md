# UnImpersonateHelper::Impersonate(void)

- ea: `0x18004db70`
- end: `0x18004dc20`
- name: `?Impersonate@UnImpersonateHelper@@QEAAJXZ`
- size: `176`
- prototype: `__int64 __fastcall(UnImpersonateHelper *__hidden this)`
- caller_count: `11`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020bb4`
- `0x18002406c`
- `0x18002ba38`
- `0x180032e94`
- `0x18003ff18`
- `0x180048104`
- `0x18004db58`
- `0x18005950c`
- `0x18005990c`
- `0x18005ef28`
- `0x18006abd8`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x18001d16c`
- `0x18004db70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dbb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dbb9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004dbaf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004dbaf`
- `ntdll!NtClose` at `0x18004dbf9`
- `ntdll!NtClose` at `0x18004dbf9`

## string_xrefs

- `0x18004dbdb`: `SetThreadToken impersonate`
- `0x18004db86`: `UnImpersonateHelper::Impersonate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UnImpersonateHelper::Impersonate(UnImpersonateHelper *this)
{
  void *v2; // rdx
  signed int LastError; // eax
  unsigned int v4; // ebx
  const char *v6[7]; // [rsp+30h] [rbp-38h] BYREF
  signed int v7; // [rsp+70h] [rbp+8h] BYREF

  v7 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v6,
    (int)"unimpersonatehelper.cpp",
    (int)"UnImpersonateHelper::Impersonate",
    (int)&v7);
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    if ( *(_BYTE *)this && !SetThreadToken(0, v2) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError;
      if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          Microsoft_Windows_AAD_Context,
          Aad_CloudAPPlugin_Error,
          L"SetThreadToken impersonate",
          (unsigned int)LastError);
    }
    NtClose(*((HANDLE *)this + 1));
    *((_QWORD *)this + 1) = 0;
    *(_BYTE *)this = 0;
  }
  v4 = v7;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v6);
  return v4;
}

```

## disassembly

```asm
0x18004db70  push    rbx
0x18004db72  sub     rsp, 60h
0x18004db76  mov     rbx, rcx
0x18004db79  mov     [rsp+68h+arg_0], 0
0x18004db81  lea     r9, [rsp+68h+arg_0]
0x18004db86  lea     r8, aUnimpersonateh_0; "UnImpersonateHelper::Impersonate"
0x18004db8d  lea     rdx, aOnecoreuapDsEx_27+21h; "unimpersonatehelper.cpp"
0x18004db94  lea     rcx, [rsp+68h+var_38]
0x18004db99  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18004db9e  nop
0x18004db9f  mov     rdx, [rbx+8]; Token
0x18004dba3  test    rdx, rdx
0x18004dba6  jz      short loc_18004DC0A
0x18004dba8  cmp     byte ptr [rbx], 0
0x18004dbab  jz      short loc_18004DBF5
0x18004dbad  xor     ecx, ecx; Thread
0x18004dbaf  call    cs:__imp_SetThreadToken
0x18004dbb5  test    eax, eax
0x18004dbb7  jnz     short loc_18004DBF5
0x18004dbb9  call    cs:__imp_GetLastError
0x18004dbbf  test    eax, eax
0x18004dbc1  jle     short loc_18004DBCB
0x18004dbc3  movzx   eax, ax
0x18004dbc6  or      eax, 80070000h
0x18004dbcb  mov     [rsp+68h+arg_0], eax
0x18004dbcf  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 2
0x18004dbd6  jz      short loc_18004DBF5
0x18004dbd8  mov     r9d, eax
0x18004dbdb  lea     r8, aSetthreadtoken_0; "SetThreadToken impersonate"
0x18004dbe2  lea     rdx, Aad_CloudAPPlugin_Error
0x18004dbe9  lea     rcx, Microsoft_Windows_AAD_Context
0x18004dbf0  call    McTemplateU0zq_EventWriteTransfer
0x18004dbf5  mov     rcx, [rbx+8]; Handle
0x18004dbf9  call    cs:__imp_NtClose
0x18004dbff  mov     qword ptr [rbx+8], 0
0x18004dc07  mov     byte ptr [rbx], 0
0x18004dc0a  mov     ebx, [rsp+68h+arg_0]
0x18004dc0e  lea     rcx, [rsp+68h+var_38]
0x18004dc13  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18004dc18  mov     eax, ebx
0x18004dc1a  add     rsp, 60h
0x18004dc1e  pop     rbx
0x18004dc1f  retn
```
