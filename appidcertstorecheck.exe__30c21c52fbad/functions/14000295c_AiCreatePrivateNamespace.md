# AiCreatePrivateNamespace

- ea: `0x14000295c`
- end: `0x140002aed`
- name: `AiCreatePrivateNamespace`
- size: `401`
- prototype: `__int64 __fastcall(__int64, HANDLE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400024e8`

## callees

- `0x14000241c`
- `0x14000295c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400029b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400029b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a94`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x1400029a6`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x1400029a6`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x1400029f8`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x1400029f8`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x140002ada`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x140002ada`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x140002a5f`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x140002a5f`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x140002a86`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x140002a86`

## pseudocode

```c
__int64 __fastcall AiCreatePrivateNamespace(__int64 a1, HANDLE *a2)
{
  DWORD LastError; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  HANDLE v6; // rax
  struct _SECURITY_ATTRIBUTES PrivateNamespaceAttributes; // [rsp+20h] [rbp-28h] BYREF
  HANDLE BoundaryDescriptor; // [rsp+60h] [rbp+18h] BYREF

  BoundaryDescriptor = 0;
  qword_1400056F8 = (__int64)qword_140003768;
  RequiredSid = qword_140003758;
  memset(&PrivateNamespaceAttributes, 0, sizeof(PrivateNamespaceAttributes));
  BoundaryDescriptor = CreateBoundaryDescriptorW(L"AppIDSvcBoundary", 0);
  if ( BoundaryDescriptor )
  {
    if ( AddSIDToBoundaryDescriptor(&BoundaryDescriptor, RequiredSid) )
    {
      PrivateNamespaceAttributes.lpSecurityDescriptor = (LPVOID)qword_1400056F8;
      LastError = 0;
      PrivateNamespaceAttributes.nLength = 24;
      v6 = CreatePrivateNamespaceW(&PrivateNamespaceAttributes, BoundaryDescriptor, L"AppIDSvc");
      *a2 = v6;
      if ( !v6 && GetLastError() == 183 )
        *a2 = OpenPrivateNamespaceW(BoundaryDescriptor, L"AppIDSvc");
      if ( !*a2 )
      {
        LastError = GetLastError();
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          v5 = 22;
          goto LABEL_16;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        v5 = 21;
        goto LABEL_16;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v5 = 20;
LABEL_16:
      WPP_SF_d(v4[2], v5, WPP_cdd24d3a097b35f56b152dc45e02695a_Traceguids, LastError);
    }
  }
  if ( BoundaryDescriptor )
    DeleteBoundaryDescriptor(BoundaryDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x14000295c  mov     [rsp+arg_0], rbx
0x140002961  push    rdi
0x140002962  sub     rsp, 40h
0x140002966  xor     eax, eax
0x140002968  mov     [rsp+48h+BoundaryDescriptor], 0
0x140002971  mov     qword ptr [rsp+48h+PrivateNamespaceAttributes.bInheritHandle], rax
0x140002976  lea     rcx, aAppidsvcbounda; "AppIDSvcBoundary"
0x14000297d  lea     rax, qword_140003768
0x140002984  mov     rdi, rdx
0x140002987  mov     cs:qword_1400056F8, rax
0x14000298e  xorps   xmm0, xmm0
0x140002991  lea     rax, qword_140003758
0x140002998  xor     edx, edx; Flags
0x14000299a  mov     cs:RequiredSid, rax
0x1400029a1  movups  xmmword ptr [rsp+48h+PrivateNamespaceAttributes.nLength], xmm0
0x1400029a6  call    cs:__imp_CreateBoundaryDescriptorW
0x1400029ac  mov     [rsp+48h+BoundaryDescriptor], rax
0x1400029b1  test    rax, rax
0x1400029b4  jnz     short loc_1400029EC
0x1400029b6  call    cs:__imp_GetLastError
0x1400029bc  mov     ebx, eax
0x1400029be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029c5  lea     rax, WPP_GLOBAL_Control
0x1400029cc  cmp     rcx, rax
0x1400029cf  jz      loc_140002AD0
0x1400029d5  test    dword ptr [rcx+1Ch], 400h
0x1400029dc  jz      loc_140002AD0
0x1400029e2  mov     edx, 14h
0x1400029e7  jmp     loc_140002ABD
0x1400029ec  mov     rdx, cs:RequiredSid; RequiredSid
0x1400029f3  lea     rcx, [rsp+48h+BoundaryDescriptor]; BoundaryDescriptor
0x1400029f8  call    cs:__imp_AddSIDToBoundaryDescriptor
0x1400029fe  test    eax, eax
0x140002a00  jnz     short loc_140002A38
0x140002a02  call    cs:__imp_GetLastError
0x140002a08  mov     ebx, eax
0x140002a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a11  lea     rax, WPP_GLOBAL_Control
0x140002a18  cmp     rcx, rax
0x140002a1b  jz      loc_140002AD0
0x140002a21  test    dword ptr [rcx+1Ch], 400h
0x140002a28  jz      loc_140002AD0
0x140002a2e  mov     edx, 15h
0x140002a33  jmp     loc_140002ABD
0x140002a38  mov     rax, cs:qword_1400056F8
0x140002a3f  lea     r8, AliasPrefix; "AppIDSvc"
0x140002a46  mov     rdx, [rsp+48h+BoundaryDescriptor]; lpBoundaryDescriptor
0x140002a4b  lea     rcx, [rsp+48h+PrivateNamespaceAttributes]; lpPrivateNamespaceAttributes
0x140002a50  mov     [rsp+48h+PrivateNamespaceAttributes.lpSecurityDescriptor], rax
0x140002a55  xor     ebx, ebx
0x140002a57  mov     [rsp+48h+PrivateNamespaceAttributes.nLength], 18h
0x140002a5f  call    cs:__imp_CreatePrivateNamespaceW
0x140002a65  mov     [rdi], rax
0x140002a68  test    rax, rax
0x140002a6b  jnz     short loc_140002A8F
0x140002a6d  call    cs:__imp_GetLastError
0x140002a73  cmp     eax, 0B7h
0x140002a78  jnz     short loc_140002A8F
0x140002a7a  mov     rcx, [rsp+48h+BoundaryDescriptor]; lpBoundaryDescriptor
0x140002a7f  lea     rdx, AliasPrefix; "AppIDSvc"
0x140002a86  call    cs:__imp_OpenPrivateNamespaceW
0x140002a8c  mov     [rdi], rax
0x140002a8f  cmp     [rdi], rbx
0x140002a92  jnz     short loc_140002AD0
0x140002a94  call    cs:__imp_GetLastError
0x140002a9a  mov     ebx, eax
0x140002a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002aa3  lea     rax, WPP_GLOBAL_Control
0x140002aaa  cmp     rcx, rax
0x140002aad  jz      short loc_140002AD0
0x140002aaf  test    dword ptr [rcx+1Ch], 400h
0x140002ab6  jz      short loc_140002AD0
0x140002ab8  mov     edx, 16h
0x140002abd  mov     rcx, [rcx+10h]
0x140002ac1  lea     r8, WPP_cdd24d3a097b35f56b152dc45e02695a_Traceguids
0x140002ac8  mov     r9d, ebx
0x140002acb  call    WPP_SF_d
0x140002ad0  mov     rcx, [rsp+48h+BoundaryDescriptor]; BoundaryDescriptor
0x140002ad5  test    rcx, rcx
0x140002ad8  jz      short loc_140002AE0
0x140002ada  call    cs:__imp_DeleteBoundaryDescriptor
0x140002ae0  mov     eax, ebx
0x140002ae2  mov     rbx, [rsp+48h+arg_0]
0x140002ae7  add     rsp, 40h
0x140002aeb  pop     rdi
0x140002aec  retn
```
