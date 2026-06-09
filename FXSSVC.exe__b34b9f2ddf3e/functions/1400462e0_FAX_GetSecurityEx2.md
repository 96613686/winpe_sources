# FAX_GetSecurityEx2

- ea: `0x1400462e0`
- end: `0x1400465ab`
- name: `FAX_GetSecurityEx2`
- size: `715`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x1400452ac`
- `0x1400462e0`
- `0x140065d14`
- `0x140065dbc`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x140046472`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x140046472`
- `ADVAPI32!GetPrivateObjectSecurity` at `0x1400464d5`
- `ADVAPI32!GetPrivateObjectSecurity` at `0x140046530`
- `ADVAPI32!GetPrivateObjectSecurity` at `0x1400464d5`
- `ADVAPI32!GetPrivateObjectSecurity` at `0x140046530`
- `KERNEL32!GetLastError` at `0x14004653a`
- `KERNEL32!GetLastError` at `0x14004653a`
- `KERNEL32!EnterCriticalSection` at `0x1400463ba`
- `KERNEL32!EnterCriticalSection` at `0x1400463ba`
- `KERNEL32!LeaveCriticalSection` at `0x140046575`
- `KERNEL32!LeaveCriticalSection` at `0x140046575`

## pseudocode

```c
__int64 __fastcall FAX_GetSecurityEx2(__int64 a1, SECURITY_INFORMATION a2, LPVOID *a3, DWORD *a4)
{
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx
  DWORD v10; // ecx
  unsigned int LastError; // eax
  unsigned int v12; // ebx
  CMapDeviceId *v13; // rcx
  __int64 v14; // rdx
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  void *v17; // rax
  int v18[18]; // [rsp+30h] [rbp-48h] BYREF
  DWORD DescriptorLength; // [rsp+90h] [rbp+18h] BYREF

  DescriptorLength = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  v18[0] = 0;
  if ( !a3 )
    return 87;
  if ( (a2 & 0xF) == 0 )
  {
    if ( v7 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 4) == 0 || *((_BYTE *)v7 + 25) < 2u )
      return 87;
    v8 = 73;
LABEL_11:
    WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    return 87;
  }
  if ( (a2 & 0xFFFFFFF0) != 0 )
  {
    if ( v7 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 4) == 0 || *((_BYTE *)v7 + 25) < 2u )
      return 87;
    v8 = 74;
    goto LABEL_11;
  }
  *a3 = 0;
  *a4 = 0;
  EnterCriticalSection(&g_CsSecurity);
  v10 = ((a2 & 7) != 0 ? 0x20000 : 0) | 0x1000000;
  if ( (a2 & 8) == 0 )
    v10 = (a2 & 7) != 0 ? 0x20000 : 0;
  LastError = FaxSvcAccessCheck(v10, v18, 0, 1);
  v12 = LastError;
  if ( LastError )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v14 = 75;
    goto LABEL_25;
  }
  if ( !v18[0] )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    }
    v12 = 5;
    goto LABEL_49;
  }
  if ( !IsValidSecurityDescriptor(g_pFaxSD) )
  {
    v12 = 1338;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v16 = 77;
    goto LABEL_37;
  }
  GetPrivateObjectSecurity(g_pFaxSD, a2, 0, 0, &DescriptorLength);
  v17 = (void *)pMemAlloc(DescriptorLength);
  *a3 = v17;
  if ( !v17 )
  {
    v12 = 8;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v16 = 78;
LABEL_37:
    WPP_SF_(*((_QWORD *)v15 + 2), v16, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    goto LABEL_49;
  }
  if ( !GetPrivateObjectSecurity(g_pFaxSD, a2, v17, DescriptorLength, &DescriptorLength) )
  {
    LastError = GetLastError();
    v12 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v14 = 79;
LABEL_25:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    goto LABEL_49;
  }
  *a4 = DescriptorLength;
LABEL_49:
  LeaveCriticalSection(&g_CsSecurity);
  if ( v12 )
  {
    pMemFree(*a3);
    *a3 = 0;
    *a4 = 0;
    if ( v12 == 8 || v12 == 14 )
      return 7001;
  }
  return v12;
}

```

## disassembly

```asm
0x1400462e0  mov     rax, rsp
0x1400462e3  push    rbx
0x1400462e4  push    rsi
0x1400462e5  push    rdi
0x1400462e6  push    r12
0x1400462e8  push    r13
0x1400462ea  push    r14
0x1400462ec  sub     rsp, 48h
0x1400462f0  mov     r14, r9
0x1400462f3  mov     dword ptr [rax+18h], 0
0x1400462fa  mov     rsi, r8
0x1400462fd  mov     edi, edx
0x1400462ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140046306  lea     r12, WPP_GLOBAL_Control
0x14004630d  lea     r13, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140046314  cmp     rcx, r12
0x140046317  jz      short loc_14004633D
0x140046319  test    byte ptr [rcx+1Ch], 4
0x14004631d  jz      short loc_14004633D
0x14004631f  cmp     byte ptr [rcx+19h], 5
0x140046323  jb      short loc_14004633D
0x140046325  mov     rcx, [rcx+10h]
0x140046329  mov     edx, 48h ; 'H'
0x14004632e  mov     r8, r13
0x140046331  call    WPP_SF_
0x140046336  mov     rcx, cs:WPP_GLOBAL_Control
0x14004633d  mov     [rsp+78h+var_48], 0
0x140046345  test    rsi, rsi
0x140046348  jz      short loc_140046372
0x14004634a  test    dil, 0Fh
0x14004634e  jnz     short loc_140046385
0x140046350  cmp     rcx, r12
0x140046353  jz      short loc_140046372
0x140046355  test    byte ptr [rcx+1Ch], 4
0x140046359  jz      short loc_140046372
0x14004635b  cmp     byte ptr [rcx+19h], 2
0x14004635f  jb      short loc_140046372
0x140046361  mov     edx, 49h ; 'I'
0x140046366  mov     rcx, [rcx+10h]
0x14004636a  mov     r8, r13
0x14004636d  call    WPP_SF_
0x140046372  mov     eax, 57h ; 'W'
0x140046377  add     rsp, 48h
0x14004637b  pop     r14
0x14004637d  pop     r13
0x14004637f  pop     r12
0x140046381  pop     rdi
0x140046382  pop     rsi
0x140046383  pop     rbx
0x140046384  retn
0x140046385  test    edi, 0FFFFFFF0h
0x14004638b  jz      short loc_1400463A5
0x14004638d  cmp     rcx, r12
0x140046390  jz      short loc_140046372
0x140046392  test    byte ptr [rcx+1Ch], 4
0x140046396  jz      short loc_140046372
0x140046398  cmp     byte ptr [rcx+19h], 2
0x14004639c  jb      short loc_140046372
0x14004639e  mov     edx, 4Ah ; 'J'
0x1400463a3  jmp     short loc_140046366
0x1400463a5  mov     qword ptr [rsi], 0
0x1400463ac  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400463b3  mov     dword ptr [r14], 0
0x1400463ba  call    cs:__imp_EnterCriticalSection
0x1400463c0  mov     eax, edi
0x1400463c2  mov     r9d, 1; int
0x1400463c8  and     al, 7
0x1400463ca  neg     al
0x1400463cc  sbb     edx, edx
0x1400463ce  and     edx, 20000h
0x1400463d4  mov     ecx, edx
0x1400463d6  bts     ecx, 18h
0x1400463da  test    dil, 8
0x1400463de  cmovz   ecx, edx; unsigned int
0x1400463e1  xor     r8d, r8d; unsigned int *
0x1400463e4  lea     rdx, [rsp+78h+var_48]; int *
0x1400463e9  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x1400463ee  mov     ebx, eax
0x1400463f0  test    eax, eax
0x1400463f2  jz      short loc_140046431
0x1400463f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400463fb  cmp     rcx, r12
0x1400463fe  jz      loc_14004656E
0x140046404  test    byte ptr [rcx+1Ch], 4
0x140046408  jz      loc_14004656E
0x14004640e  cmp     byte ptr [rcx+19h], 2
0x140046412  jb      loc_14004656E
0x140046418  mov     edx, 4Bh ; 'K'
0x14004641d  mov     rcx, [rcx+10h]
0x140046421  mov     r9d, eax
0x140046424  mov     r8, r13
0x140046427  call    WPP_SF_d
0x14004642c  jmp     loc_14004656E
0x140046431  cmp     [rsp+78h+var_48], 0
0x140046436  jnz     short loc_14004646B
0x140046438  mov     rcx, cs:WPP_GLOBAL_Control
0x14004643f  cmp     rcx, r12
0x140046442  jz      short loc_140046461
0x140046444  test    byte ptr [rcx+1Ch], 4
0x140046448  jz      short loc_140046461
0x14004644a  cmp     byte ptr [rcx+19h], 2
0x14004644e  jb      short loc_140046461
0x140046450  mov     rcx, [rcx+10h]
0x140046454  mov     edx, 4Ch ; 'L'
0x140046459  mov     r8, r13
0x14004645c  call    WPP_SF_
0x140046461  mov     ebx, 5
0x140046466  jmp     loc_14004656E
0x14004646b  mov     rcx, cs:?g_pFaxSD@@3PEAXEA; pSecurityDescriptor
0x140046472  call    cs:__imp_IsValidSecurityDescriptor
0x140046478  test    eax, eax
0x14004647a  jnz     short loc_1400464B9
0x14004647c  mov     ebx, 53Ah
0x140046481  mov     rcx, cs:WPP_GLOBAL_Control
0x140046488  cmp     rcx, r12
0x14004648b  jz      loc_14004656E
0x140046491  test    byte ptr [rcx+1Ch], 4
0x140046495  jz      loc_14004656E
0x14004649b  cmp     byte ptr [rcx+19h], 2
0x14004649f  jb      loc_14004656E
0x1400464a5  lea     edx, [rax+4Dh]
0x1400464a8  mov     rcx, [rcx+10h]
0x1400464ac  mov     r8, r13
0x1400464af  call    WPP_SF_
0x1400464b4  jmp     loc_14004656E
0x1400464b9  mov     rcx, cs:?g_pFaxSD@@3PEAXEA; ObjectDescriptor
0x1400464c0  lea     rax, [rsp+78h+DescriptorLength]
0x1400464c8  xor     r9d, r9d; DescriptorLength
0x1400464cb  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1400464d0  xor     r8d, r8d; ResultantDescriptor
0x1400464d3  mov     edx, edi; SecurityInformation
0x1400464d5  call    cs:__imp_GetPrivateObjectSecurity
0x1400464db  mov     ecx, [rsp+78h+DescriptorLength]; dwBytes
0x1400464e2  call    pMemAlloc
0x1400464e7  mov     [rsi], rax
0x1400464ea  test    rax, rax
0x1400464ed  jnz     short loc_14004650F
0x1400464ef  lea     ebx, [rax+8]
0x1400464f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400464f9  cmp     rcx, r12
0x1400464fc  jz      short loc_14004656E
0x1400464fe  test    byte ptr [rcx+1Ch], 4
0x140046502  jz      short loc_14004656E
0x140046504  cmp     byte ptr [rcx+19h], 2
0x140046508  jb      short loc_14004656E
0x14004650a  lea     edx, [rax+4Eh]
0x14004650d  jmp     short loc_1400464A8
0x14004650f  mov     r9d, [rsp+78h+DescriptorLength]; DescriptorLength
0x140046517  lea     rcx, [rsp+78h+DescriptorLength]
0x14004651f  mov     [rsp+78h+ReturnLength], rcx; ReturnLength
0x140046524  mov     r8, rax; ResultantDescriptor
0x140046527  mov     rcx, cs:?g_pFaxSD@@3PEAXEA; ObjectDescriptor
0x14004652e  mov     edx, edi; SecurityInformation
0x140046530  call    cs:__imp_GetPrivateObjectSecurity
0x140046536  test    eax, eax
0x140046538  jnz     short loc_140046564
0x14004653a  call    cs:__imp_GetLastError
0x140046540  mov     ebx, eax
0x140046542  mov     rcx, cs:WPP_GLOBAL_Control
0x140046549  cmp     rcx, r12
0x14004654c  jz      short loc_14004656E
0x14004654e  test    byte ptr [rcx+1Ch], 4
0x140046552  jz      short loc_14004656E
0x140046554  cmp     byte ptr [rcx+19h], 2
0x140046558  jb      short loc_14004656E
0x14004655a  mov     edx, 4Fh ; 'O'
0x14004655f  jmp     loc_14004641D
0x140046564  mov     eax, [rsp+78h+DescriptorLength]
0x14004656b  mov     [r14], eax
0x14004656e  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140046575  call    cs:__imp_LeaveCriticalSection
0x14004657b  test    ebx, ebx
0x14004657d  jz      short loc_1400465A4
0x14004657f  mov     rcx, [rsi]; lpMem
0x140046582  call    pMemFree
0x140046587  mov     qword ptr [rsi], 0
0x14004658e  mov     dword ptr [r14], 0
0x140046595  cmp     ebx, 8
0x140046598  jz      short loc_14004659F
0x14004659a  cmp     ebx, 0Eh
0x14004659d  jnz     short loc_1400465A4
0x14004659f  mov     ebx, 1B59h
0x1400465a4  mov     eax, ebx
0x1400465a6  jmp     loc_140046377
```
