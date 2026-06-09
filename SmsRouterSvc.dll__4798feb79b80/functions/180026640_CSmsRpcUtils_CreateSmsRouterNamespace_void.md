# CSmsRpcUtils::CreateSmsRouterNamespace(void * *)

- ea: `0x180026640`
- end: `0x1800267ef`
- name: `?CreateSmsRouterNamespace@CSmsRpcUtils@@SAJPEAPEAX@Z`
- size: `431`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015c78`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x180026640`
- `0x180026f00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002675c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002675c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800267bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800267bc`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x18002674e`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x18002674e`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180026784`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180026784`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180026739`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x1800267ab`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180026739`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x1800267ab`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180026716`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180026716`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x1800266e1`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x1800266e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800266b1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800266b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSmsRpcUtils::CreateSmsRouterNamespace(void **a1)
{
  signed int UserSid; // edi
  const WCHAR *v3; // rcx
  signed int v4; // eax
  PSID v5; // rbx
  signed int v6; // eax
  signed int v7; // eax
  HANDLE PrivateNamespaceW; // rsi
  signed int LastError; // eax
  signed int v10; // eax
  HANDLE BoundaryDescriptor; // [rsp+20h] [rbp-40h] BYREF
  PSID Sid[2]; // [rsp+28h] [rbp-38h] BYREF
  LPCWSTR StringSid[2]; // [rsp+38h] [rbp-28h] BYREF
  __m128i si128; // [rsp+48h] [rbp-18h]

  Sid[0] = 0;
  *(_OWORD *)StringSid = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(StringSid[0]) = 0;
  Sid[1] = 0;
  BoundaryDescriptor = 0;
  UserSid = CSmsRpcUtils::GetUserSid(StringSid);
  if ( UserSid >= 0 )
  {
    v3 = (const WCHAR *)StringSid;
    if ( si128.m128i_i64[1] > 7uLL )
      v3 = StringSid[0];
    if ( ConvertStringSidToSidW(v3, Sid) )
    {
      v5 = Sid[0];
      BoundaryDescriptor = CreateBoundaryDescriptorW(L"SmsRouter", 0);
      if ( BoundaryDescriptor )
      {
        if ( AddSIDToBoundaryDescriptor(&BoundaryDescriptor, Sid[0]) )
        {
          PrivateNamespaceW = CreatePrivateNamespaceW(0, BoundaryDescriptor, L"SmsRouter");
          if ( !PrivateNamespaceW )
          {
            LastError = GetLastError();
            UserSid = LastError;
            if ( LastError > 0 )
              UserSid = (unsigned __int16)LastError | 0x80070000;
            if ( UserSid != -2147024713 )
            {
              PrivateNamespaceW = OpenPrivateNamespaceW(BoundaryDescriptor, L"SmsRouter");
              if ( !PrivateNamespaceW )
              {
                v10 = GetLastError();
                UserSid = v10;
                if ( v10 > 0 )
                  UserSid = (unsigned __int16)v10 | 0x80070000;
              }
            }
          }
          DeleteBoundaryDescriptor(BoundaryDescriptor);
          *a1 = PrivateNamespaceW;
        }
        else
        {
          v7 = GetLastError();
          UserSid = v7;
          if ( v7 > 0 )
            UserSid = (unsigned __int16)v7 | 0x80070000;
          DeleteBoundaryDescriptor(BoundaryDescriptor);
        }
      }
      else
      {
        v6 = GetLastError();
        UserSid = v6;
        if ( v6 > 0 )
          UserSid = (unsigned __int16)v6 | 0x80070000;
      }
      if ( v5 )
        LocalFree(v5);
    }
    else
    {
      v4 = GetLastError();
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      UserSid = v4;
    }
  }
  std::wstring::~wstring((char **)StringSid);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180026640  mov     [rsp-18h+arg_8], rbx
0x180026645  mov     [rsp-18h+arg_10], rsi
0x18002664a  push    rbp
0x18002664b  push    rdi
0x18002664c  push    r14
0x18002664e  mov     rbp, rsp
0x180026651  sub     rsp, 60h
0x180026655  mov     rax, cs:__security_cookie
0x18002665c  xor     rax, rsp
0x18002665f  mov     [rbp+var_8], rax
0x180026663  mov     r14, rcx
0x180026666  mov     [rbp+Sid], 0
0x18002666e  xorps   xmm0, xmm0
0x180026671  movups  xmmword ptr [rbp+StringSid], xmm0
0x180026675  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002667d  movdqu  [rbp+var_18], xmm1
0x180026682  xor     eax, eax
0x180026684  mov     word ptr [rbp+StringSid], ax
0x180026688  mov     [rbp+var_30], rax
0x18002668c  mov     [rbp+BoundaryDescriptor], rax
0x180026690  lea     rcx, [rbp+StringSid]
0x180026694  call    ?GetUserSid@CSmsRpcUtils@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CSmsRpcUtils::GetUserSid(std::wstring &)
0x180026699  mov     edi, eax
0x18002669b  test    eax, eax
0x18002669d  js      short loc_1800266CF
0x18002669f  lea     rcx, [rbp+StringSid]
0x1800266a3  cmp     qword ptr [rbp+var_18+8], 7
0x1800266a8  cmova   rcx, [rbp+StringSid]; StringSid
0x1800266ad  lea     rdx, [rbp+Sid]; Sid
0x1800266b1  call    cs:__imp_ConvertStringSidToSidW
0x1800266b7  test    eax, eax
0x1800266b9  jnz     short loc_1800266D4
0x1800266bb  call    cs:__imp_GetLastError
0x1800266c1  test    eax, eax
0x1800266c3  jle     short loc_1800266CD
0x1800266c5  movzx   eax, ax
0x1800266c8  or      eax, 80070000h
0x1800266cd  mov     edi, eax
0x1800266cf  jmp     loc_1800267C3
0x1800266d4  mov     rbx, [rbp+Sid]
0x1800266d8  xor     edx, edx; Flags
0x1800266da  lea     rcx, AliasPrefix; "SmsRouter"
0x1800266e1  call    cs:__imp_CreateBoundaryDescriptorW
0x1800266e7  mov     [rbp+BoundaryDescriptor], rax
0x1800266eb  test    rax, rax
0x1800266ee  jnz     short loc_18002670E
0x1800266f0  call    cs:__imp_GetLastError
0x1800266f6  mov     edi, eax
0x1800266f8  test    eax, eax
0x1800266fa  jle     loc_1800267B4
0x180026700  movzx   edi, ax
0x180026703  or      edi, 80070000h
0x180026709  jmp     loc_1800267B4
0x18002670e  mov     rdx, [rbp+Sid]; RequiredSid
0x180026712  lea     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x180026716  call    cs:__imp_AddSIDToBoundaryDescriptor
0x18002671c  test    eax, eax
0x18002671e  jnz     short loc_180026741
0x180026720  call    cs:__imp_GetLastError
0x180026726  mov     edi, eax
0x180026728  test    eax, eax
0x18002672a  jle     short loc_180026735
0x18002672c  movzx   edi, ax
0x18002672f  or      edi, 80070000h
0x180026735  mov     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x180026739  call    cs:__imp_DeleteBoundaryDescriptor
0x18002673f  jmp     short loc_1800267B4
0x180026741  lea     r8, AliasPrefix; "SmsRouter"
0x180026748  mov     rdx, [rbp+BoundaryDescriptor]; lpBoundaryDescriptor
0x18002674c  xor     ecx, ecx; lpPrivateNamespaceAttributes
0x18002674e  call    cs:__imp_CreatePrivateNamespaceW
0x180026754  mov     rsi, rax
0x180026757  test    rax, rax
0x18002675a  jnz     short loc_1800267A7
0x18002675c  call    cs:__imp_GetLastError
0x180026762  mov     edi, eax
0x180026764  test    eax, eax
0x180026766  jle     short loc_180026771
0x180026768  movzx   edi, ax
0x18002676b  or      edi, 80070000h
0x180026771  cmp     edi, 800700B7h
0x180026777  jz      short loc_1800267A7
0x180026779  lea     rdx, AliasPrefix; "SmsRouter"
0x180026780  mov     rcx, [rbp+BoundaryDescriptor]; lpBoundaryDescriptor
0x180026784  call    cs:__imp_OpenPrivateNamespaceW
0x18002678a  mov     rsi, rax
0x18002678d  test    rax, rax
0x180026790  jnz     short loc_1800267A7
0x180026792  call    cs:__imp_GetLastError
0x180026798  mov     edi, eax
0x18002679a  test    eax, eax
0x18002679c  jle     short loc_1800267A7
0x18002679e  movzx   edi, ax
0x1800267a1  or      edi, 80070000h
0x1800267a7  mov     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x1800267ab  call    cs:__imp_DeleteBoundaryDescriptor
0x1800267b1  mov     [r14], rsi
0x1800267b4  test    rbx, rbx
0x1800267b7  jz      short loc_1800267C3
0x1800267b9  mov     rcx, rbx; hMem
0x1800267bc  call    cs:__imp_LocalFree
0x1800267c2  nop
0x1800267c3  lea     rcx, [rbp+StringSid]; void *
0x1800267c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800267cc  mov     eax, edi
0x1800267ce  mov     rcx, [rbp+var_8]
0x1800267d2  xor     rcx, rsp; StackCookie
0x1800267d5  call    __security_check_cookie
0x1800267da  lea     r11, [rsp+60h+var_s0]
0x1800267df  mov     rbx, [r11+28h]
0x1800267e3  mov     rsi, [r11+30h]
0x1800267e7  mov     rsp, r11
0x1800267ea  pop     r14
0x1800267ec  pop     rdi
0x1800267ed  pop     rbp
0x1800267ee  retn
```
