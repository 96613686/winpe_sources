# ShieldProvider::QueryAndActionManager::GetConfigVectorValueEx(ushort const *,ulong *,ConfigData * *)

- ea: `0x18003005c`
- end: `0x180030437`
- name: `?GetConfigVectorValueEx@QueryAndActionManager@ShieldProvider@@QEAAJPEBGPEAKPEAPEAUConfigData@@@Z`
- size: `987`
- prototype: `__int64 __fastcall(ShieldProvider::QueryAndActionManager *__hidden this, const unsigned __int16 *, unsigned int *, struct ConfigData **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ffb0`

## callees

- `0x18000d7fc`
- `0x180015894`
- `0x180016d08`
- `0x180027e54`
- `0x180028044`
- `0x1800280a4`
- `0x180028134`
- `0x1800281b0`
- `0x180028604`
- `0x18002e110`
- `0x18002e680`
- `0x18003005c`
- `0x180034730`
- `0x1800db17c`
- `0x1800db1ec`
- `0x1800e1764`
- `0x1800e17e8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180030241`
- `ole32!CoTaskMemFree` at `0x180030250`
- `ole32!CoTaskMemFree` at `0x180030241`
- `ole32!CoTaskMemFree` at `0x180030250`

## pseudocode

```c
__int64 __fastcall ShieldProvider::QueryAndActionManager::GetConfigVectorValueEx(
        ShieldProvider::QueryAndActionManager *this,
        const unsigned __int16 *a2,
        enum tagMPRUNNING_MODE *a3,
        struct ConfigData **a4)
{
  ShieldProvider *v5; // rcx
  unsigned int DefenderRunningMode; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  struct ConfigData *v9; // r15
  __int64 v10; // rdx
  int v11; // edi
  __int64 v12; // r8
  unsigned int i; // esi
  int v14; // eax
  unsigned __int64 v15; // r8
  bool v16; // r9
  unsigned int j; // ebx
  unsigned __int16 ***k; // rbx
  int v19; // eax
  unsigned __int16 *v20; // r8
  unsigned __int16 ***v21; // rbx
  unsigned int v22; // r13d
  unsigned __int16 **v23; // r12
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // rdx
  int v26; // r12d
  __int64 v28; // [rsp+38h] [rbp-39h] BYREF
  unsigned __int16 **v29; // [rsp+40h] [rbp-31h] BYREF
  CommonUtil *v30; // [rsp+48h] [rbp-29h] BYREF
  int v31; // [rsp+50h] [rbp-21h] BYREF
  int v32; // [rsp+54h] [rbp-1Dh] BYREF
  __int64 v33; // [rsp+58h] [rbp-19h] BYREF
  int v34; // [rsp+60h] [rbp-11h] BYREF
  int v35; // [rsp+64h] [rbp-Dh] BYREF
  __int64 v36; // [rsp+68h] [rbp-9h] BYREF
  unsigned __int16 ***v37; // [rsp+70h] [rbp-1h] BYREF
  unsigned __int16 ***v38; // [rsp+78h] [rbp+7h]
  __int64 v39; // [rsp+80h] [rbp+Fh]
  __int64 v40; // [rsp+88h] [rbp+17h] BYREF
  int v41; // [rsp+90h] [rbp+1Fh]
  int v42; // [rsp+94h] [rbp+23h]

  if ( !a4 || !a3 )
  {
    v7 = WPP_GLOBAL_Control;
    DefenderRunningMode = -2147024809;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return DefenderRunningMode;
    v8 = 30;
    goto LABEL_70;
  }
  *a4 = 0;
  *(_DWORD *)a3 = 0;
  v5 = (ShieldProvider *)*((_QWORD *)this + 2);
  v31 = 0;
  DefenderRunningMode = ShieldProvider::GetDefenderRunningMode(v5, (struct tagMPCONTEXT *)&v31, a3);
  if ( (DefenderRunningMode & 0x80000000) != 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return DefenderRunningMode;
    v8 = 31;
LABEL_70:
    WPP_SF_d(v7[2], v8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, DefenderRunningMode);
    return DefenderRunningMode;
  }
  if ( v31 == 3 )
  {
    v7 = WPP_GLOBAL_Control;
    DefenderRunningMode = -2147024846;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return DefenderRunningMode;
    v8 = 32;
    goto LABEL_70;
  }
  std::vector<_incompatibleDriver>::vector<_incompatibleDriver>(&v37);
  v30 = 0;
  v33 = 0;
  v9 = 0;
  v36 = 0;
  v11 = MpConfigOpen(a2, &v36);
  if ( v11 >= 0 )
  {
    if ( v33 )
    {
      MpConfigIteratorClose();
      v33 = 0;
    }
    v11 = MpConfigIteratorOpen(v36, v10, v12, &v33);
    if ( v11 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v28 = 0;
        v29 = 0;
        v35 = 0;
        v32 = 0;
        v34 = 0;
        v14 = MpConfigIteratorEnum(
                v33,
                (unsigned int)&v28,
                (unsigned int)&v35,
                (unsigned int)&v34,
                (__int64)&v29,
                (__int64)&v32);
        v11 = v14;
        if ( v14 == -2147024637 )
        {
          if ( v29 )
            ((void (*)(void))MpFreeMemory)();
          if ( v28 )
            ((void (*)(void))MpFreeMemory)();
          if ( !i )
          {
            v11 = 1;
            goto LABEL_31;
          }
          LOBYTE(v15) = 1;
          v19 = CommonUtil::UtilCoTaskMemAlloc((CommonUtil *)&v30, (void **)(16LL * i), v15, v16);
          v9 = v30;
          v11 = v19;
          if ( v19 < 0 )
            goto LABEL_27;
          v21 = v37;
          v22 = 0;
          while ( v21 != v38 )
          {
            if ( v22 >= i )
            {
              v11 = -2147418113;
              goto LABEL_27;
            }
            v23 = *v21;
            v29 = *v21;
            v30 = (struct ConfigData *)((char *)v9 + 16 * v22);
            v11 = CommonUtil::UtilCoDuplicateString(v30, v29, v20);
            if ( v11 < 0 )
              goto LABEL_27;
            *((_DWORD *)v30 + 2) = *((_DWORD *)v21 + 2);
            if ( (unsigned int)CommonUtil::UtilIsDirectoryExists((CommonUtil *)v23, v24) )
            {
              if ( (unsigned int)CommonUtil::UtilIsFileExists((CommonUtil *)v23, v25) )
              {
                v26 = 0;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    33,
                    WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
                    v29);
              }
              else
              {
                v26 = 1;
              }
            }
            else
            {
              v26 = 2;
            }
            ++v22;
            v21 += 2;
            *((_DWORD *)v30 + 3) = v26;
          }
          *(_DWORD *)a3 = i;
          *a4 = v9;
          goto LABEL_31;
        }
        if ( v14 < 0 )
        {
          if ( v29 )
            ((void (*)(void))MpFreeMemory)();
          if ( v28 )
            ((void (*)(void))MpFreeMemory)();
          goto LABEL_31;
        }
        v40 = v28;
        v41 = v32;
        v28 = 0;
        v42 = 0;
        v11 = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<ConfigData,std::allocator<ConfigData>>,ConfigData>(
                &v37,
                &v40);
        if ( v11 < 0 )
          break;
        if ( v29 )
          MpFreeMemory(v29);
        if ( v28 )
          MpFreeMemory(v28);
      }
      if ( v29 )
        MpFreeMemory(v29);
      if ( v28 )
      {
        i = 0;
        MpFreeMemory(v28);
LABEL_27:
        if ( v9 )
        {
          for ( j = 0; j < i; ++j )
            CoTaskMemFree(*((LPVOID *)v9 + 2 * j));
          CoTaskMemFree(v9);
        }
      }
    }
  }
LABEL_31:
  for ( k = v37; k != v38; k += 2 )
    MpFreeMemory(*k);
  if ( v36 )
    MpConfigClose();
  if ( v33 )
    MpConfigIteratorClose();
  if ( v37 )
    std::_Deallocate<16>(v37, (v39 - (_QWORD)v37) & 0xFFFFFFFFFFFFFFF0uLL);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003005c  mov     rax, rsp
0x18003005f  mov     [rax+8], rbx
0x180030063  mov     [rax+20h], r9
0x180030067  mov     [rax+18h], r8
0x18003006b  push    rbp
0x18003006c  push    rsi
0x18003006d  push    rdi
0x18003006e  push    r12
0x180030070  push    r13
0x180030072  push    r14
0x180030074  push    r15
0x180030076  lea     rbp, [rax-5Fh]
0x18003007a  sub     rsp, 90h
0x180030081  xor     r14d, r14d
0x180030084  mov     rdi, rdx
0x180030087  test    r9, r9
0x18003008a  jz      loc_1800303E4
0x180030090  test    r8, r8
0x180030093  jz      loc_1800303E4
0x180030099  mov     [r9], r14
0x18003009c  lea     rdx, [rbp+57h+var_78]; struct tagMPCONTEXT *
0x1800300a0  mov     [r8], r14d
0x1800300a3  mov     rcx, [rcx+10h]; this
0x1800300a7  mov     [rbp+57h+var_78], r14d
0x1800300ab  call    ?GetDefenderRunningMode@ShieldProvider@@YAJPEAUtagMPCONTEXT@@PEAW4tagMPRUNNING_MODE@@@Z; ShieldProvider::GetDefenderRunningMode(tagMPCONTEXT *,tagMPRUNNING_MODE *)
0x1800300b0  mov     ebx, eax
0x1800300b2  test    eax, eax
0x1800300b4  jns     short loc_1800300E1
0x1800300b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300bd  lea     r14, WPP_GLOBAL_Control
0x1800300c4  cmp     rcx, r14
0x1800300c7  jz      loc_18003041A
0x1800300cd  test    byte ptr [rcx+1Ch], 1
0x1800300d1  jz      loc_18003041A
0x1800300d7  mov     edx, 1Fh
0x1800300dc  jmp     loc_180030407
0x1800300e1  cmp     [rbp+57h+var_78], 3
0x1800300e5  jnz     short loc_180030117
0x1800300e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300ee  lea     r14, WPP_GLOBAL_Control
0x1800300f5  mov     ebx, 80070032h
0x1800300fa  cmp     rcx, r14
0x1800300fd  jz      loc_18003041A
0x180030103  test    byte ptr [rcx+1Ch], 1
0x180030107  jz      loc_18003041A
0x18003010d  mov     edx, 20h ; ' '
0x180030112  jmp     loc_180030407
0x180030117  lea     rcx, [rbp+57h+var_58]
0x18003011b  call    ??0?$vector@U_incompatibleDriver@@V?$allocator@U_incompatibleDriver@@@std@@@std@@QEAA@XZ; std::vector<_incompatibleDriver>::vector<_incompatibleDriver>(void)
0x180030120  lea     rdx, [rbp+57h+var_60]
0x180030124  mov     [rbp+57h+var_80], r14
0x180030128  mov     rcx, rdi
0x18003012b  mov     [rbp+57h+var_70], r14
0x18003012f  mov     r15, r14
0x180030132  mov     [rbp+57h+var_60], r14
0x180030136  call    MpConfigOpen
0x18003013b  mov     edi, eax
0x18003013d  test    eax, eax
0x18003013f  js      loc_180030256
0x180030145  mov     rcx, [rbp+57h+var_70]
0x180030149  test    rcx, rcx
0x18003014c  jz      short loc_180030157
0x18003014e  call    MpConfigIteratorClose
0x180030153  mov     [rbp+57h+var_70], r14
0x180030157  mov     rcx, [rbp+57h+var_60]
0x18003015b  lea     r9, [rbp+57h+var_70]
0x18003015f  call    MpConfigIteratorOpen
0x180030164  mov     edi, eax
0x180030166  test    eax, eax
0x180030168  js      loc_180030256
0x18003016e  mov     esi, r14d
0x180030171  mov     rcx, [rbp+57h+var_70]
0x180030175  lea     rax, [rbp+57h+var_74]
0x180030179  mov     [rsp+28h], rax
0x18003017e  lea     r9, [rbp+57h+var_68]
0x180030182  lea     rax, [rbp+57h+var_88]
0x180030186  mov     [rbp+57h+var_90], r14
0x18003018a  lea     r8, [rbp+57h+var_64]
0x18003018e  mov     [rsp+0C0h+var_A0], rax
0x180030193  lea     rdx, [rbp+57h+var_90]
0x180030197  mov     [rbp+57h+var_88], r14
0x18003019b  mov     [rbp+57h+var_64], r14d
0x18003019f  mov     [rbp+57h+var_74], r14d
0x1800301a3  mov     [rbp+57h+var_68], r14d
0x1800301a7  call    MpConfigIteratorEnum
0x1800301ac  mov     edi, eax
0x1800301ae  cmp     eax, 80070103h
0x1800301b3  jz      loc_180030290
0x1800301b9  test    eax, eax
0x1800301bb  js      loc_180030272
0x1800301c1  mov     rax, [rbp+57h+var_90]
0x1800301c5  lea     rdx, [rbp+57h+var_40]
0x1800301c9  mov     [rbp+57h+var_40], rax
0x1800301cd  lea     rcx, [rbp+57h+var_58]
0x1800301d1  mov     eax, [rbp+57h+var_74]
0x1800301d4  mov     [rbp+57h+var_38], eax
0x1800301d7  mov     [rbp+57h+var_90], r14
0x1800301db  mov     [rbp+57h+var_34], r14d
0x1800301df  call    ??$HrStdPushBack@V?$CStdVector@UConfigData@@V?$allocator@UConfigData@@@std@@@CommonUtil@@UConfigData@@@CommonUtil@@YAJAEAV?$CStdVector@UConfigData@@V?$allocator@UConfigData@@@std@@@0@AEBUConfigData@@@Z; CommonUtil::HrStdPushBack<CommonUtil::CStdVector<ConfigData,std::allocator<ConfigData>>,ConfigData>(CommonUtil::CStdVector<ConfigData,std::allocator<ConfigData>> &,ConfigData const &)
0x1800301e4  mov     rcx, [rbp+57h+var_88]
0x1800301e8  mov     edi, eax
0x1800301ea  test    eax, eax
0x1800301ec  js      short loc_180030211
0x1800301ee  inc     esi
0x1800301f0  test    rcx, rcx
0x1800301f3  jz      short loc_1800301FA
0x1800301f5  call    MpFreeMemory
0x1800301fa  mov     rcx, [rbp+57h+var_90]
0x1800301fe  test    rcx, rcx
0x180030201  jz      loc_180030171
0x180030207  call    MpFreeMemory
0x18003020c  jmp     loc_180030171
0x180030211  test    rcx, rcx
0x180030214  jz      short loc_18003021B
0x180030216  call    MpFreeMemory
0x18003021b  mov     rcx, [rbp+57h+var_90]
0x18003021f  test    rcx, rcx
0x180030222  jz      short loc_180030256
0x180030224  mov     esi, r14d
0x180030227  call    MpFreeMemory
0x18003022c  test    r15, r15
0x18003022f  jz      short loc_180030256
0x180030231  mov     ebx, r14d
0x180030234  test    esi, esi
0x180030236  jz      short loc_18003024D
0x180030238  mov     ecx, ebx
0x18003023a  add     rcx, rcx
0x18003023d  mov     rcx, [r15+rcx*8]; pv
0x180030241  call    cs:__imp_CoTaskMemFree
0x180030247  inc     ebx
0x180030249  cmp     ebx, esi
0x18003024b  jb      short loc_180030238
0x18003024d  mov     rcx, r15; pv
0x180030250  call    cs:__imp_CoTaskMemFree
0x180030256  mov     rbx, [rbp+57h+var_58]
0x18003025a  cmp     rbx, [rbp+57h+var_50]
0x18003025e  jz      loc_1800303AB
0x180030264  mov     rcx, [rbx]
0x180030267  call    MpFreeMemory
0x18003026c  add     rbx, 10h
0x180030270  jmp     short loc_18003025A
0x180030272  mov     rcx, [rbp+57h+var_88]
0x180030276  test    rcx, rcx
0x180030279  jz      short loc_180030280
0x18003027b  call    MpFreeMemory
0x180030280  mov     rcx, [rbp+57h+var_90]
0x180030284  test    rcx, rcx
0x180030287  jz      short loc_180030256
0x180030289  call    MpFreeMemory
0x18003028e  jmp     short loc_180030256
0x180030290  mov     rcx, [rbp+57h+var_88]
0x180030294  test    rcx, rcx
0x180030297  jz      short loc_18003029E
0x180030299  call    MpFreeMemory
0x18003029e  mov     rcx, [rbp+57h+var_90]
0x1800302a2  test    rcx, rcx
0x1800302a5  jz      short loc_1800302AC
0x1800302a7  call    MpFreeMemory
0x1800302ac  test    esi, esi
0x1800302ae  jnz     short loc_1800302B5
0x1800302b0  lea     edi, [rsi+1]
0x1800302b3  jmp     short loc_180030256
0x1800302b5  mov     edx, esi
0x1800302b7  lea     rcx, [rbp+57h+var_80]; this
0x1800302bb  shl     rdx, 4; void **
0x1800302bf  mov     r8b, 1; unsigned __int64
0x1800302c2  call    ?UtilCoTaskMemAlloc@CommonUtil@@YAJPEAPEAX_K_N@Z; CommonUtil::UtilCoTaskMemAlloc(void * *,unsigned __int64,bool)
0x1800302c7  mov     r15, [rbp+57h+var_80]
0x1800302cb  mov     edi, eax
0x1800302cd  test    eax, eax
0x1800302cf  js      loc_18003022C
0x1800302d5  mov     rbx, [rbp+57h+var_58]
0x1800302d9  mov     r13d, r14d
0x1800302dc  lea     r14, WPP_GLOBAL_Control
0x1800302e3  cmp     rbx, [rbp+57h+var_50]
0x1800302e7  jz      loc_180030399
0x1800302ed  cmp     r13d, esi
0x1800302f0  jnb     loc_18003038C
0x1800302f6  mov     r12, [rbx]
0x1800302f9  mov     eax, r13d
0x1800302fc  mov     rdx, r12; unsigned __int16 **
0x1800302ff  shl     rax, 4
0x180030303  add     rax, r15
0x180030306  mov     [rbp+57h+var_88], r12
0x18003030a  mov     rcx, rax; this
0x18003030d  mov     [rbp+57h+var_80], rax
0x180030311  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x180030316  mov     edi, eax
0x180030318  test    eax, eax
0x18003031a  js      short loc_180030391
0x18003031c  mov     rcx, [rbp+57h+var_80]
0x180030320  mov     eax, [rbx+8]
0x180030323  mov     [rcx+8], eax
0x180030326  mov     rcx, r12; this
0x180030329  call    ?UtilIsDirectoryExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsDirectoryExists(ushort const *)
0x18003032e  test    eax, eax
0x180030330  jnz     short loc_180030338
0x180030332  lea     r12d, [rax+2]
0x180030336  jmp     short loc_180030378
0x180030338  mov     rcx, r12; this
0x18003033b  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x180030340  test    eax, eax
0x180030342  jnz     short loc_18003034A
0x180030344  lea     r12d, [rax+1]
0x180030348  jmp     short loc_180030378
0x18003034a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030351  xor     r12d, r12d
0x180030354  cmp     rcx, r14
0x180030357  jz      short loc_180030378
0x180030359  test    byte ptr [rcx+1Ch], 2
0x18003035d  jz      short loc_180030378
0x18003035f  mov     r9, [rbp+57h+var_88]
0x180030363  lea     edx, [r12+21h]
0x180030368  mov     rcx, [rcx+10h]
0x18003036c  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030373  call    WPP_SF_S
0x180030378  mov     rax, [rbp+57h+var_80]
0x18003037c  inc     r13d
0x18003037f  add     rbx, 10h
0x180030383  mov     [rax+0Ch], r12d
0x180030387  jmp     loc_1800302E3
0x18003038c  mov     edi, 8000FFFFh
0x180030391  xor     r14d, r14d
0x180030394  jmp     loc_18003022C
0x180030399  mov     rax, [rbp+57h+arg_10]
0x18003039d  mov     [rax], esi
0x18003039f  mov     rax, [rbp+57h+arg_18]
0x1800303a3  mov     [rax], r15
0x1800303a6  jmp     loc_180030256
0x1800303ab  mov     rcx, [rbp+57h+var_60]
0x1800303af  test    rcx, rcx
0x1800303b2  jz      short loc_1800303B9
0x1800303b4  call    MpConfigClose
0x1800303b9  mov     rcx, [rbp+57h+var_70]
0x1800303bd  test    rcx, rcx
0x1800303c0  jz      short loc_1800303C7
0x1800303c2  call    MpConfigIteratorClose
0x1800303c7  mov     rcx, [rbp+57h+var_58]
0x1800303cb  test    rcx, rcx
0x1800303ce  jz      short loc_1800303E0
0x1800303d0  mov     rdx, [rbp+57h+var_48]
0x1800303d4  sub     rdx, rcx
0x1800303d7  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800303db  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800303e0  mov     eax, edi
0x1800303e2  jmp     short loc_18003041C
0x1800303e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800303eb  lea     r14, WPP_GLOBAL_Control
0x1800303f2  mov     ebx, 80070057h
0x1800303f7  cmp     rcx, r14
0x1800303fa  jz      short loc_18003041A
0x1800303fc  test    byte ptr [rcx+1Ch], 1
0x180030400  jz      short loc_18003041A
0x180030402  mov     edx, 1Eh
0x180030407  mov     rcx, [rcx+10h]
0x18003040b  lea     r8, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x180030412  mov     r9d, ebx
0x180030415  call    WPP_SF_d
0x18003041a  mov     eax, ebx
0x18003041c  mov     rbx, [rsp+0C0h+arg_0]
0x180030424  add     rsp, 90h
0x18003042b  pop     r15
0x18003042d  pop     r14
0x18003042f  pop     r13
0x180030431  pop     r12
0x180030433  pop     rdi
0x180030434  pop     rsi
0x180030435  pop     rbp
0x180030436  retn
```
