# Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)

- ea: `0x180986560`
- end: `0x180986aaa`
- name: `??0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z`
- size: `1354`
- prototype: `_QWORD(Art::MSOToSAXAttrsAdapter *__hidden this, wchar_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180988fb0`

## callees

- `0x1801285f0`
- `0x1803b9770`
- `0x180985980`
- `0x180986560`
- `0x180987500`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x180986659`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1809866d6`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1809867b6`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1809868e0`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1809869e3`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x180986659`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1809866d6`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1809867b6`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1809868e0`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1809869e3`
- `Mso98Win32Client!__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z` at `0x1809865b0`
- `Mso98Win32Client!__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z` at `0x1809865ce`
- `Mso98Win32Client!__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z` at `0x1809865b0`
- `Mso98Win32Client!__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z` at `0x1809865ce`
- `Mso98Win32Client!__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z` at `0x1809865bc`
- `Mso98Win32Client!__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z` at `0x1809865da`
- `Mso98Win32Client!__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z` at `0x1809865bc`
- `Mso98Win32Client!__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z` at `0x1809865da`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180986a90`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180986a90`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1809865ff`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1809865ff`

## pseudocode

```c
Art::MSOToSAXAttrsAdapter *__fastcall Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(
        Art::MSOToSAXAttrsAdapter *this,
        wchar_t *a2,
        unsigned __int64 a3)
{
  char *v5; // r12
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  int v8; // eax
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // r9
  bool v11; // cf
  __int64 v12; // r8
  unsigned __int64 v13; // r15
  int v14; // eax
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rcx
  __int64 v17; // r9
  __int16 v18; // dx
  unsigned __int64 v19; // r14
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // r8
  int v22; // eax
  __int64 v23; // rdx
  unsigned __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  _WORD *v27; // rax
  unsigned __int64 v28; // rcx
  _QWORD *v29; // rdx
  unsigned __int64 v30; // r14
  __int64 v31; // rcx
  unsigned __int64 v32; // rdi
  int v33; // eax
  __int16 v34; // ax
  unsigned __int64 v35; // rdx
  __int64 v36; // r10
  __int16 v37; // cx
  unsigned __int64 v38; // rbx
  unsigned __int64 v39; // r9
  unsigned __int64 v40; // r8
  unsigned __int64 v41; // r11
  unsigned __int64 v42; // r14
  int v43; // eax
  unsigned __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  _WORD *v47; // rax
  unsigned __int64 v48; // rcx
  _QWORD *v49; // rdx
  unsigned __int64 *v51; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 *p_ui; // [rsp+28h] [rbp-20h]
  Art::MSOToSAXAttrsAdapter *v53; // [rsp+30h] [rbp-18h]
  unsigned __int64 v54; // [rsp+90h] [rbp+48h] BYREF
  unsigned __int64 v55; // [rsp+98h] [rbp+50h] BYREF
  unsigned __int64 ui; // [rsp+A0h] [rbp+58h] BYREF
  _WORD *v57; // [rsp+A8h] [rbp+60h] BYREF

  ui = a3;
  Ofc::CPoint::CPoint(this);
  *(_QWORD *)this = &Art::MSOToSAXAttrsAdapter::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v5 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = MsoWzDeclarationFromXmlns(42);
  *((_DWORD *)this + 14) = (unsigned __int16)MsoCchDeclarationFromXmlns(42);
  *((_QWORD *)this + 8) = MsoWzDeclarationFromXmlns(58);
  *((_DWORD *)this + 18) = (unsigned __int16)MsoCchDeclarationFromXmlns(58);
  if ( a2 && ui )
  {
    *((_QWORD *)this + 2) = SysAllocStringLen(a2, ui);
    v54 = 0;
    v51 = &v54;
    p_ui = &ui;
    v53 = this;
    if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&qword_180E1C908) )
    {
      v6 = v54;
      v7 = ui;
      if ( v54 < ui )
      {
LABEL_9:
        v11 = v6 < v7;
        while ( 1 )
        {
          v10 = v6;
          v9 = v6;
          if ( v11 )
          {
            v8 = iswspace(*(_WORD *)(*((_QWORD *)this + 2) + 2 * v6));
            v6 = v54;
            if ( v8 || (v9 = v54, v10 = v54, *(_WORD *)(*((_QWORD *)this + 2) + 2 * v54) == 47) )
            {
              v6 = ++v54;
              v7 = ui;
              goto LABEL_9;
            }
            v7 = ui;
          }
          if ( v9 < v7 )
          {
            v12 = *((_QWORD *)this + 2);
            if ( *(_WORD *)(v12 + 2 * v10) != 62 )
            {
              v13 = v9;
              if ( v9 != v7 - 2 || *(_WORD *)(v12 + 2 * v10) != 47 || *(_WORD *)(v12 + 2 * v10 + 2) != 62 )
              {
                if ( v9 < v7 )
                {
                  do
                  {
                    v14 = iswspace(*(_WORD *)(v12 + 2 * v6));
                    v6 = v54;
                    if ( v14 )
                      break;
                    v12 = *((_QWORD *)this + 2);
                    if ( *(_WORD *)(v12 + 2 * v54) == 61 && v54 != v13 )
                      break;
                    if ( *(_WORD *)(v12 + 2 * v54) == 62 )
                      break;
                    if ( *(_WORD *)(v12 + 2 * v54) == 47 )
                      break;
                    v6 = v54 + 1;
                    v54 = v6;
                  }
                  while ( v6 < ui );
                }
                `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter'::`2'::_lambda_1_::operator()(&v51);
                if ( v54 < ui && *(_WORD *)(*((_QWORD *)this + 2) + 2 * v54) == 61 )
                {
                  ++v54;
                  `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter'::`2'::_lambda_1_::operator()(&v51);
                  v15 = v54;
                  v16 = ui;
                  if ( v54 < ui
                    && ((v17 = *((_QWORD *)this + 2), v18 = *(_WORD *)(v17 + 2 * v54), v18 == 34) || v18 == 39) )
                  {
                    v19 = v54 + 1;
                    v54 = v19;
                    ++v15;
                    if ( v19 < ui )
                    {
                      v20 = v19 + 1;
                      v21 = v19;
                      do
                      {
                        if ( *(_WORD *)(v17 + 2 * v21) == v18 )
                          break;
                        v15 = v20;
                        v54 = v20++;
                        v21 = v15;
                      }
                      while ( v15 < ui );
                      v5 = (char *)this + 24;
                    }
                  }
                  else
                  {
                    v19 = v54;
                    while ( v15 < v16 )
                    {
                      v22 = iswspace(*(_WORD *)(*((_QWORD *)this + 2) + 2 * v15));
                      v15 = v54;
                      if ( v22 )
                        break;
                      v23 = *((_QWORD *)this + 2);
                      v24 = *(unsigned __int16 *)(v23 + 2 * v54);
                      LOWORD(v24) = v24 - 34;
                      if ( (unsigned __int16)v24 <= 0x3Eu )
                      {
                        v25 = 0x4000000014000021LL;
                        if ( _bittest64(&v25, v24) )
                          break;
                      }
                      v16 = ui;
                      if ( v54 == ui - 2 && *(_WORD *)(v23 + 2 * v54) == 47 && *(_WORD *)(v23 + 2 * v54 + 2) == 62 )
                        break;
                      v15 = ++v54;
                    }
                  }
                }
                else
                {
                  v19 = v6;
                  v15 = v6;
                }
                *(_WORD *)(*((_QWORD *)this + 2) + 2 * v6) = 0;
                *(_WORD *)(*((_QWORD *)this + 2) + 2 * v15) = 0;
                v26 = *((_QWORD *)this + 2);
                v27 = (_WORD *)(v26 + 2 * v13);
                if ( *v27 )
                {
                  v28 = v26 + 2 * v19;
                  v55 = v28;
                  v57 = v27;
                  v29 = (_QWORD *)*((_QWORD *)v5 + 1);
                  if ( v29 == *((_QWORD **)v5 + 2) )
                  {
                    std::vector<std::pair<wchar_t *,wchar_t *>>::_Emplace_reallocate<wchar_t *,wchar_t *>(
                      v5,
                      v29,
                      &v57,
                      &v55,
                      v51,
                      p_ui,
                      v53);
                  }
                  else
                  {
                    *v29 = v27;
                    v29[1] = v28;
                    *((_QWORD *)v5 + 1) += 16LL;
                  }
                }
                v6 = v15 + 1;
                v54 = v15 + 1;
                v7 = ui;
                v11 = v15 + 1 < ui;
                if ( v15 + 1 < ui )
                  continue;
              }
            }
          }
          return this;
        }
      }
    }
    else
    {
      while ( v54 < ui )
      {
        `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter'::`2'::_lambda_1_::operator()(&v51);
        v30 = v54;
        v55 = v54;
        if ( v54 >= ui )
          break;
        v31 = *((_QWORD *)this + 2);
        if ( *(_WORD *)(v31 + 2 * v54) == 62 || *(_WORD *)(v31 + 2 * v54) == 47 )
          break;
        v32 = v54;
        do
        {
          v33 = iswspace(*(_WORD *)(v31 + 2 * v32));
          v32 = v54;
          if ( v33 )
            break;
          v31 = *((_QWORD *)this + 2);
          v34 = *(_WORD *)(v31 + 2 * v54);
          if ( v34 == 47 )
            break;
          if ( (unsigned __int16)(v34 - 61) <= 1u )
            break;
          v32 = v54 + 1;
          v54 = v32;
        }
        while ( v32 < ui );
        `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter'::`2'::_lambda_1_::operator()(&v51);
        if ( v54 < ui && *(_WORD *)(*((_QWORD *)this + 2) + 2 * v54) == 61 )
        {
          ++v54;
          `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter'::`2'::_lambda_1_::operator()(&v51);
          v35 = v54;
          if ( v54 < ui && ((v36 = *((_QWORD *)this + 2), v37 = *(_WORD *)(v36 + 2 * v54), v37 == 34) || v37 == 39) )
          {
            v38 = v54 + 1;
            v54 = v38;
            ++v35;
            v39 = v38;
            if ( v38 < ui )
            {
              v40 = v38 + 1;
              v41 = v38;
              v42 = v38;
              do
              {
                v39 = v42;
                if ( *(_WORD *)(v36 + 2 * v41) == v37 )
                  break;
                v35 = v40;
                v54 = v40++;
                v41 = v35;
                v42 = v35;
                v39 = v35;
              }
              while ( v35 < ui );
              v30 = v55;
              v5 = (char *)this + 24;
            }
            if ( v35 < ui && *(_WORD *)(v36 + 2 * v39) == v37 )
              v54 = v35 + 1;
          }
          else
          {
            v38 = v54;
            if ( v54 < ui )
            {
              do
              {
                v43 = iswspace(*(_WORD *)(*((_QWORD *)this + 2) + 2 * v35));
                v35 = v54;
                if ( v43 )
                  break;
                v44 = *(unsigned __int16 *)(*((_QWORD *)this + 2) + 2 * v54);
                LOWORD(v44) = v44 - 34;
                if ( (unsigned __int16)v44 <= 0x3Eu )
                {
                  v45 = 0x400000001C002021LL;
                  if ( _bittest64(&v45, v44) )
                    break;
                }
                v35 = v54 + 1;
                v54 = v35;
              }
              while ( v35 < ui );
            }
          }
        }
        else
        {
          v38 = v32;
          v35 = v32;
        }
        *(_WORD *)(*((_QWORD *)this + 2) + 2 * v32) = 0;
        *(_WORD *)(*((_QWORD *)this + 2) + 2 * v35) = 0;
        v46 = *((_QWORD *)this + 2);
        v47 = (_WORD *)(v46 + 2 * v30);
        if ( *v47 )
        {
          v48 = v46 + 2 * v38;
          v55 = v48;
          v57 = v47;
          v49 = (_QWORD *)*((_QWORD *)v5 + 1);
          if ( v49 == *((_QWORD **)v5 + 2) )
          {
            std::vector<std::pair<wchar_t *,wchar_t *>>::_Emplace_reallocate<wchar_t *,wchar_t *>(
              v5,
              v49,
              &v57,
              &v55,
              v51,
              p_ui,
              v53);
          }
          else
          {
            *v49 = v47;
            v49[1] = v48;
            *((_QWORD *)v5 + 1) += 16LL;
          }
        }
      }
    }
  }
  else
  {
    MsoShipAssertTagProc(505180507);
  }
  return this;
}

```

## disassembly

```asm
0x180986560  mov     [rsp-40h+ui], r8
0x180986565  push    rbp
0x180986566  push    rbx
0x180986567  push    rsi
0x180986568  push    rdi
0x180986569  push    r12
0x18098656b  push    r13
0x18098656d  push    r14
0x18098656f  push    r15
0x180986571  mov     rbp, rsp
0x180986574  sub     rsp, 48h
0x180986578  mov     rbx, rdx
0x18098657b  mov     rsi, rcx
0x18098657e  call    ??0CPoint@Ofc@@QEAA@XZ; Ofc::CPoint::CPoint(void)
0x180986583  lea     rcx, ??_7MSOToSAXAttrsAdapter@Art@@6B@; const Art::MSOToSAXAttrsAdapter::`vftable'
0x18098658a  mov     [rsi], rcx
0x18098658d  xor     r15d, r15d
0x180986590  mov     [rsi+8], r15
0x180986594  mov     [rsi+10h], r15
0x180986598  lea     r12, [rsi+18h]
0x18098659c  mov     [r12], r15
0x1809865a0  mov     [r12+8], r15
0x1809865a5  mov     [r12+10h], r15
0x1809865aa  lea     edi, [r15+2Ah]
0x1809865ae  mov     ecx, edi
0x1809865b0  call    cs:__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z; MsoWzDeclarationFromXmlns(MSOXMLNS)
0x1809865b6  mov     [rsi+30h], rax
0x1809865ba  mov     ecx, edi
0x1809865bc  call    cs:__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z; MsoCchDeclarationFromXmlns(MSOXMLNS)
0x1809865c2  movzx   eax, ax
0x1809865c5  mov     [rsi+38h], eax
0x1809865c8  lea     edi, [r15+3Ah]
0x1809865cc  mov     ecx, edi
0x1809865ce  call    cs:__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z; MsoWzDeclarationFromXmlns(MSOXMLNS)
0x1809865d4  mov     [rsi+40h], rax
0x1809865d8  mov     ecx, edi
0x1809865da  call    cs:__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z; MsoCchDeclarationFromXmlns(MSOXMLNS)
0x1809865e0  movzx   eax, ax
0x1809865e3  mov     [rsi+48h], eax
0x1809865e6  test    rbx, rbx
0x1809865e9  jz      loc_180986A8B
0x1809865ef  mov     rdx, [rbp+ui]; ui
0x1809865f3  test    rdx, rdx
0x1809865f6  jz      loc_180986A8B
0x1809865fc  mov     rcx, rbx; strIn
0x1809865ff  call    cs:__imp_SysAllocStringLen
0x180986605  mov     [rsi+10h], rax
0x180986609  mov     [rbp+arg_0], r15
0x18098660d  lea     rax, [rbp+arg_0]
0x180986611  mov     [rbp+var_28], rax
0x180986615  lea     rax, [rbp+ui]
0x180986619  mov     [rbp+var_20], rax
0x18098661d  mov     [rbp+var_18], rsi
0x180986621  lea     rcx, qword_180E1C908
0x180986628  call    ??BChangeGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::ChangeGate::operator bool(void)
0x18098662d  test    al, al
0x18098662f  jz      loc_18098688F
0x180986635  mov     rbx, [rbp+arg_0]
0x180986639  mov     rcx, [rbp+ui]
0x18098663d  cmp     rbx, rcx
0x180986640  jnb     loc_180986A96
0x180986646  mov     r13w, 3Eh ; '>'
0x18098664b  lea     edi, [r15+1]
0x18098664f  jmp     short loc_180986683
0x180986651  mov     rcx, [rsi+10h]
0x180986655  movzx   ecx, word ptr [rcx+rdx*2]; C
0x180986659  call    cs:__imp_iswspace
0x18098665f  mov     rbx, [rbp+arg_0]
0x180986663  test    eax, eax
0x180986665  jnz     short loc_180986678
0x180986667  mov     rdx, rbx
0x18098666a  mov     r9, rbx
0x18098666d  mov     rax, [rsi+10h]
0x180986671  cmp     word ptr [rax+rbx*2], 2Fh ; '/'
0x180986676  jnz     short loc_180986690
0x180986678  inc     rbx
0x18098667b  mov     [rbp+arg_0], rbx
0x18098667f  mov     rcx, [rbp+ui]
0x180986683  cmp     rbx, rcx
0x180986686  mov     r9, rbx
0x180986689  mov     rdx, rbx
0x18098668c  jb      short loc_180986651
0x18098668e  jmp     short loc_180986694
0x180986690  mov     rcx, [rbp+ui]
0x180986694  cmp     rdx, rcx
0x180986697  jnb     loc_180986A96
0x18098669d  mov     r8, [rsi+10h]
0x1809866a1  cmp     [r8+r9*2], r13w
0x1809866a6  jz      loc_180986A96
0x1809866ac  mov     r15, rdx
0x1809866af  lea     rax, [rcx-2]
0x1809866b3  cmp     rdx, rax
0x1809866b6  jnz     short loc_1809866CC
0x1809866b8  cmp     word ptr [r8+r9*2], 2Fh ; '/'
0x1809866be  jnz     short loc_1809866CC
0x1809866c0  cmp     [r8+r9*2+2], r13w
0x1809866c6  jz      loc_180986A96
0x1809866cc  cmp     r15, rcx
0x1809866cf  jnb     short loc_180986711
0x1809866d1  movzx   ecx, word ptr [r8+rbx*2]; C
0x1809866d6  call    cs:__imp_iswspace
0x1809866dc  mov     rbx, [rbp+arg_0]
0x1809866e0  test    eax, eax
0x1809866e2  jnz     short loc_180986711
0x1809866e4  mov     r8, [rsi+10h]
0x1809866e8  cmp     word ptr [r8+rbx*2], 3Dh ; '='
0x1809866ee  jnz     short loc_1809866F5
0x1809866f0  cmp     rbx, r15
0x1809866f3  jnz     short loc_180986711
0x1809866f5  cmp     [r8+rbx*2], r13w
0x1809866fa  jz      short loc_180986711
0x1809866fc  cmp     word ptr [r8+rbx*2], 2Fh ; '/'
0x180986702  jz      short loc_180986711
0x180986704  add     rbx, rdi
0x180986707  mov     [rbp+arg_0], rbx
0x18098670b  cmp     rbx, [rbp+ui]
0x18098670f  jb      short loc_1809866D1
0x180986711  lea     rcx, [rbp+var_28]
0x180986715  call    ??R_lambda_1_@?1???0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z@QEBA@XZ; `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)'::`2'::_lambda_1_::operator()(void)
0x18098671a  mov     rcx, [rbp+arg_0]
0x18098671e  cmp     rcx, [rbp+ui]
0x180986722  jnb     loc_180986810
0x180986728  mov     rax, [rsi+10h]
0x18098672c  cmp     word ptr [rax+rcx*2], 3Dh ; '='
0x180986731  jnz     loc_180986810
0x180986737  add     rcx, rdi
0x18098673a  mov     [rbp+arg_0], rcx
0x18098673e  lea     rcx, [rbp+var_28]
0x180986742  call    ??R_lambda_1_@?1???0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z@QEBA@XZ; `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)'::`2'::_lambda_1_::operator()(void)
0x180986747  mov     rdi, [rbp+arg_0]
0x18098674b  mov     rcx, [rbp+ui]
0x18098674f  cmp     rdi, rcx
0x180986752  jnb     short loc_1809867A9
0x180986754  mov     r9, [rsi+10h]
0x180986758  movzx   edx, word ptr [r9+rdi*2]
0x18098675d  cmp     dx, 22h ; '"'
0x180986761  jz      short loc_180986769
0x180986763  cmp     dx, 27h ; '''
0x180986767  jnz     short loc_1809867A9
0x180986769  lea     r14, [rdi+1]
0x18098676d  mov     [rbp+arg_0], r14
0x180986771  mov     rdi, r14
0x180986774  cmp     r14, rcx
0x180986777  jnb     loc_180986816
0x18098677d  lea     rax, [r14+1]
0x180986781  mov     r8, r14
0x180986784  mov     r10, rax
0x180986787  mov     r11, rax
0x18098678a  cmp     [r9+r8*2], dx
0x18098678f  jz      short loc_1809867A3
0x180986791  mov     rdi, rax
0x180986794  mov     [rbp+arg_0], rax
0x180986798  inc     rax
0x18098679b  mov     r8, rdi
0x18098679e  cmp     rdi, rcx
0x1809867a1  jb      short loc_180986784
0x1809867a3  lea     r12, [rsi+18h]
0x1809867a7  jmp     short loc_180986816
0x1809867a9  mov     r14, rdi
0x1809867ac  jmp     short loc_180986809
0x1809867ae  mov     rcx, [rsi+10h]
0x1809867b2  movzx   ecx, word ptr [rcx+rdi*2]; C
0x1809867b6  call    cs:__imp_iswspace
0x1809867bc  mov     rdi, [rbp+arg_0]
0x1809867c0  test    eax, eax
0x1809867c2  jnz     short loc_180986816
0x1809867c4  mov     rdx, [rsi+10h]
0x1809867c8  movzx   eax, word ptr [rdx+rdi*2]
0x1809867cc  sub     ax, 22h ; '"'
0x1809867d0  cmp     ax, r13w
0x1809867d4  ja      short loc_1809867E6
0x1809867d6  mov     rcx, 4000000014000021h
0x1809867e0  bt      rcx, rax
0x1809867e4  jb      short loc_180986816
0x1809867e6  mov     rcx, [rbp+ui]
0x1809867ea  lea     rax, [rcx-2]
0x1809867ee  cmp     rdi, rax
0x1809867f1  jnz     short loc_180986802
0x1809867f3  cmp     word ptr [rdx+rdi*2], 2Fh ; '/'
0x1809867f8  jnz     short loc_180986802
0x1809867fa  cmp     [rdx+rdi*2+2], r13w
0x180986800  jz      short loc_180986816
0x180986802  inc     rdi
0x180986805  mov     [rbp+arg_0], rdi
0x180986809  cmp     rdi, rcx
0x18098680c  jb      short loc_1809867AE
0x18098680e  jmp     short loc_180986816
0x180986810  mov     r14, rbx
0x180986813  mov     rdi, rbx
0x180986816  mov     rax, [rsi+10h]
0x18098681a  xor     ecx, ecx
0x18098681c  mov     [rax+rbx*2], cx
0x180986820  mov     rax, [rsi+10h]
0x180986824  mov     [rax+rdi*2], cx
0x180986828  mov     rcx, [rsi+10h]
0x18098682c  lea     rax, [rcx+r15*2]
0x180986830  xor     r15d, r15d
0x180986833  cmp     [rax], r15w
0x180986837  jz      short loc_180986870
0x180986839  lea     rcx, [rcx+r14*2]
0x18098683d  mov     [rbp+arg_8], rcx
0x180986841  mov     [rbp+arg_18], rax
0x180986845  mov     rdx, [r12+8]
0x18098684a  cmp     rdx, [r12+10h]
0x18098684f  jz      short loc_180986860
0x180986851  mov     [rdx], rax
0x180986854  mov     [rdx+8], rcx
0x180986858  add     qword ptr [r12+8], 10h
0x18098685e  jmp     short loc_180986870
0x180986860  lea     r9, [rbp+arg_8]
0x180986864  lea     r8, [rbp+arg_18]
0x180986868  mov     rcx, r12
0x18098686b  call    ??$_Emplace_reallocate@PEA_WPEA_W@?$vector@U?$pair@PEA_WPEA_W@std@@V?$allocator@U?$pair@PEA_WPEA_W@std@@@2@@std@@AEAAPEAU?$pair@PEA_WPEA_W@1@QEAU21@$$QEAPEA_W1@Z; std::vector<std::pair<wchar_t *,wchar_t *>>::_Emplace_reallocate<wchar_t *,wchar_t *>(std::pair<wchar_t *,wchar_t *> * const,wchar_t * &&,wchar_t * &&)
0x180986870  lea     rbx, [rdi+1]
0x180986874  mov     [rbp+arg_0], rbx
0x180986878  mov     rcx, [rbp+ui]
0x18098687c  cmp     rbx, rcx
0x18098687f  mov     edi, 1
0x180986884  jb      loc_180986686
0x18098688a  jmp     loc_180986A96
0x18098688f  mov     ebx, 1
0x180986894  mov     rax, [rbp+ui]
0x180986898  cmp     [rbp+arg_0], rax
0x18098689c  jnb     loc_180986A96
0x1809868a2  lea     rcx, [rbp+var_28]
0x1809868a6  call    ??R_lambda_1_@?1???0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z@QEBA@XZ; `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)'::`2'::_lambda_1_::operator()(void)
0x1809868ab  mov     r14, [rbp+arg_0]
0x1809868af  mov     [rbp+arg_8], r14
0x1809868b3  cmp     r14, [rbp+ui]
0x1809868b7  jnb     loc_180986A96
0x1809868bd  mov     rcx, [rsi+10h]
0x1809868c1  cmp     word ptr [rcx+r14*2], 3Eh ; '>'
0x1809868c7  jz      loc_180986A96
0x1809868cd  cmp     word ptr [rcx+r14*2], 2Fh ; '/'
0x1809868d3  jz      loc_180986A96
0x1809868d9  mov     rdi, r14
0x1809868dc  movzx   ecx, word ptr [rcx+rdi*2]; C
0x1809868e0  call    cs:__imp_iswspace
0x1809868e6  mov     rdi, [rbp+arg_0]
0x1809868ea  test    eax, eax
0x1809868ec  jnz     short loc_180986912
0x1809868ee  mov     rcx, [rsi+10h]
0x1809868f2  movzx   eax, word ptr [rcx+rdi*2]
0x1809868f6  cmp     ax, 2Fh ; '/'
0x1809868fa  jz      short loc_180986912
0x1809868fc  sub     ax, 3Dh ; '='
0x180986900  cmp     ax, bx
0x180986903  jbe     short loc_180986912
0x180986905  inc     rdi
0x180986908  mov     [rbp+arg_0], rdi
0x18098690c  cmp     rdi, [rbp+ui]
0x180986910  jb      short loc_1809868DC
0x180986912  lea     rcx, [rbp+var_28]
0x180986916  call    ??R_lambda_1_@?1???0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z@QEBA@XZ; `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)'::`2'::_lambda_1_::operator()(void)
0x18098691b  mov     rcx, [rbp+arg_0]
0x18098691f  cmp     rcx, [rbp+ui]
0x180986923  jnb     loc_180986A22
0x180986929  mov     rax, [rsi+10h]
0x18098692d  cmp     word ptr [rax+rcx*2], 3Dh ; '='
0x180986932  jnz     loc_180986A22
0x180986938  add     rcx, rbx
0x18098693b  mov     [rbp+arg_0], rcx
0x18098693f  lea     rcx, [rbp+var_28]
0x180986943  call    ??R_lambda_1_@?1???0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z@QEBA@XZ; `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)'::`2'::_lambda_1_::operator()(void)
0x180986948  mov     rdx, [rbp+arg_0]
0x18098694c  mov     rax, [rbp+ui]
0x180986950  cmp     rdx, rax
0x180986953  jnb     short loc_1809869D3
0x180986955  mov     r10, [rsi+10h]
0x180986959  movzx   ecx, word ptr [r10+rdx*2]
0x18098695e  cmp     cx, 22h ; '"'
0x180986962  jz      short loc_18098696A
0x180986964  cmp     cx, 27h ; '''
0x180986968  jnz     short loc_1809869D3
0x18098696a  lea     rbx, [rdx+1]
0x18098696e  mov     [rbp+arg_0], rbx
0x180986972  mov     rdx, rbx
0x180986975  mov     r9, rbx
0x180986978  cmp     rbx, rax
0x18098697b  jnb     short loc_1809869BD
0x18098697d  lea     r8, [rbx+1]
0x180986981  mov     r11, rbx
0x180986984  mov     r14, rbx
0x180986987  mov     r12, r8
0x18098698a  mov     r15, r8
0x18098698d  mov     r13, r8
0x180986990  mov     r9, r14
0x180986993  cmp     [r10+r11*2], cx
0x180986998  jz      short loc_1809869B2
0x18098699a  mov     rdx, r8
0x18098699d  mov     [rbp+arg_0], r8
0x1809869a1  inc     r8
0x1809869a4  mov     r11, rdx
0x1809869a7  mov     r14, rdx
0x1809869aa  mov     r9, rdx
0x1809869ad  cmp     rdx, rax
0x1809869b0  jb      short loc_180986987
0x1809869b2  mov     r14, [rbp+arg_8]
0x1809869b6  lea     r12, [rsi+18h]
0x1809869ba  xor     r15d, r15d
  ... truncated ...
```
