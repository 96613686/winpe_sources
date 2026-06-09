# I_XmlAllocAndCopyKeyInfo

- ea: `0x18000d500`
- end: `0x18000e20c`
- name: `I_XmlAllocAndCopyKeyInfo`
- size: `3340`
- prototype: `__int64 __fastcall(HANDLE hHeap)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b3b0`
- `0x180012d90`

## callees

- `0x18000d500`
- `0x180014ce0`
- `0x18001860d`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d81d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d81d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d51a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d619`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d700`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d77c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d7b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d8d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000da6e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000dad6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000db94`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000dc80`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000dd68`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d51a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d619`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d700`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d77c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d7b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d8d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000da6e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000dad6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000db94`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000dc80`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000dd68`

## string_xrefs

- `0x18000d838`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18000e195`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlAllocAndCopyKeyInfo(HANDLE hHeap, __int64 a2, _QWORD *a3)
{
  _QWORD *v4; // r14
  unsigned int v6; // eax
  unsigned int v7; // edx
  unsigned int v8; // esi
  unsigned __int64 v9; // rdi
  __int64 v10; // rdx
  unsigned __int64 v11; // r15
  int v12; // eax
  __int64 v13; // r8
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  const WCHAR *v20; // rcx
  unsigned __int64 v21; // rcx
  const WCHAR *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // r12
  __int64 v25; // rcx
  const WCHAR *v26; // rcx
  const WCHAR *v27; // rcx
  int v28; // eax
  __int64 v29; // rax
  _QWORD *v30; // rax
  _QWORD *v31; // rsi
  const char *v32; // r8
  char v33; // dl
  const char *v34; // r9
  bool v35; // zf
  unsigned int v37; // eax
  unsigned __int64 v38; // rbp
  size_t v39; // r12
  char *v40; // r12
  unsigned int v41; // ebp
  unsigned __int64 v42; // r15
  _DWORD *v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rbp
  __int64 v47; // r13
  __int64 v48; // rdx
  __int64 v49; // rdi
  __int64 v50; // rdi
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rdi
  size_t v54; // rdi
  __int64 v55; // rcx
  int v56; // eax
  int v57; // eax
  int v58; // eax
  size_t v59; // rdi
  __int64 v60; // rcx
  char *v61; // rdi
  __int64 v62; // rcx
  char *v63; // rdi
  __int64 v64; // r12
  unsigned __int64 v65; // rdi
  __int64 v66; // rcx
  const char *v67; // r8
  char v68; // dl
  const char *v69; // r9
  bool v70; // zf
  int v71; // [rsp+68h] [rbp+10h]

  v4 = a3;
  v6 = lstrlenW(*(LPCWSTR *)(a2 + 8));
  *v4 = 0;
  v7 = *(_DWORD *)(a2 + 16);
  if ( v7 <= 0x7FF8 && v6 <= 0x100 )
  {
    v8 = 0;
    v9 = ((2LL * (v6 + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL) + ((unsigned __int64)v7 << 7) + 40;
    if ( v7 )
    {
      do
      {
        v10 = *(_QWORD *)(a2 + 24);
        v11 = (unsigned __int64)v8 << 7;
        v12 = *(_DWORD *)(v10 + v11);
        v13 = v10 + v11;
        if ( v12 == 4 )
        {
          v23 = *(unsigned int *)(v13 + 8);
          v9 += 24 * v23;
          if ( (_DWORD)v23 )
          {
            v24 = 0;
            do
            {
              v25 = 24 * v24 + *(_QWORD *)(v10 + v11 + 16);
              switch ( *(_DWORD *)v25 )
              {
                case 1:
                  v26 = *(const WCHAR **)(v25 + 8);
                  if ( v26 )
                    v9 += ((unsigned int)(2 * lstrlenW(v26) + 2) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
                  v10 = *(_QWORD *)(a2 + 24);
                  v27 = *(const WCHAR **)(*(_QWORD *)(v10 + v11 + 16) + 24 * v24 + 16);
                  goto LABEL_29;
                case 2:
                case 4:
                case 5:
                  v29 = *(unsigned int *)(v25 + 8);
                  goto LABEL_34;
                case 3:
                  v27 = *(const WCHAR **)(v25 + 8);
LABEL_29:
                  if ( v27 )
                  {
                    v28 = lstrlenW(v27);
                    v10 = *(_QWORD *)(a2 + 24);
                    v9 += ((unsigned int)(2 * v28 + 2) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
                  }
                  break;
                case 6:
                  v29 = *(unsigned int *)(v25 + 12);
LABEL_34:
                  v9 += (v29 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
                  break;
                default:
                  break;
              }
              v24 = (unsigned int)(v24 + 1);
            }
            while ( (unsigned int)v24 < *(_DWORD *)(v10 + v11 + 8) );
          }
          goto LABEL_36;
        }
        v14 = v12 - 1;
        if ( !v14 )
        {
          v22 = *(const WCHAR **)(v13 + 8);
          if ( v22 )
            v9 += ((unsigned int)(2 * lstrlenW(v22) + 2) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
          goto LABEL_36;
        }
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( !v16 || v16 == 2 )
            v9 += (*(unsigned int *)(v13 + 12) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
        }
        else
        {
          v17 = *(_DWORD *)(v13 + 8);
          if ( v17 == 2 )
          {
            v21 = (*(unsigned int *)(v13 + 32) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
          }
          else
          {
            v18 = v17 - 1;
            if ( v18 )
            {
              v19 = v18 - 2;
              if ( v19 )
              {
                if ( v19 == 1 )
                  v9 += (*(unsigned int *)(v13 + 20) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              else
              {
                v20 = *(const WCHAR **)(v13 + 16);
                if ( v20 )
                  v9 += ((unsigned int)(2 * lstrlenW(v20) + 2) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
                v9 += ((*(unsigned int *)(*(_QWORD *)(a2 + 24) + v11 + 40) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
                    + ((*(unsigned int *)(*(_QWORD *)(a2 + 24) + v11 + 60) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
                    + ((*(unsigned int *)(*(_QWORD *)(a2 + 24) + v11 + 24) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
              }
              goto LABEL_36;
            }
            v21 = ((*(unsigned int *)(v13 + 32) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
                + ((*(unsigned int *)(v13 + 48) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
                + ((*(unsigned int *)(v13 + 64) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
                + ((*(unsigned int *)(v13 + 80) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
                + ((*(unsigned int *)(v13 + 96) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
                + ((*(unsigned int *)(v13 + 112) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
          }
          v9 += v21 + ((*(unsigned int *)(v13 + 16) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
        }
LABEL_36:
        ++v8;
      }
      while ( v8 < *(_DWORD *)(a2 + 16) );
    }
    v30 = HeapAlloc(hHeap, 8u, v9 + 4);
    v31 = v30;
    if ( !v30 )
    {
      v32 = "";
      while ( 1 )
      {
        v33 = *(v32 - 1);
        v34 = v32--;
        v35 = v33 == 92;
        if ( v33 == 92 )
          break;
        if ( v32 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
        {
          v35 = v33 == 92;
          break;
        }
      }
      if ( v35 )
        v32 = v34;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v32, 1041);
      return 2147942414LL;
    }
    *(_DWORD *)((char *)v30 + v9) = 305414945;
    *(_DWORD *)v30 = 40;
    v30[4] = *(_QWORD *)(a2 + 32);
    v30[3] = v30 + 5;
    v37 = *(_DWORD *)(a2 + 16);
    *((_DWORD *)v31 + 4) = v37;
    v38 = (unsigned __int64)&v31[16 * (unsigned __int64)v37 + 5];
    if ( *(_QWORD *)(a2 + 8) )
    {
      v31[1] = v38;
      v39 = (unsigned int)(2 * lstrlenW(*(LPCWSTR *)(a2 + 8)) + 2);
      memcpy_0((void *)v31[1], *(const void **)(a2 + 8), v39);
      v40 = (char *)(v38 + ((v39 + 7) & 0xFFFFFFFFFFFFFFF8uLL));
    }
    else
    {
      v40 = (char *)&v31[16 * (unsigned __int64)v37 + 5];
    }
    v41 = 0;
    v71 = 0;
    if ( !*((_DWORD *)v31 + 4) )
    {
LABEL_101:
      *v4 = v31;
      return 0;
    }
    while ( 1 )
    {
      v42 = (unsigned __int64)v41 << 7;
      *(_DWORD *)(v42 + v31[3]) = *(_DWORD *)(v42 + *(_QWORD *)(a2 + 24));
      v43 = (_DWORD *)(v42 + *(_QWORD *)(a2 + 24));
      switch ( *v43 )
      {
        case 2:
          *(_DWORD *)(v31[3] + v42 + 8) = v43[2];
          v55 = *(_QWORD *)(a2 + 24);
          v56 = *(_DWORD *)(v55 + v42 + 8);
          if ( v56 == 2 )
          {
            *(_QWORD *)(v31[3] + v42 + 24) = v40;
            *(_DWORD *)(v31[3] + v42 + 16) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16);
            memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 24), *(unsigned int *)(v31[3] + v42 + 16));
            v66 = v31[3];
            v63 = &v40[(*(unsigned int *)(v66 + v42 + 16) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
            *(_QWORD *)(v66 + v42 + 40) = v63;
            *(_DWORD *)(v31[3] + v42 + 32) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 32);
            memcpy_0(v63, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 40), *(unsigned int *)(v31[3] + v42 + 32));
            v64 = *(unsigned int *)(v31[3] + v42 + 32);
            goto LABEL_98;
          }
          v57 = v56 - 1;
          if ( !v57 )
          {
            if ( *(_DWORD *)(v55 + v42 + 16) )
            {
              *(_QWORD *)(v31[3] + v42 + 24) = v40;
              *(_DWORD *)(v31[3] + v42 + 16) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16);
              memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 24), *(unsigned int *)(v31[3] + v42 + 16));
              v40 += (*(unsigned int *)(v31[3] + v42 + 16) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
            }
            if ( *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 32) )
            {
              *(_QWORD *)(v31[3] + v42 + 40) = v40;
              *(_DWORD *)(v31[3] + v42 + 32) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 32);
              memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 40), *(unsigned int *)(v31[3] + v42 + 32));
              v40 += (*(unsigned int *)(v31[3] + v42 + 32) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
            }
            if ( *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 80) )
            {
              *(_QWORD *)(v31[3] + v42 + 88) = v40;
              *(_DWORD *)(v31[3] + v42 + 80) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 80);
              memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 88), *(unsigned int *)(v31[3] + v42 + 80));
              v40 += (*(unsigned int *)(v31[3] + v42 + 80) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
            }
            if ( *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 64) )
            {
              *(_QWORD *)(v31[3] + v42 + 72) = v40;
              *(_DWORD *)(v31[3] + v42 + 64) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 64);
              memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 72), *(unsigned int *)(v31[3] + v42 + 64));
              v40 += (*(unsigned int *)(v31[3] + v42 + 64) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
            }
            if ( *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 48) )
            {
              *(_QWORD *)(v31[3] + v42 + 56) = v40;
              *(_DWORD *)(v31[3] + v42 + 48) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 48);
              memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 56), *(unsigned int *)(v31[3] + v42 + 48));
              v40 += (*(unsigned int *)(v31[3] + v42 + 48) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
            }
            if ( *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 96) )
            {
              *(_QWORD *)(v31[3] + v42 + 104) = v40;
              *(_DWORD *)(v31[3] + v42 + 96) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 96);
              memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 104), *(unsigned int *)(v31[3] + v42 + 96));
              v40 += (*(unsigned int *)(v31[3] + v42 + 96) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
            }
            if ( *(_DWORD *)(((unsigned __int64)v41 << 7) + *(_QWORD *)(a2 + 24) + 112) )
            {
              *(_QWORD *)(((unsigned __int64)v41 << 7) + v31[3] + 120) = v40;
              v65 = (unsigned __int64)v41 << 7;
              *(_DWORD *)(v31[3] + v65 + 112) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v65 + 112);
              memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v65 + 120), *(unsigned int *)(v31[3] + v65 + 112));
              v40 += (*(unsigned int *)(v31[3] + v65 + 112) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
            }
            break;
          }
          v58 = v57 - 2;
          if ( v58 )
          {
            if ( v58 == 1 )
            {
              *(_QWORD *)(v31[3] + v42 + 24) = v40;
              *(_DWORD *)(v31[3] + v42 + 16) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16);
              *(_DWORD *)(v31[3] + v42 + 20) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 20);
              memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 24), *(unsigned int *)(v31[3] + v42 + 20));
              v40 += (*(unsigned int *)(v31[3] + v42 + 20) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
            }
            break;
          }
          if ( *(_QWORD *)(v55 + v42 + 16) )
          {
            *(_QWORD *)(v31[3] + v42 + 16) = v40;
            v59 = (unsigned int)(2 * lstrlenW(*(LPCWSTR *)(*(_QWORD *)(a2 + 24) + v42 + 16)) + 2);
            memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 16), v59);
            v40 += (v59 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          }
          *(_QWORD *)(v31[3] + v42 + 32) = v40;
          *(_DWORD *)(v31[3] + v42 + 24) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 24);
          memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 32), *(unsigned int *)(v31[3] + v42 + 24));
          v60 = v31[3];
          v61 = &v40[(*(unsigned int *)(v60 + v42 + 24) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
          *(_QWORD *)(v60 + v42 + 48) = v61;
          *(_DWORD *)(v31[3] + v42 + 40) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 40);
          memcpy_0(v61, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 48), *(unsigned int *)(v31[3] + v42 + 40));
          v62 = v31[3];
          v63 = &v61[(*(unsigned int *)(v62 + v42 + 40) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
          if ( *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 60) )
          {
            *(_QWORD *)(v62 + v42 + 64) = v63;
            *(_DWORD *)(v31[3] + v42 + 60) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 60);
            memcpy_0(v63, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 64), *(unsigned int *)(v31[3] + v42 + 60));
            v64 = *(unsigned int *)(v31[3] + v42 + 60);
LABEL_98:
            v40 = &v63[(v64 + 7) & 0xFFFFFFFFFFFFFFF8uLL];
            break;
          }
          v40 = v63;
          break;
        case 1:
          if ( *((_QWORD *)v43 + 1) )
          {
            *(_QWORD *)(v31[3] + v42 + 8) = v40;
            v54 = (unsigned int)(2 * lstrlenW(*(LPCWSTR *)(*(_QWORD *)(a2 + 24) + v42 + 8)) + 2);
            memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 8), v54);
            v40 += (v54 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          }
          break;
        case 3:
          goto LABEL_55;
        case 4:
          *(_DWORD *)(v31[3] + v42 + 8) = v43[2];
          *(_QWORD *)(v31[3] + v42 + 16) = v40;
          v44 = *(_QWORD *)(a2 + 24);
          v45 = *(unsigned int *)(v44 + v42 + 8);
          v40 += 24 * v45;
          if ( (_DWORD)v45 )
          {
            v46 = 0;
            while ( 2 )
            {
              v47 = 24 * v46;
              *(_DWORD *)(*(_QWORD *)(v42 + v31[3] + 16) + 24 * v46) = *(_DWORD *)(*(_QWORD *)(v44 + v42 + 16) + 24 * v46);
              v48 = *(_QWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16);
              switch ( *(_DWORD *)(v48 + 24 * v46) )
              {
                case 1:
                  if ( *(_QWORD *)(v48 + v47 + 8) )
                  {
                    *(_QWORD *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 8) = v40;
                    v49 = (unsigned int)(2
                                       * lstrlenW(*(LPCWSTR *)(*(_QWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16) + v47 + 8))
                                       + 2);
                    memcpy_0(
                      v40,
                      *(const void **)(*(_QWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16) + v47 + 8),
                      (unsigned int)v49);
                    v40 += (v49 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
                  }
                  if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16) + v47 + 16) )
                  {
                    *(_QWORD *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 16) = v40;
                    v50 = (unsigned int)(2
                                       * lstrlenW(*(LPCWSTR *)(*(_QWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16) + v47 + 16))
                                       + 2);
                    memcpy_0(
                      v40,
                      *(const void **)(*(_QWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16) + v47 + 16),
                      (unsigned int)v50);
                    v51 = v50 + 7;
                    goto LABEL_68;
                  }
                  goto LABEL_69;
                case 2:
                case 4:
                case 5:
                  *(_QWORD *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 16) = v40;
                  *(_DWORD *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 8) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 24)
                                                                                                + v42
                                                                                                + 16)
                                                                                    + v47
                                                                                    + 8);
                  memcpy_0(
                    v40,
                    *(const void **)(*(_QWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16) + v47 + 16),
                    *(unsigned int *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 8));
                  v52 = *(unsigned int *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 8);
                  goto LABEL_67;
                case 3:
                  if ( !*(_QWORD *)(v48 + v47 + 8) )
                    goto LABEL_69;
                  *(_QWORD *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 8) = v40;
                  v53 = (unsigned int)(2
                                     * lstrlenW(*(LPCWSTR *)(*(_QWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16) + v47 + 8))
                                     + 2);
                  memcpy_0(
                    v40,
                    *(const void **)(*(_QWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16) + v47 + 8),
                    (unsigned int)v53);
                  v51 = v53 + 7;
LABEL_68:
                  v40 += v51 & 0xFFFFFFFFFFFFFFF8uLL;
LABEL_69:
                  v44 = *(_QWORD *)(a2 + 24);
                  v46 = (unsigned int)(v46 + 1);
                  if ( (unsigned int)v46 < *(_DWORD *)(v42 + v44 + 8) )
                    continue;
                  v41 = v71;
                  break;
                case 6:
                  *(_QWORD *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 16) = v40;
                  *(_DWORD *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 8) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 24)
                                                                                                + v42
                                                                                                + 16)
                                                                                    + v47
                                                                                    + 8);
                  *(_DWORD *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 12) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 24)
                                                                                                 + v42
                                                                                                 + 16)
                                                                                     + v47
                                                                                     + 12);
                  memcpy_0(
                    v40,
                    *(const void **)(*(_QWORD *)(*(_QWORD *)(a2 + 24) + v42 + 16) + v47 + 16),
                    *(unsigned int *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 12));
                  v52 = *(unsigned int *)(*(_QWORD *)(v31[3] + v42 + 16) + v47 + 12);
LABEL_67:
                  v51 = v52 + 7;
                  goto LABEL_68;
                default:
                  goto LABEL_69;
              }
              break;
            }
          }
          break;
        case 5:
LABEL_55:
          *(_QWORD *)(v31[3] + v42 + 16) = v40;
          *(_DWORD *)(v31[3] + v42 + 8) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 8);
          *(_DWORD *)(v31[3] + v42 + 12) = *(_DWORD *)(*(_QWORD *)(a2 + 24) + v42 + 12);
          memcpy_0(v40, *(const void **)(*(_QWORD *)(a2 + 24) + v42 + 16), *(unsigned int *)(v31[3] + v42 + 12));
          v40 += (*(unsigned int *)(v31[3] + v42 + 12) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
          break;
      }
      v71 = ++v41;
      if ( v41 >= *((_DWORD *)v31 + 4) )
      {
        v4 = a3;
        goto LABEL_101;
      }
    }
  }
  v67 = "";
  while ( 1 )
  {
    v68 = *(v67 - 1);
    v69 = v67--;
    v70 = v68 == 92;
    if ( v68 == 92 )
      break;
    if ( v67 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
    {
      v70 = v68 == 92;
      break;
    }
  }
  if ( v70 )
    v67 = v69;
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885375, v67, 915);
  return 2148081921LL;
}

```

## disassembly

```asm
0x18000d500  mov     [rsp+arg_10], r8
0x18000d505  push    rbx
0x18000d506  push    rbp
0x18000d507  push    r14
0x18000d509  sub     rsp, 40h
0x18000d50d  mov     rbp, rcx
0x18000d510  mov     r14, r8
0x18000d513  mov     rcx, [rdx+8]; lpString
0x18000d517  mov     rbx, rdx
0x18000d51a  call    cs:__imp_lstrlenW
0x18000d521  nop     dword ptr [rax+rax+00h]
0x18000d526  mov     qword ptr [r14], 0
0x18000d52d  mov     edx, [rbx+10h]
0x18000d530  cmp     edx, 7FF8h
0x18000d536  ja      loc_18000E18E
0x18000d53c  cmp     eax, 100h
0x18000d541  ja      loc_18000E18E
0x18000d547  mov     [rsp+58h+arg_0], rsi
0x18000d54c  lea     r9, __ImageBase
0x18000d553  mov     [rsp+58h+var_20], rdi
0x18000d558  inc     eax
0x18000d55a  mov     [rsp+58h+var_28], r12
0x18000d55f  mov     edi, edx
0x18000d561  shl     rdi, 7
0x18000d565  xor     esi, esi
0x18000d567  add     rdi, 28h ; '('
0x18000d56b  mov     [rsp+58h+var_30], r13
0x18000d570  lea     rcx, ds:7[rax*2]
0x18000d578  mov     [rsp+58h+var_38], r15
0x18000d57d  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000d581  add     rdi, rcx
0x18000d584  test    edx, edx
0x18000d586  jz      loc_18000D811
0x18000d58c  mov     rdx, [rbx+18h]
0x18000d590  mov     r15d, esi
0x18000d593  shl     r15, 7
0x18000d597  mov     eax, [rdx+r15]
0x18000d59b  lea     r8, [rdx+r15]
0x18000d59f  cmp     eax, 4
0x18000d5a2  jz      loc_18000D72A
0x18000d5a8  sub     eax, 1
0x18000d5ab  jz      loc_18000D6F3
0x18000d5b1  sub     eax, 1
0x18000d5b4  jz      short loc_18000D5D8
0x18000d5b6  sub     eax, 1
0x18000d5b9  jz      short loc_18000D5C4
0x18000d5bb  cmp     eax, 2
0x18000d5be  jnz     loc_18000D806
0x18000d5c4  mov     eax, [r8+0Ch]
0x18000d5c8  add     rax, 7
0x18000d5cc  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d5d0  add     rdi, rax
0x18000d5d3  jmp     loc_18000D806
0x18000d5d8  mov     eax, [r8+8]
0x18000d5dc  cmp     eax, 2
0x18000d5df  jz      loc_18000D6D0
0x18000d5e5  sub     eax, 1
0x18000d5e8  jz      loc_18000D677
0x18000d5ee  sub     eax, 2
0x18000d5f1  jz      short loc_18000D610
0x18000d5f3  cmp     eax, 1
0x18000d5f6  jnz     loc_18000D806
0x18000d5fc  mov     eax, [r8+14h]
0x18000d600  add     rax, 7
0x18000d604  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d608  add     rdi, rax
0x18000d60b  jmp     loc_18000D806
0x18000d610  mov     rcx, [r8+10h]; lpString
0x18000d614  test    rcx, rcx
0x18000d617  jz      short loc_18000D63E
0x18000d619  call    cs:__imp_lstrlenW
0x18000d620  nop     dword ptr [rax+rax+00h]
0x18000d625  lea     r9, __ImageBase
0x18000d62c  lea     ecx, ds:2[rax*2]
0x18000d633  add     rcx, 7
0x18000d637  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000d63b  add     rdi, rcx
0x18000d63e  mov     rcx, [rbx+18h]
0x18000d642  mov     edx, [rcx+r15+3Ch]
0x18000d647  mov     eax, [rcx+r15+28h]
0x18000d64c  add     rdx, 7
0x18000d650  add     rax, 7
0x18000d654  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000d658  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d65c  add     rdx, rax
0x18000d65f  mov     eax, [rcx+r15+18h]
0x18000d664  add     rax, 7
0x18000d668  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d66c  add     rdi, rax
0x18000d66f  add     rdi, rdx
0x18000d672  jmp     loc_18000D806
0x18000d677  mov     ecx, [r8+70h]
0x18000d67b  mov     eax, [r8+60h]
0x18000d67f  add     rcx, 7
0x18000d683  add     rax, 7
0x18000d687  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000d68b  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d68f  add     rcx, rax
0x18000d692  mov     eax, [r8+50h]
0x18000d696  add     rax, 7
0x18000d69a  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d69e  add     rcx, rax
0x18000d6a1  mov     eax, [r8+40h]
0x18000d6a5  add     rax, 7
0x18000d6a9  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d6ad  add     rcx, rax
0x18000d6b0  mov     eax, [r8+30h]
0x18000d6b4  add     rax, 7
0x18000d6b8  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d6bc  add     rcx, rax
0x18000d6bf  mov     eax, [r8+20h]
0x18000d6c3  add     rax, 7
0x18000d6c7  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d6cb  add     rcx, rax
0x18000d6ce  jmp     short loc_18000D6DC
0x18000d6d0  mov     ecx, [r8+20h]
0x18000d6d4  add     rcx, 7
0x18000d6d8  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000d6dc  mov     eax, [r8+10h]
0x18000d6e0  add     rax, 7
0x18000d6e4  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d6e8  add     rdi, rax
0x18000d6eb  add     rdi, rcx
0x18000d6ee  jmp     loc_18000D806
0x18000d6f3  mov     rcx, [r8+8]; lpString
0x18000d6f7  test    rcx, rcx
0x18000d6fa  jz      loc_18000D806
0x18000d700  call    cs:__imp_lstrlenW
0x18000d707  nop     dword ptr [rax+rax+00h]
0x18000d70c  lea     r9, __ImageBase
0x18000d713  lea     ecx, ds:2[rax*2]
0x18000d71a  add     rcx, 7
0x18000d71e  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000d722  add     rdi, rcx
0x18000d725  jmp     loc_18000D806
0x18000d72a  mov     ecx, [r8+8]
0x18000d72e  lea     rax, [rcx+rcx*2]
0x18000d732  lea     rdi, [rdi+rax*8]
0x18000d736  test    ecx, ecx
0x18000d738  jz      loc_18000D806
0x18000d73e  xor     r12d, r12d
0x18000d741  lea     rcx, [r12+r12*2]
0x18000d745  lea     r13, ds:0[rcx*8]
0x18000d74d  mov     rcx, [rdx+r15+10h]
0x18000d752  add     rcx, r13
0x18000d755  mov     eax, [rcx]
0x18000d757  dec     eax; switch 6 cases
0x18000d759  cmp     eax, 5
0x18000d75c  ja      def_18000D76D; jumptable 000000018000D76D default case
0x18000d762  mov     eax, ds:(jpt_18000D76D - 180000000h)[r9+rax*4]
0x18000d76a  add     rax, r9
0x18000d76d  jmp     rax; switch jump
0x18000d773  mov     rcx, [rcx+8]; jumptable 000000018000D76D case 1
0x18000d777  test    rcx, rcx
0x18000d77a  jz      short loc_18000D7A1
0x18000d77c  call    cs:__imp_lstrlenW
0x18000d783  nop     dword ptr [rax+rax+00h]
0x18000d788  lea     r9, __ImageBase
0x18000d78f  lea     ecx, ds:2[rax*2]
0x18000d796  add     rcx, 7
0x18000d79a  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000d79e  add     rdi, rcx
0x18000d7a1  mov     rdx, [rbx+18h]
0x18000d7a5  mov     rax, [rdx+r15+10h]
0x18000d7aa  mov     rcx, [rax+r13+10h]; lpString
0x18000d7af  test    rcx, rcx
0x18000d7b2  jz      short def_18000D76D; jumptable 000000018000D76D default case
0x18000d7b4  call    cs:__imp_lstrlenW
0x18000d7bb  nop     dword ptr [rax+rax+00h]
0x18000d7c0  mov     rdx, [rbx+18h]
0x18000d7c4  lea     r9, __ImageBase
0x18000d7cb  lea     ecx, ds:2[rax*2]
0x18000d7d2  add     rcx, 7
0x18000d7d6  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000d7da  add     rdi, rcx
0x18000d7dd  jmp     short def_18000D76D; jumptable 000000018000D76D default case
0x18000d7df  mov     eax, [rcx+8]; jumptable 000000018000D76D cases 2,4,5
0x18000d7e2  jmp     short loc_18000D7ED
0x18000d7e4  mov     rcx, [rcx+8]; jumptable 000000018000D76D case 3
0x18000d7e8  jmp     short loc_18000D7AF
0x18000d7ea  mov     eax, [rcx+0Ch]; jumptable 000000018000D76D case 6
0x18000d7ed  add     rax, 7
0x18000d7f1  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000d7f5  add     rdi, rax
0x18000d7f8  inc     r12d; jumptable 000000018000D76D default case
0x18000d7fb  cmp     r12d, [rdx+r15+8]
0x18000d800  jb      loc_18000D741
0x18000d806  inc     esi
0x18000d808  cmp     esi, [rbx+10h]
0x18000d80b  jb      loc_18000D58C
0x18000d811  lea     r8, [rdi+4]; dwBytes
0x18000d815  mov     edx, 8; dwFlags
0x18000d81a  mov     rcx, rbp; hHeap
0x18000d81d  call    cs:__imp_HeapAlloc
0x18000d824  nop     dword ptr [rax+rax+00h]
0x18000d829  mov     rsi, rax
0x18000d82c  test    rax, rax
0x18000d82f  jnz     short loc_18000D89A
0x18000d831  lea     r8, aOnecoreDsSecur_1+35h; ""
0x18000d838  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d83f  movzx   edx, byte ptr [r8-1]
0x18000d844  mov     r9, r8
0x18000d847  dec     r8
0x18000d84a  cmp     dl, 5Ch ; '\'
0x18000d84d  jz      short loc_18000D857
0x18000d84f  cmp     r8, rcx
0x18000d852  ja      short loc_18000D83F
0x18000d854  cmp     dl, 5Ch ; '\'
0x18000d857  cmovz   r8, r9
0x18000d85b  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d862  mov     r9d, 411h
0x18000d868  mov     edx, 8007000Eh
0x18000d86d  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000d872  mov     eax, 8007000Eh
0x18000d877  mov     r13, [rsp+58h+var_30]
0x18000d87c  mov     r12, [rsp+58h+var_28]
0x18000d881  mov     r15, [rsp+58h+var_38]
0x18000d886  mov     rsi, [rsp+58h+arg_0]
0x18000d88b  mov     rdi, [rsp+58h+var_20]
0x18000d890  add     rsp, 40h
0x18000d894  pop     r14
0x18000d896  pop     rbp
0x18000d897  pop     rbx
0x18000d898  retn
0x18000d89a  mov     dword ptr [rdi+rax], 12344321h
0x18000d8a1  lea     rcx, [rsi+28h]
0x18000d8a5  mov     dword ptr [rax], 28h ; '('
0x18000d8ab  mov     rax, [rbx+20h]
0x18000d8af  mov     [rsi+20h], rax
0x18000d8b3  mov     [rsi+18h], rcx
0x18000d8b7  mov     eax, [rbx+10h]
0x18000d8ba  mov     ebp, eax
0x18000d8bc  mov     [rsi+10h], eax
0x18000d8bf  shl     rbp, 7
0x18000d8c3  add     rbp, rcx
0x18000d8c6  cmp     qword ptr [rbx+8], 0
0x18000d8cb  jz      short loc_18000D908
0x18000d8cd  mov     [rsi+8], rbp
0x18000d8d1  mov     rcx, [rbx+8]; lpString
0x18000d8d5  call    cs:__imp_lstrlenW
0x18000d8dc  nop     dword ptr [rax+rax+00h]
0x18000d8e1  mov     rdx, [rbx+8]; Src
0x18000d8e5  mov     rcx, [rsi+8]; void *
0x18000d8e9  lea     eax, ds:2[rax*2]
0x18000d8f0  mov     r8d, eax; Size
0x18000d8f3  mov     r12d, eax
0x18000d8f6  call    memcpy_0
0x18000d8fb  add     r12, 7
0x18000d8ff  and     r12, 0FFFFFFFFFFFFFFF8h
0x18000d903  add     r12, rbp
0x18000d906  jmp     short loc_18000D90B
0x18000d908  mov     r12, rbp
0x18000d90b  xor     ebp, ebp
0x18000d90d  mov     [rsp+58h+arg_8], ebp
0x18000d911  cmp     [rsi+10h], ebp
0x18000d914  jbe     loc_18000E184
0x18000d91a  lea     r14, __ImageBase
0x18000d921  mov     rax, [rbx+18h]
0x18000d925  mov     rcx, [rsi+18h]
0x18000d929  mov     r15d, ebp
0x18000d92c  shl     r15, 7
0x18000d930  mov     edi, ebp
0x18000d932  mov     eax, [r15+rax]
0x18000d936  mov     [r15+rcx], eax
0x18000d93a  mov     rdx, [rbx+18h]
0x18000d93e  add     rdx, r15
0x18000d941  mov     eax, [rdx]
0x18000d943  cmp     eax, 2
0x18000d946  jz      loc_18000DCB9
0x18000d94c  sub     eax, 1
0x18000d94f  jz      loc_18000DC63
0x18000d955  sub     eax, 2
0x18000d958  jz      short loc_18000D968
0x18000d95a  sub     eax, 1
0x18000d95d  jz      short loc_18000D9C8
0x18000d95f  cmp     eax, 1
0x18000d962  jnz     loc_18000E170
0x18000d968  mov     rax, [rsi+18h]
0x18000d96c  mov     [rax+r15+10h], r12
0x18000d971  mov     rax, [rbx+18h]
0x18000d975  mov     rcx, [rsi+18h]
0x18000d979  mov     eax, [rax+r15+8]
0x18000d97e  mov     [rcx+r15+8], eax
0x18000d983  mov     rax, [rbx+18h]
0x18000d987  mov     rcx, [rsi+18h]
0x18000d98b  mov     eax, [rax+r15+0Ch]
0x18000d990  mov     [rcx+r15+0Ch], eax
0x18000d995  mov     rcx, r12; void *
0x18000d998  mov     rax, [rsi+18h]
0x18000d99c  mov     rdx, [rbx+18h]
0x18000d9a0  mov     r8d, [rax+r15+0Ch]; Size
0x18000d9a5  mov     rdx, [rdx+r15+10h]; Src
0x18000d9aa  call    memcpy_0
0x18000d9af  mov     rax, [rsi+18h]
0x18000d9b3  mov     ecx, [rax+r15+0Ch]
0x18000d9b8  add     rcx, 7
0x18000d9bc  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000d9c0  add     r12, rcx
0x18000d9c3  jmp     loc_18000E170
0x18000d9c8  mov     eax, [rdx+8]
  ... truncated ...
```
