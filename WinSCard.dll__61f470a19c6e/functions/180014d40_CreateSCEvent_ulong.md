# CreateSCEvent(ulong)

- ea: `0x180014d40`
- end: `0x180014ee8`
- name: `?CreateSCEvent@@YAPEAXK@Z`
- size: `424`
- prototype: `void *__fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006400`
- `0x180007f40`
- `0x180014970`
- `0x1800210b0`

## callees

- `0x180014d40`
- `0x180014ef0`
- `0x18002e93c`
- `0x18002eb30`
- `0x18002ec68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014e50`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014e50`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180014d63`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180014e75`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180014e9a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180014eca`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180014d63`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180014e75`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180014e9a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180014eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HANDLE __fastcall CreateSCEvent(unsigned int a1)
{
  const WCHAR *v2; // rax
  HANDLE result; // rax
  HANDLE v4; // rbx
  const WCHAR *v5; // rax
  const WCHAR *v6; // rax
  const WCHAR *v7; // rax
  const WCHAR *v8; // rax
  _OWORD v9[2]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v10; // [rsp+40h] [rbp-30h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+48h] [rbp-28h] BYREF
  BOOL v12; // [rsp+60h] [rbp-10h]

  v2 = CalaisString(a1);
  result = OpenEventW(0x100002u, 0, v2);
  v4 = result;
  if ( !result )
  {
    if ( GetLastError() == 2 )
    {
      memset(v9, 0, sizeof(v9));
      v10 = 0;
      v12 = 0;
      if ( (int)CSecurityDescriptor::Initialize((CSecurityDescriptor *)v9) < 0 )
      {
        CSecurityDescriptor::~CSecurityDescriptor((CSecurityDescriptor *)v9);
        return 0;
      }
      CSecurityDescriptor::Allow(
        (CSecurityDescriptor *)v9,
        (const struct CSecurityDescriptor::SecurityId *)&CSecurityDescriptor::SID_LocalService,
        0x100002u);
      CSecurityDescriptor::Allow(
        (CSecurityDescriptor *)v9,
        (const struct CSecurityDescriptor::SecurityId *)&CSecurityDescriptor::SID_NetworkService,
        0x100000u);
      CSecurityDescriptor::Allow(
        (CSecurityDescriptor *)v9,
        (const struct CSecurityDescriptor::SecurityId *)&CSecurityDescriptor::SID_Interactive,
        0x100000u);
      CSecurityDescriptor::Allow(
        (CSecurityDescriptor *)v9,
        (const struct CSecurityDescriptor::SecurityId *)&CSecurityDescriptor::SID_System,
        0x100000u);
      CSecurityDescriptor::Allow(
        (CSecurityDescriptor *)v9,
        (const struct CSecurityDescriptor::SecurityId *)&CSecurityDescriptor::SID_SharedUserCertCapability,
        0x100000u);
      EventAttributes.nLength = 24;
      EventAttributes.lpSecurityDescriptor = *(LPVOID *)&v9[0];
      EventAttributes.bInheritHandle = v12;
      v5 = CalaisString(a1);
      v4 = CreateEventW(&EventAttributes, 1, 0, v5);
      if ( GetLastError() == 5 )
      {
        v6 = CalaisString(a1);
        v4 = OpenEventW(0x100002u, 0, v6);
        if ( GetLastError() == 5 )
        {
          v7 = CalaisString(a1);
          v4 = OpenEventW(0x100000u, 0, v7);
        }
      }
      CSecurityDescriptor::~CSecurityDescriptor((CSecurityDescriptor *)v9);
    }
    else if ( GetLastError() == 5 )
    {
      v8 = CalaisString(a1);
      return OpenEventW(0x100000u, 0, v8);
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180014d40  mov     [rsp-8+arg_0], rbx
0x180014d45  mov     [rsp-8+arg_8], rdi
0x180014d4a  push    rbp
0x180014d4b  mov     rbp, rsp
0x180014d4e  sub     rsp, 70h
0x180014d52  mov     edi, ecx
0x180014d54  call    ?CalaisString@@YAPEBGK@Z; CalaisString(ulong)
0x180014d59  mov     r8, rax; lpName
0x180014d5c  xor     edx, edx; bInheritHandle
0x180014d5e  mov     ecx, 100002h; dwDesiredAccess
0x180014d63  call    cs:__imp_OpenEventW
0x180014d69  mov     rbx, rax
0x180014d6c  test    rax, rax
0x180014d6f  jnz     loc_180014ED6
0x180014d75  call    cs:__imp_GetLastError
0x180014d7b  cmp     eax, 2
0x180014d7e  jnz     loc_180014EAE
0x180014d84  xorps   xmm0, xmm0
0x180014d87  movdqa  [rbp+var_50], xmm0
0x180014d8c  xorps   xmm1, xmm1
0x180014d8f  movdqa  [rbp+var_40], xmm1
0x180014d94  mov     [rbp+var_30], rbx
0x180014d98  mov     [rbp+var_10], ebx
0x180014d9b  lea     rcx, [rbp+var_50]; this
0x180014d9f  call    ?Initialize@CSecurityDescriptor@@QEAAJXZ; CSecurityDescriptor::Initialize(void)
0x180014da4  test    eax, eax
0x180014da6  jns     short loc_180014DB8
0x180014da8  lea     rcx, [rbp+var_50]; this
0x180014dac  call    ??1CSecurityDescriptor@@QEAA@XZ; CSecurityDescriptor::~CSecurityDescriptor(void)
0x180014db1  xor     eax, eax
0x180014db3  jmp     loc_180014ED6
0x180014db8  mov     r8d, 100002h; unsigned int
0x180014dbe  lea     rdx, ?SID_LocalService@CSecurityDescriptor@@2USecurityId@1@B; struct CSecurityDescriptor::SecurityId *
0x180014dc5  lea     rcx, [rbp+var_50]; this
0x180014dc9  call    ?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z; CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)
0x180014dce  mov     r8d, 100000h; unsigned int
0x180014dd4  lea     rdx, ?SID_NetworkService@CSecurityDescriptor@@2USecurityId@1@B; struct CSecurityDescriptor::SecurityId *
0x180014ddb  lea     rcx, [rbp+var_50]; this
0x180014ddf  call    ?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z; CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)
0x180014de4  mov     r8d, 100000h; unsigned int
0x180014dea  lea     rdx, ?SID_Interactive@CSecurityDescriptor@@2USecurityId@1@B; struct CSecurityDescriptor::SecurityId *
0x180014df1  lea     rcx, [rbp+var_50]; this
0x180014df5  call    ?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z; CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)
0x180014dfa  mov     r8d, 100000h; unsigned int
0x180014e00  lea     rdx, ?SID_System@CSecurityDescriptor@@2USecurityId@1@B; struct CSecurityDescriptor::SecurityId *
0x180014e07  lea     rcx, [rbp+var_50]; this
0x180014e0b  call    ?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z; CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)
0x180014e10  mov     r8d, 100000h; unsigned int
0x180014e16  lea     rdx, ?SID_SharedUserCertCapability@CSecurityDescriptor@@2USecurityId@1@B; struct CSecurityDescriptor::SecurityId *
0x180014e1d  lea     rcx, [rbp+var_50]; this
0x180014e21  call    ?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z; CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)
0x180014e26  mov     [rbp+EventAttributes.nLength], 18h
0x180014e2d  mov     rax, qword ptr [rbp+var_50]
0x180014e31  mov     [rbp+EventAttributes.lpSecurityDescriptor], rax
0x180014e35  mov     eax, [rbp+var_10]
0x180014e38  mov     [rbp+EventAttributes.bInheritHandle], eax
0x180014e3b  mov     ecx, edi; unsigned int
0x180014e3d  call    ?CalaisString@@YAPEBGK@Z; CalaisString(ulong)
0x180014e42  mov     r9, rax; lpName
0x180014e45  xor     r8d, r8d; bInitialState
0x180014e48  lea     edx, [r8+1]; bManualReset
0x180014e4c  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x180014e50  call    cs:__imp_CreateEventW
0x180014e56  mov     rbx, rax
0x180014e59  call    cs:__imp_GetLastError
0x180014e5f  cmp     eax, 5
0x180014e62  jnz     short loc_180014EA3
0x180014e64  mov     ecx, edi; unsigned int
0x180014e66  call    ?CalaisString@@YAPEBGK@Z; CalaisString(ulong)
0x180014e6b  mov     r8, rax; lpName
0x180014e6e  xor     edx, edx; bInheritHandle
0x180014e70  mov     ecx, 100002h; dwDesiredAccess
0x180014e75  call    cs:__imp_OpenEventW
0x180014e7b  mov     rbx, rax
0x180014e7e  call    cs:__imp_GetLastError
0x180014e84  cmp     eax, 5
0x180014e87  jnz     short loc_180014EA3
0x180014e89  mov     ecx, edi; unsigned int
0x180014e8b  call    ?CalaisString@@YAPEBGK@Z; CalaisString(ulong)
0x180014e90  mov     r8, rax; lpName
0x180014e93  xor     edx, edx; bInheritHandle
0x180014e95  mov     ecx, 100000h; dwDesiredAccess
0x180014e9a  call    cs:__imp_OpenEventW
0x180014ea0  mov     rbx, rax
0x180014ea3  lea     rcx, [rbp+var_50]; this
0x180014ea7  call    ??1CSecurityDescriptor@@QEAA@XZ; CSecurityDescriptor::~CSecurityDescriptor(void)
0x180014eac  jmp     short loc_180014ED3
0x180014eae  call    cs:__imp_GetLastError
0x180014eb4  cmp     eax, 5
0x180014eb7  jnz     short loc_180014ED3
0x180014eb9  mov     ecx, edi; unsigned int
0x180014ebb  call    ?CalaisString@@YAPEBGK@Z; CalaisString(ulong)
0x180014ec0  mov     r8, rax; lpName
0x180014ec3  xor     edx, edx; bInheritHandle
0x180014ec5  mov     ecx, 100000h; dwDesiredAccess
0x180014eca  call    cs:__imp_OpenEventW
0x180014ed0  mov     rbx, rax
0x180014ed3  mov     rax, rbx
0x180014ed6  lea     r11, [rsp+70h+var_s0]
0x180014edb  mov     rbx, [r11+10h]
0x180014edf  mov     rdi, [r11+18h]
0x180014ee3  mov     rsp, r11
0x180014ee6  pop     rbp
0x180014ee7  retn
```
