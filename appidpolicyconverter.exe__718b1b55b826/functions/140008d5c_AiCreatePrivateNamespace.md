# AiCreatePrivateNamespace

- ea: `0x140008d5c`
- end: `0x140008eed`
- name: `AiCreatePrivateNamespace`
- size: `401`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000775c`

## callees

- `0x140007428`
- `0x140008d5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e94`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x140008df8`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x140008df8`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x140008e86`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x140008e86`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x140008da6`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x140008da6`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x140008eda`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x140008eda`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x140008e5f`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x140008e5f`

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
  qword_140020F70 = (__int64)qword_1400189C0;
  RequiredSid = qword_1400189B0;
  memset(&PrivateNamespaceAttributes, 0, sizeof(PrivateNamespaceAttributes));
  BoundaryDescriptor = CreateBoundaryDescriptorW(L"AppIDSvcBoundary", 0);
  if ( BoundaryDescriptor )
  {
    if ( AddSIDToBoundaryDescriptor(&BoundaryDescriptor, RequiredSid) )
    {
      PrivateNamespaceAttributes.lpSecurityDescriptor = (LPVOID)qword_140020F70;
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
0x140008d5c  mov     [rsp+arg_0], rbx
0x140008d61  push    rdi
0x140008d62  sub     rsp, 40h
0x140008d66  xor     eax, eax
0x140008d68  mov     [rsp+48h+BoundaryDescriptor], 0
0x140008d71  mov     qword ptr [rsp+48h+PrivateNamespaceAttributes.bInheritHandle], rax
0x140008d76  lea     rcx, aAppidsvcbounda; "AppIDSvcBoundary"
0x140008d7d  lea     rax, qword_1400189C0
0x140008d84  mov     rdi, rdx
0x140008d87  mov     cs:qword_140020F70, rax
0x140008d8e  xorps   xmm0, xmm0
0x140008d91  lea     rax, qword_1400189B0
0x140008d98  xor     edx, edx; Flags
0x140008d9a  mov     cs:RequiredSid, rax
0x140008da1  movups  xmmword ptr [rsp+48h+PrivateNamespaceAttributes.nLength], xmm0
0x140008da6  call    cs:__imp_CreateBoundaryDescriptorW
0x140008dac  mov     [rsp+48h+BoundaryDescriptor], rax
0x140008db1  test    rax, rax
0x140008db4  jnz     short loc_140008DEC
0x140008db6  call    cs:__imp_GetLastError
0x140008dbc  mov     ebx, eax
0x140008dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140008dc5  lea     rax, WPP_GLOBAL_Control
0x140008dcc  cmp     rcx, rax
0x140008dcf  jz      loc_140008ED0
0x140008dd5  test    dword ptr [rcx+1Ch], 400h
0x140008ddc  jz      loc_140008ED0
0x140008de2  mov     edx, 14h
0x140008de7  jmp     loc_140008EBD
0x140008dec  mov     rdx, cs:RequiredSid; RequiredSid
0x140008df3  lea     rcx, [rsp+48h+BoundaryDescriptor]; BoundaryDescriptor
0x140008df8  call    cs:__imp_AddSIDToBoundaryDescriptor
0x140008dfe  test    eax, eax
0x140008e00  jnz     short loc_140008E38
0x140008e02  call    cs:__imp_GetLastError
0x140008e08  mov     ebx, eax
0x140008e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e11  lea     rax, WPP_GLOBAL_Control
0x140008e18  cmp     rcx, rax
0x140008e1b  jz      loc_140008ED0
0x140008e21  test    dword ptr [rcx+1Ch], 400h
0x140008e28  jz      loc_140008ED0
0x140008e2e  mov     edx, 15h
0x140008e33  jmp     loc_140008EBD
0x140008e38  mov     rax, cs:qword_140020F70
0x140008e3f  lea     r8, AliasPrefix; "AppIDSvc"
0x140008e46  mov     rdx, [rsp+48h+BoundaryDescriptor]; lpBoundaryDescriptor
0x140008e4b  lea     rcx, [rsp+48h+PrivateNamespaceAttributes]; lpPrivateNamespaceAttributes
0x140008e50  mov     [rsp+48h+PrivateNamespaceAttributes.lpSecurityDescriptor], rax
0x140008e55  xor     ebx, ebx
0x140008e57  mov     [rsp+48h+PrivateNamespaceAttributes.nLength], 18h
0x140008e5f  call    cs:__imp_CreatePrivateNamespaceW
0x140008e65  mov     [rdi], rax
0x140008e68  test    rax, rax
0x140008e6b  jnz     short loc_140008E8F
0x140008e6d  call    cs:__imp_GetLastError
0x140008e73  cmp     eax, 0B7h
0x140008e78  jnz     short loc_140008E8F
0x140008e7a  mov     rcx, [rsp+48h+BoundaryDescriptor]; lpBoundaryDescriptor
0x140008e7f  lea     rdx, AliasPrefix; "AppIDSvc"
0x140008e86  call    cs:__imp_OpenPrivateNamespaceW
0x140008e8c  mov     [rdi], rax
0x140008e8f  cmp     [rdi], rbx
0x140008e92  jnz     short loc_140008ED0
0x140008e94  call    cs:__imp_GetLastError
0x140008e9a  mov     ebx, eax
0x140008e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ea3  lea     rax, WPP_GLOBAL_Control
0x140008eaa  cmp     rcx, rax
0x140008ead  jz      short loc_140008ED0
0x140008eaf  test    dword ptr [rcx+1Ch], 400h
0x140008eb6  jz      short loc_140008ED0
0x140008eb8  mov     edx, 16h
0x140008ebd  mov     rcx, [rcx+10h]
0x140008ec1  lea     r8, WPP_cdd24d3a097b35f56b152dc45e02695a_Traceguids
0x140008ec8  mov     r9d, ebx
0x140008ecb  call    WPP_SF_d
0x140008ed0  mov     rcx, [rsp+48h+BoundaryDescriptor]; BoundaryDescriptor
0x140008ed5  test    rcx, rcx
0x140008ed8  jz      short loc_140008EE0
0x140008eda  call    cs:__imp_DeleteBoundaryDescriptor
0x140008ee0  mov     eax, ebx
0x140008ee2  mov     rbx, [rsp+48h+arg_0]
0x140008ee7  add     rsp, 40h
0x140008eeb  pop     rdi
0x140008eec  retn
```
