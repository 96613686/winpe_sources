# WcnGetLastFcDirectory(ushort *,ulong)

- ea: `0x1800795fc`
- end: `0x180079725`
- name: `?WcnGetLastFcDirectory@@YAJPEAGK@Z`
- size: `297`
- prototype: `__int64 __fastcall(wchar_t *Buffer)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180079864`

## callees

- `0x180004adc`
- `0x18001d4d4`
- `0x180076f84`
- `0x180076fe0`
- `0x1800795fc`
- `0x180088304`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800796d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800796d2`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180079664`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180079664`

## string_xrefs

- `0x1800796a2`: `%s\Microsoft\LastFlashConfig.wfc`

## pseudocode

```c
__int64 __fastcall WcnGetLastFcDirectory(wchar_t *Buffer)
{
  const char *Indent; // rax
  __int64 v3; // r10
  HRESULT v4; // eax
  int v5; // ebx
  PVOID *v6; // r10
  unsigned int v7; // eax
  __int64 v8; // r10
  PWSTR ppszPath; // [rsp+50h] [rbp+18h] BYREF

  ppszPath = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 24, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, Indent);
  }
  v4 = SHGetKnownFolderPath(&FOLDERID_RoamingAppData, 0, 0, &ppszPath);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( swprintf_s(Buffer, 0x104u, L"%s\\Microsoft\\LastFlashConfig.wfc", ppszPath) == -1 )
      v5 = -2147418113;
    goto LABEL_10;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, (unsigned int)v4);
LABEL_10:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( ppszPath )
  {
    CoTaskMemFree(ppszPath);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (v5 < 0 || *((_BYTE *)v6 + 25) >= 6u) )
  {
    v7 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v8 + 16), 26, (unsigned int)WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, v7, v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800795fc  mov     [rsp+arg_0], rbx
0x180079601  mov     [rsp+arg_8], rsi
0x180079606  push    rdi
0x180079607  sub     rsp, 30h
0x18007960b  mov     rdi, rcx
0x18007960e  mov     [rsp+38h+ppszPath], 0
0x180079617  mov     r10, cs:WPP_GLOBAL_Control
0x18007961e  lea     rsi, WPP_GLOBAL_Control
0x180079625  cmp     r10, rsi
0x180079628  jz      short loc_180079653
0x18007962a  cmp     byte ptr [r10+19h], 6
0x18007962f  jb      short loc_180079653
0x180079631  mov     ecx, 1; int
0x180079636  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18007963b  mov     rcx, [r10+10h]
0x18007963f  lea     r8, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180079646  mov     edx, 18h
0x18007964b  mov     r9, rax
0x18007964e  call    WPP_SF_s
0x180079653  lea     r9, [rsp+38h+ppszPath]; ppszPath
0x180079658  xor     r8d, r8d; hToken
0x18007965b  xor     edx, edx; dwFlags
0x18007965d  lea     rcx, FOLDERID_RoamingAppData; rfid
0x180079664  call    cs:__imp_SHGetKnownFolderPath
0x18007966a  mov     ebx, eax
0x18007966c  test    eax, eax
0x18007966e  jns     short loc_18007969D
0x180079670  mov     r10, cs:WPP_GLOBAL_Control
0x180079677  cmp     r10, rsi
0x18007967a  jz      short loc_1800796C8
0x18007967c  cmp     byte ptr [r10+19h], 2
0x180079681  jb      short loc_1800796C8
0x180079683  mov     rcx, [r10+10h]
0x180079687  lea     r8, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x18007968e  mov     edx, 19h
0x180079693  mov     r9d, eax
0x180079696  call    WPP_SF_d
0x18007969b  jmp     short loc_1800796C1
0x18007969d  mov     r9, [rsp+38h+ppszPath]
0x1800796a2  lea     r8, aSMicrosoftLast; "%s\\Microsoft\\LastFlashConfig.wfc"
0x1800796a9  mov     edx, 104h; BufferCount
0x1800796ae  mov     rcx, rdi; Buffer
0x1800796b1  call    swprintf_s
0x1800796b6  cmp     eax, 0FFFFFFFFh
0x1800796b9  mov     ecx, 8000FFFFh
0x1800796be  cmovz   ebx, ecx
0x1800796c1  mov     r10, cs:WPP_GLOBAL_Control
0x1800796c8  mov     rcx, [rsp+38h+ppszPath]; pv
0x1800796cd  test    rcx, rcx
0x1800796d0  jz      short loc_1800796DF
0x1800796d2  call    cs:__imp_CoTaskMemFree
0x1800796d8  mov     r10, cs:WPP_GLOBAL_Control
0x1800796df  cmp     r10, rsi
0x1800796e2  jz      short loc_180079713
0x1800796e4  test    ebx, ebx
0x1800796e6  js      short loc_1800796EF
0x1800796e8  cmp     byte ptr [r10+19h], 6
0x1800796ed  jb      short loc_180079713
0x1800796ef  or      ecx, 0FFFFFFFFh; int
0x1800796f2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800796f7  mov     rcx, [r10+10h]
0x1800796fb  lea     r8, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180079702  mov     edx, 1Ah
0x180079707  mov     [rsp+38h+var_18], ebx
0x18007970b  mov     r9, rax
0x18007970e  call    WPP_SF_sd
0x180079713  mov     rsi, [rsp+38h+arg_8]
0x180079718  mov     eax, ebx
0x18007971a  mov     rbx, [rsp+38h+arg_0]
0x18007971f  add     rsp, 30h
0x180079723  pop     rdi
0x180079724  retn
```
