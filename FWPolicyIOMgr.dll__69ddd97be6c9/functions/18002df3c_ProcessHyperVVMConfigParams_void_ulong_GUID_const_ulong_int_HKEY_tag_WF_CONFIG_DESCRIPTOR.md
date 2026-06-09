# ProcessHyperVVMConfigParams(void *,ulong,_GUID const &,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *)

- ea: `0x18002df3c`
- end: `0x18002e1b5`
- name: `?ProcessHyperVVMConfigParams@@YAJPEAXKAEBU_GUID@@KHPEAPEAUHKEY__@@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(int *, unsigned int, const struct _GUID *, unsigned int, int, HKEY *, struct _tag_WF_CONFIG_DESCRIPTOR **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002baf4`
- `0x180030680`

## callees

- `0x180001cdc`
- `0x1800042c4`
- `0x18001e9ac`
- `0x18001f650`
- `0x18002b930`
- `0x18002df3c`
- `0x180030f84`

## import_xrefs

- `fwbase!FwRegOpenKey` at `0x18002e111`
- `fwbase!FwRegOpenKey` at `0x18002e111`
- `fwbase!FwRegCloseKey` at `0x18002e19b`
- `fwbase!FwRegCloseKey` at `0x18002e19b`
- `fwbase!FwRegCreateKey` at `0x18002e079`
- `fwbase!FwRegCreateKey` at `0x18002e079`

## string_xrefs

- `0x18002e0ab`: `FwRegCreateKey`
- `0x18002e13b`: `FwRegOpenKey`

## pseudocode

```c
__int64 __fastcall ProcessHyperVVMConfigParams(
        int *a1,
        unsigned int a2,
        const struct _GUID *a3,
        unsigned int a4,
        int a5,
        HKEY *a6,
        struct _tag_WF_CONFIG_DESCRIPTOR **a7)
{
  __int64 v9; // rbx
  int HyperVRegHandleFromStoreIOHandle; // ebx
  LPCOLESTR v12; // rcx
  int v13; // edx
  const char *v14; // rax
  __int64 v15; // rdx
  int v17; // eax
  HKEY v18; // [rsp+30h] [rbp-58h] BYREF
  int v19; // [rsp+38h] [rbp-50h] BYREF

  v9 = a2;
  v19 = 0;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_L_guid_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, (_DWORD)a3, a2, (__int64)a3);
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (unsigned int)v9 >= 6 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *a6 = 0;
  *a7 = (struct _tag_WF_CONFIG_DESCRIPTOR *)(&g_HyperVVMConfigSettings + 5 * v9);
  HyperVRegHandleFromStoreIOHandle = FwGetHyperVRegHandleFromStoreIOHandle(a1, a3, a5, &v18);
  if ( HyperVRegHandleFromStoreIOHandle < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_34;
    v13 = 248;
    v14 = "FwGetHyperVVMTypeRegHandleFromStoreIOHandle";
LABEL_12:
    WPP_SF_ds(
      *((_QWORD *)v12 + 2),
      v13,
      (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      HyperVRegHandleFromStoreIOHandle,
      (__int64)v14);
LABEL_34:
    FwRegCloseKey(*a6);
    *a6 = 0;
    *a7 = 0;
    goto LABEL_20;
  }
  v15 = *((_QWORD *)*a7 + 1);
  if ( !v15 )
  {
    *a6 = v18;
    v17 = 1;
    v19 = 1;
LABEL_30:
    if ( !v17 )
    {
      HyperVRegHandleFromStoreIOHandle = -2147024894;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          251,
          WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
          2147942402LL);
      goto LABEL_34;
    }
    goto LABEL_20;
  }
  if ( a5 != 1 )
  {
    HyperVRegHandleFromStoreIOHandle = FwRegOpenKey(v18, v15, a4, a6, &v19);
    if ( HyperVRegHandleFromStoreIOHandle < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_34;
      v13 = 250;
      v14 = "FwRegOpenKey";
      goto LABEL_12;
    }
    v17 = v19;
    goto LABEL_30;
  }
  HyperVRegHandleFromStoreIOHandle = FwRegCreateKey(v18, v15, a4, a6);
  if ( HyperVRegHandleFromStoreIOHandle < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_34;
    v13 = 249;
    v14 = "FwRegCreateKey";
    goto LABEL_12;
  }
  v19 = 1;
LABEL_20:
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      252,
      WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      (unsigned int)HyperVRegHandleFromStoreIOHandle);
  return (unsigned int)HyperVRegHandleFromStoreIOHandle;
}

```

## disassembly

```asm
0x18002df3c  push    rbx
0x18002df3e  push    rbp
0x18002df3f  push    rsi
0x18002df40  push    rdi
0x18002df41  push    r12
0x18002df43  push    r14
0x18002df45  push    r15
0x18002df47  sub     rsp, 50h
0x18002df4b  mov     rax, cs:__security_cookie
0x18002df52  xor     rax, rsp
0x18002df55  mov     [rsp+88h+var_48], rax
0x18002df5a  mov     rdi, [rsp+88h+arg_28]
0x18002df62  mov     r15d, r9d
0x18002df65  mov     r12, [rsp+88h+arg_30]
0x18002df6d  mov     r14, r8
0x18002df70  mov     ebx, edx
0x18002df72  mov     rbp, rcx
0x18002df75  mov     [rsp+88h+var_50], 0
0x18002df7d  mov     [rsp+88h+var_58], 0
0x18002df86  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df8d  lea     rax, WPP_GLOBAL_Control
0x18002df94  mov     esi, [rsp+88h+arg_20]
0x18002df9b  cmp     rcx, rax
0x18002df9e  jz      short loc_18002DFC0
0x18002dfa0  test    byte ptr [rcx+1Ch], 8
0x18002dfa4  jz      short loc_18002DFC0
0x18002dfa6  mov     rcx, [rcx+10h]
0x18002dfaa  mov     edx, 0F7h
0x18002dfaf  mov     [rsp+88h+var_60], esi
0x18002dfb3  mov     r9d, ebx
0x18002dfb6  mov     [rsp+88h+var_68], r8
0x18002dfbb  call    WPP_SF_L_guid_l
0x18002dfc0  test    rbp, rbp
0x18002dfc3  jnz     short loc_18002DFCA
0x18002dfc5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002dfca  cmp     ebx, 6
0x18002dfcd  jb      short loc_18002DFD4
0x18002dfcf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002dfd4  lea     r8, [rbx+rbx*4]
0x18002dfd8  mov     qword ptr [rdi], 0
0x18002dfdf  lea     rax, ?g_HyperVVMConfigSettings@@3PAU_tag_WF_CONFIG_DESCRIPTOR@@A; _tag_WF_CONFIG_DESCRIPTOR near * g_HyperVVMConfigSettings
0x18002dfe6  mov     rdx, r14; struct _GUID *
0x18002dfe9  lea     rax, [rax+r8*8]
0x18002dfed  mov     rcx, rbp; void *
0x18002dff0  mov     r8d, esi; int
0x18002dff3  mov     [r12], rax
0x18002dff7  lea     r9, [rsp+88h+var_58]; HKEY *
0x18002dffc  call    ?FwGetHyperVRegHandleFromStoreIOHandle@@YAJPEAXAEBU_GUID@@HPEAPEAUHKEY__@@@Z; FwGetHyperVRegHandleFromStoreIOHandle(void *,_GUID const &,int,HKEY__ * *)
0x18002e001  lea     rbp, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002e008  mov     ebx, eax
0x18002e00a  test    eax, eax
0x18002e00c  jns     short loc_18002E054
0x18002e00e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e015  lea     rsi, WPP_GLOBAL_Control
0x18002e01c  cmp     rcx, rsi
0x18002e01f  jz      loc_18002E198
0x18002e025  test    byte ptr [rcx+1Ch], 1
0x18002e029  jz      loc_18002E198
0x18002e02f  mov     edx, 0F8h
0x18002e034  lea     rax, aFwgethypervvmt; "FwGetHyperVVMTypeRegHandleFromStoreIOHa"...
0x18002e03b  mov     rcx, [rcx+10h]
0x18002e03f  mov     r9d, ebx
0x18002e042  mov     r8, rbp
0x18002e045  mov     [rsp+88h+var_68], rax
0x18002e04a  call    WPP_SF_ds
0x18002e04f  jmp     loc_18002E198
0x18002e054  mov     rax, [r12]
0x18002e058  mov     rdx, [rax+8]
0x18002e05c  test    rdx, rdx
0x18002e05f  jz      loc_18002E14D
0x18002e065  mov     rcx, [rsp+88h+var_58]
0x18002e06a  mov     r9, rdi
0x18002e06d  mov     r8d, r15d
0x18002e070  cmp     esi, 1
0x18002e073  jnz     loc_18002E107
0x18002e079  call    cs:__imp_FwRegCreateKey
0x18002e07f  mov     ebx, eax
0x18002e081  test    eax, eax
0x18002e083  jns     short loc_18002E0B4
0x18002e085  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e08c  lea     rsi, WPP_GLOBAL_Control
0x18002e093  cmp     rcx, rsi
0x18002e096  jz      loc_18002E198
0x18002e09c  test    byte ptr [rcx+1Ch], 1
0x18002e0a0  jz      loc_18002E198
0x18002e0a6  mov     edx, 0F9h
0x18002e0ab  lea     rax, aFwregcreatekey_0; "FwRegCreateKey"
0x18002e0b2  jmp     short loc_18002E03B
0x18002e0b4  mov     [rsp+88h+var_50], 1
0x18002e0bc  lea     rsi, WPP_GLOBAL_Control
0x18002e0c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e0ca  cmp     rcx, rsi
0x18002e0cd  jz      short loc_18002E0E9
0x18002e0cf  test    byte ptr [rcx+1Ch], 8
0x18002e0d3  jz      short loc_18002E0E9
0x18002e0d5  mov     rcx, [rcx+10h]
0x18002e0d9  mov     edx, 0FCh
0x18002e0de  mov     r9d, ebx
0x18002e0e1  mov     r8, rbp
0x18002e0e4  call    WPP_SF_d
0x18002e0e9  mov     eax, ebx
0x18002e0eb  mov     rcx, [rsp+88h+var_48]
0x18002e0f0  xor     rcx, rsp; StackCookie
0x18002e0f3  call    __security_check_cookie
0x18002e0f8  add     rsp, 50h
0x18002e0fc  pop     r15
0x18002e0fe  pop     r14
0x18002e100  pop     r12
0x18002e102  pop     rdi
0x18002e103  pop     rsi
0x18002e104  pop     rbp
0x18002e105  pop     rbx
0x18002e106  retn
0x18002e107  lea     rax, [rsp+88h+var_50]
0x18002e10c  mov     [rsp+88h+var_68], rax
0x18002e111  call    cs:__imp_FwRegOpenKey
0x18002e117  mov     ebx, eax
0x18002e119  test    eax, eax
0x18002e11b  jns     short loc_18002E147
0x18002e11d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e124  lea     rsi, WPP_GLOBAL_Control
0x18002e12b  cmp     rcx, rsi
0x18002e12e  jz      short loc_18002E198
0x18002e130  test    byte ptr [rcx+1Ch], 1
0x18002e134  jz      short loc_18002E198
0x18002e136  mov     edx, 0FAh
0x18002e13b  lea     rax, aFwregopenkey_0; "FwRegOpenKey"
0x18002e142  jmp     loc_18002E03B
0x18002e147  mov     eax, [rsp+88h+var_50]
0x18002e14b  jmp     short loc_18002E15E
0x18002e14d  mov     rax, [rsp+88h+var_58]
0x18002e152  mov     [rdi], rax
0x18002e155  mov     eax, 1
0x18002e15a  mov     [rsp+88h+var_50], eax
0x18002e15e  test    eax, eax
0x18002e160  jnz     loc_18002E0BC
0x18002e166  mov     ebx, 80070002h
0x18002e16b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e172  lea     rsi, WPP_GLOBAL_Control
0x18002e179  cmp     rcx, rsi
0x18002e17c  jz      short loc_18002E198
0x18002e17e  test    byte ptr [rcx+1Ch], 1
0x18002e182  jz      short loc_18002E198
0x18002e184  mov     rcx, [rcx+10h]
0x18002e188  mov     edx, 0FBh
0x18002e18d  mov     r9d, ebx
0x18002e190  mov     r8, rbp
0x18002e193  call    WPP_SF_d
0x18002e198  mov     rcx, [rdi]
0x18002e19b  call    cs:__imp_FwRegCloseKey
0x18002e1a1  mov     qword ptr [rdi], 0
0x18002e1a8  mov     qword ptr [r12], 0
0x18002e1b0  jmp     loc_18002E0C3
```
