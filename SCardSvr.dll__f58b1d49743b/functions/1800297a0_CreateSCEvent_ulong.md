# CreateSCEvent(ulong)

- ea: `0x1800297a0`
- end: `0x180029948`
- name: `?CreateSCEvent@@YAPEAXK@Z`
- size: `424`
- prototype: `HANDLE __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001a21c`
- `0x18001a2ac`
- `0x180029f78`

## callees

- `0x1800143c0`
- `0x1800297a0`
- `0x1800319e4`
- `0x180031bd8`
- `0x180031d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800298b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800298b0`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800297c3`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800298d5`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800298fa`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002992a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800297c3`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800298d5`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800298fa`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002992a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002990e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002990e`

## pseudocode

```c
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
0x1800297a0  mov     [rsp-8+arg_0], rbx
0x1800297a5  mov     [rsp-8+arg_8], rdi
0x1800297aa  push    rbp
0x1800297ab  mov     rbp, rsp
0x1800297ae  sub     rsp, 70h
0x1800297b2  mov     edi, ecx
0x1800297b4  call    ?CalaisString@@YAPEBGK@Z; CalaisString(ulong)
0x1800297b9  mov     r8, rax; lpName
0x1800297bc  xor     edx, edx; bInheritHandle
0x1800297be  mov     ecx, 100002h; dwDesiredAccess
0x1800297c3  call    cs:__imp_OpenEventW
0x1800297c9  mov     rbx, rax
0x1800297cc  test    rax, rax
0x1800297cf  jnz     loc_180029936
0x1800297d5  call    cs:__imp_GetLastError
0x1800297db  cmp     eax, 2
0x1800297de  jnz     loc_18002990E
0x1800297e4  xorps   xmm0, xmm0
0x1800297e7  movdqa  [rbp+var_50], xmm0
0x1800297ec  xorps   xmm1, xmm1
0x1800297ef  movdqa  [rbp+var_40], xmm1
0x1800297f4  mov     [rbp+var_30], rbx
0x1800297f8  mov     [rbp+var_10], ebx
0x1800297fb  lea     rcx, [rbp+var_50]; this
0x1800297ff  call    ?Initialize@CSecurityDescriptor@@QEAAJXZ; CSecurityDescriptor::Initialize(void)
0x180029804  test    eax, eax
0x180029806  jns     short loc_180029818
0x180029808  lea     rcx, [rbp+var_50]; this
0x18002980c  call    ??1CSecurityDescriptor@@QEAA@XZ; CSecurityDescriptor::~CSecurityDescriptor(void)
0x180029811  xor     eax, eax
0x180029813  jmp     loc_180029936
0x180029818  mov     r8d, 100002h; unsigned int
0x18002981e  lea     rdx, ?SID_LocalService@CSecurityDescriptor@@2USecurityId@1@B; struct CSecurityDescriptor::SecurityId *
0x180029825  lea     rcx, [rbp+var_50]; this
0x180029829  call    ?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z; CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)
0x18002982e  mov     r8d, 100000h; unsigned int
0x180029834  lea     rdx, ?SID_NetworkService@CSecurityDescriptor@@2USecurityId@1@B; struct CSecurityDescriptor::SecurityId *
0x18002983b  lea     rcx, [rbp+var_50]; this
0x18002983f  call    ?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z; CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)
0x180029844  mov     r8d, 100000h; unsigned int
0x18002984a  lea     rdx, ?SID_Interactive@CSecurityDescriptor@@2USecurityId@1@B; struct CSecurityDescriptor::SecurityId *
0x180029851  lea     rcx, [rbp+var_50]; this
0x180029855  call    ?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z; CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)
0x18002985a  mov     r8d, 100000h; unsigned int
0x180029860  lea     rdx, ?SID_System@CSecurityDescriptor@@2USecurityId@1@B; struct CSecurityDescriptor::SecurityId *
0x180029867  lea     rcx, [rbp+var_50]; this
0x18002986b  call    ?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z; CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)
0x180029870  mov     r8d, 100000h; unsigned int
0x180029876  lea     rdx, ?SID_SharedUserCertCapability@CSecurityDescriptor@@2USecurityId@1@B; struct CSecurityDescriptor::SecurityId *
0x18002987d  lea     rcx, [rbp+var_50]; this
0x180029881  call    ?Allow@CSecurityDescriptor@@QEAAJPEBUSecurityId@1@K@Z; CSecurityDescriptor::Allow(CSecurityDescriptor::SecurityId const *,ulong)
0x180029886  mov     [rbp+EventAttributes.nLength], 18h
0x18002988d  mov     rax, qword ptr [rbp+var_50]
0x180029891  mov     [rbp+EventAttributes.lpSecurityDescriptor], rax
0x180029895  mov     eax, [rbp+var_10]
0x180029898  mov     [rbp+EventAttributes.bInheritHandle], eax
0x18002989b  mov     ecx, edi; unsigned int
0x18002989d  call    ?CalaisString@@YAPEBGK@Z; CalaisString(ulong)
0x1800298a2  mov     r9, rax; lpName
0x1800298a5  xor     r8d, r8d; bInitialState
0x1800298a8  lea     edx, [r8+1]; bManualReset
0x1800298ac  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x1800298b0  call    cs:__imp_CreateEventW
0x1800298b6  mov     rbx, rax
0x1800298b9  call    cs:__imp_GetLastError
0x1800298bf  cmp     eax, 5
0x1800298c2  jnz     short loc_180029903
0x1800298c4  mov     ecx, edi; unsigned int
0x1800298c6  call    ?CalaisString@@YAPEBGK@Z; CalaisString(ulong)
0x1800298cb  mov     r8, rax; lpName
0x1800298ce  xor     edx, edx; bInheritHandle
0x1800298d0  mov     ecx, 100002h; dwDesiredAccess
0x1800298d5  call    cs:__imp_OpenEventW
0x1800298db  mov     rbx, rax
0x1800298de  call    cs:__imp_GetLastError
0x1800298e4  cmp     eax, 5
0x1800298e7  jnz     short loc_180029903
0x1800298e9  mov     ecx, edi; unsigned int
0x1800298eb  call    ?CalaisString@@YAPEBGK@Z; CalaisString(ulong)
0x1800298f0  mov     r8, rax; lpName
0x1800298f3  xor     edx, edx; bInheritHandle
0x1800298f5  mov     ecx, 100000h; dwDesiredAccess
0x1800298fa  call    cs:__imp_OpenEventW
0x180029900  mov     rbx, rax
0x180029903  lea     rcx, [rbp+var_50]; this
0x180029907  call    ??1CSecurityDescriptor@@QEAA@XZ; CSecurityDescriptor::~CSecurityDescriptor(void)
0x18002990c  jmp     short loc_180029933
0x18002990e  call    cs:__imp_GetLastError
0x180029914  cmp     eax, 5
0x180029917  jnz     short loc_180029933
0x180029919  mov     ecx, edi; unsigned int
0x18002991b  call    ?CalaisString@@YAPEBGK@Z; CalaisString(ulong)
0x180029920  mov     r8, rax; lpName
0x180029923  xor     edx, edx; bInheritHandle
0x180029925  mov     ecx, 100000h; dwDesiredAccess
0x18002992a  call    cs:__imp_OpenEventW
0x180029930  mov     rbx, rax
0x180029933  mov     rax, rbx
0x180029936  lea     r11, [rsp+70h+var_s0]
0x18002993b  mov     rbx, [r11+10h]
0x18002993f  mov     rdi, [r11+18h]
0x180029943  mov     rsp, r11
0x180029946  pop     rbp
0x180029947  retn
```
