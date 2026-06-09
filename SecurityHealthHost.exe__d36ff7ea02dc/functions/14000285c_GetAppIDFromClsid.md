# GetAppIDFromClsid

- ea: `0x14000285c`
- end: `0x140002a8e`
- name: `GetAppIDFromClsid`
- size: `562`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPIID lpiid, __int64, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140002a94`

## callees

- `0x140001614`
- `0x14000285c`
- `0x140003040`
- `0x14000de38`
- `0x14000e47c`
- `0x14000e948`

## import_xrefs

- `ole32!IIDFromString` at `0x1400029e6`
- `ole32!IIDFromString` at `0x1400029e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002933`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002a39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002a66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002933`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002a39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002a66`

## string_xrefs

- `0x14000287f`: `CLSID\%s`

## pseudocode

```c
__int64 __fastcall GetAppIDFromClsid(unsigned __int16 *a1, LPIID lpiid, __int64 a3, char *a4)
{
  int v5; // eax
  HKEY *v6; // rdx
  const unsigned __int16 *v7; // r9
  unsigned int v8; // ebx
  HKEY v10; // rbx
  int v11; // eax
  HKEY v12; // rdx
  const unsigned __int16 *v13; // r8
  int ValueAlloc; // edi
  HKEY v15; // rcx
  HKEY v16; // rsi
  CommonUtil *v17; // rcx
  HKEY v18; // rdi
  HRESULT v19; // eax
  unsigned int v20; // r14d
  unsigned int v21[4]; // [rsp+40h] [rbp-10h] BYREF
  HKEY v22; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  v22 = 0;
  v5 = CommonUtil::NewSprintfW((CommonUtil *)&v22, (unsigned __int16 **)L"CLSID\\%s", a1, a4);
  v8 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_76cadd58faaf347d002667510d93f4e0_Traceguids,
        (unsigned int)v5);
    if ( v22 )
      operator delete(v22);
    return v8;
  }
  v10 = v22;
  hKey = 0;
  v11 = CommonUtil::UtilRegOpenKey((CommonUtil *)&hKey, v6, (const WCHAR *)v22, v7);
  ValueAlloc = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_76cadd58faaf347d002667510d93f4e0_Traceguids,
        (unsigned int)v11);
    v15 = hKey;
    if ( !hKey )
      goto LABEL_14;
    goto LABEL_13;
  }
  v16 = hKey;
  LODWORD(v22) = 0;
  v17 = (CommonUtil *)hKey;
  *(_QWORD *)v21 = 0;
  hKey = 0;
  ValueAlloc = CommonUtil::UtilRegGetValueAlloc(v17, v12, v13, (DWORD *)&v22, v21, (unsigned __int64 *)&hKey);
  if ( ValueAlloc < 0 )
  {
    if ( hKey )
      operator delete(hKey);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_76cadd58faaf347d002667510d93f4e0_Traceguids,
        (unsigned int)ValueAlloc);
    if ( !v16 )
      goto LABEL_14;
    v15 = v16;
LABEL_13:
    RegCloseKey(v15);
LABEL_14:
    if ( v10 )
      operator delete(v10);
    return (unsigned int)ValueAlloc;
  }
  v18 = hKey;
  v19 = IIDFromString((LPCOLESTR)hKey, lpiid);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( v18 )
      operator delete(v18);
    if ( v16 )
      RegCloseKey(v16);
    if ( v10 )
      operator delete(v10);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_76cadd58faaf347d002667510d93f4e0_Traceguids,
        (unsigned int)v19);
    if ( v18 )
      operator delete(v18);
    if ( v16 )
      RegCloseKey(v16);
    if ( v10 )
      operator delete(v10);
    return v20;
  }
}

```

## disassembly

```asm
0x14000285c  mov     [rsp-18h+arg_0], rbx
0x140002861  mov     [rsp-18h+arg_8], rsi
0x140002866  push    rbp
0x140002867  push    rdi
0x140002868  push    r14
0x14000286a  mov     rbp, rsp
0x14000286d  sub     rsp, 50h
0x140002871  mov     r14, rdx
0x140002874  mov     [rbp+arg_10], 0
0x14000287c  mov     r8, rcx; unsigned __int16 *
0x14000287f  lea     rdx, aClsidS; "CLSID\\%s"
0x140002886  lea     rcx, [rbp+arg_10]; this
0x14000288a  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x14000288f  mov     ebx, eax
0x140002891  test    eax, eax
0x140002893  jns     short loc_1400028DB
0x140002895  mov     rcx, cs:WPP_GLOBAL_Control
0x14000289c  lea     rdx, WPP_GLOBAL_Control
0x1400028a3  cmp     rcx, rdx
0x1400028a6  jz      short loc_1400028C6
0x1400028a8  test    byte ptr [rcx+1Ch], 1
0x1400028ac  jz      short loc_1400028C6
0x1400028ae  mov     rcx, [rcx+10h]
0x1400028b2  lea     r8, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids
0x1400028b9  mov     edx, 0Ah
0x1400028be  mov     r9d, eax
0x1400028c1  call    WPP_SF_d
0x1400028c6  mov     rcx, [rbp+arg_10]; void *
0x1400028ca  test    rcx, rcx
0x1400028cd  jz      short loc_1400028D4
0x1400028cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400028d4  mov     eax, ebx
0x1400028d6  jmp     loc_140002A7B
0x1400028db  mov     rbx, [rbp+arg_10]
0x1400028df  lea     rcx, [rbp+hKey]; this
0x1400028e3  mov     r8, rbx; HKEY
0x1400028e6  mov     [rbp+hKey], 0
0x1400028ee  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)
0x1400028f3  mov     edi, eax
0x1400028f5  test    eax, eax
0x1400028f7  jns     short loc_14000294D
0x1400028f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140002900  lea     rdx, WPP_GLOBAL_Control
0x140002907  cmp     rcx, rdx
0x14000290a  jz      short loc_14000292A
0x14000290c  test    byte ptr [rcx+1Ch], 1
0x140002910  jz      short loc_14000292A
0x140002912  mov     rcx, [rcx+10h]
0x140002916  lea     r8, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids
0x14000291d  mov     edx, 0Bh
0x140002922  mov     r9d, eax
0x140002925  call    WPP_SF_d
0x14000292a  mov     rcx, [rbp+hKey]; hKey
0x14000292e  test    rcx, rcx
0x140002931  jz      short loc_140002939
0x140002933  call    cs:__imp_RegCloseKey
0x140002939  test    rbx, rbx
0x14000293c  jz      short loc_140002946
0x14000293e  mov     rcx, rbx; void *
0x140002941  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002946  mov     eax, edi
0x140002948  jmp     loc_140002A7B
0x14000294d  mov     rsi, [rbp+hKey]
0x140002951  lea     rax, [rbp+hKey]
0x140002955  mov     [rsp+50h+var_28], rax; unsigned __int64 *
0x14000295a  lea     r9, [rbp+arg_10]; unsigned int
0x14000295e  lea     rax, [rbp+var_10]
0x140002962  mov     dword ptr [rbp+arg_10], 0
0x140002969  mov     rcx, rsi; this
0x14000296c  mov     [rsp+50h+var_30], rax; unsigned int *
0x140002971  mov     qword ptr [rbp+var_10], 0
0x140002979  mov     [rbp+hKey], 0
0x140002981  call    ?UtilRegGetValueAlloc@CommonUtil@@YAJPEAUHKEY__@@PEBGKPEAKPEA_KPEAPEAE_K@Z; CommonUtil::UtilRegGetValueAlloc(HKEY__ *,ushort const *,ulong,ulong *,unsigned __int64 *,uchar * *,unsigned __int64)
0x140002986  mov     edi, eax
0x140002988  test    eax, eax
0x14000298a  jns     short loc_1400029DC
0x14000298c  mov     rcx, [rbp+hKey]; void *
0x140002990  test    rcx, rcx
0x140002993  jz      short loc_14000299A
0x140002995  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000299a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029a1  lea     rdx, WPP_GLOBAL_Control
0x1400029a8  cmp     rcx, rdx
0x1400029ab  jz      short loc_1400029CB
0x1400029ad  test    byte ptr [rcx+1Ch], 1
0x1400029b1  jz      short loc_1400029CB
0x1400029b3  mov     rcx, [rcx+10h]
0x1400029b7  lea     r8, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids
0x1400029be  mov     edx, 0Ch
0x1400029c3  mov     r9d, edi
0x1400029c6  call    WPP_SF_d
0x1400029cb  test    rsi, rsi
0x1400029ce  jz      loc_140002939
0x1400029d4  mov     rcx, rsi
0x1400029d7  jmp     loc_140002933
0x1400029dc  mov     rdi, [rbp+hKey]
0x1400029e0  mov     rdx, r14; lpiid
0x1400029e3  mov     rcx, rdi; lpsz
0x1400029e6  call    cs:__imp_IIDFromString
0x1400029ec  mov     r14d, eax
0x1400029ef  test    eax, eax
0x1400029f1  jns     short loc_140002A51
0x1400029f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029fa  lea     rdx, WPP_GLOBAL_Control
0x140002a01  cmp     rcx, rdx
0x140002a04  jz      short loc_140002A24
0x140002a06  test    byte ptr [rcx+1Ch], 1
0x140002a0a  jz      short loc_140002A24
0x140002a0c  mov     rcx, [rcx+10h]
0x140002a10  lea     r8, WPP_76cadd58faaf347d002667510d93f4e0_Traceguids
0x140002a17  mov     edx, 0Dh
0x140002a1c  mov     r9d, eax
0x140002a1f  call    WPP_SF_d
0x140002a24  test    rdi, rdi
0x140002a27  jz      short loc_140002A31
0x140002a29  mov     rcx, rdi; void *
0x140002a2c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002a31  test    rsi, rsi
0x140002a34  jz      short loc_140002A3F
0x140002a36  mov     rcx, rsi; hKey
0x140002a39  call    cs:__imp_RegCloseKey
0x140002a3f  test    rbx, rbx
0x140002a42  jz      short loc_140002A4C
0x140002a44  mov     rcx, rbx; void *
0x140002a47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002a4c  mov     eax, r14d
0x140002a4f  jmp     short loc_140002A7B
0x140002a51  test    rdi, rdi
0x140002a54  jz      short loc_140002A5E
0x140002a56  mov     rcx, rdi; void *
0x140002a59  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002a5e  test    rsi, rsi
0x140002a61  jz      short loc_140002A6C
0x140002a63  mov     rcx, rsi; hKey
0x140002a66  call    cs:__imp_RegCloseKey
0x140002a6c  test    rbx, rbx
0x140002a6f  jz      short loc_140002A79
0x140002a71  mov     rcx, rbx; void *
0x140002a74  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140002a79  xor     eax, eax
0x140002a7b  mov     rbx, [rsp+50h+arg_0]
0x140002a80  mov     rsi, [rsp+50h+arg_8]
0x140002a85  add     rsp, 50h
0x140002a89  pop     r14
0x140002a8b  pop     rdi
0x140002a8c  pop     rbp
0x140002a8d  retn
```
