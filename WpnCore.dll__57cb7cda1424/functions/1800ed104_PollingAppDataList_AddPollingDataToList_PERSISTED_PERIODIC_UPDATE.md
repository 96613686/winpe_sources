# PollingAppDataList::AddPollingDataToList(_PERSISTED_PERIODIC_UPDATE *)

- ea: `0x1800ed104`
- end: `0x1800ed332`
- name: `?AddPollingDataToList@PollingAppDataList@@QEAAJPEAU_PERSISTED_PERIODIC_UPDATE@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(PollingAppDataList *__hidden this, struct _PERSISTED_PERIODIC_UPDATE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ed99c`

## callees

- `0x18002ee38`
- `0x18002fae0`
- `0x1800af0a4`
- `0x1800ed104`
- `0x1800ee394`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed16c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ed16c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ed158`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ed2d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ed158`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ed2d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ed2e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ed2e7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ed13a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ed13a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed2cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed2cb`

## pseudocode

```c
__int64 __fastcall PollingAppDataList::AddPollingDataToList(
        PollingAppDataList *this,
        struct _PERSISTED_PERIODIC_UPDATE *a2)
{
  _QWORD *v2; // rsi
  unsigned int i; // ebx
  PollingAppDataList *v6; // rcx
  unsigned int v7; // ebx
  _QWORD *v8; // rdi
  int v9; // ebp
  HANDLE ProcessHeap; // rax
  LPVOID v11; // rax
  __int64 v12; // r8
  int v13; // eax
  unsigned int v14; // r8d
  int v15; // eax
  void *v16; // rcx
  HANDLE v17; // rax
  PollingAppDataList **v18; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = *(_QWORD **)this;
  for ( i = 0; i < *((_DWORD *)this + 4); ++i )
  {
    if ( CompareStringOrdinal((LPCWCH)a2 + 40, -1, (LPCWCH)v2[2], -1, 1) == 2 )
    {
      v7 = 0;
      v8 = 0;
      v9 = 1;
LABEL_15:
      v14 = *((_DWORD *)v2 + 32);
      if ( v14 >= 5 && *((_DWORD *)a2 + 149) != 2 )
        return v7;
      v15 = PollingAppDataList::PopulateRoamingData(
              v6,
              a2,
              v14,
              (struct __MIDL___MIDL_itf_wpnplatform_0000_0029_0001 *)(v2 + 2));
      v7 = v15;
      if ( v15 >= 0 )
      {
        if ( *((_DWORD *)a2 + 149) == 1 )
          ++*((_DWORD *)v2 + 32);
        if ( !v9 )
        {
          v18 = (PollingAppDataList **)*((_QWORD *)this + 1);
          if ( *v18 != this )
            __fastfail(3u);
          *v2 = this;
          v2[1] = v18;
          *v18 = (PollingAppDataList *)v2;
          *((_QWORD *)this + 1) = v2;
          ++*((_DWORD *)this + 4);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x831,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
          (const char *)(unsigned int)v15,
          bIgnoreCase);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids, v7);
        if ( v8 )
          goto LABEL_22;
      }
      return v7;
    }
    v2 = (_QWORD *)*v2;
  }
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, 0x88u);
  v8 = v11;
  if ( v11 )
  {
    v13 = WpnCoTaskStrCpy((const unsigned __int16 *)a2 + 40, (unsigned __int16 **)v11 + 2, v12);
    v7 = v13;
    if ( v13 >= 0 )
    {
      v9 = 0;
      v2 = v8;
      goto LABEL_15;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x821,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids, v7);
LABEL_22:
    v16 = (void *)v8[2];
    if ( v16 )
    {
      CoTaskMemFree(v16);
      v8[2] = 0;
    }
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v8);
    return v7;
  }
  v7 = -2147024882;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x81D,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
    (const char *)0x8007000ELL,
    bIgnoreCase);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids, 2147942414LL);
  return v7;
}

```

## disassembly

```asm
0x1800ed104  push    rbx
0x1800ed106  push    rbp
0x1800ed107  push    rsi
0x1800ed108  push    rdi
0x1800ed109  push    r14
0x1800ed10b  push    r15
0x1800ed10d  sub     rsp, 38h
0x1800ed111  mov     rsi, [rcx]
0x1800ed114  xor     ebx, ebx
0x1800ed116  or      edi, 0FFFFFFFFh
0x1800ed119  mov     r15, rdx
0x1800ed11c  mov     r14, rcx
0x1800ed11f  cmp     ebx, [r14+10h]
0x1800ed123  jnb     short loc_1800ED158
0x1800ed125  mov     r8, [rsi+10h]; lpString2
0x1800ed129  lea     rcx, [r15+50h]; lpString1
0x1800ed12d  mov     r9d, edi; cchCount2
0x1800ed130  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x1800ed138  mov     edx, edi; cchCount1
0x1800ed13a  call    cs:__imp_CompareStringOrdinal
0x1800ed140  cmp     eax, 2
0x1800ed143  jz      short loc_1800ED14C
0x1800ed145  mov     rsi, [rsi]
0x1800ed148  inc     ebx
0x1800ed14a  jmp     short loc_1800ED11F
0x1800ed14c  xor     ebx, ebx
0x1800ed14e  xor     edi, edi
0x1800ed150  lea     ebp, [rbx+1]
0x1800ed153  jmp     loc_1800ED246
0x1800ed158  call    cs:__imp_GetProcessHeap
0x1800ed15e  mov     edx, 8; dwFlags
0x1800ed163  mov     r8d, 88h; dwBytes
0x1800ed169  mov     rcx, rax; hHeap
0x1800ed16c  call    cs:__imp_HeapAlloc
0x1800ed172  mov     rdi, rax
0x1800ed175  test    rax, rax
0x1800ed178  jnz     short loc_1800ED1D7
0x1800ed17a  mov     rcx, [rsp+68h]; this
0x1800ed17f  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ed186  mov     ebx, 8007000Eh
0x1800ed18b  mov     edx, 81Dh; void *
0x1800ed190  mov     r9d, ebx; char *
0x1800ed193  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ed198  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed19f  lea     rax, WPP_GLOBAL_Control
0x1800ed1a6  cmp     rcx, rax
0x1800ed1a9  jz      loc_1800ED323
0x1800ed1af  test    byte ptr [rcx+1Ch], 80h
0x1800ed1b3  jz      loc_1800ED323
0x1800ed1b9  mov     rcx, [rcx+10h]
0x1800ed1bd  lea     edx, [rdi+6Ch]
0x1800ed1c0  mov     r9d, 8007000Eh
0x1800ed1c6  lea     r8, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids
0x1800ed1cd  call    WPP_SF_d
0x1800ed1d2  jmp     loc_1800ED323
0x1800ed1d7  lea     rdx, [rax+10h]; unsigned __int16 **
0x1800ed1db  lea     rcx, [r15+50h]; unsigned __int16 *
0x1800ed1df  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x1800ed1e4  mov     ebx, eax
0x1800ed1e6  test    eax, eax
0x1800ed1e8  jns     short loc_1800ED241
0x1800ed1ea  mov     rcx, [rsp+68h]; this
0x1800ed1ef  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ed1f6  mov     r9d, eax; char *
0x1800ed1f9  mov     edx, 821h; void *
0x1800ed1fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ed203  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed20a  lea     rax, WPP_GLOBAL_Control
0x1800ed211  cmp     rcx, rax
0x1800ed214  jz      loc_1800ED2C2
0x1800ed21a  test    byte ptr [rcx+1Ch], 80h
0x1800ed21e  jz      loc_1800ED2C2
0x1800ed224  mov     rcx, [rcx+10h]
0x1800ed228  lea     r8, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids
0x1800ed22f  mov     edx, 6Dh ; 'm'
0x1800ed234  mov     r9d, ebx
0x1800ed237  call    WPP_SF_d
0x1800ed23c  jmp     loc_1800ED2C2
0x1800ed241  xor     ebp, ebp
0x1800ed243  mov     rsi, rdi
0x1800ed246  mov     r8d, [rsi+80h]; unsigned int
0x1800ed24d  cmp     r8d, 5
0x1800ed251  jb      short loc_1800ED261
0x1800ed253  cmp     dword ptr [r15+254h], 2
0x1800ed25b  jnz     loc_1800ED323
0x1800ed261  lea     r9, [rsi+10h]; struct __MIDL___MIDL_itf_wpnplatform_0000_0029_0001 *
0x1800ed265  mov     rdx, r15; struct _PERSISTED_PERIODIC_UPDATE *
0x1800ed268  call    ?PopulateRoamingData@PollingAppDataList@@AEAAJQEAU_PERSISTED_PERIODIC_UPDATE@@IPEAU__MIDL___MIDL_itf_wpnplatform_0000_0029_0001@@@Z; PollingAppDataList::PopulateRoamingData(_PERSISTED_PERIODIC_UPDATE * const,uint,__MIDL___MIDL_itf_wpnplatform_0000_0029_0001 *)
0x1800ed26d  mov     ebx, eax
0x1800ed26f  test    eax, eax
0x1800ed271  jns     short loc_1800ED2EF
0x1800ed273  mov     rcx, [rsp+68h]; this
0x1800ed278  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ed27f  mov     r9d, eax; char *
0x1800ed282  mov     edx, 831h; void *
0x1800ed287  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ed28c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed293  lea     rax, WPP_GLOBAL_Control
0x1800ed29a  cmp     rcx, rax
0x1800ed29d  jz      short loc_1800ED2BD
0x1800ed29f  test    byte ptr [rcx+1Ch], 80h
0x1800ed2a3  jz      short loc_1800ED2BD
0x1800ed2a5  mov     rcx, [rcx+10h]
0x1800ed2a9  lea     r8, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids
0x1800ed2b0  mov     edx, 6Eh ; 'n'
0x1800ed2b5  mov     r9d, ebx
0x1800ed2b8  call    WPP_SF_d
0x1800ed2bd  test    rdi, rdi
0x1800ed2c0  jz      short loc_1800ED323
0x1800ed2c2  mov     rcx, [rdi+10h]; pv
0x1800ed2c6  test    rcx, rcx
0x1800ed2c9  jz      short loc_1800ED2D9
0x1800ed2cb  call    cs:__imp_CoTaskMemFree
0x1800ed2d1  mov     qword ptr [rdi+10h], 0
0x1800ed2d9  call    cs:__imp_GetProcessHeap
0x1800ed2df  mov     r8, rdi; lpMem
0x1800ed2e2  xor     edx, edx; dwFlags
0x1800ed2e4  mov     rcx, rax; hHeap
0x1800ed2e7  call    cs:__imp_HeapFree
0x1800ed2ed  jmp     short loc_1800ED323
0x1800ed2ef  cmp     dword ptr [r15+254h], 1
0x1800ed2f7  jnz     short loc_1800ED2FF
0x1800ed2f9  inc     dword ptr [rsi+80h]
0x1800ed2ff  test    ebp, ebp
0x1800ed301  jnz     short loc_1800ED323
0x1800ed303  mov     rax, [r14+8]
0x1800ed307  cmp     [rax], r14
0x1800ed30a  jz      short loc_1800ED311
0x1800ed30c  lea     ecx, [rbp+3]
0x1800ed30f  int     29h; Win8: RtlFailFast(ecx)
0x1800ed311  mov     [rsi], r14
0x1800ed314  mov     [rsi+8], rax
0x1800ed318  mov     [rax], rsi
0x1800ed31b  mov     [r14+8], rsi
0x1800ed31f  inc     dword ptr [r14+10h]
0x1800ed323  mov     eax, ebx
0x1800ed325  add     rsp, 38h
0x1800ed329  pop     r15
0x1800ed32b  pop     r14
0x1800ed32d  pop     rdi
0x1800ed32e  pop     rsi
0x1800ed32f  pop     rbp
0x1800ed330  pop     rbx
0x1800ed331  retn
```
