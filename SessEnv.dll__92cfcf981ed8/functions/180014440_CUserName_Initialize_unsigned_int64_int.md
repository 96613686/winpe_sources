# CUserName::Initialize(unsigned __int64,int)

- ea: `0x180014440`
- end: `0x1800145cd`
- name: `?Initialize@CUserName@@UEAAJ_KH@Z`
- size: `397`
- prototype: `int(CUserName *__hidden this, unsigned __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003f30`
- `0x180014440`
- `0x1800178e0`
- `0x18001a280`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x1800144de`
- `ntdll!NtDuplicateToken` at `0x1800144de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001452f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001452f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014525`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180014525`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001457b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001457b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800144f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800144fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800144f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800144fb`

## string_xrefs

- `0x180014561`: `NtDuplicateToken failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserName::Initialize(void **this, void *a2, int a3)
{
  HANDLE *v5; // r14
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  HANDLE CurrentProcess; // rbx
  HANDLE v9; // rax
  signed int LastError; // eax
  DWORD CurrentProcessId; // eax
  int v13; // eax
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-9h] BYREF
  _DWORD v15[4]; // [rsp+78h] [rbp+27h] BYREF

  if ( !a3 )
  {
    v13 = CUserName::InitializeUserName((CUserName *)this, a2);
    v7 = v13;
    if ( v13 < 0 )
    {
      _DbgPrintMessage(8, "InitializeUserName failed: 0x%x in %s", (unsigned int)v13, "CUserName::Initialize");
      return v7;
    }
    return 0;
  }
  v5 = this + 199;
  v15[2] = 1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  v15[0] = 12;
  v15[1] = 2;
  ObjectAttributes.SecurityQualityOfService = v15;
  v6 = NtDuplicateToken(a2, 0x2000000u, &ObjectAttributes, 0, TokenPrimary, this + 199);
  v7 = v6 | 0x10000000;
  if ( (v6 | 0x10000000) != 0xD0000022 )
  {
    if ( v6 < 0 )
    {
      _DbgPrintMessage(8, "NtDuplicateToken failed: 0x%x in %s", v7, "CUserName::Initialize");
      return v7;
    }
    goto LABEL_10;
  }
  CurrentProcess = GetCurrentProcess();
  v9 = GetCurrentProcess();
  if ( DuplicateHandle(v9, a2, CurrentProcess, v5, 0, 0, 2u) )
  {
LABEL_10:
    CurrentProcessId = GetCurrentProcessId();
    *((_DWORD *)this + 400) |= 1u;
    *((_DWORD *)this + 672) = CurrentProcessId;
    return 0;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  _DbgPrintMessage(8, "DuplicateHandle failed: 0x%x", v7);
  return v7;
}

```

## disassembly

```asm
0x180014440  mov     r11, rsp
0x180014443  mov     [r11+18h], rbx
0x180014447  mov     [r11+20h], rsi
0x18001444b  push    rbp
0x18001444c  push    rdi
0x18001444d  push    r14
0x18001444f  lea     rbp, [r11-5Fh]
0x180014453  sub     rsp, 90h
0x18001445a  mov     rax, cs:__security_cookie
0x180014461  xor     rax, rsp
0x180014464  mov     [rbp+57h+var_20], rax
0x180014468  mov     rsi, rdx
0x18001446b  mov     rdi, rcx
0x18001446e  test    r8d, r8d
0x180014471  jz      loc_1800145B6
0x180014477  lea     r14, [rcx+638h]
0x18001447e  mov     [rbp+57h+var_28], 1
0x180014485  lea     rax, [rbp+57h+var_30]
0x180014489  mov     [r11-80h], r14
0x18001448d  xor     r9d, r9d; EffectiveOnly
0x180014490  mov     [rsp+0A0h+TokenType], 1; TokenType
0x180014498  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001449c  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800144a4  mov     edx, 2000000h; DesiredAccess
0x1800144a9  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0
0x1800144b1  mov     rcx, rsi; ExistingTokenHandle
0x1800144b4  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800144bc  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1800144c4  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x1800144cc  mov     [rbp+57h+var_30], 0Ch
0x1800144d3  mov     [rbp+57h+var_2C], 2
0x1800144da  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x1800144de  call    cs:__imp_NtDuplicateToken
0x1800144e4  mov     ebx, eax
0x1800144e6  bts     ebx, 1Ch
0x1800144ea  cmp     ebx, 0D0000022h
0x1800144f0  jnz     short loc_18001455A
0x1800144f2  call    cs:__imp_GetCurrentProcess
0x1800144f8  mov     rbx, rax
0x1800144fb  call    cs:__imp_GetCurrentProcess
0x180014501  mov     [rsp+0A0h+dwOptions], 2; dwOptions
0x180014509  mov     r9, r14; lpTargetHandle
0x18001450c  mov     rcx, rax; hSourceProcessHandle
0x18001450f  mov     [rsp+0A0h+bInheritHandle], 0; bInheritHandle
0x180014517  mov     r8, rbx; hTargetProcessHandle
0x18001451a  mov     [rsp+0A0h+TokenType], 0; dwDesiredAccess
0x180014522  mov     rdx, rsi; hSourceHandle
0x180014525  call    cs:__imp_DuplicateHandle
0x18001452b  test    eax, eax
0x18001452d  jnz     short loc_18001457B
0x18001452f  call    cs:__imp_GetLastError
0x180014535  mov     ebx, eax
0x180014537  test    eax, eax
0x180014539  jle     short loc_180014544
0x18001453b  movzx   ebx, ax
0x18001453e  or      ebx, 80070000h
0x180014544  mov     r8d, ebx
0x180014547  lea     rdx, aDuplicatehandl; "DuplicateHandle failed: 0x%x"
0x18001454e  mov     ecx, 8; int
0x180014553  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014558  jmp     short loc_180014590
0x18001455a  test    ebx, ebx
0x18001455c  jns     short loc_18001457B
0x18001455e  mov     r8d, ebx
0x180014561  lea     rdx, aNtduplicatetok; "NtDuplicateToken failed: 0x%x in %s"
0x180014568  lea     r9, aCusernameIniti_1; "CUserName::Initialize"
0x18001456f  mov     ecx, 8; int
0x180014574  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014579  jmp     short loc_180014590
0x18001457b  call    cs:__imp_GetCurrentProcessId
0x180014581  or      dword ptr [rdi+640h], 1
0x180014588  mov     [rdi+0A80h], eax
0x18001458e  xor     ebx, ebx
0x180014590  mov     eax, ebx
0x180014592  mov     rcx, [rbp+57h+var_20]
0x180014596  xor     rcx, rsp; StackCookie
0x180014599  call    __security_check_cookie
0x18001459e  lea     r11, [rsp+0A0h+var_10]
0x1800145a6  mov     rbx, [r11+30h]
0x1800145aa  mov     rsi, [r11+38h]
0x1800145ae  mov     rsp, r11
0x1800145b1  pop     r14
0x1800145b3  pop     rdi
0x1800145b4  pop     rbp
0x1800145b5  retn
0x1800145b6  call    ?InitializeUserName@CUserName@@AEAAJPEAX@Z; CUserName::InitializeUserName(void *)
0x1800145bb  mov     ebx, eax
0x1800145bd  test    eax, eax
0x1800145bf  jns     short loc_18001458E
0x1800145c1  mov     r8d, eax
0x1800145c4  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x1800145cb  jmp     short loc_180014568
```
