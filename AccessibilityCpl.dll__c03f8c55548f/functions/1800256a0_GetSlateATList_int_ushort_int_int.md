# GetSlateATList(int,ushort * *,int *,int *)

- ea: `0x1800256a0`
- end: `0x180025a10`
- name: `?GetSlateATList@@YAJHPEAPEAGPEAH1@Z`
- size: `880`
- prototype: `__int64 __fastcall(int, unsigned __int16 **, int *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a210`

## callees

- `0x18000546c`
- `0x1800055c0`
- `0x1800071c4`
- `0x180014828`
- `0x180014b34`
- `0x180014b84`
- `0x18001a67c`
- `0x18001ed60`
- `0x180024fd4`
- `0x180025068`
- `0x180025344`
- `0x1800255fc`
- `0x1800256a0`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800259cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800259cf`
- `ole32!CoTaskMemAlloc` at `0x180025840`
- `ole32!CoTaskMemAlloc` at `0x180025840`

## string_xrefs

- `0x180025721`: `Control Panel\Accessibility\SlateLaunch\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetSlateATList(__int64 a1, unsigned __int16 **a2, int *a3, int *a4)
{
  int *v4; // r14
  int v5; // ebx
  int v6; // r15d
  unsigned int v7; // r13d
  __int64 v8; // r12
  unsigned __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // r9
  char *v12; // rax
  char *v13; // r8
  int v14; // edx
  unsigned __int64 v15; // r15
  unsigned __int16 *v16; // rax
  _QWORD *v17; // r11
  unsigned __int64 v18; // rsi
  unsigned __int64 v19; // r9
  unsigned __int16 *v20; // rax
  int v21; // edx
  int v22; // esi
  int *v23; // rdx
  unsigned __int16 **v24; // r8
  __int64 v25; // r9
  int i; // ecx
  int v27; // eax
  unsigned int v29; // [rsp+20h] [rbp-438h] BYREF
  unsigned int v30[2]; // [rsp+28h] [rbp-430h] BYREF
  __int64 v31; // [rsp+30h] [rbp-428h]
  int *v32; // [rsp+38h] [rbp-420h]
  __int64 v33; // [rsp+40h] [rbp-418h] BYREF
  unsigned __int64 v34; // [rsp+48h] [rbp-410h]
  unsigned __int64 v35; // [rsp+50h] [rbp-408h]
  int v36; // [rsp+58h] [rbp-400h]
  _QWORD v37[3]; // [rsp+60h] [rbp-3F8h] BYREF
  unsigned int v38; // [rsp+78h] [rbp-3E0h] BYREF
  unsigned __int16 *v39; // [rsp+80h] [rbp-3D8h]
  unsigned __int16 **v40; // [rsp+88h] [rbp-3D0h]
  unsigned __int16 **v41; // [rsp+90h] [rbp-3C8h]
  int *v42; // [rsp+A0h] [rbp-3B8h]
  int *v43; // [rsp+A8h] [rbp-3B0h]
  _BYTE v44[352]; // [rsp+B0h] [rbp-3A8h] BYREF
  unsigned __int16 v45[256]; // [rsp+210h] [rbp-248h] BYREF

  v32 = a4;
  v4 = a3;
  v40 = a2;
  v41 = a2;
  v42 = a3;
  v43 = a4;
  v5 = 0;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v45[0] = 0;
  memset(v37, 0, sizeof(v37));
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)v37,
                        HKEY_CURRENT_USER,
                        L"Control Panel\\Accessibility\\SlateLaunch\\",
                        0x20019u) )
  {
    v29 = 0;
    if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v37, L"LaunchAT", &v29) )
    {
      if ( v29 )
      {
        v30[0] = 256;
        if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v37, L"ATapp", v45, v30) )
          v45[0] = 0;
      }
    }
  }
  v6 = 0;
  v7 = -1;
  v29 = -1;
  v8 = 0;
  v33 = 0;
  v9 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  ATManager::ATManager((ATManager *)v44, 0);
  try
  {
    *(_QWORD *)v30 = *(_QWORD *)ATManager::GetAccommodations(v44);
    v22 = 0;
    while ( v6 >= 0 && *(_QWORD *)v30 )
    {
      v11 = *(_QWORD *)ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
                         v10,
                         v30);
      v31 = v11;
      v12 = *(char **)(v11 + 40);
      if ( *((int *)v12 - 4) > 0 )
      {
        v13 = (char *)((char *)L"SystemSetting" - v12);
        do
        {
          v10 = *(unsigned __int16 *)&v13[(_QWORD)v12];
          v14 = *(unsigned __int16 *)v12 - (_DWORD)v10;
          if ( v14 )
            break;
          v12 += 2;
        }
        while ( (_DWORD)v10 );
        if ( v14 )
        {
          v15 = *(_DWORD *)(*(_QWORD *)(v11 + 8) - 16LL) + 1;
          v16 = (unsigned __int16 *)CoTaskMemAlloc(2 * v15);
          v39 = v16;
          if ( v16 )
          {
            v6 = StringCchCopyW(v16, v15, *(const unsigned __int16 **)(v31 + 8));
            if ( v6 >= 0 )
            {
              v18 = v9;
              if ( v9 >= v35 )
              {
                if ( !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATData>,ATL::CAutoPtrElementTraits<ATData>>::GrowBuffer(
                                         &v33,
                                         v9 + 1) )
                  ATL::AtlThrowImpl(-2147024882);
                v9 = v34;
                v8 = v33;
                v17 = (_QWORD *)v31;
              }
              *(_QWORD *)(v8 + 8 * v18) = v39;
              v19 = v9 + 1;
              v9 = v19;
              v34 = v19;
              if ( v45[0] )
              {
                v20 = v45;
                do
                {
                  v10 = *(unsigned __int16 *)((char *)v20 + *v17 - (_QWORD)v45);
                  v21 = *v20 - (_DWORD)v10;
                  if ( v21 )
                    break;
                  ++v20;
                }
                while ( (_DWORD)v10 );
                if ( !v21 )
                {
                  v7 = v19 - 1;
                  v29 = v19 - 1;
                }
              }
              v22 = v19;
              if ( v19 == 32 )
                break;
            }
          }
          else
          {
            v6 = -2147024882;
          }
        }
      }
    }
    ATManager::~ATManager((ATManager *)v44);
    v24 = v40;
  }
  catch ( ATL::CAtlException v38 )
  {
    v30[0] = v38;
    v5 = 0;
    v6 = v38;
    v7 = v29;
    v9 = v34;
    v22 = v34;
    v8 = v33;
    v24 = v41;
    v4 = v42;
    v23 = v43;
    v32 = v43;
  }
  v25 = 32;
  if ( v6 < 0 )
  {
    *v4 = 0;
    if ( v22 > 0 )
    {
      do
      {
        if ( v5 >= v9 )
LABEL_46:
          ATL::AtlThrowImpl(-2147024809);
        CoTaskMemFree(*(LPVOID *)(v8 + 8LL * v5++));
      }
      while ( v5 < v22 );
    }
  }
  else if ( v22 > 0 )
  {
    for ( i = 0; ; ++i )
    {
      v27 = v22;
      if ( v22 > 32 )
        v27 = 32;
      if ( i >= v27 )
        break;
      if ( i >= v9 )
        goto LABEL_46;
      v24[i] = *(unsigned __int16 **)(v8 + 8LL * i);
    }
    *v4 = v22;
    v23 = v32;
    if ( v32 )
      *v32 = v7;
  }
  ATL::CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>::~CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>(
    &v33,
    v23,
    v24,
    v25);
  ATL::CRegKey::Close((ATL::CRegKey *)v37);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800256a0  push    rbx
0x1800256a2  push    rsi
0x1800256a3  push    rdi
0x1800256a4  push    r12
0x1800256a6  push    r13
0x1800256a8  push    r14
0x1800256aa  push    r15
0x1800256ac  sub     rsp, 420h
0x1800256b3  mov     rax, cs:__security_cookie
0x1800256ba  xor     rax, rsp
0x1800256bd  mov     [rsp+458h+var_48], rax
0x1800256c5  mov     [rsp+458h+var_420], r9
0x1800256ca  mov     r14, r8
0x1800256cd  mov     [rsp+458h+var_3D0], rdx
0x1800256d5  mov     [rsp+458h+var_3C8], rdx
0x1800256dd  mov     [rsp+458h+var_3B8], r8
0x1800256e5  mov     [rsp+458h+var_3B0], r9
0x1800256ed  xor     ebx, ebx
0x1800256ef  test    rdx, rdx
0x1800256f2  jz      loc_1800259E8
0x1800256f8  test    r8, r8
0x1800256fb  jz      loc_1800259E8
0x180025701  mov     [r8], ebx
0x180025704  mov     [rsp+458h+var_248], bx
0x18002570c  mov     [rsp+458h+var_3F8], rbx
0x180025711  mov     [rsp+458h+var_3F0], rbx
0x180025716  mov     [rsp+458h+var_3E8], rbx
0x18002571b  mov     r9d, 20019h; unsigned int
0x180025721  lea     r8, aControlPanelAc_0; "Control Panel\\Accessibility\\SlateLaun"...
0x180025728  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18002572f  lea     rcx, [rsp+458h+var_3F8]; this
0x180025734  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180025739  test    eax, eax
0x18002573b  jnz     short loc_180025793
0x18002573d  mov     [rsp+458h+var_438], ebx
0x180025741  lea     r8, [rsp+458h+var_438]; unsigned int *
0x180025746  lea     rdx, aLaunchat; "LaunchAT"
0x18002574d  lea     rcx, [rsp+458h+var_3F8]; this
0x180025752  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180025757  test    eax, eax
0x180025759  jnz     short loc_180025793
0x18002575b  cmp     [rsp+458h+var_438], ebx
0x18002575f  jz      short loc_180025793
0x180025761  mov     [rsp+458h+var_430], 100h
0x180025769  lea     r9, [rsp+458h+var_430]; unsigned int *
0x18002576e  lea     r8, [rsp+458h+var_248]; unsigned __int16 *
0x180025776  lea     rdx, aAtapp; "ATapp"
0x18002577d  lea     rcx, [rsp+458h+var_3F8]; this
0x180025782  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x180025787  test    eax, eax
0x180025789  jz      short loc_180025793
0x18002578b  mov     [rsp+458h+var_248], bx
0x180025793  mov     r15d, ebx
0x180025796  or      r13d, 0FFFFFFFFh
0x18002579a  mov     [rsp+458h+var_438], r13d
0x18002579f  mov     r12, rbx
0x1800257a2  mov     [rsp+458h+var_418], rbx
0x1800257a7  mov     rdi, rbx
0x1800257aa  mov     [rsp+458h+var_410], rbx
0x1800257af  mov     [rsp+458h+var_408], rbx
0x1800257b4  mov     [rsp+458h+var_400], ebx
0x1800257b8  xor     edx, edx; int
0x1800257ba  lea     rcx, [rsp+458h+var_3A8]; this
0x1800257c2  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x1800257c7  nop
0x1800257c8  lea     rcx, [rsp+458h+var_3A8]
0x1800257d0  call    ?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ; ATManager::GetAccommodations(void)
0x1800257d5  mov     rax, [rax]
0x1800257d8  mov     qword ptr [rsp+458h+var_430], rax
0x1800257dd  mov     esi, ebx
0x1800257df  test    r15d, r15d
0x1800257e2  js      loc_180025908
0x1800257e8  cmp     qword ptr [rsp+458h+var_430], rbx
0x1800257ed  jz      loc_180025908
0x1800257f3  lea     rdx, [rsp+458h+var_430]
0x1800257f8  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x1800257fd  mov     r9, [rax]
0x180025800  mov     [rsp+458h+var_428], r9
0x180025805  mov     rax, [r9+28h]
0x180025809  cmp     [rax-10h], ebx
0x18002580c  jle     short loc_1800257DF
0x18002580e  lea     r8, aSystemsetting_0; "SystemSetting"
0x180025815  sub     r8, rax
0x180025818  movzx   edx, word ptr [rax]
0x18002581b  movzx   ecx, word ptr [rax+r8]
0x180025820  sub     edx, ecx
0x180025822  jnz     short loc_18002582C
0x180025824  add     rax, 2
0x180025828  test    ecx, ecx
0x18002582a  jnz     short loc_180025818
0x18002582c  test    edx, edx
0x18002582e  jz      short loc_1800257DF
0x180025830  mov     rax, [r9+8]
0x180025834  mov     ecx, [rax-10h]
0x180025837  inc     ecx
0x180025839  movsxd  r15, ecx
0x18002583c  lea     rcx, [r15+r15]; cb
0x180025840  call    cs:__imp_CoTaskMemAlloc
0x180025846  mov     [rsp+458h+var_3D8], rax
0x18002584e  test    rax, rax
0x180025851  jz      loc_180025920
0x180025857  mov     r11, [rsp+458h+var_428]
0x18002585c  mov     r8, [r11+8]; unsigned __int16 *
0x180025860  mov     rdx, r15; unsigned __int64
0x180025863  mov     rcx, rax; unsigned __int16 *
0x180025866  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002586b  mov     r15d, eax
0x18002586e  test    eax, eax
0x180025870  js      loc_1800257DF
0x180025876  mov     rsi, rdi
0x180025879  cmp     rdi, [rsp+458h+var_408]
0x18002587e  jb      short loc_1800258AB
0x180025880  lea     rdx, [rdi+1]
0x180025884  lea     rcx, [rsp+458h+var_418]
0x180025889  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VATData@@@ATL@@V?$CAutoPtrElementTraits@VATData@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATData>,ATL::CAutoPtrElementTraits<ATData>>::GrowBuffer(unsigned __int64)
0x18002588e  test    al, al
0x180025890  jnz     short loc_18002589C
0x180025892  mov     ecx, 8007000Eh; int
0x180025897  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002589c  mov     rdi, [rsp+458h+var_410]
0x1800258a1  mov     r12, [rsp+458h+var_418]
0x1800258a6  mov     r11, [rsp+458h+var_428]
0x1800258ab  mov     rax, [rsp+458h+var_3D8]
0x1800258b3  mov     [r12+rsi*8], rax
0x1800258b7  lea     r9, [rdi+1]
0x1800258bb  mov     rdi, r9
0x1800258be  mov     [rsp+458h+var_410], r9
0x1800258c3  cmp     [rsp+458h+var_248], bx
0x1800258cb  jz      short loc_1800258FC
0x1800258cd  lea     rax, [rsp+458h+var_248]
0x1800258d5  mov     r8, [r11]
0x1800258d8  sub     r8, rax
0x1800258db  movzx   edx, word ptr [rax]
0x1800258de  movzx   ecx, word ptr [rax+r8]
0x1800258e3  sub     edx, ecx
0x1800258e5  jnz     short loc_1800258EF
0x1800258e7  add     rax, 2
0x1800258eb  test    ecx, ecx
0x1800258ed  jnz     short loc_1800258DB
0x1800258ef  test    edx, edx
0x1800258f1  jnz     short loc_1800258FC
0x1800258f3  lea     r13d, [r9-1]
0x1800258f7  mov     [rsp+458h+var_438], r13d
0x1800258fc  mov     esi, edi
0x1800258fe  cmp     r9, 20h ; ' '
0x180025902  jnz     loc_1800257DF
0x180025908  lea     rcx, [rsp+458h+var_3A8]; this
0x180025910  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x180025915  nop
0x180025916  mov     r8, [rsp+458h+var_3D0]
0x18002591e  jmp     short loc_180025960
0x180025920  mov     r15d, 8007000Eh
0x180025926  jmp     loc_1800257DF
0x18002592b  xor     ebx, ebx
0x18002592d  mov     r15d, [rsp+458h+var_430]
0x180025932  mov     r13d, [rsp+458h+var_438]
0x180025937  mov     rdi, [rsp+458h+var_410]
0x18002593c  mov     esi, edi
0x18002593e  mov     r12, [rsp+458h+var_418]
0x180025943  mov     r8, [rsp+458h+var_3C8]
0x18002594b  mov     r14, [rsp+458h+var_3B8]
0x180025953  mov     rdx, [rsp+458h+var_3B0]
0x18002595b  mov     [rsp+458h+var_420], rdx
0x180025960  mov     r9d, 20h ; ' '
0x180025966  test    r15d, r15d
0x180025969  js      short loc_1800259BC
0x18002596b  test    esi, esi
0x18002596d  jle     short loc_1800259A2
0x18002596f  mov     ecx, ebx
0x180025971  mov     eax, esi
0x180025973  cmp     esi, r9d
0x180025976  cmovg   eax, r9d
0x18002597a  cmp     ecx, eax
0x18002597c  jge     short loc_180025992
0x18002597e  movsxd  rdx, ecx
0x180025981  cmp     rdx, rdi
0x180025984  jnb     short loc_1800259DD
0x180025986  mov     rax, [r12+rdx*8]
0x18002598a  mov     [r8+rdx*8], rax
0x18002598e  inc     ecx
0x180025990  jmp     short loc_180025971
0x180025992  mov     [r14], esi
0x180025995  mov     rdx, [rsp+458h+var_420]
0x18002599a  test    rdx, rdx
0x18002599d  jz      short loc_1800259A2
0x18002599f  mov     [rdx], r13d
0x1800259a2  lea     rcx, [rsp+458h+var_418]
0x1800259a7  call    ??1?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>>::~CAtlArray<ushort *,ATL::CElementTraits<ushort *>>(void)
0x1800259ac  nop
0x1800259ad  lea     rcx, [rsp+458h+var_3F8]; this
0x1800259b2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800259b7  mov     eax, r15d
0x1800259ba  jmp     short loc_1800259ED
0x1800259bc  mov     [r14], ebx
0x1800259bf  test    esi, esi
0x1800259c1  jle     short loc_1800259A2
0x1800259c3  movsxd  rcx, ebx
0x1800259c6  cmp     rcx, rdi
0x1800259c9  jnb     short loc_1800259DD
0x1800259cb  mov     rcx, [r12+rcx*8]; pv
0x1800259cf  call    cs:__imp_CoTaskMemFree
0x1800259d5  inc     ebx
0x1800259d7  cmp     ebx, esi
0x1800259d9  jl      short loc_1800259C3
0x1800259db  jmp     short loc_1800259A2
0x1800259dd  mov     ecx, 80070057h; int
0x1800259e2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800259e8  mov     eax, 80004003h
0x1800259ed  mov     rcx, [rsp+458h+var_48]
0x1800259f5  xor     rcx, rsp; StackCookie
0x1800259f8  call    __security_check_cookie
0x1800259fd  add     rsp, 420h
0x180025a04  pop     r15
0x180025a06  pop     r14
0x180025a08  pop     r13
0x180025a0a  pop     r12
0x180025a0c  pop     rdi
0x180025a0d  pop     rsi
0x180025a0e  pop     rbx
0x180025a0f  retn
```
