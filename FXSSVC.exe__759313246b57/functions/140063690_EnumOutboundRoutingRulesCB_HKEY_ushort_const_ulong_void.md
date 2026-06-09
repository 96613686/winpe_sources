# EnumOutboundRoutingRulesCB(HKEY__ *,ushort const *,ulong,void *)

- ea: `0x140063690`
- end: `0x14006395f`
- name: `?EnumOutboundRoutingRulesCB@@YAHPEAUHKEY__@@PEBGKPEAX@Z`
- size: `719`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140001bac`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x140063080`
- `0x140063690`
- `0x140063968`
- `0x140063e08`
- `0x140064288`
- `0x140074f18`
- `0x14007566c`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140063834`
- `ADVAPI32!RegCloseKey` at `0x140063834`
- `ADVAPI32!RegDeleteKeyW` at `0x1400637df`
- `ADVAPI32!RegDeleteKeyW` at `0x1400637df`
- `KERNEL32!GetLastError` at `0x140063788`
- `KERNEL32!GetLastError` at `0x140063788`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnumOutboundRoutingRulesCB(HKEY hKey, WCHAR *a2, __int64 a3, _DWORD *a4)
{
  unsigned int LastError; // esi
  int v8; // r15d
  HKEY v9; // rax
  HKEY v10; // r14
  LSTATUS v11; // eax
  __int64 v12; // rdx
  unsigned int Status; // eax
  unsigned int v14; // eax
  int v16; // [rsp+30h] [rbp-40h] BYREF
  void *Block[3]; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int64 v18; // [rsp+50h] [rbp-20h]
  int v19; // [rsp+60h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids);
  }
  v18 = 7;
  Block[2] = 0;
  LOWORD(Block[0]) = 0;
  if ( a2 )
  {
    LastError = COutboundRoutingRule::Load((BYTE *)Block, hKey);
    if ( LastError )
    {
      v8 = 0;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids,
          (_DWORD)a2,
          LastError);
      }
      v9 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Outbound Routing\\Rules", 0, 0x3001Fu);
      v10 = v9;
      if ( v9 )
      {
        v11 = RegDeleteKeyW(v9, a2);
        if ( v11 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              83,
              (unsigned int)WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids,
              (_DWORD)a2,
              v11);
          }
        }
        else
        {
          v8 = 1;
        }
        RegCloseKey(v10);
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, LastError);
        }
      }
      if ( !LastError )
        goto LABEL_43;
      if ( v8 )
      {
        v12 = 3221257541LL;
LABEL_42:
        FaxLogOutboundRule(a2, v12);
LABEL_43:
        *a4 = 0;
        if ( v18 >= 8 )
          operator delete(Block[0]);
        return 1;
      }
    }
    else
    {
      if ( v19 && !(unsigned int)IsServerSku() )
        goto LABEL_43;
      v16 = 0;
      Status = COutboundRoutingRule::GetStatus((COutboundRoutingRule *)Block, (enum FAX_ENUM_RULE_STATUS *)&v16);
      if ( Status )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids, Status);
        }
      }
      else if ( v16 && v16 != 3 )
      {
        FaxLogOutboundRule(a2, 2147515716LL);
      }
      v14 = COutboundRulesMap::AddRule(g_pRulesMap, (struct COutboundRoutingRule *)Block);
      if ( !v14 )
        goto LABEL_43;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids,
          (_DWORD)a2,
          v14);
      }
    }
    v12 = 3221257543LL;
    goto LABEL_42;
  }
  return 1;
}

```

## disassembly

```asm
0x140063690  push    rbp
0x140063692  push    rbx
0x140063693  push    rsi
0x140063694  push    rdi
0x140063695  push    r12
0x140063697  push    r14
0x140063699  push    r15
0x14006369b  mov     rbp, rsp
0x14006369e  sub     rsp, 70h
0x1400636a2  mov     rax, cs:__security_cookie
0x1400636a9  xor     rax, rsp
0x1400636ac  mov     [rbp+var_8], rax
0x1400636b0  mov     r12, r9
0x1400636b3  mov     rdi, rdx
0x1400636b6  mov     rbx, rcx
0x1400636b9  lea     r15, WPP_GLOBAL_Control
0x1400636c0  mov     r14b, 4
0x1400636c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400636ca  cmp     rcx, r15
0x1400636cd  jz      short loc_1400636F0
0x1400636cf  test    [rcx+1Ch], r14b
0x1400636d3  jz      short loc_1400636F0
0x1400636d5  cmp     byte ptr [rcx+19h], 5
0x1400636d9  jb      short loc_1400636F0
0x1400636db  mov     edx, 50h ; 'P'
0x1400636e0  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x1400636e7  mov     rcx, [rcx+10h]
0x1400636eb  call    WPP_SF_
0x1400636f0  mov     [rbp+var_20], 7
0x1400636f8  mov     [rbp+var_28], 0
0x140063700  xor     eax, eax
0x140063702  mov     word ptr [rbp+Block], ax
0x140063706  test    rdi, rdi
0x140063709  jnz     short loc_140063710
0x14006370b  jmp     loc_14006393E
0x140063710  mov     rdx, rbx; hKey
0x140063713  lea     rcx, [rbp+Block]; this
0x140063717  call    ?Load@COutboundRoutingRule@@QEAAKPEAUHKEY__@@@Z; COutboundRoutingRule::Load(HKEY__ *)
0x14006371c  mov     esi, eax
0x14006371e  test    eax, eax
0x140063720  jz      loc_14006385B
0x140063726  xor     r15d, r15d
0x140063729  mov     bl, 2
0x14006372b  mov     rcx, cs:WPP_GLOBAL_Control
0x140063732  lea     rax, WPP_GLOBAL_Control
0x140063739  cmp     rcx, rax
0x14006373c  jz      short loc_140063764
0x14006373e  test    [rcx+1Ch], r14b
0x140063742  jz      short loc_140063764
0x140063744  cmp     [rcx+19h], bl
0x140063747  jb      short loc_140063764
0x140063749  lea     edx, [r15+51h]
0x14006374d  mov     [rsp+70h+var_50], esi
0x140063751  mov     r9, rdi
0x140063754  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x14006375b  mov     rcx, [rcx+10h]
0x14006375f  call    WPP_SF_Sd
0x140063764  mov     r9d, 3001Fh
0x14006376a  xor     r8d, r8d
0x14006376d  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Fax\\Outbound Rout"...
0x140063774  mov     rcx, 0FFFFFFFF80000002h
0x14006377b  call    OpenRegistryKey
0x140063780  mov     r14, rax
0x140063783  test    rax, rax
0x140063786  jnz     short loc_1400637D9
0x140063788  call    cs:__imp_GetLastError
0x14006378f  nop     dword ptr [rax+rax+00h]
0x140063794  mov     esi, eax
0x140063796  mov     rcx, cs:WPP_GLOBAL_Control
0x14006379d  lea     rax, WPP_GLOBAL_Control
0x1400637a4  cmp     rcx, rax
0x1400637a7  jz      loc_140063840
0x1400637ad  test    byte ptr [rcx+1Ch], 4
0x1400637b1  jz      loc_140063840
0x1400637b7  cmp     [rcx+19h], bl
0x1400637ba  jb      loc_140063840
0x1400637c0  lea     edx, [r14+52h]
0x1400637c4  mov     r9d, esi
0x1400637c7  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x1400637ce  mov     rcx, [rcx+10h]
0x1400637d2  call    WPP_SF_d
0x1400637d7  jmp     short loc_140063840
0x1400637d9  mov     rdx, rdi; lpSubKey
0x1400637dc  mov     rcx, r14; hKey
0x1400637df  call    cs:__imp_RegDeleteKeyW
0x1400637e6  nop     dword ptr [rax+rax+00h]
0x1400637eb  test    eax, eax
0x1400637ed  jz      short loc_14006382B
0x1400637ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400637f6  lea     rdx, WPP_GLOBAL_Control
0x1400637fd  cmp     rcx, rdx
0x140063800  jz      short loc_140063831
0x140063802  test    byte ptr [rcx+1Ch], 4
0x140063806  jz      short loc_140063831
0x140063808  cmp     [rcx+19h], bl
0x14006380b  jb      short loc_140063831
0x14006380d  mov     edx, 53h ; 'S'
0x140063812  mov     [rsp+70h+var_50], eax
0x140063816  mov     r9, rdi
0x140063819  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x140063820  mov     rcx, [rcx+10h]
0x140063824  call    WPP_SF_Sd
0x140063829  jmp     short loc_140063831
0x14006382b  mov     r15d, 1
0x140063831  mov     rcx, r14; hKey
0x140063834  call    cs:__imp_RegCloseKey
0x14006383b  nop     dword ptr [rax+rax+00h]
0x140063840  test    esi, esi
0x140063842  jz      loc_140063926
0x140063848  test    r15d, r15d
0x14006384b  jz      loc_140063919
0x140063851  mov     edx, 0C0007D45h
0x140063856  jmp     loc_14006391E
0x14006385b  cmp     [rbp+var_10], 0
0x14006385f  jz      short loc_14006386E
0x140063861  call    IsServerSku
0x140063866  test    eax, eax
0x140063868  jz      loc_140063926
0x14006386e  mov     [rbp+var_40], 0
0x140063875  lea     rdx, [rbp+var_40]; enum FAX_ENUM_RULE_STATUS *
0x140063879  lea     rcx, [rbp+Block]; this
0x14006387d  call    ?GetStatus@COutboundRoutingRule@@QEBAKPEAW4FAX_ENUM_RULE_STATUS@@@Z; COutboundRoutingRule::GetStatus(FAX_ENUM_RULE_STATUS *)
0x140063882  mov     bl, 2
0x140063884  test    eax, eax
0x140063886  jnz     short loc_1400638A3
0x140063888  mov     eax, [rbp+var_40]
0x14006388b  test    eax, eax
0x14006388d  jz      short loc_1400638D2
0x14006388f  cmp     eax, 3
0x140063892  jz      short loc_1400638D2
0x140063894  mov     edx, 80007D44h; unsigned __int64
0x140063899  mov     rcx, rdi; unsigned __int16 *
0x14006389c  call    ?FaxLogOutboundRule@@YAXPEBG_K@Z; FaxLogOutboundRule(ushort const *,unsigned __int64)
0x1400638a1  jmp     short loc_1400638D2
0x1400638a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400638aa  cmp     rcx, r15
0x1400638ad  jz      short loc_1400638D2
0x1400638af  test    [rcx+1Ch], r14b
0x1400638b3  jz      short loc_1400638D2
0x1400638b5  cmp     [rcx+19h], bl
0x1400638b8  jb      short loc_1400638D2
0x1400638ba  mov     edx, 54h ; 'T'
0x1400638bf  mov     r9d, eax
0x1400638c2  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x1400638c9  mov     rcx, [rcx+10h]
0x1400638cd  call    WPP_SF_d
0x1400638d2  lea     rdx, [rbp+Block]; struct COutboundRoutingRule *
0x1400638d6  mov     rcx, cs:?g_pRulesMap@@3PEAVCOutboundRulesMap@@EA; this
0x1400638dd  call    ?AddRule@COutboundRulesMap@@QEAAKAEAVCOutboundRoutingRule@@@Z; COutboundRulesMap::AddRule(COutboundRoutingRule &)
0x1400638e2  test    eax, eax
0x1400638e4  jz      short loc_140063926
0x1400638e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400638ed  cmp     rcx, r15
0x1400638f0  jz      short loc_140063919
0x1400638f2  test    [rcx+1Ch], r14b
0x1400638f6  jz      short loc_140063919
0x1400638f8  cmp     [rcx+19h], bl
0x1400638fb  jb      short loc_140063919
0x1400638fd  mov     edx, 55h ; 'U'
0x140063902  mov     [rsp+70h+var_50], eax
0x140063906  mov     r9, rdi
0x140063909  lea     r8, WPP_7832b6fd1af0352d8a430ec1cefaf76b_Traceguids
0x140063910  mov     rcx, [rcx+10h]
0x140063914  call    WPP_SF_Sd
0x140063919  mov     edx, 0C0007D47h; unsigned __int64
0x14006391e  mov     rcx, rdi; unsigned __int16 *
0x140063921  call    ?FaxLogOutboundRule@@YAXPEBG_K@Z; FaxLogOutboundRule(ushort const *,unsigned __int64)
0x140063926  mov     dword ptr [r12], 0
0x14006392e  cmp     [rbp+var_20], 8
0x140063933  jb      short loc_14006393E
0x140063935  mov     rcx, [rbp+Block]; Block
0x140063939  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006393e  mov     eax, 1
0x140063943  mov     rcx, [rbp+var_8]
0x140063947  xor     rcx, rsp; StackCookie
0x14006394a  call    __security_check_cookie
0x14006394f  add     rsp, 70h
0x140063953  pop     r15
0x140063955  pop     r14
0x140063957  pop     r12
0x140063959  pop     rdi
0x14006395a  pop     rsi
0x14006395b  pop     rbx
0x14006395c  pop     rbp
0x14006395d  retn
```
