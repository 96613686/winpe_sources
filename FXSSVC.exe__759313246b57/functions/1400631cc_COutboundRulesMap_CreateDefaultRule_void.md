# COutboundRulesMap::CreateDefaultRule(void)

- ea: `0x1400631cc`
- end: `0x14006358b`
- name: `?CreateDefaultRule@COutboundRulesMap@@QEAAHXZ`
- size: `959`
- prototype: `__int64 __fastcall(COutboundRulesMap *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x140049f40`

## callees

- `0x140001bac`
- `0x140004c78`
- `0x140004ca8`
- `0x14002d8d4`
- `0x14002da4c`
- `0x140063080`
- `0x1400631cc`
- `0x140063594`
- `0x140063a84`
- `0x140063e08`
- `0x140063fa8`
- `0x1400647b0`
- `0x1400699d0`
- `0x1400831c4`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14006352b`
- `ADVAPI32!RegCloseKey` at `0x14006352b`
- `KERNEL32!GetLastError` at `0x14006324e`
- `KERNEL32!GetLastError` at `0x1400632b2`
- `KERNEL32!GetLastError` at `0x14006324e`
- `KERNEL32!GetLastError` at `0x1400632b2`
- `KERNEL32!SetLastError` at `0x14006353d`
- `KERNEL32!SetLastError` at `0x14006353d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall COutboundRulesMap::CreateDefaultRule(COutboundRulesMap *this)
{
  COutboundRulesMap *v1; // r14
  unsigned int v2; // ebx
  DWORD LastError; // eax
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  HKEY v7; // r15
  DWORD v8; // eax
  DWORD v9; // esi
  unsigned int Status; // eax
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  COutboundRulesMap *v14; // rcx
  unsigned int v15; // [rsp+30h] [rbp-C8h] BYREF
  _QWORD v16[2]; // [rsp+38h] [rbp-C0h] BYREF
  void *v17[6]; // [rsp+48h] [rbp-B0h] BYREF
  void *Block[3]; // [rsp+78h] [rbp-80h] BYREF
  unsigned __int64 v19; // [rsp+90h] [rbp-68h]
  void *v20[3]; // [rsp+98h] [rbp-60h] BYREF
  unsigned __int64 v21; // [rsp+B0h] [rbp-48h]

  v1 = g_pRulesMap;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids);
  }
  v2 = 0;
  v16[0] = 0;
  v15 = 0;
  if ( COutboundRulesMap::FindRule(v1, (struct CDialingLocation *)v16) )
    return 1;
  LastError = GetLastError();
  if ( LastError != 7005 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v6 = 69;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, LastError);
    return 0;
  }
  v7 = (HKEY)OpenOutboundRuleKey(0, 0, 1);
  v16[1] = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 70;
    v5 = WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  v21 = 7;
  v20[2] = 0;
  LOWORD(v20[0]) = 0;
  v19 = 7;
  Block[2] = 0;
  LOWORD(Block[0]) = 0;
  std::wstring::assign((char *)Block, (char *)L"<All devices>");
  v17[3] = (void *)7;
  v17[2] = 0;
  LOWORD(v17[0]) = 0;
  std::wstring::assign(v17, Block, 0, 0xFFFFFFFFFFFFFFFFuLL);
  v8 = COutboundRoutingRule::Init(v20);
  v9 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, v8);
    }
    if ( v19 >= 8 )
      operator delete(Block[0]);
    goto LABEL_53;
  }
  if ( v19 >= 8 )
    operator delete(Block[0]);
  Status = COutboundRulesMap::AddRule(v1, (struct COutboundRoutingRule *)v20);
  v9 = Status;
  if ( Status )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 73;
LABEL_34:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, Status);
    }
  }
  else
  {
    v13 = COutboundRoutingRule::Save((COutboundRoutingRule *)v20, v7);
    v9 = v13;
    if ( v13 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, v13);
      }
      COutboundRulesMap::DelRule(v14, (struct CDialingLocation *)v16);
      goto LABEL_53;
    }
    Status = COutboundRoutingRule::GetStatus((COutboundRoutingRule *)v20, (enum FAX_ENUM_RULE_STATUS *)&v15);
    if ( !Status )
    {
      if ( v15 && v15 != 3 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, v15);
        }
        FaxLog(1u, 2u, 2u, 0x80007D44, (char)L"*");
      }
      goto LABEL_53;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 75;
      goto LABEL_34;
    }
  }
LABEL_53:
  RegCloseKey(v7);
  if ( v9 )
    SetLastError(v9);
  else
    v2 = 1;
  if ( v21 >= 8 )
    operator delete(v20[0]);
  return v2;
}

```

## disassembly

```asm
0x1400631cc  push    rbx
0x1400631ce  push    rsi
0x1400631cf  push    r12
0x1400631d1  push    r14
0x1400631d3  push    r15
0x1400631d5  sub     rsp, 0D0h
0x1400631dc  mov     rax, cs:__security_cookie
0x1400631e3  xor     rax, rsp
0x1400631e6  mov     [rsp+0F8h+var_30], rax
0x1400631ee  mov     r14, cs:?g_pRulesMap@@3PEAVCOutboundRulesMap@@EA; COutboundRulesMap * g_pRulesMap
0x1400631f5  lea     r12, WPP_GLOBAL_Control
0x1400631fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140063203  cmp     rcx, r12
0x140063206  jz      short loc_140063229
0x140063208  test    byte ptr [rcx+1Ch], 4
0x14006320c  jz      short loc_140063229
0x14006320e  cmp     byte ptr [rcx+19h], 5
0x140063212  jb      short loc_140063229
0x140063214  mov     edx, 44h ; 'D'
0x140063219  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x140063220  mov     rcx, [rcx+10h]
0x140063224  call    WPP_SF_
0x140063229  xor     ebx, ebx
0x14006322b  mov     [rsp+0F8h+var_C0], rbx
0x140063230  mov     [rsp+0F8h+var_C8], ebx
0x140063234  lea     rdx, [rsp+0F8h+var_C0]; struct CDialingLocation *
0x140063239  mov     rcx, r14; this
0x14006323c  call    ?FindRule@COutboundRulesMap@@QEAAPEAVCOutboundRoutingRule@@AEAVCDialingLocation@@@Z; COutboundRulesMap::FindRule(CDialingLocation &)
0x140063241  test    rax, rax
0x140063244  jz      short loc_14006324E
0x140063246  lea     eax, [rbx+1]
0x140063249  jmp     loc_14006356A
0x14006324e  call    cs:__imp_GetLastError
0x140063255  nop     dword ptr [rax+rax+00h]
0x14006325a  cmp     eax, 1B5Dh
0x14006325f  jz      short loc_140063280
0x140063261  mov     rcx, cs:WPP_GLOBAL_Control
0x140063268  cmp     rcx, r12
0x14006326b  jz      short loc_1400632DC
0x14006326d  test    byte ptr [rcx+1Ch], 4
0x140063271  jz      short loc_1400632DC
0x140063273  cmp     byte ptr [rcx+19h], 2
0x140063277  jb      short loc_1400632DC
0x140063279  mov     edx, 45h ; 'E'
0x14006327e  jmp     short loc_1400632C9
0x140063280  xor     edx, edx
0x140063282  xor     ecx, ecx
0x140063284  lea     r8d, [rdx+1]
0x140063288  call    OpenOutboundRuleKey
0x14006328d  mov     r15, rax
0x140063290  mov     [rsp+0F8h+var_B8], rax
0x140063295  test    rax, rax
0x140063298  jnz     short loc_1400632E3
0x14006329a  mov     rax, cs:WPP_GLOBAL_Control
0x1400632a1  cmp     rax, r12
0x1400632a4  jz      short loc_1400632DC
0x1400632a6  test    byte ptr [rax+1Ch], 4
0x1400632aa  jz      short loc_1400632DC
0x1400632ac  cmp     byte ptr [rax+19h], 2
0x1400632b0  jb      short loc_1400632DC
0x1400632b2  call    cs:__imp_GetLastError
0x1400632b9  nop     dword ptr [rax+rax+00h]
0x1400632be  lea     edx, [r15+46h]
0x1400632c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400632c9  mov     r9d, eax
0x1400632cc  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x1400632d3  mov     rcx, [rcx+10h]
0x1400632d7  call    WPP_SF_d
0x1400632dc  xor     eax, eax
0x1400632de  jmp     loc_14006356A
0x1400632e3  mov     esi, 7
0x1400632e8  mov     [rsp+0F8h+var_48], rsi
0x1400632f0  mov     [rsp+0F8h+var_50], rbx
0x1400632f8  mov     word ptr [rsp+0F8h+var_60], bx
0x140063300  mov     [rsp+0F8h+var_68], rsi
0x140063308  mov     [rsp+0F8h+var_70], rbx
0x140063310  mov     word ptr [rsp+0F8h+Block], bx
0x140063315  lea     rdx, aAllDevices; "<All devices>"
0x14006331c  lea     rcx, [rsp+0F8h+Block]; void *
0x140063321  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140063326  nop
0x140063327  mov     [rsp+0F8h+var_98], rsi
0x14006332c  mov     [rsp+0F8h+var_A0], rbx
0x140063331  mov     [rsp+0F8h+var_B0], bx
0x140063336  or      r9, 0FFFFFFFFFFFFFFFFh
0x14006333a  xor     r8d, r8d
0x14006333d  lea     rdx, [rsp+0F8h+Block]
0x140063342  lea     rcx, [rsp+0F8h+var_B0]; void *
0x140063347  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x14006334c  lea     r8, [rsp+0F8h+var_B0]
0x140063351  mov     rdx, [rsp+0F8h+var_C0]
0x140063356  lea     rcx, [rsp+0F8h+var_60]; void *
0x14006335e  call    ?Init@COutboundRoutingRule@@QEAAKVCDialingLocation@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; COutboundRoutingRule::Init(CDialingLocation,std::wstring)
0x140063363  mov     esi, eax
0x140063365  test    eax, eax
0x140063367  jz      short loc_1400633B5
0x140063369  mov     rcx, cs:WPP_GLOBAL_Control
0x140063370  cmp     rcx, r12
0x140063373  jz      short loc_14006339A
0x140063375  test    byte ptr [rcx+1Ch], 4
0x140063379  jz      short loc_14006339A
0x14006337b  cmp     byte ptr [rcx+19h], 2
0x14006337f  jb      short loc_14006339A
0x140063381  mov     edx, 47h ; 'G'
0x140063386  mov     r9d, eax
0x140063389  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x140063390  mov     rcx, [rcx+10h]
0x140063394  call    WPP_SF_d
0x140063399  nop
0x14006339a  cmp     [rsp+0F8h+var_68], 8
0x1400633a3  jb      short loc_1400633B0
0x1400633a5  mov     rcx, [rsp+0F8h+Block]; Block
0x1400633aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400633af  nop
0x1400633b0  jmp     loc_140063528
0x1400633b5  cmp     [rsp+0F8h+var_68], 8
0x1400633be  jb      short loc_1400633CB
0x1400633c0  mov     rcx, [rsp+0F8h+Block]; Block
0x1400633c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400633ca  nop
0x1400633cb  lea     rdx, [rsp+0F8h+var_60]; struct COutboundRoutingRule *
0x1400633d3  mov     rcx, r14; this
0x1400633d6  call    ?AddRule@COutboundRulesMap@@QEAAKAEAVCOutboundRoutingRule@@@Z; COutboundRulesMap::AddRule(COutboundRoutingRule &)
0x1400633db  mov     esi, eax
0x1400633dd  test    eax, eax
0x1400633df  jz      short loc_140063422
0x1400633e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400633e8  cmp     rcx, r12
0x1400633eb  jz      loc_140063528
0x1400633f1  test    byte ptr [rcx+1Ch], 4
0x1400633f5  jz      loc_140063528
0x1400633fb  cmp     byte ptr [rcx+19h], 2
0x1400633ff  jb      loc_140063528
0x140063405  mov     edx, 49h ; 'I'
0x14006340a  mov     r9d, eax
0x14006340d  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x140063414  mov     rcx, [rcx+10h]
0x140063418  call    WPP_SF_d
0x14006341d  jmp     loc_140063528
0x140063422  mov     rdx, r15; HKEY
0x140063425  lea     rcx, [rsp+0F8h+var_60]; this
0x14006342d  call    ?Save@COutboundRoutingRule@@QEBAKPEAUHKEY__@@@Z; COutboundRoutingRule::Save(HKEY__ *)
0x140063432  mov     esi, eax
0x140063434  test    eax, eax
0x140063436  jz      short loc_140063477
0x140063438  mov     rcx, cs:WPP_GLOBAL_Control
0x14006343f  cmp     rcx, r12
0x140063442  jz      short loc_140063468
0x140063444  test    byte ptr [rcx+1Ch], 4
0x140063448  jz      short loc_140063468
0x14006344a  cmp     byte ptr [rcx+19h], 2
0x14006344e  jb      short loc_140063468
0x140063450  mov     edx, 4Ah ; 'J'
0x140063455  mov     r9d, eax
0x140063458  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14006345f  mov     rcx, [rcx+10h]
0x140063463  call    WPP_SF_d
0x140063468  lea     rdx, [rsp+0F8h+var_C0]; struct CDialingLocation *
0x14006346d  call    ?DelRule@COutboundRulesMap@@QEAAKAEAVCDialingLocation@@@Z; COutboundRulesMap::DelRule(CDialingLocation &)
0x140063472  jmp     loc_140063528
0x140063477  lea     rdx, [rsp+0F8h+var_C8]; enum FAX_ENUM_RULE_STATUS *
0x14006347c  lea     rcx, [rsp+0F8h+var_60]; this
0x140063484  call    ?GetStatus@COutboundRoutingRule@@QEBAKPEAW4FAX_ENUM_RULE_STATUS@@@Z; COutboundRoutingRule::GetStatus(FAX_ENUM_RULE_STATUS *)
0x140063489  test    eax, eax
0x14006348b  jz      short loc_1400634B7
0x14006348d  mov     rcx, cs:WPP_GLOBAL_Control
0x140063494  cmp     rcx, r12
0x140063497  jz      loc_140063528
0x14006349d  test    byte ptr [rcx+1Ch], 4
0x1400634a1  jz      loc_140063528
0x1400634a7  cmp     byte ptr [rcx+19h], 2
0x1400634ab  jb      short loc_140063528
0x1400634ad  mov     edx, 4Bh ; 'K'
0x1400634b2  jmp     loc_14006340A
0x1400634b7  mov     r9d, [rsp+0F8h+var_C8]
0x1400634bc  test    r9d, r9d
0x1400634bf  jz      short loc_140063528
0x1400634c1  cmp     r9d, 3
0x1400634c5  jz      short loc_140063528
0x1400634c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400634ce  cmp     rcx, r12
0x1400634d1  jz      short loc_1400634F4
0x1400634d3  test    byte ptr [rcx+1Ch], 4
0x1400634d7  jz      short loc_1400634F4
0x1400634d9  cmp     byte ptr [rcx+19h], 5
0x1400634dd  jb      short loc_1400634F4
0x1400634df  mov     edx, 4Ch ; 'L'
0x1400634e4  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x1400634eb  mov     rcx, [rcx+10h]
0x1400634ef  call    WPP_SF_d
0x1400634f4  lea     rax, asc_140094F24; "*"
0x1400634fb  mov     [rsp+0F8h+var_D0], rax
0x140063500  mov     [rsp+0F8h+var_D8], rax
0x140063505  mov     edx, 2
0x14006350a  lea     ecx, [rdx-1]
0x14006350d  mov     r9d, 80007D44h
0x140063513  mov     r8d, edx
0x140063516  call    FaxLog
0x14006351b  jmp     short loc_140063528
0x14006351d  xor     ebx, ebx
0x14006351f  mov     esi, [rsp+0F8h+var_C8]
0x140063523  mov     r15, [rsp+0F8h+var_B8]
0x140063528  mov     rcx, r15; hKey
0x14006352b  call    cs:__imp_RegCloseKey
0x140063532  nop     dword ptr [rax+rax+00h]
0x140063537  test    esi, esi
0x140063539  jz      short loc_14006354B
0x14006353b  mov     ecx, esi; dwErrCode
0x14006353d  call    cs:__imp_SetLastError
0x140063544  nop     dword ptr [rax+rax+00h]
0x140063549  jmp     short loc_140063550
0x14006354b  mov     ebx, 1
0x140063550  cmp     [rsp+0F8h+var_48], 8
0x140063559  jb      short loc_140063568
0x14006355b  mov     rcx, [rsp+0F8h+var_60]; Block
0x140063563  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140063568  mov     eax, ebx
0x14006356a  mov     rcx, [rsp+0F8h+var_30]
0x140063572  xor     rcx, rsp; StackCookie
0x140063575  call    __security_check_cookie
0x14006357a  add     rsp, 0D0h
0x140063581  pop     r15
0x140063583  pop     r14
0x140063585  pop     r12
0x140063587  pop     rsi
0x140063588  pop     rbx
0x140063589  retn
```
