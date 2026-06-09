# CCacheStore::MigratePartitionEntry(unsigned __int64,unsigned __int64,ulong,unsigned __int64,ushort const *,ulong,PartitionSets,ushort const *,_FILETIME,ulong *,CWxString *,CWxString *)

- ea: `0x1801a8bac`
- end: `0x1801a8e69`
- name: `?MigratePartitionEntry@CCacheStore@@QEAAJ_K0K0PEBGKW4PartitionSets@@1U_FILETIME@@PEAKPEAVCWxString@@5@Z`
- size: `701`
- prototype: `int __high(unsigned __int64, unsigned __int64, unsigned int, unsigned __int64, const unsigned __int16 *, unsigned int, enum PartitionSets, const unsigned __int16 *, struct _FILETIME, unsigned int *, struct CWxString *, struct CWxString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1801a90c8`

## callees

- `0x18007e550`
- `0x18007ec9c`
- `0x18014a7a0`
- `0x1801a8bac`
- `0x1801a8e70`
- `0x1801e3048`
- `0x1801e3c24`

## import_xrefs

- `ESENT!JetSetColumn` at `0x1801a8d13`
- `ESENT!JetSetColumn` at `0x1801a8d4b`
- `ESENT!JetSetColumn` at `0x1801a8dab`
- `ESENT!JetSetColumn` at `0x1801a8d13`
- `ESENT!JetSetColumn` at `0x1801a8d4b`
- `ESENT!JetSetColumn` at `0x1801a8dab`
- `ESENT!JetRetrieveColumn` at `0x1801a8c8a`
- `ESENT!JetRetrieveColumn` at `0x1801a8c8a`
- `ESENT!JetUpdate` at `0x1801a8ddc`
- `ESENT!JetUpdate` at `0x1801a8ddc`
- `ESENT!JetPrepareUpdate` at `0x1801a8c42`
- `ESENT!JetPrepareUpdate` at `0x1801a8ccd`
- `ESENT!JetPrepareUpdate` at `0x1801a8c42`
- `ESENT!JetPrepareUpdate` at `0x1801a8ccd`

## pseudocode

```c
__int64 __fastcall CCacheStore::MigratePartitionEntry(
        __int64 a1,
        JET_SESID a2,
        JET_TABLEID a3,
        unsigned int a4,
        unsigned __int64 a5,
        unsigned __int16 *a6,
        unsigned int a7,
        char a8,
        unsigned __int16 *a9,
        __int64 a10,
        JET_COLUMNID *a11,
        struct CWxString *a12,
        struct CWxString *a13)
{
  unsigned __int16 *v15; // r13
  JET_COLUMNID *v16; // r14
  JET_ERR v17; // eax
  int v18; // ebx
  JET_ERR v19; // eax
  JET_ERR v21; // eax
  JET_ERR v22; // eax
  JET_ERR v23; // eax
  JET_ERR v24; // eax
  CCacheStore *v25; // rcx
  struct CWxString *v27; // [rsp+50h] [rbp-30h]
  struct CWxString *v28; // [rsp+58h] [rbp-28h]
  unsigned int pcbActual; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int64 pvData; // [rsp+68h] [rbp-18h] BYREF
  __int64 v31; // [rsp+70h] [rbp-10h] BYREF

  v15 = a9;
  v16 = a11;
  v31 = a10;
  v28 = a12;
  v27 = a13;
  pvData = 0;
  pcbActual = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_q(1036, 60, &WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, a5);
  v17 = JetPrepareUpdate(a2, a3, 0);
  v18 = HRESULTFromJET_ERR(v17, 1);
  if ( v18 >= 0 )
  {
    v19 = JetRetrieveColumn(a2, a3, *v16, &pvData, 8u, &pcbActual, 1u, 0);
    v18 = HRESULTFromJET_ERR(v19, 1);
    if ( v18 < 0 )
      goto LABEL_6;
    v18 = SetStringColumn(a2, a3, v16[1], a6);
    if ( v18 < 0 )
      goto LABEL_6;
    v21 = JetSetColumn(a2, a3, v16[2], &a7, 4u, 0, 0);
    v18 = HRESULTFromJET_ERR(v21, 1);
    if ( v18 < 0
      || (v22 = JetSetColumn(a2, a3, v16[3], &a8, 4u, 0, 0), v18 = HRESULTFromJET_ERR(v22, 1), v18 < 0)
      || (v18 = SetStringColumn(a2, a3, v16[4], v15), v18 < 0)
      || (v23 = JetSetColumn(a2, a3, v16[5], &v31, 8u, 0, 0), v18 = HRESULTFromJET_ERR(v23, 1), v18 < 0)
      || (v24 = JetUpdate(a2, a3, 0, 0, 0), v18 = HRESULTFromJET_ERR(v24, 1), v18 < 0) )
    {
LABEL_6:
      JetPrepareUpdate(a2, a3, 3u);
    }
    else
    {
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_qP(1036, 61, &WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, a5, pvData);
      return (unsigned int)CCacheStore::MigratePartitionRenameTables(v25, a2, a4, a5, pvData, a7, v28, v27);
    }
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1801a8bac  push    rbp
0x1801a8bae  push    rbx
0x1801a8baf  push    rsi
0x1801a8bb0  push    rdi
0x1801a8bb1  push    r12
0x1801a8bb3  push    r13
0x1801a8bb5  push    r14
0x1801a8bb7  mov     rbp, rsp
0x1801a8bba  sub     rsp, 80h
0x1801a8bc1  mov     rax, cs:__security_cookie
0x1801a8bc8  xor     rax, rsp
0x1801a8bcb  mov     [rbp+var_8], rax
0x1801a8bcf  mov     rax, [rbp+arg_48]
0x1801a8bd6  mov     rsi, r8
0x1801a8bd9  mov     r12, [rbp+arg_28]
0x1801a8bdd  mov     rdi, rdx
0x1801a8be0  mov     r13, [rbp+arg_40]
0x1801a8be7  mov     r14, [rbp+arg_50]
0x1801a8bee  mov     [rbp+var_10], rax
0x1801a8bf2  mov     rax, [rbp+arg_58]
0x1801a8bf9  mov     [rbp+var_28], rax
0x1801a8bfd  mov     rax, [rbp+arg_60]
0x1801a8c04  mov     [rbp+var_30], rax
0x1801a8c08  xor     eax, eax
0x1801a8c0a  mov     [rbp+var_34], eax
0x1801a8c0d  mov     [rbp+pvData], rax
0x1801a8c11  mov     [rbp+var_20], eax
0x1801a8c14  mov     [rbp+var_40], r9d
0x1801a8c18  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a8c1f  jz      short loc_1801A8C39
0x1801a8c21  mov     r9, [rbp+arg_20]
0x1801a8c25  lea     edx, [rax+3Ch]
0x1801a8c28  mov     ecx, 40Ch
0x1801a8c2d  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1801a8c34  call    WPP_SF_q
0x1801a8c39  xor     r8d, r8d; prep
0x1801a8c3c  mov     rdx, rsi; tableid
0x1801a8c3f  mov     rcx, rdi; sesid
0x1801a8c42  call    cs:__imp_JetPrepareUpdate
0x1801a8c48  mov     ecx, eax; int
0x1801a8c4a  mov     edx, 1; int
0x1801a8c4f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a8c54  mov     ebx, eax
0x1801a8c56  test    eax, eax
0x1801a8c58  js      short loc_1801A8CD3
0x1801a8c5a  mov     r8d, [r14]; columnid
0x1801a8c5d  lea     rax, [rbp+var_20]
0x1801a8c61  mov     [rsp+80h+pretinfo], 0; pretinfo
0x1801a8c6a  lea     r9, [rbp+pvData]; pvData
0x1801a8c6e  mov     ebx, 1
0x1801a8c73  mov     rdx, rsi; tableid
0x1801a8c76  mov     [rsp+80h+grbit], ebx; grbit
0x1801a8c7a  mov     rcx, rdi; sesid
0x1801a8c7d  mov     [rsp+80h+pcbActual], rax; pcbActual
0x1801a8c82  mov     [rsp+80h+cbData], 8; cbData
0x1801a8c8a  call    cs:__imp_JetRetrieveColumn
0x1801a8c90  mov     ecx, eax; int
0x1801a8c92  mov     edx, ebx; int
0x1801a8c94  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a8c99  mov     ebx, eax
0x1801a8c9b  test    eax, eax
0x1801a8c9d  js      short loc_1801A8CC1
0x1801a8c9f  mov     r8d, [r14+4]; columnid
0x1801a8ca3  mov     r9, r12; pvData
0x1801a8ca6  mov     rdx, rsi; tableid
0x1801a8ca9  mov     rcx, rdi; sesid
0x1801a8cac  call    ?SetStringColumn@@YAJ_K0KPEBG@Z; SetStringColumn(unsigned __int64,unsigned __int64,ulong,ushort const *)
0x1801a8cb1  xor     r12d, r12d
0x1801a8cb4  mov     ebx, eax
0x1801a8cb6  test    eax, eax
0x1801a8cb8  jns     short loc_1801A8CF3
0x1801a8cba  mov     [rbp+var_34], 0D1Ch
0x1801a8cc1  mov     r8d, 3; prep
0x1801a8cc7  mov     rdx, rsi; tableid
0x1801a8cca  mov     rcx, rdi; sesid
0x1801a8ccd  call    cs:__imp_JetPrepareUpdate
0x1801a8cd3  mov     eax, ebx
0x1801a8cd5  mov     rcx, [rbp+var_8]
0x1801a8cd9  xor     rcx, rsp; StackCookie
0x1801a8cdc  call    __security_check_cookie
0x1801a8ce1  add     rsp, 80h
0x1801a8ce8  pop     r14
0x1801a8cea  pop     r13
0x1801a8cec  pop     r12
0x1801a8cee  pop     rdi
0x1801a8cef  pop     rsi
0x1801a8cf0  pop     rbx
0x1801a8cf1  pop     rbp
0x1801a8cf2  retn
0x1801a8cf3  mov     r8d, [r14+8]; columnid
0x1801a8cf7  lea     r9, [rbp+arg_30]; pvData
0x1801a8cfb  mov     qword ptr [rsp+80h+grbit], r12; psetinfo
0x1801a8d00  mov     rdx, rsi; tableid
0x1801a8d03  mov     dword ptr [rsp+80h+pcbActual], r12d; grbit
0x1801a8d08  mov     rcx, rdi; sesid
0x1801a8d0b  mov     [rsp+80h+cbData], 4; cbData
0x1801a8d13  call    cs:__imp_JetSetColumn
0x1801a8d19  mov     ecx, eax; int
0x1801a8d1b  mov     edx, 1; int
0x1801a8d20  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a8d25  mov     ebx, eax
0x1801a8d27  test    eax, eax
0x1801a8d29  js      short loc_1801A8CC1
0x1801a8d2b  mov     r8d, [r14+0Ch]; columnid
0x1801a8d2f  lea     r9, [rbp+arg_38]; pvData
0x1801a8d33  mov     qword ptr [rsp+80h+grbit], r12; psetinfo
0x1801a8d38  mov     rdx, rsi; tableid
0x1801a8d3b  mov     dword ptr [rsp+80h+pcbActual], r12d; grbit
0x1801a8d40  mov     rcx, rdi; sesid
0x1801a8d43  mov     [rsp+80h+cbData], 4; cbData
0x1801a8d4b  call    cs:__imp_JetSetColumn
0x1801a8d51  mov     ecx, eax; int
0x1801a8d53  mov     edx, 1; int
0x1801a8d58  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a8d5d  mov     ebx, eax
0x1801a8d5f  test    eax, eax
0x1801a8d61  js      loc_1801A8CC1
0x1801a8d67  mov     r8d, [r14+10h]; columnid
0x1801a8d6b  mov     r9, r13; pvData
0x1801a8d6e  mov     rdx, rsi; tableid
0x1801a8d71  mov     rcx, rdi; sesid
0x1801a8d74  call    ?SetStringColumn@@YAJ_K0KPEBG@Z; SetStringColumn(unsigned __int64,unsigned __int64,ulong,ushort const *)
0x1801a8d79  mov     ebx, eax
0x1801a8d7b  test    eax, eax
0x1801a8d7d  jns     short loc_1801A8D8B
0x1801a8d7f  mov     [rbp+var_34], 0D31h
0x1801a8d86  jmp     loc_1801A8CC1
0x1801a8d8b  mov     r8d, [r14+14h]; columnid
0x1801a8d8f  lea     r9, [rbp+var_10]; pvData
0x1801a8d93  mov     qword ptr [rsp+80h+grbit], r12; psetinfo
0x1801a8d98  mov     rdx, rsi; tableid
0x1801a8d9b  mov     dword ptr [rsp+80h+pcbActual], r12d; grbit
0x1801a8da0  mov     rcx, rdi; sesid
0x1801a8da3  mov     [rsp+80h+cbData], 8; cbData
0x1801a8dab  call    cs:__imp_JetSetColumn
0x1801a8db1  mov     r14d, 1
0x1801a8db7  mov     ecx, eax; int
0x1801a8db9  mov     edx, r14d; int
0x1801a8dbc  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a8dc1  mov     ebx, eax
0x1801a8dc3  test    eax, eax
0x1801a8dc5  js      loc_1801A8CC1
0x1801a8dcb  xor     r9d, r9d; cbBookmark
0x1801a8dce  mov     qword ptr [rsp+80h+cbData], r12; pcbActual
0x1801a8dd3  xor     r8d, r8d; pvBookmark
0x1801a8dd6  mov     rdx, rsi; tableid
0x1801a8dd9  mov     rcx, rdi; sesid
0x1801a8ddc  call    cs:__imp_JetUpdate
0x1801a8de2  mov     ecx, eax; int
0x1801a8de4  mov     edx, r14d; int
0x1801a8de7  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a8dec  mov     ebx, eax
0x1801a8dee  test    eax, eax
0x1801a8df0  js      loc_1801A8CC1
0x1801a8df6  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a8dfd  jz      short loc_1801A8E21
0x1801a8dff  mov     rax, [rbp+pvData]
0x1801a8e03  lea     edx, [r14+3Ch]
0x1801a8e07  mov     r9, [rbp+arg_20]
0x1801a8e0b  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1801a8e12  mov     ecx, 40Ch
0x1801a8e17  mov     qword ptr [rsp+80h+cbData], rax
0x1801a8e1c  call    WPP_SF_qP
0x1801a8e21  mov     rax, [rbp+var_30]
0x1801a8e25  mov     rdx, rdi; unsigned __int64
0x1801a8e28  mov     r9, [rbp+arg_20]; unsigned __int64
0x1801a8e2c  mov     r8d, [rbp+var_40]; unsigned int
0x1801a8e30  mov     [rsp+80h+pretinfo], rax; struct CWxString *
0x1801a8e35  mov     rax, [rbp+var_28]
0x1801a8e39  mov     qword ptr [rsp+80h+grbit], rax; struct CWxString *
0x1801a8e3e  mov     eax, [rbp+arg_30]
0x1801a8e41  mov     dword ptr [rsp+80h+pcbActual], eax; unsigned int
0x1801a8e45  mov     rax, [rbp+pvData]
0x1801a8e49  mov     qword ptr [rsp+80h+cbData], rax; unsigned __int64
0x1801a8e4e  call    ?MigratePartitionRenameTables@CCacheStore@@QEAAJ_KK00KPEAVCWxString@@1@Z; CCacheStore::MigratePartitionRenameTables(unsigned __int64,ulong,unsigned __int64,unsigned __int64,ulong,CWxString *,CWxString *)
0x1801a8e53  mov     ebx, eax
0x1801a8e55  test    eax, eax
0x1801a8e57  jns     loc_1801A8CD3
0x1801a8e5d  mov     [rbp+var_34], 0D4Ah
0x1801a8e64  jmp     loc_1801A8CD3
```
