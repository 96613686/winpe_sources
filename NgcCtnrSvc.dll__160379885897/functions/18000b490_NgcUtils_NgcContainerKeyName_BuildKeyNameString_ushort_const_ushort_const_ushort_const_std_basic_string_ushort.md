# NgcUtils::NgcContainerKeyName::BuildKeyNameString(ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18000b490`
- end: `0x18000c1c9`
- name: `?BuildKeyNameString@NgcContainerKeyName@NgcUtils@@YAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `3385`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `21`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x18000addc`
- `0x18000cd38`
- `0x18000e230`
- `0x18000eaac`
- `0x18000ec9c`
- `0x180015810`
- `0x180022530`
- `0x180022748`
- `0x18002295c`
- `0x180048850`
- `0x180048dd0`
- `0x180049018`
- `0x180049a1c`
- `0x180049c30`
- `0x180049e78`
- `0x18004ad54`
- `0x18004af44`
- `0x18004b284`
- `0x18004b584`
- `0x18004b7d4`
- `0x18004ba88`

## callees

- `0x18000a8e0`
- `0x18000b490`
- `0x18000cab0`
- `0x180025634`
- `0x180029488`
- `0x18002c640`
- `0x18002cae0`
- `0x18002cdec`
- `0x18002d500`
- `0x18002d50c`
- `0x1800343f4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c0bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c185`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c0bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c185`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::NgcContainerKeyName::BuildKeyNameString(_WORD *Src, void *a2, void *a3, __int64 a4)
{
  _WORD *v5; // r9
  __int64 v6; // rcx
  _WORD *v7; // rax
  struct _EVENT_DATA_DESCRIPTOR *p_UserData; // rax
  unsigned __int64 v9; // r8
  __int64 v10; // rcx
  _WORD *v11; // rax
  __int16 *v12; // rax
  unsigned __int64 v13; // rdx
  __int64 v14; // rcx
  _WORD *v15; // rax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // rsi
  __int64 v22; // r15
  size_t v23; // rcx
  void *v24; // rax
  _WORD *v25; // r14
  unsigned __int64 v26; // rbx
  void **v27; // rdi
  size_t v28; // rbx
  size_t v29; // r12
  char *v30; // rdi
  unsigned __int64 v31; // rcx
  size_t v32; // rcx
  void *v33; // rax
  unsigned __int64 v34; // rdx
  _BYTE *v35; // rcx
  void **v36; // rax
  unsigned __int64 v37; // r12
  void *v38; // rax
  char *v39; // rsi
  size_t v40; // r14
  size_t v41; // rcx
  size_t v42; // rcx
  void *v43; // rax
  size_t v44; // rbx
  unsigned __int64 v45; // rdx
  _BYTE *v46; // rcx
  unsigned __int64 v47; // r14
  char *v48; // rdi
  void **v49; // rbx
  char *v50; // rdi
  unsigned __int64 v51; // rbx
  unsigned __int64 v52; // rcx
  size_t v53; // rcx
  char *v54; // rbx
  void *v55; // rax
  size_t v56; // r8
  unsigned __int64 v57; // r14
  unsigned __int64 v58; // rdx
  _BYTE *v59; // rcx
  void **v60; // rax
  unsigned __int64 v61; // r13
  char *v62; // rbx
  void *v63; // r14
  unsigned __int64 v64; // rcx
  size_t v65; // rcx
  void *v66; // rax
  size_t v67; // r8
  unsigned __int64 v68; // rdx
  _BYTE *v69; // rcx
  unsigned __int64 v70; // rsi
  char *v71; // rdi
  void **v72; // rbx
  unsigned __int64 v73; // r12
  unsigned __int64 v74; // rcx
  __int64 v75; // rdx
  size_t v76; // rax
  _QWORD *v77; // rbx
  void *v78; // rax
  size_t v79; // r8
  size_t v80; // rsi
  char *v81; // r15
  unsigned __int64 v82; // rdx
  void *v83; // rcx
  char *v85; // [rsp+30h] [rbp-A9h] BYREF
  size_t Size; // [rsp+38h] [rbp-A1h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-99h] BYREF
  void *v88; // [rsp+50h] [rbp-89h]
  void *v89; // [rsp+58h] [rbp-81h]
  void *v90; // [rsp+60h] [rbp-79h]
  unsigned __int64 v91; // [rsp+68h] [rbp-71h]
  unsigned __int64 v92; // [rsp+70h] [rbp-69h]
  unsigned __int64 v93; // [rsp+78h] [rbp-61h]
  unsigned __int64 v94; // [rsp+80h] [rbp-59h]
  void *Srca[2]; // [rsp+88h] [rbp-51h] BYREF
  char *v96; // [rsp+98h] [rbp-41h]
  size_t v97; // [rsp+A0h] [rbp-39h]
  size_t *p_Size; // [rsp+A8h] [rbp-31h]
  __int64 v99; // [rsp+B0h] [rbp-29h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B8h] [rbp-21h] BYREF
  char *v101; // [rsp+C8h] [rbp-11h]
  int v102; // [rsp+D0h] [rbp-9h]
  int v103; // [rsp+D4h] [rbp-5h]
  char **v104; // [rsp+D8h] [rbp-1h]
  __int64 v105; // [rsp+E0h] [rbp+7h]

  *(_QWORD *)&EventDescriptor.Id = a4;
  v90 = a3;
  v88 = a2;
  v5 = Src;
  v85 = (char *)Src;
  if ( Src && a3 )
  {
    v6 = 0x7FFFFFFF;
    v7 = v5;
    while ( *v7 )
    {
      ++v7;
      if ( !--v6 )
      {
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          LODWORD(Size) = -2147024809;
          p_Size = &Size;
          v99 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 2;
          EventDescriptor.Keyword = 0;
          Srca[0] = off_1800BE0C0;
          Srca[1] = (void *)(*(unsigned __int16 *)off_1800BE0C0 | 0x200000000LL);
          v96 = byte_1800AE453;
          v97 = 0x100000033LL;
          LODWORD(v85) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          p_UserData = (struct _EVENT_DATA_DESCRIPTOR *)Srca;
          goto LABEL_188;
        }
        return 2147942487LL;
      }
    }
    v9 = 0x7FFFFFFF - v6;
    v91 = 0x7FFFFFFF - v6;
    if ( a2 )
    {
      v10 = 0x7FFFFFFF;
      v11 = a2;
      while ( *v11 )
      {
        ++v11;
        if ( !--v10 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 2 )
          {
            LODWORD(v85) = -2147024809;
            p_Size = (size_t *)&v85;
            v99 = 4;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            *(_DWORD *)&EventDescriptor.Level = 2;
            EventDescriptor.Keyword = 0;
            Srca[0] = off_1800BE0C0;
            LODWORD(Srca[1]) = *(unsigned __int16 *)off_1800BE0C0;
            v12 = word_1800AE492;
            LODWORD(v97) = 51;
            goto LABEL_14;
          }
          return 2147942487LL;
        }
      }
      v13 = 0x7FFFFFFF - v10;
    }
    else
    {
      v13 = 0;
      v91 = 0x7FFFFFFF - v6;
    }
    v92 = v13;
    v14 = 0x7FFFFFFF;
    v15 = a3;
    while ( *v15 )
    {
      ++v15;
      if ( !--v14 )
      {
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          LODWORD(v85) = -2147024809;
          p_Size = (size_t *)&v85;
          v99 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 2;
          EventDescriptor.Keyword = 0;
          Srca[0] = off_1800BE0C0;
          LODWORD(Srca[1]) = *(unsigned __int16 *)off_1800BE0C0;
          v12 = (__int16 *)byte_1800AE355;
          LODWORD(v97) = 54;
LABEL_14:
          v96 = (char *)v12;
          HIDWORD(Srca[1]) = 2;
          HIDWORD(v97) = 1;
          LODWORD(Size) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          p_UserData = (struct _EVENT_DATA_DESCRIPTOR *)Srca;
LABEL_188:
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, p_UserData);
        }
        return 2147942487LL;
      }
    }
    v16 = v9 + 1;
    if ( v9 + 1 < v9
      || (v17 = v16 + v13, v17 < v16)
      || (v18 = v17 + 1, v17 + 1 < v17)
      || (v94 = 0x7FFFFFFF - v14, v19 = v18 + 0x7FFFFFFF - v14, v19 < v18)
      || (v20 = v19 + 1, v19 + 1 < v19) )
    {
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v14);
    }
    *(_OWORD *)Srca = 0;
    v96 = 0;
    v21 = 7;
    v97 = 7;
    LOWORD(Srca[0]) = 0;
    v22 = 0x7FFFFFFFFFFFFFFELL;
    if ( v20 <= 7 )
    {
      v25 = Srca[0];
      goto LABEL_44;
    }
    if ( v20 > 0x7FFFFFFFFFFFFFFELL )
      goto LABEL_192;
    v21 = v20 | 7;
    if ( (v20 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      if ( v21 < 0xA )
        v21 = 10;
      if ( v21 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_191;
      v23 = 2 * (v21 + 1);
      if ( !v23 )
      {
        v25 = 0;
LABEL_42:
        v97 = v21;
        *v25 = 0;
        Srca[0] = v25;
        v96 = 0;
LABEL_44:
        v26 = -1;
        do
          ++v26;
        while ( v5[v26] );
        if ( v26 <= v21 )
        {
          v96 = (char *)v26;
          v27 = Srca;
          if ( v21 > 7 )
            v27 = (void **)v25;
          v28 = 2 * v26;
          memmove_0(v27, v5, v28);
          *(_WORD *)((char *)v27 + v28) = 0;
          v29 = v97;
          Size = v97;
          v26 = (unsigned __int64)v96;
          v30 = (char *)Srca[0];
          goto LABEL_72;
        }
        if ( v26 > 0x7FFFFFFFFFFFFFFELL )
          goto LABEL_192;
        v29 = v26 | 7;
        if ( (v26 | 7) > 0x7FFFFFFFFFFFFFFELL || (v31 = v21 >> 1, v21 > 0x7FFFFFFFFFFFFFFELL - (v21 >> 1)) )
        {
          v29 = 0x7FFFFFFFFFFFFFFELL;
          Size = 0x7FFFFFFFFFFFFFFELL;
          v32 = -2;
        }
        else
        {
          if ( v29 < v21 + v31 )
            v29 = v21 + v31;
          Size = v29;
          if ( v29 + 1 > 0x7FFFFFFFFFFFFFFFLL )
            goto LABEL_191;
          v32 = 2 * (v29 + 1);
          if ( !v32 )
          {
            v30 = 0;
LABEL_65:
            v96 = (char *)v26;
            v97 = v29;
            v85 = &v30[2 * v26];
            memcpy_0(v30, v5, 2 * v26);
            *(_WORD *)v85 = 0;
            if ( v21 > 7 )
            {
              v34 = 2 * v21 + 2;
              if ( v34 < 0x1000 )
              {
                v35 = v25;
              }
              else
              {
                v35 = (_BYTE *)*((_QWORD *)v25 - 1);
                if ( (unsigned __int64)((char *)v25 - v35 - 8) > 0x1F )
                  goto LABEL_174;
                v34 = 2 * v21 + 41;
              }
              operator delete(v35, v34);
            }
            Srca[0] = v30;
LABEL_72:
            if ( v26 < v29 )
            {
              v96 = (char *)(v26 + 1);
              v36 = Srca;
              if ( v29 > 7 )
                v36 = (void **)v30;
              *(_DWORD *)((char *)v36 + 2 * v26) = 47;
              v37 = v97;
              v38 = v96;
              v85 = v96;
              v39 = (char *)Srca[0];
              goto LABEL_97;
            }
            if ( v26 == 0x7FFFFFFFFFFFFFFELL )
              goto LABEL_192;
            v85 = (char *)(v26 + 1);
            v37 = (v26 + 1) | 7;
            v40 = Size;
            if ( v37 > 0x7FFFFFFFFFFFFFFELL || (v41 = Size >> 1, Size > 0x7FFFFFFFFFFFFFFELL - (Size >> 1)) )
            {
              v37 = 0x7FFFFFFFFFFFFFFELL;
              v42 = -2;
            }
            else
            {
              if ( v37 < Size + v41 )
                v37 = Size + v41;
              if ( v37 + 1 > 0x7FFFFFFFFFFFFFFFLL )
                goto LABEL_191;
              v42 = 2 * (v37 + 1);
              if ( !v42 )
              {
                v39 = 0;
LABEL_90:
                v96 = (char *)(v26 + 1);
                v97 = v37;
                v44 = 2 * v26;
                if ( v40 <= 7 )
                {
                  memcpy_0(v39, Srca, v44);
                  *(_DWORD *)&v39[v44] = 47;
                }
                else
                {
                  memcpy_0(v39, v30, v44);
                  *(_DWORD *)&v39[v44] = 47;
                  v45 = 2 * v40 + 2;
                  if ( v45 < 0x1000 )
                  {
                    operator delete(v30, v45);
                  }
                  else
                  {
                    v46 = (_BYTE *)*((_QWORD *)v30 - 1);
                    if ( (unsigned __int64)(v30 - v46 - 8) > 0x1F )
                      goto LABEL_174;
                    operator delete(v46, 2 * v40 + 41);
                  }
                }
                v38 = v85;
                Srca[0] = v39;
LABEL_97:
                if ( !v88 )
                {
                  v50 = v85;
                  goto LABEL_125;
                }
                v47 = -1;
                do
                  ++v47;
                while ( *((_WORD *)v88 + v47) );
                v89 = v38;
                if ( v47 <= v37 - (unsigned __int64)v38 )
                {
                  v48 = (char *)v38 + v47;
                  v96 = (char *)v38 + v47;
                  v49 = Srca;
                  if ( v37 > 7 )
                    v49 = (void **)v39;
                  memmove_0((char *)v49 + 2 * (_QWORD)v38, v88, 2 * v47);
                  *((_WORD *)v49 + (_QWORD)v48) = 0;
                  v37 = v97;
                  v50 = v96;
                  v85 = v96;
                  v39 = (char *)Srca[0];
                  goto LABEL_125;
                }
                if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v38 < v47 )
                  goto LABEL_192;
                v50 = (char *)v38 + v47;
                v85 = (char *)v38 + v47;
                v51 = v37;
                v93 = v37;
                v37 = ((unsigned __int64)v38 + v47) | 7;
                if ( v37 > 0x7FFFFFFFFFFFFFFELL || (v52 = v51 >> 1, v51 > 0x7FFFFFFFFFFFFFFELL - (v51 >> 1)) )
                {
                  v37 = 0x7FFFFFFFFFFFFFFELL;
                  v53 = -2;
                }
                else
                {
                  if ( v37 < v51 + v52 )
                    v37 = v51 + v52;
                  if ( v37 + 1 > 0x7FFFFFFFFFFFFFFFLL )
                    goto LABEL_191;
                  v53 = 2 * (v37 + 1);
                  if ( !v53 )
                  {
                    v54 = 0;
LABEL_118:
                    v96 = v50;
                    v97 = v37;
                    v56 = 2LL * (_QWORD)v89;
                    Size = 2 * v47;
                    v89 = &v54[2 * (_QWORD)v89];
                    v57 = v93;
                    if ( v93 <= 7 )
                    {
                      memcpy_0(v54, Srca, v56);
                      memcpy_0(v89, v88, Size);
                      *(_WORD *)&v54[2 * (_QWORD)v50] = 0;
                      v39 = v54;
                      Srca[0] = v54;
                    }
                    else
                    {
                      memcpy_0(v54, v39, v56);
                      memcpy_0(v89, v88, Size);
                      *(_WORD *)&v54[2 * (_QWORD)v50] = 0;
                      v58 = 2 * v57 + 2;
                      if ( v58 < 0x1000 )
                      {
                        operator delete(v39, v58);
                        v39 = v54;
                        Srca[0] = v54;
                      }
                      else
                      {
                        v59 = (_BYTE *)*((_QWORD *)v39 - 1);
                        if ( (unsigned __int64)(v39 - v59 - 8) > 0x1F )
                          goto LABEL_174;
                        operator delete(v59, 2 * v57 + 41);
                        v39 = v54;
                        Srca[0] = v54;
                      }
                    }
LABEL_125:
                    if ( (unsigned __int64)v50 < v37 )
                    {
                      v96 = v50 + 1;
                      v60 = Srca;
                      if ( v37 > 7 )
                        v60 = (void **)v39;
                      *(_DWORD *)((char *)v60 + 2 * (_QWORD)v50) = 47;
                      v61 = v97;
                      v62 = v96;
                      v88 = v96;
                      v63 = Srca[0];
                      goto LABEL_150;
                    }
                    if ( v50 == (char *)0x7FFFFFFFFFFFFFFELL )
                      goto LABEL_192;
                    v62 = v50 + 1;
                    v88 = v50 + 1;
                    v61 = (unsigned __int64)(v50 + 1) | 7;
                    if ( v61 > 0x7FFFFFFFFFFFFFFELL || (v64 = v37 >> 1, v37 > 0x7FFFFFFFFFFFFFFELL - (v37 >> 1)) )
                    {
                      v61 = 0x7FFFFFFFFFFFFFFELL;
                      v65 = -2;
                    }
                    else
                    {
                      if ( v61 < v37 + v64 )
                        v61 = v37 + v64;
                      if ( v61 + 1 > 0x7FFFFFFFFFFFFFFFLL )
                        goto LABEL_191;
                      v65 = 2 * (v61 + 1);
                      if ( !v65 )
                      {
                        v63 = 0;
LABEL_143:
                        v96 = v50 + 1;
                        v97 = v61;
                        v89 = (void *)(2LL * (_QWORD)v85);
                        v67 = 2LL * (_QWORD)v85;
                        if ( v37 <= 7 )
                        {
                          memcpy_0(v63, Srca, v67);
                          *(_DWORD *)((char *)v89 + (_QWORD)v63) = 47;
                        }
                        else
                        {
                          memcpy_0(v63, v39, v67);
                          *(_DWORD *)((char *)v89 + (_QWORD)v63) = 47;
                          v68 = 2 * v37 + 2;
                          if ( v68 < 0x1000 )
                          {
                            operator delete(v39, v68);
                          }
                          else
                          {
                            v69 = (_BYTE *)*((_QWORD *)v39 - 1);
                            if ( (unsigned __int64)(v39 - v69 - 8) > 0x1F )
                              goto LABEL_174;
                            operator delete(v69, 2 * v37 + 41);
                          }
                        }
                        Srca[0] = v63;
LABEL_150:
                        v70 = -1;
                        do
                          ++v70;
                        while ( *((_WORD *)v90 + v70) );
                        if ( v70 <= v61 - (unsigned __int64)v62 )
                        {
                          v71 = &v62[v70];
                          v96 = &v62[v70];
                          v72 = Srca;
                          if ( v61 > 7 )
                            v72 = (void **)v63;
                          memmove_0((char *)v72 + 2 * (_QWORD)v88, v90, 2 * v70);
                          *((_WORD *)v72 + (_QWORD)v71) = 0;
                          v73 = (unsigned __int64)v96;
                          goto LABEL_178;
                        }
                        if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v62 >= v70 )
                        {
                          v73 = (unsigned __int64)&v62[v70];
                          v74 = (unsigned __int64)&v62[v70] | 7;
                          if ( v74 > 0x7FFFFFFFFFFFFFFELL || (v75 = v61 >> 1, v61 > 0x7FFFFFFFFFFFFFFELL - (v61 >> 1)) )
                          {
                            v76 = -2;
                          }
                          else
                          {
                            v22 = (unsigned __int64)&v62[v70] | 7;
                            if ( v74 < v75 + v61 )
                              v22 = v75 + v61;
                            if ( (unsigned __int64)(v22 + 1) > 0x7FFFFFFFFFFFFFFFLL )
                              goto LABEL_191;
                            v76 = 2 * (v22 + 1);
                            if ( !v76 )
                            {
                              v77 = 0;
                              goto LABEL_170;
                            }
                          }
                          if ( v76 < 0x1000 )
                          {
                            v77 = operator new(v76);
                            goto LABEL_170;
                          }
                          if ( v76 + 39 >= v76 )
                          {
                            v78 = operator new(v76 + 39);
                            if ( !v78 )
                              goto LABEL_174;
                            v77 = (_QWORD *)(((unsigned __int64)v78 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                            *(v77 - 1) = v78;
LABEL_170:
                            v96 = (char *)v73;
                            v97 = v22;
                            v79 = 2LL * (_QWORD)v88;
                            v80 = 2 * v70;
                            v81 = (char *)v77 + 2 * (_QWORD)v88;
                            if ( v61 <= 7 )
                            {
                              memcpy_0(v77, Srca, v79);
                              memcpy_0(v81, v90, v80);
                              *((_WORD *)v77 + v73) = 0;
                              goto LABEL_177;
                            }
                            memcpy_0(v77, v63, v79);
                            memcpy_0(v81, v90, v80);
                            *((_WORD *)v77 + v73) = 0;
                            v82 = 2 * v61 + 2;
                            if ( v82 < 0x1000 )
                            {
                              operator delete(v63, v82);
                              goto LABEL_177;
                            }
                            v83 = (void *)*((_QWORD *)v63 - 1);
                            if ( (unsigned __int64)((_BYTE *)v63 - (_BYTE *)v83 - 8) <= 0x1F )
                            {
                              operator delete(v83, 2 * v61 + 41);
LABEL_177:
                              Srca[0] = v77;
LABEL_178:
                              if ( v91 > 0x104 || v92 > 0x104 || v94 > 0x104 || v73 > 0x433 )
                              {
                                if ( (unsigned int)dword_1800BE0B8 > 2 )
                                {
                                  LODWORD(v85) = -2147024809;
                                  v104 = &v85;
                                  v105 = 4;
                                  *(_DWORD *)&EventDescriptor.Id = 184549376;
                                  *(_DWORD *)&EventDescriptor.Level = 2;
                                  EventDescriptor.Keyword = 0;
                                  UserData.Ptr = (ULONGLONG)off_1800BE0C0;
                                  UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
                                  UserData.Reserved = 2;
                                  v101 = &byte_1800AE397;
                                  v102 = 55;
                                  v103 = 1;
                                  LODWORD(Size) = (unsigned int)&TraceLoggingMetadataEnd
                                                - (unsigned int)&TraceLoggingMetadata;
                                  EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
                                }
                                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Srca);
                                return 2147942487LL;
                              }
                              std::wstring::operator=(*(_QWORD *)&EventDescriptor.Id, Srca);
                              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Srca);
                              return 0;
                            }
LABEL_174:
                            __fastfail(5u);
                          }
LABEL_191:
                          std::_Throw_bad_array_new_length();
                        }
LABEL_192:
                        std::_Xlen_string();
                      }
                    }
                    if ( v65 < 0x1000 )
                    {
                      v63 = operator new(v65);
                    }
                    else
                    {
                      if ( v65 + 39 < v65 )
                        goto LABEL_191;
                      v66 = operator new(v65 + 39);
                      if ( !v66 )
                        goto LABEL_174;
                      v63 = (void *)(((unsigned __int64)v66 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                      *((_QWORD *)v63 - 1) = v66;
                    }
                    goto LABEL_143;
                  }
                }
                if ( v53 < 0x1000 )
                {
                  v54 = (char *)operator new(v53);
                }
                else
                {
                  if ( v53 + 39 < v53 )
                    goto LABEL_191;
                  v55 = operator new(v53 + 39);
                  if ( !v55 )
                    goto LABEL_174;
                  v54 = (char *)(((unsigned __int64)v55 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                  *((_QWORD *)v54 - 1) = v55;
                }
                goto LABEL_118;
              }
            }
            if ( v42 < 0x1000 )
            {
              v39 = (char *)operator new(v42);
            }
            else
            {
              if ( v42 + 39 < v42 )
                goto LABEL_191;
              v43 = operator new(v42 + 39);
              if ( !v43 )
                goto LABEL_174;
              v39 = (char *)(((unsigned __int64)v43 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v39 - 1) = v43;
            }
            goto LABEL_90;
          }
        }
        if ( v32 < 0x1000 )
        {
          v30 = (char *)operator new(v32);
        }
        else
        {
          if ( v32 + 39 < v32 )
            goto LABEL_191;
          v33 = operator new(v32 + 39);
          if ( !v33 )
            goto LABEL_174;
          v30 = (char *)(((unsigned __int64)v33 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v30 - 1) = v33;
        }
        v5 = v85;
        goto LABEL_65;
      }
    }
    else
    {
      v21 = 0x7FFFFFFFFFFFFFFELL;
      v23 = -2;
    }
    if ( v23 < 0x1000 )
    {
      v25 = operator new(v23);
    }
    else
    {
      if ( v23 + 39 < v23 )
        goto LABEL_191;
      v24 = operator new(v23 + 39);
      if ( !v24 )
        goto LABEL_174;
      v25 = (_WORD *)(((unsigned __int64)v24 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *((_QWORD *)v25 - 1) = v24;
    }
    v5 = v85;
    goto LABEL_42;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    LODWORD(v85) = -2147024809;
    v104 = &v85;
    v105 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_1800BE0C0;
    UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
    UserData.Reserved = 2;
    v101 = byte_1800AE4D1;
    v102 = 57;
    v103 = 1;
    LODWORD(Size) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    p_UserData = &UserData;
    goto LABEL_188;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000b490  push    rbp
0x18000b492  push    rbx
0x18000b493  push    rsi
0x18000b494  push    rdi
0x18000b495  push    r12
0x18000b497  push    r13
0x18000b499  push    r14
0x18000b49b  push    r15
0x18000b49d  lea     rbp, [rsp-1Fh]
0x18000b4a2  sub     rsp, 0F8h
0x18000b4a9  mov     rax, cs:__security_cookie
0x18000b4b0  xor     rax, rsp
0x18000b4b3  mov     [rbp+57h+var_48], rax
0x18000b4b7  mov     qword ptr [rsp+130h+EventDescriptor.Id], r9
0x18000b4bc  mov     r11, r8
0x18000b4bf  mov     [rbp+57h+var_D0], r8
0x18000b4c3  mov     [rsp+130h+var_E0], rdx
0x18000b4c8  mov     r9, rcx
0x18000b4cb  mov     [rsp+130h+var_100], rcx
0x18000b4d0  test    rcx, rcx
0x18000b4d3  jz      loc_18000C0D7
0x18000b4d9  test    r8, r8
0x18000b4dc  jz      loc_18000C0D7
0x18000b4e2  mov     r10d, 7FFFFFFFh
0x18000b4e8  mov     ecx, r10d
0x18000b4eb  mov     rax, r9
0x18000b4ee  xchg    ax, ax
0x18000b4f0  cmp     word ptr [rax], 0
0x18000b4f4  jz      loc_18000B596
0x18000b4fa  add     rax, 2
0x18000b4fe  sub     rcx, 1
0x18000b502  jnz     short loc_18000B4F0
0x18000b504  mov     eax, cs:dword_1800BE0B8
0x18000b50a  cmp     eax, 2
0x18000b50d  jbe     loc_18000C191
0x18000b513  mov     dword ptr [rsp+130h+Size], 80070057h
0x18000b51b  lea     rax, [rsp+130h+Size]
0x18000b520  mov     [rbp+57h+var_88], rax
0x18000b524  mov     [rbp+57h+var_80], 4
0x18000b52c  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x18000b534  movzx   eax, cs:word_1800AE449
0x18000b53b  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x18000b53f  mov     [rsp+130h+EventDescriptor.Keyword], rcx
0x18000b544  mov     rax, cs:off_1800BE0C0
0x18000b54b  mov     [rbp+57h+Src], rax
0x18000b54f  movzx   eax, word ptr [rax]
0x18000b552  mov     dword ptr [rbp+57h+Src+8], eax
0x18000b555  mov     dword ptr [rbp+57h+Src+0Ch], 2
0x18000b55c  lea     rax, byte_1800AE453
0x18000b563  mov     [rbp+57h+var_98], rax
0x18000b567  mov     dword ptr [rbp+57h+var_90], 33h ; '3'
0x18000b56e  mov     dword ptr [rbp+57h+var_90+4], 1
0x18000b575  lea     rax, _TraceLoggingMetadataEnd
0x18000b57c  lea     rcx, _TraceLoggingMetadata
0x18000b583  sub     eax, ecx
0x18000b585  mov     dword ptr [rsp+130h+var_100], eax
0x18000b589  mov     eax, dword ptr [rsp+130h+var_100]
0x18000b58d  lea     rax, [rbp+57h+Src]
0x18000b591  jmp     loc_18000C166
0x18000b596  mov     r8, r10
0x18000b599  sub     r8, rcx
0x18000b59c  mov     [rbp+57h+var_C8], r8
0x18000b5a0  xor     r13d, r13d
0x18000b5a3  test    rdx, rdx
0x18000b5a6  jz      loc_18000B660
0x18000b5ac  mov     rcx, r10
0x18000b5af  mov     rax, rdx
0x18000b5b2  cmp     [rax], r13w
0x18000b5b6  jz      loc_18000B658
0x18000b5bc  add     rax, 2
0x18000b5c0  sub     rcx, 1
0x18000b5c4  jnz     short loc_18000B5B2
0x18000b5c6  mov     eax, cs:dword_1800BE0B8
0x18000b5cc  cmp     eax, 2
0x18000b5cf  jbe     loc_18000C191
0x18000b5d5  mov     dword ptr [rsp+130h+var_100], 80070057h
0x18000b5dd  lea     rax, [rsp+130h+var_100]
0x18000b5e2  mov     [rbp+57h+var_88], rax
0x18000b5e6  mov     [rbp+57h+var_80], 4
0x18000b5ee  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x18000b5f6  movzx   eax, cs:word_1800AE488
0x18000b5fd  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x18000b601  mov     [rsp+130h+EventDescriptor.Keyword], r13
0x18000b606  mov     rax, cs:off_1800BE0C0
0x18000b60d  mov     [rbp+57h+Src], rax
0x18000b611  movzx   eax, word ptr [rax]
0x18000b614  mov     dword ptr [rbp+57h+Src+8], eax
0x18000b617  lea     rax, word_1800AE492
0x18000b61e  mov     dword ptr [rbp+57h+var_90], 33h ; '3'
0x18000b625  mov     [rbp+57h+var_98], rax
0x18000b629  mov     dword ptr [rbp+57h+Src+0Ch], 2
0x18000b630  mov     dword ptr [rbp+57h+var_90+4], 1
0x18000b637  lea     rax, _TraceLoggingMetadataEnd
0x18000b63e  lea     rcx, _TraceLoggingMetadata
0x18000b645  sub     eax, ecx
0x18000b647  mov     dword ptr [rsp+130h+Size], eax
0x18000b64b  mov     eax, dword ptr [rsp+130h+Size]
0x18000b64f  lea     rax, [rbp+57h+Src]
0x18000b653  jmp     loc_18000C166
0x18000b658  mov     rdx, r10
0x18000b65b  sub     rdx, rcx
0x18000b65e  jmp     short loc_18000B667
0x18000b660  mov     rdx, r13
0x18000b663  mov     [rbp+57h+var_C8], r8
0x18000b667  mov     [rbp+57h+var_C0], rdx
0x18000b66b  mov     rcx, r10
0x18000b66e  mov     rax, r11
0x18000b671  cmp     [rax], r13w
0x18000b675  jz      short loc_18000B6E5
0x18000b677  add     rax, 2
0x18000b67b  sub     rcx, 1
0x18000b67f  jnz     short loc_18000B671
0x18000b681  mov     eax, cs:dword_1800BE0B8
0x18000b687  cmp     eax, 2
0x18000b68a  jbe     loc_18000C191
0x18000b690  mov     dword ptr [rsp+130h+var_100], 80070057h
0x18000b698  lea     rax, [rsp+130h+var_100]
0x18000b69d  mov     [rbp+57h+var_88], rax
0x18000b6a1  mov     [rbp+57h+var_80], 4
0x18000b6a9  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x18000b6b1  movzx   eax, cs:word_1800AE34B
0x18000b6b8  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x18000b6bc  mov     [rsp+130h+EventDescriptor.Keyword], r13
0x18000b6c1  mov     rax, cs:off_1800BE0C0
0x18000b6c8  mov     [rbp+57h+Src], rax
0x18000b6cc  movzx   eax, word ptr [rax]
0x18000b6cf  mov     dword ptr [rbp+57h+Src+8], eax
0x18000b6d2  lea     rax, byte_1800AE355
0x18000b6d9  mov     dword ptr [rbp+57h+var_90], 36h ; '6'
0x18000b6e0  jmp     loc_18000B625
0x18000b6e5  lea     rax, [r8+1]
0x18000b6e9  cmp     rax, r8
0x18000b6ec  jb      loc_18000C1B7
0x18000b6f2  add     rdx, rax
0x18000b6f5  cmp     rdx, rax
0x18000b6f8  jb      loc_18000C1B7
0x18000b6fe  lea     r8, [rdx+1]
0x18000b702  cmp     r8, rdx
0x18000b705  jb      loc_18000C1B7
0x18000b70b  sub     r10, rcx
0x18000b70e  mov     [rbp+57h+var_B0], r10
0x18000b712  lea     rax, [r8+r10]
0x18000b716  cmp     rax, r8
0x18000b719  jb      loc_18000C1B7
0x18000b71f  lea     rbx, [rax+1]
0x18000b723  cmp     rbx, rax
0x18000b726  jb      loc_18000C1B7
0x18000b72c  xorps   xmm0, xmm0
0x18000b72f  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18000b733  mov     [rbp+57h+var_98], r13
0x18000b737  mov     esi, 7
0x18000b73c  mov     [rbp+57h+var_90], rsi
0x18000b740  mov     word ptr [rbp+57h+Src], r13w
0x18000b745  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x18000b74c  mov     r15, 7FFFFFFFFFFFFFFEh
0x18000b756  mov     r8, 7FFFFFFFFFFFFFFFh
0x18000b760  cmp     rbx, rsi
0x18000b763  jbe     loc_18000B80C
0x18000b769  cmp     rbx, r15
0x18000b76c  ja      loc_18000C1C3
0x18000b772  mov     rsi, rbx
0x18000b775  or      rsi, 7
0x18000b779  cmp     rsi, r15
0x18000b77c  jbe     short loc_18000B7B9
0x18000b77e  mov     rsi, r15
0x18000b781  mov     rcx, rdx; Size
0x18000b784  cmp     rcx, 1000h
0x18000b78b  jb      short loc_18000B7DC
0x18000b78d  lea     rax, [rcx+27h]
0x18000b791  cmp     rax, rcx
0x18000b794  jbe     loc_18000C1BD
0x18000b79a  mov     rcx, rax; Size
0x18000b79d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b7a2  test    rax, rax
0x18000b7a5  jz      loc_18000BF98
0x18000b7ab  lea     r14, [rax+27h]
0x18000b7af  and     r14, 0FFFFFFFFFFFFFFE0h
0x18000b7b3  mov     [r14-8], rax
0x18000b7b7  jmp     short loc_18000B7E4
0x18000b7b9  mov     eax, 0Ah
0x18000b7be  cmp     rsi, rax
0x18000b7c1  cmovb   rsi, rax
0x18000b7c5  lea     rcx, [rsi+1]
0x18000b7c9  cmp     rcx, r8
0x18000b7cc  ja      loc_18000C1BD
0x18000b7d2  add     rcx, rcx
0x18000b7d5  jnz     short loc_18000B784
0x18000b7d7  mov     r14, r13
0x18000b7da  jmp     short loc_18000B7FA
0x18000b7dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b7e1  mov     r14, rax
0x18000b7e4  mov     r8, 7FFFFFFFFFFFFFFFh
0x18000b7ee  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x18000b7f5  mov     r9, [rsp+130h+var_100]
0x18000b7fa  mov     [rbp+57h+var_90], rsi
0x18000b7fe  mov     [r14], r13w
0x18000b802  mov     [rbp+57h+Src], r14
0x18000b806  mov     [rbp+57h+var_98], r13
0x18000b80a  jmp     short loc_18000B810
0x18000b80c  mov     r14, [rbp+57h+Src]
0x18000b810  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b817  nop     word ptr [rax+rax+00000000h]
0x18000b820  inc     rbx
0x18000b823  cmp     word ptr [r9+rbx*2], 0
0x18000b829  jnz     short loc_18000B820
0x18000b82b  cmp     rbx, rsi
0x18000b82e  ja      short loc_18000B86C
0x18000b830  mov     [rbp+57h+var_98], rbx
0x18000b834  lea     rdi, [rbp+57h+Src]
0x18000b838  cmp     rsi, 7
0x18000b83c  cmova   rdi, r14
0x18000b840  add     rbx, rbx
0x18000b843  mov     r8, rbx; Size
0x18000b846  mov     rdx, r9; Src
0x18000b849  mov     rcx, rdi; void *
0x18000b84c  call    memmove_0
0x18000b851  mov     [rbx+rdi], r13w
0x18000b856  mov     r12, [rbp+57h+var_90]
0x18000b85a  mov     [rsp+130h+Size], r12
0x18000b85f  mov     rbx, [rbp+57h+var_98]
0x18000b863  mov     rdi, [rbp+57h+Src]
0x18000b867  jmp     loc_18000B96E
0x18000b86c  cmp     rbx, r15
0x18000b86f  ja      loc_18000C1C3
0x18000b875  mov     r12, rbx
0x18000b878  or      r12, 7
0x18000b87c  cmp     r12, r15
0x18000b87f  ja      short loc_18000B8BA
0x18000b881  mov     rcx, rsi
0x18000b884  shr     rcx, 1
0x18000b887  mov     rax, r15
0x18000b88a  sub     rax, rcx
0x18000b88d  cmp     rsi, rax
0x18000b890  ja      short loc_18000B8BA
0x18000b892  lea     rax, [rsi+rcx]
0x18000b896  cmp     r12, rax
0x18000b899  cmovb   r12, rax
0x18000b89d  mov     [rsp+130h+Size], r12
0x18000b8a2  lea     rcx, [r12+1]
0x18000b8a7  cmp     rcx, r8
0x18000b8aa  ja      loc_18000C1BD
0x18000b8b0  add     rcx, rcx
0x18000b8b3  jnz     short loc_18000B8C5
0x18000b8b5  mov     rdi, r13
0x18000b8b8  jmp     short loc_18000B907
0x18000b8ba  mov     r12, r15
0x18000b8bd  mov     [rsp+130h+Size], r15
0x18000b8c2  mov     rcx, rdx; Size
0x18000b8c5  cmp     rcx, 1000h
0x18000b8cc  jb      short loc_18000B8FA
0x18000b8ce  lea     rax, [rcx+27h]
0x18000b8d2  cmp     rax, rcx
0x18000b8d5  jbe     loc_18000C1BD
0x18000b8db  mov     rcx, rax; Size
0x18000b8de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b8e3  test    rax, rax
0x18000b8e6  jz      loc_18000BF98
0x18000b8ec  lea     rdi, [rax+27h]
0x18000b8f0  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18000b8f4  mov     [rdi-8], rax
0x18000b8f8  jmp     short loc_18000B902
0x18000b8fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b8ff  mov     rdi, rax
0x18000b902  mov     r9, [rsp+130h+var_100]
0x18000b907  mov     [rbp+57h+var_98], rbx
0x18000b90b  mov     [rbp+57h+var_90], r12
0x18000b90f  lea     r8, [rbx+rbx]; Size
0x18000b913  lea     rax, [r8+rdi]
0x18000b917  mov     [rsp+130h+var_100], rax
0x18000b91c  mov     rdx, r9; Src
0x18000b91f  mov     rcx, rdi; void *
0x18000b922  call    memcpy_0
0x18000b927  mov     rax, [rsp+130h+var_100]
0x18000b92c  mov     [rax], r13w
0x18000b930  cmp     rsi, 7
0x18000b934  jbe     short loc_18000B96A
0x18000b936  lea     rdx, ds:2[rsi*2]; unsigned __int64
0x18000b93e  cmp     rdx, 1000h
0x18000b945  jb      short loc_18000B962
0x18000b947  mov     rcx, [r14-8]
0x18000b94b  sub     r14, rcx
0x18000b94e  sub     r14, 8
0x18000b952  cmp     r14, 1Fh
0x18000b956  ja      loc_18000BF98
0x18000b95c  add     rdx, 27h ; '''
0x18000b960  jmp     short loc_18000B965
0x18000b962  mov     rcx, r14; void *
0x18000b965  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b96a  mov     [rbp+57h+Src], rdi
0x18000b96e  cmp     rbx, r12
0x18000b971  jnb     short loc_18000B9A4
0x18000b973  lea     rax, [rbx+1]
0x18000b977  mov     [rbp+57h+var_98], rax
0x18000b97b  lea     rax, [rbp+57h+Src]
0x18000b97f  cmp     r12, 7
0x18000b983  cmova   rax, rdi
0x18000b987  mov     dword ptr [rax+rbx*2], 2Fh ; '/'
0x18000b98e  mov     r12, [rbp+57h+var_90]
0x18000b992  mov     rax, [rbp+57h+var_98]
0x18000b996  mov     [rsp+130h+var_100], rax
  ... truncated ...
```
