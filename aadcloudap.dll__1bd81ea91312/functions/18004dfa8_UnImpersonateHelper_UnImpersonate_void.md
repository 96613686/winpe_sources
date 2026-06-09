# UnImpersonateHelper::UnImpersonate(void)

- ea: `0x18004dfa8`
- end: `0x18004e0b7`
- name: `?UnImpersonate@UnImpersonateHelper@@QEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(UnImpersonateHelper *__hidden this)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002406c`
- `0x18002ba38`
- `0x180032e94`
- `0x18003ff18`
- `0x180048104`
- `0x18005950c`
- `0x180059b74`
- `0x18005ef08`
- `0x18006abd8`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x18001d16c`
- `0x18004dfa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e075`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004e06b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004e06b`
- `ntdll!RtlNtStatusToDosError` at `0x18004e009`
- `ntdll!RtlNtStatusToDosError` at `0x18004e009`
- `ntdll!NtOpenThreadToken` at `0x18004dff6`
- `ntdll!NtOpenThreadToken` at `0x18004dff6`

## string_xrefs

- `0x18004dfc2`: `UnImpersonateHelper::UnImpersonate`
- `0x18004e097`: `SetThreadToken un-impersonate`
- `0x18004e02b`: `NtOpenThreadToken un-impersonate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
UnImpersonate *__fastcall UnImpersonateHelper::UnImpersonate(UnImpersonate *this)
{
  int v2; // eax
  signed int v3; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  const char *v7[7]; // [rsp+30h] [rbp-38h] BYREF
  signed int v8; // [rsp+70h] [rbp+8h] BYREF

  v8 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v7,
    (int)"unimpersonatehelper.cpp",
    (int)"UnImpersonateHelper::UnImpersonate",
    (int)&v8);
  if ( !*((_QWORD *)this + 1) )
  {
    v2 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, (PHANDLE)this + 1);
    if ( v2 == -1073741700 )
    {
LABEL_8:
      *((_QWORD *)this + 1) = 0;
      goto LABEL_9;
    }
    if ( v2 < 0 )
    {
      v3 = RtlNtStatusToDosError(v2);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      v8 = v3;
      if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          Microsoft_Windows_AAD_Context,
          Aad_CloudAPPlugin_Error,
          L"NtOpenThreadToken un-impersonate",
          (unsigned int)v3);
      goto LABEL_8;
    }
    if ( !SetThreadToken(0, 0) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = LastError;
      if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          Microsoft_Windows_AAD_Context,
          Aad_CloudAPPlugin_Error,
          L"SetThreadToken un-impersonate",
          (unsigned int)LastError);
    }
    *(_BYTE *)this = 1;
  }
LABEL_9:
  v4 = v8;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v7);
  return (UnImpersonate *)v4;
}

```

## disassembly

```asm
0x18004dfa8  mov     rax, rsp
0x18004dfab  mov     [rax+10h], rbx
0x18004dfaf  push    rdi
0x18004dfb0  sub     rsp, 60h
0x18004dfb4  mov     rdi, rcx
0x18004dfb7  mov     dword ptr [rax+8], 0
0x18004dfbe  lea     r9, [rax+8]
0x18004dfc2  lea     r8, aUnimpersonateh; "UnImpersonateHelper::UnImpersonate"
0x18004dfc9  lea     rdx, aOnecoreuapDsEx_27+21h; "unimpersonatehelper.cpp"
0x18004dfd0  lea     rcx, [rax-38h]
0x18004dfd4  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18004dfd9  nop
0x18004dfda  lea     rbx, [rdi+8]
0x18004dfde  cmp     qword ptr [rbx], 0
0x18004dfe2  jnz     short loc_18004E04C
0x18004dfe4  mov     r9, rbx; TokenHandle
0x18004dfe7  mov     r8b, 1; OpenAsSelf
0x18004dfea  mov     edx, 0Ch; DesiredAccess
0x18004dfef  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18004dff6  call    cs:__imp_NtOpenThreadToken
0x18004dffc  cmp     eax, 0C000007Ch
0x18004e001  jz      short loc_18004E045
0x18004e003  test    eax, eax
0x18004e005  jns     short loc_18004E067
0x18004e007  mov     ecx, eax; Status
0x18004e009  call    cs:__imp_RtlNtStatusToDosError
0x18004e00f  test    eax, eax
0x18004e011  jle     short loc_18004E01B
0x18004e013  movzx   eax, ax
0x18004e016  or      eax, 80070000h
0x18004e01b  mov     [rsp+68h+arg_0], eax
0x18004e01f  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 2
0x18004e026  jz      short loc_18004E045
0x18004e028  mov     r9d, eax
0x18004e02b  lea     r8, aNtopenthreadto; "NtOpenThreadToken un-impersonate"
0x18004e032  lea     rdx, Aad_CloudAPPlugin_Error
0x18004e039  lea     rcx, Microsoft_Windows_AAD_Context
0x18004e040  call    McTemplateU0zq_EventWriteTransfer
0x18004e045  mov     qword ptr [rbx], 0
0x18004e04c  mov     ebx, [rsp+68h+arg_0]
0x18004e050  lea     rcx, [rsp+68h+var_38]
0x18004e055  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18004e05a  mov     eax, ebx
0x18004e05c  mov     rbx, [rsp+68h+arg_8]
0x18004e061  add     rsp, 60h
0x18004e065  pop     rdi
0x18004e066  retn
0x18004e067  xor     edx, edx; Token
0x18004e069  xor     ecx, ecx; Thread
0x18004e06b  call    cs:__imp_SetThreadToken
0x18004e071  test    eax, eax
0x18004e073  jnz     short loc_18004E0B1
0x18004e075  call    cs:__imp_GetLastError
0x18004e07b  test    eax, eax
0x18004e07d  jle     short loc_18004E087
0x18004e07f  movzx   eax, ax
0x18004e082  or      eax, 80070000h
0x18004e087  mov     [rsp+68h+arg_0], eax
0x18004e08b  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 2
0x18004e092  jz      short loc_18004E0B1
0x18004e094  mov     r9d, eax
0x18004e097  lea     r8, aSetthreadtoken; "SetThreadToken un-impersonate"
0x18004e09e  lea     rdx, Aad_CloudAPPlugin_Error
0x18004e0a5  lea     rcx, Microsoft_Windows_AAD_Context
0x18004e0ac  call    McTemplateU0zq_EventWriteTransfer
0x18004e0b1  mov     byte ptr [rdi], 1
0x18004e0b4  jmp     short loc_18004E04C
```
