# CxFile::FGetsBuffer(char * *,int &,int,int &,bool)

- ea: `0x182dcf7f0`
- end: `0x182dcff0f`
- name: `?FGetsBuffer@CxFile@@QEAAPEADPEAPEADAEAHH1_N@Z`
- size: `1823`
- prototype: `char *__fastcall(CxFile *__hidden this, char **, int *, int, int *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x182dcf790`

## callees

- `0x1815ce310`
- `0x182dc4440`
- `0x182dcc420`
- `0x182dcc6d0`
- `0x182dcca70`
- `0x182dcf7f0`
- `0x183035300`
- `0x1832dbeb0`

## import_xrefs

- `VCRUNTIME140!strchr` at `0x182dcf9ea`
- `VCRUNTIME140!strchr` at `0x182dcfd20`
- `VCRUNTIME140!strchr` at `0x182dcf9ea`
- `VCRUNTIME140!strchr` at `0x182dcfd20`
- `api-ms-win-crt-heap-l1-1-0!realloc` at `0x182dcfa9b`
- `api-ms-win-crt-heap-l1-1-0!realloc` at `0x182dcfa9b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x182dcfab1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x182dcfab1`

## string_xrefs

- `0x182dcf8d2`: ` FastReadVM failed, or action was canceled 3`
- `0x182dcf982`: ` FastReadVM failed, or action was canceled 4`
- `0x182dcfc95`: ` FastReadVM failed, or action was canceled 4`
- `0x182dcfcc8`: ` FastReadVM failed, or action was canceled 5`
- `0x182dcfedb`: `There was an error in reading the file.`

## pseudocode

```c
char *__fastcall CxFile::FGetsBuffer(CxFile *this, char **a2, int *a3, int a4, int *a5, bool a6)
{
  int v6; // r12d
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  bool v13; // cc
  int v14; // eax
  int v15; // r12d
  int v16; // eax
  _BYTE *v17; // rdx
  _BYTE *v18; // rax
  __int64 v19; // rcx
  char *v20; // rax
  char *v21; // rsi
  int v22; // edi
  int v23; // ebx
  char *i; // rax
  int v25; // r12d
  char *v26; // r13
  int v27; // r12d
  int v28; // eax
  const void *v29; // r8
  void *v30; // rcx
  unsigned __int64 v31; // r12
  int v32; // eax
  int v33; // eax
  __int64 v34; // rax
  _BYTE *v35; // rdx
  _BYTE *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // r8
  const char *v39; // rcx
  char *v40; // rax
  char *v41; // rdi
  unsigned __int64 v42; // rbx
  char *v43; // rax
  char *v44; // rcx
  int v45; // edi
  char *v46; // r10
  char *v47; // rax
  char *v48; // rcx
  __int64 v49; // rax
  int v50; // ecx
  __int64 v51; // rax
  int v52; // ecx
  const std::exception *v54; // [rsp+28h] [rbp-60h] BYREF
  const std::exception *v55; // [rsp+30h] [rbp-58h] BYREF
  const std::exception *v56; // [rsp+38h] [rbp-50h] BYREF
  const std::exception *v57; // [rsp+40h] [rbp-48h] BYREF
  const std::exception *v58; // [rsp+48h] [rbp-40h] BYREF
  int v62; // [rsp+B0h] [rbp+28h]

  v6 = a4;
  *a5 = 0;
  if ( !*((_QWORD *)this + 12) )
  {
    CxStr::Resize((CxFile *)((char *)this + 88), CxFile::sm_iTotalBufSize + 2, 0);
    v10 = *((_QWORD *)this + 11);
    *((_QWORD *)this + 12) = v10;
    *(_BYTE *)(CxFile::sm_iTotalBufSize + v10) = 0;
    v11 = *((_QWORD *)this + 12);
    *(_BYTE *)(CxFile::sm_iTotalBufSize + v11 + 1) = 0;
  }
  try
  {
    LODWORD(v12) = *((_DWORD *)this + 21);
    v13 = (int)v12 <= 0;
    if ( (_DWORD)v12 )
    {
LABEL_24:
      if ( v13 )
      {
        if ( (_DWORD)v12 == -1 )
        {
          *a2 = 0;
          *a5 = -1;
          *((_BYTE *)this + 81) = 1;
          CxThrowError("There was an error in reading the file.");
        }
        if ( !(_DWORD)v12 )
        {
          *a5 = 1;
          *a2 = 0;
        }
      }
      else
      {
        v20 = strchr(*((const char **)this + 14), 10);
        v21 = v20;
        if ( v20 )
        {
          v22 = (_DWORD)v20 - *((_DWORD *)this + 28) + 1;
          if ( v22 > *((_DWORD *)this + 21) )
            CxInternalError("1.3...... Error:  iLineLen > m_iBytesInBuffer");
          v23 = (int)v21;
          for ( i = v21 - 1; *i == 13; --i )
          {
            v23 = (int)i;
            *(_WORD *)i = 10;
          }
          if ( v22 > *a3 )
          {
            if ( a6 )
            {
              if ( v22 > v6 )
                CxReportError("ERROR: Line length is too long! Line length exceeds the maximum size of line buffer!");
              v25 = (int)((double)v22 * 1.2);
              if ( v25 > a4 )
                v25 = a4;
              v26 = (char *)realloc(*a2, v25);
              if ( !v26 )
              {
                *((_BYTE *)this + 81) = 1;
                free(*a2);
                CxReportError("ERROR: Line length is too long! Required memory cannot be allocated to the line buffer!");
              }
              *a2 = v26;
              memset_0(&v26[*a3], 0, v25 - *a3);
              *a3 = v25;
            }
            else
            {
              *((_BYTE *)this + 81) = 1;
              CxReportError("ERROR: Line length is too long!");
            }
          }
          v27 = (_DWORD)v21 - v23;
          CxMemCpy(*a2, v22 - v27, *((const void **)this + 14), v22 - v27);
          (*a2)[v22 - (__int64)v27] = 0;
          *((_DWORD *)this + 30) += v22;
          v28 = *((_DWORD *)this + 30);
          *((_QWORD *)this + 16) += v22;
          if ( v28 > CxFile::sm_iTotalBufSize )
            CxInternalError("2.3...... Error:  m_iCurrentPosition > CxFile::sm_iTotalBufSize");
          *((_QWORD *)this + 14) = v21 + 1;
          *((_DWORD *)this + 21) -= v22;
          return *a2;
        }
        v29 = (const void *)*((_QWORD *)this + 14);
        v30 = *a2;
        if ( *((_BYTE *)this + 104) )
        {
          v31 = *((int *)this + 21);
          CxMemCpy(v30, v31, v29, v31);
          *((_DWORD *)this + 30) += v31;
          v32 = *((_DWORD *)this + 30);
          *((_QWORD *)this + 16) += v31;
          if ( v32 > CxFile::sm_iTotalBufSize )
            CxInternalError("2.6...... Error:  m_iCurrentPosition > CxFile::sm_iTotalBufSize");
          try
          {
            LODWORD(v34) = (*(__int64 (__fastcall **)(CxFile *, _QWORD, _QWORD))(*(_QWORD *)this + 168LL))(
                             this,
                             *((_QWORD *)this + 12),
                             CxFile::sm_iTotalBufSize);
            *((_DWORD *)this + 21) = v34;
            *((_DWORD *)this + 30) = 0;
          }
          catch ( const std::exception *v56 )
          {
            *((_BYTE *)this + 81) = 1;
            throw;
          }
          catch ( ... )
          {
            *((_BYTE *)this + 81) = 1;
            throw;
          }
          if ( (int)v34 < CxFile::sm_iTotalBufSize )
          {
            if ( (int)v34 <= 0 )
            {
              if ( (_DWORD)v34 )
              {
                *a5 = -1;
                *a2 = 0;
                *((_BYTE *)this + 81) = 1;
                CxReportError(" FastReadVM failed, or action was canceled 5");
              }
              else
              {
                *a5 = 1;
                *((_BYTE *)this + 104) = 0;
              }
LABEL_64:
              v37 = *((_QWORD *)this + 16);
              *((_QWORD *)this + 17) = v37;
              v38 = *((int *)this + 21);
              *((_QWORD *)this + 18) = v37 + v38;
              *((_BYTE *)this + 104) = (_DWORD)v38 == CxFile::sm_iTotalBufSize;
              v39 = (const char *)*((_QWORD *)this + 12);
              *((_QWORD *)this + 14) = v39;
              if ( (int)v38 <= 0 )
              {
                (*a2)[v31] = 0;
              }
              else
              {
                v40 = strchr(v39, 10);
                v41 = v40;
                if ( v40 )
                {
                  v42 = (unsigned __int64)&v40[-*((_QWORD *)this + 12) + 1];
                  if ( v42 > *((int *)this + 21) )
                    CxInternalError("5.2...... Error:  iSecondHalfLen > m_iBytesInBuffer");
                  v43 = v41;
                  if ( (unsigned __int64)v41 > *((_QWORD *)this + 12) )
                  {
                    do
                    {
                      v44 = v43 - 1;
                      if ( *(v43 - 1) != 13 )
                        break;
                      --v43;
                      *v44 = 10;
                    }
                    while ( (unsigned __int64)v44 > *((_QWORD *)this + 12) );
                  }
                  v45 = (_DWORD)v41 - (_DWORD)v43;
                  v46 = *a2;
                  v47 = &(*a2)[v31];
                  if ( v47 > *a2 )
                  {
                    do
                    {
                      v48 = v47 - 1;
                      if ( *(v47 - 1) != 13 )
                        break;
                      --v47;
                    }
                    while ( v48 > v46 );
                  }
                  CxMemCpy(
                    &v46[-(int)v31 - ((int)v46 - (int)v47) + v31],
                    v42 - v45,
                    *((const void **)this + 12),
                    v42 - v45);
                  (*a2)[v42 + v31] = 0;
                  *((_DWORD *)this + 30) = v42;
                  *((_QWORD *)this + 16) += v42;
                  if ( (int)v42 > CxFile::sm_iTotalBufSize )
                    CxInternalError("5.4...... Error:  m_iCurrentPosition > CxFile::sm_iTotalBufSize");
                  *((_QWORD *)this + 14) += v42;
                  *((_DWORD *)this + 21) -= v42;
                }
                else if ( *((_BYTE *)this + 104) )
                {
                  CxInternalError("5.7...... Error:  not found newline for the 2nd half row in the just refilled buffer.");
                }
                else
                {
                  CxMemCpy(&(*a2)[v31], *((int *)this + 21), *((const void **)this + 12), *((int *)this + 21));
                  (*a2)[*((int *)this + 21) + v31] = 0;
                  v49 = *((int *)this + 21);
                  *((_DWORD *)this + 30) += v49;
                  v50 = *((_DWORD *)this + 30);
                  *((_QWORD *)this + 16) += v49;
                  if ( v50 > CxFile::sm_iTotalBufSize )
                    CxInternalError("5.6...... Error:  m_iCurrentPosition > CxFile::sm_iTotalBufSize");
                  *((_QWORD *)this + 14) += *((int *)this + 21);
                  *((_DWORD *)this + 21) = 0;
                }
              }
              return *a2;
            }
            v62 = CxFile::sm_iTotalBufSize - v34;
            try
            {
              v33 = (*(__int64 (__fastcall **)(CxFile *, _QWORD, _QWORD))(*(_QWORD *)this + 168LL))(
                      this,
                      *((_QWORD *)this + 12) + *((int *)this + 21),
                      CxFile::sm_iTotalBufSize - (int)v34);
            }
            catch ( const std::exception *v57 )
            {
              *((_BYTE *)this + 81) = 1;
              throw;
            }
            catch ( ... )
            {
              *((_BYTE *)this + 81) = 1;
              throw;
            }
            if ( v33 )
            {
              if ( v33 == v62 )
              {
                *((_DWORD *)this + 21) = CxFile::sm_iTotalBufSize;
                v34 = CxFile::sm_iTotalBufSize;
LABEL_63:
                *(_BYTE *)(*((_QWORD *)this + 12) + v34) = 0;
                goto LABEL_64;
              }
              if ( v33 <= 0 || v33 >= v62 )
              {
                *a5 = -1;
                *a2 = 0;
                *((_BYTE *)this + 81) = 1;
                CxReportError(" FastReadVM failed, or action was canceled 4");
                goto LABEL_64;
              }
              *((_DWORD *)this + 21) += v33;
            }
            v35 = (_BYTE *)(*((_QWORD *)this + 12) + *((int *)this + 21));
            v36 = v35 - 1;
            if ( *(v35 - 1) != 10 )
            {
              v36 = (_BYTE *)(*((_QWORD *)this + 12) + *((int *)this + 21));
              *v35 = 10;
              ++*((_DWORD *)this + 21);
            }
            v36[1] = 0;
            *((_BYTE *)this + 104) = 0;
            goto LABEL_64;
          }
          v34 = (int)v34;
          goto LABEL_63;
        }
        CxMemCpy(v30, *((int *)this + 21), v29, *((int *)this + 21));
        (*a2)[*((int *)this + 21)] = 0;
        v51 = *((int *)this + 21);
        *((_DWORD *)this + 30) += v51;
        v52 = *((_DWORD *)this + 30);
        *((_QWORD *)this + 16) += v51;
        if ( v52 > CxFile::sm_iTotalBufSize )
          CxInternalError("6...... Error:  m_iCurrentPosition > CxFile::sm_iTotalBufSize");
        *((_DWORD *)this + 21) = 0;
        *a5 = 1;
      }
      return *a2;
    }
    if ( !*((_BYTE *)this + 104) )
    {
LABEL_23:
      v13 = (int)v12 <= 0;
      goto LABEL_24;
    }
    try
    {
      v14 = (*(__int64 (__fastcall **)(CxFile *, _QWORD, _QWORD))(*(_QWORD *)this + 168LL))(
              this,
              *((_QWORD *)this + 12),
              CxFile::sm_iTotalBufSize);
      *((_DWORD *)this + 21) = v14;
      *((_DWORD *)this + 30) = 0;
    }
    catch ( const std::exception *v54 )
    {
      *((_BYTE *)this + 81) = 1;
      throw;
    }
    catch ( ... )
    {
      *((_BYTE *)this + 81) = 1;
      throw;
    }
    if ( v14 < CxFile::sm_iTotalBufSize )
    {
      if ( v14 != -1 )
      {
        if ( v14 <= 0 )
        {
          *a5 = 1;
          *a2 = 0;
          goto LABEL_22;
        }
        v15 = CxFile::sm_iTotalBufSize - v14;
        try
        {
          v16 = (*(__int64 (__fastcall **)(CxFile *, _QWORD, _QWORD))(*(_QWORD *)this + 168LL))(
                  this,
                  *((_QWORD *)this + 12) + *((int *)this + 21),
                  CxFile::sm_iTotalBufSize - v14);
        }
        catch ( const std::exception *v55 )
        {
          *((_BYTE *)this + 81) = 1;
          throw;
        }
        catch ( ... )
        {
          *((_BYTE *)this + 81) = 1;
          throw;
        }
        if ( v16 )
        {
          if ( v16 == v15 )
          {
            *((_DWORD *)this + 21) = CxFile::sm_iTotalBufSize;
            *(_BYTE *)(*((_QWORD *)this + 12) + CxFile::sm_iTotalBufSize) = 0;
            v6 = a4;
            goto LABEL_22;
          }
          if ( v16 <= 0 || v16 >= v15 )
          {
            *((_BYTE *)this + 81) = 1;
            CxReportError(" FastReadVM failed, or action was canceled 4");
            v6 = a4;
            goto LABEL_22;
          }
          *((_DWORD *)this + 21) += v16;
        }
        v17 = (_BYTE *)(*((_QWORD *)this + 12) + *((int *)this + 21));
        v18 = v17 - 1;
        if ( *(v17 - 1) != 10 )
        {
          v18 = (_BYTE *)(*((_QWORD *)this + 12) + *((int *)this + 21));
          *v17 = 10;
          ++*((_DWORD *)this + 21);
        }
        v18[1] = 0;
        *((_BYTE *)this + 104) = 0;
        v6 = a4;
        goto LABEL_22;
      }
      *((_BYTE *)this + 81) = 1;
      CxReportError(" FastReadVM failed, or action was canceled 3");
    }
LABEL_22:
    v19 = *((_QWORD *)this + 16);
    *((_QWORD *)this + 17) = v19;
    v12 = *((int *)this + 21);
    *((_QWORD *)this + 18) = v19 + v12;
    *((_BYTE *)this + 104) = (_DWORD)v12 == CxFile::sm_iTotalBufSize;
    *((_QWORD *)this + 14) = *((_QWORD *)this + 12);
    goto LABEL_23;
  }
  catch ( const std::exception *v58 )
  {
    *((_BYTE *)this + 81) = 1;
    throw;
  }
  catch ( ... )
  {
    *((_BYTE *)this + 81) = 1;
    throw;
  }
  return *a2;
}

```

## disassembly

```asm
0x182dcf7f0  mov     [rsp+arg_18], r9d
0x182dcf7f5  mov     [rsp+arg_10], r8
0x182dcf7fa  mov     [rsp+arg_0], rcx
0x182dcf7ff  push    rbx
0x182dcf800  push    rsi
0x182dcf801  push    rdi
0x182dcf802  push    r12
0x182dcf804  push    r13
0x182dcf806  push    r14
0x182dcf808  push    r15
0x182dcf80a  sub     rsp, 50h
0x182dcf80e  mov     [rsp+88h+var_68], 0FFFFFFFFFFFFFFFEh
0x182dcf817  mov     r12d, r9d
0x182dcf81a  mov     r15, rdx
0x182dcf81d  mov     r14, rcx
0x182dcf820  mov     r13, [rsp+88h+arg_20]
0x182dcf828  mov     dword ptr [r13+0], 0
0x182dcf830  cmp     qword ptr [rcx+60h], 0
0x182dcf835  jnz     short loc_182DCF872
0x182dcf837  mov     eax, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcf83d  add     eax, 2
0x182dcf840  movsxd  rdx, eax; unsigned __int64
0x182dcf843  xor     r8d, r8d; char
0x182dcf846  add     rcx, 58h ; 'X'; this
0x182dcf84a  call    ?Resize@CxStr@@QEAAX_KD@Z; CxStr::Resize(unsigned __int64,char)
0x182dcf84f  mov     rcx, [r14+58h]
0x182dcf853  mov     [r14+60h], rcx
0x182dcf857  movsxd  rax, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcf85e  mov     byte ptr [rax+rcx], 0
0x182dcf862  movsxd  rcx, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcf869  mov     rax, [r14+60h]
0x182dcf86d  mov     byte ptr [rcx+rax+1], 0
0x182dcf872  mov     edx, [r14+54h]; unsigned int
0x182dcf876  test    edx, edx
0x182dcf878  jnz     loc_182DCF9DB
0x182dcf87e  cmp     [r14+68h], dl
0x182dcf882  jz      loc_182DCF9D9
0x182dcf888  mov     rax, [r14]
0x182dcf88b  movsxd  rbx, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcf892  mov     rdi, [rax+0A8h]
0x182dcf899  mov     rcx, rdi; this
0x182dcf89c  call    cs:__guard_check_icall_fptr; CxVector::SetPadForMissings(uint) ...
0x182dcf8a2  mov     r8, rbx
0x182dcf8a5  mov     rdx, [r14+60h]
0x182dcf8a9  mov     rcx, r14
0x182dcf8ac  call    rdi
0x182dcf8ae  mov     [r14+54h], eax
0x182dcf8b2  mov     dword ptr [r14+78h], 0
0x182dcf8ba  mov     ecx, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcf8c0  cmp     eax, ecx
0x182dcf8c2  jge     loc_182DCF9A7
0x182dcf8c8  cmp     eax, 0FFFFFFFFh
0x182dcf8cb  jnz     short loc_182DCF8E3
0x182dcf8cd  mov     byte ptr [r14+51h], 1
0x182dcf8d2  lea     rcx, aFastreadvmFail; " FastReadVM failed, or action was cance"...
0x182dcf8d9  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x182dcf8de  jmp     loc_182DCF9A7
0x182dcf8e3  test    eax, eax
0x182dcf8e5  jle     loc_182DCF998
0x182dcf8eb  sub     ecx, eax
0x182dcf8ed  movsxd  r12, ecx
0x182dcf8f0  mov     rax, [r14]
0x182dcf8f3  movsxd  rdi, dword ptr [r14+54h]
0x182dcf8f7  add     rdi, [r14+60h]
0x182dcf8fb  mov     rsi, [rax+0A8h]
0x182dcf902  mov     rcx, rsi; this
0x182dcf905  call    cs:__guard_check_icall_fptr; CxVector::SetPadForMissings(uint) ...
0x182dcf90b  mov     r8, r12
0x182dcf90e  mov     rdx, rdi
0x182dcf911  mov     rcx, r14
0x182dcf914  call    rsi
0x182dcf916  nop
0x182dcf917  test    eax, eax
0x182dcf919  jz      short loc_182DCF94F
0x182dcf91b  cmp     eax, r12d
0x182dcf91e  jnz     short loc_182DCF942
0x182dcf920  mov     eax, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcf926  mov     [r14+54h], eax
0x182dcf92a  movsxd  rax, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcf931  add     rax, [r14+60h]
0x182dcf935  mov     byte ptr [rax], 0
0x182dcf938  mov     r12d, [rsp+88h+arg_18]
0x182dcf940  jmp     short loc_182DCF9A7
0x182dcf942  test    eax, eax
0x182dcf944  jle     short loc_182DCF97D
0x182dcf946  cmp     eax, r12d
0x182dcf949  jge     short loc_182DCF97D
0x182dcf94b  add     [r14+54h], eax
0x182dcf94f  movsxd  rdx, dword ptr [r14+54h]
0x182dcf953  add     rdx, [r14+60h]
0x182dcf957  lea     rax, [rdx-1]
0x182dcf95b  cmp     byte ptr [rax], 0Ah
0x182dcf95e  jz      short loc_182DCF96A
0x182dcf960  mov     rax, rdx
0x182dcf963  mov     byte ptr [rdx], 0Ah
0x182dcf966  inc     dword ptr [r14+54h]
0x182dcf96a  mov     byte ptr [rax+1], 0
0x182dcf96e  mov     byte ptr [r14+68h], 0
0x182dcf973  mov     r12d, [rsp+88h+arg_18]
0x182dcf97b  jmp     short loc_182DCF9A7
0x182dcf97d  mov     byte ptr [r14+51h], 1
0x182dcf982  lea     rcx, aFastreadvmFail_0; " FastReadVM failed, or action was cance"...
0x182dcf989  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x182dcf98e  mov     r12d, [rsp+88h+arg_18]
0x182dcf996  jmp     short loc_182DCF9A7
0x182dcf998  mov     dword ptr [r13+0], 1
0x182dcf9a0  mov     qword ptr [r15], 0
0x182dcf9a7  mov     rcx, [r14+80h]
0x182dcf9ae  mov     [r14+88h], rcx
0x182dcf9b5  movsxd  rdx, dword ptr [r14+54h]
0x182dcf9b9  lea     rax, [rcx+rdx]
0x182dcf9bd  mov     [r14+90h], rax
0x182dcf9c4  cmp     edx, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcf9ca  setz    al
0x182dcf9cd  mov     [r14+68h], al
0x182dcf9d1  mov     rax, [r14+60h]
0x182dcf9d5  mov     [r14+70h], rax
0x182dcf9d9  test    edx, edx
0x182dcf9db  jle     loc_182DCFEC6
0x182dcf9e1  mov     edx, 0Ah; Val
0x182dcf9e6  mov     rcx, [r14+70h]; Str
0x182dcf9ea  call    cs:__imp_strchr
0x182dcf9f0  mov     rsi, rax
0x182dcf9f3  test    rax, rax
0x182dcf9f6  jz      loc_182DCFB65
0x182dcf9fc  mov     edi, esi
0x182dcf9fe  sub     edi, [r14+70h]
0x182dcfa02  inc     edi
0x182dcfa04  cmp     edi, [r14+54h]
0x182dcfa08  jle     short loc_182DCFA16
0x182dcfa0a  lea     rcx, a13ErrorIlinele; "1.3...... Error:  iLineLen > m_iBytesIn"...
0x182dcfa11  call    ?CxInternalError@@YAXPEBDZZ; CxInternalError(char const *,...)
0x182dcfa16  mov     rbx, rsi
0x182dcfa19  lea     rax, [rsi-1]
0x182dcfa1d  cmp     byte ptr [rax], 0Dh
0x182dcfa20  jnz     short loc_182DCFA40
0x182dcfa22  nop     dword ptr [rax+00h]
0x182dcfa26  nop     word ptr [rax+rax+00000000h]
0x182dcfa30  mov     rbx, rax
0x182dcfa33  mov     word ptr [rax], 0Ah
0x182dcfa38  dec     rax
0x182dcfa3b  cmp     byte ptr [rax], 0Dh
0x182dcfa3e  jz      short loc_182DCFA30
0x182dcfa40  mov     rax, [rsp+88h+arg_10]
0x182dcfa48  cmp     edi, [rax]
0x182dcfa4a  jle     loc_182DCFB01
0x182dcfa50  cmp     [rsp+88h+arg_28], 0
0x182dcfa58  jz      loc_182DCFAF0
0x182dcfa5e  cmp     edi, r12d
0x182dcfa61  jle     short loc_182DCFA6F
0x182dcfa63  lea     rcx, aErrorLineLengt_0; "ERROR: Line length is too long! Line le"...
0x182dcfa6a  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x182dcfa6f  movd    xmm0, edi
0x182dcfa73  cvtdq2pd xmm0, xmm0
0x182dcfa77  mulsd   xmm0, cs:__real@3ff3333333333333
0x182dcfa7f  cvttsd2si r12d, xmm0
0x182dcfa84  cmp     r12d, [rsp+88h+arg_18]
0x182dcfa8c  cmovg   r12d, [rsp+88h+arg_18]
0x182dcfa95  movsxd  rdx, r12d; Size
0x182dcfa98  mov     rcx, [r15]; Block
0x182dcfa9b  call    cs:__imp_realloc
0x182dcfaa1  mov     r13, rax
0x182dcfaa4  test    rax, rax
0x182dcfaa7  jnz     short loc_182DCFAC3
0x182dcfaa9  mov     byte ptr [r14+51h], 1
0x182dcfaae  mov     rcx, [r15]; Block
0x182dcfab1  call    cs:__imp_free
0x182dcfab7  lea     rcx, aErrorLineLengt; "ERROR: Line length is too long! Require"...
0x182dcfabe  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x182dcfac3  mov     [r15], r13
0x182dcfac6  mov     rax, [rsp+88h+arg_10]
0x182dcface  movsxd  rcx, dword ptr [rax]
0x182dcfad1  mov     eax, r12d
0x182dcfad4  sub     eax, ecx
0x182dcfad6  movsxd  r8, eax; Size
0x182dcfad9  add     rcx, r13; void *
0x182dcfadc  xor     edx, edx; Val
0x182dcfade  call    memset_0
0x182dcfae3  mov     rax, [rsp+88h+arg_10]
0x182dcfaeb  mov     [rax], r12d
0x182dcfaee  jmp     short loc_182DCFB01
0x182dcfaf0  mov     byte ptr [r14+51h], 1
0x182dcfaf5  lea     rcx, aErrorLineLengt_1; "ERROR: Line length is too long!"
0x182dcfafc  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x182dcfb01  mov     r12d, esi
0x182dcfb04  sub     r12d, ebx
0x182dcfb07  mov     eax, edi
0x182dcfb09  sub     eax, r12d
0x182dcfb0c  movsxd  rdx, eax; unsigned __int64
0x182dcfb0f  mov     r9, rdx; unsigned __int64
0x182dcfb12  mov     r8, [r14+70h]; void *
0x182dcfb16  mov     rcx, [r15]; void *
0x182dcfb19  call    ?CxMemCpy@@YAPEAXPEAX_KPEBX1@Z; CxMemCpy(void *,unsigned __int64,void const *,unsigned __int64)
0x182dcfb1e  movsxd  rdx, edi
0x182dcfb21  movsxd  rax, r12d
0x182dcfb24  mov     rcx, rdx
0x182dcfb27  sub     rcx, rax
0x182dcfb2a  mov     rax, [r15]
0x182dcfb2d  mov     byte ptr [rcx+rax], 0
0x182dcfb31  add     [r14+78h], edi
0x182dcfb35  mov     eax, [r14+78h]
0x182dcfb39  add     [r14+80h], rdx
0x182dcfb40  cmp     eax, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcfb46  jle     short loc_182DCFB54
0x182dcfb48  lea     rcx, a23ErrorMIcurre; "2.3...... Error:  m_iCurrentPosition > "...
0x182dcfb4f  call    ?CxInternalError@@YAXPEBDZZ; CxInternalError(char const *,...)
0x182dcfb54  lea     rax, [rsi+1]
0x182dcfb58  mov     [r14+70h], rax
0x182dcfb5c  sub     [r14+54h], edi
0x182dcfb60  jmp     loc_182DCFEFC
0x182dcfb65  mov     r8, [r14+70h]; void *
0x182dcfb69  mov     rcx, [r15]; void *
0x182dcfb6c  cmp     byte ptr [r14+68h], 0
0x182dcfb71  jz      loc_182DCFE76
0x182dcfb77  movsxd  r12, dword ptr [r14+54h]
0x182dcfb7b  mov     r9, r12; unsigned __int64
0x182dcfb7e  mov     rdx, r12; unsigned __int64
0x182dcfb81  call    ?CxMemCpy@@YAPEAXPEAX_KPEBX1@Z; CxMemCpy(void *,unsigned __int64,void const *,unsigned __int64)
0x182dcfb86  add     [r14+78h], r12d
0x182dcfb8a  mov     eax, [r14+78h]
0x182dcfb8e  add     [r14+80h], r12
0x182dcfb95  cmp     eax, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcfb9b  jle     short loc_182DCFBAA
0x182dcfb9d  lea     rcx, a26ErrorMIcurre; "2.6...... Error:  m_iCurrentPosition > "...
0x182dcfba4  call    ?CxInternalError@@YAXPEBDZZ; CxInternalError(char const *,...)
0x182dcfba9  nop
0x182dcfbaa  mov     rax, [r14]
0x182dcfbad  movsxd  rbx, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcfbb4  mov     rdi, [rax+0A8h]
0x182dcfbbb  mov     rcx, rdi; this
0x182dcfbbe  call    cs:__guard_check_icall_fptr; CxVector::SetPadForMissings(uint) ...
0x182dcfbc4  mov     r8, rbx
0x182dcfbc7  mov     rdx, [r14+60h]
0x182dcfbcb  mov     rcx, r14
0x182dcfbce  call    rdi
0x182dcfbd0  mov     [r14+54h], eax
0x182dcfbd4  mov     dword ptr [r14+78h], 0
0x182dcfbdc  mov     ecx, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcfbe2  cmp     eax, ecx
0x182dcfbe4  jge     loc_182DCFCD6
0x182dcfbea  test    eax, eax
0x182dcfbec  jle     loc_182DCFCA3
0x182dcfbf2  sub     ecx, eax
0x182dcfbf4  movsxd  rcx, ecx
0x182dcfbf7  mov     [rsp+88h+arg_20], rcx
0x182dcfbff  mov     rax, [r14]
0x182dcfc02  mov     rbx, rcx
0x182dcfc05  movsxd  rdi, dword ptr [r14+54h]
0x182dcfc09  add     rdi, [r14+60h]
0x182dcfc0d  mov     rsi, [rax+0A8h]
0x182dcfc14  mov     rcx, rsi; this
0x182dcfc17  call    cs:__guard_check_icall_fptr; CxVector::SetPadForMissings(uint) ...
0x182dcfc1d  mov     r8, rbx
0x182dcfc20  mov     rdx, rdi
0x182dcfc23  mov     rcx, r14
0x182dcfc26  call    rsi
0x182dcfc28  nop
0x182dcfc29  test    eax, eax
0x182dcfc2b  jz      short loc_182DCFC5B
0x182dcfc2d  mov     rcx, [rsp+88h+arg_20]
0x182dcfc35  cmp     eax, ecx
0x182dcfc37  jnz     short loc_182DCFC4F
0x182dcfc39  mov     eax, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcfc3f  mov     [r14+54h], eax
0x182dcfc43  movsxd  rax, cs:?sm_iTotalBufSize@CxFile@@2HA; int CxFile::sm_iTotalBufSize
0x182dcfc4a  jmp     loc_182DCFCD8
0x182dcfc4f  test    eax, eax
0x182dcfc51  jle     short loc_182DCFC81
0x182dcfc53  cmp     eax, ecx
0x182dcfc55  jge     short loc_182DCFC81
0x182dcfc57  add     [r14+54h], eax
0x182dcfc5b  movsxd  rdx, dword ptr [r14+54h]
0x182dcfc5f  add     rdx, [r14+60h]
0x182dcfc63  lea     rax, [rdx-1]
0x182dcfc67  cmp     byte ptr [rax], 0Ah
0x182dcfc6a  jz      short loc_182DCFC76
0x182dcfc6c  mov     rax, rdx
0x182dcfc6f  mov     byte ptr [rdx], 0Ah
0x182dcfc72  inc     dword ptr [r14+54h]
0x182dcfc76  mov     byte ptr [rax+1], 0
0x182dcfc7a  mov     byte ptr [r14+68h], 0
0x182dcfc7f  jmp     short loc_182DCFCDF
0x182dcfc81  mov     dword ptr [r13+0], 0FFFFFFFFh
0x182dcfc89  mov     qword ptr [r15], 0
0x182dcfc90  mov     byte ptr [r14+51h], 1
0x182dcfc95  lea     rcx, aFastreadvmFail_0; " FastReadVM failed, or action was cance"...
0x182dcfc9c  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x182dcfca1  jmp     short loc_182DCFCDF
0x182dcfca3  jnz     short loc_182DCFCB4
0x182dcfca5  mov     dword ptr [r13+0], 1
0x182dcfcad  mov     byte ptr [r14+68h], 0
0x182dcfcb2  jmp     short loc_182DCFCDF
0x182dcfcb4  mov     dword ptr [r13+0], 0FFFFFFFFh
0x182dcfcbc  mov     qword ptr [r15], 0
0x182dcfcc3  mov     byte ptr [r14+51h], 1
0x182dcfcc8  lea     rcx, aFastreadvmFail_1; " FastReadVM failed, or action was cance"...
0x182dcfccf  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x182dcfcd4  jmp     short loc_182DCFCDF
0x182dcfcd6  cdqe
0x182dcfcd8  add     rax, [r14+60h]
  ... truncated ...
```
