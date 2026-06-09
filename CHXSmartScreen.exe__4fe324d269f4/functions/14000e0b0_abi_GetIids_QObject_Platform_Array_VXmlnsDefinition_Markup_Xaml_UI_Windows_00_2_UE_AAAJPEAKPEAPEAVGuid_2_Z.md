# ?__abi_GetIids@?QObject@Platform@@?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAJPEAKPEAPEAVGuid@2@@Z

- ea: `0x14000e0b0`
- end: `0x14000e154`
- name: `?__abi_GetIids@?QObject@Platform@@?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAJPEAKPEAPEAVGuid@2@@Z`
- size: `164`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000e160`
- `0x14000e170`
- `0x14000e180`
- `0x14000e190`
- `0x14000e1a0`
- `0x14000e1b0`
- `0x14000e1c0`
- `0x14000e1d0`

## callees

- `0x140002844`
- `0x140031960`

## pseudocode

```c
__int64 __fastcall ___abi_GetIids__QObject_Platform____Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_2_UE_AAAJPEAKPEAPEAVGuid_2__Z(
        __int64 a1,
        int a2,
        const struct __s_GUID *a3)
{
  __int64 v4; // [rsp+20h] [rbp-50h] BYREF
  int v5; // [rsp+28h] [rbp-48h]
  int v6; // [rsp+2Ch] [rbp-44h]
  int v7; // [rsp+30h] [rbp-40h]
  int v8; // [rsp+34h] [rbp-3Ch]
  int v9; // [rsp+38h] [rbp-38h]
  int v10; // [rsp+3Ch] [rbp-34h]
  int v11; // [rsp+40h] [rbp-30h]
  int v12; // [rsp+44h] [rbp-2Ch]
  int v13; // [rsp+48h] [rbp-28h]
  int v14; // [rsp+4Ch] [rbp-24h]
  __int64 v15; // [rsp+50h] [rbp-20h]
  int v16; // [rsp+58h] [rbp-18h]
  int v17; // [rsp+5Ch] [rbp-14h]

  v5 = 639045002;
  v6 = 975021596;
  v7 = 819308585;
  v8 = 1076264868;
  v9 = 1540864899;
  v10 = -1633071442;
  v11 = 2120490263;
  v12 = 1343316573;
  v13 = 500875198;
  v14 = 23865584;
  v15 = 56;
  v16 = 192;
  v17 = 1174405120;
  return __winRT::__getIids((__winRT *)4, a2, (unsigned int *)&v4, a3, (struct Platform::Guid **)0x37DC63CCE894A67DLL);
}

```

## disassembly

```asm
0x14000e0b0  push    rbp
0x14000e0b2  mov     rbp, rsp
0x14000e0b5  sub     rsp, 70h
0x14000e0b9  mov     rax, cs:__security_cookie
0x14000e0c0  xor     rax, rsp
0x14000e0c3  mov     [rbp+var_10], rax
0x14000e0c7  mov     r9, r8; struct __s_GUID *
0x14000e0ca  mov     dword ptr [rbp+var_50], 0E894A67Dh
0x14000e0d1  lea     r8, [rbp+var_50]; unsigned int *
0x14000e0d5  mov     dword ptr [rbp+var_50+4], 37DC63CCh
0x14000e0dc  mov     ecx, 4; this
0x14000e0e1  mov     [rbp+var_48], 26170D8Ah
0x14000e0e8  mov     [rbp+var_44], 3A1DA61Ch
0x14000e0ef  mov     [rbp+var_40], 30D5A829h
0x14000e0f6  mov     [rbp+var_3C], 40267FA4h
0x14000e0fd  mov     [rbp+var_38], 5BD7BB83h
0x14000e104  mov     [rbp+var_34], 9EA94EAEh
0x14000e10b  mov     [rbp+var_30], 7E641D17h
0x14000e112  mov     [rbp+var_2C], 5011625Dh
0x14000e119  mov     [rbp+var_28], 1DDABFBEh
0x14000e120  mov     [rbp+var_24], 16C28F0h
0x14000e127  mov     [rbp+var_20], 38h ; '8'
0x14000e12f  mov     [rbp+var_18], 0C0h
0x14000e136  mov     [rbp+var_14], 46000000h
0x14000e13d  call    ?__getIids@__winRT@@YAJHPEAKPEBU__s_GUID@@PEAPEAVGuid@Platform@@@Z; __winRT::__getIids(int,ulong *,__s_GUID const *,Platform::Guid * *)
0x14000e142  mov     rcx, [rbp+var_10]
0x14000e146  xor     rcx, rsp; StackCookie
0x14000e149  call    __security_check_cookie
0x14000e14e  add     rsp, 70h
0x14000e152  pop     rbp
0x14000e153  retn
```
