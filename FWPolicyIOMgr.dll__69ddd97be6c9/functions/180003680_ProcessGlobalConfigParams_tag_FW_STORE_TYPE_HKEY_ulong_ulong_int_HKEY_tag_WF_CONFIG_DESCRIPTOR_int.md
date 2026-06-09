# ProcessGlobalConfigParams(_tag_FW_STORE_TYPE,HKEY__ *,ulong,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *,int)

- ea: `0x180003680`
- end: `0x180003a09`
- name: `?ProcessGlobalConfigParams@@YAJW4_tag_FW_STORE_TYPE@@PEAUHKEY__@@KKHPEAPEAU2@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@H@Z`
- size: `905`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, unsigned int, int, _QWORD *, __int64, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800032b0`
- `0x180030160`

## callees

- `0x180001cdc`
- `0x180003680`
- `0x180004238`
- `0x1800042c4`
- `0x18001e9ac`
- `0x18001f650`

## import_xrefs

- `fwbase!FwRegOpenKey` at `0x180003770`
- `fwbase!FwRegOpenKey` at `0x18000398a`
- `fwbase!FwRegOpenKey` at `0x180003770`
- `fwbase!FwRegOpenKey` at `0x18000398a`
- `fwbase!FwRegCloseKey` at `0x18000382d`
- `fwbase!FwRegCloseKey` at `0x18000382d`
- `fwbase!FwRegCreateKey` at `0x180003894`
- `fwbase!FwRegCreateKey` at `0x180003894`

## string_xrefs

- `0x1800038c6`: `FwRegCreateKey`
- `0x1800038d4`: `FwRegOpenKey`

## pseudocode

```c
__int64 __fastcall ProcessGlobalConfigParams(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        _QWORD *a6,
        __int64 a7,
        int a8)
{
  __int64 v10; // rbx
  __int64 v11; // rdi
  struct _tag_WF_CONFIG_DESCRIPTOR near **v12; // rax
  __int64 v13; // rcx
  int Key; // ebx
  LPCOLESTR v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  LPCOLESTR v19; // rcx
  int v20; // edx
  const char *v21; // rax
  __int64 v22; // rdx
  int v23; // [rsp+40h] [rbp-48h] BYREF

  v10 = (unsigned int)a3;
  v11 = (int)a1;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_LLll(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, a3, a1, a3, a5, a8);
  v23 = 0;
  if ( (unsigned int)v10 >= 0x14 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *a6 = 0;
  v12 = &g_GlobalConfigSettings + 5 * v10;
  *(_QWORD *)a7 = v12;
  if ( *(_DWORD *)v12 != (_DWORD)v10 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !*(_QWORD *)(*(_QWORD *)a7 + 16LL) )
  {
    Key = -2147024891;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_20;
    v17 = 240;
    v18 = 2147942405LL;
LABEL_48:
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v18);
    goto LABEL_20;
  }
  v13 = 33 * v11;
  if ( a5 == 1 )
  {
    if ( (_DWORD)v11 != 6 )
      a2 = -2147483646;
    Key = FwRegCreateKey(a2, qword_18004D8B0[v13], a4, a6);
    if ( Key >= 0 )
    {
      v23 = 1;
      goto LABEL_13;
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_20;
    v20 = 241;
    v21 = "FwRegCreateKey";
    goto LABEL_30;
  }
  if ( !a8 )
  {
    if ( (_DWORD)v11 != 6 )
      a2 = -2147483646;
    Key = FwRegOpenKey(a2, qword_18004D8B0[v13], a4, a6, &v23);
    if ( Key >= 0 )
      goto LABEL_12;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_20;
    v20 = 242;
    goto LABEL_29;
  }
  v22 = qword_18004D8B0[v13 + 1];
  if ( !v22 )
  {
    v18 = 2147942402LL;
    Key = -2147024894;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_20;
    v17 = 243;
    goto LABEL_48;
  }
  if ( (_DWORD)v11 != 6 )
    a2 = -2147483646;
  Key = FwRegOpenKey(a2, v22, a4, a6, &v23);
  if ( Key < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_20;
    v20 = 244;
LABEL_29:
    v21 = "FwRegOpenKey";
LABEL_30:
    WPP_SF_ds(
      *((_QWORD *)v19 + 2),
      v20,
      (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      Key,
      (__int64)v21);
LABEL_20:
    FwRegCloseKey(*a6);
    *a6 = 0;
    *(_QWORD *)a7 = 0;
    goto LABEL_13;
  }
LABEL_12:
  if ( !v23 )
  {
    v18 = 2147942402LL;
    Key = -2147024894;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_20;
    v17 = 245;
    goto LABEL_48;
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      246,
      WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      (unsigned int)Key);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180003680  mov     [rsp+arg_10], rbx
0x180003685  push    rbp
0x180003686  push    rsi
0x180003687  push    rdi
0x180003688  push    r12
0x18000368a  push    r13
0x18000368c  push    r14
0x18000368e  push    r15
0x180003690  sub     rsp, 50h
0x180003694  mov     rax, cs:__security_cookie
0x18000369b  xor     rax, rsp
0x18000369e  mov     [rsp+88h+var_40], rax
0x1800036a3  mov     r14, [rsp+88h+arg_28]
0x1800036ab  mov     r13d, r9d
0x1800036ae  mov     r12, [rsp+88h+arg_30]
0x1800036b6  mov     rsi, rdx
0x1800036b9  mov     ebx, r8d
0x1800036bc  movsxd  rdi, ecx
0x1800036bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036c6  lea     rax, WPP_GLOBAL_Control
0x1800036cd  mov     ebp, [rsp+88h+arg_38]
0x1800036d4  mov     r15d, [rsp+88h+arg_20]
0x1800036dc  cmp     rcx, rax
0x1800036df  jnz     loc_1800037C5
0x1800036e5  mov     [rsp+88h+var_48], 0
0x1800036ed  cmp     ebx, 14h
0x1800036f0  jnb     loc_180003847
0x1800036f6  mov     qword ptr [r14], 0
0x1800036fd  lea     rdx, __ImageBase
0x180003704  lea     rax, rva ?g_GlobalConfigSettings@@3PAU_tag_WF_CONFIG_DESCRIPTOR@@A[rdx]; _tag_WF_CONFIG_DESCRIPTOR near * g_GlobalConfigSettings ...
0x18000370b  lea     rcx, [rbx+rbx*4]
0x18000370f  lea     rax, [rax+rcx*8]
0x180003713  mov     [r12], rax
0x180003717  cmp     [rax], ebx
0x180003719  jnz     loc_180003851
0x18000371f  mov     rax, [r12]
0x180003723  cmp     qword ptr [rax+10h], 0
0x180003728  jz      loc_180003812
0x18000372e  imul    rcx, rdi, 108h
0x180003735  cmp     r15d, 1
0x180003739  jz      loc_180003875
0x18000373f  test    ebp, ebp
0x180003741  jnz     loc_180003928
0x180003747  mov     rdx, [rcx+rdx+4D8B0h]
0x18000374f  mov     rax, 0FFFFFFFF80000002h
0x180003756  cmp     edi, 6
0x180003759  mov     r9, r14
0x18000375c  mov     r8d, r13d
0x18000375f  cmovnz  rsi, rax
0x180003763  lea     rax, [rsp+88h+var_48]
0x180003768  mov     rcx, rsi
0x18000376b  mov     [rsp+88h+var_68], rax
0x180003770  call    cs:__imp_FwRegOpenKey
0x180003776  mov     ebx, eax
0x180003778  test    eax, eax
0x18000377a  js      loc_180003905
0x180003780  cmp     [rsp+88h+var_48], 0
0x180003785  jz      loc_1800039C5
0x18000378b  lea     rdi, WPP_GLOBAL_Control
0x180003792  mov     rcx, cs:WPP_GLOBAL_Control
0x180003799  cmp     rcx, rdi
0x18000379c  jnz     short loc_1800037F2
0x18000379e  mov     eax, ebx
0x1800037a0  mov     rcx, [rsp+88h+var_40]
0x1800037a5  xor     rcx, rsp; StackCookie
0x1800037a8  call    __security_check_cookie
0x1800037ad  mov     rbx, [rsp+88h+arg_10]
0x1800037b5  add     rsp, 50h
0x1800037b9  pop     r15
0x1800037bb  pop     r14
0x1800037bd  pop     r13
0x1800037bf  pop     r12
0x1800037c1  pop     rdi
0x1800037c2  pop     rsi
0x1800037c3  pop     rbp
0x1800037c4  retn
0x1800037c5  test    byte ptr [rcx+1Ch], 8
0x1800037c9  jz      loc_1800036E5
0x1800037cf  mov     rcx, [rcx+10h]
0x1800037d3  mov     edx, 0EFh
0x1800037d8  mov     [rsp+88h+var_58], ebp
0x1800037dc  mov     r9d, edi
0x1800037df  mov     [rsp+88h+var_60], r15d
0x1800037e4  mov     dword ptr [rsp+88h+var_68], ebx
0x1800037e8  call    WPP_SF_LLll
0x1800037ed  jmp     loc_1800036E5
0x1800037f2  test    byte ptr [rcx+1Ch], 8
0x1800037f6  jz      short loc_18000379E
0x1800037f8  mov     rcx, [rcx+10h]
0x1800037fc  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180003803  mov     edx, 0F6h
0x180003808  mov     r9d, ebx
0x18000380b  call    WPP_SF_d
0x180003810  jmp     short loc_18000379E
0x180003812  mov     ebx, 80070005h
0x180003817  mov     rcx, cs:WPP_GLOBAL_Control
0x18000381e  lea     rdi, WPP_GLOBAL_Control
0x180003825  cmp     rcx, rdi
0x180003828  jnz     short loc_180003862
0x18000382a  mov     rcx, [r14]
0x18000382d  call    cs:__imp_FwRegCloseKey
0x180003833  mov     qword ptr [r14], 0
0x18000383a  mov     qword ptr [r12], 0
0x180003842  jmp     loc_180003792
0x180003847  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000384c  jmp     loc_1800036F6
0x180003851  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003856  lea     rdx, __ImageBase
0x18000385d  jmp     loc_18000371F
0x180003862  test    byte ptr [rcx+1Ch], 1
0x180003866  jz      short loc_18000382A
0x180003868  mov     edx, 0F0h
0x18000386d  mov     r9d, ebx
0x180003870  jmp     loc_1800039F4
0x180003875  mov     rdx, [rcx+rdx+4D8B0h]
0x18000387d  mov     rax, 0FFFFFFFF80000002h
0x180003884  cmp     edi, 6
0x180003887  mov     r9, r14
0x18000388a  mov     r8d, r13d
0x18000388d  cmovnz  rsi, rax
0x180003891  mov     rcx, rsi
0x180003894  call    cs:__imp_FwRegCreateKey
0x18000389a  mov     ebx, eax
0x18000389c  test    eax, eax
0x18000389e  jns     short loc_1800038F8
0x1800038a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038a7  lea     rdi, WPP_GLOBAL_Control
0x1800038ae  cmp     rcx, rdi
0x1800038b1  jz      loc_18000382A
0x1800038b7  test    byte ptr [rcx+1Ch], 1
0x1800038bb  jz      loc_18000382A
0x1800038c1  mov     edx, 0F1h
0x1800038c6  lea     rax, aFwregcreatekey_0; "FwRegCreateKey"
0x1800038cd  jmp     short loc_1800038DB
0x1800038cf  mov     edx, 0F2h
0x1800038d4  lea     rax, aFwregopenkey_0; "FwRegOpenKey"
0x1800038db  mov     rcx, [rcx+10h]
0x1800038df  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x1800038e6  mov     r9d, ebx
0x1800038e9  mov     [rsp+88h+var_68], rax
0x1800038ee  call    WPP_SF_ds
0x1800038f3  jmp     loc_18000382A
0x1800038f8  mov     [rsp+88h+var_48], 1
0x180003900  jmp     loc_18000378B
0x180003905  mov     rcx, cs:WPP_GLOBAL_Control
0x18000390c  lea     rdi, WPP_GLOBAL_Control
0x180003913  cmp     rcx, rdi
0x180003916  jz      loc_18000382A
0x18000391c  test    byte ptr [rcx+1Ch], 1
0x180003920  jz      loc_18000382A
0x180003926  jmp     short loc_1800038CF
0x180003928  mov     rdx, [rcx+rdx+4D8B8h]
0x180003930  test    rdx, rdx
0x180003933  jnz     short loc_180003969
0x180003935  mov     r9d, 80070002h
0x18000393b  mov     ebx, r9d
0x18000393e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003945  lea     rdi, WPP_GLOBAL_Control
0x18000394c  cmp     rcx, rdi
0x18000394f  jz      loc_18000382A
0x180003955  test    byte ptr [rcx+1Ch], 1
0x180003959  jz      loc_18000382A
0x18000395f  mov     edx, 0F3h
0x180003964  jmp     loc_1800039F4
0x180003969  mov     rax, 0FFFFFFFF80000002h
0x180003970  cmp     edi, 6
0x180003973  mov     r9, r14
0x180003976  mov     r8d, r13d
0x180003979  cmovnz  rsi, rax
0x18000397d  lea     rax, [rsp+88h+var_48]
0x180003982  mov     rcx, rsi
0x180003985  mov     [rsp+88h+var_68], rax
0x18000398a  call    cs:__imp_FwRegOpenKey
0x180003990  mov     ebx, eax
0x180003992  test    eax, eax
0x180003994  jns     loc_180003780
0x18000399a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039a1  lea     rdi, WPP_GLOBAL_Control
0x1800039a8  cmp     rcx, rdi
0x1800039ab  jz      loc_18000382A
0x1800039b1  test    byte ptr [rcx+1Ch], 1
0x1800039b5  jz      loc_18000382A
0x1800039bb  mov     edx, 0F4h
0x1800039c0  jmp     loc_1800038D4
0x1800039c5  mov     r9d, 80070002h
0x1800039cb  mov     ebx, r9d
0x1800039ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039d5  lea     rdi, WPP_GLOBAL_Control
0x1800039dc  cmp     rcx, rdi
0x1800039df  jz      loc_18000382A
0x1800039e5  test    byte ptr [rcx+1Ch], 1
0x1800039e9  jz      loc_18000382A
0x1800039ef  mov     edx, 0F5h
0x1800039f4  mov     rcx, [rcx+10h]
0x1800039f8  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x1800039ff  call    WPP_SF_d
0x180003a04  jmp     loc_18000382A
```
