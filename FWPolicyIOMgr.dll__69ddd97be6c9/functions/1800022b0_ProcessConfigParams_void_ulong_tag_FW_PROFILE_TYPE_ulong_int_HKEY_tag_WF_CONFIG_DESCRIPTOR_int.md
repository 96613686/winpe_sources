# ProcessConfigParams(void *,ulong,_tag_FW_PROFILE_TYPE,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *,int)

- ea: `0x1800022b0`
- end: `0x180002586`
- name: `?ProcessConfigParams@@YAJPEAXKW4_tag_FW_PROFILE_TYPE@@KHPEAPEAUHKEY__@@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@H@Z`
- size: `726`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, int, _QWORD *, __int64, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001850`
- `0x18000203c`

## callees

- `0x180001cdc`
- `0x1800022b0`
- `0x180002590`
- `0x180004238`
- `0x1800042c4`
- `0x18001e9ac`
- `0x18001f650`

## import_xrefs

- `fwbase!FwRegOpenKey` at `0x18000250c`
- `fwbase!FwRegOpenKey` at `0x18000250c`
- `fwbase!FwRegCloseKey` at `0x180002395`
- `fwbase!FwRegCloseKey` at `0x180002395`
- `fwbase!FwRegCreateKey` at `0x1800024ba`
- `fwbase!FwRegCreateKey` at `0x1800024ba`

## string_xrefs

- `0x1800024ec`: `FwRegCreateKey`
- `0x18000248a`: `FwRegOpenKey`

## pseudocode

```c
__int64 __fastcall ProcessConfigParams(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        _QWORD *a6,
        __int64 a7,
        int a8)
{
  unsigned int v9; // r14d
  __int64 v10; // rbx
  struct _tag_WF_CONFIG_DESCRIPTOR near **v12; // rax
  int ProfileRegHandleFromStoreIOHandle; // ebx
  LPCOLESTR v14; // rcx
  __int64 v16; // rdx
  int v17; // eax
  int v18; // edx
  const char *v19; // rax
  __int64 v20; // [rsp+40h] [rbp-68h] BYREF
  int v21; // [rsp+48h] [rbp-60h] BYREF

  v9 = a3;
  v10 = a2;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_LLll(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, a3, a2, a3, a5, a8);
  v21 = 0;
  v20 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (unsigned int)v10 >= 0x14 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *a6 = 0;
  v12 = &g_configSettings + 5 * v10;
  *(_QWORD *)a7 = v12;
  if ( *(_DWORD *)v12 != (_DWORD)v10 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  ProfileRegHandleFromStoreIOHandle = FwGetProfileRegHandleFromStoreIOHandle(a1, v9, a5, &v20, a8);
  if ( ProfileRegHandleFromStoreIOHandle < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_10;
    v18 = 234;
    v19 = "FwGetProfileRegHandleFromStoreIOHandle";
    goto LABEL_23;
  }
  v16 = *(_QWORD *)(*(_QWORD *)a7 + 8LL);
  if ( !v16 )
  {
    *a6 = v20;
    v17 = 1;
    v21 = 1;
LABEL_17:
    if ( v17 )
      goto LABEL_11;
    ProfileRegHandleFromStoreIOHandle = -2147024894;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, 2147942402LL);
    goto LABEL_10;
  }
  if ( a5 != 1 )
  {
    ProfileRegHandleFromStoreIOHandle = FwRegOpenKey(v20, v16, a4, a6, &v21);
    if ( ProfileRegHandleFromStoreIOHandle >= 0 )
    {
      v17 = v21;
      goto LABEL_17;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_10;
    v18 = 236;
    v19 = "FwRegOpenKey";
LABEL_23:
    WPP_SF_ds(
      *((_QWORD *)v14 + 2),
      v18,
      (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      ProfileRegHandleFromStoreIOHandle,
      (__int64)v19);
    goto LABEL_10;
  }
  ProfileRegHandleFromStoreIOHandle = FwRegCreateKey(v20, v16, a4, a6);
  if ( ProfileRegHandleFromStoreIOHandle >= 0 )
  {
    v21 = 1;
    goto LABEL_11;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v18 = 235;
    v19 = "FwRegCreateKey";
    goto LABEL_23;
  }
LABEL_10:
  FwRegCloseKey(*a6);
  *a6 = 0;
  *(_QWORD *)a7 = 0;
LABEL_11:
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      238,
      WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      (unsigned int)ProfileRegHandleFromStoreIOHandle);
  return (unsigned int)ProfileRegHandleFromStoreIOHandle;
}

```

## disassembly

```asm
0x1800022b0  push    rbx
0x1800022b2  push    rbp
0x1800022b3  push    rsi
0x1800022b4  push    rdi
0x1800022b5  push    r12
0x1800022b7  push    r13
0x1800022b9  push    r14
0x1800022bb  push    r15
0x1800022bd  sub     rsp, 68h
0x1800022c1  mov     rax, cs:__security_cookie
0x1800022c8  xor     rax, rsp
0x1800022cb  mov     [rsp+0A8h+var_58], rax
0x1800022d0  mov     rdi, [rsp+0A8h+arg_28]
0x1800022d8  mov     r13d, r9d
0x1800022db  mov     r12, [rsp+0A8h+arg_30]
0x1800022e3  mov     r14d, r8d
0x1800022e6  mov     ebx, edx
0x1800022e8  mov     rbp, rcx
0x1800022eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022f2  lea     rax, WPP_GLOBAL_Control
0x1800022f9  mov     r15d, [rsp+0A8h+arg_38]
0x180002301  mov     esi, [rsp+0A8h+arg_20]
0x180002308  cmp     rcx, rax
0x18000230b  jnz     loc_180002421
0x180002311  mov     [rsp+0A8h+var_60], 0
0x180002319  mov     [rsp+0A8h+var_68], 0
0x180002322  test    rbp, rbp
0x180002325  jz      loc_18000244F
0x18000232b  cmp     ebx, 14h
0x18000232e  jnb     loc_180002459
0x180002334  mov     qword ptr [rdi], 0
0x18000233b  lea     r8, [rbx+rbx*4]
0x18000233f  lea     rax, ?g_configSettings@@3PAU_tag_WF_CONFIG_DESCRIPTOR@@A; _tag_WF_CONFIG_DESCRIPTOR near * g_configSettings
0x180002346  lea     rax, [rax+r8*8]
0x18000234a  mov     [r12], rax
0x18000234e  cmp     [rax], ebx
0x180002350  jnz     loc_180002463
0x180002356  lea     r9, [rsp+0A8h+var_68]
0x18000235b  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180002360  mov     r8d, esi
0x180002363  mov     edx, r14d
0x180002366  mov     rcx, rbp
0x180002369  call    ?FwGetProfileRegHandleFromStoreIOHandle@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@HPEAPEAUHKEY__@@H@Z; FwGetProfileRegHandleFromStoreIOHandle(void *,_tag_FW_PROFILE_TYPE,int,HKEY__ * *,int)
0x18000236e  lea     rbp, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180002375  mov     ebx, eax
0x180002377  test    eax, eax
0x180002379  jns     short loc_1800023F0
0x18000237b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002382  lea     rsi, WPP_GLOBAL_Control
0x180002389  cmp     rcx, rsi
0x18000238c  jnz     loc_18000246D
0x180002392  mov     rcx, [rdi]
0x180002395  call    cs:__imp_FwRegCloseKey
0x18000239b  mov     qword ptr [rdi], 0
0x1800023a2  mov     qword ptr [r12], 0
0x1800023aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023b1  cmp     rcx, rsi
0x1800023b4  jz      short loc_1800023D0
0x1800023b6  test    byte ptr [rcx+1Ch], 8
0x1800023ba  jz      short loc_1800023D0
0x1800023bc  mov     rcx, [rcx+10h]
0x1800023c0  mov     edx, 0EEh
0x1800023c5  mov     r9d, ebx
0x1800023c8  mov     r8, rbp
0x1800023cb  call    WPP_SF_d
0x1800023d0  mov     eax, ebx
0x1800023d2  mov     rcx, [rsp+0A8h+var_58]
0x1800023d7  xor     rcx, rsp; StackCookie
0x1800023da  call    __security_check_cookie
0x1800023df  add     rsp, 68h
0x1800023e3  pop     r15
0x1800023e5  pop     r14
0x1800023e7  pop     r13
0x1800023e9  pop     r12
0x1800023eb  pop     rdi
0x1800023ec  pop     rsi
0x1800023ed  pop     rbp
0x1800023ee  pop     rbx
0x1800023ef  retn
0x1800023f0  mov     rax, [r12]
0x1800023f4  mov     rdx, [rax+8]
0x1800023f8  test    rdx, rdx
0x1800023fb  jnz     loc_1800024AA
0x180002401  mov     rax, [rsp+0A8h+var_68]
0x180002406  mov     [rdi], rax
0x180002409  lea     eax, [rdx+1]
0x18000240c  mov     [rsp+0A8h+var_60], eax
0x180002410  test    eax, eax
0x180002412  jz      loc_180002547
0x180002418  lea     rsi, WPP_GLOBAL_Control
0x18000241f  jmp     short loc_1800023AA
0x180002421  test    byte ptr [rcx+1Ch], 8
0x180002425  jz      loc_180002311
0x18000242b  mov     rcx, [rcx+10h]
0x18000242f  mov     edx, 0E9h
0x180002434  mov     [rsp+0A8h+var_78], r15d
0x180002439  mov     r9d, ebx
0x18000243c  mov     [rsp+0A8h+var_80], esi
0x180002440  mov     dword ptr [rsp+0A8h+var_88], r14d
0x180002445  call    WPP_SF_LLll
0x18000244a  jmp     loc_180002311
0x18000244f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002454  jmp     loc_18000232B
0x180002459  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000245e  jmp     loc_180002334
0x180002463  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002468  jmp     loc_180002356
0x18000246d  test    byte ptr [rcx+1Ch], 1
0x180002471  jz      loc_180002392
0x180002477  mov     edx, 0EAh
0x18000247c  lea     rax, aFwgetprofilere; "FwGetProfileRegHandleFromStoreIOHandle"
0x180002483  jmp     short loc_180002491
0x180002485  mov     edx, 0ECh
0x18000248a  lea     rax, aFwregopenkey_0; "FwRegOpenKey"
0x180002491  mov     rcx, [rcx+10h]
0x180002495  mov     r9d, ebx
0x180002498  mov     r8, rbp
0x18000249b  mov     [rsp+0A8h+var_88], rax
0x1800024a0  call    WPP_SF_ds
0x1800024a5  jmp     loc_180002392
0x1800024aa  mov     rcx, [rsp+0A8h+var_68]
0x1800024af  mov     r9, rdi
0x1800024b2  mov     r8d, r13d
0x1800024b5  cmp     esi, 1
0x1800024b8  jnz     short loc_180002502
0x1800024ba  call    cs:__imp_FwRegCreateKey
0x1800024c0  mov     ebx, eax
0x1800024c2  test    eax, eax
0x1800024c4  jns     short loc_1800024F5
0x1800024c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024cd  lea     rsi, WPP_GLOBAL_Control
0x1800024d4  cmp     rcx, rsi
0x1800024d7  jz      loc_180002392
0x1800024dd  test    byte ptr [rcx+1Ch], 1
0x1800024e1  jz      loc_180002392
0x1800024e7  mov     edx, 0EBh
0x1800024ec  lea     rax, aFwregcreatekey_0; "FwRegCreateKey"
0x1800024f3  jmp     short loc_180002491
0x1800024f5  mov     [rsp+0A8h+var_60], 1
0x1800024fd  jmp     loc_180002418
0x180002502  lea     rax, [rsp+0A8h+var_60]
0x180002507  mov     [rsp+0A8h+var_88], rax
0x18000250c  call    cs:__imp_FwRegOpenKey
0x180002512  mov     ebx, eax
0x180002514  test    eax, eax
0x180002516  jns     short loc_18000253E
0x180002518  mov     rcx, cs:WPP_GLOBAL_Control
0x18000251f  lea     rsi, WPP_GLOBAL_Control
0x180002526  cmp     rcx, rsi
0x180002529  jz      loc_180002392
0x18000252f  test    byte ptr [rcx+1Ch], 1
0x180002533  jz      loc_180002392
0x180002539  jmp     loc_180002485
0x18000253e  mov     eax, [rsp+0A8h+var_60]
0x180002542  jmp     loc_180002410
0x180002547  mov     ebx, 80070002h
0x18000254c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002553  lea     rsi, WPP_GLOBAL_Control
0x18000255a  cmp     rcx, rsi
0x18000255d  jz      loc_180002392
0x180002563  test    byte ptr [rcx+1Ch], 1
0x180002567  jz      loc_180002392
0x18000256d  mov     rcx, [rcx+10h]
0x180002571  mov     edx, 0EDh
0x180002576  mov     r9d, ebx
0x180002579  mov     r8, rbp
0x18000257c  call    WPP_SF_d
0x180002581  jmp     loc_180002392
```
