# AppInfoCallback::NextAppEntry(WPN_APPDB_APP_ENTRY *)

- ea: `0x18007b3a0`
- end: `0x18007b599`
- name: `?NextAppEntry@AppInfoCallback@@UEAAJPEAUWPN_APPDB_APP_ENTRY@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(AppInfoCallback *__hidden this, struct WPN_APPDB_APP_ENTRY *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002ee38`
- `0x18002fae0`
- `0x18007b3a0`
- `0x1800a6570`
- `0x1800af0a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b3e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007b3e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b3d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b56c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b3d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b56c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b57a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b57a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b547`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b55e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b547`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b55e`

## pseudocode

```c
__int64 __fastcall AppInfoCallback::NextAppEntry(AppInfoCallback *this, struct WPN_APPDB_APP_ENTRY *a2)
{
  unsigned int v2; // edi
  HANDLE ProcessHeap; // rax
  unsigned __int16 **v7; // rax
  __int64 v8; // r8
  unsigned __int16 **v9; // rbx
  AppInfoCallback **v10; // rcx
  int v11; // eax
  __int64 v12; // r8
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rcx
  int v16; // eax
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // rcx
  HANDLE v19; // rax
  int v20; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = 0;
  if ( (*((_DWORD *)this + 4) & *((_DWORD *)a2 + 12)) == 0
    || !SettingsEndpointImpl::IsAppInPackage(*((LPCWCH *)this + 6), *((const unsigned __int16 **)a2 + 4)) )
  {
    return v2;
  }
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned __int16 **)HeapAlloc(ProcessHeap, 8u, 0x28u);
  v9 = v7;
  if ( !v7 )
  {
    v2 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x713,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
      (const char *)0x8007000ELL,
      v20);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids, 2147942414LL);
    return v2;
  }
  *((_DWORD *)v7 + 7) = *((_DWORD *)a2 + 12) & *((_DWORD *)this + 5);
  *((_DWORD *)v7 + 6) = *((_DWORD *)a2 + 12) & 0xF0000000;
  v11 = WpnCoTaskStrCpy(*((const unsigned __int16 **)a2 + 4), v7 + 2, v8);
  v2 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x71D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
      (const char *)(unsigned int)v11,
      v20);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_20;
    v14 = 103;
LABEL_19:
    WPP_SF_d(v13[2], v14, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids, v2);
LABEL_20:
    v17 = v9[2];
    if ( v17 )
    {
      CoTaskMemFree(v17);
      v9[2] = 0;
    }
    v18 = v9[4];
    if ( v18 )
    {
      CoTaskMemFree(v18);
      v9[4] = 0;
    }
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v9);
    return v2;
  }
  v15 = (const unsigned __int16 *)*((_QWORD *)a2 + 74);
  if ( v15 )
  {
    v16 = WpnCoTaskStrCpy(v15, v9 + 4, v12);
    v2 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x724,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
        (const char *)(unsigned int)v16,
        v20);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_20;
      v14 = 104;
      goto LABEL_19;
    }
  }
  else
  {
    v9[4] = 0;
  }
  v10 = (AppInfoCallback **)*((_QWORD *)this + 4);
  if ( *v10 != (AppInfoCallback *)((char *)this + 24) )
    __fastfail(3u);
  *v9 = (unsigned __int16 *)((char *)this + 24);
  v9[1] = (unsigned __int16 *)v10;
  *v10 = (AppInfoCallback *)v9;
  *((_QWORD *)this + 4) = v9;
  ++*((_DWORD *)this + 10);
  return v2;
}

```

## disassembly

```asm
0x18007b3a0  push    rbx
0x18007b3a2  push    rbp
0x18007b3a3  push    rsi
0x18007b3a4  push    rdi
0x18007b3a5  sub     rsp, 28h
0x18007b3a9  mov     eax, [rcx+10h]
0x18007b3ac  xor     edi, edi
0x18007b3ae  mov     rbp, rdx
0x18007b3b1  mov     rsi, rcx
0x18007b3b4  test    [rdx+30h], eax
0x18007b3b7  jnz     short loc_18007B3C4
0x18007b3b9  mov     eax, edi
0x18007b3bb  add     rsp, 28h
0x18007b3bf  pop     rdi
0x18007b3c0  pop     rsi
0x18007b3c1  pop     rbp
0x18007b3c2  pop     rbx
0x18007b3c3  retn
0x18007b3c4  mov     rdx, [rdx+20h]; unsigned __int16 *
0x18007b3c8  mov     rcx, [rcx+30h]; lpString1
0x18007b3cc  call    ?IsAppInPackage@SettingsEndpointImpl@@SA_NPEBG0@Z; SettingsEndpointImpl::IsAppInPackage(ushort const *,ushort const *)
0x18007b3d1  test    al, al
0x18007b3d3  jz      short loc_18007B3B9
0x18007b3d5  call    cs:__imp_GetProcessHeap
0x18007b3db  mov     edx, 8; dwFlags
0x18007b3e0  mov     rcx, rax; hHeap
0x18007b3e3  lea     r8d, [rdx+20h]; dwBytes
0x18007b3e7  call    cs:__imp_HeapAlloc
0x18007b3ed  mov     rbx, rax
0x18007b3f0  test    rax, rax
0x18007b3f3  jnz     short loc_18007B471
0x18007b3f5  mov     rcx, [rsp+48h]; this
0x18007b3fa  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007b401  mov     edi, 8007000Eh
0x18007b406  mov     edx, 713h; void *
0x18007b40b  mov     r9d, edi; char *
0x18007b40e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007b413  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b41a  lea     rax, WPP_GLOBAL_Control
0x18007b421  cmp     rcx, rax
0x18007b424  jz      short loc_18007B3B9
0x18007b426  test    byte ptr [rcx+1Ch], 80h
0x18007b42a  jz      short loc_18007B3B9
0x18007b42c  mov     rcx, [rcx+10h]
0x18007b430  lea     edx, [rbx+66h]
0x18007b433  mov     r9d, 8007000Eh
0x18007b439  lea     r8, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids
0x18007b440  call    WPP_SF_d
0x18007b445  jmp     loc_18007B3B9
0x18007b44a  lea     rax, [rsi+18h]
0x18007b44e  mov     rcx, [rax+8]
0x18007b452  cmp     [rcx], rax
0x18007b455  jnz     loc_18007B592
0x18007b45b  mov     [rbx], rax
0x18007b45e  mov     [rbx+8], rcx
0x18007b462  mov     [rcx], rbx
0x18007b465  mov     [rax+8], rbx
0x18007b469  inc     dword ptr [rsi+28h]
0x18007b46c  jmp     loc_18007B3B9
0x18007b471  lea     rdx, [rax+10h]; unsigned __int16 **
0x18007b475  mov     eax, [rsi+14h]
0x18007b478  and     eax, [rbp+30h]
0x18007b47b  mov     [rdx+0Ch], eax
0x18007b47e  mov     eax, [rbp+30h]
0x18007b481  and     eax, 0F0000000h
0x18007b486  mov     [rbx+18h], eax
0x18007b489  mov     rcx, [rbp+20h]; unsigned __int16 *
0x18007b48d  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x18007b492  mov     edi, eax
0x18007b494  test    eax, eax
0x18007b496  jns     short loc_18007B4D1
0x18007b498  mov     rcx, [rsp+48h]; this
0x18007b49d  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007b4a4  mov     r9d, eax; char *
0x18007b4a7  mov     edx, 71Dh; void *
0x18007b4ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007b4b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b4b8  lea     rax, WPP_GLOBAL_Control
0x18007b4bf  cmp     rcx, rax
0x18007b4c2  jz      short loc_18007B53E
0x18007b4c4  test    byte ptr [rcx+1Ch], 80h
0x18007b4c8  jz      short loc_18007B53E
0x18007b4ca  mov     edx, 67h ; 'g'
0x18007b4cf  jmp     short loc_18007B52B
0x18007b4d1  mov     rcx, [rbp+250h]; unsigned __int16 *
0x18007b4d8  test    rcx, rcx
0x18007b4db  jz      loc_18007B585
0x18007b4e1  lea     rdx, [rbx+20h]; unsigned __int16 **
0x18007b4e5  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x18007b4ea  mov     edi, eax
0x18007b4ec  test    eax, eax
0x18007b4ee  jns     loc_18007B44A
0x18007b4f4  mov     rcx, [rsp+48h]; this
0x18007b4f9  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007b500  mov     r9d, eax; char *
0x18007b503  mov     edx, 724h; void *
0x18007b508  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007b50d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b514  lea     rax, WPP_GLOBAL_Control
0x18007b51b  cmp     rcx, rax
0x18007b51e  jz      short loc_18007B53E
0x18007b520  test    byte ptr [rcx+1Ch], 80h
0x18007b524  jz      short loc_18007B53E
0x18007b526  mov     edx, 68h ; 'h'
0x18007b52b  mov     rcx, [rcx+10h]
0x18007b52f  lea     r8, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids
0x18007b536  mov     r9d, edi
0x18007b539  call    WPP_SF_d
0x18007b53e  mov     rcx, [rbx+10h]; pv
0x18007b542  test    rcx, rcx
0x18007b545  jz      short loc_18007B555
0x18007b547  call    cs:__imp_CoTaskMemFree
0x18007b54d  mov     qword ptr [rbx+10h], 0
0x18007b555  mov     rcx, [rbx+20h]; pv
0x18007b559  test    rcx, rcx
0x18007b55c  jz      short loc_18007B56C
0x18007b55e  call    cs:__imp_CoTaskMemFree
0x18007b564  mov     qword ptr [rbx+20h], 0
0x18007b56c  call    cs:__imp_GetProcessHeap
0x18007b572  mov     r8, rbx; lpMem
0x18007b575  xor     edx, edx; dwFlags
0x18007b577  mov     rcx, rax; hHeap
0x18007b57a  call    cs:__imp_HeapFree
0x18007b580  jmp     loc_18007B3B9
0x18007b585  mov     qword ptr [rbx+20h], 0
0x18007b58d  jmp     loc_18007B44A
0x18007b592  mov     ecx, 3
0x18007b597  int     29h; Win8: RtlFailFast(ecx)
```
