# CSynchronizeCallback::_PackageEvent(ushort const *,SYNCMGR_EVENT_LEVEL,SYNCMGR_EVENT_FLAGS,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,SYNCMGR_EVENTINFO *)

- ea: `0x18001210c`
- end: `0x180012360`
- name: `?_PackageEvent@CSynchronizeCallback@@AEAAJPEBGW4SYNCMGR_EVENT_LEVEL@@W4SYNCMGR_EVENT_FLAGS@@00000PEAUSYNCMGR_EVENTINFO@@@Z`
- size: `596`
- prototype: `__int64 __fastcall(CSynchronizeCallback *this, const unsigned __int16 *, enum SYNCMGR_EVENT_LEVEL, enum SYNCMGR_EVENT_FLAGS, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct SYNCMGR_EVENTINFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011d60`

## callees

- `0x180005660`
- `0x18000a8ac`
- `0x18001210c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001218c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001218c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012199`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012199`

## pseudocode

```c
__int64 __fastcall CSynchronizeCallback::_PackageEvent(
        CSynchronizeCallback *this,
        const unsigned __int16 *a2,
        enum SYNCMGR_EVENT_LEVEL a3,
        enum SYNCMGR_EVENT_FLAGS a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        struct SYNCMGR_EVENTINFO *a10)
{
  int v10; // r10d
  __int64 v13; // rdi
  int v14; // r8d
  int v15; // r8d
  _OWORD *v16; // rax
  __int64 v17; // rdx
  _OWORD *v18; // rcx
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  struct SYNCMGR_EVENTINFO *v26; // rax
  _OWORD *v27; // rcx
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  unsigned int v35; // esi
  unsigned __int64 v36; // r11
  _BYTE v38[312]; // [rsp+20h] [rbp-138h] BYREF

  v10 = 0;
  v13 = 2;
  *((_DWORD *)a10 + 69) = 0;
  if ( a4 )
    v10 = -2147024809;
  v14 = a3 - 1;
  if ( v14 )
  {
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( v15 != 1 )
        return (unsigned int)-2147024809;
      *((_DWORD *)a10 + 68) = 4;
    }
    else
    {
      *((_DWORD *)a10 + 68) = 3;
    }
  }
  else
  {
    *((_DWORD *)a10 + 68) = 2;
  }
  if ( v10 >= 0 )
  {
    CoCreateGuid((GUID *)a10 + 16);
    GetSystemTimeAsFileTime((LPFILETIME)((char *)a10 + 2868));
    v16 = (_OWORD *)((char *)this + 28);
    v17 = 2;
    v18 = v38;
    do
    {
      v19 = v16[1];
      *v18 = *v16;
      v20 = v16[2];
      v18[1] = v19;
      v21 = v16[3];
      v18[2] = v20;
      v22 = v16[4];
      v18[3] = v21;
      v23 = v16[5];
      v18[4] = v22;
      v24 = v16[6];
      v18[5] = v23;
      v25 = v16[7];
      v16 += 8;
      v18[6] = v24;
      v18[7] = v25;
      v18 += 8;
      --v17;
    }
    while ( v17 );
    v26 = a10;
    v27 = v38;
    do
    {
      v28 = v27[1];
      *(_OWORD *)v26 = *v27;
      v29 = v27[2];
      *((_OWORD *)v26 + 1) = v28;
      v30 = v27[3];
      *((_OWORD *)v26 + 2) = v29;
      v31 = v27[4];
      *((_OWORD *)v26 + 3) = v30;
      v32 = v27[5];
      *((_OWORD *)v26 + 4) = v31;
      v33 = v27[6];
      *((_OWORD *)v26 + 5) = v32;
      v34 = v27[7];
      v27 += 8;
      *((_OWORD *)v26 + 6) = v33;
      *((_OWORD *)v26 + 7) = v34;
      v26 = (struct SYNCMGR_EVENTINFO *)((char *)v26 + 128);
      --v13;
    }
    while ( v13 );
    if ( a2 )
    {
      v35 = *((_DWORD *)this + 74);
      while ( (unsigned int)v13 < v35 )
      {
        if ( CSyncMgrID::s_AreIDStringsEqual(a2, *(PCNZWCH *)(*((_QWORD *)this + 36) + 8 * v13)) )
        {
          v10 = StringCchCopyW((unsigned __int16 *)a10 + 64, 0x40u, a2);
          if ( v10 < 0 )
            return (unsigned int)v10;
          goto LABEL_20;
        }
        v13 = (unsigned int)(v13 + 1);
      }
      return (unsigned int)-2147024809;
    }
LABEL_20:
    v10 = StringCchCopyW((unsigned __int16 *)a10 + 142, 0x80u, a5);
    if ( v10 >= 0 )
    {
      v10 = StringCchCopyW((unsigned __int16 *)a10 + 270, 0x104u, a6);
      if ( v10 >= 0 )
      {
        if ( !a7 || (v10 = StringCchCopyW((unsigned __int16 *)a10 + 530, 0x80u, a7), v10 >= 0) )
        {
          if ( !a8 || (v10 = StringCchCopyW((unsigned __int16 *)a10 + 658, v36, a8), v10 >= 0) )
          {
            if ( a9 )
              return (unsigned int)StringCchCopyW((unsigned __int16 *)a10 + 918, v36, a9);
          }
        }
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001210c  push    rbx
0x18001210e  push    rbp
0x18001210f  push    rsi
0x180012110  push    rdi
0x180012111  push    r12
0x180012113  push    r14
0x180012115  push    r15
0x180012117  sub     rsp, 120h
0x18001211e  mov     rbx, [rsp+158h+arg_48]
0x180012126  xor     r10d, r10d
0x180012129  test    r9d, r9d
0x18001212c  mov     r12d, 80070057h
0x180012132  mov     rbp, rdx
0x180012135  mov     r14, rcx
0x180012138  mov     edi, 2
0x18001213d  mov     [rbx+114h], r10d
0x180012144  cmovnz  r10d, r12d
0x180012148  sub     r8d, 1
0x18001214c  jz      short loc_180012176
0x18001214e  sub     r8d, 1
0x180012152  jz      short loc_18001216A
0x180012154  cmp     r8d, 1
0x180012158  jnz     loc_18001235B
0x18001215e  mov     dword ptr [rbx+110h], 4
0x180012168  jmp     short loc_18001217C
0x18001216a  mov     dword ptr [rbx+110h], 3
0x180012174  jmp     short loc_18001217C
0x180012176  mov     [rbx+110h], edi
0x18001217c  test    r10d, r10d
0x18001217f  js      loc_180012346
0x180012185  lea     rcx, [rbx+100h]; pguid
0x18001218c  call    cs:__imp_CoCreateGuid
0x180012192  lea     rcx, [rbx+0B34h]; lpSystemTimeAsFileTime
0x180012199  call    cs:__imp_GetSystemTimeAsFileTime
0x18001219f  lea     rax, [r14+1Ch]
0x1800121a3  mov     rdx, rdi
0x1800121a6  lea     rcx, [rsp+158h+var_138]
0x1800121ab  mov     r15d, 80h
0x1800121b1  movups  xmm0, xmmword ptr [rax]
0x1800121b4  movups  xmm1, xmmword ptr [rax+10h]
0x1800121b8  movups  xmmword ptr [rcx], xmm0
0x1800121bb  movups  xmm0, xmmword ptr [rax+20h]
0x1800121bf  movups  xmmword ptr [rcx+10h], xmm1
0x1800121c3  movups  xmm1, xmmword ptr [rax+30h]
0x1800121c7  movups  xmmword ptr [rcx+20h], xmm0
0x1800121cb  movups  xmm0, xmmword ptr [rax+40h]
0x1800121cf  movups  xmmword ptr [rcx+30h], xmm1
0x1800121d3  movups  xmm1, xmmword ptr [rax+50h]
0x1800121d7  movups  xmmword ptr [rcx+40h], xmm0
0x1800121db  movups  xmm0, xmmword ptr [rax+60h]
0x1800121df  movups  xmmword ptr [rcx+50h], xmm1
0x1800121e3  movups  xmm1, xmmword ptr [rax+70h]
0x1800121e7  add     rax, r15
0x1800121ea  movups  xmmword ptr [rcx+60h], xmm0
0x1800121ee  movups  xmmword ptr [rcx+70h], xmm1
0x1800121f2  add     rcx, r15
0x1800121f5  sub     rdx, 1
0x1800121f9  jnz     short loc_1800121B1
0x1800121fb  mov     rax, rbx
0x1800121fe  lea     rcx, [rsp+158h+var_138]
0x180012203  movups  xmm0, xmmword ptr [rcx]
0x180012206  movups  xmm1, xmmword ptr [rcx+10h]
0x18001220a  movups  xmmword ptr [rax], xmm0
0x18001220d  movups  xmm0, xmmword ptr [rcx+20h]
0x180012211  movups  xmmword ptr [rax+10h], xmm1
0x180012215  movups  xmm1, xmmword ptr [rcx+30h]
0x180012219  movups  xmmword ptr [rax+20h], xmm0
0x18001221d  movups  xmm0, xmmword ptr [rcx+40h]
0x180012221  movups  xmmword ptr [rax+30h], xmm1
0x180012225  movups  xmm1, xmmword ptr [rcx+50h]
0x180012229  movups  xmmword ptr [rax+40h], xmm0
0x18001222d  movups  xmm0, xmmword ptr [rcx+60h]
0x180012231  movups  xmmword ptr [rax+50h], xmm1
0x180012235  movups  xmm1, xmmword ptr [rcx+70h]
0x180012239  add     rcx, r15
0x18001223c  movups  xmmword ptr [rax+60h], xmm0
0x180012240  movups  xmmword ptr [rax+70h], xmm1
0x180012244  add     rax, r15
0x180012247  sub     rdi, 1
0x18001224b  jnz     short loc_180012203
0x18001224d  test    rbp, rbp
0x180012250  jz      short loc_18001229B
0x180012252  mov     esi, [r14+128h]
0x180012259  cmp     edi, esi
0x18001225b  jnb     loc_18001235B
0x180012261  mov     rdx, [r14+120h]
0x180012268  mov     rcx, rbp; lpString1
0x18001226b  mov     rdx, [rdx+rdi*8]; lpString2
0x18001226f  call    ?s_AreIDStringsEqual@CSyncMgrID@@SA_NPEBG0@Z; CSyncMgrID::s_AreIDStringsEqual(ushort const *,ushort const *)
0x180012274  cmp     al, 1
0x180012276  jz      short loc_18001227C
0x180012278  inc     edi
0x18001227a  jmp     short loc_180012259
0x18001227c  lea     rcx, [rbx+80h]; unsigned __int16 *
0x180012283  mov     r8, rbp; unsigned __int16 *
0x180012286  mov     edx, 40h ; '@'; unsigned __int64
0x18001228b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012290  mov     r10d, eax
0x180012293  test    eax, eax
0x180012295  js      loc_180012346
0x18001229b  mov     r8, [rsp+158h+arg_20]; unsigned __int16 *
0x1800122a3  lea     rcx, [rbx+11Ch]; unsigned __int16 *
0x1800122aa  mov     rdx, r15; unsigned __int64
0x1800122ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800122b2  mov     r10d, eax
0x1800122b5  test    eax, eax
0x1800122b7  js      loc_180012346
0x1800122bd  mov     r8, [rsp+158h+arg_28]; unsigned __int16 *
0x1800122c5  lea     rcx, [rbx+21Ch]; unsigned __int16 *
0x1800122cc  mov     r11d, 104h
0x1800122d2  mov     edx, r11d; unsigned __int64
0x1800122d5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800122da  mov     r10d, eax
0x1800122dd  test    eax, eax
0x1800122df  js      short loc_180012346
0x1800122e1  mov     r8, [rsp+158h+arg_30]; unsigned __int16 *
0x1800122e9  test    r8, r8
0x1800122ec  jz      short loc_180012304
0x1800122ee  lea     rcx, [rbx+424h]; unsigned __int16 *
0x1800122f5  mov     rdx, r15; unsigned __int64
0x1800122f8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800122fd  mov     r10d, eax
0x180012300  test    eax, eax
0x180012302  js      short loc_180012346
0x180012304  mov     r8, [rsp+158h+arg_38]; unsigned __int16 *
0x18001230c  test    r8, r8
0x18001230f  jz      short loc_180012327
0x180012311  lea     rcx, [rbx+524h]; unsigned __int16 *
0x180012318  mov     rdx, r11; unsigned __int64
0x18001231b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012320  mov     r10d, eax
0x180012323  test    eax, eax
0x180012325  js      short loc_180012346
0x180012327  mov     r8, [rsp+158h+arg_40]; unsigned __int16 *
0x18001232f  test    r8, r8
0x180012332  jz      short loc_180012346
0x180012334  lea     rcx, [rbx+72Ch]; unsigned __int16 *
0x18001233b  mov     rdx, r11; unsigned __int64
0x18001233e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012343  mov     r10d, eax
0x180012346  mov     eax, r10d
0x180012349  add     rsp, 120h
0x180012350  pop     r15
0x180012352  pop     r14
0x180012354  pop     r12
0x180012356  pop     rdi
0x180012357  pop     rsi
0x180012358  pop     rbp
0x180012359  pop     rbx
0x18001235a  retn
0x18001235b  mov     r10d, r12d
0x18001235e  jmp     short loc_180012346
```
