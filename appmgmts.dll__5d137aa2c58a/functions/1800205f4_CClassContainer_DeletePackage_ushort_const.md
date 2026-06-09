# CClassContainer::DeletePackage(ushort const *)

- ea: `0x1800205f4`
- end: `0x1800208bb`
- name: `?DeletePackage@CClassContainer@@QEAAJPEBG@Z`
- size: `711`
- prototype: `int __fastcall(CClassContainer *this, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update`

## callers

- `0x180020180`
- `0x1800208c4`
- `0x180022e00`

## callees

- `0x1800016d0`
- `0x18001b1a0`
- `0x18001d130`
- `0x18001e82c`
- `0x1800205f4`
- `0x180023448`
- `0x18002350c`
- `0x180024218`
- `0x180024b90`
- `0x180026f3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800207e8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800207e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020735`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002081c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002081c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002071d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002071d`
- `adsldpc!ADSIGetObjectAttributes` at `0x1800206cc`
- `adsldpc!ADSIGetObjectAttributes` at `0x1800206cc`
- `adsldpc!ADSICloseDSObject` at `0x180020836`
- `adsldpc!ADSICloseDSObject` at `0x180020836`
- `adsldpc!BuildADsParentPath` at `0x180020847`
- `adsldpc!BuildADsParentPath` at `0x180020847`
- `adsldpc!ADSIDeleteDSObject` at `0x180020867`
- `adsldpc!ADSIDeleteDSObject` at `0x180020867`
- `adsldpc!FreeADsMem` at `0x18002082c`
- `adsldpc!FreeADsMem` at `0x180020856`
- `adsldpc!FreeADsMem` at `0x180020878`
- `adsldpc!FreeADsMem` at `0x18002082c`
- `adsldpc!FreeADsMem` at `0x180020856`
- `adsldpc!FreeADsMem` at `0x180020878`

## string_xrefs

- `0x18002063e`: `msiScriptPath`

## pseudocode

```c
int __fastcall CClassContainer::DeletePackage(CClassContainer *this, unsigned __int16 *a2)
{
  CClassContainer *v3; // r13
  unsigned int v4; // r14d
  wchar_t *v5; // rsi
  unsigned int v6; // eax
  int result; // eax
  unsigned int PropertyFromAttr; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rbx
  BOOL v12; // eax
  DWORD LastError; // eax
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int128 v17; // xmm1
  unsigned int v18; // edi
  __int64 v19; // rbx
  __int64 v20; // r15
  int v21; // ebx
  unsigned int v22; // [rsp+30h] [rbp-89h] BYREF
  LPVOID pMem; // [rsp+38h] [rbp-81h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-79h] BYREF
  wchar_t *EndPtr; // [rsp+48h] [rbp-71h] BYREF
  void *v26; // [rsp+50h] [rbp-69h] BYREF
  LPVOID v27; // [rsp+58h] [rbp-61h] BYREF
  LPVOID v28; // [rsp+60h] [rbp-59h] BYREF
  CClassContainer *v29; // [rsp+68h] [rbp-51h]
  struct _GUID v30; // [rsp+70h] [rbp-49h] BYREF
  __int128 v31; // [rsp+80h] [rbp-39h]
  _QWORD v32[3]; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int16 v33[20]; // [rsp+A8h] [rbp-11h] BYREF

  v29 = this;
  v24 = 0;
  v22 = 0;
  v27 = 0;
  v3 = this;
  v28 = 0;
  v4 = 0;
  EndPtr = 0;
  v5 = 0;
  v32[0] = L"canUpgradeScript";
  v32[1] = L"objectGUID";
  v32[2] = L"msiScriptPath";
  pMem = 0;
  v26 = 0;
  if ( (gCsOptions & 1) != 0 )
    v6 = GetADsOpenObjectFlags() | 0x21;
  else
    v6 = 101;
  result = DSServerOpenDSObject((CClassContainer *)((char *)v3 + 592), a2, v6, &v26);
  if ( result >= 0 )
  {
    GetCurrentUsn(v33);
    ADSIGetObjectAttributes(v26, v32, 3, &pMem, &v22);
    GetPropertyFromAttr((struct _ads_attr_info *)pMem, v22, L"objectGUID");
    PropertyFromAttr = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v22, L"msiScriptPath");
    if ( PropertyFromAttr < v22 )
    {
      v9 = 32LL * PropertyFromAttr;
      if ( *(_DWORD *)((char *)pMem + v9 + 24) )
      {
        v10 = *(_QWORD *)((char *)pMem + v9 + 16);
        v11 = *(_QWORD *)(v10 + 8);
        if ( v11 )
        {
          v12 = DeleteFileW(*(LPCWSTR *)(v10 + 8));
          if ( gDebug )
          {
            if ( v12 )
              LastError = 0;
            else
              LastError = GetLastError();
            _DebugMsg(2, 0xC80u, v11, LastError);
          }
        }
      }
    }
    v14 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v22, L"canUpgradeScript");
    if ( v14 < v22 )
    {
      v16 = 32LL * v14;
      v17 = *(_OWORD *)((char *)pMem + v16 + 16);
      v30 = *(struct _GUID *)((char *)pMem + v16);
      v31 = v17;
      UnpackStrArrFrom<_ads_attr_info>((__int64)&v30, &EndPtr, &v24);
      v4 = v24;
      v5 = EndPtr;
    }
    v18 = 0;
    if ( v4 )
    {
      do
      {
        EndPtr = 0;
        v19 = -1;
        v30 = 0;
        v20 = *(_QWORD *)&v5[4 * v18];
        do
          ++v19;
        while ( *(_WORD *)(v20 + 2 * v19) );
        if ( (unsigned int)v19 > 0x29 )
        {
          *(_WORD *)(v20 + 2LL * (unsigned int)(v19 - 3)) = 0;
          wcstoul((const wchar_t *)(v20 + 2LL * (unsigned int)(v19 - 2)), &EndPtr, 16);
          *(_WORD *)(v20 + 2LL * (unsigned int)(v19 - 41)) = 0;
          GUIDFromString((const unsigned __int16 *)(v20 + 2 * ((unsigned int)v19 - 39LL)), &v30);
        }
        ++v18;
      }
      while ( v18 < v4 );
      v3 = v29;
    }
    if ( v5 )
      LocalFree(v5);
    if ( pMem )
      FreeADsMem(pMem);
    ADSICloseDSObject(v26, v15);
    BuildADsParentPath(a2, (unsigned __int16 **)&v28, (unsigned __int16 **)&v27);
    if ( v28 )
      FreeADsMem(v28);
    v21 = ADSIDeleteDSObject(*((_QWORD *)v3 + 70), v27);
    if ( v27 )
      FreeADsMem(v27);
    if ( v21 >= 0 )
      UpdateStoreUsn(*((void **)v3 + 69), v33);
    return v21;
  }
  return result;
}

```

## disassembly

```asm
0x1800205f4  mov     [rsp-8+arg_10], rbx
0x1800205f9  push    rbp
0x1800205fa  push    rsi
0x1800205fb  push    rdi
0x1800205fc  push    r12
0x1800205fe  push    r13
0x180020600  push    r14
0x180020602  push    r15
0x180020604  lea     rbp, [rsp-27h]
0x180020609  sub     rsp, 0E0h
0x180020610  mov     rax, cs:__security_cookie
0x180020617  xor     rax, rsp
0x18002061a  mov     [rbp+57h+var_40], rax
0x18002061e  xor     r15d, r15d
0x180020621  mov     [rbp+57h+var_A8], rcx
0x180020625  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x18002062c  lea     rax, aCanupgradescri; "canUpgradeScript"
0x180020633  lea     rbx, aObjectguid; "objectGUID"
0x18002063a  mov     [rbp+57h+var_D0], r15d
0x18002063e  lea     rdi, aMsiscriptpath; "msiScriptPath"
0x180020645  mov     [rsp+110h+var_E0], r15d
0x18002064a  mov     r12, rdx
0x18002064d  mov     [rbp+57h+var_B8], r15
0x180020651  mov     r13, rcx
0x180020654  mov     [rbp+57h+var_B0], r15
0x180020658  mov     r14d, r15d
0x18002065b  mov     [rbp+57h+EndPtr], r15
0x18002065f  mov     esi, r15d
0x180020662  mov     [rbp+57h+var_80], rax
0x180020666  mov     [rbp+57h+var_78], rbx
0x18002066a  mov     [rbp+57h+var_70], rdi
0x18002066e  mov     [rsp+110h+pMem], r15
0x180020673  mov     [rbp+57h+var_C0], r15
0x180020677  jz      short loc_180020683
0x180020679  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x18002067e  or      eax, 21h
0x180020681  jmp     short loc_180020688
0x180020683  mov     eax, 65h ; 'e'
0x180020688  lea     rcx, [r13+250h]; struct CServerContext *
0x18002068f  mov     r8d, eax; int
0x180020692  lea     r9, [rbp+57h+var_C0]; void **
0x180020696  mov     rdx, r12; unsigned __int16 *
0x180020699  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x18002069e  test    eax, eax
0x1800206a0  js      loc_180020894
0x1800206a6  lea     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x1800206aa  call    ?GetCurrentUsn@@YAXPEAG@Z; GetCurrentUsn(ushort *)
0x1800206af  mov     rcx, [rbp+57h+var_C0]
0x1800206b3  lea     rax, [rsp+110h+var_E0]
0x1800206b8  lea     r9, [rsp+110h+pMem]
0x1800206bd  mov     [rsp+110h+var_F0], rax
0x1800206c2  mov     r8d, 3
0x1800206c8  lea     rdx, [rbp+57h+var_80]
0x1800206cc  call    cs:__imp_ADSIGetObjectAttributes
0x1800206d2  mov     edx, [rsp+110h+var_E0]; unsigned int
0x1800206d6  mov     r8, rbx; unsigned __int16 *
0x1800206d9  mov     rcx, [rsp+110h+pMem]; struct _ads_attr_info *
0x1800206de  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x1800206e3  mov     edx, [rsp+110h+var_E0]; unsigned int
0x1800206e7  mov     r8, rdi; unsigned __int16 *
0x1800206ea  mov     rcx, [rsp+110h+pMem]; struct _ads_attr_info *
0x1800206ef  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x1800206f4  cmp     eax, [rsp+110h+var_E0]
0x1800206f8  jnb     short loc_180020750
0x1800206fa  mov     rcx, [rsp+110h+pMem]
0x1800206ff  mov     eax, eax
0x180020701  shl     rax, 5
0x180020705  cmp     [rax+rcx+18h], r15d
0x18002070a  jz      short loc_180020750
0x18002070c  mov     rax, [rax+rcx+10h]
0x180020711  mov     rbx, [rax+8]
0x180020715  test    rbx, rbx
0x180020718  jz      short loc_180020750
0x18002071a  mov     rcx, rbx; lpFileName
0x18002071d  call    cs:__imp_DeleteFileW
0x180020723  cmp     cs:?gDebug@@3KA, r15d; ulong gDebug
0x18002072a  jz      short loc_180020750
0x18002072c  test    eax, eax
0x18002072e  jz      short loc_180020735
0x180020730  mov     eax, r15d
0x180020733  jmp     short loc_18002073B
0x180020735  call    cs:__imp_GetLastError
0x18002073b  mov     r9d, eax
0x18002073e  mov     r8, rbx
0x180020741  mov     edx, 0C80h; unsigned int
0x180020746  mov     ecx, 2; unsigned int
0x18002074b  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180020750  mov     edx, [rsp+110h+var_E0]; unsigned int
0x180020754  lea     r8, aCanupgradescri; "canUpgradeScript"
0x18002075b  mov     rcx, [rsp+110h+pMem]; struct _ads_attr_info *
0x180020760  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x180020765  cmp     eax, [rsp+110h+var_E0]
0x180020769  jnb     short loc_1800207A0
0x18002076b  mov     ecx, eax
0x18002076d  lea     r8, [rbp+57h+var_D0]
0x180020771  mov     rax, [rsp+110h+pMem]
0x180020776  lea     rdx, [rbp+57h+EndPtr]
0x18002077a  shl     rcx, 5
0x18002077e  movups  xmm0, xmmword ptr [rcx+rax]
0x180020782  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x180020787  lea     rcx, [rbp+57h+var_A0]
0x18002078b  movaps  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x18002078f  movaps  [rbp+57h+var_90], xmm1
0x180020793  call    ??$UnpackStrArrFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAPEAGPEAK@Z; UnpackStrArrFrom<_ads_attr_info>(_ads_attr_info,ushort * * *,ulong *)
0x180020798  mov     r14d, [rbp+57h+var_D0]
0x18002079c  mov     rsi, [rbp+57h+EndPtr]
0x1800207a0  mov     edi, r15d
0x1800207a3  test    r14d, r14d
0x1800207a6  jz      short loc_180020814
0x1800207a8  xor     r13d, r13d
0x1800207ab  mov     eax, edi
0x1800207ad  xorps   xmm0, xmm0
0x1800207b0  mov     [rbp+57h+EndPtr], r13
0x1800207b4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800207b8  movups  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x1800207bc  mov     r15, [rsi+rax*8]
0x1800207c0  inc     rbx
0x1800207c3  cmp     [r15+rbx*2], r13w
0x1800207c8  jnz     short loc_1800207C0
0x1800207ca  cmp     ebx, 29h ; ')'
0x1800207cd  jbe     short loc_180020809
0x1800207cf  lea     eax, [rbx-3]
0x1800207d2  mov     r8d, 10h; Radix
0x1800207d8  mov     [r15+rax*2], r13w
0x1800207dd  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1800207e1  lea     eax, [rbx-2]
0x1800207e4  lea     rcx, [r15+rax*2]; String
0x1800207e8  call    cs:__imp_wcstoul
0x1800207ee  lea     eax, [rbx-29h]
0x1800207f1  lea     rdx, [rbp+57h+var_A0]; struct _GUID *
0x1800207f5  mov     [r15+rax*2], r13w
0x1800207fa  mov     eax, ebx
0x1800207fc  add     rax, 0FFFFFFFFFFFFFFD9h
0x180020800  lea     rcx, [r15+rax*2]; unsigned __int16 *
0x180020804  call    ?GUIDFromString@@YAXPEBGPEAU_GUID@@@Z; GUIDFromString(ushort const *,_GUID *)
0x180020809  inc     edi
0x18002080b  cmp     edi, r14d
0x18002080e  jb      short loc_1800207AB
0x180020810  mov     r13, [rbp+57h+var_A8]
0x180020814  test    rsi, rsi
0x180020817  jz      short loc_180020822
0x180020819  mov     rcx, rsi; hMem
0x18002081c  call    cs:__imp_LocalFree
0x180020822  mov     rcx, [rsp+110h+pMem]; pMem
0x180020827  test    rcx, rcx
0x18002082a  jz      short loc_180020832
0x18002082c  call    cs:__imp_FreeADsMem
0x180020832  mov     rcx, [rbp+57h+var_C0]
0x180020836  call    cs:__imp_ADSICloseDSObject
0x18002083c  lea     r8, [rbp+57h+var_B8]
0x180020840  mov     rcx, r12
0x180020843  lea     rdx, [rbp+57h+var_B0]
0x180020847  call    cs:__imp_?BuildADsParentPath@@YAJPEAGPEAPEAG1@Z; BuildADsParentPath(ushort *,ushort * *,ushort * *)
0x18002084d  mov     rcx, [rbp+57h+var_B0]; pMem
0x180020851  test    rcx, rcx
0x180020854  jz      short loc_18002085C
0x180020856  call    cs:__imp_FreeADsMem
0x18002085c  mov     rdx, [rbp+57h+var_B8]
0x180020860  mov     rcx, [r13+230h]
0x180020867  call    cs:__imp_ADSIDeleteDSObject
0x18002086d  mov     rcx, [rbp+57h+var_B8]; pMem
0x180020871  mov     ebx, eax
0x180020873  test    rcx, rcx
0x180020876  jz      short loc_18002087E
0x180020878  call    cs:__imp_FreeADsMem
0x18002087e  test    ebx, ebx
0x180020880  js      short loc_180020892
0x180020882  mov     rcx, [r13+228h]; void *
0x180020889  lea     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x18002088d  call    ?UpdateStoreUsn@@YAJPEAXPEBG@Z; UpdateStoreUsn(void *,ushort const *)
0x180020892  mov     eax, ebx
0x180020894  mov     rcx, [rbp+57h+var_40]
0x180020898  xor     rcx, rsp; StackCookie
0x18002089b  call    __security_check_cookie
0x1800208a0  mov     rbx, [rsp+110h+arg_10]
0x1800208a8  add     rsp, 0E0h
0x1800208af  pop     r15
0x1800208b1  pop     r14
0x1800208b3  pop     r13
0x1800208b5  pop     r12
0x1800208b7  pop     rdi
0x1800208b8  pop     rsi
0x1800208b9  pop     rbp
0x1800208ba  retn
```
