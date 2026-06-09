# qmcomm_v1_0_S_QMAttachProcess

- ea: `0x180036830`
- end: `0x18003694d`
- name: `qmcomm_v1_0_S_QMAttachProcess`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800055c0`

## callees

- `0x180012ea8`
- `0x18002c61c`
- `0x180036830`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x1800368fa`
- `msvcrt!free` at `0x180036932`
- `msvcrt!free` at `0x1800368fa`
- `msvcrt!free` at `0x180036932`
- `ADVAPI32!CopySid` at `0x1800368f0`
- `ADVAPI32!CopySid` at `0x1800368f0`
- `ADVAPI32!GetTokenInformation` at `0x1800368a5`
- `ADVAPI32!GetTokenInformation` at `0x1800368d3`
- `ADVAPI32!GetTokenInformation` at `0x1800368a5`
- `ADVAPI32!GetTokenInformation` at `0x1800368d3`
- `ADVAPI32!OpenProcessToken` at `0x180036888`
- `ADVAPI32!OpenProcessToken` at `0x180036888`
- `ADVAPI32!GetLengthSid` at `0x1800368dc`
- `ADVAPI32!GetLengthSid` at `0x1800368dc`
- `KERNEL32!CloseHandle` at `0x18003685e`
- `KERNEL32!CloseHandle` at `0x18003685e`
- `KERNEL32!GetCurrentProcess` at `0x180036876`
- `KERNEL32!GetCurrentProcess` at `0x180036876`
- `KERNEL32!OpenProcess` at `0x180036850`
- `KERNEL32!OpenProcess` at `0x180036850`

## string_xrefs

- `0x18003691b`: `qmcommnd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall qmcomm_v1_0_S_QMAttachProcess(__int64 a1, DWORD a2, DWORD a3, void *a4, DWORD *a5)
{
  HANDLE v7; // rax
  HANDLE CurrentProcess; // rax
  PSID *v10; // rbx
  DWORD LengthSid; // ecx
  void *TokenHandle; // [rsp+30h] [rbp-18h] BYREF
  PSID *v13; // [rsp+38h] [rbp-10h]
  DWORD TokenInformationLength; // [rsp+78h] [rbp+30h] BYREF

  if ( a2 )
  {
    v7 = OpenProcess(0x40u, 0, a2);
    if ( v7 )
    {
      CloseHandle(v7);
      return 0;
    }
  }
  TokenHandle = 0;
  TokenInformationLength = 0;
  v13 = 0;
  CurrentProcess = GetCurrentProcess();
  OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v10 = (PSID *)MmAllocate(TokenInformationLength);
  v13 = v10;
  GetTokenInformation(TokenHandle, TokenUser, v10, TokenInformationLength, &TokenInformationLength);
  LengthSid = GetLengthSid(*v10);
  if ( a3 >= LengthSid )
  {
    CopySid(a3, a4, *v10);
    free(v10);
    CHandle::~CHandle((CHandle *)&TokenHandle);
    return 0;
  }
  *a5 = LengthSid;
  LogMsgHR(-1072824285, (wchar_t *)L"qmcommnd", 0x8Cu);
  free(v10);
  CHandle::~CHandle((CHandle *)&TokenHandle);
  return 3222143011LL;
}

```

## disassembly

```asm
0x180036830  push    rbp
0x180036832  push    rbx
0x180036833  push    rsi
0x180036834  push    rdi
0x180036835  mov     rbp, rsp
0x180036838  sub     rsp, 48h
0x18003683c  mov     rsi, r9
0x18003683f  mov     edi, r8d
0x180036842  xor     ebx, ebx
0x180036844  test    edx, edx
0x180036846  jz      short loc_18003686B
0x180036848  mov     r8d, edx; dwProcessId
0x18003684b  xor     edx, edx; bInheritHandle
0x18003684d  lea     ecx, [rbx+40h]; dwDesiredAccess
0x180036850  call    cs:__imp_OpenProcess
0x180036856  test    rax, rax
0x180036859  jz      short loc_18003686B
0x18003685b  mov     rcx, rax; hObject
0x18003685e  call    cs:__imp_CloseHandle
0x180036864  xor     eax, eax
0x180036866  jmp     loc_180036944
0x18003686b  mov     [rbp+TokenHandle], rbx
0x18003686f  mov     [rbp+TokenInformationLength], ebx
0x180036872  mov     [rbp+var_10], rbx
0x180036876  call    cs:__imp_GetCurrentProcess
0x18003687c  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180036880  mov     edx, 8; DesiredAccess
0x180036885  mov     rcx, rax; ProcessHandle
0x180036888  call    cs:__imp_OpenProcessToken
0x18003688e  lea     rax, [rbp+TokenInformationLength]
0x180036892  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180036897  xor     r9d, r9d; TokenInformationLength
0x18003689a  xor     r8d, r8d; TokenInformation
0x18003689d  lea     edx, [r9+1]; TokenInformationClass
0x1800368a1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800368a5  call    cs:__imp_GetTokenInformation
0x1800368ab  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x1800368ae  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800368b3  mov     rbx, rax
0x1800368b6  mov     [rbp+var_10], rax
0x1800368ba  lea     rax, [rbp+TokenInformationLength]
0x1800368be  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800368c3  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800368c7  mov     r8, rbx; TokenInformation
0x1800368ca  mov     edx, 1; TokenInformationClass
0x1800368cf  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800368d3  call    cs:__imp_GetTokenInformation
0x1800368d9  mov     rcx, [rbx]; pSid
0x1800368dc  call    cs:__imp_GetLengthSid
0x1800368e2  mov     ecx, eax
0x1800368e4  cmp     edi, eax
0x1800368e6  jb      short loc_18003690F
0x1800368e8  mov     r8, [rbx]; pSourceSid
0x1800368eb  mov     rdx, rsi; pDestinationSid
0x1800368ee  mov     ecx, edi; nDestinationSidLength
0x1800368f0  call    cs:__imp_CopySid
0x1800368f6  nop
0x1800368f7  mov     rcx, rbx; Block
0x1800368fa  call    cs:__imp_free
0x180036900  nop
0x180036901  lea     rcx, [rbp+TokenHandle]; this
0x180036905  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18003690a  jmp     loc_180036864
0x18003690f  mov     rax, [rbp+arg_20]
0x180036913  mov     [rax], ecx
0x180036915  mov     r8d, 8Ch; unsigned __int16
0x18003691b  lea     rdx, aQmcommnd; "qmcommnd"
0x180036922  mov     edi, 0C00E0023h
0x180036927  mov     ecx, edi; int
0x180036929  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18003692e  nop
0x18003692f  mov     rcx, rbx; Block
0x180036932  call    cs:__imp_free
0x180036938  nop
0x180036939  lea     rcx, [rbp+TokenHandle]; this
0x18003693d  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180036942  mov     eax, edi
0x180036944  add     rsp, 48h
0x180036948  pop     rdi
0x180036949  pop     rsi
0x18003694a  pop     rbx
0x18003694b  pop     rbp
0x18003694c  retn
```
