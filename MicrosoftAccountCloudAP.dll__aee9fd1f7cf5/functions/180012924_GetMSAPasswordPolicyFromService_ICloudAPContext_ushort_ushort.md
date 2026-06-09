# GetMSAPasswordPolicyFromService(ICloudAPContext *,ushort *,ushort *)

- ea: `0x180012924`
- end: `0x180012a45`
- name: `?GetMSAPasswordPolicyFromService@@YAJPEAVICloudAPContext@@PEAG1@Z`
- size: `289`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180013c0c`

## callees

- `0x180008440`
- `0x18000baac`
- `0x180012924`
- `0x180026c8c`
- `0x180032010`

## string_xrefs

- `0x18001297f`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x1800129dd`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180012950`: `GetMSAPasswordPolicyFromService`
- `0x1800129c5`: `hr = pNtServiceContext->WLIDCGetConfigDWORDValue(WLID_CONFIG_MIN_PASSWORD_LENGTH, &providerPasswordLength)`
- `0x180012a0a`: `hr = pNtServiceContext->WLIDCGetConfigDWORDValue(WLID_CONFIG_MIN_PASSWORD_CHAR_GROUPS, &providerPasswordCharacterGroups)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetMSAPasswordPolicyFromService(
        struct ICloudAPContext *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  __int64 v6; // rbx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // r8d
  int v10; // eax
  unsigned int v11; // ebx
  char *v13; // [rsp+20h] [rbp-30h]
  _QWORD v14[4]; // [rsp+30h] [rbp-20h] BYREF
  int v15; // [rsp+80h] [rbp+30h] BYREF
  int v16; // [rsp+88h] [rbp+38h] BYREF
  int v17; // [rsp+90h] [rbp+40h] BYREF

  v15 = 0;
  v16 = 0;
  v17 = 0;
  v14[0] = "GetMSAPasswordPolicyFromService";
  v14[1] = &v15;
  v14[2] = 0;
  v14[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "GetMSAPasswordPolicyFromService",
    (const char *)0x673,
    0,
    (const unsigned __int16 *)v13);
  *a2 = 0;
  *a3 = 0;
  v6 = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v6 + 96LL))(v6, 18, &v16);
  v15 = v7;
  if ( v7 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v6 + 96LL))(v6, 19, &v17);
    v15 = v10;
    if ( v10 >= 0 )
    {
      *a2 = v16;
      *a3 = v17;
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
        "GetMSAPasswordPolicyFromService",
        0x67Fu,
        v10,
        "hr = pNtServiceContext->WLIDCGetConfigDWORDValue(WLID_CONFIG_MIN_PASSWORD_CHAR_GROUPS, &providerPasswordCharacterGroups)");
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
      "GetMSAPasswordPolicyFromService",
      0x67Cu,
      v7,
      "hr = pNtServiceContext->WLIDCGetConfigDWORDValue(WLID_CONFIG_MIN_PASSWORD_LENGTH, &providerPasswordLength)");
  }
  v11 = v15;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v14, v8, v9);
  return v11;
}

```

## disassembly

```asm
0x180012924  push    rbp
0x180012926  push    rbx
0x180012927  push    rsi
0x180012928  push    rdi
0x180012929  push    r14
0x18001292b  mov     rbp, rsp
0x18001292e  sub     rsp, 50h
0x180012932  mov     rdi, r8
0x180012935  mov     rsi, rdx
0x180012938  mov     rbx, rcx
0x18001293b  mov     [rbp+arg_0], 0
0x180012942  mov     [rbp+arg_8], 0
0x180012949  mov     [rbp+arg_10], 0
0x180012950  lea     r14, aGetmsapassword_0; "GetMSAPasswordPolicyFromService"
0x180012957  mov     [rbp+var_20], r14
0x18001295b  lea     rax, [rbp+arg_0]
0x18001295f  mov     [rbp+var_18], rax
0x180012963  mov     [rbp+var_10], 0
0x18001296b  mov     [rbp+var_8], 0
0x180012973  xor     r9d, r9d; unsigned int
0x180012976  mov     r8d, 673h; char *
0x18001297c  mov     rdx, r14; char *
0x18001297f  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180012986  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001298b  nop
0x18001298c  xor     eax, eax
0x18001298e  mov     [rsi], ax
0x180012991  mov     [rdi], ax
0x180012994  mov     rax, [rbx]
0x180012997  mov     rcx, rbx
0x18001299a  mov     rax, [rax+18h]
0x18001299e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129a3  mov     rbx, rax
0x1800129a6  mov     rcx, [rax]
0x1800129a9  mov     rax, [rcx+60h]
0x1800129ad  lea     r8, [rbp+arg_8]
0x1800129b1  mov     edx, 12h
0x1800129b6  mov     rcx, rbx
0x1800129b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129be  mov     [rbp+arg_0], eax
0x1800129c1  test    eax, eax
0x1800129c3  jns     short loc_1800129EB
0x1800129c5  lea     r8, aHrPntserviceco_0; "hr = pNtServiceContext->WLIDCGetConfigD"...
0x1800129cc  mov     [rsp+50h+var_30], r8; char *
0x1800129d1  mov     r8d, 67Ch; unsigned int
0x1800129d7  mov     r9d, eax; int
0x1800129da  mov     rdx, r14; char *
0x1800129dd  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800129e4  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800129e9  jmp     short loc_180012A2C
0x1800129eb  mov     rax, [rbx]
0x1800129ee  lea     r8, [rbp+arg_10]
0x1800129f2  mov     edx, 13h
0x1800129f7  mov     rcx, rbx
0x1800129fa  mov     rax, [rax+60h]
0x1800129fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a03  mov     [rbp+arg_0], eax
0x180012a06  test    eax, eax
0x180012a08  jns     short loc_180012A1E
0x180012a0a  lea     rcx, aHrPntserviceco; "hr = pNtServiceContext->WLIDCGetConfigD"...
0x180012a11  mov     [rsp+50h+var_30], rcx
0x180012a16  mov     r8d, 67Fh
0x180012a1c  jmp     short loc_1800129D7
0x180012a1e  movzx   eax, word ptr [rbp+arg_8]
0x180012a22  mov     [rsi], ax
0x180012a25  movzx   eax, word ptr [rbp+arg_10]
0x180012a29  mov     [rdi], ax
0x180012a2c  mov     ebx, [rbp+arg_0]
0x180012a2f  lea     rcx, [rbp+var_20]
0x180012a33  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180012a38  mov     eax, ebx
0x180012a3a  add     rsp, 50h
0x180012a3e  pop     r14
0x180012a40  pop     rdi
0x180012a41  pop     rsi
0x180012a42  pop     rbx
0x180012a43  pop     rbp
0x180012a44  retn
```
