# UpdateSpaceUsage(unsigned __int64,unsigned __int64,ulong,ulong,unsigned __int64,bool,unsigned __int64 *)

- ea: `0x180063e3c`
- end: `0x1800641ac`
- name: `?UpdateSpaceUsage@@YAK_K0KK0_NPEA_K@Z`
- size: `880`
- prototype: `unsigned int __usercall@<eax>(JET_SESID sesid@<rcx>, JET_TABLEID tableid@<rdx>, JET_COLUMNID columnid@<r8d>, unsigned int@<r9d>, unsigned __int64, bool, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800749f4`
- `0x180090d90`
- `0x180090f4c`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800082d0`
- `0x180063e3c`
- `0x180064624`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x180063f38`
- `ESENT!JetRetrieveColumns` at `0x180063f38`
- `ESENT!JetEscrowUpdate` at `0x180064022`
- `ESENT!JetEscrowUpdate` at `0x1800640c2`
- `ESENT!JetEscrowUpdate` at `0x180064022`
- `ESENT!JetEscrowUpdate` at `0x1800640c2`

## pseudocode

```c
__int64 __fastcall UpdateSpaceUsage(
        JET_SESID sesid,
        JET_TABLEID tableid,
        JET_COLUMNID columnid,
        JET_COLUMNID a4,
        unsigned __int64 a5,
        bool a6,
        unsigned __int64 *pvOld)
{
  unsigned __int64 *v7; // r12
  unsigned __int64 v12; // rbx
  const wchar_t *v13; // rax
  unsigned int v14; // edi
  CHostedCacheMsgEncoding *v15; // rcx
  __int64 v16; // rdx
  int v17; // ecx
  unsigned int v18; // ebx
  int v19; // edx
  int v20; // eax
  CHostedCacheMsgEncoding *v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // ebx
  int pv; // [rsp+58h] [rbp-61h] BYREF
  unsigned int pcbOldActual; // [rsp+5Ch] [rbp-5Dh] BYREF
  unsigned int v27; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v28[2]; // [rsp+68h] [rbp-51h] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+78h] [rbp-41h] BYREF
  __int64 v30; // [rsp+A8h] [rbp-11h]
  char *v31; // [rsp+B0h] [rbp-9h]
  __int128 v32; // [rsp+B8h] [rbp-1h]
  __int128 v33; // [rsp+C8h] [rbp+Fh]
  int v34; // [rsp+118h] [rbp+5Fh] BYREF
  JET_COLUMNID columnida; // [rsp+120h] [rbp+67h]

  columnida = a4;
  v7 = pvOld;
  *pvOld = 0;
  v12 = a5;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v13 = L"Y";
    if ( !a6 )
      v13 = (const wchar_t *)L"N";
    WPP_SF_IS(*((_QWORD *)WPP_GLOBAL_Control + 12), (unsigned int)L"N", 0, a5, (__int64)v13);
  }
  pcbOldActual = 0;
  pv = 0;
  *(&pretrievecolumn.columnid + 1) = 0;
  v34 = 0;
  pretrievecolumn.pvData = v28;
  *(_OWORD *)&pretrievecolumn.itagSequence = 0;
  LODWORD(pvOld) = 0;
  v33 = 0;
  v27 = 0;
  pretrievecolumn.itagSequence = 1;
  LODWORD(v33) = 1;
  *(_OWORD *)&pretrievecolumn.cbData = 0;
  v28[0] = 0;
  v32 = 0;
  pretrievecolumn.columnid = columnid;
  pretrievecolumn.cbData = 4;
  v30 = a4;
  LODWORD(v32) = 4;
  v31 = (char *)v28 + 4;
  v14 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 2u);
  if ( v14 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_13;
    }
    v16 = 69;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v15 + 12), v16, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids, v14);
LABEL_13:
    v17 = v14;
    return TranslateJetError(v17);
  }
  v19 = HIDWORD(a5);
  if ( a6 )
  {
    if ( v28[0] + v12 >= v28[0] )
    {
      v20 = v12;
      goto LABEL_24;
    }
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return 774;
    }
    v22 = 70;
LABEL_48:
    WPP_SF_(*((_QWORD *)v21 + 12), v22, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids);
    return 774;
  }
  if ( v28[0] < v12 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return 774;
    }
    v22 = 71;
    goto LABEL_48;
  }
  v19 = -HIDWORD(a5);
  v20 = -(int)v12;
LABEL_24:
  pv = v20;
  v34 = v19;
  v14 = JetEscrowUpdate(sesid, tableid, columnid, &pv, 4u, &pvOld, 4u, &pcbOldActual, 0);
  if ( v14 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_13;
    }
    v16 = 72;
    goto LABEL_12;
  }
  if ( a6 )
  {
    if ( (int)pvOld + pv < (unsigned int)pvOld )
      ++v34;
  }
  else if ( (int)pvOld - (int)v12 > (unsigned int)pvOld )
  {
    --v34;
  }
  pcbOldActual = 0;
  v23 = JetEscrowUpdate(sesid, tableid, columnida, &v34, 4u, &v27, 4u, &pcbOldActual, 0);
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 73, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids, v23);
    }
    v17 = v23;
    return TranslateJetError(v17);
  }
  v18 = 0;
  a5 = __PAIR64__(v27, (unsigned int)pvOld);
  *v7 = __PAIR64__(v27, (unsigned int)pvOld);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 74, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids);
  }
  return v18;
}

```

## disassembly

```asm
0x180063e3c  mov     rax, rsp
0x180063e3f  mov     [rax+8], rbx
0x180063e43  mov     [rax+10h], rdi
0x180063e47  mov     [rax+20h], r9d
0x180063e4b  push    rbp
0x180063e4c  push    r12
0x180063e4e  push    r13
0x180063e50  push    r14
0x180063e52  push    r15
0x180063e54  lea     rbp, [rax-47h]
0x180063e58  sub     rsp, 0D0h
0x180063e5f  mov     r12, [rbp+3Fh+arg_30]
0x180063e63  mov     r13d, r8d
0x180063e66  xor     r8d, r8d
0x180063e69  mov     edi, r9d
0x180063e6c  mov     r14, rdx
0x180063e6f  mov     r15, rcx
0x180063e72  mov     [r12], r8
0x180063e76  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e7d  lea     rax, WPP_GLOBAL_Control
0x180063e84  mov     rbx, [rbp+3Fh+arg_20]
0x180063e88  cmp     rcx, rax
0x180063e8b  jz      short loc_180063EC3
0x180063e8d  test    byte ptr [rcx+6Ch], 4
0x180063e91  jz      short loc_180063EC3
0x180063e93  cmp     byte ptr [rcx+69h], 4
0x180063e97  jb      short loc_180063EC3
0x180063e99  cmp     [rbp+3Fh+arg_28], r8b
0x180063e9d  lea     rdx, aN; "N"
0x180063ea4  mov     rcx, [rcx+60h]
0x180063ea8  lea     rax, aY; "Y"
0x180063eaf  cmovz   rax, rdx
0x180063eb3  mov     r9, rbx
0x180063eb6  mov     qword ptr [rsp+0F0h+cbMax], rax
0x180063ebb  call    WPP_SF_IS
0x180063ec0  xor     r8d, r8d
0x180063ec3  xorps   xmm0, xmm0
0x180063ec6  mov     [rbp+3Fh+var_9C], r8d
0x180063eca  mov     ecx, 1
0x180063ecf  mov     [rbp+3Fh+pv], r8d
0x180063ed3  movups  xmmword ptr [rbp+3Fh+pretrievecolumn.columnid], xmm0
0x180063ed7  lea     rax, [rbp+3Fh+var_90]
0x180063edb  mov     [rbp+3Fh+arg_10], r8d
0x180063edf  movups  [rbp+3Fh+var_50], xmm0
0x180063ee3  mov     [rbp+3Fh+pretrievecolumn.pvData], rax
0x180063ee7  lea     r9d, [rcx+1]; cretrievecolumn
0x180063eeb  movups  xmmword ptr [rbp+3Fh+pretrievecolumn.itagSequence], xmm0
0x180063eef  mov     dword ptr [rbp+3Fh+arg_30], r8d
0x180063ef3  lea     rax, [rbp+3Fh+var_90+4]
0x180063ef7  movups  [rbp+3Fh+var_30], xmm0
0x180063efb  mov     [rbp+3Fh+var_98], r8d
0x180063eff  mov     rdx, r14; tableid
0x180063f02  mov     [rbp+3Fh+pretrievecolumn.itagSequence], ecx
0x180063f05  lea     r8, [rbp+3Fh+pretrievecolumn]; pretrievecolumn
0x180063f09  mov     dword ptr [rbp+3Fh+var_30], ecx
0x180063f0c  mov     rcx, r15; sesid
0x180063f0f  movups  xmmword ptr [rbp+3Fh+pretrievecolumn.cbData], xmm0
0x180063f13  mov     [rbp+3Fh+var_90], 0
0x180063f1b  movups  [rbp+3Fh+var_40], xmm0
0x180063f1f  mov     [rbp+3Fh+pretrievecolumn.columnid], r13d
0x180063f23  mov     [rbp+3Fh+pretrievecolumn.cbData], 4
0x180063f2a  mov     dword ptr [rbp+3Fh+var_50], edi
0x180063f2d  mov     dword ptr [rbp+3Fh+var_40], 4
0x180063f34  mov     qword ptr [rbp+3Fh+var_50+8], rax
0x180063f38  call    cs:__imp_JetRetrieveColumns
0x180063f3e  mov     edi, eax
0x180063f40  test    eax, eax
0x180063f42  jz      short loc_180063F89
0x180063f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180063f4b  lea     rax, WPP_GLOBAL_Control
0x180063f52  cmp     rcx, rax
0x180063f55  jz      short loc_180063F7B
0x180063f57  test    byte ptr [rcx+6Ch], 4
0x180063f5b  jz      short loc_180063F7B
0x180063f5d  cmp     byte ptr [rcx+69h], 1
0x180063f61  jb      short loc_180063F7B
0x180063f63  mov     edx, 45h ; 'E'
0x180063f68  mov     rcx, [rcx+60h]
0x180063f6c  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180063f73  mov     r9d, edi
0x180063f76  call    WPP_SF_d
0x180063f7b  mov     ecx, edi; int
0x180063f7d  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180063f82  mov     ebx, eax
0x180063f84  jmp     loc_18006418D
0x180063f89  cmp     [rbp+3Fh+arg_28], 0
0x180063f8d  mov     edx, dword ptr [rbp+3Fh+arg_20+4]
0x180063f90  jz      short loc_180063FD8
0x180063f92  mov     rax, [rbp+3Fh+var_90]
0x180063f96  lea     rcx, [rax+rbx]
0x180063f9a  cmp     rcx, rax
0x180063f9d  jb      short loc_180063FA3
0x180063f9f  mov     eax, ebx
0x180063fa1  jmp     short loc_180063FE8
0x180063fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180063faa  lea     rax, WPP_GLOBAL_Control
0x180063fb1  cmp     rcx, rax
0x180063fb4  jz      loc_180064188
0x180063fba  test    byte ptr [rcx+6Ch], 4
0x180063fbe  jz      loc_180064188
0x180063fc4  cmp     byte ptr [rcx+69h], 1
0x180063fc8  jb      loc_180064188
0x180063fce  mov     edx, 46h ; 'F'
0x180063fd3  jmp     loc_180064178
0x180063fd8  cmp     [rbp+3Fh+var_90], rbx
0x180063fdc  jb      loc_180064154
0x180063fe2  neg     edx
0x180063fe4  mov     eax, ebx
0x180063fe6  neg     eax
0x180063fe8  mov     [rsp+0F0h+grbit], 0; grbit
0x180063ff0  lea     r9, [rbp+3Fh+pv]; pv
0x180063ff4  mov     [rbp+3Fh+pv], eax
0x180063ff7  mov     ecx, 4
0x180063ffc  lea     rax, [rbp+3Fh+var_9C]
0x180064000  mov     [rbp+3Fh+arg_10], edx
0x180064003  mov     [rsp+0F0h+pcbOldActual], rax; pcbOldActual
0x180064008  mov     r8d, r13d; columnid
0x18006400b  mov     [rsp+0F0h+cbOldMax], ecx; cbOldMax
0x18006400f  lea     rax, [rbp+3Fh+arg_30]
0x180064013  mov     [rsp+0F0h+pvOld], rax; pvOld
0x180064018  mov     rdx, r14; tableid
0x18006401b  mov     [rsp+0F0h+cbMax], ecx; cbMax
0x18006401f  mov     rcx, r15; sesid
0x180064022  call    cs:__imp_JetEscrowUpdate
0x180064028  mov     edi, eax
0x18006402a  test    eax, eax
0x18006402c  jz      short loc_180064063
0x18006402e  mov     rcx, cs:WPP_GLOBAL_Control
0x180064035  lea     rax, WPP_GLOBAL_Control
0x18006403c  cmp     rcx, rax
0x18006403f  jz      loc_180063F7B
0x180064045  test    byte ptr [rcx+6Ch], 4
0x180064049  jz      loc_180063F7B
0x18006404f  cmp     byte ptr [rcx+69h], 1
0x180064053  jb      loc_180063F7B
0x180064059  mov     edx, 48h ; 'H'
0x18006405e  jmp     loc_180063F68
0x180064063  cmp     [rbp+3Fh+arg_28], 0
0x180064067  jz      short loc_180064079
0x180064069  mov     ecx, [rbp+3Fh+pv]
0x18006406c  add     ecx, dword ptr [rbp+3Fh+arg_30]
0x18006406f  cmp     ecx, dword ptr [rbp+3Fh+arg_30]
0x180064072  jnb     short loc_180064086
0x180064074  inc     [rbp+3Fh+arg_10]
0x180064077  jmp     short loc_180064086
0x180064079  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x18006407c  sub     eax, ebx
0x18006407e  cmp     eax, dword ptr [rbp+3Fh+arg_30]
0x180064081  jbe     short loc_180064086
0x180064083  dec     [rbp+3Fh+arg_10]
0x180064086  mov     r8d, [rbp+3Fh+columnid]; columnid
0x18006408a  lea     rax, [rbp+3Fh+var_9C]
0x18006408e  mov     [rsp+0F0h+grbit], 0; grbit
0x180064096  lea     r9, [rbp+3Fh+arg_10]; pv
0x18006409a  mov     [rsp+0F0h+pcbOldActual], rax; pcbOldActual
0x18006409f  mov     edi, 4
0x1800640a4  lea     rax, [rbp+3Fh+var_98]
0x1800640a8  mov     [rsp+0F0h+cbOldMax], edi; cbOldMax
0x1800640ac  mov     [rsp+0F0h+pvOld], rax; pvOld
0x1800640b1  mov     rdx, r14; tableid
0x1800640b4  mov     rcx, r15; sesid
0x1800640b7  mov     [rsp+0F0h+cbMax], edi; cbMax
0x1800640bb  mov     [rbp+3Fh+var_9C], 0
0x1800640c2  call    cs:__imp_JetEscrowUpdate
0x1800640c8  mov     ebx, eax
0x1800640ca  test    eax, eax
0x1800640cc  jz      short loc_18006410A
0x1800640ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800640d5  lea     rax, WPP_GLOBAL_Control
0x1800640dc  cmp     rcx, rax
0x1800640df  jz      short loc_180064103
0x1800640e1  test    [rcx+6Ch], dil
0x1800640e5  jz      short loc_180064103
0x1800640e7  cmp     byte ptr [rcx+69h], 1
0x1800640eb  jb      short loc_180064103
0x1800640ed  mov     rcx, [rcx+60h]
0x1800640f1  lea     edx, [rdi+45h]
0x1800640f4  mov     r9d, ebx
0x1800640f7  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x1800640fe  call    WPP_SF_d
0x180064103  mov     ecx, ebx
0x180064105  jmp     loc_180063F7D
0x18006410a  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x18006410d  xor     ebx, ebx
0x18006410f  mov     dword ptr [rbp+3Fh+arg_20], eax
0x180064112  mov     eax, [rbp+3Fh+var_98]
0x180064115  mov     dword ptr [rbp+3Fh+arg_20+4], eax
0x180064118  mov     r9, [rbp+3Fh+arg_20]
0x18006411c  mov     [r12], r9
0x180064120  mov     rcx, cs:WPP_GLOBAL_Control
0x180064127  lea     rax, WPP_GLOBAL_Control
0x18006412e  cmp     rcx, rax
0x180064131  jz      short loc_18006418D
0x180064133  test    [rcx+6Ch], dil
0x180064137  jz      short loc_18006418D
0x180064139  cmp     [rcx+69h], dil
0x18006413d  jb      short loc_18006418D
0x18006413f  mov     rcx, [rcx+60h]
0x180064143  lea     edx, [rbx+4Ah]
0x180064146  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x18006414d  call    WPP_SF_q
0x180064152  jmp     short loc_18006418D
0x180064154  mov     rcx, cs:WPP_GLOBAL_Control
0x18006415b  lea     rax, WPP_GLOBAL_Control
0x180064162  cmp     rcx, rax
0x180064165  jz      short loc_180064188
0x180064167  test    byte ptr [rcx+6Ch], 4
0x18006416b  jz      short loc_180064188
0x18006416d  cmp     byte ptr [rcx+69h], 1
0x180064171  jb      short loc_180064188
0x180064173  mov     edx, 47h ; 'G'
0x180064178  mov     rcx, [rcx+60h]
0x18006417c  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180064183  call    WPP_SF_
0x180064188  mov     ebx, 306h
0x18006418d  lea     r11, [rsp+0F0h+var_20]
0x180064195  mov     eax, ebx
0x180064197  mov     rbx, [r11+30h]
0x18006419b  mov     rdi, [r11+38h]
0x18006419f  mov     rsp, r11
0x1800641a2  pop     r15
0x1800641a4  pop     r14
0x1800641a6  pop     r13
0x1800641a8  pop     r12
0x1800641aa  pop     rbp
0x1800641ab  retn
```
