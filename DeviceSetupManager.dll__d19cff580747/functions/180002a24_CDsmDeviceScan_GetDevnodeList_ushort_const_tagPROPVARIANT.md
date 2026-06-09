# CDsmDeviceScan::GetDevnodeList(ushort const *,tagPROPVARIANT *)

- ea: `0x180002a24`
- end: `0x180002b96`
- name: `?GetDevnodeList@CDsmDeviceScan@@SAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `370`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz, struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009928`
- `0x180012a48`
- `0x180030fac`

## callees

- `0x180002a24`
- `0x180004080`
- `0x18001af70`
- `0x180025294`
- `0x180027ba8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180002a8c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180002a8c`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180002b6e`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180002b6e`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180002b19`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180002b19`

## pseudocode

```c
__int64 __fastcall CDsmDeviceScan::GetDevnodeList(LPCOLESTR lpsz, PROPVARIANT *a2)
{
  int Objects; // ebx
  unsigned int v6; // [rsp+40h] [rbp-19h] BYREF
  struct _DEV_OBJECT *v7; // [rsp+48h] [rbp-11h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-9h] BYREF
  int v9; // [rsp+60h] [rbp+7h] BYREF
  DEVPROPKEY v10; // [rsp+68h] [rbp+Fh]
  int v11; // [rsp+7Ch] [rbp+23h]
  __int64 v12; // [rsp+80h] [rbp+27h]
  int v13; // [rsp+88h] [rbp+2Fh]
  int v14; // [rsp+8Ch] [rbp+33h]
  GUID *p_pclsid; // [rsp+90h] [rbp+37h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids, lpsz);
  pclsid = 0;
  Objects = CLSIDFromString(lpsz, &pclsid);
  if ( Objects >= 0 )
  {
    v10 = DEVPKEY_Device_ContainerId;
    v9 = 2;
    p_pclsid = &pclsid;
    v11 = 0;
    v12 = 0;
    v13 = 13;
    v14 = 16;
    v6 = 0;
    v7 = 0;
    Objects = DevGetObjects(3, 0, 0, 0, 1, &v9, &v6, &v7);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids,
        (unsigned int)Objects,
        v6);
    if ( Objects >= 0 )
    {
      Objects = CDsmDeviceScan::_DevObjectsToPropVariantList(v6, v7, a2);
      DevFreeObjects(v6, v7);
    }
  }
  return (unsigned int)Objects;
}

```

## disassembly

```asm
0x180002a24  mov     [rsp-8+arg_10], rbx
0x180002a29  push    rbp
0x180002a2a  push    rdi
0x180002a2b  push    r14
0x180002a2d  lea     rbp, [rsp-47h]
0x180002a32  sub     rsp, 0A0h
0x180002a39  mov     rax, cs:__security_cookie
0x180002a40  xor     rax, rsp
0x180002a43  mov     [rbp+57h+var_18], rax
0x180002a47  mov     rdi, rdx
0x180002a4a  mov     rbx, rcx
0x180002a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a54  lea     r14, WPP_GLOBAL_Control
0x180002a5b  cmp     rcx, r14
0x180002a5e  jz      short loc_180002A7E
0x180002a60  test    byte ptr [rcx+1Ch], 1
0x180002a64  jz      short loc_180002A7E
0x180002a66  mov     rcx, [rcx+10h]
0x180002a6a  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x180002a71  mov     edx, 12h
0x180002a76  mov     r9, rbx
0x180002a79  call    WPP_SF_S
0x180002a7e  xorps   xmm0, xmm0
0x180002a81  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180002a85  mov     rcx, rbx; lpsz
0x180002a88  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180002a8c  call    cs:__imp_CLSIDFromString
0x180002a92  mov     ebx, eax
0x180002a94  test    eax, eax
0x180002a96  js      loc_180002B74
0x180002a9c  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x180002aa2  xor     edx, edx
0x180002aa4  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x180002aab  mov     [rbp+57h+var_38], eax
0x180002aae  xor     r9d, r9d
0x180002ab1  lea     rax, [rbp+57h+pclsid]
0x180002ab5  mov     [rbp+57h+var_50], 2
0x180002abc  mov     [rbp+57h+var_20], rax
0x180002ac0  lea     ecx, [rdx+3]
0x180002ac3  lea     rax, [rbp+57h+var_68]
0x180002ac7  mov     [rbp+57h+var_34], 0
0x180002ace  mov     [rsp+0B0h+var_78], rax
0x180002ad3  xor     r8d, r8d
0x180002ad6  lea     rax, [rbp+57h+var_70]
0x180002ada  mov     [rbp+57h+var_30], 0
0x180002ae2  mov     [rsp+0B0h+var_80], rax
0x180002ae7  lea     rax, [rbp+57h+var_50]
0x180002aeb  mov     [rsp+0B0h+var_88], rax
0x180002af0  mov     [rsp+0B0h+var_90], 1
0x180002af8  movups  [rbp+57h+var_48], xmm0
0x180002afc  mov     [rbp+57h+var_28], 0Dh
0x180002b03  mov     [rbp+57h+var_24], 10h
0x180002b0a  mov     [rbp+57h+var_70], 0
0x180002b11  mov     [rbp+57h+var_68], 0
0x180002b19  call    cs:__imp_DevGetObjects
0x180002b1f  mov     ebx, eax
0x180002b21  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b28  cmp     rcx, r14
0x180002b2b  jz      short loc_180002B52
0x180002b2d  test    byte ptr [rcx+1Ch], 1
0x180002b31  jz      short loc_180002B52
0x180002b33  mov     eax, [rbp+57h+var_70]
0x180002b36  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x180002b3d  mov     rcx, [rcx+10h]
0x180002b41  mov     edx, 13h
0x180002b46  mov     r9d, ebx
0x180002b49  mov     [rsp+0B0h+var_90], eax
0x180002b4d  call    WPP_SF_Dd
0x180002b52  test    ebx, ebx
0x180002b54  js      short loc_180002B74
0x180002b56  mov     rdx, [rbp+57h+var_68]; struct _DEV_OBJECT *
0x180002b5a  mov     r8, rdi; struct tagPROPVARIANT *
0x180002b5d  mov     ecx, [rbp+57h+var_70]; unsigned int
0x180002b60  call    ?_DevObjectsToPropVariantList@CDsmDeviceScan@@CAJKPEBU_DEV_OBJECT@@PEAUtagPROPVARIANT@@@Z; CDsmDeviceScan::_DevObjectsToPropVariantList(ulong,_DEV_OBJECT const *,tagPROPVARIANT *)
0x180002b65  mov     rdx, [rbp+57h+var_68]
0x180002b69  mov     ebx, eax
0x180002b6b  mov     ecx, [rbp+57h+var_70]
0x180002b6e  call    cs:__imp_DevFreeObjects
0x180002b74  mov     eax, ebx
0x180002b76  mov     rcx, [rbp+57h+var_18]
0x180002b7a  xor     rcx, rsp; StackCookie
0x180002b7d  call    __security_check_cookie
0x180002b82  mov     rbx, [rsp+0B0h+arg_10]
0x180002b8a  add     rsp, 0A0h
0x180002b91  pop     r14
0x180002b93  pop     rdi
0x180002b94  pop     rbp
0x180002b95  retn
```
