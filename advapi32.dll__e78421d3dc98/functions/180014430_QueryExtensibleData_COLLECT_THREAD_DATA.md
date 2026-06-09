# QueryExtensibleData(COLLECT_THREAD_DATA *)

- ea: `0x180014430`
- end: `0x180014d97`
- name: `?QueryExtensibleData@@YAJPEAUCOLLECT_THREAD_DATA@@@Z`
- size: `2407`
- prototype: `__int64 __fastcall(struct COLLECT_THREAD_DATA *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callers

- `0x1800288a0`

## callees

- `0x180014430`
- `0x180014da0`
- `0x180014e2c`
- `0x180014e50`
- `0x18001585c`
- `0x1800158ac`
- `0x180015964`
- `0x180015c80`
- `0x180015ff0`
- `0x1800160c0`
- `0x18003b2bc`
- `0x18003b57c`
- `0x18003b5bc`
- `0x18003b748`
- `0x18003d070`
- `0x180057dfc`
- `0x180065042`

## import_xrefs

- `ntdll!RtlWakeAddressAll` at `0x180014610`
- `ntdll!RtlWakeAddressAll` at `0x180014610`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014932`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014932`
- `KERNEL32!LocalFree` at `0x18001496d`
- `KERNEL32!LocalFree` at `0x1800149e2`
- `KERNEL32!LocalFree` at `0x180014a6f`
- `KERNEL32!LocalFree` at `0x18001496d`
- `KERNEL32!LocalFree` at `0x1800149e2`
- `KERNEL32!LocalFree` at `0x180014a6f`

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
  unsigned int v14; // r12d
  _WORD *v15; // r8
  struct EXT_OBJ_LIST *v16; // rdi
  struct EXT_OBJ_LIST *v17; // r12
  int v18; // edx
  unsigned int v19; // ecx
  _WORD *v20; // rbx
  int v21; // r9d
  char *v22; // rdi
  struct EXT_OBJ_LIST *v23; // rcx
  char *v24; // rdx
  _QWORD *v25; // rcx
  __int64 result; // rax
  unsigned __int32 v27; // ebx
  struct EXT_OBJ_LIST *j; // rbx
  unsigned int v29; // r15d
  _DWORD *v30; // rsi
  __int64 v31; // r14
  struct EXT_OBJ_LIST *v32; // rax
  char *v33; // rsi
  _DWORD *i; // rdi
  _DWORD *v35; // rbx
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  const unsigned __int16 *v38; // rsi
  DWORD CurrentThreadId; // eax
  unsigned int v40; // ebx
  struct EXT_OBJ_LIST *k; // rax
  char *v42; // rbx
  _DWORD *v43; // rax
  __int64 v44; // rdx
  void *v45; // r9
  int V2Provider; // eax
  unsigned __int8 **v47; // [rsp+20h] [rbp-49h]
  HLOCAL Src; // [rsp+40h] [rbp-29h] BYREF
  __int64 v49; // [rsp+48h] [rbp-21h] BYREF
  _DWORD *v50; // [rsp+50h] [rbp-19h]
  __int64 v51; // [rsp+58h] [rbp-11h]
  HLOCAL hMem; // [rsp+60h] [rbp-9h] BYREF
  struct EXT_OBJ_LIST *v53; // [rsp+68h] [rbp-1h]
  struct EXT_OBJ_LIST *v54; // [rsp+70h] [rbp+7h]
  size_t Size; // [rsp+D0h] [rbp+67h] BYREF
  unsigned int v56; // [rsp+D8h] [rbp+6Fh] BYREF
  int v57; // [rsp+E0h] [rbp+77h] BYREF
  void *v58; // [rsp+E8h] [rbp+7Fh] BYREF

  Size = (size_t)a1;
  v1 = (unsigned int *)*((_QWORD *)a1 + 3);
  v2 = a1;
  v3 = (_DWORD *)*((_QWORD *)a1 + 2);
  v4 = *(unsigned __int16 *)a1;
  v50 = v3;
  if ( v1 )
    v5 = *v1;
  else
    v5 = 0;
  v6 = (void *)**((_QWORD **)a1 + 4);
  v58 = v6;
  Src = v6;
  IsDisabled = PerflibciIsDisabled();
  if ( ((unsigned __int8)v6 & 7) != 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 1784;
    v44 = 28;
    v45 = v6;
    goto LABEL_124;
  }
  if ( ((unsigned __int8)v3 & 7) != 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 1784;
    v44 = 29;
    v45 = v3;
LABEL_124:
    WPP_SF_q(v25[2], v44, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v45);
    return 1784;
  }
  v8 = *((_WORD *)v2 + 1);
  v9 = (__int64)v3 + v5;
  v10 = IsDisabled;
  v11 = v4;
  v57 = IsDisabled;
  v51 = v9;
  LOWORD(v56) = v8;
  if ( IsDisabled && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
  v12 = (unsigned int)_InterlockedIncrement(&dwExtObjListRefCount);
  v13 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v12);
    v13 = WPP_GLOBAL_Control;
  }
  v14 = 234;
  if ( v4 != 2 || v10 )
  {
    if ( v8 || ((v4 - 1) & 0xFFFFFFF7) != 0 )
    {
      v33 = (char *)v58;
    }
    else
    {
      V2Provider = QueryV2Provider(L"Global", 0, 0, (__int64)&Src, (__int64)(v50 + 7));
      v33 = (char *)Src;
      if ( V2Provider == 234 )
        goto LABEL_28;
      v13 = WPP_GLOBAL_Control;
    }
LABEL_55:
    for ( i = ExtensibleObjects; ; i = *(_DWORD **)i )
    {
      if ( !i )
      {
        v14 = 0;
        goto LABEL_28;
      }
      if ( v11 == 2 )
      {
        if ( !v10 && (i[95] & 0x80000010) == 0x80000000 )
          goto LABEL_61;
      }
      else if ( !v10 )
      {
        goto LABEL_61;
      }
      if ( *((_QWORD *)i + 11) )
      {
        if ( (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 4u )
          WPP_SF_Sd(v13[2], 38, (unsigned int)WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, *((_QWORD *)i + 49), v11);
        if ( (unsigned int)PerfpLockExtObject(i) )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              39,
              WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
              *((_QWORD *)i + 49));
        }
        else
        {
          CloseExtObjectLibrary((struct EXT_OBJECT *)i, v10);
          PerfpUnlockExtObject(i);
        }
        v35 = i + 95;
        goto LABEL_64;
      }
LABEL_61:
      v35 = i + 95;
      v36 = i[95];
      if ( (v36 & 0x10) != 0 )
        goto LABEL_64;
      switch ( v11 )
      {
        case 2u:
          if ( v36 >= 0 )
            goto LABEL_64;
          v37 = (const unsigned __int16 *)*((_QWORD *)v2 + 1);
          if ( !v37 )
            goto LABEL_64;
          break;
        case 1u:
          v37 = L"Global";
          break;
        case 3u:
          v37 = L"Foreigh";
          break;
        case 4u:
          v37 = L"Costly";
          break;
        case 9u:
          v37 = L"MetadataGlobal";
          if ( (v36 & 0x80u) == 0 )
            v37 = L"Global";
          break;
        case 0xAu:
          v37 = L"MetadataCostly";
          if ( (v36 & 0x80u) == 0 )
            v37 = L"Costly";
          break;
        default:
          goto LABEL_64;
      }
      LODWORD(v58) = 0;
      v57 = 0;
      LODWORD(v47) = v51 - (_DWORD)v33;
      if ( (unsigned int)QueryV1Provider((__int64)v37, (__int64)i, v11, v33, v47, &v57, &v58) == 234 )
        goto LABEL_28;
      v33 += (unsigned int)v57;
      v50[7] += (_DWORD)v58;
LABEL_64:
      *v35 &= ~0x80000000;
      v13 = WPP_GLOBAL_Control;
    }
  }
  utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>(&hMem);
  v16 = v53;
  v17 = (struct EXT_OBJ_LIST *)hMem;
LABEL_10:
  while ( 1 )
  {
    LOWORD(v18) = *v15;
    if ( !*v15 )
      break;
    v19 = 0;
    v20 = v15;
    v21 = 0;
    while ( 1 )
    {
      if ( (_WORD)v18 != 32 )
      {
        v18 = (unsigned __int16)*v20;
        if ( (_WORD)v18 )
        {
          if ( (unsigned __int16)(v18 - 48) <= 9u )
          {
            v21 = 1;
            v19 = v18 + 2 * (5 * v19 - 24);
          }
          else
          {
            v21 = 0;
          }
          goto LABEL_16;
        }
      }
      if ( v21 || !(_WORD)v18 )
        break;
LABEL_16:
      if ( !++v20 )
        goto LABEL_10;
      LOWORD(v18) = *v20;
    }
    if ( v19 )
    {
      v49 = v19;
      if ( v16 != v54 )
      {
        *(_QWORD *)v16 = v49;
        v16 = (struct EXT_OBJ_LIST *)((char *)v16 + 8);
        v53 = v16;
        goto LABEL_81;
      }
      v22 = (char *)((char *)&v49 - (char *)v17);
      if ( !(unsigned __int8)utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::_Grow(&hMem) )
      {
        v14 = 14;
        if ( hMem != (HLOCAL)-1LL )
          operator delete(hMem);
        goto LABEL_141;
      }
      v23 = v53;
      v24 = (char *)&v49;
      v17 = (struct EXT_OBJ_LIST *)hMem;
      if ( (unsigned __int64)v22 < v53 - (struct EXT_OBJ_LIST *)hMem )
        v24 = &v22[(_QWORD)hMem];
      v16 = (struct EXT_OBJ_LIST *)((char *)v53 + 8);
      *(_QWORD *)v53 = *(_QWORD *)v24;
      v15 = v20;
      v53 = (struct EXT_OBJ_LIST *)((char *)v23 + 8);
    }
    else
    {
LABEL_81:
      v15 = v20;
    }
  }
  v13 = WPP_GLOBAL_Control;
  for ( j = v17; j != v16; j = (struct EXT_OBJ_LIST *)((char *)j + 8) )
  {
    v29 = *(_DWORD *)j;
    if ( (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 5u )
    {
      WPP_SF_d(v13[2], 31, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v29);
      v13 = WPP_GLOBAL_Control;
    }
    v30 = ExtensibleObjects;
    if ( ExtensibleObjects )
    {
      do
      {
        if ( v30[28] )
        {
          v31 = 0;
          do
          {
            if ( *(_DWORD *)j == v30[v31 + 29] )
            {
              *((_DWORD *)j + 1) |= 1u;
              v30[95] |= 0x80000000;
              v13 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
                  *((_QWORD *)v30 + 49));
                v13 = WPP_GLOBAL_Control;
              }
            }
            v31 = (unsigned int)(v31 + 1);
          }
          while ( (unsigned int)v31 < v30[28] );
        }
        else if ( v29 >= v30[93] && v29 <= v30[94] )
        {
          *((_DWORD *)j + 1) |= 1u;
          v30[95] |= 0x80000000;
          v13 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
              *((_QWORD *)v30 + 49));
            v13 = WPP_GLOBAL_Control;
          }
        }
        v30 = *(_DWORD **)v30;
      }
      while ( v30 );
    }
  }
  v32 = v17;
  while ( 2 )
  {
    if ( v32 == v16 )
    {
      v2 = (struct COLLECT_THREAD_DATA *)Size;
      goto LABEL_52;
    }
    if ( (*((_BYTE *)v32 + 4) & 1) != 0 )
    {
      v32 = (struct EXT_OBJ_LIST *)((char *)v32 + 8);
      continue;
    }
    break;
  }
  if ( (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 5u )
  {
    WPP_SF_(v13[2], 34, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
    v13 = WPP_GLOBAL_Control;
  }
  if ( (_WORD)v56 )
  {
    v2 = (struct COLLECT_THREAD_DATA *)Size;
    goto LABEL_144;
  }
  if ( (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 4u )
    WPP_SF_(v13[2], 35, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
  v2 = (struct COLLECT_THREAD_DATA *)Size;
  Src = 0;
  LODWORD(Size) = 0;
  v56 = 0;
  v38 = (const unsigned __int16 *)*((_QWORD *)v2 + 1);
  CurrentThreadId = GetCurrentThreadId();
  v40 = PerflibciQueryV2Provider(
          CurrentThreadId,
          v38,
          v17,
          (v16 - v17) >> 3,
          (unsigned __int8 **)&Src,
          (unsigned int *)&Size,
          &v56);
  if ( v40 || !(_DWORD)Size )
  {
    LocalFree(Src);
    if ( v40 == 234 )
      goto LABEL_113;
LABEL_90:
    for ( k = v17; ; k = (struct EXT_OBJ_LIST *)((char *)k + 8) )
    {
      if ( k == v16 )
        goto LABEL_92;
      if ( (*((_BYTE *)k + 4) & 1) == 0 )
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
LABEL_144:
      if ( (*((_BYTE *)v13 + 28) & 2) != 0 && *((_BYTE *)v13 + 25) >= 3u )
      {
        WPP_SF_(v13[2], 37, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
        v13 = WPP_GLOBAL_Control;
      }
    }
    v43 = ExtensibleObjects;
    if ( ExtensibleObjects )
    {
      do
      {
        if ( !v43[28] )
          v43[95] |= 0x80000000;
        v43 = *(_DWORD **)v43;
      }
      while ( v43 );
LABEL_92:
      v13 = WPP_GLOBAL_Control;
    }
LABEL_52:
    if ( v17 != (struct EXT_OBJ_LIST *)-1LL )
    {
      operator delete(v17);
      v13 = WPP_GLOBAL_Control;
    }
    v33 = (char *)v58;
    v14 = 234;
    v10 = v57;
    goto LABEL_55;
  }
  v42 = (char *)v58;
  if ( (int)v51 - (int)v58 >= (unsigned int)Size )
  {
    memcpy_0(v58, Src, (unsigned int)Size);
    v58 = &v42[(unsigned int)Size];
    v50[7] += v56;
    LocalFree(Src);
    goto LABEL_90;
  }
  LocalFree(Src);
LABEL_113:
  if ( v17 != (struct EXT_OBJ_LIST *)-1LL )
    operator delete(v17);
  v10 = v57;
  v14 = 234;
LABEL_141:
  v33 = (char *)v58;
LABEL_28:
  v27 = _InterlockedDecrement(&dwExtObjListRefCount);
  if ( !v27 )
    RtlWakeAddressAll(&dwExtObjListRefCount);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v27);
  if ( v10 )
    v14 = 1058;
  result = v14;
  **((_QWORD **)v2 + 4) = v33;
  return result;
}

```

## disassembly

```asm
0x180014430  mov     [rsp-8+Size], rcx
0x180014435  push    rbp
0x180014436  push    rbx
0x180014437  push    rsi
0x180014438  push    rdi
0x180014439  push    r14
0x18001443b  push    r15
0x18001443d  lea     rbp, [rsp-2Fh]
0x180014442  sub     rsp, 98h
0x180014449  mov     rax, [rcx+18h]
0x18001444d  mov     r15, rcx
0x180014450  mov     r14, [rcx+10h]
0x180014454  movzx   edi, word ptr [rcx]
0x180014457  mov     [rbp+57h+var_70], r14
0x18001445b  test    rax, rax
0x18001445e  jz      loc_180014A64
0x180014464  mov     ebx, [rax]
0x180014466  mov     rax, [rcx+20h]
0x18001446a  mov     rsi, [rax]
0x18001446d  mov     [rbp+57h+arg_18], rsi
0x180014471  mov     [rbp+57h+Src], rsi
0x180014475  call    ?PerflibciIsDisabled@@YAEXZ; PerflibciIsDisabled(void)
0x18001447a  test    sil, 7
0x18001447e  jnz     loc_1800145C6
0x180014484  test    r14b, 7
0x180014488  jnz     loc_180014ADF
0x18001448e  movzx   esi, word ptr [r15+2]
0x180014493  add     rbx, r14
0x180014496  movzx   r14d, al
0x18001449a  mov     [rsp+0C0h+var_30], r12
0x1800144a2  mov     [rsp+0C0h+var_38], r13
0x1800144aa  mov     r13d, edi
0x1800144ad  mov     [rbp+57h+arg_10], r14d
0x1800144b1  mov     [rbp+57h+var_68], rbx
0x1800144b5  mov     word ptr [rbp+57h+arg_8], si
0x1800144b9  test    al, al
0x1800144bb  jnz     loc_180014B2B
0x1800144c1  mov     r9d, 1
0x1800144c7  lock xadd cs:?dwExtObjListRefCount@@3JC, r9d; long volatile dwExtObjListRefCount
0x1800144d0  inc     r9d
0x1800144d3  mov     r10, cs:WPP_GLOBAL_Control
0x1800144da  test    byte ptr [r10+1Ch], 20h
0x1800144df  jnz     loc_180014AAB
0x1800144e5  lea     r8, ?GLOBAL_STRING@@3QBGB; "Global"
0x1800144ec  mov     r12d, 0EAh
0x1800144f2  cmp     r13d, 2
0x1800144f6  jnz     loc_180014A99
0x1800144fc  test    r14d, r14d
0x1800144ff  jnz     loc_180014A99
0x180014505  mov     r8, [r15+8]
0x180014509  lea     rcx, [rbp+57h+hMem]
0x18001450d  call    ??0?$vector@UEXT_OBJ_LIST@@V?$allocator@UEXT_OBJ_LIST@@@utl@@@utl@@QEAA@XZ; utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>(void)
0x180014512  mov     rdi, [rbp+57h+var_58]
0x180014516  mov     r12, [rbp+57h+hMem]
0x18001451a  movzx   edx, word ptr [r8]
0x18001451e  test    dx, dx
0x180014521  jz      loc_180014655
0x180014527  xor     ecx, ecx
0x180014529  mov     rbx, r8
0x18001452c  xor     r9d, r9d
0x18001452f  cmp     dx, 20h ; ' '
0x180014533  jz      short loc_180014558
0x180014535  movzx   edx, word ptr [rbx]
0x180014538  test    dx, dx
0x18001453b  jz      short loc_180014558
0x18001453d  lea     eax, [rdx-30h]
0x180014540  cmp     ax, 9
0x180014544  jbe     loc_180014CB7
0x18001454a  xor     r9d, r9d
0x18001454d  add     rbx, 2
0x180014551  jz      short loc_18001451A
0x180014553  movzx   edx, word ptr [rbx]
0x180014556  jmp     short loc_18001452F
0x180014558  test    r9d, r9d
0x18001455b  jz      loc_1800148E0
0x180014561  test    ecx, ecx
0x180014563  jz      loc_1800148D8
0x180014569  mov     dword ptr [rbp+57h+var_78], ecx
0x18001456c  mov     dword ptr [rbp+57h+var_78+4], 0
0x180014573  cmp     rdi, [rbp+57h+var_50]
0x180014577  jnz     loc_1800148C9
0x18001457d  lea     rdi, [rbp+57h+var_78]
0x180014581  lea     rcx, [rbp+57h+hMem]
0x180014585  sub     rdi, r12
0x180014588  call    ?_Grow@?$vector@UEXT_OBJ_LIST@@V?$allocator@UEXT_OBJ_LIST@@@utl@@@utl@@AEAA_NXZ; utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::_Grow(void)
0x18001458d  test    al, al
0x18001458f  jz      loc_180014C38
0x180014595  mov     rcx, [rbp+57h+var_58]
0x180014599  lea     rdx, [rbp+57h+var_78]
0x18001459d  mov     r12, [rbp+57h+hMem]
0x1800145a1  mov     rax, rcx
0x1800145a4  sub     rax, r12
0x1800145a7  cmp     rdi, rax
0x1800145aa  jb      loc_180014CCB
0x1800145b0  mov     rax, [rdx]
0x1800145b3  lea     rdi, [rcx+8]
0x1800145b7  mov     [rcx], rax
0x1800145ba  mov     r8, rbx
0x1800145bd  mov     [rbp+57h+var_58], rdi
0x1800145c1  jmp     loc_18001451A
0x1800145c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145cd  test    byte ptr [rcx+1Ch], 2
0x1800145d1  jnz     loc_180014B17
0x1800145d7  mov     eax, 6F8h
0x1800145dc  add     rsp, 98h
0x1800145e3  pop     r15
0x1800145e5  pop     r14
0x1800145e7  pop     rdi
0x1800145e8  pop     rsi
0x1800145e9  pop     rbx
0x1800145ea  pop     rbp
0x1800145eb  retn
0x1800145ec  xor     r12d, r12d
0x1800145ef  mov     ebx, 0FFFFFFFFh
0x1800145f4  lock xadd cs:?dwExtObjListRefCount@@3JC, ebx; long volatile dwExtObjListRefCount
0x1800145fc  mov     r13, [rsp+0C0h+var_38]
0x180014604  sub     ebx, 1
0x180014607  jnz     short loc_180014616
0x180014609  lea     rcx, ?dwExtObjListRefCount@@3JC; long volatile dwExtObjListRefCount
0x180014610  call    cs:__imp_RtlWakeAddressAll
0x180014616  mov     rcx, cs:WPP_GLOBAL_Control
0x18001461d  test    byte ptr [rcx+1Ch], 20h
0x180014621  jnz     loc_180014D70
0x180014627  mov     rcx, [r15+20h]
0x18001462b  mov     eax, 422h
0x180014630  test    r14d, r14d
0x180014633  cmovnz  r12d, eax
0x180014637  mov     eax, r12d
0x18001463a  mov     [rcx], rsi
0x18001463d  mov     r12, [rsp+0C0h+var_30]
0x180014645  add     rsp, 98h
0x18001464c  pop     r15
0x18001464e  pop     r14
0x180014650  pop     rdi
0x180014651  pop     rsi
0x180014652  pop     rbx
0x180014653  pop     rbp
0x180014654  retn
0x180014655  mov     r10, cs:WPP_GLOBAL_Control
0x18001465c  mov     rbx, r12
0x18001465f  cmp     rbx, rdi
0x180014662  jz      loc_180014702
0x180014668  mov     r15d, [rbx]
0x18001466b  test    byte ptr [r10+1Ch], 2
0x180014670  jnz     loc_180014B60
0x180014676  mov     rsi, cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA; EXT_OBJECT * ExtensibleObjects
0x18001467d  test    rsi, rsi
0x180014680  jz      short loc_18001469D
0x180014682  cmp     dword ptr [rsi+70h], 0
0x180014686  ja      short loc_1800146A3
0x180014688  cmp     r15d, [rsi+174h]
0x18001468f  jnb     loc_18001485A
0x180014695  mov     rsi, [rsi]
0x180014698  test    rsi, rsi
0x18001469b  jnz     short loc_180014682
0x18001469d  add     rbx, 8
0x1800146a1  jmp     short loc_18001465F
0x1800146a3  xor     r14d, r14d
0x1800146a6  mov     ecx, [rsi+r14*4+74h]
0x1800146ab  cmp     [rbx], ecx
0x1800146ad  jz      short loc_1800146BA
0x1800146af  inc     r14d
0x1800146b2  cmp     r14d, [rsi+70h]
0x1800146b6  jb      short loc_1800146A6
0x1800146b8  jmp     short loc_180014695
0x1800146ba  or      dword ptr [rbx+4], 1
0x1800146be  or      dword ptr [rsi+17Ch], 80000000h
0x1800146c8  mov     r10, cs:WPP_GLOBAL_Control
0x1800146cf  test    byte ptr [r10+1Ch], 2
0x1800146d4  jz      short loc_1800146AF
0x1800146d6  cmp     byte ptr [r10+19h], 5
0x1800146db  jb      short loc_1800146AF
0x1800146dd  mov     r9, [rsi+188h]
0x1800146e4  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x1800146eb  mov     rcx, [r10+10h]
0x1800146ef  mov     edx, 20h ; ' '
0x1800146f4  call    WPP_SF_S
0x1800146f9  mov     r10, cs:WPP_GLOBAL_Control
0x180014700  jmp     short loc_1800146AF
0x180014702  mov     rax, r12
0x180014705  cmp     rax, rdi
0x180014708  jnz     loc_1800148BA
0x18001470e  mov     r15, [rbp+57h+Size]
0x180014712  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180014716  jz      short loc_18001472E
0x180014718  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001471f  mov     rcx, r12; hMem
0x180014722  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014727  mov     r10, cs:WPP_GLOBAL_Control
0x18001472e  mov     rsi, [rbp+57h+arg_18]
0x180014732  mov     r12d, 0EAh
0x180014738  mov     r14d, [rbp+57h+arg_10]
0x18001473c  lea     r8, ?GLOBAL_STRING@@3QBGB; "Global"
0x180014743  mov     rdi, cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA; EXT_OBJECT * ExtensibleObjects
0x18001474a  lea     rdx, ?COSTLY_STRING@@3QBGB; "Costly"
0x180014751  test    rdi, rdi
0x180014754  jz      loc_1800145EC
0x18001475a  cmp     r13d, 2
0x18001475e  jnz     short loc_1800147B6
0x180014760  test    r14d, r14d
0x180014763  jnz     short loc_180014777
0x180014765  mov     eax, [rdi+17Ch]
0x18001476b  and     eax, 80000010h
0x180014770  cmp     eax, 80000000h
0x180014775  jz      short loc_180014782
0x180014777  cmp     qword ptr [rdi+58h], 0
0x18001477c  jnz     loc_180014819
0x180014782  lea     rbx, [rdi+17Ch]
0x180014789  mov     eax, [rbx]
0x18001478b  test    al, 10h
0x18001478d  jnz     short loc_18001479D
0x18001478f  cmp     r13d, 2
0x180014793  jnz     loc_1800149EA
0x180014799  test    eax, eax
0x18001479b  js      short loc_1800147BD
0x18001479d  and     dword ptr [rbx], 7FFFFFFFh
0x1800147a3  lea     r8, ?GLOBAL_STRING@@3QBGB; "Global"
0x1800147aa  mov     r10, cs:WPP_GLOBAL_Control
0x1800147b1  mov     rdi, [rdi]
0x1800147b4  jmp     short loc_180014751
0x1800147b6  test    r14d, r14d
0x1800147b9  jz      short loc_180014782
0x1800147bb  jmp     short loc_180014777
0x1800147bd  mov     rcx, [r15+8]
0x1800147c1  test    rcx, rcx
0x1800147c4  jz      short loc_18001479D
0x1800147c6  xor     eax, eax
0x1800147c8  lea     rdx, [rbp+57h+arg_18]
0x1800147cc  mov     [rsp+0C0h+var_90], rdx
0x1800147d1  mov     r9, rsi
0x1800147d4  mov     dword ptr [rbp+57h+arg_18], eax
0x1800147d7  lea     rdx, [rbp+57h+arg_10]
0x1800147db  mov     [rbp+57h+arg_10], eax
0x1800147de  mov     r8d, r13d
0x1800147e1  mov     eax, dword ptr [rbp+57h+var_68]
0x1800147e4  mov     [rsp+0C0h+var_98], rdx
0x1800147e9  sub     eax, esi
0x1800147eb  mov     rdx, rdi
0x1800147ee  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800147f2  call    QueryV1Provider
0x1800147f7  cmp     eax, r12d
0x1800147fa  jz      loc_1800145EF
0x180014800  mov     eax, [rbp+57h+arg_10]
0x180014803  lea     rdx, ?COSTLY_STRING@@3QBGB; "Costly"
0x18001480a  mov     rcx, [rbp+57h+var_70]
0x18001480e  add     rsi, rax
0x180014811  mov     eax, dword ptr [rbp+57h+arg_18]
0x180014814  add     [rcx+1Ch], eax
0x180014817  jmp     short loc_18001479D
0x180014819  test    byte ptr [r10+1Ch], 2
0x18001481e  jnz     loc_180014CD4
0x180014824  mov     rcx, rdi
0x180014827  call    PerfpLockExtObject
0x18001482c  test    eax, eax
0x18001482e  jnz     loc_180014D05
0x180014834  mov     edx, r14d; int
0x180014837  mov     rcx, rdi; struct EXT_OBJECT *
0x18001483a  call    ?CloseExtObjectLibrary@@YAKPEAUEXT_OBJECT@@H@Z; CloseExtObjectLibrary(EXT_OBJECT *,int)
0x18001483f  mov     rcx, rdi
0x180014842  call    PerfpUnlockExtObject
0x180014847  lea     rbx, [rdi+17Ch]
0x18001484e  lea     rdx, ?COSTLY_STRING@@3QBGB; "Costly"
0x180014855  jmp     loc_18001479D
0x18001485a  cmp     r15d, [rsi+178h]
0x180014861  ja      loc_180014695
0x180014867  or      dword ptr [rbx+4], 1
0x18001486b  or      dword ptr [rsi+17Ch], 80000000h
0x180014875  mov     r10, cs:WPP_GLOBAL_Control
0x18001487c  test    byte ptr [r10+1Ch], 2
0x180014881  jz      loc_180014695
0x180014887  cmp     byte ptr [r10+19h], 5
0x18001488c  jb      loc_180014695
0x180014892  mov     r9, [rsi+188h]
0x180014899  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x1800148a0  mov     rcx, [r10+10h]
0x1800148a4  mov     edx, 21h ; '!'
0x1800148a9  call    WPP_SF_S
0x1800148ae  mov     r10, cs:WPP_GLOBAL_Control
0x1800148b5  jmp     loc_180014695
0x1800148ba  test    byte ptr [rax+4], 1
0x1800148be  jz      short loc_1800148EE
0x1800148c0  add     rax, 8
0x1800148c4  jmp     loc_180014705
0x1800148c9  mov     rax, [rbp+57h+var_78]
0x1800148cd  mov     [rdi], rax
0x1800148d0  add     rdi, 8
0x1800148d4  mov     [rbp+57h+var_58], rdi
0x1800148d8  mov     r8, rbx
0x1800148db  jmp     loc_18001451A
0x1800148e0  test    dx, dx
0x1800148e3  jz      loc_180014561
0x1800148e9  jmp     loc_18001454D
0x1800148ee  test    byte ptr [r10+1Ch], 2
0x1800148f3  jnz     loc_180014BE7
0x1800148f9  cmp     word ptr [rbp+57h+arg_8], 0
0x1800148fe  jz      short loc_180014909
0x180014900  mov     r15, [rbp+57h+Size]
0x180014904  jmp     loc_180014C80
0x180014909  test    byte ptr [r10+1Ch], 2
0x18001490e  jnz     loc_180014C13
  ... truncated ...
```
