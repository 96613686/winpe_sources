# QueryExtensibleData(COLLECT_THREAD_DATA *)

- ea: `0x18000d240`
- end: `0x18000dbce`
- name: `?QueryExtensibleData@@YAJPEAUCOLLECT_THREAD_DATA@@@Z`
- size: `2446`
- prototype: `__int64 __fastcall(struct COLLECT_THREAD_DATA *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callers

- `0x18002b280`

## callees

- `0x18000c614`
- `0x18000c6f0`
- `0x18000d240`
- `0x18000dbd4`
- `0x18000dc60`
- `0x18000dc80`
- `0x18000e6ac`
- `0x18000e704`
- `0x18000e7cc`
- `0x18000eb18`
- `0x18003e354`
- `0x18003fb18`
- `0x18003fb5c`
- `0x18003fd04`
- `0x180041684`
- `0x180063f10`
- `0x180072042`

## import_xrefs

- `ntdll!RtlWakeAddressAll` at `0x18000d421`
- `ntdll!RtlWakeAddressAll` at `0x18000d421`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d751`
- `KERNEL32!LocalFree` at `0x18000d792`
- `KERNEL32!LocalFree` at `0x18000d80d`
- `KERNEL32!LocalFree` at `0x18000d8a0`
- `KERNEL32!LocalFree` at `0x18000d792`
- `KERNEL32!LocalFree` at `0x18000d80d`
- `KERNEL32!LocalFree` at `0x18000d8a0`

## pseudocode

```c
__int64 __fastcall QueryExtensibleData(struct COLLECT_THREAD_DATA *a1)
{
  unsigned int *v1; // rax
  struct COLLECT_THREAD_DATA *v2; // r15
  _DWORD *v3; // r14
  unsigned int v4; // edi
  __int64 v5; // rbx
  void *v6; // rsi
  unsigned __int8 IsDisabled; // al
  __int16 v8; // si
  __int64 v9; // rbx
  int v10; // r14d
  unsigned int v11; // r13d
  __int64 v12; // r9
  _QWORD *v13; // r10
  const wchar_t *v14; // r8
  unsigned int v15; // r12d
  _WORD *v16; // r8
  struct EXT_OBJ_LIST *v17; // rdi
  struct EXT_OBJ_LIST *v18; // r12
  int v19; // edx
  unsigned int v20; // ecx
  _WORD *v21; // rbx
  int v22; // r9d
  char *v23; // rdi
  struct EXT_OBJ_LIST *v24; // rcx
  char *v25; // rdx
  _QWORD *v26; // rcx
  __int64 result; // rax
  unsigned __int32 v28; // ebx
  struct EXT_OBJ_LIST *i; // rbx
  unsigned int v30; // r15d
  _DWORD *v31; // rsi
  __int64 v32; // r14
  struct EXT_OBJ_LIST *v33; // rax
  char *v34; // rsi
  _DWORD *v35; // rdi
  const wchar_t *v36; // rdx
  _DWORD *v37; // rbx
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  const unsigned __int16 *v40; // rsi
  DWORD CurrentThreadId; // eax
  unsigned int v42; // ebx
  struct EXT_OBJ_LIST *j; // rax
  char *v44; // rbx
  _DWORD *v45; // rax
  __int64 v46; // rdx
  void *v47; // r9
  int V2Provider; // eax
  HLOCAL Src; // [rsp+40h] [rbp-29h] BYREF
  __int64 v50; // [rsp+48h] [rbp-21h] BYREF
  _DWORD *v51; // [rsp+50h] [rbp-19h]
  __int64 v52; // [rsp+58h] [rbp-11h]
  HLOCAL hMem; // [rsp+60h] [rbp-9h] BYREF
  struct EXT_OBJ_LIST *v54; // [rsp+68h] [rbp-1h]
  struct EXT_OBJ_LIST *v55; // [rsp+70h] [rbp+7h]
  size_t Size; // [rsp+D0h] [rbp+67h] BYREF
  unsigned int v57; // [rsp+D8h] [rbp+6Fh] BYREF
  int v58; // [rsp+E0h] [rbp+77h] BYREF
  void *v59; // [rsp+E8h] [rbp+7Fh] BYREF

  Size = (size_t)a1;
  v1 = (unsigned int *)*((_QWORD *)a1 + 3);
  v2 = a1;
  v3 = (_DWORD *)*((_QWORD *)a1 + 2);
  v4 = *(unsigned __int16 *)a1;
  v51 = v3;
  if ( v1 )
    v5 = *v1;
  else
    v5 = 0;
  v6 = (void *)**((_QWORD **)a1 + 4);
  v59 = v6;
  Src = v6;
  IsDisabled = PerflibciIsDisabled();
  if ( ((unsigned __int8)v6 & 7) != 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 1784;
    v46 = 28;
    v47 = v6;
    goto LABEL_125;
  }
  if ( ((unsigned __int8)v3 & 7) != 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 1784;
    v46 = 29;
    v47 = v3;
LABEL_125:
    WPP_SF_q(v26[2], v46, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v47);
    return 1784;
  }
  v8 = *((_WORD *)v2 + 1);
  v9 = (__int64)v3 + v5;
  v10 = IsDisabled;
  v11 = v4;
  v58 = IsDisabled;
  v52 = v9;
  LOWORD(v57) = v8;
  if ( IsDisabled && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
  v12 = (unsigned int)_InterlockedIncrement(&dwExtObjListRefCount);
  v13 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v12);
    v13 = WPP_GLOBAL_Control;
  }
  v14 = L"Global";
  v15 = 234;
  if ( v4 != 2 || v10 )
  {
    if ( v8 || ((v4 - 1) & 0xFFFFFFF7) != 0 )
    {
      v34 = (char *)v59;
      goto LABEL_56;
    }
    V2Provider = QueryV2Provider(L"Global", 0, 0, (__int64)&Src, (__int64)(v51 + 7));
    v34 = (char *)Src;
    if ( V2Provider == 234 )
      goto LABEL_28;
    v13 = WPP_GLOBAL_Control;
LABEL_55:
    v14 = L"Global";
LABEL_56:
    v35 = ExtensibleObjects;
    v36 = L"Costly";
    while ( 1 )
    {
      if ( !v35 )
      {
        v15 = 0;
        goto LABEL_28;
      }
      if ( v11 == 2 )
      {
        if ( !v10 && (v35[95] & 0x80000010) == 0x80000000 )
          goto LABEL_62;
      }
      else if ( !v10 )
      {
        goto LABEL_62;
      }
      if ( *((_QWORD *)v35 + 11) )
      {
        if ( (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 4u )
          WPP_SF_Sd(
            v13[2],
            38,
            (unsigned int)WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
            *((_QWORD *)v35 + 49),
            v11);
        if ( (unsigned int)PerfpLockExtObject(v35, v36, v14) )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              39,
              WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
              *((_QWORD *)v35 + 49));
        }
        else
        {
          CloseExtObjectLibrary((struct EXT_OBJECT *)v35, v10);
          PerfpUnlockExtObject(v35);
        }
        v37 = v35 + 95;
        v36 = L"Costly";
        goto LABEL_65;
      }
LABEL_62:
      v37 = v35 + 95;
      v38 = v35[95];
      if ( (v38 & 0x10) != 0 )
        goto LABEL_65;
      switch ( v11 )
      {
        case 2u:
          if ( v38 >= 0 )
            goto LABEL_65;
          v39 = (const unsigned __int16 *)*((_QWORD *)v2 + 1);
          if ( !v39 )
            goto LABEL_65;
          break;
        case 1u:
          v39 = L"Global";
          break;
        case 3u:
          v39 = L"Foreigh";
          break;
        case 4u:
          v39 = L"Costly";
          break;
        case 9u:
          v39 = L"MetadataGlobal";
          if ( (v38 & 0x80u) == 0 )
            v39 = L"Global";
          break;
        case 0xAu:
          v39 = L"MetadataCostly";
          if ( (v38 & 0x80u) == 0 )
            v39 = L"Costly";
          break;
        default:
          goto LABEL_65;
      }
      LODWORD(v59) = 0;
      v58 = 0;
      if ( (unsigned int)QueryV1Provider(v39, v35, v11, v34, (int)v52 - (int)v34, &v58, &v59) == 234 )
        goto LABEL_28;
      v36 = L"Costly";
      v34 += (unsigned int)v58;
      v51[7] += (_DWORD)v59;
LABEL_65:
      *v37 &= ~0x80000000;
      v14 = L"Global";
      v13 = WPP_GLOBAL_Control;
      v35 = *(_DWORD **)v35;
    }
  }
  utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>(&hMem);
  v17 = v54;
  v18 = (struct EXT_OBJ_LIST *)hMem;
LABEL_10:
  while ( 1 )
  {
    LOWORD(v19) = *v16;
    if ( !*v16 )
      break;
    v20 = 0;
    v21 = v16;
    v22 = 0;
    while ( 1 )
    {
      if ( (_WORD)v19 != 32 )
      {
        v19 = (unsigned __int16)*v21;
        if ( (_WORD)v19 )
        {
          if ( (unsigned __int16)(v19 - 48) <= 9u )
          {
            v22 = 1;
            v20 = v19 + 2 * (5 * v20 - 24);
          }
          else
          {
            v22 = 0;
          }
          goto LABEL_16;
        }
      }
      if ( v22 || !(_WORD)v19 )
        break;
LABEL_16:
      if ( !++v21 )
        goto LABEL_10;
      LOWORD(v19) = *v21;
    }
    if ( v20 )
    {
      v50 = v20;
      if ( v17 != v55 )
      {
        *(_QWORD *)v17 = v50;
        v17 = (struct EXT_OBJ_LIST *)((char *)v17 + 8);
        v54 = v17;
        goto LABEL_82;
      }
      v23 = (char *)((char *)&v50 - (char *)v18);
      if ( !(unsigned __int8)utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::_Grow(&hMem) )
      {
        v15 = 14;
        if ( hMem != (HLOCAL)-1LL )
          operator delete(hMem);
        goto LABEL_142;
      }
      v24 = v54;
      v25 = (char *)&v50;
      v18 = (struct EXT_OBJ_LIST *)hMem;
      if ( (unsigned __int64)v23 < v54 - (struct EXT_OBJ_LIST *)hMem )
        v25 = &v23[(_QWORD)hMem];
      v17 = (struct EXT_OBJ_LIST *)((char *)v54 + 8);
      *(_QWORD *)v54 = *(_QWORD *)v25;
      v16 = v21;
      v54 = (struct EXT_OBJ_LIST *)((char *)v24 + 8);
    }
    else
    {
LABEL_82:
      v16 = v21;
    }
  }
  v13 = WPP_GLOBAL_Control;
  for ( i = v18; i != v17; i = (struct EXT_OBJ_LIST *)((char *)i + 8) )
  {
    v30 = *(_DWORD *)i;
    if ( (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 5u )
    {
      WPP_SF_d(v13[2], 31, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v30);
      v13 = WPP_GLOBAL_Control;
    }
    v31 = ExtensibleObjects;
    if ( ExtensibleObjects )
    {
      do
      {
        if ( v31[28] )
        {
          v32 = 0;
          do
          {
            if ( *(_DWORD *)i == v31[v32 + 29] )
            {
              *((_DWORD *)i + 1) |= 1u;
              v31[95] |= 0x80000000;
              v13 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
                  *((_QWORD *)v31 + 49));
                v13 = WPP_GLOBAL_Control;
              }
            }
            v32 = (unsigned int)(v32 + 1);
          }
          while ( (unsigned int)v32 < v31[28] );
        }
        else if ( v30 >= v31[93] && v30 <= v31[94] )
        {
          *((_DWORD *)i + 1) |= 1u;
          v31[95] |= 0x80000000;
          v13 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
              *((_QWORD *)v31 + 49));
            v13 = WPP_GLOBAL_Control;
          }
        }
        v31 = *(_DWORD **)v31;
      }
      while ( v31 );
    }
  }
  v33 = v18;
  while ( 2 )
  {
    if ( v33 == v17 )
    {
      v2 = (struct COLLECT_THREAD_DATA *)Size;
      goto LABEL_52;
    }
    if ( (*((_BYTE *)v33 + 4) & 1) != 0 )
    {
      v33 = (struct EXT_OBJ_LIST *)((char *)v33 + 8);
      continue;
    }
    break;
  }
  if ( (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 5u )
  {
    WPP_SF_(v13[2], 34, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
    v13 = WPP_GLOBAL_Control;
  }
  if ( (_WORD)v57 )
  {
    v2 = (struct COLLECT_THREAD_DATA *)Size;
    goto LABEL_145;
  }
  if ( (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 4u )
    WPP_SF_(v13[2], 35, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
  v2 = (struct COLLECT_THREAD_DATA *)Size;
  Src = 0;
  LODWORD(Size) = 0;
  v57 = 0;
  v40 = (const unsigned __int16 *)*((_QWORD *)v2 + 1);
  CurrentThreadId = GetCurrentThreadId();
  v42 = PerflibciQueryV2Provider(
          CurrentThreadId,
          v40,
          v18,
          (v17 - v18) >> 3,
          (unsigned __int8 **)&Src,
          (unsigned int *)&Size,
          &v57);
  if ( v42 || !(_DWORD)Size )
  {
    LocalFree(Src);
    if ( v42 == 234 )
      goto LABEL_114;
LABEL_91:
    for ( j = v18; ; j = (struct EXT_OBJ_LIST *)((char *)j + 8) )
    {
      if ( j == v17 )
        goto LABEL_93;
      if ( (*((_BYTE *)j + 4) & 1) == 0 )
        break;
    }
    v13 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
        v13 = WPP_GLOBAL_Control;
      }
LABEL_145:
      if ( (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 3u )
      {
        WPP_SF_(v13[2], 37, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
        v13 = WPP_GLOBAL_Control;
      }
    }
    v45 = ExtensibleObjects;
    if ( ExtensibleObjects )
    {
      do
      {
        if ( !v45[28] )
          v45[95] |= 0x80000000;
        v45 = *(_DWORD **)v45;
      }
      while ( v45 );
LABEL_93:
      v13 = WPP_GLOBAL_Control;
    }
LABEL_52:
    if ( v18 != (struct EXT_OBJ_LIST *)-1LL )
    {
      operator delete(v18);
      v13 = WPP_GLOBAL_Control;
    }
    v34 = (char *)v59;
    v15 = 234;
    v10 = v58;
    goto LABEL_55;
  }
  v44 = (char *)v59;
  if ( (int)v52 - (int)v59 >= (unsigned int)Size )
  {
    memcpy_0(v59, Src, (unsigned int)Size);
    v59 = &v44[(unsigned int)Size];
    v51[7] += v57;
    LocalFree(Src);
    goto LABEL_91;
  }
  LocalFree(Src);
LABEL_114:
  if ( v18 != (struct EXT_OBJ_LIST *)-1LL )
    operator delete(v18);
  v10 = v58;
  v15 = 234;
LABEL_142:
  v34 = (char *)v59;
LABEL_28:
  v28 = _InterlockedDecrement(&dwExtObjListRefCount);
  if ( !v28 )
    RtlWakeAddressAll(&dwExtObjListRefCount);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v28);
  if ( v10 )
    v15 = 1058;
  result = v15;
  **((_QWORD **)v2 + 4) = v34;
  return result;
}

```

## disassembly

```asm
0x18000d240  mov     [rsp-8+Size], rcx
0x18000d245  push    rbp
0x18000d246  push    rbx
0x18000d247  push    rsi
0x18000d248  push    rdi
0x18000d249  push    r14
0x18000d24b  push    r15
0x18000d24d  lea     rbp, [rsp-2Fh]
0x18000d252  sub     rsp, 98h
0x18000d259  mov     rax, [rcx+18h]
0x18000d25d  mov     r15, rcx
0x18000d260  mov     r14, [rcx+10h]
0x18000d264  movzx   edi, word ptr [rcx]
0x18000d267  mov     [rbp+57h+var_70], r14
0x18000d26b  test    rax, rax
0x18000d26e  jz      loc_18000D895
0x18000d274  mov     ebx, [rax]
0x18000d276  mov     rax, [rcx+20h]
0x18000d27a  mov     rsi, [rax]
0x18000d27d  mov     [rbp+57h+arg_18], rsi
0x18000d281  mov     [rbp+57h+Src], rsi
0x18000d285  call    ?PerflibciIsDisabled@@YAEXZ; PerflibciIsDisabled(void)
0x18000d28a  test    sil, 7
0x18000d28e  jnz     loc_18000D3D6
0x18000d294  test    r14b, 7
0x18000d298  jnz     loc_18000D916
0x18000d29e  movzx   esi, word ptr [r15+2]
0x18000d2a3  add     rbx, r14
0x18000d2a6  movzx   r14d, al
0x18000d2aa  mov     [rsp+0C0h+var_30], r12
0x18000d2b2  mov     [rsp+0C0h+var_38], r13
0x18000d2ba  mov     r13d, edi
0x18000d2bd  mov     [rbp+57h+arg_10], r14d
0x18000d2c1  mov     [rbp+57h+var_68], rbx
0x18000d2c5  mov     word ptr [rbp+57h+arg_8], si
0x18000d2c9  test    al, al
0x18000d2cb  jnz     loc_18000D962
0x18000d2d1  mov     r9d, 1
0x18000d2d7  lock xadd cs:?dwExtObjListRefCount@@3JC, r9d; long volatile dwExtObjListRefCount
0x18000d2e0  inc     r9d
0x18000d2e3  mov     r10, cs:WPP_GLOBAL_Control
0x18000d2ea  test    byte ptr [r10+1Ch], 20h
0x18000d2ef  jnz     loc_18000D8E2
0x18000d2f5  lea     r8, ?GLOBAL_STRING@@3QBGB; "Global"
0x18000d2fc  mov     r12d, 0EAh
0x18000d302  cmp     r13d, 2
0x18000d306  jnz     loc_18000D8D0
0x18000d30c  test    r14d, r14d
0x18000d30f  jnz     loc_18000D8D0
0x18000d315  mov     r8, [r15+8]
0x18000d319  lea     rcx, [rbp+57h+hMem]
0x18000d31d  call    ??0?$vector@UEXT_OBJ_LIST@@V?$allocator@UEXT_OBJ_LIST@@@utl@@@utl@@QEAA@XZ; utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>(void)
0x18000d322  mov     rdi, [rbp+57h+var_58]
0x18000d326  mov     r12, [rbp+57h+hMem]
0x18000d32a  movzx   edx, word ptr [r8]
0x18000d32e  test    dx, dx
0x18000d331  jz      loc_18000D46D
0x18000d337  xor     ecx, ecx
0x18000d339  mov     rbx, r8
0x18000d33c  xor     r9d, r9d
0x18000d33f  cmp     dx, 20h ; ' '
0x18000d343  jz      short loc_18000D368
0x18000d345  movzx   edx, word ptr [rbx]
0x18000d348  test    dx, dx
0x18000d34b  jz      short loc_18000D368
0x18000d34d  lea     eax, [rdx-30h]
0x18000d350  cmp     ax, 9
0x18000d354  jbe     loc_18000DAEE
0x18000d35a  xor     r9d, r9d
0x18000d35d  add     rbx, 2
0x18000d361  jz      short loc_18000D32A
0x18000d363  movzx   edx, word ptr [rbx]
0x18000d366  jmp     short loc_18000D33F
0x18000d368  test    r9d, r9d
0x18000d36b  jz      loc_18000D6FF
0x18000d371  test    ecx, ecx
0x18000d373  jz      loc_18000D6F7
0x18000d379  mov     dword ptr [rbp+57h+var_78], ecx
0x18000d37c  mov     dword ptr [rbp+57h+var_78+4], 0
0x18000d383  cmp     rdi, [rbp+57h+var_50]
0x18000d387  jnz     loc_18000D6E8
0x18000d38d  lea     rdi, [rbp+57h+var_78]
0x18000d391  lea     rcx, [rbp+57h+hMem]
0x18000d395  sub     rdi, r12
0x18000d398  call    ?_Grow@?$vector@UEXT_OBJ_LIST@@V?$allocator@UEXT_OBJ_LIST@@@utl@@@utl@@AEAA_NXZ; utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::_Grow(void)
0x18000d39d  test    al, al
0x18000d39f  jz      loc_18000DA6F
0x18000d3a5  mov     rcx, [rbp+57h+var_58]
0x18000d3a9  lea     rdx, [rbp+57h+var_78]
0x18000d3ad  mov     r12, [rbp+57h+hMem]
0x18000d3b1  mov     rax, rcx
0x18000d3b4  sub     rax, r12
0x18000d3b7  cmp     rdi, rax
0x18000d3ba  jb      loc_18000DB02
0x18000d3c0  mov     rax, [rdx]
0x18000d3c3  lea     rdi, [rcx+8]
0x18000d3c7  mov     [rcx], rax
0x18000d3ca  mov     r8, rbx
0x18000d3cd  mov     [rbp+57h+var_58], rdi
0x18000d3d1  jmp     loc_18000D32A
0x18000d3d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3dd  test    byte ptr [rcx+1Ch], 2
0x18000d3e1  jnz     loc_18000D94E
0x18000d3e7  mov     eax, 6F8h
0x18000d3ec  add     rsp, 98h
0x18000d3f3  pop     r15
0x18000d3f5  pop     r14
0x18000d3f7  pop     rdi
0x18000d3f8  pop     rsi
0x18000d3f9  pop     rbx
0x18000d3fa  pop     rbp
0x18000d3fb  retn
0x18000d3fd  xor     r12d, r12d
0x18000d400  mov     ebx, 0FFFFFFFFh
0x18000d405  lock xadd cs:?dwExtObjListRefCount@@3JC, ebx; long volatile dwExtObjListRefCount
0x18000d40d  mov     r13, [rsp+0C0h+var_38]
0x18000d415  sub     ebx, 1
0x18000d418  jnz     short loc_18000D42D
0x18000d41a  lea     rcx, ?dwExtObjListRefCount@@3JC; long volatile dwExtObjListRefCount
0x18000d421  call    cs:__imp_RtlWakeAddressAll
0x18000d428  nop     dword ptr [rax+rax+00h]
0x18000d42d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d434  test    byte ptr [rcx+1Ch], 20h
0x18000d438  jnz     loc_18000DBA7
0x18000d43e  mov     rcx, [r15+20h]
0x18000d442  mov     eax, 422h
0x18000d447  test    r14d, r14d
0x18000d44a  cmovnz  r12d, eax
0x18000d44e  mov     eax, r12d
0x18000d451  mov     [rcx], rsi
0x18000d454  mov     r12, [rsp+0C0h+var_30]
0x18000d45c  add     rsp, 98h
0x18000d463  pop     r15
0x18000d465  pop     r14
0x18000d467  pop     rdi
0x18000d468  pop     rsi
0x18000d469  pop     rbx
0x18000d46a  pop     rbp
0x18000d46b  retn
0x18000d46d  mov     r10, cs:WPP_GLOBAL_Control
0x18000d474  mov     rbx, r12
0x18000d477  cmp     rbx, rdi
0x18000d47a  jz      loc_18000D520
0x18000d480  mov     r15d, [rbx]
0x18000d483  test    byte ptr [r10+1Ch], 2
0x18000d488  jnz     loc_18000D997
0x18000d48e  mov     rsi, cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA; EXT_OBJECT * ExtensibleObjects
0x18000d495  test    rsi, rsi
0x18000d498  jz      short loc_18000D4BB
0x18000d49a  nop     word ptr [rax+rax+00h]
0x18000d4a0  cmp     dword ptr [rsi+70h], 0
0x18000d4a4  ja      short loc_18000D4C1
0x18000d4a6  cmp     r15d, [rsi+174h]
0x18000d4ad  jnb     loc_18000D679
0x18000d4b3  mov     rsi, [rsi]
0x18000d4b6  test    rsi, rsi
0x18000d4b9  jnz     short loc_18000D4A0
0x18000d4bb  add     rbx, 8
0x18000d4bf  jmp     short loc_18000D477
0x18000d4c1  xor     r14d, r14d
0x18000d4c4  mov     ecx, [rsi+r14*4+74h]
0x18000d4c9  cmp     [rbx], ecx
0x18000d4cb  jz      short loc_18000D4D8
0x18000d4cd  inc     r14d
0x18000d4d0  cmp     r14d, [rsi+70h]
0x18000d4d4  jb      short loc_18000D4C4
0x18000d4d6  jmp     short loc_18000D4B3
0x18000d4d8  or      dword ptr [rbx+4], 1
0x18000d4dc  or      dword ptr [rsi+17Ch], 80000000h
0x18000d4e6  mov     r10, cs:WPP_GLOBAL_Control
0x18000d4ed  test    byte ptr [r10+1Ch], 2
0x18000d4f2  jz      short loc_18000D4CD
0x18000d4f4  cmp     byte ptr [r10+19h], 5
0x18000d4f9  jb      short loc_18000D4CD
0x18000d4fb  mov     r9, [rsi+188h]
0x18000d502  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18000d509  mov     rcx, [r10+10h]
0x18000d50d  mov     edx, 20h ; ' '
0x18000d512  call    WPP_SF_S
0x18000d517  mov     r10, cs:WPP_GLOBAL_Control
0x18000d51e  jmp     short loc_18000D4CD
0x18000d520  mov     rax, r12
0x18000d523  cmp     rax, rdi
0x18000d526  jnz     loc_18000D6D9
0x18000d52c  mov     r15, [rbp+57h+Size]
0x18000d530  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18000d534  jz      short loc_18000D54C
0x18000d536  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000d53d  mov     rcx, r12; hMem
0x18000d540  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d545  mov     r10, cs:WPP_GLOBAL_Control
0x18000d54c  mov     rsi, [rbp+57h+arg_18]
0x18000d550  mov     r12d, 0EAh
0x18000d556  mov     r14d, [rbp+57h+arg_10]
0x18000d55a  lea     r8, ?GLOBAL_STRING@@3QBGB; "Global"
0x18000d561  mov     rdi, cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA; EXT_OBJECT * ExtensibleObjects
0x18000d568  lea     rdx, ?COSTLY_STRING@@3QBGB; "Costly"
0x18000d56f  nop
0x18000d570  test    rdi, rdi
0x18000d573  jz      loc_18000D3FD
0x18000d579  cmp     r13d, 2
0x18000d57d  jnz     short loc_18000D5D5
0x18000d57f  test    r14d, r14d
0x18000d582  jnz     short loc_18000D596
0x18000d584  mov     eax, [rdi+17Ch]
0x18000d58a  and     eax, 80000010h
0x18000d58f  cmp     eax, 80000000h
0x18000d594  jz      short loc_18000D5A1
0x18000d596  cmp     qword ptr [rdi+58h], 0
0x18000d59b  jnz     loc_18000D638
0x18000d5a1  lea     rbx, [rdi+17Ch]
0x18000d5a8  mov     eax, [rbx]
0x18000d5aa  test    al, 10h
0x18000d5ac  jnz     short loc_18000D5BC
0x18000d5ae  cmp     r13d, 2
0x18000d5b2  jnz     loc_18000D81B
0x18000d5b8  test    eax, eax
0x18000d5ba  js      short loc_18000D5DC
0x18000d5bc  and     dword ptr [rbx], 7FFFFFFFh
0x18000d5c2  lea     r8, ?GLOBAL_STRING@@3QBGB; "Global"
0x18000d5c9  mov     r10, cs:WPP_GLOBAL_Control
0x18000d5d0  mov     rdi, [rdi]
0x18000d5d3  jmp     short loc_18000D570
0x18000d5d5  test    r14d, r14d
0x18000d5d8  jz      short loc_18000D5A1
0x18000d5da  jmp     short loc_18000D596
0x18000d5dc  mov     rcx, [r15+8]
0x18000d5e0  test    rcx, rcx
0x18000d5e3  jz      short loc_18000D5BC
0x18000d5e5  xor     eax, eax
0x18000d5e7  lea     rdx, [rbp+57h+arg_18]
0x18000d5eb  mov     [rsp+0C0h+var_90], rdx
0x18000d5f0  mov     r9, rsi
0x18000d5f3  mov     dword ptr [rbp+57h+arg_18], eax
0x18000d5f6  lea     rdx, [rbp+57h+arg_10]
0x18000d5fa  mov     [rbp+57h+arg_10], eax
0x18000d5fd  mov     r8d, r13d
0x18000d600  mov     eax, dword ptr [rbp+57h+var_68]
0x18000d603  mov     [rsp+0C0h+var_98], rdx
0x18000d608  sub     eax, esi
0x18000d60a  mov     rdx, rdi
0x18000d60d  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18000d611  call    QueryV1Provider
0x18000d616  cmp     eax, r12d
0x18000d619  jz      loc_18000D400
0x18000d61f  mov     eax, [rbp+57h+arg_10]
0x18000d622  lea     rdx, ?COSTLY_STRING@@3QBGB; "Costly"
0x18000d629  mov     rcx, [rbp+57h+var_70]
0x18000d62d  add     rsi, rax
0x18000d630  mov     eax, dword ptr [rbp+57h+arg_18]
0x18000d633  add     [rcx+1Ch], eax
0x18000d636  jmp     short loc_18000D5BC
0x18000d638  test    byte ptr [r10+1Ch], 2
0x18000d63d  jnz     loc_18000DB0B
0x18000d643  mov     rcx, rdi
0x18000d646  call    PerfpLockExtObject
0x18000d64b  test    eax, eax
0x18000d64d  jnz     loc_18000DB3C
0x18000d653  mov     edx, r14d; int
0x18000d656  mov     rcx, rdi; struct EXT_OBJECT *
0x18000d659  call    ?CloseExtObjectLibrary@@YAKPEAUEXT_OBJECT@@H@Z; CloseExtObjectLibrary(EXT_OBJECT *,int)
0x18000d65e  mov     rcx, rdi
0x18000d661  call    PerfpUnlockExtObject
0x18000d666  lea     rbx, [rdi+17Ch]
0x18000d66d  lea     rdx, ?COSTLY_STRING@@3QBGB; "Costly"
0x18000d674  jmp     loc_18000D5BC
0x18000d679  cmp     r15d, [rsi+178h]
0x18000d680  ja      loc_18000D4B3
0x18000d686  or      dword ptr [rbx+4], 1
0x18000d68a  or      dword ptr [rsi+17Ch], 80000000h
0x18000d694  mov     r10, cs:WPP_GLOBAL_Control
0x18000d69b  test    byte ptr [r10+1Ch], 2
0x18000d6a0  jz      loc_18000D4B3
0x18000d6a6  cmp     byte ptr [r10+19h], 5
0x18000d6ab  jb      loc_18000D4B3
0x18000d6b1  mov     r9, [rsi+188h]
0x18000d6b8  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18000d6bf  mov     rcx, [r10+10h]
0x18000d6c3  mov     edx, 21h ; '!'
0x18000d6c8  call    WPP_SF_S
0x18000d6cd  mov     r10, cs:WPP_GLOBAL_Control
0x18000d6d4  jmp     loc_18000D4B3
0x18000d6d9  test    byte ptr [rax+4], 1
0x18000d6dd  jz      short loc_18000D70D
0x18000d6df  add     rax, 8
0x18000d6e3  jmp     loc_18000D523
0x18000d6e8  mov     rax, [rbp+57h+var_78]
0x18000d6ec  mov     [rdi], rax
0x18000d6ef  add     rdi, 8
0x18000d6f3  mov     [rbp+57h+var_58], rdi
0x18000d6f7  mov     r8, rbx
0x18000d6fa  jmp     loc_18000D32A
0x18000d6ff  test    dx, dx
0x18000d702  jz      loc_18000D371
0x18000d708  jmp     loc_18000D35D
0x18000d70d  test    byte ptr [r10+1Ch], 2
0x18000d712  jnz     loc_18000DA1E
0x18000d718  cmp     word ptr [rbp+57h+arg_8], 0
0x18000d71d  jz      short loc_18000D728
0x18000d71f  mov     r15, [rbp+57h+Size]
  ... truncated ...
```
