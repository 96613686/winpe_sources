# CDsmDeviceTree::PopulateDeviceTree(ushort const *)

- ea: `0x180002c90`
- end: `0x180002ee0`
- name: `?PopulateDeviceTree@CDsmDeviceTree@@QEAAJPEBG@Z`
- size: `592`
- prototype: `__int64 __fastcall(CDsmDeviceTree *__hidden this, LPCOLESTR lpsz)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800191b0`

## callees

- `0x180002c90`
- `0x180002ef0`
- `0x180003ec0`
- `0x180004080`
- `0x180007190`
- `0x18001af70`
- `0x180021790`
- `0x180022070`
- `0x180025294`
- `0x180027ba8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002eb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002eb5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180002d34`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180002d34`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180002e16`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180002e16`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180002db5`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180002db5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDsmDeviceTree::PopulateDeviceTree(CDsmDeviceTree *this, LPCOLESTR lpsz)
{
  PVOID *v4; // rcx
  int Objects; // edi
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  unsigned int v8; // esi
  __int64 v10; // [rsp+20h] [rbp-69h]
  unsigned int v11; // [rsp+40h] [rbp-49h] BYREF
  struct _DEV_OBJECT *v12; // [rsp+48h] [rbp-41h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v14; // [rsp+60h] [rbp-29h]
  GUID pclsid; // [rsp+68h] [rbp-21h] BYREF
  int v16; // [rsp+78h] [rbp-11h] BYREF
  DEVPROPKEY v17; // [rsp+80h] [rbp-9h]
  int v18; // [rsp+94h] [rbp+Bh]
  __int64 v19; // [rsp+98h] [rbp+Fh]
  int v20; // [rsp+A0h] [rbp+17h]
  int v21; // [rsp+A4h] [rbp+1Bh]
  GUID *p_pclsid; // [rsp+A8h] [rbp+1Fh]

  CDsmDeviceTree::_PurgeTree(this);
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_70ed05df840b3b152097d566b29f6267_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  *(_OWORD *)pvar = 0;
  v14 = 0;
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
    WPP_SF_S(v4[2], 18, &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids, lpsz);
  pclsid = 0;
  Objects = CLSIDFromString(lpsz, &pclsid);
  v6 = 0;
  if ( Objects >= 0 )
  {
    v16 = 2;
    v17 = DEVPKEY_Device_ContainerId;
    v18 = 0;
    v19 = 0;
    v20 = 13;
    v21 = 16;
    p_pclsid = &pclsid;
    v11 = 0;
    v12 = 0;
    Objects = DevGetObjects(3, 0, 0, 0, 1, &v16, &v11, &v12);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LODWORD(v10) = v11;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids,
        (unsigned int)Objects,
        v10);
    }
    if ( Objects < 0 )
      goto LABEL_25;
    Objects = CDsmDeviceScan::_DevObjectsToPropVariantList(v11, v12, pvar);
    DevFreeObjects(v11, v12);
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( Objects >= 0 )
  {
    v8 = (unsigned int)pvar[1];
    if ( LODWORD(pvar[1]) )
    {
      while ( 1 )
      {
        Objects = CDsmDeviceTree::_AddDevice(this, *(const unsigned __int16 **)(v14 + 8LL * v6));
        if ( Objects < 0 )
          break;
        if ( ++v6 >= v8 )
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_18;
        }
      }
    }
    else
    {
LABEL_18:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
        WPP_SF_(v7[2], 11, &WPP_70ed05df840b3b152097d566b29f6267_Traceguids);
      Objects = CDsmDeviceTree::_AssignLevels(this);
      if ( Objects >= 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_70ed05df840b3b152097d566b29f6267_Traceguids,
          *((unsigned int *)this + 2));
    }
  }
LABEL_25:
  PropVariantClear(pvar);
  return (unsigned int)Objects;
}

```

## disassembly

```asm
0x180002c90  mov     [rsp-8+arg_10], rbx
0x180002c95  push    rbp
0x180002c96  push    rsi
0x180002c97  push    rdi
0x180002c98  push    r14
0x180002c9a  push    r15
0x180002c9c  lea     rbp, [rsp-37h]
0x180002ca1  sub     rsp, 0C0h
0x180002ca8  mov     rax, cs:__security_cookie
0x180002caf  xor     rax, rsp
0x180002cb2  mov     [rbp+57h+var_30], rax
0x180002cb6  mov     rbx, rdx
0x180002cb9  mov     r14, rcx
0x180002cbc  call    ?_PurgeTree@CDsmDeviceTree@@AEAAXXZ; CDsmDeviceTree::_PurgeTree(void)
0x180002cc1  lea     r15, WPP_GLOBAL_Control
0x180002cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ccf  cmp     rcx, r15
0x180002cd2  jz      short loc_180002CF6
0x180002cd4  test    byte ptr [rcx+1Ch], 1
0x180002cd8  jz      short loc_180002CF6
0x180002cda  mov     edx, 0Ah
0x180002cdf  lea     r8, WPP_70ed05df840b3b152097d566b29f6267_Traceguids
0x180002ce6  mov     rcx, [rcx+10h]
0x180002cea  call    WPP_SF_
0x180002cef  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cf6  xorps   xmm0, xmm0
0x180002cf9  xor     eax, eax
0x180002cfb  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180002cff  mov     [rbp+57h+var_80], rax
0x180002d03  cmp     rcx, r15
0x180002d06  jz      short loc_180002D26
0x180002d08  test    byte ptr [rcx+1Ch], 1
0x180002d0c  jz      short loc_180002D26
0x180002d0e  mov     edx, 12h
0x180002d13  mov     r9, rbx
0x180002d16  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x180002d1d  mov     rcx, [rcx+10h]
0x180002d21  call    WPP_SF_S
0x180002d26  xorps   xmm0, xmm0
0x180002d29  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180002d2d  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180002d31  mov     rcx, rbx; lpsz
0x180002d34  call    cs:__imp_CLSIDFromString
0x180002d3a  mov     edi, eax
0x180002d3c  xor     ebx, ebx
0x180002d3e  test    eax, eax
0x180002d40  js      loc_180002E1C
0x180002d46  mov     [rbp+57h+var_68], 2
0x180002d4d  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x180002d54  movups  [rbp+57h+var_60], xmm0
0x180002d58  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x180002d5e  mov     [rbp+57h+var_50], eax
0x180002d61  mov     [rbp+57h+var_4C], ebx
0x180002d64  mov     [rbp+57h+var_48], rbx
0x180002d68  mov     [rbp+57h+var_40], 0Dh
0x180002d6f  mov     [rbp+57h+var_3C], 10h
0x180002d76  lea     rax, [rbp+57h+pclsid]
0x180002d7a  mov     [rbp+57h+var_38], rax
0x180002d7e  mov     [rbp+57h+var_A0], ebx
0x180002d81  mov     [rbp+57h+var_98], rbx
0x180002d85  lea     rax, [rbp+57h+var_98]
0x180002d89  mov     [rsp+0E0h+var_A8], rax
0x180002d8e  lea     rax, [rbp+57h+var_A0]
0x180002d92  mov     [rsp+0E0h+var_B0], rax
0x180002d97  lea     rax, [rbp+57h+var_68]
0x180002d9b  mov     [rsp+0E0h+var_B8], rax
0x180002da0  mov     dword ptr [rsp+0E0h+var_C0], 1
0x180002da8  xor     r9d, r9d
0x180002dab  xor     r8d, r8d
0x180002dae  xor     edx, edx
0x180002db0  mov     ecx, 3
0x180002db5  call    cs:__imp_DevGetObjects
0x180002dbb  mov     edi, eax
0x180002dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dc4  cmp     rcx, r15
0x180002dc7  jz      short loc_180002DF5
0x180002dc9  test    byte ptr [rcx+1Ch], 1
0x180002dcd  jz      short loc_180002DF5
0x180002dcf  mov     edx, 13h
0x180002dd4  mov     eax, [rbp+57h+var_A0]
0x180002dd7  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180002ddb  mov     r9d, edi
0x180002dde  lea     r8, WPP_43d4499022663c6448c6fdf63854fbee_Traceguids
0x180002de5  mov     rcx, [rcx+10h]
0x180002de9  call    WPP_SF_Dd
0x180002dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180002df5  test    edi, edi
0x180002df7  js      loc_180002EB1
0x180002dfd  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180002e01  mov     rdx, [rbp+57h+var_98]; struct _DEV_OBJECT *
0x180002e05  mov     ecx, [rbp+57h+var_A0]; unsigned int
0x180002e08  call    ?_DevObjectsToPropVariantList@CDsmDeviceScan@@CAJKPEBU_DEV_OBJECT@@PEAUtagPROPVARIANT@@@Z; CDsmDeviceScan::_DevObjectsToPropVariantList(ulong,_DEV_OBJECT const *,tagPROPVARIANT *)
0x180002e0d  mov     edi, eax
0x180002e0f  mov     rdx, [rbp+57h+var_98]
0x180002e13  mov     ecx, [rbp+57h+var_A0]
0x180002e16  call    cs:__imp_DevFreeObjects
0x180002e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e23  test    edi, edi
0x180002e25  js      loc_180002EB1
0x180002e2b  mov     esi, dword ptr [rbp+57h+pvar+8]
0x180002e2e  test    esi, esi
0x180002e30  jz      short loc_180002E57
0x180002e32  mov     eax, ebx
0x180002e34  mov     rdx, [rbp+57h+var_80]
0x180002e38  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x180002e3c  mov     rcx, r14; this
0x180002e3f  call    ?_AddDevice@CDsmDeviceTree@@AEAAJPEBG@Z; CDsmDeviceTree::_AddDevice(ushort const *)
0x180002e44  mov     edi, eax
0x180002e46  test    eax, eax
0x180002e48  js      short loc_180002EB1
0x180002e4a  inc     ebx
0x180002e4c  cmp     ebx, esi
0x180002e4e  jb      short loc_180002E32
0x180002e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e57  cmp     rcx, r15
0x180002e5a  jz      short loc_180002E77
0x180002e5c  test    byte ptr [rcx+1Ch], 1
0x180002e60  jz      short loc_180002E77
0x180002e62  mov     edx, 0Bh
0x180002e67  lea     r8, WPP_70ed05df840b3b152097d566b29f6267_Traceguids
0x180002e6e  mov     rcx, [rcx+10h]
0x180002e72  call    WPP_SF_
0x180002e77  mov     rcx, r14; this
0x180002e7a  call    ?_AssignLevels@CDsmDeviceTree@@AEAAJXZ; CDsmDeviceTree::_AssignLevels(void)
0x180002e7f  mov     edi, eax
0x180002e81  test    eax, eax
0x180002e83  js      short loc_180002EB1
0x180002e85  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e8c  cmp     rcx, r15
0x180002e8f  jz      short loc_180002EB1
0x180002e91  test    byte ptr [rcx+1Ch], 1
0x180002e95  jz      short loc_180002EB1
0x180002e97  mov     edx, 0Ch
0x180002e9c  mov     r9d, [r14+8]
0x180002ea0  lea     r8, WPP_70ed05df840b3b152097d566b29f6267_Traceguids
0x180002ea7  mov     rcx, [rcx+10h]
0x180002eab  call    WPP_SF_d
0x180002eb0  nop
0x180002eb1  lea     rcx, [rbp+57h+pvar]; pvar
0x180002eb5  call    cs:__imp_PropVariantClear
0x180002ebb  mov     eax, edi
0x180002ebd  mov     rcx, [rbp+57h+var_30]
0x180002ec1  xor     rcx, rsp; StackCookie
0x180002ec4  call    __security_check_cookie
0x180002ec9  mov     rbx, [rsp+0E0h+arg_10]
0x180002ed1  add     rsp, 0C0h
0x180002ed8  pop     r15
0x180002eda  pop     r14
0x180002edc  pop     rdi
0x180002edd  pop     rsi
0x180002ede  pop     rbp
0x180002edf  retn
```
