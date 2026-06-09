# ServiceManager::PdcActivatorCallback(void *,_PDC_ACTIVATOR_ERROR_DETAIL,void *,void *)

- ea: `0x18001af10`
- end: `0x18001af86`
- name: `?PdcActivatorCallback@ServiceManager@@CAXPEAXW4_PDC_ACTIVATOR_ERROR_DETAIL@@00@Z`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001af10`

## import_xrefs

- `UMPDC!Pdcv2ActivationClientRenewActivation` at `0x18001af5e`
- `UMPDC!Pdcv2ActivationClientRenewActivation` at `0x18001af5e`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x18001af7b`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x18001af7b`

## string_xrefs

- `0x18001af6c`: `ServiceManager::PdcActivatorCallback`

## pseudocode

```c
void __fastcall ServiceManager::PdcActivatorCallback(__int64 a1, int a2)
{
  int v2; // eax
  _DWORD v3[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v4; // [rsp+28h] [rbp-40h]
  __int128 v5; // [rsp+30h] [rbp-38h]
  __int128 v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+50h] [rbp-18h]
  int v8; // [rsp+78h] [rbp+10h] BYREF

  if ( (unsigned int)(a2 - 100) <= 1 )
  {
    v8 = 0;
    v6 = 0;
    v7 = 0;
    v3[0] = 1;
    v3[1] = 300;
    v4 = 0;
    v5 = 0;
    v2 = Pdcv2ActivationClientRenewActivation(a1, v3, &v8);
    if ( v2 < 0 )
      ZTraceReportIgnoreNoThis(v2 | 0x10000000, "ServiceManager::PdcActivatorCallback", 3369);
  }
}

```

## disassembly

```asm
0x18001af10  mov     r11, rsp
0x18001af13  sub     rsp, 68h
0x18001af17  lea     eax, [rdx-64h]
0x18001af1a  cmp     eax, 1
0x18001af1d  ja      short loc_18001AF81
0x18001af1f  xorps   xmm0, xmm0
0x18001af22  mov     [rsp+68h+arg_8], 0
0x18001af2a  movdqu  [rsp+68h+var_28], xmm0
0x18001af30  mov     qword ptr [r11-18h], 0
0x18001af38  lea     r8, [r11+10h]
0x18001af3c  mov     [rsp+68h+var_48], 1
0x18001af44  lea     rdx, [r11-48h]
0x18001af48  mov     [rsp+68h+var_44], 12Ch
0x18001af50  mov     qword ptr [r11-40h], 0
0x18001af58  movdqu  [rsp+68h+var_38], xmm0
0x18001af5e  call    cs:__imp_Pdcv2ActivationClientRenewActivation
0x18001af64  test    eax, eax
0x18001af66  jns     short loc_18001AF81
0x18001af68  bts     eax, 1Ch
0x18001af6c  lea     rdx, aServicemanager_47; "ServiceManager::PdcActivatorCallback"
0x18001af73  mov     ecx, eax
0x18001af75  mov     r8d, 0D29h
0x18001af7b  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x18001af81  add     rsp, 68h
0x18001af85  retn
```
