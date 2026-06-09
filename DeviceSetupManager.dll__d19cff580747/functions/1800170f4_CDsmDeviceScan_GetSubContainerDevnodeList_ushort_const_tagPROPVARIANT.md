# CDsmDeviceScan::GetSubContainerDevnodeList(ushort const *,tagPROPVARIANT *)

- ea: `0x1800170f4`
- end: `0x18001726b`
- name: `?GetSubContainerDevnodeList@CDsmDeviceScan@@SAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `375`
- prototype: `static int(const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800057f4`

## callees

- `0x180004080`
- `0x1800170f4`
- `0x18001af70`
- `0x180025294`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180017127`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180017127`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180017242`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180017242`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x1800171e6`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x1800171e6`

## pseudocode

```c
__int64 __fastcall CDsmDeviceScan::GetSubContainerDevnodeList(const unsigned __int16 *a1, PROPVARIANT *a2)
{
  int Objects; // ebx
  unsigned int v5; // [rsp+40h] [rbp-49h] BYREF
  struct _DEV_OBJECT *v6; // [rsp+48h] [rbp-41h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-39h] BYREF
  int v8; // [rsp+60h] [rbp-29h] BYREF
  DEVPROPKEY v9; // [rsp+68h] [rbp-21h]
  int v10; // [rsp+7Ch] [rbp-Dh]
  __int64 v11; // [rsp+80h] [rbp-9h]
  int v12; // [rsp+88h] [rbp-1h]
  int v13; // [rsp+8Ch] [rbp+3h]
  GUID *p_pclsid; // [rsp+90h] [rbp+7h]
  int v15; // [rsp+98h] [rbp+Fh]
  DEVPROPKEY v16; // [rsp+A0h] [rbp+17h]
  int v17; // [rsp+B4h] [rbp+2Bh]
  __int64 v18; // [rsp+B8h] [rbp+2Fh]
  __int64 v19; // [rsp+C0h] [rbp+37h]
  __int64 v20; // [rsp+C8h] [rbp+3Fh]

  pclsid = 0;
  Objects = CLSIDFromString(a1, &pclsid);
  if ( Objects >= 0 )
  {
    v9 = DEVPKEY_Device_ContainerId;
    v8 = 2;
    p_pclsid = &pclsid;
    v16 = DEVPKEY_Device_ModelId;
    v12 = 13;
    v19 = 13;
    v10 = 0;
    v11 = 0;
    v13 = 16;
    v15 = 1;
    v17 = 0;
    v18 = 0;
    v20 = 0;
    v5 = 0;
    v6 = 0;
    Objects = DevGetObjects(3, 0, 0, 0, 2, &v8, &v5, &v6);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids,
        (unsigned int)Objects,
        v5);
    if ( Objects >= 0 )
    {
      Objects = CDsmDeviceScan::_DevObjectsToPropVariantList(v5, v6, a2);
      DevFreeObjects(v5, v6);
    }
  }
  return (unsigned int)Objects;
}

```

## disassembly

```asm
0x1800170f4  mov     [rsp-8+arg_10], rbx
0x1800170f9  mov     [rsp-8+arg_18], rdi
0x1800170fe  push    rbp
0x1800170ff  lea     rbp, [rsp-57h]
0x180017104  sub     rsp, 0E0h
0x18001710b  mov     rax, cs:__security_cookie
0x180017112  xor     rax, rsp
0x180017115  mov     [rbp+57h+var_10], rax
0x180017119  mov     rdi, rdx
0x18001711c  xorps   xmm0, xmm0
0x18001711f  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180017123  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180017127  call    cs:__imp_CLSIDFromString
0x18001712d  mov     ebx, eax
0x18001712f  test    eax, eax
0x180017131  js      loc_180017248
0x180017137  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x18001713d  mov     edx, 2
0x180017142  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x180017149  mov     [rbp+57h+var_68], eax
0x18001714c  xor     r9d, r9d
0x18001714f  lea     rax, [rbp+57h+pclsid]
0x180017153  mov     [rbp+57h+var_80], edx
0x180017156  mov     [rbp+57h+var_50], rax
0x18001715a  lea     ecx, [rdx+0Bh]
0x18001715d  mov     eax, cs:DEVPKEY_Device_ModelId.pid
0x180017163  xor     r8d, r8d
0x180017166  mov     [rbp+57h+var_30], eax
0x180017169  lea     rax, [rbp+57h+var_98]
0x18001716d  mov     [rsp+0E0h+var_A8], rax
0x180017172  lea     rax, [rbp+57h+var_A0]
0x180017176  mov     [rsp+0E0h+var_B0], rax
0x18001717b  lea     rax, [rbp+57h+var_80]
0x18001717f  mov     [rsp+0E0h+var_B8], rax
0x180017184  mov     [rsp+0E0h+var_C0], edx
0x180017188  xor     edx, edx
0x18001718a  movups  [rbp+57h+var_78], xmm0
0x18001718e  mov     [rbp+57h+var_58], ecx
0x180017191  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ModelId.fmtid.Data1
0x180017198  mov     [rbp+57h+var_20], rcx
0x18001719c  lea     ecx, [rdx+3]
0x18001719f  mov     [rbp+57h+var_64], 0
0x1800171a6  mov     [rbp+57h+var_60], 0
0x1800171ae  mov     [rbp+57h+var_54], 10h
0x1800171b5  mov     [rbp+57h+var_48], 1
0x1800171bc  movaps  [rbp+57h+var_40], xmm0
0x1800171c0  mov     [rbp+57h+var_2C], 0
0x1800171c7  mov     [rbp+57h+var_28], 0
0x1800171cf  mov     [rbp+57h+var_18], 0
0x1800171d7  mov     [rbp+57h+var_A0], 0
0x1800171de  mov     [rbp+57h+var_98], 0
0x1800171e6  call    cs:__imp_DevGetObjects
0x1800171ec  mov     ebx, eax
0x1800171ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171f5  lea     rax, WPP_GLOBAL_Control
0x1800171fc  cmp     rcx, rax
0x1800171ff  jz      short loc_180017226
0x180017201  test    byte ptr [rcx+1Ch], 1
0x180017205  jz      short loc_180017226
0x180017207  mov     eax, [rbp+57h+var_A0]
0x18001720a  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x180017211  mov     rcx, [rcx+10h]
0x180017215  mov     edx, 15h
0x18001721a  mov     r9d, ebx
0x18001721d  mov     [rsp+0E0h+var_C0], eax
0x180017221  call    WPP_SF_Dd
0x180017226  test    ebx, ebx
0x180017228  js      short loc_180017248
0x18001722a  mov     rdx, [rbp+57h+var_98]; struct _DEV_OBJECT *
0x18001722e  mov     r8, rdi; struct tagPROPVARIANT *
0x180017231  mov     ecx, [rbp+57h+var_A0]; unsigned int
0x180017234  call    ?_DevObjectsToPropVariantList@CDsmDeviceScan@@CAJKPEBU_DEV_OBJECT@@PEAUtagPROPVARIANT@@@Z; CDsmDeviceScan::_DevObjectsToPropVariantList(ulong,_DEV_OBJECT const *,tagPROPVARIANT *)
0x180017239  mov     rdx, [rbp+57h+var_98]
0x18001723d  mov     ebx, eax
0x18001723f  mov     ecx, [rbp+57h+var_A0]
0x180017242  call    cs:__imp_DevFreeObjects
0x180017248  mov     eax, ebx
0x18001724a  mov     rcx, [rbp+57h+var_10]
0x18001724e  xor     rcx, rsp; StackCookie
0x180017251  call    __security_check_cookie
0x180017256  lea     r11, [rsp+0E0h+var_s0]
0x18001725e  mov     rbx, [r11+20h]
0x180017262  mov     rdi, [r11+28h]
0x180017266  mov     rsp, r11
0x180017269  pop     rbp
0x18001726a  retn
```
