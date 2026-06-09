# ProcessHyperVProfileConfigParams(void *,_tag_FW_PROFILE_TYPE,ulong,_GUID const &,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *)

- ea: `0x18002dcb0`
- end: `0x18002df33`
- name: `?ProcessHyperVProfileConfigParams@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@KAEBU_GUID@@KHPEAPEAUHKEY__@@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, const GUID *, unsigned int, int, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b56c`
- `0x180030390`

## callees

- `0x180001cdc`
- `0x1800042c4`
- `0x18001e9ac`
- `0x18001f650`
- `0x18002b6b4`
- `0x18002dcb0`
- `0x180030f84`

## import_xrefs

- `fwbase!FwRegOpenKey` at `0x18002de90`
- `fwbase!FwRegOpenKey` at `0x18002de90`
- `fwbase!FwRegCloseKey` at `0x18002df1a`
- `fwbase!FwRegCloseKey` at `0x18002df1a`
- `fwbase!FwRegCreateKey` at `0x18002ddf8`
- `fwbase!FwRegCreateKey` at `0x18002ddf8`

## string_xrefs

- `0x18002de2a`: `FwRegCreateKey`
- `0x18002deba`: `FwRegOpenKey`

## pseudocode

```c
__int64 __fastcall ProcessHyperVProfileConfigParams(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        const GUID *a4,
        unsigned int a5,
        int a6,
        _QWORD *a7,
        __int64 a8)
{
  __int64 v10; // rbx
  struct _tag_WF_CONFIG_DESCRIPTOR near **v12; // rax
  int HyperVProfileRegHandleFromStoreIOHandle; // ebx
  LPCOLESTR v14; // rcx
  int v15; // edx
  const char *v16; // rax
  __int64 v17; // rdx
  int v19; // eax
  __int64 v20; // [rsp+30h] [rbp-58h] BYREF
  int v21; // [rsp+38h] [rbp-50h] BYREF

  v10 = a3;
  v21 = 0;
  v20 = 0;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_L_guid_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, a3, a3, (__int64)a4);
  if ( (unsigned int)v10 >= 5 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *a7 = 0;
  v12 = &g_HyperVProfileConfigSettings + 5 * v10;
  *(_QWORD *)a8 = v12;
  if ( *(_DWORD *)v12 != (_DWORD)v10 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  HyperVProfileRegHandleFromStoreIOHandle = FwGetHyperVProfileRegHandleFromStoreIOHandle(a1, a2, a4, a6, (__int64)&v20);
  if ( HyperVProfileRegHandleFromStoreIOHandle < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_34;
    v15 = 254;
    v16 = "FwGetHyperVVMTypeRegHandleFromStoreIOHandle";
LABEL_12:
    WPP_SF_ds(
      *((_QWORD *)v14 + 2),
      v15,
      (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      HyperVProfileRegHandleFromStoreIOHandle,
      (__int64)v16);
LABEL_34:
    FwRegCloseKey(*a7);
    *a7 = 0;
    *(_QWORD *)a8 = 0;
    goto LABEL_20;
  }
  v17 = *(_QWORD *)(*(_QWORD *)a8 + 8LL);
  if ( !v17 )
  {
    *a7 = v20;
    v19 = 1;
    v21 = 1;
LABEL_30:
    if ( !v19 )
    {
      HyperVProfileRegHandleFromStoreIOHandle = -2147024894;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          257,
          WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
          2147942402LL);
      goto LABEL_34;
    }
    goto LABEL_20;
  }
  if ( a6 != 1 )
  {
    HyperVProfileRegHandleFromStoreIOHandle = FwRegOpenKey(v20, v17, a5, a7, &v21);
    if ( HyperVProfileRegHandleFromStoreIOHandle < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_34;
      v15 = 256;
      v16 = "FwRegOpenKey";
      goto LABEL_12;
    }
    v19 = v21;
    goto LABEL_30;
  }
  HyperVProfileRegHandleFromStoreIOHandle = FwRegCreateKey(v20, v17, a5, a7);
  if ( HyperVProfileRegHandleFromStoreIOHandle < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_34;
    v15 = 255;
    v16 = "FwRegCreateKey";
    goto LABEL_12;
  }
  v21 = 1;
LABEL_20:
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      258,
      WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      (unsigned int)HyperVProfileRegHandleFromStoreIOHandle);
  return (unsigned int)HyperVProfileRegHandleFromStoreIOHandle;
}

```

## disassembly

```asm
0x18002dcb0  push    rbx
0x18002dcb2  push    rbp
0x18002dcb3  push    rsi
0x18002dcb4  push    rdi
0x18002dcb5  push    r12
0x18002dcb7  push    r14
0x18002dcb9  push    r15
0x18002dcbb  sub     rsp, 50h
0x18002dcbf  mov     rax, cs:__security_cookie
0x18002dcc6  xor     rax, rsp
0x18002dcc9  mov     [rsp+88h+var_48], rax
0x18002dcce  mov     rdi, [rsp+88h+arg_30]
0x18002dcd6  mov     rbp, r9
0x18002dcd9  mov     r14, [rsp+88h+arg_38]
0x18002dce1  mov     r12d, edx
0x18002dce4  mov     ebx, r8d
0x18002dce7  mov     r15, rcx
0x18002dcea  mov     [rsp+88h+var_50], 0
0x18002dcf2  mov     [rsp+88h+var_58], 0
0x18002dcfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd02  lea     rax, WPP_GLOBAL_Control
0x18002dd09  mov     esi, [rsp+88h+arg_28]
0x18002dd10  cmp     rcx, rax
0x18002dd13  jz      short loc_18002DD35
0x18002dd15  test    byte ptr [rcx+1Ch], 8
0x18002dd19  jz      short loc_18002DD35
0x18002dd1b  mov     rcx, [rcx+10h]
0x18002dd1f  mov     edx, 0FDh
0x18002dd24  mov     [rsp+88h+var_60], esi
0x18002dd28  mov     [rsp+88h+var_68], r9
0x18002dd2d  mov     r9d, ebx
0x18002dd30  call    WPP_SF_L_guid_l
0x18002dd35  cmp     ebx, 5
0x18002dd38  jb      short loc_18002DD3F
0x18002dd3a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002dd3f  mov     qword ptr [rdi], 0
0x18002dd46  lea     r9, [rbx+rbx*4]
0x18002dd4a  lea     rax, ?g_HyperVProfileConfigSettings@@3PAU_tag_WF_CONFIG_DESCRIPTOR@@A; _tag_WF_CONFIG_DESCRIPTOR near * g_HyperVProfileConfigSettings
0x18002dd51  lea     rax, [rax+r9*8]
0x18002dd55  mov     [r14], rax
0x18002dd58  cmp     [rax], ebx
0x18002dd5a  jz      short loc_18002DD61
0x18002dd5c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002dd61  lea     rax, [rsp+88h+var_58]
0x18002dd66  mov     r9d, esi
0x18002dd69  mov     r8, rbp
0x18002dd6c  mov     [rsp+88h+var_68], rax
0x18002dd71  mov     edx, r12d
0x18002dd74  mov     rcx, r15
0x18002dd77  call    ?FwGetHyperVProfileRegHandleFromStoreIOHandle@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@AEBU_GUID@@HPEAPEAUHKEY__@@@Z; FwGetHyperVProfileRegHandleFromStoreIOHandle(void *,_tag_FW_PROFILE_TYPE,_GUID const &,int,HKEY__ * *)
0x18002dd7c  lea     rbp, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002dd83  mov     ebx, eax
0x18002dd85  test    eax, eax
0x18002dd87  jns     short loc_18002DDCF
0x18002dd89  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd90  lea     rsi, WPP_GLOBAL_Control
0x18002dd97  cmp     rcx, rsi
0x18002dd9a  jz      loc_18002DF17
0x18002dda0  test    byte ptr [rcx+1Ch], 1
0x18002dda4  jz      loc_18002DF17
0x18002ddaa  mov     edx, 0FEh
0x18002ddaf  lea     rax, aFwgethypervvmt; "FwGetHyperVVMTypeRegHandleFromStoreIOHa"...
0x18002ddb6  mov     rcx, [rcx+10h]
0x18002ddba  mov     r9d, ebx
0x18002ddbd  mov     r8, rbp
0x18002ddc0  mov     [rsp+88h+var_68], rax
0x18002ddc5  call    WPP_SF_ds
0x18002ddca  jmp     loc_18002DF17
0x18002ddcf  mov     rax, [r14]
0x18002ddd2  mov     rdx, [rax+8]
0x18002ddd6  test    rdx, rdx
0x18002ddd9  jz      loc_18002DECC
0x18002dddf  mov     r8d, [rsp+88h+arg_20]
0x18002dde7  mov     r9, rdi
0x18002ddea  mov     rcx, [rsp+88h+var_58]
0x18002ddef  cmp     esi, 1
0x18002ddf2  jnz     loc_18002DE86
0x18002ddf8  call    cs:__imp_FwRegCreateKey
0x18002ddfe  mov     ebx, eax
0x18002de00  test    eax, eax
0x18002de02  jns     short loc_18002DE33
0x18002de04  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de0b  lea     rsi, WPP_GLOBAL_Control
0x18002de12  cmp     rcx, rsi
0x18002de15  jz      loc_18002DF17
0x18002de1b  test    byte ptr [rcx+1Ch], 1
0x18002de1f  jz      loc_18002DF17
0x18002de25  mov     edx, 0FFh
0x18002de2a  lea     rax, aFwregcreatekey_0; "FwRegCreateKey"
0x18002de31  jmp     short loc_18002DDB6
0x18002de33  mov     [rsp+88h+var_50], 1
0x18002de3b  lea     rsi, WPP_GLOBAL_Control
0x18002de42  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de49  cmp     rcx, rsi
0x18002de4c  jz      short loc_18002DE68
0x18002de4e  test    byte ptr [rcx+1Ch], 8
0x18002de52  jz      short loc_18002DE68
0x18002de54  mov     rcx, [rcx+10h]
0x18002de58  mov     edx, 102h
0x18002de5d  mov     r9d, ebx
0x18002de60  mov     r8, rbp
0x18002de63  call    WPP_SF_d
0x18002de68  mov     eax, ebx
0x18002de6a  mov     rcx, [rsp+88h+var_48]
0x18002de6f  xor     rcx, rsp; StackCookie
0x18002de72  call    __security_check_cookie
0x18002de77  add     rsp, 50h
0x18002de7b  pop     r15
0x18002de7d  pop     r14
0x18002de7f  pop     r12
0x18002de81  pop     rdi
0x18002de82  pop     rsi
0x18002de83  pop     rbp
0x18002de84  pop     rbx
0x18002de85  retn
0x18002de86  lea     rax, [rsp+88h+var_50]
0x18002de8b  mov     [rsp+88h+var_68], rax
0x18002de90  call    cs:__imp_FwRegOpenKey
0x18002de96  mov     ebx, eax
0x18002de98  test    eax, eax
0x18002de9a  jns     short loc_18002DEC6
0x18002de9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dea3  lea     rsi, WPP_GLOBAL_Control
0x18002deaa  cmp     rcx, rsi
0x18002dead  jz      short loc_18002DF17
0x18002deaf  test    byte ptr [rcx+1Ch], 1
0x18002deb3  jz      short loc_18002DF17
0x18002deb5  mov     edx, 100h
0x18002deba  lea     rax, aFwregopenkey_0; "FwRegOpenKey"
0x18002dec1  jmp     loc_18002DDB6
0x18002dec6  mov     eax, [rsp+88h+var_50]
0x18002deca  jmp     short loc_18002DEDD
0x18002decc  mov     rax, [rsp+88h+var_58]
0x18002ded1  mov     [rdi], rax
0x18002ded4  mov     eax, 1
0x18002ded9  mov     [rsp+88h+var_50], eax
0x18002dedd  test    eax, eax
0x18002dedf  jnz     loc_18002DE3B
0x18002dee5  mov     ebx, 80070002h
0x18002deea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002def1  lea     rsi, WPP_GLOBAL_Control
0x18002def8  cmp     rcx, rsi
0x18002defb  jz      short loc_18002DF17
0x18002defd  test    byte ptr [rcx+1Ch], 1
0x18002df01  jz      short loc_18002DF17
0x18002df03  mov     rcx, [rcx+10h]
0x18002df07  mov     edx, 101h
0x18002df0c  mov     r9d, ebx
0x18002df0f  mov     r8, rbp
0x18002df12  call    WPP_SF_d
0x18002df17  mov     rcx, [rdi]
0x18002df1a  call    cs:__imp_FwRegCloseKey
0x18002df20  mov     qword ptr [rdi], 0
0x18002df27  mov     qword ptr [r14], 0
0x18002df2e  jmp     loc_18002DE42
```
