# NotificationHandler::RuntimeClassInitialize(ushort const *,ushort const *,ushort const *,INotificationHandlerSettings *,IWNSChannelDetails *,IStream *,unsigned __int64,ushort const *,ushort const *)

- ea: `0x180010b90`
- end: `0x180011610`
- name: `?RuntimeClassInitialize@NotificationHandler@@QEAAJPEBG00PEAUINotificationHandlerSettings@@PEAUIWNSChannelDetails@@PEAUIStream@@_K00@Z`
- size: `2688`
- prototype: `__int64 __fastcall(NotificationHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct INotificationHandlerSettings *, struct IWNSChannelDetails *, struct IStream *, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e0c4`
- `0x18000e620`
- `0x18004e124`
- `0x18004f9b8`
- `0x1800a39cc`
- `0x1800e1b44`
- `0x1800f273c`

## callees

- `0x18000e090`
- `0x18000f9d4`
- `0x180010b90`
- `0x180011618`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010e7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010f8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011014`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001109d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800111ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010e7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010f8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011014`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001109d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800111ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001116f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001129a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800112f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001137b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800114a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001116f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001129a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800112f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001137b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800114a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NotificationHandler::RuntimeClassInitialize(
        NotificationHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct INotificationHandlerSettings *a5,
        struct IWNSChannelDetails *a6,
        struct IStream *a7,
        void (__stdcall *a8)(GUID connectionId, void *pContextData),
        const unsigned __int16 *a9,
        const unsigned __int16 *a10)
{
  const unsigned __int16 *v12; // rbx
  NotificationHandler *v13; // rdi
  NotificationHandler *v14; // r13
  unsigned __int64 v15; // rbp
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rcx
  int v18; // r12d
  int v20; // ebp
  NotificationHandler v21; // rcx
  NotificationHandler v22; // rcx
  NotificationHandler v23; // rcx
  NotificationHandler *v24; // r12
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // rbx
  unsigned __int64 v27; // rcx
  NotificationHandler *v28; // r14
  unsigned __int64 v29; // r12
  unsigned __int64 v30; // rdi
  unsigned __int64 v31; // rbx
  unsigned __int64 v32; // rcx
  int v33; // ebp
  NotificationHandler *v34; // r15
  const unsigned __int16 *v35; // rbx
  unsigned __int64 v36; // rsi
  unsigned __int64 v37; // rdi
  unsigned __int64 v38; // rcx
  int v39; // ebp
  void (__stdcall *v40)(GUID, void *); // rax
  unsigned __int16 *v41; // rdx
  unsigned __int64 v42; // rcx
  unsigned __int16 v43; // ax
  unsigned __int16 *v44; // rax
  NotificationHandler *v45; // r14
  const unsigned __int16 *v46; // rbx
  unsigned __int64 v47; // rdi
  unsigned __int64 v48; // r8
  int v49; // ebp
  void (__stdcall *v50)(GUID, void *); // rax
  _WORD *v51; // rdx
  unsigned __int64 v52; // rcx
  __int16 v53; // ax
  _WORD *v54; // rax
  void (__stdcall *v55)(GUID, void *); // rax
  _WORD *v56; // rdx
  unsigned __int64 v57; // rcx
  __int16 v58; // ax
  _WORD *v59; // rax
  void (__stdcall *v60)(GUID, void *); // rax
  unsigned __int16 *v61; // rdx
  unsigned __int64 v62; // rcx
  unsigned __int16 v63; // ax
  unsigned __int16 *v64; // rax
  unsigned __int64 v65; // rsi
  void (__stdcall *v66)(GUID, void *); // rax
  __int64 v67; // rcx
  void (__stdcall *v68)(GUID, void *); // rax
  int v69; // ecx
  unsigned __int16 *v70; // rdx
  unsigned __int64 v71; // rax
  unsigned __int16 v72; // cx
  unsigned __int16 *v73; // rax
  unsigned __int64 v74; // rsi
  void (__stdcall *v75)(GUID, void *); // rax
  unsigned __int64 v76; // rsi
  void (__stdcall *v77)(GUID, void *); // rax
  unsigned __int64 v78; // r14
  void (__stdcall *v79)(GUID, void *); // rax
  unsigned __int64 v80; // rsi
  void (__stdcall *v81)(GUID, void *); // rax
  int v82; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v12 = a2;
  v13 = this;
  v14 = this + 6;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(this + 6);
    goto LABEL_12;
  }
  v15 = -1;
  do
    ++v15;
  while ( a2[v15] );
  v16 = v15 + 1;
  if ( v15 + 1 < v15 )
    goto LABEL_8;
  v17 = (unsigned __int64)this[8];
  if ( v17 == -1 )
  {
    v67 = (__int64)v14[1];
    if ( v67 == -1 )
    {
      if ( *v14 )
      {
        v67 = -1;
        do
          ++v67;
        while ( *((_WORD *)*v14 + v67) );
      }
      else
      {
        v67 = 0;
      }
      v14[1] = (NotificationHandler)v67;
    }
    v17 = v67 + 1;
    if ( !*v14 )
      v17 = 0;
    v14[2] = (NotificationHandler)v17;
  }
  if ( v17 )
  {
    v18 = 0;
    if ( v16 > v17 )
    {
      v65 = 2 * v17;
      if ( !is_mul_ok(v17, 2u) )
        goto LABEL_8;
      if ( v17 > 0x800 )
        v65 = v17 + 2048;
      if ( v16 > v65 )
        v65 = v15 + 1;
      v66 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(*v14, 2 * v65);
      if ( !v66 )
      {
        v18 = -2147024882;
        goto LABEL_10;
      }
      v14[2] = (NotificationHandler)v65;
      *v14 = v66;
    }
  }
  else
  {
    if ( !is_mul_ok(v16, 2u) )
    {
LABEL_8:
      v18 = -2147024362;
      goto LABEL_9;
    }
    v40 = (void (__stdcall *)(GUID, void *))CoTaskMemAlloc(2 * v16);
    if ( v40 )
    {
      v18 = 0;
      v14[2] = (NotificationHandler)v16;
      *v14 = v40;
      *(_WORD *)v40 = 0;
    }
    else
    {
      v18 = -2147024882;
    }
    if ( v18 < 0 )
      goto LABEL_10;
  }
  if ( v15 != -1 )
  {
    v41 = (unsigned __int16 *)*v14;
    if ( v16 > 0x7FFFFFFF )
    {
      *v41 = 0;
    }
    else
    {
      if ( v15 > 0x7FFFFFFE )
      {
        *v41 = 0;
        v14[1] = (NotificationHandler)v15;
        goto LABEL_9;
      }
      v42 = v15;
      do
      {
        if ( !v42 )
          break;
        v43 = *v12;
        if ( !*v12 )
          break;
        ++v12;
        *v41++ = v43;
        --v42;
        --v16;
      }
      while ( v16 );
      v44 = v41 - 1;
      if ( v16 )
        v44 = v41;
      *v44 = 0;
    }
  }
  v14[1] = (NotificationHandler)v15;
LABEL_9:
  if ( v18 < 0 )
  {
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
      (const char *)(unsigned int)v18,
      v82);
    return (unsigned int)v18;
  }
  v13 = this;
LABEL_12:
  v20 = -2147024882;
  if ( (char *)v13[9] != (char *)a5 )
  {
    if ( a5 )
      (*(void (__fastcall **)(struct INotificationHandlerSettings *))(*(_QWORD *)a5 + 8LL))(a5);
    v21 = v13[9];
    v13[9] = (NotificationHandler)a5;
    if ( v21 )
      (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v21 + 16LL))(v21);
  }
  if ( (char *)v13[10] != (char *)a6 )
  {
    if ( a6 )
      (*(void (__fastcall **)(struct IWNSChannelDetails *))(*(_QWORD *)a6 + 8LL))(a6);
    v22 = v13[10];
    v13[10] = (NotificationHandler)a6;
    if ( v22 )
      (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( (char *)v13[11] != (char *)a7 )
  {
    if ( a7 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)a7 + 8LL))(a7);
    v23 = v13[11];
    v13[11] = (NotificationHandler)a7;
    if ( v23 )
      (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v13[21] = a8;
  v24 = v13 + 12;
  if ( a3 )
  {
    v25 = -1;
    do
      ++v25;
    while ( a3[v25] );
    v26 = v25 + 1;
    if ( v25 + 1 < v25 )
      goto LABEL_34;
    v27 = (unsigned __int64)v24[2];
    if ( v27 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v24);
      if ( *v24 )
        v27 = (unsigned __int64)v24[1] + 1;
      else
        v27 = 0;
      v24[2] = (NotificationHandler)v27;
    }
    if ( v27 )
    {
      v20 = 0;
      if ( v26 > v27 )
      {
        v74 = 2 * v27;
        if ( !is_mul_ok(v27, 2u) )
          goto LABEL_34;
        if ( v27 > 0x800 )
          v74 = v27 + 2048;
        if ( v26 > v74 )
          v74 = v25 + 1;
        v75 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(*v24, 2 * v74);
        if ( !v75 )
        {
          v20 = -2147024882;
          goto LABEL_191;
        }
        v20 = 0;
        v24[2] = (NotificationHandler)v74;
        *v24 = v75;
      }
    }
    else
    {
      if ( !is_mul_ok(v26, 2u) )
      {
LABEL_34:
        v20 = -2147024362;
        goto LABEL_35;
      }
      v50 = (void (__stdcall *)(GUID, void *))CoTaskMemAlloc(2 * v26);
      if ( v50 )
      {
        v20 = 0;
        v24[2] = (NotificationHandler)v26;
        *v24 = v50;
        *(_WORD *)v50 = 0;
      }
      if ( v20 < 0 )
        goto LABEL_191;
    }
    if ( v25 != -1 )
    {
      v51 = *v24;
      if ( v26 > 0x7FFFFFFF )
      {
        *v51 = 0;
      }
      else
      {
        if ( v25 > 0x7FFFFFFE )
        {
          *v51 = 0;
          v24[1] = (NotificationHandler)v25;
LABEL_35:
          if ( v20 >= 0 )
          {
            v13 = this;
            goto LABEL_37;
          }
LABEL_191:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x28,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
            (const char *)(unsigned int)v20,
            v82);
          return (unsigned int)v20;
        }
        v52 = v25;
        do
        {
          if ( !v52 )
            break;
          v53 = *a3;
          if ( !*a3 )
            break;
          ++a3;
          *v51++ = v53;
          --v52;
          --v26;
        }
        while ( v26 );
        v54 = v51 - 1;
        if ( v26 )
          v54 = v51;
        *v54 = 0;
      }
    }
    v24[1] = (NotificationHandler)v25;
    goto LABEL_35;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v13 + 12);
LABEL_37:
  v28 = v13 + 15;
  if ( !a4 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v13 + 15);
    v29 = -1;
LABEL_47:
    v34 = v13 + 18;
    v35 = a9;
    if ( !a9 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v13 + 18);
      goto LABEL_72;
    }
    v36 = -1;
    do
      ++v36;
    while ( a9[v36] );
    v37 = v36 + 1;
    if ( v36 + 1 < v36 )
      goto LABEL_54;
    v38 = (unsigned __int64)v34[2];
    if ( v38 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v34);
      if ( *v34 )
        v38 = (unsigned __int64)v34[1] + 1;
      else
        v38 = 0;
      v34[2] = (NotificationHandler)v38;
    }
    if ( v38 )
    {
      v39 = 0;
      if ( v37 > v38 )
      {
        v78 = 2 * v38;
        if ( !is_mul_ok(v38, 2u) )
          goto LABEL_54;
        if ( v38 > 0x800 )
          v78 = v38 + 2048;
        if ( v37 > v78 )
          v78 = v36 + 1;
        v79 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(*v34, 2 * v78);
        if ( !v79 )
        {
          v39 = -2147024882;
          goto LABEL_56;
        }
        v39 = 0;
        v34[2] = (NotificationHandler)v78;
        *v34 = v79;
      }
    }
    else
    {
      if ( !is_mul_ok(v37, 2u) )
      {
LABEL_54:
        v39 = -2147024362;
        goto LABEL_55;
      }
      v60 = (void (__stdcall *)(GUID, void *))CoTaskMemAlloc(2 * v37);
      if ( v60 )
      {
        v39 = 0;
        v34[2] = (NotificationHandler)v37;
        *v34 = v60;
        *(_WORD *)v60 = 0;
      }
      else
      {
        v39 = -2147024882;
      }
      if ( v39 < 0 )
        goto LABEL_56;
    }
    if ( v36 != -1 )
    {
      v61 = (unsigned __int16 *)*v34;
      if ( v37 > 0x7FFFFFFF )
      {
        *v61 = 0;
      }
      else
      {
        if ( v36 > 0x7FFFFFFE )
        {
          *v61 = 0;
          v34[1] = (NotificationHandler)v36;
          goto LABEL_55;
        }
        v62 = v36;
        do
        {
          if ( !v62 )
            break;
          v63 = *v35;
          if ( !*v35 )
            break;
          ++v35;
          *v61++ = v63;
          --v62;
          --v37;
        }
        while ( v37 );
        v64 = v61 - 1;
        if ( v37 )
          v64 = v61;
        *v64 = 0;
      }
    }
    v34[1] = (NotificationHandler)v36;
LABEL_55:
    if ( v39 < 0 )
    {
LABEL_56:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
        (const char *)(unsigned int)v39,
        v82);
      return (unsigned int)v39;
    }
    v13 = this;
LABEL_72:
    v45 = v13 + 22;
    v46 = a10;
    if ( !a10 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v13 + 22);
      return 0;
    }
    do
      ++v29;
    while ( a10[v29] );
    v47 = v29 + 1;
    if ( v29 + 1 < v29 )
      goto LABEL_78;
    v48 = (unsigned __int64)v45[2];
    if ( v48 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v45);
      if ( *v45 )
        v48 = (unsigned __int64)v45[1] + 1;
      else
        v48 = 0;
      v45[2] = (NotificationHandler)v48;
    }
    if ( v48 )
    {
      v49 = 0;
      if ( v47 > v48 )
      {
        v80 = 2 * v48;
        if ( !is_mul_ok(v48, 2u) )
          goto LABEL_78;
        if ( v48 > 0x800 )
          v80 = v48 + 2048;
        if ( v47 > v80 )
          v80 = v29 + 1;
        v81 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(*v45, 2 * v80);
        if ( !v81 )
        {
          v49 = -2147024882;
          goto LABEL_80;
        }
        v49 = 0;
        v45[2] = (NotificationHandler)v80;
        *v45 = v81;
      }
    }
    else
    {
      if ( !is_mul_ok(v47, 2u) )
      {
LABEL_78:
        v49 = -2147024362;
        goto LABEL_79;
      }
      v68 = (void (__stdcall *)(GUID, void *))CoTaskMemAlloc(2 * v47);
      if ( v68 )
      {
        v69 = 0;
        v45[2] = (NotificationHandler)v47;
        *v45 = v68;
        *(_WORD *)v68 = 0;
      }
      else
      {
        v69 = -2147024882;
      }
      v49 = v69;
      if ( v69 < 0 )
        goto LABEL_80;
    }
    if ( v29 != -1 )
    {
      v70 = (unsigned __int16 *)*v45;
      if ( v47 > 0x7FFFFFFF )
      {
        *v70 = 0;
      }
      else
      {
        if ( v29 > 0x7FFFFFFE )
        {
          *v70 = 0;
          v45[1] = (NotificationHandler)v29;
LABEL_79:
          if ( v49 < 0 )
          {
LABEL_80:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2B,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
              (const char *)(unsigned int)v49,
              v82);
            return (unsigned int)v49;
          }
          return 0;
        }
        v71 = v29;
        do
        {
          if ( !v71 )
            break;
          v72 = *v46;
          if ( !*v46 )
            break;
          ++v46;
          *v70++ = v72;
          --v71;
          --v47;
        }
        while ( v47 );
        v73 = v70 - 1;
        if ( v47 )
          v73 = v70;
        *v73 = 0;
      }
    }
    v45[1] = (NotificationHandler)v29;
    goto LABEL_79;
  }
  v29 = -1;
  v30 = -1;
  do
    ++v30;
  while ( a4[v30] );
  v31 = v30 + 1;
  if ( v30 + 1 < v30 )
    goto LABEL_44;
  v32 = (unsigned __int64)v28[2];
  if ( v32 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v28);
    if ( *v28 )
      v32 = (unsigned __int64)v28[1] + 1;
    else
      v32 = 0;
    v28[2] = (NotificationHandler)v32;
  }
  if ( v32 )
  {
    v33 = 0;
    if ( v31 <= v32 )
      goto LABEL_98;
    v76 = 2 * v32;
    if ( !is_mul_ok(v32, 2u) )
      goto LABEL_44;
    if ( v32 > 0x800 )
      v76 = v32 + 2048;
    if ( v31 > v76 )
      v76 = v30 + 1;
    v77 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(*v28, 2 * v76);
    if ( v77 )
    {
      v33 = 0;
      v28[2] = (NotificationHandler)v76;
      *v28 = v77;
      goto LABEL_98;
    }
    v33 = -2147024882;
  }
  else
  {
    if ( !is_mul_ok(v31, 2u) )
    {
LABEL_44:
      v33 = -2147024362;
      goto LABEL_45;
    }
    v55 = (void (__stdcall *)(GUID, void *))CoTaskMemAlloc(2 * v31);
    if ( v55 )
    {
      v33 = 0;
      v28[2] = (NotificationHandler)v31;
      *v28 = v55;
      *(_WORD *)v55 = 0;
    }
    else
    {
      v33 = -2147024882;
    }
    if ( v33 >= 0 )
    {
LABEL_98:
      if ( v30 != -1 )
      {
        v56 = *v28;
        if ( v31 > 0x7FFFFFFF )
        {
          *v56 = 0;
        }
        else
        {
          if ( v30 > 0x7FFFFFFE )
          {
            *v56 = 0;
            v28[1] = (NotificationHandler)v30;
LABEL_45:
            if ( v33 >= 0 )
            {
              v13 = this;
              goto LABEL_47;
            }
            goto LABEL_194;
          }
          v57 = v30;
          do
          {
            if ( !v57 )
              break;
            v58 = *a4;
            if ( !*a4 )
              break;
            ++a4;
            *v56++ = v58;
            --v57;
            --v31;
          }
          while ( v31 );
          v59 = v56 - 1;
          if ( v31 )
            v59 = v56;
          *v59 = 0;
        }
      }
      v28[1] = (NotificationHandler)v30;
      goto LABEL_45;
    }
  }
LABEL_194:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x29,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
    (const char *)(unsigned int)v33,
    v82);
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x180010b90  mov     [rsp+arg_10], rbx
0x180010b95  mov     [rsp+arg_0], rcx
0x180010b9a  push    rbp
0x180010b9b  push    rsi
0x180010b9c  push    rdi
0x180010b9d  push    r12
0x180010b9f  push    r13
0x180010ba1  push    r14
0x180010ba3  push    r15; int
0x180010ba5  sub     rsp, 20h
0x180010ba9  mov     r15, r9
0x180010bac  mov     r14, r8
0x180010baf  mov     rbx, rdx
0x180010bb2  mov     rdi, rcx
0x180010bb5  lea     r13, [rcx+30h]
0x180010bb9  test    rdx, rdx
0x180010bbc  jz      loc_1800114E3
0x180010bc2  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180010bc9  mov     rbp, rdx
0x180010bcc  nop     dword ptr [rax+00h]
0x180010bd0  inc     rbp
0x180010bd3  cmp     word ptr [rbx+rbp*2], 0
0x180010bd8  jnz     short loc_180010BD0
0x180010bda  lea     rdi, [rbp+1]
0x180010bde  xor     esi, esi
0x180010be0  cmp     rdi, rbp
0x180010be3  jb      short loc_180010C0C
0x180010be5  mov     rcx, [r13+10h]
0x180010be9  cmp     rcx, rdx
0x180010bec  jz      loc_18001118D
0x180010bf2  test    rcx, rcx
0x180010bf5  jnz     loc_18001112F
0x180010bfb  mov     eax, 2
0x180010c00  mul     rdi
0x180010c03  test    rdx, rdx
0x180010c06  jz      loc_180010E78
0x180010c0c  mov     r12d, 80070216h
0x180010c12  test    r12d, r12d
0x180010c15  jns     short loc_180010C48
0x180010c17  mov     rcx, [rsp+58h]; this
0x180010c1c  mov     r9d, r12d; char *
0x180010c1f  lea     r8, aOnecoreuapBase_83; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010c26  mov     edx, 23h ; '#'; void *
0x180010c2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c30  mov     eax, r12d
0x180010c33  mov     rbx, [rsp+58h+arg_10]
0x180010c38  add     rsp, 20h
0x180010c3c  pop     r15
0x180010c3e  pop     r14
0x180010c40  pop     r13
0x180010c42  pop     r12
0x180010c44  pop     rdi
0x180010c45  pop     rsi
0x180010c46  pop     rbp
0x180010c47  retn
0x180010c48  mov     rdi, [rsp+58h+arg_0]
0x180010c4d  mov     ebp, 8007000Eh
0x180010c52  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180010c59  xor     r13d, r13d
0x180010c5c  mov     rbx, [rsp+58h+arg_20]
0x180010c64  cmp     [rdi+48h], rbx
0x180010c68  jz      short loc_180010C99
0x180010c6a  test    rbx, rbx
0x180010c6d  jz      short loc_180010C7F
0x180010c6f  mov     rax, [rbx]
0x180010c72  mov     rcx, rbx
0x180010c75  mov     rax, [rax+8]
0x180010c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c7e  nop
0x180010c7f  mov     rcx, [rdi+48h]
0x180010c83  mov     [rdi+48h], rbx
0x180010c87  test    rcx, rcx
0x180010c8a  jz      short loc_180010C99
0x180010c8c  mov     rax, [rcx]
0x180010c8f  mov     rax, [rax+10h]
0x180010c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c98  nop
0x180010c99  mov     rbx, [rsp+58h+arg_28]
0x180010ca1  cmp     [rdi+50h], rbx
0x180010ca5  jz      short loc_180010CD6
0x180010ca7  test    rbx, rbx
0x180010caa  jz      short loc_180010CBC
0x180010cac  mov     rax, [rbx]
0x180010caf  mov     rcx, rbx
0x180010cb2  mov     rax, [rax+8]
0x180010cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cbb  nop
0x180010cbc  mov     rcx, [rdi+50h]
0x180010cc0  mov     [rdi+50h], rbx
0x180010cc4  test    rcx, rcx
0x180010cc7  jz      short loc_180010CD6
0x180010cc9  mov     rax, [rcx]
0x180010ccc  mov     rax, [rax+10h]
0x180010cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cd5  nop
0x180010cd6  mov     rbx, [rsp+58h+arg_30]
0x180010cde  cmp     [rdi+58h], rbx
0x180010ce2  jz      short loc_180010D13
0x180010ce4  test    rbx, rbx
0x180010ce7  jz      short loc_180010CF9
0x180010ce9  mov     rax, [rbx]
0x180010cec  mov     rcx, rbx
0x180010cef  mov     rax, [rax+8]
0x180010cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cf8  nop
0x180010cf9  mov     rcx, [rdi+58h]
0x180010cfd  mov     [rdi+58h], rbx
0x180010d01  test    rcx, rcx
0x180010d04  jz      short loc_180010D13
0x180010d06  mov     rax, [rcx]
0x180010d09  mov     rax, [rax+10h]
0x180010d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d12  nop
0x180010d13  mov     rax, [rsp+58h+arg_38]
0x180010d1b  mov     [rdi+0A8h], rax
0x180010d22  lea     r12, [rdi+60h]
0x180010d26  test    r14, r14
0x180010d29  jz      loc_180011509
0x180010d2f  mov     rdi, rsi
0x180010d32  inc     rdi
0x180010d35  cmp     word ptr [r14+rdi*2], 0
0x180010d3b  jnz     short loc_180010D32
0x180010d3d  lea     rbx, [rdi+1]
0x180010d41  cmp     rbx, rdi
0x180010d44  jb      short loc_180010D6F
0x180010d46  mov     rcx, [r12+10h]
0x180010d4b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010d4f  jz      loc_180011317
0x180010d55  test    rcx, rcx
0x180010d58  jnz     loc_18001125A
0x180010d5e  mov     eax, 2
0x180010d63  mul     rbx
0x180010d66  test    rdx, rdx
0x180010d69  jz      loc_180010F8A
0x180010d6f  mov     ebp, 80070216h
0x180010d74  test    ebp, ebp
0x180010d76  js      loc_1800113ED
0x180010d7c  mov     rdi, [rsp+58h+arg_0]
0x180010d81  lea     r14, [rdi+78h]
0x180010d85  test    r15, r15
0x180010d88  jz      loc_180011516
0x180010d8e  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180010d95  mov     rdi, r12
0x180010d98  nop     dword ptr [rax+rax+00000000h]
0x180010da0  inc     rdi
0x180010da3  cmp     word ptr [r15+rdi*2], 0
0x180010da9  jnz     short loc_180010DA0
0x180010dab  lea     rbx, [rdi+1]
0x180010daf  cmp     rbx, rdi
0x180010db2  jb      short loc_180010DDB
0x180010db4  mov     rcx, [r14+10h]
0x180010db8  cmp     rcx, r12
0x180010dbb  jz      loc_180011399
0x180010dc1  test    rcx, rcx
0x180010dc4  jnz     loc_1800112BA
0x180010dca  mov     eax, 2
0x180010dcf  mul     rbx
0x180010dd2  test    rdx, rdx
0x180010dd5  jz      loc_180011011
0x180010ddb  mov     ebp, 80070216h
0x180010de0  test    ebp, ebp
0x180010de2  js      loc_18001141C
0x180010de8  mov     rdi, [rsp+58h+arg_0]
0x180010ded  lea     r15, [rdi+90h]
0x180010df4  mov     rbx, [rsp+58h+arg_40]
0x180010dfc  test    rbx, rbx
0x180010dff  jz      loc_18001152A
0x180010e05  mov     rsi, r12
0x180010e08  nop     dword ptr [rax+rax+00000000h]
0x180010e10  inc     rsi
0x180010e13  cmp     word ptr [rbx+rsi*2], 0
0x180010e18  jnz     short loc_180010E10
0x180010e1a  lea     rdi, [rsi+1]
0x180010e1e  cmp     rdi, rsi
0x180010e21  jb      short loc_180010E4B
0x180010e23  mov     rcx, [r15+10h]
0x180010e27  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010e2b  jz      loc_1800113BB
0x180010e31  test    rcx, rcx
0x180010e34  jnz     loc_18001133C
0x180010e3a  mov     eax, 2
0x180010e3f  mul     rdi
0x180010e42  test    rdx, rdx
0x180010e45  jz      loc_18001109A
0x180010e4b  mov     ebp, 80070216h
0x180010e50  test    ebp, ebp
0x180010e52  jns     loc_180010EFF
0x180010e58  mov     rcx, [rsp+58h]; this
0x180010e5d  mov     r9d, ebp; char *
0x180010e60  lea     r8, aOnecoreuapBase_83; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010e67  mov     edx, 2Ah ; '*'; void *
0x180010e6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010e71  mov     eax, ebp
0x180010e73  jmp     loc_180010C33
0x180010e78  mov     rcx, rax; cb
0x180010e7b  call    cs:__imp_CoTaskMemAlloc
0x180010e81  test    rax, rax
0x180010e84  jz      loc_18001124F
0x180010e8a  mov     r12d, esi
0x180010e8d  mov     [r13+10h], rdi
0x180010e91  mov     [r13+0], rax
0x180010e95  mov     [rax], si
0x180010e98  test    r12d, r12d
0x180010e9b  js      loc_180010C17
0x180010ea1  test    rdi, rdi
0x180010ea4  jz      short loc_180010EF6
0x180010ea6  mov     rdx, [r13+0]
0x180010eaa  cmp     rdi, 7FFFFFFFh
0x180010eb1  ja      loc_180011594
0x180010eb7  cmp     rbp, 7FFFFFFEh
0x180010ebe  ja      loc_18001153F
0x180010ec4  mov     rcx, rbp
0x180010ec7  test    rcx, rcx
0x180010eca  jz      short loc_180010EE8
0x180010ecc  movzx   eax, word ptr [rbx]
0x180010ecf  test    ax, ax
0x180010ed2  jz      short loc_180010EE8
0x180010ed4  add     rbx, 2
0x180010ed8  mov     [rdx], ax
0x180010edb  add     rdx, 2
0x180010edf  dec     rcx
0x180010ee2  sub     rdi, 1
0x180010ee6  jnz     short loc_180010EC7
0x180010ee8  lea     rax, [rdx-2]
0x180010eec  test    rdi, rdi
0x180010eef  cmovnz  rax, rdx
0x180010ef3  mov     [rax], si
0x180010ef6  mov     [r13+8], rbp
0x180010efa  jmp     loc_180010C12
0x180010eff  mov     rdi, [rsp+58h+arg_0]
0x180010f04  lea     r14, [rdi+0B0h]
0x180010f0b  mov     rbx, [rsp+58h+arg_48]
0x180010f13  test    rbx, rbx
0x180010f16  jz      loc_180011120
0x180010f1c  nop     dword ptr [rax+00h]
0x180010f20  inc     r12
0x180010f23  cmp     word ptr [rbx+r12*2], 0
0x180010f29  jnz     short loc_180010F20
0x180010f2b  lea     rdi, [r12+1]
0x180010f30  cmp     rdi, r12
0x180010f33  jb      short loc_180010F5D
0x180010f35  mov     r8, [r14+10h]
0x180010f39  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180010f3d  jz      loc_1800114BB
0x180010f43  test    r8, r8
0x180010f46  jnz     loc_18001145E
0x180010f4c  mov     eax, 2
0x180010f51  mul     rdi
0x180010f54  test    rdx, rdx
0x180010f57  jz      loc_1800111C7
0x180010f5d  mov     ebp, 80070216h
0x180010f62  test    ebp, ebp
0x180010f64  jns     loc_180011128
0x180010f6a  mov     rcx, [rsp+58h]; this
0x180010f6f  mov     r9d, ebp; char *
0x180010f72  lea     r8, aOnecoreuapBase_83; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180010f79  mov     edx, 2Bh ; '+'; void *
0x180010f7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010f83  mov     eax, ebp
0x180010f85  jmp     loc_180010C33
0x180010f8a  mov     rcx, rax; cb
0x180010f8d  call    cs:__imp_CoTaskMemAlloc
0x180010f93  test    rax, rax
0x180010f96  jz      short loc_180010FA8
0x180010f98  mov     ebp, r13d
0x180010f9b  mov     [r12+10h], rbx
0x180010fa0  mov     [r12], rax
0x180010fa4  mov     [rax], r13w
0x180010fa8  test    ebp, ebp
0x180010faa  js      loc_1800113ED
0x180010fb0  test    rbx, rbx
0x180010fb3  jz      short loc_180011007
0x180010fb5  mov     rdx, [r12]
0x180010fb9  cmp     rbx, 7FFFFFFFh
0x180010fc0  ja      loc_1800115B0
0x180010fc6  cmp     rdi, 7FFFFFFEh
0x180010fcd  ja      loc_18001154B
0x180010fd3  mov     rcx, rdi
0x180010fd6  test    rcx, rcx
0x180010fd9  jz      short loc_180010FF8
0x180010fdb  movzx   eax, word ptr [r14]
0x180010fdf  test    ax, ax
0x180010fe2  jz      short loc_180010FF8
0x180010fe4  add     r14, 2
0x180010fe8  mov     [rdx], ax
0x180010feb  add     rdx, 2
0x180010fef  dec     rcx
0x180010ff2  sub     rbx, 1
0x180010ff6  jnz     short loc_180010FD6
0x180010ff8  lea     rax, [rdx-2]
0x180010ffc  test    rbx, rbx
0x180010fff  cmovnz  rax, rdx
0x180011003  mov     [rax], r13w
0x180011007  mov     [r12+8], rdi
0x18001100c  jmp     loc_180010D74
0x180011011  mov     rcx, rax; cb
0x180011014  call    cs:__imp_CoTaskMemAlloc
0x18001101a  test    rax, rax
0x18001101d  jz      loc_18001140D
0x180011023  mov     ebp, r13d
  ... truncated ...
```
