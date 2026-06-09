# StructuredQuery1::IntegerConditionGenerator::RecognizeNamedEntities(wchar_t const *,ulong,ITokenCollection *,INamedEntityCollector *)

- ea: `0x180035670`
- end: `0x180035b82`
- name: `?RecognizeNamedEntities@IntegerConditionGenerator@StructuredQuery1@@UEAAJPEB_WKPEAUITokenCollection@@PEAUINamedEntityCollector@@@Z`
- size: `1298`
- prototype: `int(StructuredQuery1::IntegerConditionGenerator *__hidden this, const wchar_t *, unsigned int, struct ITokenCollection *, struct INamedEntityCollector *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180035670`
- `0x180035b90`
- `0x180035bac`
- `0x18005daf0`
- `0x18005e85c`
- `0x18008b010`

## import_xrefs

- `OLEAUT32!__imp_VarParseNumFromStr` at `0x18003570f`
- `OLEAUT32!__imp_VarParseNumFromStr` at `0x18003570f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b16`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::IntegerConditionGenerator::RecognizeNamedEntities(
        StructuredQuery1::IntegerConditionGenerator *this,
        const wchar_t *a2,
        LCID a3,
        struct ITokenCollection *a4,
        struct INamedEntityCollector *a5)
{
  struct ITokenCollection *v5; // rsi
  __int16 v6; // r9
  int v7; // ebx
  LCID v8; // r10d
  const wchar_t *v9; // rax
  const OLECHAR *v10; // rdi
  HRESULT v11; // eax
  INT cchUsed; // r14d
  wchar_t v14; // cx
  ULONG v15; // r15d
  wchar_t *v16; // rdx
  ULONG v17; // r9d
  struct ITokenCollectionVtbl *lpVtbl; // rax
  unsigned int v19; // r13d
  __int64 v20; // r12
  unsigned int v21; // ecx
  __int64 v22; // rdi
  unsigned int v23; // esi
  ULONG v24; // eax
  bool v25; // zf
  unsigned int v26; // r13d
  int v27; // eax
  struct ITokenCollection *v28; // r13
  unsigned int v29; // r14d
  unsigned int v30; // edi
  struct ITokenCollection v31; // rax
  int v32; // eax
  struct ITokenCollectionVtbl *v33; // rax
  struct ITokenCollection *v34; // r14
  wchar_t *v35; // rdi
  __int64 v36; // rcx
  unsigned int v37; // esi
  __int64 v38; // rdx
  int v39; // eax
  struct INamedEntityCollector *v40; // rsi
  StructuredQuery1::IntegerConditionGenerator *v41; // rdi
  int v42; // eax
  int nPwr10; // ecx
  __int64 v44; // rdx
  char v45; // al
  int v46; // eax
  struct ITokenCollection v47; // rax
  __int64 v48; // rdx
  int v49; // eax
  __int128 v50; // rax
  __int64 v51; // r8
  bool v52; // zf
  BYTE *rgbDig; // [rsp+20h] [rbp-E0h]
  int v54; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v55; // [rsp+58h] [rbp-A8h] BYREF
  struct ITokenCollection *v56; // [rsp+60h] [rbp-A0h]
  ULONG v57; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *Buffer; // [rsp+70h] [rbp-90h] BYREF
  const OLECHAR *v59; // [rsp+78h] [rbp-88h]
  unsigned int v60; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v61; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v62; // [rsp+88h] [rbp-78h] BYREF
  LCID v63; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v64; // [rsp+90h] [rbp-70h]
  StructuredQuery1::IntegerConditionGenerator *v65; // [rsp+98h] [rbp-68h]
  struct INamedEntityCollector *v66; // [rsp+A0h] [rbp-60h]
  NUMPARSE pnumprs; // [rsp+A8h] [rbp-58h] BYREF
  BYTE v68[112]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = a4;
  v56 = a4;
  v65 = this;
  v6 = 0;
  v7 = 0;
  v66 = a5;
  v8 = a3;
  v63 = a3;
  v9 = a2;
  v64 = a2;
  v10 = a2;
  while ( *v10 != v6 )
  {
    if ( *v10 != 46 && *v10 != 0xFF0E || v9 >= v10 || !SemanticsUM::Syntax::IsFullStop(*(v10 - 1)) )
    {
      pnumprs.cDig = 100;
      pnumprs.dwInFlags = 2836;
      *(_OWORD *)&pnumprs.dwOutFlags = 0;
      v11 = VarParseNumFromStr(v10, v8, 0, &pnumprs, v68);
      v6 = 0;
      if ( v11 >= 0 )
      {
        cchUsed = pnumprs.cchUsed;
        if ( pnumprs.cchUsed > 0 )
        {
          v14 = v10[pnumprs.cchUsed - 1];
          v15 = (pnumprs.dwOutFlags >> 8) & 1;
          v59 = &v10[pnumprs.cchUsed];
          if ( SemanticsUM::Syntax::IsFullStop(v14) && SemanticsUM::Syntax::IsFullStop(*v16) )
          {
            --cchUsed;
            v15 = v17;
            pnumprs.cchUsed = cchUsed;
          }
          lpVtbl = v5->lpVtbl;
          v57 = v17;
          v19 = v17;
          v20 = v17;
          v7 = ((__int64 (__fastcall *)(struct ITokenCollection *, ULONG *))lpVtbl->NumberOfTokens)(v5, &v57);
          if ( v7 >= 0 )
          {
            v21 = 0;
            v22 = v10 - v64;
            v23 = 0;
            v60 = 0;
            do
            {
              v24 = v57;
              v25 = v23 == v57;
              if ( v23 >= v57 )
                goto LABEL_21;
              LODWORD(v55) = v20;
              v26 = v23;
              v27 = ((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD, unsigned int *, wchar_t **, __int64))v56->lpVtbl->GetToken)(
                      v56,
                      v23,
                      &v60,
                      &v55,
                      v20);
              v7 = v27;
              v21 = v60;
              if ( v60 + (unsigned int)v55 > (unsigned int)v22 )
                break;
              ++v23;
            }
            while ( v27 >= 0 );
            v23 = v26 + 1;
            if ( v60 + (unsigned int)v55 > (unsigned int)v22 )
              v23 = v26;
            if ( v27 < 0 )
            {
LABEL_42:
              v5 = v56;
              v19 = v20;
              goto LABEL_43;
            }
            v24 = v57;
            v25 = v23 == v57;
LABEL_21:
            if ( !v25 && v21 >= (unsigned int)v22 )
            {
              v28 = v56;
              v29 = v22 + cchUsed;
              v30 = v23 + 1;
              while ( v30 < v24 )
              {
                v31.lpVtbl = v28->lpVtbl;
                LODWORD(v55) = v20;
                v32 = ((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD, wchar_t **, _QWORD, __int64))v31.lpVtbl->GetToken)(
                        v28,
                        v30,
                        &v55,
                        0,
                        v20);
                v7 = v32;
                if ( (unsigned int)v55 >= v29 )
                {
                  if ( v32 < 0 )
                    goto LABEL_42;
                  break;
                }
                ++v30;
                if ( v32 < 0 )
                  goto LABEL_42;
                v24 = v57;
              }
              v33 = v28->lpVtbl;
              LODWORD(v55) = v20;
              LODWORD(Buffer) = v20;
              v7 = ((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD, wchar_t **, wchar_t **, __int64))v33->GetToken)(
                     v28,
                     v30 - 1,
                     &v55,
                     &Buffer,
                     v20);
              if ( v7 < 0 )
                goto LABEL_42;
              if ( (int)Buffer + (int)v55 <= v29 )
              {
                v19 = v23;
                LODWORD(v20) = v30;
                goto LABEL_35;
              }
              v7 = 1;
              v5 = v28;
LABEL_44:
              v6 = 0;
LABEL_45:
              v10 = v59;
LABEL_46:
              v8 = v63;
              goto LABEL_8;
            }
            v7 = 1;
LABEL_48:
            v5 = v56;
            goto LABEL_44;
          }
LABEL_43:
          if ( v7 < 0 )
            goto LABEL_44;
LABEL_35:
          if ( v19 >= (unsigned int)v20 )
            goto LABEL_48;
          v34 = v56;
          v35 = 0;
          v54 = 0;
          v36 = *((_QWORD *)v65 + 2);
          v37 = v20;
          v38 = *((_QWORD *)v65 + 5);
          Buffer = 0;
          LODWORD(rgbDig) = v20;
          v39 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, struct ITokenCollection *, BYTE *, int *, wchar_t **))(*(_QWORD *)v36 + 72LL))(
                  v36,
                  v38,
                  v64,
                  v56,
                  rgbDig,
                  &v54,
                  &Buffer);
          v6 = 0;
          v7 = v39;
          if ( v39 >= 0 && Buffer && v54 )
          {
            v55 = 0;
            if ( swscanf(Buffer, L"=%I64d", &v55) == 1 )
            {
              v35 = v55;
              v37 = v20 + v54;
            }
            CoTaskMemFree(Buffer);
            Buffer = v35;
LABEL_39:
            if ( v37 <= (unsigned int)v20 )
              goto LABEL_40;
            nPwr10 = pnumprs.nPwr10;
            v44 = 1;
            while ( 1 )
            {
              v45 = 1;
              if ( nPwr10 >= 0 )
                break;
              v55 = 0;
              v50 = v44 * (__int128)10LL;
              v51 = *((_QWORD *)&v50 + 1);
              v44 = v50;
              if ( (__int64)v50 >= 0 )
                v52 = v51 == 0;
              else
                v52 = v51 == -1;
              if ( !v52 )
              {
                v44 = -1;
                v45 = 0;
                ++nPwr10;
                break;
              }
              ++nPwr10;
            }
            pnumprs.nPwr10 = nPwr10;
            v55 = (wchar_t *)v44;
            if ( v45 )
            {
              v46 = StructuredQuery1::EncodeNumberOrInterval(
                      (unsigned int)&pnumprs,
                      (unsigned int)v68,
                      0x100000,
                      v15,
                      *((_QWORD *)v65 + 3),
                      v19,
                      v37,
                      (__int64)&Buffer,
                      (__int64)&v55,
                      (__int64)v66);
              v6 = 0;
              v7 = v46;
              if ( v46 >= 0 )
              {
                v47.lpVtbl = v34->lpVtbl;
                v48 = v37 - 1;
                v62 = 0;
                v61 = 0;
                v5 = v34;
                v49 = ((__int64 (__fastcall *)(struct ITokenCollection *, __int64, unsigned int *, unsigned int *, _QWORD))v47.lpVtbl->GetToken)(
                        v34,
                        v48,
                        &v62,
                        &v61,
                        0);
                v6 = 0;
                v7 = v49;
                if ( v49 < 0 )
                  goto LABEL_45;
                v10 = &v64[v62 + (unsigned __int64)v61];
                goto LABEL_46;
              }
            }
            else
            {
LABEL_40:
              v40 = v66;
              v41 = v65;
              v42 = StructuredQuery1::EncodeNumberOrInterval(
                      (unsigned int)&pnumprs,
                      (unsigned int)v68,
                      0x100000,
                      v15,
                      *((_QWORD *)v65 + 3),
                      v19,
                      v20,
                      0,
                      0,
                      (__int64)v66);
              v6 = 0;
              v7 = v42;
              if ( v42 >= 0 )
              {
                v7 = StructuredQuery1::EncodeNumberOrInterval(
                       (unsigned int)&pnumprs,
                       (unsigned int)v68,
                       32,
                       v15,
                       *((_QWORD *)v41 + 4),
                       v19,
                       v20,
                       0,
                       0,
                       (__int64)v40);
                v5 = v34;
                goto LABEL_44;
              }
            }
          }
          else
          {
            Buffer = 0;
            if ( v39 >= 0 )
              goto LABEL_39;
          }
          v5 = v34;
          goto LABEL_45;
        }
      }
      v8 = v63;
    }
    ++v10;
LABEL_8:
    v9 = v64;
    if ( v7 < 0 )
      return (unsigned int)v7;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180035670  push    rbp
0x180035672  push    rbx
0x180035673  push    rsi
0x180035674  push    rdi
0x180035675  push    r12
0x180035677  push    r13
0x180035679  push    r14
0x18003567b  push    r15
0x18003567d  lea     rbp, [rsp-48h]
0x180035682  sub     rsp, 148h
0x180035689  mov     rax, cs:__security_cookie
0x180035690  xor     rax, rsp
0x180035693  mov     [rbp+80h+var_50], rax
0x180035697  mov     rsi, r9
0x18003569a  mov     [rsp+180h+var_120], r9
0x18003569f  mov     [rbp+80h+var_E8], rcx
0x1800356a3  xor     r9d, r9d
0x1800356a6  mov     rcx, [rbp+80h+arg_20]
0x1800356ad  mov     ebx, r9d
0x1800356b0  mov     [rbp+80h+var_E0], rcx
0x1800356b4  mov     r10d, r8d
0x1800356b7  mov     [rbp+80h+var_F4], r8d
0x1800356bb  mov     rax, rdx
0x1800356be  mov     [rbp+80h+var_F0], rdx
0x1800356c2  mov     rdi, rdx
0x1800356c5  cmp     [rdi], r9w
0x1800356c9  jz      short loc_18003572C
0x1800356cb  cmp     word ptr [rdi], 2Eh ; '.'
0x1800356cf  jz      loc_18003586C
0x1800356d5  mov     ecx, 0FF0Eh
0x1800356da  cmp     [rdi], cx
0x1800356dd  jz      loc_18003586C
0x1800356e3  xorps   xmm0, xmm0
0x1800356e6  mov     [rbp+80h+pnumprs.cDig], 64h ; 'd'
0x1800356ed  lea     rax, [rbp+80h+var_C0]
0x1800356f1  mov     [rbp+80h+pnumprs.dwInFlags], 0B14h
0x1800356f8  lea     r9, [rbp+80h+pnumprs]; pnumprs
0x1800356fc  mov     [rsp+180h+rgbDig], rax; rgbDig
0x180035701  xor     r8d, r8d; dwFlags
0x180035704  mov     edx, r10d; lcid
0x180035707  mov     rcx, rdi; strIn
0x18003570a  movdqu  xmmword ptr [rbp+80h+pnumprs.dwOutFlags], xmm0
0x18003570f  call    cs:__imp_VarParseNumFromStr
0x180035715  xor     r9d, r9d
0x180035718  test    eax, eax
0x18003571a  jns     short loc_18003574E
0x18003571c  mov     r10d, [rbp+80h+var_F4]
0x180035720  add     rdi, 2
0x180035724  mov     rax, [rbp+80h+var_F0]
0x180035728  test    ebx, ebx
0x18003572a  jns     short loc_1800356C5
0x18003572c  mov     eax, ebx
0x18003572e  mov     rcx, [rbp+80h+var_50]
0x180035732  xor     rcx, rsp; StackCookie
0x180035735  call    __security_check_cookie
0x18003573a  add     rsp, 148h
0x180035741  pop     r15
0x180035743  pop     r14
0x180035745  pop     r13
0x180035747  pop     r12
0x180035749  pop     rdi
0x18003574a  pop     rsi
0x18003574b  pop     rbx
0x18003574c  pop     rbp
0x18003574d  retn
0x18003574e  movsxd  r14, [rbp+80h+pnumprs.cchUsed]
0x180035752  test    r14d, r14d
0x180035755  jle     short loc_18003571C
0x180035757  mov     r15d, [rbp+80h+pnumprs.dwOutFlags]
0x18003575b  lea     rdx, [rdi+r14*2]
0x18003575f  movzx   ecx, word ptr [rdx-2]; wchar_t
0x180035763  shr     r15d, 8
0x180035767  and     r15d, 1
0x18003576b  mov     [rsp+180h+var_108], rdx
0x180035770  call    ?IsFullStop@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsFullStop(wchar_t)
0x180035775  test    al, al
0x180035777  jnz     loc_180035B31
0x18003577d  mov     rax, [rsi]
0x180035780  lea     rdx, [rsp+180h+var_118]
0x180035785  mov     rcx, rsi
0x180035788  mov     [rsp+180h+var_118], r9d
0x18003578d  mov     r13d, r9d
0x180035790  mov     r12d, r9d
0x180035793  mov     rax, [rax+18h]
0x180035797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003579c  mov     ebx, eax
0x18003579e  test    eax, eax
0x1800357a0  js      loc_1800359F5
0x1800357a6  sub     rdi, [rbp+80h+var_F0]
0x1800357aa  xor     ecx, ecx
0x1800357ac  sar     rdi, 1
0x1800357af  xor     esi, esi
0x1800357b1  mov     [rbp+80h+var_100], ecx
0x1800357b4  mov     eax, [rsp+180h+var_118]
0x1800357b8  cmp     esi, eax
0x1800357ba  jnb     short loc_180035812
0x1800357bc  mov     rcx, [rsp+180h+var_120]
0x1800357c1  lea     r9, [rsp+180h+var_128]
0x1800357c6  lea     r8, [rbp+80h+var_100]
0x1800357ca  mov     dword ptr [rsp+180h+var_128], r12d
0x1800357cf  mov     edx, esi
0x1800357d1  mov     [rsp+180h+rgbDig], r12
0x1800357d6  mov     r13d, esi
0x1800357d9  mov     rax, [rcx]
0x1800357dc  mov     rax, [rax+20h]
0x1800357e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357e5  mov     edx, dword ptr [rsp+180h+var_128]
0x1800357e9  mov     ebx, eax
0x1800357eb  mov     ecx, [rbp+80h+var_100]
0x1800357ee  add     edx, ecx
0x1800357f0  cmp     edx, edi
0x1800357f2  ja      short loc_1800357FA
0x1800357f4  inc     esi
0x1800357f6  test    eax, eax
0x1800357f8  jns     short loc_1800357B4
0x1800357fa  cmp     edx, edi
0x1800357fc  lea     esi, [r13+1]
0x180035800  cmova   esi, r13d
0x180035804  test    eax, eax
0x180035806  js      loc_1800359ED
0x18003580c  mov     eax, [rsp+180h+var_118]
0x180035810  cmp     esi, eax
0x180035812  jz      loc_180035A0E
0x180035818  cmp     ecx, edi
0x18003581a  jb      loc_180035A0E
0x180035820  mov     r13, [rsp+180h+var_120]
0x180035825  add     r14d, edi
0x180035828  lea     edi, [rsi+1]
0x18003582b  cmp     edi, eax
0x18003582d  jnb     short loc_180035893
0x18003582f  mov     rax, [r13+0]
0x180035833  lea     r8, [rsp+180h+var_128]
0x180035838  xor     r9d, r9d
0x18003583b  mov     dword ptr [rsp+180h+var_128], r12d
0x180035840  mov     edx, edi
0x180035842  mov     [rsp+180h+rgbDig], r12
0x180035847  mov     rcx, r13
0x18003584a  mov     rax, [rax+20h]
0x18003584e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035853  mov     ebx, eax
0x180035855  cmp     dword ptr [rsp+180h+var_128], r14d
0x18003585a  jnb     short loc_18003588B
0x18003585c  inc     edi
0x18003585e  test    eax, eax
0x180035860  js      loc_1800359ED
0x180035866  mov     eax, [rsp+180h+var_118]
0x18003586a  jmp     short loc_18003582B
0x18003586c  cmp     rax, rdi
0x18003586f  jnb     loc_1800356E3
0x180035875  movzx   ecx, word ptr [rdi-2]; wchar_t
0x180035879  call    ?IsFullStop@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsFullStop(wchar_t)
0x18003587e  test    al, al
0x180035880  jz      loc_1800356E3
0x180035886  jmp     loc_180035720
0x18003588b  test    eax, eax
0x18003588d  js      loc_1800359ED
0x180035893  mov     rax, [r13+0]
0x180035897  lea     edx, [rdi-1]
0x18003589a  lea     r9, [rsp+180h+Buffer]
0x18003589f  mov     dword ptr [rsp+180h+var_128], r12d
0x1800358a4  lea     r8, [rsp+180h+var_128]
0x1800358a9  mov     dword ptr [rsp+180h+Buffer], r12d
0x1800358ae  mov     rcx, r13
0x1800358b1  mov     [rsp+180h+rgbDig], r12
0x1800358b6  mov     rax, [rax+20h]
0x1800358ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358bf  mov     ebx, eax
0x1800358c1  test    eax, eax
0x1800358c3  js      loc_1800359ED
0x1800358c9  mov     ecx, dword ptr [rsp+180h+var_128]
0x1800358cd  add     ecx, dword ptr [rsp+180h+Buffer]
0x1800358d1  cmp     ecx, r14d
0x1800358d4  ja      loc_180035B50
0x1800358da  mov     r13d, esi
0x1800358dd  mov     r12d, edi
0x1800358e0  cmp     r13d, r12d
0x1800358e3  jnb     loc_180035A13
0x1800358e9  mov     rdx, [rbp+80h+var_E8]
0x1800358ed  lea     r8, [rsp+180h+Buffer]
0x1800358f2  mov     r14, [rsp+180h+var_120]
0x1800358f7  xor     edi, edi
0x1800358f9  mov     [rsp+180h+var_150], r8
0x1800358fe  mov     r9, r14
0x180035901  mov     [rsp+180h+var_130], edi
0x180035905  lea     r8, [rsp+180h+var_130]
0x18003590a  mov     rcx, [rdx+10h]
0x18003590e  mov     esi, r12d
0x180035911  mov     rdx, [rdx+28h]
0x180035915  mov     [rsp+180h+var_158], r8
0x18003591a  mov     r8, [rbp+80h+var_F0]
0x18003591e  mov     [rsp+180h+Buffer], rdi
0x180035923  mov     rax, [rcx]
0x180035926  mov     dword ptr [rsp+180h+rgbDig], r12d
0x18003592b  mov     rax, [rax+48h]
0x18003592f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035934  xor     r9d, r9d
0x180035937  mov     ebx, eax
0x180035939  test    eax, eax
0x18003593b  js      short loc_18003594B
0x18003593d  mov     rcx, [rsp+180h+Buffer]; Buffer
0x180035942  test    rcx, rcx
0x180035945  jnz     loc_180035ADF
0x18003594b  mov     [rsp+180h+Buffer], rdi
0x180035950  test    eax, eax
0x180035952  js      loc_180035B29
0x180035958  cmp     esi, r12d
0x18003595b  ja      loc_180035A1A
0x180035961  mov     rsi, [rbp+80h+var_E0]
0x180035965  lea     rdx, [rbp+80h+var_C0]
0x180035969  mov     rdi, [rbp+80h+var_E8]
0x18003596d  lea     rcx, [rbp+80h+pnumprs]
0x180035971  mov     [rsp+180h+var_138], rsi
0x180035976  mov     r8d, 100000h
0x18003597c  mov     [rsp+180h+var_140], r9
0x180035981  mov     [rsp+180h+var_148], r9
0x180035986  mov     r9d, r15d
0x180035989  mov     rax, [rdi+18h]
0x18003598d  mov     dword ptr [rsp+180h+var_150], r12d
0x180035992  mov     dword ptr [rsp+180h+var_158], r13d
0x180035997  mov     [rsp+180h+rgbDig], rax
0x18003599c  call    StructuredQuery1__EncodeNumberOrInterval
0x1800359a1  xor     r9d, r9d
0x1800359a4  mov     ebx, eax
0x1800359a6  test    eax, eax
0x1800359a8  js      loc_180035B29
0x1800359ae  mov     rax, [rdi+20h]
0x1800359b2  lea     rdx, [rbp+80h+var_C0]
0x1800359b6  mov     [rsp+180h+var_138], rsi
0x1800359bb  lea     rcx, [rbp+80h+pnumprs]
0x1800359bf  mov     [rsp+180h+var_140], r9
0x1800359c4  mov     r8d, 20h ; ' '
0x1800359ca  mov     [rsp+180h+var_148], r9
0x1800359cf  mov     r9d, r15d
0x1800359d2  mov     dword ptr [rsp+180h+var_150], r12d
0x1800359d7  mov     dword ptr [rsp+180h+var_158], r13d
0x1800359dc  mov     [rsp+180h+rgbDig], rax
0x1800359e1  call    StructuredQuery1__EncodeNumberOrInterval
0x1800359e6  mov     ebx, eax
0x1800359e8  mov     rsi, r14
0x1800359eb  jmp     short loc_1800359FD
0x1800359ed  mov     rsi, [rsp+180h+var_120]
0x1800359f2  mov     r13d, r12d
0x1800359f5  test    ebx, ebx
0x1800359f7  jns     loc_1800358E0
0x1800359fd  xor     r9d, r9d
0x180035a00  mov     rdi, [rsp+180h+var_108]
0x180035a05  mov     r10d, [rbp+80h+var_F4]
0x180035a09  jmp     loc_180035724
0x180035a0e  mov     ebx, 1
0x180035a13  mov     rsi, [rsp+180h+var_120]
0x180035a18  jmp     short loc_1800359FD
0x180035a1a  mov     ecx, [rbp+80h+pnumprs.nPwr10]
0x180035a1d  mov     edx, 1
0x180035a22  mov     al, 1
0x180035a24  test    ecx, ecx
0x180035a26  js      loc_180035B5D
0x180035a2c  mov     [rbp+80h+pnumprs.nPwr10], ecx
0x180035a2f  mov     [rsp+180h+var_128], rdx
0x180035a34  test    al, al
0x180035a36  jz      loc_180035961
0x180035a3c  mov     rax, [rbp+80h+var_E0]
0x180035a40  lea     rdx, [rbp+80h+var_C0]
0x180035a44  mov     rdi, [rbp+80h+var_E8]
0x180035a48  lea     rcx, [rbp+80h+pnumprs]
0x180035a4c  mov     [rsp+180h+var_138], rax
0x180035a51  mov     r9d, r15d
0x180035a54  lea     rax, [rsp+180h+var_128]
0x180035a59  mov     r8d, 100000h
0x180035a5f  mov     [rsp+180h+var_140], rax
0x180035a64  lea     rax, [rsp+180h+Buffer]
0x180035a69  mov     [rsp+180h+var_148], rax
0x180035a6e  mov     rax, [rdi+18h]
0x180035a72  mov     dword ptr [rsp+180h+var_150], esi
0x180035a76  mov     dword ptr [rsp+180h+var_158], r13d
0x180035a7b  mov     [rsp+180h+rgbDig], rax
0x180035a80  call    StructuredQuery1__EncodeNumberOrInterval
0x180035a85  xor     r9d, r9d
0x180035a88  mov     ebx, eax
0x180035a8a  test    eax, eax
0x180035a8c  js      loc_180035B29
0x180035a92  mov     rax, [r14]
0x180035a95  lea     edx, [rsi-1]
0x180035a98  mov     [rbp+80h+var_F8], r9d
0x180035a9c  lea     r8, [rbp+80h+var_F8]
0x180035aa0  mov     [rbp+80h+var_FC], r9d
0x180035aa4  mov     rcx, r14
0x180035aa7  mov     [rsp+180h+rgbDig], r9
0x180035aac  mov     rsi, r14
0x180035aaf  mov     rax, [rax+20h]
0x180035ab3  lea     r9, [rbp+80h+var_FC]
0x180035ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035abc  xor     r9d, r9d
0x180035abf  mov     ebx, eax
0x180035ac1  test    eax, eax
0x180035ac3  js      loc_180035A00
0x180035ac9  mov     eax, [rbp+80h+var_F8]
0x180035acc  mov     ecx, [rbp+80h+var_FC]
0x180035acf  add     rcx, rax
0x180035ad2  mov     rax, [rbp+80h+var_F0]
0x180035ad6  lea     rdi, [rax+rcx*2]
  ... truncated ...
```
