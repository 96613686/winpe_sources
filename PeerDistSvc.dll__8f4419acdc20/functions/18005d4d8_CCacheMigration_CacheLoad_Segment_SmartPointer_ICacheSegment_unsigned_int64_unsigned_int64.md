# CCacheMigration::CacheLoad_Segment(SmartPointer<ICacheSegment> *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18005d4d8`
- end: `0x18005e569`
- name: `?CacheLoad_Segment@CCacheMigration@@AEAAJPEAV?$SmartPointer@VICacheSegment@@@@PEA_K1@Z`
- size: `4241`
- prototype: `__int64 __fastcall(CCacheMigration *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18005eab4`

## callees

- `0x1800024a4`
- `0x1800024fc`
- `0x180002d42`
- `0x180008290`
- `0x18002f2bc`
- `0x18003ab84`
- `0x18005d4d8`
- `0x18005f668`
- `0x18013920c`
- `0x18013937c`
- `0x1801448c0`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d72e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d8b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005db86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dc5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dd14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dde9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005deb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005df7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e1cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d5e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d72e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d8b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005db86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dc5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dd14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dde9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005deb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005df7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e1cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e357`
- `KERNEL32!ReadFile` at `0x18005d5d9`
- `KERNEL32!ReadFile` at `0x18005d724`
- `KERNEL32!ReadFile` at `0x18005d8ad`
- `KERNEL32!ReadFile` at `0x18005da3c`
- `KERNEL32!ReadFile` at `0x18005db7c`
- `KERNEL32!ReadFile` at `0x18005dc54`
- `KERNEL32!ReadFile` at `0x18005dd0a`
- `KERNEL32!ReadFile` at `0x18005dddf`
- `KERNEL32!ReadFile` at `0x18005dea8`
- `KERNEL32!ReadFile` at `0x18005df71`
- `KERNEL32!ReadFile` at `0x18005e027`
- `KERNEL32!ReadFile` at `0x18005e0fc`
- `KERNEL32!ReadFile` at `0x18005e1c5`
- `KERNEL32!ReadFile` at `0x18005e289`
- `KERNEL32!ReadFile` at `0x18005e34d`
- `KERNEL32!ReadFile` at `0x18005d5d9`
- `KERNEL32!ReadFile` at `0x18005d724`
- `KERNEL32!ReadFile` at `0x18005d8ad`
- `KERNEL32!ReadFile` at `0x18005da3c`
- `KERNEL32!ReadFile` at `0x18005db7c`
- `KERNEL32!ReadFile` at `0x18005dc54`
- `KERNEL32!ReadFile` at `0x18005dd0a`
- `KERNEL32!ReadFile` at `0x18005dddf`
- `KERNEL32!ReadFile` at `0x18005dea8`
- `KERNEL32!ReadFile` at `0x18005df71`
- `KERNEL32!ReadFile` at `0x18005e027`
- `KERNEL32!ReadFile` at `0x18005e0fc`
- `KERNEL32!ReadFile` at `0x18005e1c5`
- `KERNEL32!ReadFile` at `0x18005e289`
- `KERNEL32!ReadFile` at `0x18005e34d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCacheMigration::CacheLoad_Segment(CCacheMigration *this, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  unsigned int v5; // ecx
  __int64 v6; // rdx
  void **v7; // rbx
  signed int LastError; // esi
  __int64 v9; // rax
  bool v10; // cc
  TnoBaseHash *v11; // rax
  TnoBaseHash *v12; // r15
  unsigned int v13; // r9d
  __int64 v14; // rdx
  TnoBaseHash *v15; // rbx
  TnoBaseHash *v16; // rdi
  TnoBaseHash *v17; // rcx
  unsigned int v18; // eax
  unsigned __int64 v19; // r12
  unsigned __int8 *v20; // r15
  TnoBaseHash *v21; // rax
  TnoBaseHash *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r9
  __int64 v25; // rax
  TnoBaseHash *v26; // rcx
  TnoBaseHash *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rax
  int v31; // ebx
  TnoBaseHash *v32; // r12
  __int64 v33; // rdx
  __int64 v34; // r9
  __int64 v35; // rax
  __int64 v36; // rdx
  unsigned int v37; // r9d
  __int64 v38; // rdx
  unsigned int v39; // r9d
  __int64 v40; // rcx
  unsigned int v41; // r9d
  __int64 v42; // rdx
  unsigned int v43; // eax
  __int64 v44; // rdx
  unsigned int v45; // r9d
  unsigned int v46; // eax
  __int64 v47; // rdx
  unsigned int v48; // r9d
  __int64 v49; // rdx
  unsigned int v50; // r9d
  __int64 v51; // rcx
  unsigned int v52; // r9d
  __int64 v53; // rdx
  unsigned int v54; // eax
  __int64 v55; // rdx
  unsigned int v56; // r9d
  unsigned int v57; // eax
  __int64 v58; // rdx
  __int16 v59; // r12
  unsigned int v60; // r9d
  unsigned int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // rbx
  unsigned int v64; // r8d
  unsigned int v65; // eax
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp-C8h] BYREF
  TnoBaseHash *v68; // [rsp+78h] [rbp-C0h]
  TnoBaseHash *v69; // [rsp+80h] [rbp-B8h]
  unsigned int v70; // [rsp+88h] [rbp-B0h]
  int v71; // [rsp+8Ch] [rbp-ACh] BYREF
  unsigned __int8 *v72; // [rsp+90h] [rbp-A8h]
  TnoBaseHash *v73; // [rsp+98h] [rbp-A0h]
  TnoBaseHash *v74; // [rsp+A0h] [rbp-98h]
  TnoBaseHash *v75; // [rsp+A8h] [rbp-90h]
  TnoBaseHash *v76; // [rsp+B0h] [rbp-88h]
  _QWORD *v77; // [rsp+B8h] [rbp-80h]
  _QWORD *v78; // [rsp+C0h] [rbp-78h]
  __int64 v79; // [rsp+C8h] [rbp-70h] BYREF
  __int64 v80; // [rsp+D0h] [rbp-68h] BYREF
  __int64 v81; // [rsp+D8h] [rbp-60h]
  __int128 v82; // [rsp+E0h] [rbp-58h] BYREF

  try
  {
    v77 = a4;
    v78 = a3;
    v81 = a2;
    v69 = 0;
    v74 = 0;
    v80 = 0;
    v79 = 0;
    v68 = 0;
    v75 = 0;
    v73 = 0;
    v76 = 0;
    v82 = 0;
    v71 = 0;
    v5 = *((_DWORD *)this + 446);
    v6 = *((unsigned int *)this + 447);
    v7 = (void **)((char *)this + 1776);
    if ( (int)v6 + 4 > v5 )
    {
      NumberOfBytesRead = 0;
      if ( (_DWORD)v6 )
      {
        memmove_0(*v7, (char *)*v7 + v6, v5 - (unsigned int)v6);
        *((_DWORD *)this + 446) -= *((_DWORD *)this + 447);
        v5 = *((_DWORD *)this + 446);
        *((_DWORD *)this + 447) = 0;
      }
      if ( ReadFile(*((HANDLE *)this + 25), (char *)*v7 + v5, 0x100000 - v5, &NumberOfBytesRead, 0) )
      {
        if ( !NumberOfBytesRead )
        {
          LastError = 232;
          goto LABEL_10;
        }
        *((_DWORD *)this + 446) += NumberOfBytesRead;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError )
        {
LABEL_10:
          v70 = 0;
          if ( LastError == 232 )
          {
            LOWORD(LastError) = 259;
            goto LABEL_27;
          }
          goto LABEL_16;
        }
      }
    }
    v9 = *((unsigned int *)this + 447);
    if ( (unsigned int)(v9 + 4) > *((_DWORD *)this + 446) )
      goto LABEL_14;
    v70 = *(_DWORD *)((char *)*v7 + v9);
    *((_DWORD *)this + 447) = v9 + 4;
    LastError = 0;
LABEL_16:
    v10 = LastError <= 0;
    if ( LastError )
      goto LABEL_26;
    v11 = (TnoBaseHash *)operator new(0x20u);
    v12 = v11;
    v69 = v11;
    if ( v11 )
    {
      *((_DWORD *)v11 + 2) = 0;
      *((_QWORD *)v11 + 2) = 0;
      *((_BYTE *)v11 + 24) = 1;
      *(_QWORD *)v11 = &TnoHash::`vftable';
    }
    else
    {
      v12 = 0;
      v69 = 0;
    }
    v74 = v12;
    v13 = *((_DWORD *)this + 446);
    v14 = *((unsigned int *)this + 447);
    if ( (int)v14 + 2 > v13 )
    {
      NumberOfBytesRead = 0;
      if ( (_DWORD)v14 )
      {
        memmove_0(*((void **)this + 222), (const void *)(*((_QWORD *)this + 222) + v14), v13 - (unsigned int)v14);
        *((_DWORD *)this + 446) -= *((_DWORD *)this + 447);
        v13 = *((_DWORD *)this + 446);
        *((_DWORD *)this + 447) = 0;
      }
      if ( ReadFile(
             *((HANDLE *)this + 25),
             (LPVOID)(*((_QWORD *)this + 222) + v13),
             0x100000 - v13,
             &NumberOfBytesRead,
             0) )
      {
        if ( !NumberOfBytesRead )
          goto LABEL_173;
        *((_DWORD *)this + 446) += NumberOfBytesRead;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError )
        {
LABEL_25:
          v10 = LastError <= 0;
          goto LABEL_26;
        }
      }
    }
    v18 = *((_DWORD *)this + 447);
    if ( v18 + 2 <= *((_DWORD *)this + 446) )
    {
      v19 = *(unsigned __int16 *)(v18 + *((_QWORD *)this + 222));
      *((_DWORD *)this + 447) = v18 + 2;
      if ( (unsigned int)v19 > 0x40 )
        goto LABEL_33;
      if ( (_WORD)v19 )
      {
        v20 = (unsigned __int8 *)operator new[](v19);
        LastError = CCacheMigration::ReadData(this, v20, v19);
        TnoBaseHash::ReleaseHash(v69);
        v21 = v69;
        *((_QWORD *)v69 + 2) = v20;
        *((_DWORD *)v21 + 2) = v19;
        *((_BYTE *)v21 + 24) = 1;
        v10 = LastError <= 0;
        if ( LastError )
          goto LABEL_26;
      }
      v22 = (TnoBaseHash *)operator new(0x20u);
      v68 = v22;
      if ( v22 )
      {
        *((_DWORD *)v22 + 2) = 0;
        *((_QWORD *)v22 + 2) = 0;
        *((_BYTE *)v22 + 24) = 1;
        *(_QWORD *)v22 = &TnoHash::`vftable';
        v75 = v22;
      }
      else
      {
        v68 = 0;
        v75 = 0;
      }
      v23 = *((unsigned int *)this + 446);
      v24 = *((unsigned int *)this + 447);
      if ( (int)v24 + 2 > (unsigned int)v23 )
      {
        NumberOfBytesRead = 0;
        if ( (_DWORD)v24 )
        {
          memmove_0(*((void **)this + 222), (const void *)(*((_QWORD *)this + 222) + v24), (unsigned int)(v23 - v24));
          v23 = (unsigned int)(*((_DWORD *)this + 446) - *((_DWORD *)this + 447));
          *((_QWORD *)this + 223) = (unsigned int)v23;
        }
        if ( ReadFile(
               *((HANDLE *)this + 25),
               (LPVOID)(*((_QWORD *)this + 222) + v23),
               0x100000 - v23,
               &NumberOfBytesRead,
               0) )
        {
          if ( !NumberOfBytesRead )
          {
            LastError = 232;
            goto LABEL_51;
          }
          *((_DWORD *)this + 446) += NumberOfBytesRead;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError )
            goto LABEL_51;
        }
      }
      v25 = *((unsigned int *)this + 447);
      if ( (unsigned int)(v25 + 2) <= *((_DWORD *)this + 446) )
      {
        LOWORD(v19) = *(_WORD *)(v25 + *((_QWORD *)this + 222));
        *((_DWORD *)this + 447) = v25 + 2;
        LastError = 0;
        if ( (unsigned __int16)v19 > 0x80u )
          goto LABEL_33;
      }
      else
      {
        LastError = 122;
      }
LABEL_51:
      if ( (_WORD)v19 )
      {
        v10 = LastError <= 0;
        if ( LastError )
          goto LABEL_26;
        v72 = (unsigned __int8 *)operator new[]((unsigned __int16)v19);
        LastError = CCacheMigration::ReadData(this, v72, (unsigned __int16)v19);
        TnoBaseHash::ReleaseHash(v68);
        v26 = v68;
        *((_QWORD *)v68 + 2) = v72;
        *((_DWORD *)v26 + 2) = (unsigned __int16)v19;
        *((_BYTE *)v26 + 24) = 1;
      }
      v10 = LastError <= 0;
      if ( LastError )
        goto LABEL_26;
      v27 = (TnoBaseHash *)operator new(0x20u);
      v73 = v27;
      if ( v27 )
      {
        *((_DWORD *)v27 + 2) = 0;
        *((_QWORD *)v27 + 2) = 0;
        *((_BYTE *)v27 + 24) = 1;
        *(_QWORD *)v27 = &TnoHoHoDk::`vftable';
        v76 = v27;
      }
      else
      {
        v73 = 0;
        v76 = 0;
      }
      v28 = *((unsigned int *)this + 446);
      v29 = *((unsigned int *)this + 447);
      if ( (int)v29 + 2 > (unsigned int)v28 )
      {
        NumberOfBytesRead = 0;
        if ( (_DWORD)v29 )
        {
          memmove_0(*((void **)this + 222), (const void *)(*((_QWORD *)this + 222) + v29), (unsigned int)(v28 - v29));
          v28 = (unsigned int)(*((_DWORD *)this + 446) - *((_DWORD *)this + 447));
          *((_QWORD *)this + 223) = (unsigned int)v28;
        }
        if ( ReadFile(
               *((HANDLE *)this + 25),
               (LPVOID)(*((_QWORD *)this + 222) + v28),
               0x100000 - v28,
               &NumberOfBytesRead,
               0) )
        {
          if ( !NumberOfBytesRead )
          {
            LastError = 232;
LABEL_71:
            if ( (_WORD)v19 )
            {
              v10 = LastError <= 0;
              if ( LastError )
                goto LABEL_26;
              v72 = (unsigned __int8 *)operator new[]((unsigned __int16)v19);
              v31 = (unsigned __int16)v19;
              LastError = CCacheMigration::ReadData(this, v72, (unsigned __int16)v19);
              v32 = v73;
              TnoBaseHash::ReleaseHash(v73);
              *((_QWORD *)v32 + 2) = v72;
              *((_DWORD *)v32 + 2) = v31;
              *((_BYTE *)v32 + 24) = 1;
            }
            v10 = LastError <= 0;
            if ( !LastError )
            {
              v33 = *((unsigned int *)this + 446);
              v34 = *((unsigned int *)this + 447);
              if ( (int)v34 + 16 > (unsigned int)v33 )
              {
                NumberOfBytesRead = 0;
                if ( (_DWORD)v34 )
                {
                  memmove_0(
                    *((void **)this + 222),
                    (const void *)(*((_QWORD *)this + 222) + v34),
                    (unsigned int)(v33 - v34));
                  v33 = (unsigned int)(*((_DWORD *)this + 446) - *((_DWORD *)this + 447));
                  *((_QWORD *)this + 223) = (unsigned int)v33;
                }
                if ( ReadFile(
                       *((HANDLE *)this + 25),
                       (LPVOID)(*((_QWORD *)this + 222) + v33),
                       0x100000 - v33,
                       &NumberOfBytesRead,
                       0) )
                {
                  if ( !NumberOfBytesRead )
                    goto LABEL_173;
                  *((_DWORD *)this + 446) += NumberOfBytesRead;
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError )
                    goto LABEL_25;
                }
              }
              v35 = *((unsigned int *)this + 447);
              v36 = (unsigned int)(v35 + 16);
              if ( (unsigned int)v36 > *((_DWORD *)this + 446) )
                goto LABEL_84;
              v82 = *(_OWORD *)(*((_QWORD *)this + 222) + v35);
              *((_DWORD *)this + 447) = v36;
              v37 = *((_DWORD *)this + 446);
              if ( (int)v35 + 24 > v37 )
              {
                NumberOfBytesRead = 0;
                if ( (_DWORD)v35 != -16 )
                {
                  memmove_0(
                    *((void **)this + 222),
                    (const void *)(*((_QWORD *)this + 222) + v36),
                    v37 - (unsigned int)v36);
                  v37 = *((_DWORD *)this + 446) - *((_DWORD *)this + 447);
                  *((_QWORD *)this + 223) = v37;
                }
                if ( ReadFile(
                       *((HANDLE *)this + 25),
                       (LPVOID)(*((_QWORD *)this + 222) + v37),
                       0x100000 - v37,
                       &NumberOfBytesRead,
                       0) )
                {
                  if ( !NumberOfBytesRead )
                    goto LABEL_173;
                  *((_DWORD *)this + 446) += NumberOfBytesRead;
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError )
                    goto LABEL_25;
                }
              }
              v38 = (unsigned int)(*((_DWORD *)this + 447) + 8);
              if ( (unsigned int)v38 > *((_DWORD *)this + 446) )
                goto LABEL_84;
              *((_DWORD *)this + 447) = v38;
              v39 = *((_DWORD *)this + 446);
              if ( (int)v38 + 8 > v39 )
              {
                NumberOfBytesRead = 0;
                if ( (_DWORD)v38 )
                {
                  memmove_0(
                    *((void **)this + 222),
                    (const void *)(*((_QWORD *)this + 222) + v38),
                    v39 - (unsigned int)v38);
                  v39 = *((_DWORD *)this + 446) - *((_DWORD *)this + 447);
                  *((_QWORD *)this + 223) = v39;
                }
                if ( ReadFile(
                       *((HANDLE *)this + 25),
                       (LPVOID)(*((_QWORD *)this + 222) + v39),
                       0x100000 - v39,
                       &NumberOfBytesRead,
                       0) )
                {
                  if ( !NumberOfBytesRead )
                    goto LABEL_173;
                  *((_DWORD *)this + 446) += NumberOfBytesRead;
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError )
                    goto LABEL_25;
                }
              }
              v40 = *((unsigned int *)this + 447);
              if ( (unsigned int)(v40 + 8) > *((_DWORD *)this + 446) )
                goto LABEL_84;
              *v78 = *(_QWORD *)(v40 + *((_QWORD *)this + 222));
              v41 = *((_DWORD *)this + 447) + 8;
              *((_DWORD *)this + 447) = v41;
              v42 = *((unsigned int *)this + 446);
              if ( v41 + 4 > (unsigned int)v42 )
              {
                NumberOfBytesRead = 0;
                if ( v41 )
                {
                  memmove_0(
                    *((void **)this + 222),
                    (const void *)(*((_QWORD *)this + 222) + v41),
                    (unsigned int)v42 - v41);
                  v42 = (unsigned int)(*((_DWORD *)this + 446) - *((_DWORD *)this + 447));
                  *((_QWORD *)this + 223) = (unsigned int)v42;
                }
                if ( ReadFile(
                       *((HANDLE *)this + 25),
                       (LPVOID)(*((_QWORD *)this + 222) + v42),
                       0x100000 - v42,
                       &NumberOfBytesRead,
                       0) )
                {
                  if ( !NumberOfBytesRead )
                    goto LABEL_173;
                  *((_DWORD *)this + 446) += NumberOfBytesRead;
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError )
                    goto LABEL_25;
                }
              }
              v43 = *((_DWORD *)this + 447);
              v44 = v43 + 4;
              if ( (unsigned int)v44 > *((_DWORD *)this + 446) )
                goto LABEL_84;
              LODWORD(v72) = *(_DWORD *)(v43 + *((_QWORD *)this + 222));
              *((_DWORD *)this + 447) = v44;
              v45 = *((_DWORD *)this + 446);
              if ( v43 + 8 > v45 )
              {
                NumberOfBytesRead = 0;
                if ( v43 != -4 )
                {
                  memmove_0(
                    *((void **)this + 222),
                    (const void *)(*((_QWORD *)this + 222) + v44),
                    v45 - (unsigned int)v44);
                  v45 = *((_DWORD *)this + 446) - *((_DWORD *)this + 447);
                  *((_QWORD *)this + 223) = v45;
                }
                if ( ReadFile(
                       *((HANDLE *)this + 25),
                       (LPVOID)(*((_QWORD *)this + 222) + v45),
                       0x100000 - v45,
                       &NumberOfBytesRead,
                       0) )
                {
                  if ( !NumberOfBytesRead )
                    goto LABEL_173;
                  *((_DWORD *)this + 446) += NumberOfBytesRead;
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError )
                    goto LABEL_25;
                }
              }
              v46 = *((_DWORD *)this + 447);
              v47 = v46 + 4;
              if ( (unsigned int)v47 > *((_DWORD *)this + 446) )
                goto LABEL_84;
              LODWORD(v78) = *(_DWORD *)(v46 + *((_QWORD *)this + 222));
              *((_DWORD *)this + 447) = v47;
              v48 = *((_DWORD *)this + 446);
              if ( v46 + 12 > v48 )
              {
                NumberOfBytesRead = 0;
                if ( v46 != -4 )
                {
                  memmove_0(
                    *((void **)this + 222),
                    (const void *)(*((_QWORD *)this + 222) + v47),
                    v48 - (unsigned int)v47);
                  v48 = *((_DWORD *)this + 446) - *((_DWORD *)this + 447);
                  *((_QWORD *)this + 223) = v48;
                }
                if ( ReadFile(
                       *((HANDLE *)this + 25),
                       (LPVOID)(*((_QWORD *)this + 222) + v48),
                       0x100000 - v48,
                       &NumberOfBytesRead,
                       0) )
                {
                  if ( !NumberOfBytesRead )
                    goto LABEL_173;
                  *((_DWORD *)this + 446) += NumberOfBytesRead;
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError )
                    goto LABEL_25;
                }
              }
              v49 = (unsigned int)(*((_DWORD *)this + 447) + 8);
              if ( (unsigned int)v49 > *((_DWORD *)this + 446) )
                goto LABEL_84;
              *((_DWORD *)this + 447) = v49;
              v50 = *((_DWORD *)this + 446);
              if ( (int)v49 + 8 > v50 )
              {
                NumberOfBytesRead = 0;
                if ( (_DWORD)v49 )
                {
                  memmove_0(
                    *((void **)this + 222),
                    (const void *)(*((_QWORD *)this + 222) + v49),
                    v50 - (unsigned int)v49);
                  v50 = *((_DWORD *)this + 446) - *((_DWORD *)this + 447);
                  *((_QWORD *)this + 223) = v50;
                }
                if ( ReadFile(
                       *((HANDLE *)this + 25),
                       (LPVOID)(*((_QWORD *)this + 222) + v50),
                       0x100000 - v50,
                       &NumberOfBytesRead,
                       0) )
                {
                  if ( !NumberOfBytesRead )
                    goto LABEL_173;
                  *((_DWORD *)this + 446) += NumberOfBytesRead;
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError )
                    goto LABEL_25;
                }
              }
              v51 = *((unsigned int *)this + 447);
              if ( (unsigned int)(v51 + 8) > *((_DWORD *)this + 446) )
                goto LABEL_84;
              *v77 = *(_QWORD *)(v51 + *((_QWORD *)this + 222));
              v52 = *((_DWORD *)this + 447) + 8;
              *((_DWORD *)this + 447) = v52;
              v53 = *((unsigned int *)this + 446);
              if ( v52 + 4 > (unsigned int)v53 )
              {
                NumberOfBytesRead = 0;
                if ( v52 )
                {
                  memmove_0(
                    *((void **)this + 222),
                    (const void *)(*((_QWORD *)this + 222) + v52),
                    (unsigned int)v53 - v52);
                  v53 = (unsigned int)(*((_DWORD *)this + 446) - *((_DWORD *)this + 447));
                  *((_QWORD *)this + 223) = (unsigned int)v53;
                }
                if ( ReadFile(
                       *((HANDLE *)this + 25),
                       (LPVOID)(*((_QWORD *)this + 222) + v53),
                       0x100000 - v53,
                       &NumberOfBytesRead,
                       0) )
                {
                  if ( !NumberOfBytesRead )
                    goto LABEL_173;
                  *((_DWORD *)this + 446) += NumberOfBytesRead;
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError )
                    goto LABEL_25;
                }
              }
              v54 = *((_DWORD *)this + 447);
              v55 = v54 + 4;
              if ( (unsigned int)v55 > *((_DWORD *)this + 446) )
                goto LABEL_84;
              LODWORD(v77) = *(_DWORD *)(v54 + *((_QWORD *)this + 222));
              *((_DWORD *)this + 447) = v55;
              v56 = *((_DWORD *)this + 446);
              if ( v54 + 6 > v56 )
              {
                NumberOfBytesRead = 0;
                if ( v54 != -4 )
                {
                  memmove_0(
                    *((void **)this + 222),
                    (const void *)(*((_QWORD *)this + 222) + v55),
                    v56 - (unsigned int)v55);
                  v56 = *((_DWORD *)this + 446) - *((_DWORD *)this + 447);
                  *((_QWORD *)this + 223) = v56;
                }
                if ( ReadFile(
                       *((HANDLE *)this + 25),
                       (LPVOID)(*((_QWORD *)this + 222) + v56),
                       0x100000 - v56,
                       &NumberOfBytesRead,
                       0) )
                {
                  if ( !NumberOfBytesRead )
                    goto LABEL_173;
                  *((_DWORD *)this + 446) += NumberOfBytesRead;
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError )
                    goto LABEL_25;
                }
              }
              v57 = *((_DWORD *)this + 447);
              v58 = v57 + 2;
              if ( (unsigned int)v58 > *((_DWORD *)this + 446) )
                goto LABEL_84;
              v59 = *(_WORD *)(v57 + *((_QWORD *)this + 222));
              *((_DWORD *)this + 447) = v58;
              v60 = *((_DWORD *)this + 446);
              if ( v57 + 6 > v60 )
              {
                NumberOfBytesRead = 0;
                if ( v57 != -2 )
                {
                  memmove_0(
                    *((void **)this + 222),
                    (const void *)(*((_QWORD *)this + 222) + v58),
                    v60 - (unsigned int)v58);
                  v60 = *((_DWORD *)this + 446) - *((_DWORD *)this + 447);
                  *((_QWORD *)this + 223) = v60;
                }
                if ( ReadFile(
                       *((HANDLE *)this + 25),
                       (LPVOID)(*((_QWORD *)this + 222) + v60),
                       0x100000 - v60,
                       &NumberOfBytesRead,
                       0) )
                {
                  if ( !NumberOfBytesRead )
                    goto LABEL_173;
                  *((_DWORD *)this + 446) += NumberOfBytesRead;
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError )
                    goto LABEL_25;
                }
              }
              v61 = *((_DWORD *)this + 447);
              v62 = v61 + 4;
              if ( (unsigned int)v62 > *((_DWORD *)this + 446) )
                goto LABEL_84;
              v63 = *(unsigned int *)(v61 + *((_QWORD *)this + 222));
              *((_DWORD *)this + 447) = v62;
              v64 = *((_DWORD *)this + 446);
              if ( v61 + 8 <= v64 )
                goto LABEL_175;
              NumberOfBytesRead = 0;
              if ( v61 != -4 )
              {
                memmove_0(
                  *((void **)this + 222),
                  (const void *)(*((_QWORD *)this + 222) + v62),
                  v64 - (unsigned int)v62);
                v64 = *((_DWORD *)this + 446) - *((_DWORD *)this + 447);
                *((_QWORD *)this + 223) = v64;
              }
              if ( !ReadFile(
                      *((HANDLE *)this + 25),
                      (LPVOID)(*((_QWORD *)this + 222) + v64),
                      0x100000 - v64,
                      &NumberOfBytesRead,
                      0) )
              {
                LastError = GetLastError();
                if ( LastError )
                  goto LABEL_25;
LABEL_175:
                v65 = *((_DWORD *)this + 447) + 4;
                if ( v65 <= *((_DWORD *)this + 446) )
                {
                  *((_DWORD *)this + 447) = v65;
                  if ( CryptAlgIdToTnoAlgId(v70, (enum _TNO_HASH_ALG_ID *)&v71) )
                  {
                    LastError = (*(__int64 (__fastcall **)(_QWORD, TnoBaseHash *, TnoBaseHash *, TnoBaseHash *, int, __int128 *, _DWORD, _DWORD, _DWORD, __int16, __int64, _DWORD, __int64 *))(**((_QWORD **)this + 6) + 40LL))(
                                  *((_QWORD *)this + 6),
                                  v73,
                                  v69,
                                  v68,
                                  v71,
                                  &v82,
                                  (_DWORD)v72,
                                  (_DWORD)v78,
                                  (_DWORD)v77,
                                  v59,
                                  v63,
                                  0,
                                  &v79);
                    if ( !LastError )
                    {
                      LastError = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 48LL))(v79, &v80);
                      if ( LastError >= 0 )
                        SmartPointer<ICacheSegment>::operator=(v81, v80);
                      goto LABEL_28;
                    }
                    goto LABEL_25;
                  }
LABEL_33:
                  LOWORD(LastError) = 13;
                  goto LABEL_27;
                }
LABEL_84:
                LOWORD(LastError) = 122;
                goto LABEL_27;
              }
              if ( NumberOfBytesRead )
              {
                *((_DWORD *)this + 446) += NumberOfBytesRead;
                goto LABEL_175;
              }
LABEL_173:
              LastError = 232;
              goto LABEL_25;
            }
LABEL_26:
            if ( v10 )
            {
LABEL_28:
              v15 = v68;
              v16 = v73;
              v17 = v69;
              goto LABEL_205;
            }
LABEL_27:
            LastError = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_28;
          }
          *((_DWORD *)this + 446) += NumberOfBytesRead;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError )
            goto LABEL_71;
        }
      }
      v30 = *((unsigned int *)this + 447);
      if ( (unsigned int)(v30 + 2) <= *((_DWORD *)this + 446) )
      {
        LOWORD(v19) = *(_WORD *)(v30 + *((_QWORD *)this + 222));
        *((_DWORD *)this + 447) = v30 + 2;
        if ( (unsigned __int16)v19 > 0x80u )
          goto LABEL_33;
        LastError = 0;
      }
      else
      {
        LastError = 122;
      }
      goto LABEL_71;
    }
LABEL_14:
    LOWORD(LastError) = 122;
    goto LABEL_27;
  }
  catch ( std::bad_alloc )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 37, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids);
    }
    NumberOfBytesRead = -2147024882;
    LastError = -2147024882;
    v16 = v76;
    v15 = v75;
    v17 = v74;
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 38, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids);
    }
    NumberOfBytesRead = -2147024122;
    LastError = -2147024122;
    v16 = v76;
    v15 = v75;
    v17 = v74;
  }
LABEL_205:
  if ( v17 )
    (**(void (__fastcall ***)(TnoBaseHash *, __int64))v17)(v17, 1);
  if ( v16 )
    (**(void (__fastcall ***)(TnoBaseHash *, __int64))v16)(v16, 1);
  if ( v15 )
    (**(void (__fastcall ***)(TnoBaseHash *, __int64))v15)(v15, 1);
  if ( (int)(LastError + 0x80000000) >= 0
    && LastError != -2147024637
    && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      39,
      WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids,
      (unsigned int)LastError);
  }
  SmartPointer<ISegmentRecord>::Release(&v79);
  SmartPointer<ISegmentRecord>::Release(&v80);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18005d4d8  mov     r11, rsp
0x18005d4db  push    rbx
0x18005d4dc  push    rsi
0x18005d4dd  push    rdi
0x18005d4de  push    r12
0x18005d4e0  push    r13
0x18005d4e2  push    r14
0x18005d4e4  push    r15
0x18005d4e6  sub     rsp, 100h
0x18005d4ed  mov     rax, cs:__security_cookie
0x18005d4f4  xor     rax, rsp
0x18005d4f7  mov     [rsp+138h+var_48], rax
0x18005d4ff  mov     [rsp+138h+var_80], r9
0x18005d507  mov     [rsp+138h+var_78], r8
0x18005d50f  mov     [rsp+138h+var_60], rdx
0x18005d517  mov     rdi, rcx
0x18005d51a  xor     r14d, r14d
0x18005d51d  mov     [rsp+138h+var_B8], r14
0x18005d525  mov     [rsp+138h+var_98], r14
0x18005d52d  mov     [r11-68h], r14
0x18005d531  mov     [r11-70h], r14
0x18005d535  mov     eax, r14d
0x18005d538  mov     [rsp+138h+var_C0], rax
0x18005d53d  mov     [rsp+138h+var_90], rax
0x18005d545  mov     edx, r14d
0x18005d548  mov     [rsp+138h+var_A0], rdx
0x18005d550  mov     [rsp+138h+var_88], rdx
0x18005d558  xorps   xmm0, xmm0
0x18005d55b  movups  xmmword ptr [r11-58h], xmm0
0x18005d560  mov     [r11-0ACh], r14d
0x18005d567  mov     ecx, [rcx+6F8h]
0x18005d56d  mov     edx, [rdi+6FCh]
0x18005d573  lea     rbx, [rdi+6F0h]
0x18005d57a  lea     eax, [rdx+4]
0x18005d57d  cmp     eax, ecx
0x18005d57f  jbe     loc_18005D627
0x18005d585  mov     [rsp+138h+NumberOfBytesRead], r14d
0x18005d58a  test    edx, edx
0x18005d58c  jz      short loc_18005D5B7
0x18005d58e  sub     ecx, edx
0x18005d590  mov     r8d, ecx; Size
0x18005d593  add     rdx, [rbx]; Src
0x18005d596  mov     rcx, [rbx]; void *
0x18005d599  call    memmove_0
0x18005d59e  mov     eax, [rdi+6FCh]
0x18005d5a4  sub     [rdi+6F8h], eax
0x18005d5aa  mov     ecx, [rdi+6F8h]
0x18005d5b0  mov     [rdi+6FCh], r14d
0x18005d5b7  mov     r12d, 100000h
0x18005d5bd  mov     r8d, r12d
0x18005d5c0  sub     r8d, ecx; nNumberOfBytesToRead
0x18005d5c3  mov     edx, ecx
0x18005d5c5  add     rdx, [rbx]; lpBuffer
0x18005d5c8  mov     [rsp+138h+lpOverlapped], r14; lpOverlapped
0x18005d5cd  lea     r9, [rsp+138h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005d5d2  mov     rcx, [rdi+0C8h]; hFile
0x18005d5d9  call    cs:__imp_ReadFile
0x18005d5df  test    eax, eax
0x18005d5e1  jnz     short loc_18005D5F7
0x18005d5e3  call    cs:__imp_GetLastError
0x18005d5e9  mov     esi, eax
0x18005d5eb  test    eax, eax
0x18005d5ed  jz      short loc_18005D62D
0x18005d5ef  mov     r13d, 0E8h
0x18005d5f5  jmp     short loc_18005D608
0x18005d5f7  mov     eax, [rsp+138h+NumberOfBytesRead]
0x18005d5fb  test    eax, eax
0x18005d5fd  jnz     short loc_18005D61F
0x18005d5ff  mov     r13d, 0E8h
0x18005d605  mov     esi, r13d
0x18005d608  mov     [rsp+138h+var_B0], r14d
0x18005d610  cmp     esi, r13d
0x18005d613  jnz     short loc_18005D667
0x18005d615  mov     esi, 103h
0x18005d61a  jmp     loc_18005D73E
0x18005d61f  add     [rdi+6F8h], eax
0x18005d625  jmp     short loc_18005D62D
0x18005d627  mov     r12d, 100000h
0x18005d62d  mov     eax, [rdi+6FCh]
0x18005d633  lea     edx, [rax+4]
0x18005d636  cmp     edx, [rdi+6F8h]
0x18005d63c  jbe     short loc_18005D648
0x18005d63e  mov     esi, 7Ah ; 'z'
0x18005d643  jmp     loc_18005D73E
0x18005d648  mov     rcx, rax
0x18005d64b  mov     rax, [rbx]
0x18005d64e  mov     eax, [rcx+rax]
0x18005d651  mov     [rsp+138h+var_B0], eax
0x18005d658  mov     [rdi+6FCh], edx
0x18005d65e  mov     esi, r14d
0x18005d661  mov     r13d, 0E8h
0x18005d667  test    esi, esi
0x18005d669  jnz     loc_18005D73C
0x18005d66f  lea     ecx, [rsi+20h]; Size
0x18005d672  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005d677  mov     r15, rax
0x18005d67a  mov     [rsp+138h+var_B8], rax
0x18005d682  test    rax, rax
0x18005d685  jz      short loc_18005D69F
0x18005d687  mov     [rax+8], r14d
0x18005d68b  mov     [rax+10h], r14
0x18005d68f  mov     byte ptr [rax+18h], 1
0x18005d693  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x18005d69a  mov     [r15], rax
0x18005d69d  jmp     short loc_18005D6AA
0x18005d69f  mov     r15, r14
0x18005d6a2  mov     [rsp+138h+var_B8], r14
0x18005d6aa  mov     [rsp+138h+var_98], r15
0x18005d6b2  mov     r9d, [rdi+6F8h]
0x18005d6b9  mov     edx, [rdi+6FCh]
0x18005d6bf  lea     eax, [rdx+2]
0x18005d6c2  cmp     eax, r9d
0x18005d6c5  jbe     loc_18005D773
0x18005d6cb  mov     [rsp+138h+NumberOfBytesRead], r14d
0x18005d6d0  test    edx, edx
0x18005d6d2  jz      short loc_18005D703
0x18005d6d4  mov     rcx, [rdi+6F0h]; void *
0x18005d6db  sub     r9d, edx
0x18005d6de  mov     r8d, r9d; Size
0x18005d6e1  add     rdx, rcx; Src
0x18005d6e4  call    memmove_0
0x18005d6e9  mov     eax, [rdi+6FCh]
0x18005d6ef  sub     [rdi+6F8h], eax
0x18005d6f5  mov     r9d, [rdi+6F8h]
0x18005d6fc  mov     [rdi+6FCh], r14d
0x18005d703  mov     r8d, r12d
0x18005d706  sub     r8d, r9d; nNumberOfBytesToRead
0x18005d709  mov     edx, r9d
0x18005d70c  add     rdx, [rdi+6F0h]; lpBuffer
0x18005d713  mov     [rsp+138h+lpOverlapped], r14; lpOverlapped
0x18005d718  lea     r9, [rsp+138h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005d71d  mov     rcx, [rdi+0C8h]; hFile
0x18005d724  call    cs:__imp_ReadFile
0x18005d72a  test    eax, eax
0x18005d72c  jnz     short loc_18005D761
0x18005d72e  call    cs:__imp_GetLastError
0x18005d734  mov     esi, eax
0x18005d736  test    eax, eax
0x18005d738  jz      short loc_18005D773
0x18005d73a  test    esi, esi
0x18005d73c  jle     short loc_18005D747
0x18005d73e  movzx   esi, si
0x18005d741  or      esi, 80070000h
0x18005d747  mov     rbx, [rsp+138h+var_C0]
0x18005d74c  mov     rdi, [rsp+138h+var_A0]
0x18005d754  mov     rcx, [rsp+138h+var_B8]
0x18005d75c  jmp     loc_18005E498
0x18005d761  mov     eax, [rsp+138h+NumberOfBytesRead]
0x18005d765  test    eax, eax
0x18005d767  jz      loc_18005E370
0x18005d76d  add     [rdi+6F8h], eax
0x18005d773  mov     eax, [rdi+6FCh]
0x18005d779  lea     edx, [rax+2]
0x18005d77c  cmp     edx, [rdi+6F8h]
0x18005d782  ja      loc_18005D63E
0x18005d788  mov     ecx, eax
0x18005d78a  mov     rax, [rdi+6F0h]
0x18005d791  movzx   r12d, word ptr [rcx+rax]
0x18005d796  mov     [rdi+6FCh], edx
0x18005d79c  cmp     r12d, 40h ; '@'
0x18005d7a0  jbe     short loc_18005D7A9
0x18005d7a2  mov     esi, 0Dh
0x18005d7a7  jmp     short loc_18005D73E
0x18005d7a9  test    r12w, r12w
0x18005d7ad  jz      short loc_18005D7F3
0x18005d7af  mov     rcx, r12; unsigned __int64
0x18005d7b2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005d7b7  mov     r15, rax
0x18005d7ba  mov     r8d, r12d; unsigned int
0x18005d7bd  mov     rdx, rax; unsigned __int8 *
0x18005d7c0  mov     rcx, rdi; this
0x18005d7c3  call    ?ReadData@CCacheMigration@@AEAAKPEAEK@Z; CCacheMigration::ReadData(uchar *,ulong)
0x18005d7c8  mov     esi, eax
0x18005d7ca  mov     rcx, [rsp+138h+var_B8]; this
0x18005d7d2  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x18005d7d7  mov     rax, [rsp+138h+var_B8]
0x18005d7df  mov     [rax+10h], r15
0x18005d7e3  mov     [rax+8], r12d
0x18005d7e7  mov     byte ptr [rax+18h], 1
0x18005d7eb  test    esi, esi
0x18005d7ed  jnz     loc_18005D73C
0x18005d7f3  mov     ecx, 20h ; ' '; Size
0x18005d7f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005d7fd  mov     rcx, rax
0x18005d800  mov     [rsp+138h+var_C0], rax
0x18005d805  test    rax, rax
0x18005d808  jz      short loc_18005D82A
0x18005d80a  mov     [rax+8], r14d
0x18005d80e  mov     [rax+10h], r14
0x18005d812  mov     byte ptr [rax+18h], 1
0x18005d816  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x18005d81d  mov     [rcx], rax
0x18005d820  mov     [rsp+138h+var_90], rcx
0x18005d828  jmp     short loc_18005D83A
0x18005d82a  mov     rax, r14
0x18005d82d  mov     [rsp+138h+var_C0], rax
0x18005d832  mov     [rsp+138h+var_90], rax
0x18005d83a  mov     edx, [rdi+6F8h]
0x18005d840  mov     r9d, [rdi+6FCh]
0x18005d847  lea     eax, [r9+2]
0x18005d84b  cmp     eax, edx
0x18005d84d  jbe     loc_18005D8D8
0x18005d853  mov     [rsp+138h+NumberOfBytesRead], r14d
0x18005d858  test    r9d, r9d
0x18005d85b  jz      short loc_18005D88C
0x18005d85d  mov     rcx, [rdi+6F0h]; void *
0x18005d864  sub     edx, r9d
0x18005d867  mov     r8d, edx; Size
0x18005d86a  lea     rdx, [rcx+r9]; Src
0x18005d86e  call    memmove_0
0x18005d873  mov     edx, [rdi+6F8h]
0x18005d879  sub     edx, [rdi+6FCh]
0x18005d87f  mov     [rdi+6F8h], edx
0x18005d885  mov     [rdi+6FCh], r14d
0x18005d88c  mov     r8d, 100000h
0x18005d892  sub     r8d, edx; nNumberOfBytesToRead
0x18005d895  add     rdx, [rdi+6F0h]; lpBuffer
0x18005d89c  mov     [rsp+138h+lpOverlapped], r14; lpOverlapped
0x18005d8a1  lea     r9, [rsp+138h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005d8a6  mov     rcx, [rdi+0C8h]; hFile
0x18005d8ad  call    cs:__imp_ReadFile
0x18005d8b3  test    eax, eax
0x18005d8b5  jnz     short loc_18005D8C5
0x18005d8b7  call    cs:__imp_GetLastError
0x18005d8bd  mov     esi, eax
0x18005d8bf  test    eax, eax
0x18005d8c1  jz      short loc_18005D8D8
0x18005d8c3  jmp     short loc_18005D91B
0x18005d8c5  mov     ecx, [rsp+138h+NumberOfBytesRead]
0x18005d8c9  test    ecx, ecx
0x18005d8cb  jnz     short loc_18005D8D2
0x18005d8cd  mov     esi, r13d
0x18005d8d0  jmp     short loc_18005D91B
0x18005d8d2  add     [rdi+6F8h], ecx
0x18005d8d8  mov     eax, [rdi+6FCh]
0x18005d8de  lea     edx, [rax+2]
0x18005d8e1  cmp     edx, [rdi+6F8h]
0x18005d8e7  jbe     short loc_18005D8F4
0x18005d8e9  mov     r15d, 7Ah ; 'z'
0x18005d8ef  mov     esi, r15d
0x18005d8f2  jmp     short loc_18005D921
0x18005d8f4  mov     rcx, rax
0x18005d8f7  mov     rax, [rdi+6F0h]
0x18005d8fe  movzx   r12d, word ptr [rcx+rax]
0x18005d903  mov     [rdi+6FCh], edx
0x18005d909  mov     esi, r14d
0x18005d90c  mov     eax, 80h
0x18005d911  cmp     r12w, ax
0x18005d915  ja      loc_18005D7A2
0x18005d91b  mov     r15d, 7Ah ; 'z'
0x18005d921  test    r12w, r12w
0x18005d925  jz      short loc_18005D976
0x18005d927  test    esi, esi
0x18005d929  jnz     loc_18005D73C
0x18005d92f  movzx   ecx, r12w; unsigned __int64
0x18005d933  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005d938  mov     [rsp+138h+var_A8], rax
0x18005d940  movzx   ebx, r12w
0x18005d944  mov     r8d, ebx; unsigned int
0x18005d947  mov     rdx, rax; unsigned __int8 *
0x18005d94a  mov     rcx, rdi; this
0x18005d94d  call    ?ReadData@CCacheMigration@@AEAAKPEAEK@Z; CCacheMigration::ReadData(uchar *,ulong)
0x18005d952  mov     esi, eax
0x18005d954  mov     rcx, [rsp+138h+var_C0]; this
0x18005d959  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x18005d95e  mov     rax, [rsp+138h+var_A8]
0x18005d966  mov     rcx, [rsp+138h+var_C0]
0x18005d96b  mov     [rcx+10h], rax
0x18005d96f  mov     [rcx+8], ebx
0x18005d972  mov     byte ptr [rcx+18h], 1
0x18005d976  test    esi, esi
0x18005d978  jnz     loc_18005D73C
0x18005d97e  lea     ecx, [rsi+20h]; Size
0x18005d981  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005d986  mov     rcx, rax
0x18005d989  mov     [rsp+138h+var_A0], rax
0x18005d991  test    rax, rax
0x18005d994  jz      short loc_18005D9B6
0x18005d996  mov     [rax+8], r14d
0x18005d99a  mov     [rax+10h], r14
0x18005d99e  mov     byte ptr [rax+18h], 1
0x18005d9a2  lea     rax, ??_7TnoHoHoDk@@6B@; const TnoHoHoDk::`vftable'
0x18005d9a9  mov     [rcx], rax
0x18005d9ac  mov     [rsp+138h+var_88], rcx
0x18005d9b4  jmp     short loc_18005D9C9
0x18005d9b6  mov     rax, r14
0x18005d9b9  mov     [rsp+138h+var_A0], rax
0x18005d9c1  mov     [rsp+138h+var_88], rax
0x18005d9c9  mov     edx, [rdi+6F8h]
0x18005d9cf  mov     r9d, [rdi+6FCh]
0x18005d9d6  lea     eax, [r9+2]
0x18005d9da  cmp     eax, edx
0x18005d9dc  jbe     loc_18005DA67
0x18005d9e2  mov     [rsp+138h+NumberOfBytesRead], r14d
0x18005d9e7  test    r9d, r9d
0x18005d9ea  jz      short loc_18005DA1B
0x18005d9ec  mov     rcx, [rdi+6F0h]; void *
0x18005d9f3  sub     edx, r9d
0x18005d9f6  mov     r8d, edx; Size
0x18005d9f9  lea     rdx, [rcx+r9]; Src
  ... truncated ...
```
