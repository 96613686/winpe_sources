# ShieldProvider::QueryAndActionManager::GetConfigVectorValue(ushort const *,ulong *,ushort * * *)

- ea: `0x18002fd24`
- end: `0x180030055`
- name: `?GetConfigVectorValue@QueryAndActionManager@ShieldProvider@@QEAAJPEBGPEAKPEAPEAPEAG@Z`
- size: `817`
- prototype: `__int64 __fastcall(ShieldProvider::QueryAndActionManager *__hidden this, const unsigned __int16 *, unsigned int *, unsigned __int16 ***)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001feb0`
- `0x1800200b0`

## callees

- `0x18000d7fc`
- `0x180016d08`
- `0x180027e54`
- `0x180028044`
- `0x1800280a4`
- `0x180028134`
- `0x1800281b0`
- `0x180028604`
- `0x18002e0d0`
- `0x18002e680`
- `0x18002fd24`
- `0x180034730`
- `0x1800e1764`
- `0x1800e17e8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002fef5`
- `ole32!CoTaskMemFree` at `0x18002ff04`
- `ole32!CoTaskMemFree` at `0x18002fef5`
- `ole32!CoTaskMemFree` at `0x18002ff04`

## pseudocode

```c
__int64 __fastcall ShieldProvider::QueryAndActionManager::GetConfigVectorValue(
        ShieldProvider::QueryAndActionManager *this,
        const unsigned __int16 *a2,
        enum tagMPRUNNING_MODE *a3,
        unsigned __int16 ***a4)
{
  unsigned int v4; // r15d
  ShieldProvider *v8; // rcx
  unsigned int DefenderRunningMode; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 **v12; // r14
  __int64 v13; // rdx
  int v14; // edi
  __int64 v15; // r8
  unsigned int i; // esi
  int v17; // eax
  unsigned __int64 v18; // r8
  bool v19; // r9
  unsigned int k; // ebx
  unsigned __int16 ***m; // rbx
  int v22; // eax
  unsigned __int16 *v23; // r8
  unsigned __int16 ***j; // rbx
  __int64 v26; // [rsp+30h] [rbp-49h] BYREF
  __int64 v27; // [rsp+38h] [rbp-41h] BYREF
  __int64 v28; // [rsp+40h] [rbp-39h] BYREF
  int v29; // [rsp+48h] [rbp-31h] BYREF
  int v30; // [rsp+4Ch] [rbp-2Dh] BYREF
  int v31; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int16 **v32; // [rsp+58h] [rbp-21h] BYREF
  __int64 v33; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 ***v34; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int16 ***v35; // [rsp+70h] [rbp-9h]
  __int64 v36; // [rsp+78h] [rbp-1h]
  __int64 v37[10]; // [rsp+80h] [rbp+7h] BYREF
  int v38; // [rsp+F8h] [rbp+7Fh] BYREF

  v4 = 0;
  if ( !a4 || !a3 )
  {
    v10 = WPP_GLOBAL_Control;
    DefenderRunningMode = -2147024809;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return DefenderRunningMode;
    v11 = 27;
    goto LABEL_61;
  }
  *a4 = 0;
  *(_DWORD *)a3 = 0;
  v8 = (ShieldProvider *)*((_QWORD *)this + 2);
  v38 = 0;
  DefenderRunningMode = ShieldProvider::GetDefenderRunningMode(v8, (struct tagMPCONTEXT *)&v38, a3);
  if ( (DefenderRunningMode & 0x80000000) != 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return DefenderRunningMode;
    v11 = 28;
LABEL_61:
    WPP_SF_d(v10[2], v11, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, DefenderRunningMode);
    return DefenderRunningMode;
  }
  if ( v38 == 3 )
  {
    v10 = WPP_GLOBAL_Control;
    DefenderRunningMode = -2147024846;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return DefenderRunningMode;
    v11 = 29;
    goto LABEL_61;
  }
  std::vector<_incompatibleDriver>::vector<_incompatibleDriver>(&v34);
  v32 = 0;
  v28 = 0;
  v12 = 0;
  v33 = 0;
  v14 = MpConfigOpen(a2, &v33);
  if ( v14 >= 0 )
  {
    v14 = MpConfigIteratorOpen(v33, v13, v15, &v28);
    if ( v14 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v26 = 0;
        v27 = 0;
        v31 = 0;
        v29 = 0;
        v30 = 0;
        v17 = MpConfigIteratorEnum(
                v28,
                (unsigned int)&v26,
                (unsigned int)&v31,
                (unsigned int)&v30,
                (__int64)&v27,
                (__int64)&v29);
        v14 = v17;
        if ( v17 == -2147024637 )
        {
          if ( v27 )
            MpFreeMemory(v27);
          if ( v26 )
            MpFreeMemory(v26);
          if ( !i )
          {
            v14 = 1;
            goto LABEL_29;
          }
          LOBYTE(v18) = 1;
          v22 = CommonUtil::UtilCoTaskMemAlloc((CommonUtil *)&v32, (void **)(8LL * i), v18, v19);
          v12 = v32;
          v14 = v22;
          if ( v22 < 0 )
            goto LABEL_25;
          for ( j = v34; j != v35; ++j )
          {
            if ( v4 >= i )
            {
              v14 = -2147418113;
              goto LABEL_25;
            }
            v14 = CommonUtil::UtilCoDuplicateString((CommonUtil *)&v12[v4], *j, v23);
            if ( v14 < 0 )
              goto LABEL_25;
            ++v4;
          }
          *(_DWORD *)a3 = i;
          *a4 = v12;
          goto LABEL_29;
        }
        if ( v17 < 0 )
        {
          if ( v27 )
            MpFreeMemory(v27);
          if ( v26 )
            MpFreeMemory(v26);
          goto LABEL_29;
        }
        v37[0] = v26;
        v26 = 0;
        v14 = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>>,unsigned __int64>(
                &v34,
                v37);
        if ( v14 < 0 )
          break;
        if ( v27 )
          MpFreeMemory(v27);
        if ( v26 )
          MpFreeMemory(v26);
      }
      if ( v27 )
        MpFreeMemory(v27);
      if ( v26 )
      {
        i = 0;
        MpFreeMemory(v26);
LABEL_25:
        if ( v12 )
        {
          for ( k = 0; k < i; ++k )
            CoTaskMemFree(v12[k]);
          CoTaskMemFree(v12);
        }
      }
    }
  }
LABEL_29:
  for ( m = v34; m != v35; ++m )
    MpFreeMemory(*m);
  if ( v33 )
    MpConfigClose();
  if ( v28 )
    MpConfigIteratorClose();
  if ( v34 )
    std::_Deallocate<16>(v34, (v36 - (_QWORD)v34) & 0xFFFFFFFFFFFFFFF8uLL);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002fd24  push    rbp
0x18002fd26  push    rbx
0x18002fd27  push    rsi
0x18002fd28  push    rdi
0x18002fd29  push    r12
0x18002fd2b  push    r13
0x18002fd2d  push    r14
0x18002fd2f  push    r15
0x18002fd31  lea     rbp, [rsp-1Fh]
0x18002fd36  sub     rsp, 98h
0x18002fd3d  xor     r15d, r15d
0x18002fd40  mov     r13, r9
0x18002fd43  mov     r12, r8
0x18002fd46  mov     rdi, rdx
0x18002fd49  test    r9, r9
0x18002fd4c  jz      loc_180030009
0x18002fd52  test    r8, r8
0x18002fd55  jz      loc_180030009
0x18002fd5b  mov     [r9], r15
0x18002fd5e  lea     rdx, [rbp+57h+arg_18]; struct tagMPCONTEXT *
0x18002fd62  mov     [r8], r15d
0x18002fd65  mov     rcx, [rcx+10h]; this
0x18002fd69  mov     [rbp+57h+arg_18], r15d
0x18002fd6d  call    ?GetDefenderRunningMode@ShieldProvider@@YAJPEAUtagMPCONTEXT@@PEAW4tagMPRUNNING_MODE@@@Z; ShieldProvider::GetDefenderRunningMode(tagMPCONTEXT *,tagMPRUNNING_MODE *)
0x18002fd72  mov     ebx, eax
0x18002fd74  test    eax, eax
0x18002fd76  jns     short loc_18002FDA2
0x18002fd78  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd7f  lea     rdx, WPP_GLOBAL_Control
0x18002fd86  cmp     rcx, rdx
0x18002fd89  jz      loc_18003003F
0x18002fd8f  test    byte ptr [rcx+1Ch], 1
0x18002fd93  jz      loc_18003003F
0x18002fd99  lea     edx, [r15+1Ch]
0x18002fd9d  jmp     loc_18003002C
0x18002fda2  cmp     [rbp+57h+arg_18], 3
0x18002fda6  jnz     short loc_18002FDD8
0x18002fda8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdaf  lea     rdx, WPP_GLOBAL_Control
0x18002fdb6  mov     ebx, 80070032h
0x18002fdbb  cmp     rcx, rdx
0x18002fdbe  jz      loc_18003003F
0x18002fdc4  test    byte ptr [rcx+1Ch], 1
0x18002fdc8  jz      loc_18003003F
0x18002fdce  mov     edx, 1Dh
0x18002fdd3  jmp     loc_18003002C
0x18002fdd8  lea     rcx, [rbp+57h+var_68]
0x18002fddc  call    ??0?$vector@U_incompatibleDriver@@V?$allocator@U_incompatibleDriver@@@std@@@std@@QEAA@XZ; std::vector<_incompatibleDriver>::vector<_incompatibleDriver>(void)
0x18002fde1  lea     rdx, [rbp+57h+var_70]
0x18002fde5  mov     [rbp+57h+var_78], r15
0x18002fde9  mov     rcx, rdi
0x18002fdec  mov     [rbp+57h+var_90], r15
0x18002fdf0  mov     r14, r15
0x18002fdf3  mov     [rbp+57h+var_70], r15
0x18002fdf7  call    MpConfigOpen
0x18002fdfc  mov     edi, eax
0x18002fdfe  test    eax, eax
0x18002fe00  js      loc_18002FF0A
0x18002fe06  mov     rcx, [rbp+57h+var_90]
0x18002fe0a  test    rcx, rcx
0x18002fe0d  jz      short loc_18002FE18
0x18002fe0f  call    MpConfigIteratorClose
0x18002fe14  mov     [rbp+57h+var_90], r15
0x18002fe18  mov     rcx, [rbp+57h+var_70]
0x18002fe1c  lea     r9, [rbp+57h+var_90]
0x18002fe20  call    MpConfigIteratorOpen
0x18002fe25  mov     edi, eax
0x18002fe27  test    eax, eax
0x18002fe29  js      loc_18002FF0A
0x18002fe2f  mov     esi, r15d
0x18002fe32  mov     rcx, [rbp+57h+var_90]
0x18002fe36  lea     rax, [rbp+57h+var_88]
0x18002fe3a  mov     [rsp+0D0h+var_A8], rax
0x18002fe3f  lea     r9, [rbp+57h+var_84]
0x18002fe43  lea     rax, [rbp+57h+var_98]
0x18002fe47  mov     [rbp+57h+var_A0], r15
0x18002fe4b  lea     r8, [rbp+57h+var_80]
0x18002fe4f  mov     [rsp+0D0h+var_B0], rax
0x18002fe54  lea     rdx, [rbp+57h+var_A0]
0x18002fe58  mov     [rbp+57h+var_98], r15
0x18002fe5c  mov     [rbp+57h+var_80], r15d
0x18002fe60  mov     [rbp+57h+var_88], r15d
0x18002fe64  mov     [rbp+57h+var_84], r15d
0x18002fe68  call    MpConfigIteratorEnum
0x18002fe6d  mov     edi, eax
0x18002fe6f  cmp     eax, 80070103h
0x18002fe74  jz      loc_18002FF44
0x18002fe7a  test    eax, eax
0x18002fe7c  js      loc_18002FF26
0x18002fe82  mov     rax, [rbp+57h+var_A0]
0x18002fe86  lea     rdx, [rbp+57h+var_50]
0x18002fe8a  lea     rcx, [rbp+57h+var_68]
0x18002fe8e  mov     [rbp+57h+var_50], rax
0x18002fe92  mov     [rbp+57h+var_A0], r15
0x18002fe96  call    ??$HrStdPushBack@V?$CStdVector@_KV?$allocator@_K@std@@@CommonUtil@@_K@CommonUtil@@YAJAEAV?$CStdVector@_KV?$allocator@_K@std@@@0@AEB_K@Z; CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>>,unsigned __int64>(CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>> &,unsigned __int64 const &)
0x18002fe9b  mov     rcx, [rbp+57h+var_98]
0x18002fe9f  mov     edi, eax
0x18002fea1  test    eax, eax
0x18002fea3  js      short loc_18002FEC8
0x18002fea5  inc     esi
0x18002fea7  test    rcx, rcx
0x18002feaa  jz      short loc_18002FEB1
0x18002feac  call    MpFreeMemory
0x18002feb1  mov     rcx, [rbp+57h+var_A0]
0x18002feb5  test    rcx, rcx
0x18002feb8  jz      loc_18002FE32
0x18002febe  call    MpFreeMemory
0x18002fec3  jmp     loc_18002FE32
0x18002fec8  test    rcx, rcx
0x18002fecb  jz      short loc_18002FED2
0x18002fecd  call    MpFreeMemory
0x18002fed2  mov     rcx, [rbp+57h+var_A0]
0x18002fed6  test    rcx, rcx
0x18002fed9  jz      short loc_18002FF0A
0x18002fedb  mov     esi, r15d
0x18002fede  call    MpFreeMemory
0x18002fee3  test    r14, r14
0x18002fee6  jz      short loc_18002FF0A
0x18002fee8  mov     ebx, r15d
0x18002feeb  test    esi, esi
0x18002feed  jz      short loc_18002FF01
0x18002feef  mov     ecx, ebx
0x18002fef1  mov     rcx, [r14+rcx*8]; pv
0x18002fef5  call    cs:__imp_CoTaskMemFree
0x18002fefb  inc     ebx
0x18002fefd  cmp     ebx, esi
0x18002feff  jb      short loc_18002FEEF
0x18002ff01  mov     rcx, r14; pv
0x18002ff04  call    cs:__imp_CoTaskMemFree
0x18002ff0a  mov     rbx, [rbp+57h+var_68]
0x18002ff0e  cmp     rbx, [rbp+57h+var_60]
0x18002ff12  jz      loc_18002FFD0
0x18002ff18  mov     rcx, [rbx]
0x18002ff1b  call    MpFreeMemory
0x18002ff20  add     rbx, 8
0x18002ff24  jmp     short loc_18002FF0E
0x18002ff26  mov     rcx, [rbp+57h+var_98]
0x18002ff2a  test    rcx, rcx
0x18002ff2d  jz      short loc_18002FF34
0x18002ff2f  call    MpFreeMemory
0x18002ff34  mov     rcx, [rbp+57h+var_A0]
0x18002ff38  test    rcx, rcx
0x18002ff3b  jz      short loc_18002FF0A
0x18002ff3d  call    MpFreeMemory
0x18002ff42  jmp     short loc_18002FF0A
0x18002ff44  mov     rcx, [rbp+57h+var_98]
0x18002ff48  test    rcx, rcx
0x18002ff4b  jz      short loc_18002FF52
0x18002ff4d  call    MpFreeMemory
0x18002ff52  mov     rcx, [rbp+57h+var_A0]
0x18002ff56  test    rcx, rcx
0x18002ff59  jz      short loc_18002FF60
0x18002ff5b  call    MpFreeMemory
0x18002ff60  test    esi, esi
0x18002ff62  jnz     short loc_18002FF69
0x18002ff64  lea     edi, [rsi+1]
0x18002ff67  jmp     short loc_18002FF0A
0x18002ff69  mov     edx, esi
0x18002ff6b  lea     rcx, [rbp+57h+var_78]; this
0x18002ff6f  shl     rdx, 3; void **
0x18002ff73  mov     r8b, 1; unsigned __int64
0x18002ff76  call    ?UtilCoTaskMemAlloc@CommonUtil@@YAJPEAPEAX_K_N@Z; CommonUtil::UtilCoTaskMemAlloc(void * *,unsigned __int64,bool)
0x18002ff7b  mov     r14, [rbp+57h+var_78]
0x18002ff7f  mov     edi, eax
0x18002ff81  test    eax, eax
0x18002ff83  js      loc_18002FEE3
0x18002ff89  mov     rbx, [rbp+57h+var_68]
0x18002ff8d  cmp     rbx, [rbp+57h+var_60]
0x18002ff91  jz      short loc_18002FFC3
0x18002ff93  cmp     r15d, esi
0x18002ff96  jnb     short loc_18002FFB6
0x18002ff98  mov     rdx, [rbx]; unsigned __int16 **
0x18002ff9b  mov     eax, r15d
0x18002ff9e  lea     rcx, [r14+rax*8]; this
0x18002ffa2  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18002ffa7  mov     edi, eax
0x18002ffa9  test    eax, eax
0x18002ffab  js      short loc_18002FFBB
0x18002ffad  inc     r15d
0x18002ffb0  add     rbx, 8
0x18002ffb4  jmp     short loc_18002FF8D
0x18002ffb6  mov     edi, 8000FFFFh
0x18002ffbb  xor     r15d, r15d
0x18002ffbe  jmp     loc_18002FEE3
0x18002ffc3  mov     [r12], esi
0x18002ffc7  mov     [r13+0], r14
0x18002ffcb  jmp     loc_18002FF0A
0x18002ffd0  mov     rcx, [rbp+57h+var_70]
0x18002ffd4  test    rcx, rcx
0x18002ffd7  jz      short loc_18002FFDE
0x18002ffd9  call    MpConfigClose
0x18002ffde  mov     rcx, [rbp+57h+var_90]
0x18002ffe2  test    rcx, rcx
0x18002ffe5  jz      short loc_18002FFEC
0x18002ffe7  call    MpConfigIteratorClose
0x18002ffec  mov     rcx, [rbp+57h+var_68]
0x18002fff0  test    rcx, rcx
0x18002fff3  jz      short loc_180030005
0x18002fff5  mov     rdx, [rbp+57h+var_58]
0x18002fff9  sub     rdx, rcx
0x18002fffc  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180030000  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180030005  mov     eax, edi
0x180030007  jmp     short loc_180030041
0x180030009  mov     rcx, cs:WPP_GLOBAL_Control
0x180030010  lea     rdx, WPP_GLOBAL_Control
0x180030017  mov     ebx, 80070057h
0x18003001c  cmp     rcx, rdx
0x18003001f  jz      short loc_18003003F
0x180030021  test    byte ptr [rcx+1Ch], 1
0x180030025  jz      short loc_18003003F
0x180030027  mov     edx, 1Bh
0x18003002c  mov     rcx, [rcx+10h]
0x180030030  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030037  mov     r9d, ebx
0x18003003a  call    WPP_SF_d
0x18003003f  mov     eax, ebx
0x180030041  add     rsp, 98h
0x180030048  pop     r15
0x18003004a  pop     r14
0x18003004c  pop     r13
0x18003004e  pop     r12
0x180030050  pop     rdi
0x180030051  pop     rsi
0x180030052  pop     rbx
0x180030053  pop     rbp
0x180030054  retn
```
