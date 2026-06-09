# RasProtocolStart

- ea: `0x18001cd30`
- end: `0x18001d30f`
- name: `RasProtocolStart`
- size: `1503`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001c70`
- `0x180002f80`
- `0x1800119c4`
- `0x18001cd30`
- `0x18001fb60`
- `0x180020fd8`
- `0x180021000`
- `0x1800210b0`
- `0x1800213a4`
- `0x1800213e4`
- `0x180021488`
- `0x180021aac`
- `0x180024d88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d1a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d1a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d197`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d197`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d103`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d103`

## pseudocode

```c
__int64 __fastcall RasProtocolStart(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        unsigned int *a11,
        __int64 a12,
        __int64 a13,
        int a14)
{
  __int64 v14; // r12
  PVOID *v17; // rcx
  PVOID *v18; // rcx
  unsigned int v19; // edi
  __int64 v20; // rdx
  HLOCAL v21; // rax
  __int64 v22; // rdx
  void *v23; // rsi
  unsigned int UserSid; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // eax
  DWORD CurrentProcessId; // [rsp+78h] [rbp-50h]

  v14 = a4;
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qqc(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a13, a14 != 0);
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a11 )
  {
    if ( v17 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
      {
        WPP_SF_(v17[2], 451, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v17 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
        {
          WPP_SF_d(v17[2], 452, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, *a11);
          v17 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v17 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
          {
            WPP_SF_q(v17[2], 453, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, *((_QWORD *)a11 + 1));
            v17 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v17 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
            {
              WPP_SF_q(v17[2], 454, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, *((_QWORD *)a11 + 2));
              v17 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v17 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
              {
                WPP_SF__guid_(v17[2], a2, a3, a11 + 134);
                v17 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v17 != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                {
                  WPP_SF_d(v17[2], 456, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a11[138]);
                  v17 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( v17 != &WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                  {
                    WPP_SF_d(v17[2], 457, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a11[139]);
                    v17 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( v17 != &WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                    {
                      LOBYTE(a4) = a11[140] != 0;
                      WPP_SF_c(v17[2], 458, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a4);
                      v17 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( v17 != &WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                      {
                        LOBYTE(a4) = a11[432] != 0;
                        WPP_SF_c(v17[2], 459, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a4);
                        v17 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v17 != &WPP_GLOBAL_Control )
                      {
                        if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                        {
                          WPP_SF_S(v17[2], 460, a3, a11 + 438);
                          v17 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        if ( v17 != &WPP_GLOBAL_Control )
                        {
                          if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                          {
                            WPP_SF_S(v17[2], 461, a3, (char *)a11 + 2266);
                            v17 = (PVOID *)WPP_GLOBAL_Control;
                          }
                          if ( v17 != &WPP_GLOBAL_Control
                            && (*((_BYTE *)v17 + 28) & 0x40) != 0
                            && *((_BYTE *)v17 + 25) >= 5u )
                          {
                            LOBYTE(a4) = a11[695] != 0;
                            WPP_SF_c(v17[2], 462, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a4);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
  {
    WPP_SF_(v17[2], 463, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    v19 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = 464;
LABEL_92:
      WPP_SF_d(v18[2], v20, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v19);
      return v19;
    }
    return v19;
  }
  if ( !(unsigned int)IsRasmanProcess() || NtCurrentTeb()->IsImpersonating )
  {
    v21 = LocalAlloc(0x40u, 0x1388u);
    v23 = v21;
    if ( v21 )
    {
      UserSid = GetUserSid(v21, v22);
      if ( UserSid )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v26 = 466;
      }
      else
      {
        UserSid = RasSetPortUserData(a1, 8, v23, 5000);
        if ( !UserSid )
          goto LABEL_77;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v26 = 465;
      }
      WPP_SF_d(v25[2], v26, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, UserSid);
LABEL_77:
      LocalFree(v23);
      goto LABEL_78;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 467, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    }
  }
LABEL_78:
  CurrentProcessId = GetCurrentProcessId();
  v27 = SubmitLocalRequest(0x41u, a1, a2, a3, v14, a5, a6, a7, a8, a9, a10, a11, a12, a13, a14, CurrentProcessId);
  v19 = v27;
  if ( v27 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v19;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_88;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 468, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v27);
  }
  v18 = (PVOID *)WPP_GLOBAL_Control;
LABEL_88:
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) >= 6u )
  {
    v20 = 469;
    goto LABEL_92;
  }
  return v19;
}

```

## disassembly

```asm
0x18001cd30  mov     [rsp+arg_8], rdx
0x18001cd35  push    rbx
0x18001cd36  push    rbp
0x18001cd37  push    rsi
0x18001cd38  push    rdi
0x18001cd39  push    r12
0x18001cd3b  push    r13
0x18001cd3d  push    r14
0x18001cd3f  push    r15
0x18001cd41  sub     rsp, 88h
0x18001cd48  mov     r12, r9
0x18001cd4b  mov     r13, r8
0x18001cd4e  mov     rbp, rcx
0x18001cd51  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd58  lea     rbx, WPP_GLOBAL_Control
0x18001cd5f  mov     r14d, [rsp+0C8h+arg_68]
0x18001cd67  mov     esi, 40h ; '@'
0x18001cd6c  mov     r15, [rsp+0C8h+arg_60]
0x18001cd74  cmp     rcx, rbx
0x18001cd77  jz      short loc_18001CDA7
0x18001cd79  test    [rcx+1Ch], sil
0x18001cd7d  jz      short loc_18001CDA7
0x18001cd7f  cmp     byte ptr [rcx+19h], 6
0x18001cd83  jb      short loc_18001CDA7
0x18001cd85  mov     rcx, [rcx+10h]
0x18001cd89  test    r14d, r14d
0x18001cd8c  mov     r9, rbp
0x18001cd8f  setnz   al
0x18001cd92  mov     byte ptr [rsp+0C8h+var_A0], al
0x18001cd96  mov     [rsp+0C8h+var_A8], r15
0x18001cd9b  call    WPP_SF_qqc
0x18001cda0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cda7  mov     rdi, [rsp+0C8h+arg_50]
0x18001cdaf  test    rdi, rdi
0x18001cdb2  jz      loc_18001D073
0x18001cdb8  cmp     rcx, rbx
0x18001cdbb  jz      loc_18001D0A1
0x18001cdc1  mov     bl, 5
0x18001cdc3  test    [rcx+1Ch], sil
0x18001cdc7  jz      short loc_18001CDEA
0x18001cdc9  cmp     [rcx+19h], bl
0x18001cdcc  jb      short loc_18001CDEA
0x18001cdce  mov     rcx, [rcx+10h]
0x18001cdd2  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001cdd9  mov     edx, 1C3h
0x18001cdde  call    WPP_SF_
0x18001cde3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdea  lea     rax, WPP_GLOBAL_Control
0x18001cdf1  cmp     rcx, rax
0x18001cdf4  jz      loc_18001D09A
0x18001cdfa  test    [rcx+1Ch], sil
0x18001cdfe  jz      short loc_18001CE2B
0x18001ce00  cmp     [rcx+19h], bl
0x18001ce03  jb      short loc_18001CE2B
0x18001ce05  mov     r9d, [rdi]
0x18001ce08  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ce0f  mov     rcx, [rcx+10h]
0x18001ce13  mov     edx, 1C4h
0x18001ce18  call    WPP_SF_d
0x18001ce1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce24  lea     rax, WPP_GLOBAL_Control
0x18001ce2b  cmp     rcx, rax
0x18001ce2e  jz      loc_18001D09A
0x18001ce34  test    [rcx+1Ch], sil
0x18001ce38  jz      short loc_18001CE66
0x18001ce3a  cmp     [rcx+19h], bl
0x18001ce3d  jb      short loc_18001CE66
0x18001ce3f  mov     r9, [rdi+8]
0x18001ce43  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ce4a  mov     rcx, [rcx+10h]
0x18001ce4e  mov     edx, 1C5h
0x18001ce53  call    WPP_SF_q
0x18001ce58  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce5f  lea     rax, WPP_GLOBAL_Control
0x18001ce66  cmp     rcx, rax
0x18001ce69  jz      loc_18001D09A
0x18001ce6f  test    [rcx+1Ch], sil
0x18001ce73  jz      short loc_18001CEA1
0x18001ce75  cmp     [rcx+19h], bl
0x18001ce78  jb      short loc_18001CEA1
0x18001ce7a  mov     r9, [rdi+10h]
0x18001ce7e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001ce85  mov     rcx, [rcx+10h]
0x18001ce89  mov     edx, 1C6h
0x18001ce8e  call    WPP_SF_q
0x18001ce93  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce9a  lea     rax, WPP_GLOBAL_Control
0x18001cea1  cmp     rcx, rax
0x18001cea4  jz      loc_18001D09A
0x18001ceaa  test    [rcx+1Ch], sil
0x18001ceae  jz      short loc_18001CED3
0x18001ceb0  cmp     [rcx+19h], bl
0x18001ceb3  jb      short loc_18001CED3
0x18001ceb5  mov     rcx, [rcx+10h]
0x18001ceb9  lea     r9, [rdi+218h]
0x18001cec0  call    WPP_SF__guid_
0x18001cec5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cecc  lea     rax, WPP_GLOBAL_Control
0x18001ced3  cmp     rcx, rax
0x18001ced6  jz      loc_18001D09A
0x18001cedc  test    [rcx+1Ch], sil
0x18001cee0  jz      short loc_18001CF11
0x18001cee2  cmp     [rcx+19h], bl
0x18001cee5  jb      short loc_18001CF11
0x18001cee7  mov     r9d, [rdi+228h]
0x18001ceee  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001cef5  mov     rcx, [rcx+10h]
0x18001cef9  mov     edx, 1C8h
0x18001cefe  call    WPP_SF_d
0x18001cf03  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf0a  lea     rax, WPP_GLOBAL_Control
0x18001cf11  cmp     rcx, rax
0x18001cf14  jz      loc_18001D09A
0x18001cf1a  test    [rcx+1Ch], sil
0x18001cf1e  jz      short loc_18001CF4F
0x18001cf20  cmp     [rcx+19h], bl
0x18001cf23  jb      short loc_18001CF4F
0x18001cf25  mov     r9d, [rdi+22Ch]
0x18001cf2c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001cf33  mov     rcx, [rcx+10h]
0x18001cf37  mov     edx, 1C9h
0x18001cf3c  call    WPP_SF_d
0x18001cf41  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf48  lea     rax, WPP_GLOBAL_Control
0x18001cf4f  cmp     rcx, rax
0x18001cf52  jz      loc_18001D09A
0x18001cf58  test    [rcx+1Ch], sil
0x18001cf5c  jz      short loc_18001CF91
0x18001cf5e  cmp     [rcx+19h], bl
0x18001cf61  jb      short loc_18001CF91
0x18001cf63  cmp     dword ptr [rdi+230h], 0
0x18001cf6a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001cf71  mov     rcx, [rcx+10h]
0x18001cf75  mov     edx, 1CAh
0x18001cf7a  setnz   r9b
0x18001cf7e  call    WPP_SF_c
0x18001cf83  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf8a  lea     rax, WPP_GLOBAL_Control
0x18001cf91  cmp     rcx, rax
0x18001cf94  jz      loc_18001D09A
0x18001cf9a  test    [rcx+1Ch], sil
0x18001cf9e  jz      short loc_18001CFD3
0x18001cfa0  cmp     [rcx+19h], bl
0x18001cfa3  jb      short loc_18001CFD3
0x18001cfa5  cmp     dword ptr [rdi+6C0h], 0
0x18001cfac  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001cfb3  mov     rcx, [rcx+10h]
0x18001cfb7  mov     edx, 1CBh
0x18001cfbc  setnz   r9b
0x18001cfc0  call    WPP_SF_c
0x18001cfc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfcc  lea     rax, WPP_GLOBAL_Control
0x18001cfd3  cmp     rcx, rax
0x18001cfd6  jz      loc_18001D09A
0x18001cfdc  test    [rcx+1Ch], sil
0x18001cfe0  jz      short loc_18001D00A
0x18001cfe2  cmp     [rcx+19h], bl
0x18001cfe5  jb      short loc_18001D00A
0x18001cfe7  mov     rcx, [rcx+10h]
0x18001cfeb  lea     r9, [rdi+6D8h]
0x18001cff2  mov     edx, 1CCh
0x18001cff7  call    WPP_SF_S
0x18001cffc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d003  lea     rax, WPP_GLOBAL_Control
0x18001d00a  cmp     rcx, rax
0x18001d00d  jz      loc_18001D09A
0x18001d013  test    [rcx+1Ch], sil
0x18001d017  jz      short loc_18001D041
0x18001d019  cmp     [rcx+19h], bl
0x18001d01c  jb      short loc_18001D041
0x18001d01e  mov     rcx, [rcx+10h]
0x18001d022  lea     r9, [rdi+8DAh]
0x18001d029  mov     edx, 1CDh
0x18001d02e  call    WPP_SF_S
0x18001d033  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d03a  lea     rax, WPP_GLOBAL_Control
0x18001d041  cmp     rcx, rax
0x18001d044  jz      short loc_18001D09A
0x18001d046  test    [rcx+1Ch], sil
0x18001d04a  jz      short loc_18001D09A
0x18001d04c  cmp     [rcx+19h], bl
0x18001d04f  jb      short loc_18001D09A
0x18001d051  cmp     dword ptr [rdi+0ADCh], 0
0x18001d058  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d05f  mov     rcx, [rcx+10h]
0x18001d063  mov     edx, 1CEh
0x18001d068  setnz   r9b
0x18001d06c  call    WPP_SF_c
0x18001d071  jmp     short loc_18001D09A
0x18001d073  cmp     rcx, rbx
0x18001d076  jz      short loc_18001D0A1
0x18001d078  test    [rcx+1Ch], sil
0x18001d07c  jz      short loc_18001D0A1
0x18001d07e  mov     bl, 5
0x18001d080  cmp     [rcx+19h], bl
0x18001d083  jb      short loc_18001D09A
0x18001d085  mov     rcx, [rcx+10h]
0x18001d089  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d090  mov     edx, 1CFh
0x18001d095  call    WPP_SF_
0x18001d09a  lea     rbx, WPP_GLOBAL_Control
0x18001d0a1  mov     rcx, rbp
0x18001d0a4  call    ValidatePortHandle
0x18001d0a9  test    eax, eax
0x18001d0ab  jnz     short loc_18001D0E1
0x18001d0ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0b4  mov     edi, 259h
0x18001d0b9  cmp     rcx, rbx
0x18001d0bc  jz      loc_18001D2F9
0x18001d0c2  test    [rcx+1Ch], sil
0x18001d0c6  jz      loc_18001D2F9
0x18001d0cc  mov     bl, 2
0x18001d0ce  cmp     [rcx+19h], bl
0x18001d0d1  jb      loc_18001D2F9
0x18001d0d7  mov     edx, 1D0h
0x18001d0dc  jmp     loc_18001D2E6
0x18001d0e1  call    IsRasmanProcess
0x18001d0e6  mov     bl, 2
0x18001d0e8  test    eax, eax
0x18001d0ea  jz      short loc_18001D0FC
0x18001d0ec  mov     eax, gs:179Ch
0x18001d0f4  test    eax, eax
0x18001d0f6  jz      loc_18001D1A2
0x18001d0fc  mov     edx, 1388h; uBytes
0x18001d101  mov     ecx, esi; uFlags
0x18001d103  call    cs:__imp_LocalAlloc
0x18001d109  mov     rsi, rax
0x18001d10c  test    rax, rax
0x18001d10f  jz      loc_18001D279
0x18001d115  mov     rcx, rax
0x18001d118  call    GetUserSid
0x18001d11d  test    eax, eax
0x18001d11f  jnz     short loc_18001D15E
0x18001d121  mov     r9d, 1388h
0x18001d127  lea     edx, [rax+8]
0x18001d12a  mov     r8, rsi
0x18001d12d  mov     rcx, rbp
0x18001d130  call    RasSetPortUserData
0x18001d135  test    eax, eax
0x18001d137  jz      short loc_18001D194
0x18001d139  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d140  lea     rdx, WPP_GLOBAL_Control
0x18001d147  cmp     rcx, rdx
0x18001d14a  jz      short loc_18001D194
0x18001d14c  test    byte ptr [rcx+1Ch], 40h
0x18001d150  jz      short loc_18001D194
0x18001d152  cmp     [rcx+19h], bl
0x18001d155  jb      short loc_18001D194
0x18001d157  mov     edx, 1D1h
0x18001d15c  jmp     short loc_18001D181
0x18001d15e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d165  lea     rdx, WPP_GLOBAL_Control
0x18001d16c  cmp     rcx, rdx
0x18001d16f  jz      short loc_18001D194
0x18001d171  test    byte ptr [rcx+1Ch], 40h
0x18001d175  jz      short loc_18001D194
0x18001d177  cmp     [rcx+19h], bl
0x18001d17a  jb      short loc_18001D194
0x18001d17c  mov     edx, 1D2h
0x18001d181  mov     rcx, [rcx+10h]
0x18001d185  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d18c  mov     r9d, eax
0x18001d18f  call    WPP_SF_d
0x18001d194  mov     rcx, rsi; hMem
0x18001d197  call    cs:__imp_LocalFree
0x18001d19d  mov     esi, 40h ; '@'
0x18001d1a2  call    cs:__imp_GetCurrentProcessId
0x18001d1a8  mov     r8, [rsp+0C8h+arg_8]
0x18001d1b0  mov     ecx, 41h ; 'A'
0x18001d1b5  mov     [rsp+0C8h+var_50], eax
0x18001d1b9  mov     r9, r13
0x18001d1bc  mov     rax, [rsp+0C8h+arg_58]
0x18001d1c4  mov     rdx, rbp
0x18001d1c7  mov     [rsp+0C8h+var_58], r14d
0x18001d1cc  mov     [rsp+0C8h+var_60], r15
0x18001d1d1  mov     [rsp+0C8h+var_68], rax
0x18001d1d6  mov     rax, [rsp+0C8h+arg_48]
0x18001d1de  mov     [rsp+0C8h+var_70], rdi
0x18001d1e3  mov     [rsp+0C8h+var_78], rax
0x18001d1e8  mov     rax, [rsp+0C8h+arg_40]
0x18001d1f0  mov     [rsp+0C8h+var_80], rax
0x18001d1f5  mov     rax, [rsp+0C8h+arg_38]
0x18001d1fd  mov     [rsp+0C8h+var_88], rax
0x18001d202  mov     rax, [rsp+0C8h+arg_30]
0x18001d20a  mov     [rsp+0C8h+var_90], rax
0x18001d20f  mov     rax, [rsp+0C8h+arg_28]
0x18001d217  mov     [rsp+0C8h+var_98], rax
0x18001d21c  mov     rax, [rsp+0C8h+arg_20]
0x18001d224  mov     [rsp+0C8h+var_A0], rax
0x18001d229  mov     [rsp+0C8h+var_A8], r12
0x18001d22e  call    SubmitLocalRequest
0x18001d233  mov     edi, eax
0x18001d235  test    eax, eax
0x18001d237  jz      loc_18001D2C2
0x18001d23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d244  lea     rbp, WPP_GLOBAL_Control
0x18001d24b  cmp     rcx, rbp
0x18001d24e  jz      loc_18001D2F9
0x18001d254  test    [rcx+1Ch], sil
0x18001d258  jz      short loc_18001D2D0
  ... truncated ...
```
