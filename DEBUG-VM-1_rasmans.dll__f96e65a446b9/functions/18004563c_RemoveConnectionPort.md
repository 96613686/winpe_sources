# RemoveConnectionPort

- ea: `0x18004563c`
- end: `0x180045d4b`
- name: `RemoveConnectionPort`
- size: `1807`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002040c`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bb90`
- `0x18000bf70`
- `0x18000c00c`
- `0x180032a98`
- `0x18003ca44`
- `0x18003ee98`
- `0x18004033c`
- `0x180041828`
- `0x18004563c`
- `0x180046ec0`
- `0x180048464`
- `0x180049de4`
- `0x180049e58`
- `0x180049f18`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800457bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800457bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800457db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045c68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800457db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045c68`
- `rtutils!RouterLogEventA` at `0x180045ab3`
- `rtutils!RouterLogEventA` at `0x180045ab3`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180045981`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180045981`

## pseudocode

```c
double __fastcall RemoveConnectionPort(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v4; // bl
  struct _LIST_ENTRY *v7; // rcx
  double result; // xmm0_8
  __int64 v9; // rdx
  int v10; // edx
  __int64 v11; // rdx
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rbx
  __int64 UserData; // rax
  __int64 v16; // rax
  const char *v17; // rdx
  char *v18; // rcx
  char *v19; // rax
  void *v20; // rdx
  struct _LIST_ENTRY *v21; // rcx
  __int64 v22; // rax
  int v23; // r8d
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rdx
  struct _LIST_ENTRY *v27; // rcx
  __int64 v28; // rax
  unsigned int v29; // eax
  enum _SID_NAME_USE peUse; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchReferencedDomainName; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v34; // [rsp+90h] [rbp-70h]
  char v35[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v36; // [rsp+B0h] [rbp-50h]
  char pszDest[80]; // [rsp+C0h] [rbp-40h] BYREF
  char v38[288]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Name[264]; // [rsp+230h] [rbp+130h] BYREF

  v4 = a3;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    LOBYTE(a4) = a3;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 234, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, a4);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(v7[1].Blink) & 0x2000) != 0 && BYTE1(v7[1].Blink) >= 2u )
      {
        result = WPP_SF_(v7[1].Flink, 235, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v7[1].Blink) & 0x2000) != 0
        && BYTE1(v7[1].Blink) >= 6u )
      {
        v9 = 236;
        return WPP_SF_(v7[1].Flink, v9, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
      }
    }
    return result;
  }
  v10 = *(_DWORD *)(a2 + 68);
  if ( v10 )
  {
    v11 = (unsigned int)(v10 - 1);
    *(_DWORD *)(a2 + 68) = v11;
    v7 = WPP_GLOBAL_Control;
  }
  else
  {
    v11 = 0;
  }
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v7[1].Blink) & 0x2000) != 0
    && BYTE1(v7[1].Blink) >= 5u )
  {
    WPP_SF_qcqd(v7[1].Flink, v11, a3, *(_QWORD *)a1, v4 != 0, a2, v11);
    v7 = WPP_GLOBAL_Control;
  }
  v12 = *(_QWORD *)(a2 + 56);
  if ( v12 )
  {
    v13 = *(_DWORD *)(a1 + 1096);
    if ( v13 < *(_DWORD *)(a2 + 64) )
    {
      *(_QWORD *)(v12 + 8LL * (v13 - 1)) = 0;
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( *(_DWORD *)(a2 + 68) )
  {
    v28 = *(_QWORD *)(a1 + 1048);
    if ( v28 && *(_DWORD *)(v28 + 24) )
    {
      if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v7[1].Blink) & 0x2000) != 0
        && BYTE1(v7[1].Blink) >= 5u )
      {
        WPP_SF_sq(
          v7[1].Flink,
          244,
          (unsigned int)WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
          a1 + 8,
          *(_QWORD *)(a1 + 1048));
      }
      SignalNotifiers(*(_QWORD *)(a2 + 48), 8, 0);
      EnterCriticalSection(&g_csConnectionNotifierList);
      SignalNotifiers(pConnectionNotifierList, 8, 0);
      LeaveCriticalSection(&g_csConnectionNotifierList);
      *(_DWORD *)g_RasEvent = 0x4000;
      v29 = DwSendNotificationInternal(a2, g_RasEvent);
      if ( v29 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_89;
        }
        result = WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 245, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v29);
      }
      v7 = WPP_GLOBAL_Control;
    }
  }
  else if ( !*(_DWORD *)(a2 + 88) || *(_DWORD *)(a1 + 1072) )
  {
    SignalNotifiers(*(_QWORD *)(a2 + 48), 2, 0);
    EnterCriticalSection(&g_csConnectionNotifierList);
    SignalNotifiers(pConnectionNotifierList, 2, 0);
    LeaveCriticalSection(&g_csConnectionNotifierList);
    if ( !*(_DWORD *)(a1 + 1072) || !hRasClientEventLogHandle )
      goto LABEL_54;
    v14 = 273;
    memset_0(v38, 0, 0x111u);
    memset_0(pszDest, 0, sizeof(pszDest));
    UserData = GetUserData(a2 + 32, 10);
    if ( UserData && *(_DWORD *)(UserData + 20) <= 0x10u )
    {
      StringCchPrintfA(
        pszDest,
        0x50u,
        "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
        *(_DWORD *)(UserData + 24),
        *(unsigned __int16 *)(UserData + 28),
        *(unsigned __int16 *)(UserData + 30),
        *(unsigned __int8 *)(UserData + 32),
        *(unsigned __int8 *)(UserData + 33),
        *(unsigned __int8 *)(UserData + 34),
        *(unsigned __int8 *)(UserData + 35),
        *(unsigned __int8 *)(UserData + 36),
        *(unsigned __int8 *)(UserData + 37),
        *(unsigned __int8 *)(UserData + 38),
        *(unsigned __int8 *)(UserData + 39));
      v14 = 273;
    }
    if ( (unsigned int)IsSystemOwnedConnection(a2) )
    {
      v16 = 2147483646;
      v17 = "SYSTEM";
      v18 = v38;
      do
      {
        if ( !v16 )
          break;
        if ( !*v17 )
          break;
        *v18++ = *v17++;
        --v16;
        --v14;
      }
      while ( v14 );
      v19 = v18 - 1;
      if ( v14 )
        v19 = v18;
      *v19 = 0;
    }
    else
    {
      memset_0(Name, 0, 0x202u);
      v20 = *(void **)(a2 + 96);
      result = 0.0;
      cchName = 257;
      cchReferencedDomainName = 16;
      peUse = 0;
      *(_OWORD *)ReferencedDomainName = 0;
      v34 = 0;
      if ( LookupAccountSidW(0, v20, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      {
        StringCchPrintfA(v38, 0x111u, "%S\\%S", ReferencedDomainName, Name);
      }
      else
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
LABEL_47:
          v22 = *(int *)(a1 + 1324);
          if ( (unsigned int)v22 <= 9 )
          {
            v23 = HIDWORD(rdrMapping[2 * v22]);
            if ( v23 )
            {
              result = 0.0;
              *(_QWORD *)ReferencedDomainName = pszDest;
              *(_QWORD *)&ReferencedDomainName[4] = v38;
              *(_QWORD *)&v34 = a2 + 445;
              *((_QWORD *)&v34 + 1) = v35;
              *(_OWORD *)v35 = 0;
              v36 = 0;
              if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v21[1].Blink) & 0x2000) != 0
                && BYTE1(v21[1].Blink) >= 5u )
              {
                WPP_SF_sd(
                  v21[1].Flink,
                  240,
                  (unsigned int)WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
                  rdrMapping[2 * v22 + 1],
                  v23);
              }
              StringCchPrintfA(v35, 0x20u, "%d", HIDWORD(rdrMapping[2 * *(int *)(a1 + 1324)]));
              RouterLogEventA(hRasClientEventLogHandle, 4u, 0x4F02u, 4u, (LPSTR *)ReferencedDomainName, 0);
            }
          }
LABEL_54:
          v24 = SendSensNotification(8, *(_QWORD *)(a2 + 16));
          if ( v24 )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
LABEL_60:
              if ( *(_DWORD *)(a1 + 1360) == 3 && (*(_BYTE *)(a1 + 1224) & 0x20) != 0 )
                goto LABEL_75;
              *(_DWORD *)g_RasEvent = 128;
              v25 = DwSendNotificationInternal(a2, g_RasEvent);
              if ( v25 )
              {
                v27 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                {
LABEL_72:
                  *(_DWORD *)(a2 + 120) = *(_DWORD *)(a1 + 1072);
                  if ( !*(_DWORD *)(a2 + 164) )
                  {
                    result = FreeConnection((char *)a2);
                    *(_QWORD *)(a1 + 1064) = 0;
                  }
                  v7 = WPP_GLOBAL_Control;
                  a2 = 0;
LABEL_75:
                  if ( !a2 )
                    goto LABEL_94;
                  goto LABEL_89;
                }
                if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
                {
LABEL_68:
                  if ( v27 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(v27[1].Blink) & 0x2000) != 0
                    && BYTE1(v27[1].Blink) >= 5u )
                  {
                    WPP_SF_qqddd(
                      v27[1].Flink,
                      v26,
                      a3,
                      *(_QWORD *)(a2 + 16),
                      a2,
                      *(_DWORD *)(a1 + 1072),
                      *(_DWORD *)(a1 + 1360),
                      *(_DWORD *)(a1 + 1224) & 0x20);
                  }
                  goto LABEL_72;
                }
                result = WPP_SF_d(
                           WPP_GLOBAL_Control[1].Flink,
                           242,
                           WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
                           v25);
              }
              v27 = WPP_GLOBAL_Control;
              goto LABEL_68;
            }
            result = WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 241, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v24);
          }
          v7 = WPP_GLOBAL_Control;
          goto LABEL_60;
        }
        result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 239, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
      }
    }
    v21 = WPP_GLOBAL_Control;
    goto LABEL_47;
  }
LABEL_89:
  if ( !*(_DWORD *)(a2 + 68)
    && v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v7[1].Blink) & 0x2000) != 0
    && BYTE1(v7[1].Blink) >= 5u )
  {
    WPP_SF_qdd(v7[1].Flink, 246, a3, *(_QWORD *)(a2 + 16), 0, *(_DWORD *)(a2 + 88));
  }
LABEL_94:
  *(_QWORD *)(a1 + 1048) = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v9 = 247;
    return WPP_SF_(v7[1].Flink, v9, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x18004563c  mov     [rsp-8+arg_18], rbx
0x180045641  push    rbp
0x180045642  push    rsi
0x180045643  push    rdi
0x180045644  push    r12
0x180045646  push    r13
0x180045648  push    r14
0x18004564a  push    r15
0x18004564c  lea     rbp, [rsp-350h]
0x180045654  sub     rsp, 450h
0x18004565b  mov     rax, cs:__security_cookie
0x180045662  xor     rax, rsp
0x180045665  mov     [rbp+380h+var_40], rax
0x18004566c  mov     bl, r8b
0x18004566f  mov     r13, rdx
0x180045672  mov     r12, rcx
0x180045675  mov     rcx, cs:WPP_GLOBAL_Control
0x18004567c  lea     r14, WPP_GLOBAL_Control
0x180045683  lea     r15, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18004568a  mov     esi, 2000h
0x18004568f  cmp     rcx, r14
0x180045692  jz      short loc_1800456BA
0x180045694  test    [rcx+1Ch], esi
0x180045697  jz      short loc_1800456BA
0x180045699  cmp     byte ptr [rcx+19h], 6
0x18004569d  jb      short loc_1800456BA
0x18004569f  mov     rcx, [rcx+10h]
0x1800456a3  mov     edx, 0EAh
0x1800456a8  mov     r9b, bl
0x1800456ab  mov     r8, r15
0x1800456ae  call    WPP_SF_c
0x1800456b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800456ba  xor     edi, edi
0x1800456bc  test    r13, r13
0x1800456bf  jnz     short loc_180045713
0x1800456c1  cmp     rcx, r14
0x1800456c4  jz      loc_180045D21
0x1800456ca  test    [rcx+1Ch], esi
0x1800456cd  jz      short loc_1800456ED
0x1800456cf  cmp     byte ptr [rcx+19h], 2
0x1800456d3  jb      short loc_1800456ED
0x1800456d5  mov     rcx, [rcx+10h]
0x1800456d9  mov     edx, 0EBh
0x1800456de  mov     r8, r15
0x1800456e1  call    WPP_SF_
0x1800456e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800456ed  cmp     rcx, r14
0x1800456f0  jz      loc_180045D21
0x1800456f6  test    [rcx+1Ch], esi
0x1800456f9  jz      loc_180045D21
0x1800456ff  cmp     byte ptr [rcx+19h], 6
0x180045703  jb      loc_180045D21
0x180045709  mov     edx, 0ECh
0x18004570e  jmp     loc_180045D15
0x180045713  mov     edx, [r13+44h]
0x180045717  test    edx, edx
0x180045719  jz      short loc_18004572A
0x18004571b  dec     edx
0x18004571d  mov     [r13+44h], edx
0x180045721  mov     rcx, cs:WPP_GLOBAL_Control
0x180045728  jmp     short loc_18004572C
0x18004572a  mov     edx, edi
0x18004572c  cmp     rcx, r14
0x18004572f  jz      short loc_180045762
0x180045731  test    [rcx+1Ch], esi
0x180045734  jz      short loc_180045762
0x180045736  cmp     byte ptr [rcx+19h], 5
0x18004573a  jb      short loc_180045762
0x18004573c  mov     r9, [r12]
0x180045740  test    bl, bl
0x180045742  mov     rcx, [rcx+10h]
0x180045746  mov     dword ptr [rsp+480h+peUse], edx
0x18004574a  setnz   al
0x18004574d  mov     [rsp+480h+cchReferencedDomainName], r13
0x180045752  mov     byte ptr [rsp+480h+ReferencedDomainName], al
0x180045756  call    WPP_SF_qcqd
0x18004575b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045762  mov     rdx, [r13+38h]
0x180045766  test    rdx, rdx
0x180045769  jz      short loc_180045786
0x18004576b  mov     eax, [r12+448h]
0x180045773  cmp     eax, [r13+40h]
0x180045777  jnb     short loc_180045786
0x180045779  dec     eax
0x18004577b  mov     [rdx+rax*8], rdi
0x18004577f  mov     rcx, cs:WPP_GLOBAL_Control
0x180045786  cmp     [r13+44h], edi
0x18004578a  jnz     loc_180045BEC
0x180045790  cmp     [r13+58h], edi
0x180045794  jz      short loc_1800457A4
0x180045796  cmp     [r12+430h], edi
0x18004579e  jz      loc_180045CBD
0x1800457a4  mov     rcx, [r13+30h]
0x1800457a8  xor     r8d, r8d
0x1800457ab  lea     edx, [r8+2]
0x1800457af  call    SignalNotifiers
0x1800457b4  lea     rcx, g_csConnectionNotifierList; lpCriticalSection
0x1800457bb  call    cs:__imp_EnterCriticalSection
0x1800457c1  mov     rcx, cs:pConnectionNotifierList
0x1800457c8  xor     r8d, r8d
0x1800457cb  lea     edx, [r8+2]
0x1800457cf  call    SignalNotifiers
0x1800457d4  lea     rcx, g_csConnectionNotifierList; lpCriticalSection
0x1800457db  call    cs:__imp_LeaveCriticalSection
0x1800457e1  cmp     [r12+430h], edi
0x1800457e9  jz      loc_180045AB9
0x1800457ef  cmp     cs:hRasClientEventLogHandle, rdi
0x1800457f6  jz      loc_180045AB9
0x1800457fc  mov     ebx, 111h
0x180045801  lea     rcx, [rbp+380h+var_370]; void *
0x180045805  mov     r8d, ebx; Size
0x180045808  xor     edx, edx; Val
0x18004580a  call    memset_0
0x18004580f  xor     edx, edx; Val
0x180045811  lea     rcx, [rbp+380h+pszDest]; void *
0x180045815  lea     r8d, [rdx+50h]; Size
0x180045819  call    memset_0
0x18004581e  lea     rcx, [r13+20h]
0x180045822  mov     edx, 0Ah
0x180045827  call    GetUserData
0x18004582c  mov     r9, rax
0x18004582f  test    rax, rax
0x180045832  jz      loc_1800458D1
0x180045838  cmp     dword ptr [rax+14h], 10h
0x18004583c  ja      loc_1800458D1
0x180045842  movzx   ecx, byte ptr [rax+27h]
0x180045846  mov     edx, 50h ; 'P'; cchDest
0x18004584b  movzx   r8d, byte ptr [rax+26h]
0x180045850  movzx   r10d, byte ptr [rax+25h]
0x180045855  movzx   r11d, byte ptr [rax+24h]
0x18004585a  movzx   ebx, byte ptr [rax+23h]
0x18004585e  movzx   edi, byte ptr [r9+21h]
0x180045863  movzx   esi, byte ptr [r9+20h]
0x180045868  movzx   r14d, word ptr [r9+1Eh]
0x18004586d  movzx   r15d, word ptr [r9+1Ch]
0x180045872  movzx   eax, byte ptr [rax+22h]
0x180045876  mov     r9d, [r9+18h]
0x18004587a  mov     [rsp+480h+var_418], ecx
0x18004587e  lea     rcx, [rbp+380h+pszDest]; pszDest
0x180045882  mov     [rsp+480h+var_420], r8d
0x180045887  lea     r8, a08x04x04x02x02_1; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x18004588e  mov     [rsp+480h+var_428], r10d
0x180045893  mov     [rsp+480h+var_430], r11d
0x180045898  mov     [rsp+480h+var_438], ebx
0x18004589c  mov     [rsp+480h+var_440], eax
0x1800458a0  mov     [rsp+480h+var_448], edi
0x1800458a4  mov     dword ptr [rsp+480h+peUse], esi
0x1800458a8  mov     dword ptr [rsp+480h+cchReferencedDomainName], r14d
0x1800458ad  mov     dword ptr [rsp+480h+ReferencedDomainName], r15d
0x1800458b2  call    StringCchPrintfA
0x1800458b7  xor     edi, edi
0x1800458b9  lea     r14, WPP_GLOBAL_Control
0x1800458c0  mov     ebx, 111h
0x1800458c5  lea     r15, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800458cc  mov     esi, 2000h
0x1800458d1  mov     rcx, r13
0x1800458d4  call    IsSystemOwnedConnection
0x1800458d9  test    eax, eax
0x1800458db  jz      short loc_18004591F
0x1800458dd  mov     eax, 7FFFFFFEh
0x1800458e2  lea     rdx, aSystem; "SYSTEM"
0x1800458e9  lea     rcx, [rbp+380h+var_370]
0x1800458ed  test    rax, rax
0x1800458f0  jz      short loc_18004590C
0x1800458f2  mov     r8b, [rdx]
0x1800458f5  test    r8b, r8b
0x1800458f8  jz      short loc_18004590C
0x1800458fa  mov     [rcx], r8b
0x1800458fd  inc     rdx
0x180045900  inc     rcx
0x180045903  dec     rax
0x180045906  sub     rbx, 1
0x18004590a  jnz     short loc_1800458ED
0x18004590c  test    rbx, rbx
0x18004590f  lea     rax, [rcx-1]
0x180045913  cmovnz  rax, rcx
0x180045917  mov     [rax], dil
0x18004591a  jmp     loc_1800459D8
0x18004591f  xor     edx, edx; Val
0x180045921  lea     rcx, [rbp+380h+Name]; void *
0x180045928  mov     r8d, 202h; Size
0x18004592e  call    memset_0
0x180045933  mov     rdx, [r13+60h]; Sid
0x180045937  lea     rax, [rsp+480h+var_410]
0x18004593c  mov     [rsp+480h+peUse], rax; peUse
0x180045941  lea     r9, [rsp+480h+cchName]; cchName
0x180045946  xorps   xmm0, xmm0
0x180045949  mov     [rsp+480h+cchName], 101h
0x180045951  lea     rax, [rsp+480h+var_40C]
0x180045956  mov     [rsp+480h+var_40C], 10h
0x18004595e  mov     [rsp+480h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180045963  lea     r8, [rbp+380h+Name]; Name
0x18004596a  lea     rax, [rbp+380h+var_400]
0x18004596e  mov     [rsp+480h+var_410], edi
0x180045972  xor     ecx, ecx; lpSystemName
0x180045974  mov     [rsp+480h+ReferencedDomainName], rax; ReferencedDomainName
0x180045979  movups  xmmword ptr [rbp+380h+var_400], xmm0
0x18004597d  movups  [rbp+380h+var_3F0], xmm0
0x180045981  call    cs:__imp_LookupAccountSidW
0x180045987  test    eax, eax
0x180045989  jnz     short loc_1800459B5
0x18004598b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045992  cmp     rcx, r14
0x180045995  jz      short loc_1800459DF
0x180045997  test    [rcx+1Ch], esi
0x18004599a  jz      short loc_1800459DF
0x18004599c  cmp     byte ptr [rcx+19h], 2
0x1800459a0  jb      short loc_1800459DF
0x1800459a2  mov     rcx, [rcx+10h]
0x1800459a6  mov     edx, 0EFh
0x1800459ab  mov     r8, r15
0x1800459ae  call    WPP_SF_
0x1800459b3  jmp     short loc_1800459D8
0x1800459b5  lea     rax, [rbp+380h+Name]
0x1800459bc  mov     rdx, rbx; cchDest
0x1800459bf  lea     r9, [rbp+380h+var_400]
0x1800459c3  mov     [rsp+480h+ReferencedDomainName], rax
0x1800459c8  lea     r8, aSS; "%S\\%S"
0x1800459cf  lea     rcx, [rbp+380h+var_370]; pszDest
0x1800459d3  call    StringCchPrintfA
0x1800459d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800459df  movsxd  rax, dword ptr [r12+52Ch]
0x1800459e7  test    eax, eax
0x1800459e9  js      loc_180045AB9
0x1800459ef  cmp     eax, 0Ah
0x1800459f2  jnb     loc_180045AB9
0x1800459f8  mov     r9, rax
0x1800459fb  lea     rbx, rdrMapping
0x180045a02  add     r9, r9
0x180045a05  mov     r8d, [rbx+r9*8+4]
0x180045a0a  test    r8d, r8d
0x180045a0d  jz      loc_180045AB9
0x180045a13  lea     rax, [rbp+380h+pszDest]
0x180045a17  xorps   xmm0, xmm0
0x180045a1a  mov     qword ptr [rbp+380h+var_400], rax
0x180045a1e  lea     rax, [rbp+380h+var_370]
0x180045a22  mov     qword ptr [rbp+380h+var_400+8], rax
0x180045a26  lea     rax, [r13+1BDh]
0x180045a2d  mov     qword ptr [rbp+380h+var_3F0], rax
0x180045a31  lea     rax, [rbp+380h+var_3E0]
0x180045a35  mov     qword ptr [rbp+380h+var_3F0+8], rax
0x180045a39  movups  xmmword ptr [rbp+380h+var_3E0], xmm0
0x180045a3d  movups  [rbp+380h+var_3D0], xmm0
0x180045a41  cmp     rcx, r14
0x180045a44  jz      short loc_180045A6C
0x180045a46  test    [rcx+1Ch], esi
0x180045a49  jz      short loc_180045A6C
0x180045a4b  cmp     byte ptr [rcx+19h], 5
0x180045a4f  jb      short loc_180045A6C
0x180045a51  mov     r9, [rbx+r9*8+8]
0x180045a56  mov     edx, 0F0h
0x180045a5b  mov     rcx, [rcx+10h]
0x180045a5f  mov     dword ptr [rsp+480h+ReferencedDomainName], r8d
0x180045a64  mov     r8, r15
0x180045a67  call    WPP_SF_sd
0x180045a6c  movsxd  r9, dword ptr [r12+52Ch]
0x180045a74  lea     r8, aD_0; "%d"
0x180045a7b  add     r9, r9
0x180045a7e  lea     rcx, [rbp+380h+var_3E0]; pszDest
0x180045a82  mov     edx, 20h ; ' '; cchDest
0x180045a87  mov     r9d, [rbx+r9*8+4]
0x180045a8c  call    StringCchPrintfA
0x180045a91  mov     rcx, cs:hRasClientEventLogHandle; hLogHandle
0x180045a98  lea     rax, [rbp+380h+var_400]
0x180045a9c  mov     edx, 4; dwEventType
0x180045aa1  mov     dword ptr [rsp+480h+cchReferencedDomainName], edi; dwErrorCode
0x180045aa5  mov     r9d, edx; dwSubStringCount
0x180045aa8  mov     [rsp+480h+ReferencedDomainName], rax; plpszSubStringArray
0x180045aad  mov     r8d, 4F02h; dwMessageId
0x180045ab3  call    cs:__imp_RouterLogEventA
0x180045ab9  mov     rdx, [r13+10h]
0x180045abd  mov     ecx, 8
0x180045ac2  call    SendSensNotification
0x180045ac7  test    eax, eax
0x180045ac9  jz      short loc_180045AF6
0x180045acb  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ad2  cmp     rcx, r14
0x180045ad5  jz      short loc_180045AFD
0x180045ad7  test    [rcx+1Ch], esi
0x180045ada  jz      short loc_180045AFD
0x180045adc  cmp     byte ptr [rcx+19h], 2
0x180045ae0  jb      short loc_180045AFD
0x180045ae2  mov     rcx, [rcx+10h]
0x180045ae6  mov     edx, 0F1h
0x180045aeb  mov     r9d, eax
0x180045aee  mov     r8, r15
0x180045af1  call    WPP_SF_d
0x180045af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180045afd  cmp     dword ptr [r12+550h], 3
0x180045b06  jnz     short loc_180045B17
0x180045b08  test    byte ptr [r12+4C8h], 20h
0x180045b11  jnz     loc_180045BDE
0x180045b17  lea     rdx, g_RasEvent
0x180045b1e  mov     cs:g_RasEvent, 80h
0x180045b28  mov     rcx, r13
0x180045b2b  call    DwSendNotificationInternal
0x180045b30  test    eax, eax
0x180045b32  jz      short loc_180045B5F
0x180045b34  mov     rcx, cs:WPP_GLOBAL_Control
0x180045b3b  cmp     rcx, r14
  ... truncated ...
```
