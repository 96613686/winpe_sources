# CDriverVerifierPlugin::EnableDriverVerifier(void *)

- ea: `0x14005188c`
- end: `0x140051ac7`
- name: `?EnableDriverVerifier@CDriverVerifierPlugin@@AEAAJPEAX@Z`
- size: `571`
- prototype: `__int64 __fastcall(CDriverVerifierPlugin *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140051b80`

## callees

- `0x140002470`
- `0x14001444c`
- `0x140014474`
- `0x140014678`
- `0x14005188c`
- `0x140052238`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x140051979`
- `ntdll!NtSetSystemInformation` at `0x1400519d0`
- `ntdll!NtSetSystemInformation` at `0x140051a3c`
- `ntdll!NtSetSystemInformation` at `0x140051979`
- `ntdll!NtSetSystemInformation` at `0x1400519d0`
- `ntdll!NtSetSystemInformation` at `0x140051a3c`
- `ntdll!RtlAdjustPrivilege` at `0x140051914`
- `ntdll!RtlAdjustPrivilege` at `0x140051a9c`
- `ntdll!RtlAdjustPrivilege` at `0x140051914`
- `ntdll!RtlAdjustPrivilege` at `0x140051a9c`
- `ntdll!RtlInitUnicodeString` at `0x140051a28`
- `ntdll!RtlInitUnicodeString` at `0x140051a28`

## pseudocode

```c
__int64 __fastcall CDriverVerifierPlugin::EnableDriverVerifier(const WCHAR ***this, void *a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // ebx
  unsigned int v5; // ebx
  CUserModeHangReport *v6; // rcx
  __int64 v7; // rdx
  const WCHAR **v8; // rbx
  const WCHAR **v9; // rdi
  const WCHAR *v10; // rdx
  NTSTATUS v11; // eax
  unsigned __int8 OldValue[8]; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-48h] BYREF
  _OWORD SystemInformation[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v16; // [rsp+68h] [rbp-18h]

  OldValue[0] = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  v16 = 0;
  if ( !(unsigned int)CDriverVerifierPlugin::PromptForEnableDriverVerifier((CDriverVerifierPlugin *)this, a2) )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids);
    }
    v3 = -2147467259;
    goto LABEL_30;
  }
  v4 = RtlAdjustPrivilege(0x14u, 1u, 0, OldValue);
  if ( (v4 & 0xC0000000) != 0xC0000000 )
  {
    LODWORD(SystemInformation[0]) = 1;
    v5 = NtSetSystemInformation(SystemVerifierInformationEx, SystemInformation, 0x28u);
    if ( (v5 & 0xC0000000) == 0xC0000000 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_16;
      }
      v7 = 29;
    }
    else
    {
      v5 = NtSetSystemInformation(SystemVerifierInformation, this + 5, 4u);
      if ( (v5 & 0xC0000000) != 0xC0000000 )
      {
        v8 = this[2];
        v9 = this[3];
        while ( v8 != v9 )
        {
          v10 = *v8;
          DestinationString = 0;
          if ( v10 != v8[1] )
          {
            RtlInitUnicodeString(&DestinationString, v10);
            v11 = NtSetSystemInformation(SystemPlugPlayBusInformation, &DestinationString, 0x10u);
            if ( (v11 & 0xC0000000) == 0xC0000000
              && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                (unsigned int)WPP_9294ba3b0f9d339286b8307f84055942_Traceguids,
                (unsigned int)*v8,
                v11);
            }
          }
          v8 += 4;
        }
        *((_DWORD *)this + 11) = 1;
        v3 = 0;
        goto LABEL_30;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_16;
      }
      v7 = 30;
    }
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids, v5);
LABEL_16:
    v3 = v5 | 0x10000000;
LABEL_30:
    if ( OldValue[0] )
      RtlAdjustPrivilege(0x14u, 0, 0, OldValue);
    return v3;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids, v4);
  }
  return v4 | 0x10000000;
}

```

## disassembly

```asm
0x14005188c  mov     [rsp-28h+arg_10], rbx
0x140051891  push    rbp
0x140051892  push    rsi
0x140051893  push    rdi
0x140051894  push    r12
0x140051896  push    r14
0x140051898  mov     rbp, rsp
0x14005189b  sub     rsp, 80h
0x1400518a2  mov     rax, cs:__security_cookie
0x1400518a9  xor     rax, rsp
0x1400518ac  mov     [rbp+var_10], rax
0x1400518b0  xorps   xmm0, xmm0
0x1400518b3  mov     [rbp+OldValue], 0
0x1400518b7  xor     eax, eax
0x1400518b9  mov     r14, rcx
0x1400518bc  movups  [rbp+SystemInformation], xmm0
0x1400518c0  mov     [rbp+var_18], rax
0x1400518c4  movups  [rbp+var_28], xmm0
0x1400518c8  call    ?PromptForEnableDriverVerifier@CDriverVerifierPlugin@@AEAAHPEAX@Z; CDriverVerifierPlugin::PromptForEnableDriverVerifier(void *)
0x1400518cd  test    eax, eax
0x1400518cf  jnz     short loc_140051907
0x1400518d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400518d8  lea     rsi, WPP_GLOBAL_Control
0x1400518df  cmp     rcx, rsi
0x1400518e2  jz      short loc_1400518FD
0x1400518e4  test    byte ptr [rcx+1Ch], 4
0x1400518e8  jz      short loc_1400518FD
0x1400518ea  mov     rcx, [rcx+10h]
0x1400518ee  lea     edx, [rax+1Bh]
0x1400518f1  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x1400518f8  call    WPP_SF_
0x1400518fd  mov     ebx, 80004005h
0x140051902  jmp     loc_140051A8A
0x140051907  xor     r8d, r8d; ForThread
0x14005190a  lea     r9, [rbp+OldValue]; OldValue
0x14005190e  mov     dl, 1; NewValue
0x140051910  lea     ecx, [r8+14h]; Privilege
0x140051914  call    cs:__imp_RtlAdjustPrivilege
0x14005191a  mov     r12d, 0C0000000h
0x140051920  mov     ebx, eax
0x140051922  and     eax, r12d
0x140051925  cmp     eax, r12d
0x140051928  jnz     short loc_140051964
0x14005192a  mov     rcx, cs:WPP_GLOBAL_Control
0x140051931  lea     rsi, WPP_GLOBAL_Control
0x140051938  cmp     rcx, rsi
0x14005193b  jz      short loc_14005195B
0x14005193d  test    byte ptr [rcx+1Ch], 1
0x140051941  jz      short loc_14005195B
0x140051943  mov     rcx, [rcx+10h]
0x140051947  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x14005194e  mov     edx, 1Ch
0x140051953  mov     r9d, ebx
0x140051956  call    WPP_SF_d
0x14005195b  bts     ebx, 1Ch
0x14005195f  jmp     loc_140051AA2
0x140051964  mov     r8d, 28h ; '('; SystemInformationLength
0x14005196a  mov     dword ptr [rbp+SystemInformation], 1
0x140051971  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x140051975  lea     ecx, [r8+34h]; SystemInformationClass
0x140051979  call    cs:__imp_NtSetSystemInformation
0x14005197f  mov     ebx, eax
0x140051981  and     eax, r12d
0x140051984  cmp     eax, r12d
0x140051987  jnz     short loc_1400519C3
0x140051989  mov     rcx, cs:WPP_GLOBAL_Control
0x140051990  lea     rsi, WPP_GLOBAL_Control
0x140051997  cmp     rcx, rsi
0x14005199a  jz      short loc_1400519BA
0x14005199c  test    byte ptr [rcx+1Ch], 1
0x1400519a0  jz      short loc_1400519BA
0x1400519a2  mov     edx, 1Dh
0x1400519a7  mov     rcx, [rcx+10h]
0x1400519ab  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x1400519b2  mov     r9d, ebx
0x1400519b5  call    WPP_SF_d
0x1400519ba  bts     ebx, 1Ch
0x1400519be  jmp     loc_140051A8A
0x1400519c3  mov     ecx, 33h ; '3'; SystemInformationClass
0x1400519c8  lea     rdx, [r14+28h]; SystemInformation
0x1400519cc  lea     r8d, [rcx-2Fh]; SystemInformationLength
0x1400519d0  call    cs:__imp_NtSetSystemInformation
0x1400519d6  mov     ebx, eax
0x1400519d8  and     eax, r12d
0x1400519db  cmp     eax, r12d
0x1400519de  jnz     short loc_140051A00
0x1400519e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400519e7  lea     rsi, WPP_GLOBAL_Control
0x1400519ee  cmp     rcx, rsi
0x1400519f1  jz      short loc_1400519BA
0x1400519f3  test    byte ptr [rcx+1Ch], 1
0x1400519f7  jz      short loc_1400519BA
0x1400519f9  mov     edx, 1Eh
0x1400519fe  jmp     short loc_1400519A7
0x140051a00  mov     rbx, [r14+10h]
0x140051a04  lea     rsi, WPP_GLOBAL_Control
0x140051a0b  mov     rdi, [r14+18h]
0x140051a0f  cmp     rbx, rdi
0x140051a12  jz      short loc_140051A80
0x140051a14  mov     rdx, [rbx]; SourceString
0x140051a17  xorps   xmm0, xmm0
0x140051a1a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140051a1e  cmp     rdx, [rbx+8]
0x140051a22  jz      short loc_140051A7A
0x140051a24  lea     rcx, [rbp+DestinationString]; DestinationString
0x140051a28  call    cs:__imp_RtlInitUnicodeString
0x140051a2e  mov     r8d, 10h; SystemInformationLength
0x140051a34  lea     rdx, [rbp+DestinationString]; SystemInformation
0x140051a38  lea     ecx, [r8+18h]; SystemInformationClass
0x140051a3c  call    cs:__imp_NtSetSystemInformation
0x140051a42  mov     ecx, eax
0x140051a44  and     ecx, r12d
0x140051a47  cmp     ecx, r12d
0x140051a4a  jnz     short loc_140051A7A
0x140051a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140051a53  cmp     rcx, rsi
0x140051a56  jz      short loc_140051A7A
0x140051a58  test    byte ptr [rcx+1Ch], 1
0x140051a5c  jz      short loc_140051A7A
0x140051a5e  mov     r9, [rbx]
0x140051a61  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x140051a68  mov     rcx, [rcx+10h]
0x140051a6c  mov     edx, 1Fh
0x140051a71  mov     [rsp+80h+var_60], eax
0x140051a75  call    WPP_SF_Sd
0x140051a7a  add     rbx, 20h ; ' '
0x140051a7e  jmp     short loc_140051A0F
0x140051a80  mov     dword ptr [r14+2Ch], 1
0x140051a88  xor     ebx, ebx
0x140051a8a  cmp     [rbp+OldValue], 0
0x140051a8e  jz      short loc_140051AA2
0x140051a90  xor     edx, edx; NewValue
0x140051a92  lea     r9, [rbp+OldValue]; OldValue
0x140051a96  xor     r8d, r8d; ForThread
0x140051a99  lea     ecx, [rdx+14h]; Privilege
0x140051a9c  call    cs:__imp_RtlAdjustPrivilege
0x140051aa2  mov     eax, ebx
0x140051aa4  mov     rcx, [rbp+var_10]
0x140051aa8  xor     rcx, rsp; StackCookie
0x140051aab  call    __security_check_cookie
0x140051ab0  mov     rbx, [rsp+80h+arg_10]
0x140051ab8  add     rsp, 80h
0x140051abf  pop     r14
0x140051ac1  pop     r12
0x140051ac3  pop     rdi
0x140051ac4  pop     rsi
0x140051ac5  pop     rbp
0x140051ac6  retn
```
