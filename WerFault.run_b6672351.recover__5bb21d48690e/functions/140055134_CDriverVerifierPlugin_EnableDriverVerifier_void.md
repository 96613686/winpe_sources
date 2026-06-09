# CDriverVerifierPlugin::EnableDriverVerifier(void *)

- ea: `0x140055134`
- end: `0x140055394`
- name: `?EnableDriverVerifier@CDriverVerifierPlugin@@AEAAJPEAX@Z`
- size: `608`
- prototype: `__int64 __fastcall(CDriverVerifierPlugin *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140055450`

## callees

- `0x140002490`
- `0x140014ee4`
- `0x140014f14`
- `0x140015138`
- `0x140055134`
- `0x140055b1c`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x140055227`
- `ntdll!NtSetSystemInformation` at `0x140055284`
- `ntdll!NtSetSystemInformation` at `0x1400552fc`
- `ntdll!NtSetSystemInformation` at `0x140055227`
- `ntdll!NtSetSystemInformation` at `0x140055284`
- `ntdll!NtSetSystemInformation` at `0x1400552fc`
- `ntdll!RtlAdjustPrivilege` at `0x1400551bc`
- `ntdll!RtlAdjustPrivilege` at `0x140055362`
- `ntdll!RtlAdjustPrivilege` at `0x1400551bc`
- `ntdll!RtlAdjustPrivilege` at `0x140055362`
- `ntdll!RtlInitUnicodeString` at `0x1400552e2`
- `ntdll!RtlInitUnicodeString` at `0x1400552e2`

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
0x140055134  mov     [rsp-28h+arg_10], rbx
0x140055139  push    rbp
0x14005513a  push    rsi
0x14005513b  push    rdi
0x14005513c  push    r12
0x14005513e  push    r14
0x140055140  mov     rbp, rsp
0x140055143  sub     rsp, 80h
0x14005514a  mov     rax, cs:__security_cookie
0x140055151  xor     rax, rsp
0x140055154  mov     [rbp+var_10], rax
0x140055158  xorps   xmm0, xmm0
0x14005515b  mov     [rbp+OldValue], 0
0x14005515f  xor     eax, eax
0x140055161  mov     r14, rcx
0x140055164  movups  [rbp+SystemInformation], xmm0
0x140055168  mov     [rbp+var_18], rax
0x14005516c  movups  [rbp+var_28], xmm0
0x140055170  call    ?PromptForEnableDriverVerifier@CDriverVerifierPlugin@@AEAAHPEAX@Z; CDriverVerifierPlugin::PromptForEnableDriverVerifier(void *)
0x140055175  test    eax, eax
0x140055177  jnz     short loc_1400551AF
0x140055179  mov     rcx, cs:WPP_GLOBAL_Control
0x140055180  lea     rsi, WPP_GLOBAL_Control
0x140055187  cmp     rcx, rsi
0x14005518a  jz      short loc_1400551A5
0x14005518c  test    byte ptr [rcx+1Ch], 4
0x140055190  jz      short loc_1400551A5
0x140055192  mov     rcx, [rcx+10h]
0x140055196  lea     edx, [rax+1Bh]
0x140055199  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x1400551a0  call    WPP_SF_
0x1400551a5  mov     ebx, 80004005h
0x1400551aa  jmp     loc_140055350
0x1400551af  xor     r8d, r8d; ForThread
0x1400551b2  lea     r9, [rbp+OldValue]; OldValue
0x1400551b6  mov     dl, 1; NewValue
0x1400551b8  lea     ecx, [r8+14h]; Privilege
0x1400551bc  call    cs:__imp_RtlAdjustPrivilege
0x1400551c3  nop     dword ptr [rax+rax+00h]
0x1400551c8  mov     r12d, 0C0000000h
0x1400551ce  mov     ebx, eax
0x1400551d0  and     eax, r12d
0x1400551d3  cmp     eax, r12d
0x1400551d6  jnz     short loc_140055212
0x1400551d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400551df  lea     rsi, WPP_GLOBAL_Control
0x1400551e6  cmp     rcx, rsi
0x1400551e9  jz      short loc_140055209
0x1400551eb  test    byte ptr [rcx+1Ch], 1
0x1400551ef  jz      short loc_140055209
0x1400551f1  mov     rcx, [rcx+10h]
0x1400551f5  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x1400551fc  mov     edx, 1Ch
0x140055201  mov     r9d, ebx
0x140055204  call    WPP_SF_d
0x140055209  bts     ebx, 1Ch
0x14005520d  jmp     loc_14005536E
0x140055212  mov     r8d, 28h ; '('; SystemInformationLength
0x140055218  mov     dword ptr [rbp+SystemInformation], 1
0x14005521f  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x140055223  lea     ecx, [r8+34h]; SystemInformationClass
0x140055227  call    cs:__imp_NtSetSystemInformation
0x14005522e  nop     dword ptr [rax+rax+00h]
0x140055233  mov     ebx, eax
0x140055235  and     eax, r12d
0x140055238  cmp     eax, r12d
0x14005523b  jnz     short loc_140055277
0x14005523d  mov     rcx, cs:WPP_GLOBAL_Control
0x140055244  lea     rsi, WPP_GLOBAL_Control
0x14005524b  cmp     rcx, rsi
0x14005524e  jz      short loc_14005526E
0x140055250  test    byte ptr [rcx+1Ch], 1
0x140055254  jz      short loc_14005526E
0x140055256  mov     edx, 1Dh
0x14005525b  mov     rcx, [rcx+10h]
0x14005525f  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x140055266  mov     r9d, ebx
0x140055269  call    WPP_SF_d
0x14005526e  bts     ebx, 1Ch
0x140055272  jmp     loc_140055350
0x140055277  mov     ecx, 33h ; '3'; SystemInformationClass
0x14005527c  lea     rdx, [r14+28h]; SystemInformation
0x140055280  lea     r8d, [rcx-2Fh]; SystemInformationLength
0x140055284  call    cs:__imp_NtSetSystemInformation
0x14005528b  nop     dword ptr [rax+rax+00h]
0x140055290  mov     ebx, eax
0x140055292  and     eax, r12d
0x140055295  cmp     eax, r12d
0x140055298  jnz     short loc_1400552BA
0x14005529a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400552a1  lea     rsi, WPP_GLOBAL_Control
0x1400552a8  cmp     rcx, rsi
0x1400552ab  jz      short loc_14005526E
0x1400552ad  test    byte ptr [rcx+1Ch], 1
0x1400552b1  jz      short loc_14005526E
0x1400552b3  mov     edx, 1Eh
0x1400552b8  jmp     short loc_14005525B
0x1400552ba  mov     rbx, [r14+10h]
0x1400552be  lea     rsi, WPP_GLOBAL_Control
0x1400552c5  mov     rdi, [r14+18h]
0x1400552c9  cmp     rbx, rdi
0x1400552cc  jz      short loc_140055346
0x1400552ce  mov     rdx, [rbx]; SourceString
0x1400552d1  xorps   xmm0, xmm0
0x1400552d4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400552d8  cmp     rdx, [rbx+8]
0x1400552dc  jz      short loc_140055340
0x1400552de  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400552e2  call    cs:__imp_RtlInitUnicodeString
0x1400552e9  nop     dword ptr [rax+rax+00h]
0x1400552ee  mov     r8d, 10h; SystemInformationLength
0x1400552f4  lea     rdx, [rbp+DestinationString]; SystemInformation
0x1400552f8  lea     ecx, [r8+18h]; SystemInformationClass
0x1400552fc  call    cs:__imp_NtSetSystemInformation
0x140055303  nop     dword ptr [rax+rax+00h]
0x140055308  mov     ecx, eax
0x14005530a  and     ecx, r12d
0x14005530d  cmp     ecx, r12d
0x140055310  jnz     short loc_140055340
0x140055312  mov     rcx, cs:WPP_GLOBAL_Control
0x140055319  cmp     rcx, rsi
0x14005531c  jz      short loc_140055340
0x14005531e  test    byte ptr [rcx+1Ch], 1
0x140055322  jz      short loc_140055340
0x140055324  mov     r9, [rbx]
0x140055327  lea     r8, WPP_9294ba3b0f9d339286b8307f84055942_Traceguids
0x14005532e  mov     rcx, [rcx+10h]
0x140055332  mov     edx, 1Fh
0x140055337  mov     [rsp+80h+var_60], eax
0x14005533b  call    WPP_SF_Sd
0x140055340  add     rbx, 20h ; ' '
0x140055344  jmp     short loc_1400552C9
0x140055346  mov     dword ptr [r14+2Ch], 1
0x14005534e  xor     ebx, ebx
0x140055350  cmp     [rbp+OldValue], 0
0x140055354  jz      short loc_14005536E
0x140055356  xor     edx, edx; NewValue
0x140055358  lea     r9, [rbp+OldValue]; OldValue
0x14005535c  xor     r8d, r8d; ForThread
0x14005535f  lea     ecx, [rdx+14h]; Privilege
0x140055362  call    cs:__imp_RtlAdjustPrivilege
0x140055369  nop     dword ptr [rax+rax+00h]
0x14005536e  mov     eax, ebx
0x140055370  mov     rcx, [rbp+var_10]
0x140055374  xor     rcx, rsp; StackCookie
0x140055377  call    __security_check_cookie
0x14005537c  mov     rbx, [rsp+80h+arg_10]
0x140055384  add     rsp, 80h
0x14005538b  pop     r14
0x14005538d  pop     r12
0x14005538f  pop     rdi
0x140055390  pop     rsi
0x140055391  pop     rbp
0x140055392  retn
```
