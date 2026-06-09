# RemoveExclusionRoutesFromVPNInterface

- ea: `0x180052538`
- end: `0x180052a1a`
- name: `RemoveExclusionRoutesFromVPNInterface`
- size: `1250`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180052a20`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180032118`
- `0x180050a50`
- `0x180052538`
- `0x18005de1c`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180052800`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180052800`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800529b0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800529b0`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x18005275c`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180052953`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x18005275c`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180052953`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x1800527e6`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x180052842`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x1800527e6`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x180052842`

## pseudocode

```c
__int64 __fastcall RemoveExclusionRoutesFromVPNInterface(__int64 a1)
{
  __int64 v2; // r12
  __int64 v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // r14
  struct _LIST_ENTRY *v6; // rcx
  unsigned int v7; // r15d
  __int64 v8; // rsi
  unsigned int *v9; // rbx
  __int64 v10; // r9
  NTSTATUS v11; // eax
  struct tagRASENTRYW *v12; // rbx
  __int64 v13; // rsi
  struct _LIST_ENTRY *v14; // rcx
  NTSTATUS v15; // eax
  DWORD v17; // [rsp+30h] [rbp-D0h] BYREF
  struct tagRASENTRYW *v18; // [rsp+38h] [rbp-C8h]
  MIB_IPFORWARD_ROW2 Row; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v20[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR WideCharStr[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 42, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
  }
  memset_0(&Row, 0, sizeof(Row));
  v2 = 0;
  v17 = 0;
  StrncpyAtoW(WideCharStr, (LPCCH)(a1 + 184));
  StrncpyAtoW(v20, (LPCCH)(a1 + 445));
  if ( *(char *)(a1 + 112) >= 0 || (v3 = *(_QWORD *)(a1 + 912)) == 0 )
  {
LABEL_36:
    if ( RasGetEntryPropertiesW(WideCharStr, v20, 0, &v17, 0, 0) != 603 )
      goto LABEL_62;
    v18 = (struct tagRASENTRYW *)GlobalAlloc(0x40u, v17);
    v12 = v18;
    if ( !v18 )
      goto LABEL_62;
    v18->dwSize = v17;
    if ( RasGetEntryPropertiesW(WideCharStr, v20, v12, &v17, 0, 0)
      || (v12->dwfOptions2 & 0x80000000) == 0
      || !*(_QWORD *)(a1 + 944)
      || !*(_DWORD *)(a1 + 952) )
    {
LABEL_61:
      GlobalFree(v12);
      goto LABEL_62;
    }
    v13 = 0;
    v14 = WPP_GLOBAL_Control;
    while ( 1 )
    {
      if ( *(_DWORD *)(v2 + 36 * v13 + 4) == 2 || *(_DWORD *)(v2 + 36 * v13 + 4) == 23 )
      {
        CreateRouteEntry(&Row);
        Row.InterfaceIndex = *(_DWORD *)(v2 + 36 * v13 + 32);
        v15 = DeleteIpForwardEntry2(&Row);
        if ( v15 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_59;
          }
          WPP_SF_qD(
            WPP_GLOBAL_Control[1].Flink,
            49,
            WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids,
            *(unsigned int *)(v2 + 36 * v13 + 32),
            v15);
        }
      }
      else
      {
        if ( v14 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(v14[1].Blink) & 0x2000) == 0
          || BYTE1(v14[1].Blink) < 4u )
        {
          goto LABEL_59;
        }
        WPP_SF_d(
          v14[1].Flink,
          48,
          WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids,
          *(unsigned int *)(*(_QWORD *)(a1 + 944) + 36 * v13 + 4));
      }
      v14 = WPP_GLOBAL_Control;
LABEL_59:
      v13 = (unsigned int)(v13 + 1);
      if ( (unsigned int)v13 >= *(_DWORD *)(a1 + 952) )
      {
        v12 = v18;
        goto LABEL_61;
      }
    }
  }
  v4 = *(unsigned int *)(v3 + 88);
  v5 = *(unsigned int *)(v3 + 44);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 43, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, (unsigned int)v5);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (_DWORD)v5 )
  {
    v2 = v3 + v4;
    if ( !(v3 + v4)
      || (unsigned __int64)(36 * v5) > 0xFFFFFFFF
      || *(_DWORD *)(*(_QWORD *)(a1 + 912) + 48LL) < (unsigned int)(36 * v5) )
    {
      if ( v6 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return 0;
      if ( (HIDWORD(v6[1].Blink) & 0x2000) == 0 || BYTE1(v6[1].Blink) < 5u )
        goto LABEL_63;
      WPP_SF_d(v6[1].Flink, 45, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 111);
      goto LABEL_62;
    }
    v7 = 0;
    v8 = 0;
    while ( 1 )
    {
      v9 = (unsigned int *)(v2 + 36 * v8);
      if ( !v9[7] || !v9[8] )
        goto LABEL_35;
      v10 = v9[1];
      if ( (_DWORD)v10 == 2 || (_DWORD)v10 == 23 )
      {
        CreateRouteEntry(&Row);
        Row.InterfaceIndex = v9[8];
        v11 = DeleteIpForwardEntry2(&Row);
        if ( v11 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_35;
          }
          WPP_SF_qD(WPP_GLOBAL_Control[1].Flink, 47, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v9[8], v11);
        }
      }
      else
      {
        if ( v6 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(v6[1].Blink) & 0x2000) == 0
          || BYTE1(v6[1].Blink) < 4u )
        {
          goto LABEL_35;
        }
        WPP_SF_d(v6[1].Flink, 46, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v10);
      }
      v6 = WPP_GLOBAL_Control;
LABEL_35:
      ++v7;
      ++v8;
      if ( v7 >= (unsigned int)v5 )
        goto LABEL_36;
    }
  }
  if ( v6 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return 0;
  if ( (HIDWORD(v6[1].Blink) & 0x2000) != 0 && BYTE1(v6[1].Blink) >= 5u )
  {
    WPP_SF_(v6[1].Flink, 44, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
LABEL_62:
    v6 = WPP_GLOBAL_Control;
  }
LABEL_63:
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v6[1].Blink) & 0x2000) != 0
    && BYTE1(v6[1].Blink) >= 6u )
  {
    WPP_SF_d(v6[1].Flink, 50, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180052538  mov     [rsp-8+arg_8], rbx
0x18005253d  mov     [rsp-8+arg_10], rsi
0x180052542  push    rbp
0x180052543  push    rdi
0x180052544  push    r12
0x180052546  push    r14
0x180052548  push    r15
0x18005254a  lea     rbp, [rsp-3E0h]
0x180052552  sub     rsp, 4E0h
0x180052559  mov     rax, cs:__security_cookie
0x180052560  xor     rax, rsp
0x180052563  mov     [rbp+400h+var_30], rax
0x18005256a  mov     rdi, rcx
0x18005256d  mov     rcx, cs:WPP_GLOBAL_Control
0x180052574  lea     rax, WPP_GLOBAL_Control
0x18005257b  mov     r15d, 2000h
0x180052581  cmp     rcx, rax
0x180052584  jz      short loc_1800525A7
0x180052586  test    [rcx+1Ch], r15d
0x18005258a  jz      short loc_1800525A7
0x18005258c  cmp     byte ptr [rcx+19h], 6
0x180052590  jb      short loc_1800525A7
0x180052592  mov     rcx, [rcx+10h]
0x180052596  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005259d  mov     edx, 2Ah ; '*'
0x1800525a2  call    WPP_SF_
0x1800525a7  xor     edx, edx; Val
0x1800525a9  lea     rcx, [rsp+500h+Row]; void *
0x1800525ae  lea     r8d, [rdx+68h]; Size
0x1800525b2  call    memset_0
0x1800525b7  xor     r12d, r12d
0x1800525ba  lea     rdx, [rdi+0B8h]; lpMultiByteStr
0x1800525c1  mov     r8d, 105h
0x1800525c7  mov     [rsp+500h+var_4D0], r12d
0x1800525cc  lea     rcx, [rbp+400h+WideCharStr]; lpWideCharStr
0x1800525d3  call    StrncpyAtoW
0x1800525d8  lea     rdx, [rdi+1BDh]; lpMultiByteStr
0x1800525df  mov     r8d, 101h
0x1800525e5  lea     rcx, [rbp+400h+var_450]; lpWideCharStr
0x1800525e9  call    StrncpyAtoW
0x1800525ee  test    byte ptr [rdi+70h], 80h
0x1800525f2  jz      loc_1800527C1
0x1800525f8  mov     rbx, [rdi+390h]
0x1800525ff  test    rbx, rbx
0x180052602  jz      loc_1800527C1
0x180052608  mov     esi, [rbx+58h]
0x18005260b  mov     r14d, [rbx+2Ch]
0x18005260f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052616  lea     r8, WPP_GLOBAL_Control
0x18005261d  cmp     rcx, r8
0x180052620  jz      short loc_180052654
0x180052622  test    [rcx+1Ch], r15d
0x180052626  jz      short loc_180052654
0x180052628  cmp     byte ptr [rcx+19h], 5
0x18005262c  jb      short loc_180052654
0x18005262e  mov     rcx, [rcx+10h]
0x180052632  lea     edx, [r12+2Bh]
0x180052637  mov     r9d, r14d
0x18005263a  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052641  call    WPP_SF_d
0x180052646  mov     rcx, cs:WPP_GLOBAL_Control
0x18005264d  lea     r8, WPP_GLOBAL_Control
0x180052654  test    r14d, r14d
0x180052657  jnz     short loc_18005268F
0x180052659  cmp     rcx, r8
0x18005265c  jz      loc_1800529ED
0x180052662  test    [rcx+1Ch], r15d
0x180052666  jz      loc_1800529C4
0x18005266c  cmp     byte ptr [rcx+19h], 5
0x180052670  jb      loc_1800529C4
0x180052676  mov     rcx, [rcx+10h]
0x18005267a  lea     edx, [r14+2Ch]
0x18005267e  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052685  call    WPP_SF_
0x18005268a  jmp     loc_1800529B6
0x18005268f  mov     r12, rsi
0x180052692  add     r12, rbx
0x180052695  jz      loc_1800528EB
0x18005269b  lea     rdx, [r14+r14*8]
0x18005269f  mov     eax, 0FFFFFFFFh
0x1800526a4  shl     rdx, 2
0x1800526a8  cmp     rdx, rax
0x1800526ab  ja      loc_1800528EB
0x1800526b1  mov     rax, [rdi+390h]
0x1800526b8  cmp     [rax+30h], edx
0x1800526bb  jb      loc_1800528EB
0x1800526c1  xor     r15d, r15d
0x1800526c4  test    r14d, r14d
0x1800526c7  jz      loc_1800527BB
0x1800526cd  xor     esi, esi
0x1800526cf  lea     rax, [rsi+rsi*8]
0x1800526d3  lea     rbx, [r12+rax*4]
0x1800526d7  cmp     dword ptr [rbx+1Ch], 0
0x1800526db  jz      loc_1800527AC
0x1800526e1  cmp     dword ptr [rbx+20h], 0
0x1800526e5  jz      loc_1800527AC
0x1800526eb  mov     r9d, [rbx+4]
0x1800526ef  cmp     r9d, 2
0x1800526f3  jz      short loc_180052739
0x1800526f5  cmp     r9d, 17h
0x1800526f9  jz      short loc_180052739
0x1800526fb  lea     rax, WPP_GLOBAL_Control
0x180052702  cmp     rcx, rax
0x180052705  jz      loc_1800527AC
0x18005270b  test    dword ptr [rcx+1Ch], 2000h
0x180052712  jz      loc_1800527AC
0x180052718  cmp     byte ptr [rcx+19h], 4
0x18005271c  jb      loc_1800527AC
0x180052722  mov     rcx, [rcx+10h]
0x180052726  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005272d  mov     edx, 2Eh ; '.'
0x180052732  call    WPP_SF_d
0x180052737  jmp     short loc_1800527A5
0x180052739  mov     r9d, [rdi+354h]
0x180052740  lea     rcx, [rsp+500h+Row]; void *
0x180052745  xor     r8d, r8d
0x180052748  mov     rdx, rbx
0x18005274b  call    CreateRouteEntry
0x180052750  mov     eax, [rbx+20h]
0x180052753  lea     rcx, [rsp+500h+Row]; Row
0x180052758  mov     [rsp+500h+Row.InterfaceIndex], eax
0x18005275c  call    cs:__imp_DeleteIpForwardEntry2
0x180052762  test    eax, eax
0x180052764  jz      short loc_1800527A5
0x180052766  mov     rcx, cs:WPP_GLOBAL_Control
0x18005276d  lea     rdx, WPP_GLOBAL_Control
0x180052774  cmp     rcx, rdx
0x180052777  jz      short loc_1800527AC
0x180052779  test    dword ptr [rcx+1Ch], 2000h
0x180052780  jz      short loc_1800527AC
0x180052782  cmp     byte ptr [rcx+19h], 2
0x180052786  jb      short loc_1800527AC
0x180052788  mov     r9d, [rbx+20h]
0x18005278c  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052793  mov     rcx, [rcx+10h]
0x180052797  mov     edx, 2Fh ; '/'
0x18005279c  mov     dword ptr [rsp+500h+var_4E0], eax
0x1800527a0  call    WPP_SF_qD
0x1800527a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800527ac  inc     r15d
0x1800527af  inc     rsi
0x1800527b2  cmp     r15d, r14d
0x1800527b5  jb      loc_1800526CF
0x1800527bb  mov     r15d, 2000h
0x1800527c1  mov     [rsp+500h+var_4D8], 0; LPDWORD
0x1800527ca  lea     r9, [rsp+500h+var_4D0]; LPDWORD
0x1800527cf  xor     r8d, r8d; struct tagRASENTRYW *
0x1800527d2  mov     [rsp+500h+var_4E0], 0; LPBYTE
0x1800527db  lea     rdx, [rbp+400h+var_450]; LPCWSTR
0x1800527df  lea     rcx, [rbp+400h+WideCharStr]; LPCWSTR
0x1800527e6  call    cs:__imp_RasGetEntryPropertiesW
0x1800527ec  cmp     eax, 25Bh
0x1800527f1  jnz     loc_1800529B6
0x1800527f7  mov     edx, [rsp+500h+var_4D0]; dwBytes
0x1800527fb  mov     ecx, 40h ; '@'; uFlags
0x180052800  call    cs:__imp_GlobalAlloc
0x180052806  mov     [rsp+500h+var_4C8], rax
0x18005280b  mov     rbx, rax
0x18005280e  test    rax, rax
0x180052811  jz      loc_1800529B6
0x180052817  mov     eax, [rsp+500h+var_4D0]
0x18005281b  lea     r9, [rsp+500h+var_4D0]; LPDWORD
0x180052820  mov     [rsp+500h+var_4D8], 0; LPDWORD
0x180052829  lea     rdx, [rbp+400h+var_450]; LPCWSTR
0x18005282d  mov     r8, rbx; struct tagRASENTRYW *
0x180052830  mov     [rbx], eax
0x180052832  lea     rcx, [rbp+400h+WideCharStr]; LPCWSTR
0x180052839  mov     [rsp+500h+var_4E0], 0; LPBYTE
0x180052842  call    cs:__imp_RasGetEntryPropertiesW
0x180052848  test    eax, eax
0x18005284a  jnz     loc_1800529AD
0x180052850  cmp     [rbx+0FD0h], eax
0x180052856  jge     loc_1800529AD
0x18005285c  cmp     qword ptr [rdi+3B0h], 0
0x180052864  jz      loc_1800529AD
0x18005286a  mov     eax, [rdi+3B8h]
0x180052870  test    eax, eax
0x180052872  jz      loc_1800529AD
0x180052878  xor     esi, esi
0x18005287a  test    eax, eax
0x18005287c  jz      loc_1800529AD
0x180052882  mov     rcx, cs:WPP_GLOBAL_Control
0x180052889  lea     rbx, WPP_GLOBAL_Control
0x180052890  lea     r14, [rsi+rsi*8]
0x180052894  cmp     dword ptr [r12+r14*4+4], 2
0x18005289a  jz      loc_180052926
0x1800528a0  cmp     dword ptr [r12+r14*4+4], 17h
0x1800528a6  jz      short loc_180052926
0x1800528a8  cmp     rcx, rbx
0x1800528ab  jz      loc_18005299A
0x1800528b1  test    [rcx+1Ch], r15d
0x1800528b5  jz      loc_18005299A
0x1800528bb  cmp     byte ptr [rcx+19h], 4
0x1800528bf  jb      loc_18005299A
0x1800528c5  mov     r9, [rdi+3B0h]
0x1800528cc  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800528d3  mov     rcx, [rcx+10h]
0x1800528d7  mov     edx, 30h ; '0'
0x1800528dc  mov     r9d, [r9+r14*4+4]
0x1800528e1  call    WPP_SF_d
0x1800528e6  jmp     loc_180052993
0x1800528eb  cmp     rcx, r8
0x1800528ee  jz      loc_1800529ED
0x1800528f4  test    [rcx+1Ch], r15d
0x1800528f8  jz      loc_1800529C4
0x1800528fe  cmp     byte ptr [rcx+19h], 5
0x180052902  jb      loc_1800529C4
0x180052908  mov     rcx, [rcx+10h]
0x18005290c  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052913  mov     edx, 2Dh ; '-'
0x180052918  lea     r9d, [rdx+42h]
0x18005291c  call    WPP_SF_d
0x180052921  jmp     loc_1800529B6
0x180052926  mov     rax, [rdi+3B0h]
0x18005292d  lea     rcx, [rsp+500h+Row]; void *
0x180052932  mov     r9d, [rdi+354h]
0x180052939  xor     r8d, r8d
0x18005293c  lea     rdx, [rax+r14*4]
0x180052940  call    CreateRouteEntry
0x180052945  mov     eax, [r12+r14*4+20h]
0x18005294a  lea     rcx, [rsp+500h+Row]; Row
0x18005294f  mov     [rsp+500h+Row.InterfaceIndex], eax
0x180052953  call    cs:__imp_DeleteIpForwardEntry2
0x180052959  test    eax, eax
0x18005295b  jz      short loc_180052993
0x18005295d  mov     rcx, cs:WPP_GLOBAL_Control
0x180052964  cmp     rcx, rbx
0x180052967  jz      short loc_18005299A
0x180052969  test    [rcx+1Ch], r15d
0x18005296d  jz      short loc_18005299A
0x18005296f  cmp     byte ptr [rcx+19h], 2
0x180052973  jb      short loc_18005299A
0x180052975  mov     r9d, [r12+r14*4+20h]
0x18005297a  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052981  mov     rcx, [rcx+10h]
0x180052985  mov     edx, 31h ; '1'
0x18005298a  mov     dword ptr [rsp+500h+var_4E0], eax
0x18005298e  call    WPP_SF_qD
0x180052993  mov     rcx, cs:WPP_GLOBAL_Control
0x18005299a  inc     esi
0x18005299c  cmp     esi, [rdi+3B8h]
0x1800529a2  jb      loc_180052890
0x1800529a8  mov     rbx, [rsp+500h+var_4C8]
0x1800529ad  mov     rcx, rbx; hMem
0x1800529b0  call    cs:__imp_GlobalFree
0x1800529b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800529bd  lea     r8, WPP_GLOBAL_Control
0x1800529c4  cmp     rcx, r8
0x1800529c7  jz      short loc_1800529ED
0x1800529c9  test    [rcx+1Ch], r15d
0x1800529cd  jz      short loc_1800529ED
0x1800529cf  cmp     byte ptr [rcx+19h], 6
0x1800529d3  jb      short loc_1800529ED
0x1800529d5  mov     rcx, [rcx+10h]
0x1800529d9  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800529e0  mov     edx, 32h ; '2'
0x1800529e5  xor     r9d, r9d
0x1800529e8  call    WPP_SF_d
0x1800529ed  xor     eax, eax
0x1800529ef  mov     rcx, [rbp+400h+var_30]
0x1800529f6  xor     rcx, rsp; StackCookie
0x1800529f9  call    __security_check_cookie
0x1800529fe  lea     r11, [rsp+500h+var_20]
0x180052a06  mov     rbx, [r11+38h]
0x180052a0a  mov     rsi, [r11+40h]
0x180052a0e  mov     rsp, r11
0x180052a11  pop     r15
0x180052a13  pop     r14
0x180052a15  pop     r12
0x180052a17  pop     rdi
0x180052a18  pop     rbp
0x180052a19  retn
```
