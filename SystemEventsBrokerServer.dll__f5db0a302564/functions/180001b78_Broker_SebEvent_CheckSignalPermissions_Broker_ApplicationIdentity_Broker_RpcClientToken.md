# Broker::SebEvent::CheckSignalPermissions(Broker::ApplicationIdentity,Broker::RpcClientToken *)

- ea: `0x180001b78`
- end: `0x180001db7`
- name: `?CheckSignalPermissions@SebEvent@Broker@@QEAA_NUApplicationIdentity@2@PEAVRpcClientToken@2@@Z`
- size: `575`
- prototype: `bool __fastcall(__int64, __int64, Broker::RpcClientToken *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800026d0`
- `0x18001b008`

## callees

- `0x180001b78`
- `0x180002e20`
- `0x18000f370`
- `0x180010c20`
- `0x18001cf50`
- `0x18001f9b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180001c05`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180001c05`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180001d7e`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180001d7e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180001d02`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180001d02`
- `RMCLIENT!RmAccessCheck` at `0x180001d2d`
- `RMCLIENT!RmAccessCheck` at `0x180001d2d`

## pseudocode

```c
bool __fastcall Broker::SebEvent::CheckSignalPermissions(__int64 a1, __int64 a2, Broker::RpcClientToken *a3)
{
  PSID *v4; // rsi
  int cchCount2; // ecx
  const WCHAR *v7; // r15
  const WCHAR *lpString2; // rax
  const WCHAR *v9; // r14
  const WCHAR *v10; // r8
  BOOL v11; // ebx
  int v12; // edx
  int v13; // r8d
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  int v16; // edx
  BOOL v17; // eax

  v4 = (PSID *)a2;
  cchCount2 = *(_DWORD *)(a1 + 48);
  v7 = (const WCHAR *)(a1 + 32);
  if ( *(_QWORD *)(a1 + 56) <= 7u )
    lpString2 = (const WCHAR *)(a1 + 32);
  else
    lpString2 = *(const WCHAR **)v7;
  v9 = (const WCHAR *)(a2 + 24);
  if ( *(_QWORD *)(a2 + 48) <= 7u )
    v10 = (const WCHAR *)(a2 + 24);
  else
    v10 = *(const WCHAR **)v9;
  v11 = 1;
  if ( CompareStringEx(&LocaleName, 1u, v10, *(_DWORD *)(a2 + 40), lpString2, cchCount2, 0, 0, 0) != 2 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( *(_QWORD *)(a1 + 56) > 7u )
        v7 = *(const WCHAR **)v7;
      if ( *((_QWORD *)v9 + 3) > 7u )
        v9 = *(const WCHAR **)v9;
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, (_DWORD)v9, (__int64)v7);
    }
    v11 = 0;
    goto LABEL_45;
  }
  v14 = *(unsigned int *)(a1 + 96);
  if ( (unsigned int)v14 <= 0x3F )
  {
    v15 = 0x820E402000000000uLL;
    if ( _bittest64((const __int64 *)&v15, v14) )
    {
      try
      {
        if ( a3 )
          Broker::RpcClientToken::AccessCheck(
            a3,
            L"O:SYG:SYD:(A;;RC;;;S-1-5-80-2995899262-2131376444-1860748247-2210972999-1941275431)(A;;RC;;;S-1-5-11)",
            0x40000000u);
      }
      catch ( ... )
      {
        v4 = (PSID *)a2;
        goto LABEL_44;
      }
      goto LABEL_45;
    }
  }
  if ( (unsigned int)(v14 - 58) <= 0xF )
  {
    v16 = 40985;
    if ( _bittest(&v16, v14 - 58) )
    {
      if ( a3 )
        Broker::RpcClientToken::AccessCheck(
          a3,
          L"O:SYG:SYD:(A;;RC;;;S-1-5-80-2636612206-2079418197-1004231589-1812192203-4197254245)",
          0x40000000u);
      goto LABEL_45;
    }
  }
  if ( (_DWORD)v14 != 20 && (_DWORD)v14 != 68 )
  {
    if ( (unsigned int)(v14 - 74) <= 1 )
    {
      if ( a3 )
        v11 = !Broker::RpcClientToken::IsAppContainer(a3);
      else
        v11 = 0;
    }
    else
    {
      if ( (_DWORD)v14 == 69 )
      {
        if ( a3 )
        {
          try
          {
            Broker::RpcClientToken::AccessCheck(
              a3,
              L"O:SYG:SYD:(A;;RC;;;S-1-5-80-4071458001-3563271761-1846288968-3700919931-3809667977)(A;;RC;;;SY)",
              0x40000000u);
          }
          catch ( ... )
          {
            v4 = (PSID *)a2;
            goto LABEL_44;
          }
        }
        goto LABEL_45;
      }
      v17 = EqualSid(*(PSID *)(a1 + 8), *v4);
      v11 = v17;
      if ( *(_DWORD *)(a1 + 96) == 40 )
      {
        if ( v17
          && (!a3 || !Broker::RpcClientToken::IsAppContainer(a3)
                  || !(unsigned int)RmAccessCheck(28, *(unsigned int *)a3)) )
        {
          goto LABEL_45;
        }
LABEL_44:
        v11 = IsWellKnownSid(*v4, WinLocalSystemSid);
        goto LABEL_45;
      }
    }
    if ( v11 )
      goto LABEL_45;
    goto LABEL_44;
  }
  try
  {
    if ( a3 )
      Broker::RpcClientToken::AccessCheck(a3, L"O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;LS)", 0x40000000u);
  }
  catch ( ... )
  {
    v4 = (PSID *)a2;
    goto LABEL_44;
  }
LABEL_45:
  Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v4);
  return v11;
}

```

## disassembly

```asm
0x180001b78  mov     [rsp+arg_18], rbx
0x180001b7d  push    rsi
0x180001b7e  push    rdi
0x180001b7f  push    r13
0x180001b81  push    r14
0x180001b83  push    r15
0x180001b85  sub     rsp, 60h
0x180001b89  mov     rax, cs:__security_cookie
0x180001b90  xor     rax, rsp
0x180001b93  mov     [rsp+88h+var_30], rax
0x180001b98  mov     rdi, r8
0x180001b9b  mov     rsi, rdx
0x180001b9e  mov     r13, rcx
0x180001ba1  mov     [rsp+88h+var_38], rdx
0x180001ba6  mov     ecx, [rcx+30h]
0x180001ba9  lea     r15, [r13+20h]
0x180001bad  cmp     qword ptr [r15+18h], 7
0x180001bb2  jbe     short loc_180001BB9
0x180001bb4  mov     rax, [r15]
0x180001bb7  jmp     short loc_180001BBC
0x180001bb9  mov     rax, r15
0x180001bbc  lea     r14, [rdx+18h]
0x180001bc0  cmp     qword ptr [r14+18h], 7
0x180001bc5  jbe     short loc_180001BCC
0x180001bc7  mov     r8, [r14]
0x180001bca  jmp     short loc_180001BCF
0x180001bcc  mov     r8, r14; lpString1
0x180001bcf  mov     [rsp+88h+lParam], 0; lParam
0x180001bd8  mov     [rsp+88h+lpReserved], 0; lpReserved
0x180001be1  mov     [rsp+88h+lpVersionInformation], 0; lpVersionInformation
0x180001bea  mov     [rsp+88h+cchCount2], ecx; cchCount2
0x180001bee  mov     [rsp+88h+lpString2], rax; lpString2
0x180001bf3  mov     r9d, [rdx+28h]; cchCount1
0x180001bf7  mov     ebx, 1
0x180001bfc  mov     edx, ebx; dwCmpFlags
0x180001bfe  lea     rcx, LocaleName; lpLocaleName
0x180001c05  call    cs:__imp_CompareStringEx
0x180001c0b  cmp     eax, 2
0x180001c0e  jz      short loc_180001C4E
0x180001c10  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c17  test    [rcx+1Ch], bl
0x180001c1a  jz      short loc_180001C47
0x180001c1c  cmp     byte ptr [rcx+19h], 2
0x180001c20  jb      short loc_180001C47
0x180001c22  cmp     qword ptr [r15+18h], 7
0x180001c27  jbe     short loc_180001C2C
0x180001c29  mov     r15, [r15]
0x180001c2c  cmp     qword ptr [r14+18h], 7
0x180001c31  jbe     short loc_180001C36
0x180001c33  mov     r14, [r14]
0x180001c36  mov     [rsp+88h+lpString2], r15
0x180001c3b  mov     r9, r14
0x180001c3e  mov     rcx, [rcx+10h]
0x180001c42  call    WPP_SF_SS
0x180001c47  xor     ebx, ebx
0x180001c49  jmp     loc_180001D86
0x180001c4e  mov     ecx, [r13+60h]
0x180001c52  cmp     ecx, 3Fh ; '?'
0x180001c55  ja      short loc_180001C88
0x180001c57  mov     rdx, 820E402000000000h
0x180001c61  bt      rdx, rcx
0x180001c65  jnb     short loc_180001C88
0x180001c67  test    rdi, rdi
0x180001c6a  jz      short loc_180001C81
0x180001c6c  mov     r8d, 40000000h; unsigned int
0x180001c72  lea     rdx, aOSygSydARcS158; "O:SYG:SYD:(A;;RC;;;S-1-5-80-2995899262-"...
0x180001c79  mov     rcx, rdi; this
0x180001c7c  call    ?AccessCheck@RpcClientToken@Broker@@QEAAXPEBGK@Z; Broker::RpcClientToken::AccessCheck(ushort const *,ulong)
0x180001c81  jmp     short loc_180001CF4
0x180001c83  jmp     loc_180001D71
0x180001c88  lea     eax, [rcx-3Ah]
0x180001c8b  cmp     eax, 0Fh
0x180001c8e  ja      short loc_180001CBB
0x180001c90  mov     edx, 0A019h
0x180001c95  bt      edx, eax
0x180001c98  jnb     short loc_180001CBB
0x180001c9a  test    rdi, rdi
0x180001c9d  jz      short loc_180001CB4
0x180001c9f  mov     r8d, 40000000h; unsigned int
0x180001ca5  lea     rdx, aOSygSydARcS158_0; "O:SYG:SYD:(A;;RC;;;S-1-5-80-2636612206-"...
0x180001cac  mov     rcx, rdi; this
0x180001caf  call    ?AccessCheck@RpcClientToken@Broker@@QEAAXPEBGK@Z; Broker::RpcClientToken::AccessCheck(ushort const *,ulong)
0x180001cb4  jmp     short loc_180001CF4
0x180001cb6  jmp     loc_180001D71
0x180001cbb  cmp     ecx, 14h
0x180001cbe  jz      loc_180001D55
0x180001cc4  cmp     ecx, 44h ; 'D'
0x180001cc7  jz      loc_180001D55
0x180001ccd  lea     eax, [rcx-4Ah]
0x180001cd0  cmp     eax, ebx
0x180001cd2  jbe     short loc_180001D39
0x180001cd4  cmp     ecx, 45h ; 'E'
0x180001cd7  jnz     short loc_180001CFB
0x180001cd9  test    rdi, rdi
0x180001cdc  jz      short loc_180001CF4
0x180001cde  mov     r8d, 40000000h; unsigned int
0x180001ce4  lea     rdx, aOSygSydARcS158_1; "O:SYG:SYD:(A;;RC;;;S-1-5-80-4071458001-"...
0x180001ceb  mov     rcx, rdi; this
0x180001cee  call    ?AccessCheck@RpcClientToken@Broker@@QEAAXPEBGK@Z; Broker::RpcClientToken::AccessCheck(ushort const *,ulong)
0x180001cf3  nop
0x180001cf4  jmp     loc_180001D86
0x180001cf9  jmp     short loc_180001D71
0x180001cfb  mov     rdx, [rsi]; pSid2
0x180001cfe  mov     rcx, [r13+8]; pSid1
0x180001d02  call    cs:__imp_EqualSid
0x180001d08  mov     ebx, eax
0x180001d0a  cmp     dword ptr [r13+60h], 28h ; '('
0x180001d0f  jnz     short loc_180001D4F
0x180001d11  test    eax, eax
0x180001d13  jz      short loc_180001D76
0x180001d15  test    rdi, rdi
0x180001d18  jz      short loc_180001D86
0x180001d1a  mov     rcx, rdi; this
0x180001d1d  call    ?IsAppContainer@RpcClientToken@Broker@@QEAA_NXZ; Broker::RpcClientToken::IsAppContainer(void)
0x180001d22  test    al, al
0x180001d24  jz      short loc_180001D86
0x180001d26  mov     edx, [rdi]
0x180001d28  mov     ecx, 1Ch
0x180001d2d  call    cs:__imp_RmAccessCheck
0x180001d33  test    eax, eax
0x180001d35  jnz     short loc_180001D76
0x180001d37  jmp     short loc_180001D86
0x180001d39  test    rdi, rdi
0x180001d3c  jz      short loc_180001D4D
0x180001d3e  mov     rcx, rdi; this
0x180001d41  call    ?IsAppContainer@RpcClientToken@Broker@@QEAA_NXZ; Broker::RpcClientToken::IsAppContainer(void)
0x180001d46  movzx   eax, al
0x180001d49  xor     ebx, eax
0x180001d4b  jmp     short loc_180001D4F
0x180001d4d  xor     ebx, ebx
0x180001d4f  test    ebx, ebx
0x180001d51  jz      short loc_180001D76
0x180001d53  jmp     short loc_180001D86
0x180001d55  test    rdi, rdi
0x180001d58  jz      short loc_180001D6F
0x180001d5a  mov     r8d, 40000000h; unsigned int
0x180001d60  lea     rdx, aOSygSydARcSyAR; "O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;LS)"
0x180001d67  mov     rcx, rdi; this
0x180001d6a  call    ?AccessCheck@RpcClientToken@Broker@@QEAAXPEBGK@Z; Broker::RpcClientToken::AccessCheck(ushort const *,ulong)
0x180001d6f  jmp     short loc_180001CF4
0x180001d71  mov     rsi, [rsp+88h+var_38]
0x180001d76  mov     edx, 16h; WellKnownSidType
0x180001d7b  mov     rcx, [rsi]; pSid
0x180001d7e  call    cs:__imp_IsWellKnownSid
0x180001d84  mov     ebx, eax
0x180001d86  test    ebx, ebx
0x180001d88  setnz   bl
0x180001d8b  mov     rcx, rsi; this
0x180001d8e  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x180001d93  mov     al, bl
0x180001d95  mov     rcx, [rsp+88h+var_30]
0x180001d9a  xor     rcx, rsp; StackCookie
0x180001d9d  call    __security_check_cookie
0x180001da2  mov     rbx, [rsp+88h+arg_18]
0x180001daa  add     rsp, 60h
0x180001dae  pop     r15
0x180001db0  pop     r14
0x180001db2  pop     r13
0x180001db4  pop     rdi
0x180001db5  pop     rsi
0x180001db6  retn
```
