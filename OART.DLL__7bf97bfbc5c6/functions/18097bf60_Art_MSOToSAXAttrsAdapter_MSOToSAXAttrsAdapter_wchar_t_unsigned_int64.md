# Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)

- ea: `0x18097bf60`
- end: `0x18097c4aa`
- name: `??0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z`
- size: `1354`
- prototype: `_QWORD(Art::MSOToSAXAttrsAdapter *__hidden this, wchar_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18097edf0`

## callees

- `0x180003c40`
- `0x1803aa350`
- `0x18097b380`
- `0x18097bf60`
- `0x18097d0e0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18097c059`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18097c0d6`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18097c1b6`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18097c2e0`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18097c3e3`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18097c059`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18097c0d6`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18097c1b6`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18097c2e0`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x18097c3e3`
- `Mso98Win32Client!__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z` at `0x18097bfb0`
- `Mso98Win32Client!__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z` at `0x18097bfce`
- `Mso98Win32Client!__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z` at `0x18097bfb0`
- `Mso98Win32Client!__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z` at `0x18097bfce`
- `Mso98Win32Client!__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z` at `0x18097bfbc`
- `Mso98Win32Client!__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z` at `0x18097bfda`
- `Mso98Win32Client!__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z` at `0x18097bfbc`
- `Mso98Win32Client!__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z` at `0x18097bfda`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18097c490`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18097c490`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18097bfff`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18097bfff`

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
    if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&qword_180E1CC58) )
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
0x18097bf60  mov     [rsp-40h+ui], r8
0x18097bf65  push    rbp
0x18097bf66  push    rbx
0x18097bf67  push    rsi
0x18097bf68  push    rdi
0x18097bf69  push    r12
0x18097bf6b  push    r13
0x18097bf6d  push    r14
0x18097bf6f  push    r15
0x18097bf71  mov     rbp, rsp
0x18097bf74  sub     rsp, 48h
0x18097bf78  mov     rbx, rdx
0x18097bf7b  mov     rsi, rcx
0x18097bf7e  call    ??0CPoint@Ofc@@QEAA@XZ; Ofc::CPoint::CPoint(void)
0x18097bf83  lea     rcx, ??_7MSOToSAXAttrsAdapter@Art@@6B@; const Art::MSOToSAXAttrsAdapter::`vftable'
0x18097bf8a  mov     [rsi], rcx
0x18097bf8d  xor     r15d, r15d
0x18097bf90  mov     [rsi+8], r15
0x18097bf94  mov     [rsi+10h], r15
0x18097bf98  lea     r12, [rsi+18h]
0x18097bf9c  mov     [r12], r15
0x18097bfa0  mov     [r12+8], r15
0x18097bfa5  mov     [r12+10h], r15
0x18097bfaa  lea     edi, [r15+2Ah]
0x18097bfae  mov     ecx, edi
0x18097bfb0  call    cs:__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z; MsoWzDeclarationFromXmlns(MSOXMLNS)
0x18097bfb6  mov     [rsi+30h], rax
0x18097bfba  mov     ecx, edi
0x18097bfbc  call    cs:__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z; MsoCchDeclarationFromXmlns(MSOXMLNS)
0x18097bfc2  movzx   eax, ax
0x18097bfc5  mov     [rsi+38h], eax
0x18097bfc8  lea     edi, [r15+3Ah]
0x18097bfcc  mov     ecx, edi
0x18097bfce  call    cs:__imp_?MsoWzDeclarationFromXmlns@@YAPEB_WW4MSOXMLNS@@@Z; MsoWzDeclarationFromXmlns(MSOXMLNS)
0x18097bfd4  mov     [rsi+40h], rax
0x18097bfd8  mov     ecx, edi
0x18097bfda  call    cs:__imp_?MsoCchDeclarationFromXmlns@@YAGW4MSOXMLNS@@@Z; MsoCchDeclarationFromXmlns(MSOXMLNS)
0x18097bfe0  movzx   eax, ax
0x18097bfe3  mov     [rsi+48h], eax
0x18097bfe6  test    rbx, rbx
0x18097bfe9  jz      loc_18097C48B
0x18097bfef  mov     rdx, [rbp+ui]; ui
0x18097bff3  test    rdx, rdx
0x18097bff6  jz      loc_18097C48B
0x18097bffc  mov     rcx, rbx; strIn
0x18097bfff  call    cs:__imp_SysAllocStringLen
0x18097c005  mov     [rsi+10h], rax
0x18097c009  mov     [rbp+arg_0], r15
0x18097c00d  lea     rax, [rbp+arg_0]
0x18097c011  mov     [rbp+var_28], rax
0x18097c015  lea     rax, [rbp+ui]
0x18097c019  mov     [rbp+var_20], rax
0x18097c01d  mov     [rbp+var_18], rsi
0x18097c021  lea     rcx, qword_180E1CC58
0x18097c028  call    ??BChangeGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::ChangeGate::operator bool(void)
0x18097c02d  test    al, al
0x18097c02f  jz      loc_18097C28F
0x18097c035  mov     rbx, [rbp+arg_0]
0x18097c039  mov     rcx, [rbp+ui]
0x18097c03d  cmp     rbx, rcx
0x18097c040  jnb     loc_18097C496
0x18097c046  mov     r13w, 3Eh ; '>'
0x18097c04b  lea     edi, [r15+1]
0x18097c04f  jmp     short loc_18097C083
0x18097c051  mov     rcx, [rsi+10h]
0x18097c055  movzx   ecx, word ptr [rcx+rdx*2]; C
0x18097c059  call    cs:__imp_iswspace
0x18097c05f  mov     rbx, [rbp+arg_0]
0x18097c063  test    eax, eax
0x18097c065  jnz     short loc_18097C078
0x18097c067  mov     rdx, rbx
0x18097c06a  mov     r9, rbx
0x18097c06d  mov     rax, [rsi+10h]
0x18097c071  cmp     word ptr [rax+rbx*2], 2Fh ; '/'
0x18097c076  jnz     short loc_18097C090
0x18097c078  inc     rbx
0x18097c07b  mov     [rbp+arg_0], rbx
0x18097c07f  mov     rcx, [rbp+ui]
0x18097c083  cmp     rbx, rcx
0x18097c086  mov     r9, rbx
0x18097c089  mov     rdx, rbx
0x18097c08c  jb      short loc_18097C051
0x18097c08e  jmp     short loc_18097C094
0x18097c090  mov     rcx, [rbp+ui]
0x18097c094  cmp     rdx, rcx
0x18097c097  jnb     loc_18097C496
0x18097c09d  mov     r8, [rsi+10h]
0x18097c0a1  cmp     [r8+r9*2], r13w
0x18097c0a6  jz      loc_18097C496
0x18097c0ac  mov     r15, rdx
0x18097c0af  lea     rax, [rcx-2]
0x18097c0b3  cmp     rdx, rax
0x18097c0b6  jnz     short loc_18097C0CC
0x18097c0b8  cmp     word ptr [r8+r9*2], 2Fh ; '/'
0x18097c0be  jnz     short loc_18097C0CC
0x18097c0c0  cmp     [r8+r9*2+2], r13w
0x18097c0c6  jz      loc_18097C496
0x18097c0cc  cmp     r15, rcx
0x18097c0cf  jnb     short loc_18097C111
0x18097c0d1  movzx   ecx, word ptr [r8+rbx*2]; C
0x18097c0d6  call    cs:__imp_iswspace
0x18097c0dc  mov     rbx, [rbp+arg_0]
0x18097c0e0  test    eax, eax
0x18097c0e2  jnz     short loc_18097C111
0x18097c0e4  mov     r8, [rsi+10h]
0x18097c0e8  cmp     word ptr [r8+rbx*2], 3Dh ; '='
0x18097c0ee  jnz     short loc_18097C0F5
0x18097c0f0  cmp     rbx, r15
0x18097c0f3  jnz     short loc_18097C111
0x18097c0f5  cmp     [r8+rbx*2], r13w
0x18097c0fa  jz      short loc_18097C111
0x18097c0fc  cmp     word ptr [r8+rbx*2], 2Fh ; '/'
0x18097c102  jz      short loc_18097C111
0x18097c104  add     rbx, rdi
0x18097c107  mov     [rbp+arg_0], rbx
0x18097c10b  cmp     rbx, [rbp+ui]
0x18097c10f  jb      short loc_18097C0D1
0x18097c111  lea     rcx, [rbp+var_28]
0x18097c115  call    ??R_lambda_1_@?1???0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z@QEBA@XZ; `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)'::`2'::_lambda_1_::operator()(void)
0x18097c11a  mov     rcx, [rbp+arg_0]
0x18097c11e  cmp     rcx, [rbp+ui]
0x18097c122  jnb     loc_18097C210
0x18097c128  mov     rax, [rsi+10h]
0x18097c12c  cmp     word ptr [rax+rcx*2], 3Dh ; '='
0x18097c131  jnz     loc_18097C210
0x18097c137  add     rcx, rdi
0x18097c13a  mov     [rbp+arg_0], rcx
0x18097c13e  lea     rcx, [rbp+var_28]
0x18097c142  call    ??R_lambda_1_@?1???0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z@QEBA@XZ; `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)'::`2'::_lambda_1_::operator()(void)
0x18097c147  mov     rdi, [rbp+arg_0]
0x18097c14b  mov     rcx, [rbp+ui]
0x18097c14f  cmp     rdi, rcx
0x18097c152  jnb     short loc_18097C1A9
0x18097c154  mov     r9, [rsi+10h]
0x18097c158  movzx   edx, word ptr [r9+rdi*2]
0x18097c15d  cmp     dx, 22h ; '"'
0x18097c161  jz      short loc_18097C169
0x18097c163  cmp     dx, 27h ; '''
0x18097c167  jnz     short loc_18097C1A9
0x18097c169  lea     r14, [rdi+1]
0x18097c16d  mov     [rbp+arg_0], r14
0x18097c171  mov     rdi, r14
0x18097c174  cmp     r14, rcx
0x18097c177  jnb     loc_18097C216
0x18097c17d  lea     rax, [r14+1]
0x18097c181  mov     r8, r14
0x18097c184  mov     r10, rax
0x18097c187  mov     r11, rax
0x18097c18a  cmp     [r9+r8*2], dx
0x18097c18f  jz      short loc_18097C1A3
0x18097c191  mov     rdi, rax
0x18097c194  mov     [rbp+arg_0], rax
0x18097c198  inc     rax
0x18097c19b  mov     r8, rdi
0x18097c19e  cmp     rdi, rcx
0x18097c1a1  jb      short loc_18097C184
0x18097c1a3  lea     r12, [rsi+18h]
0x18097c1a7  jmp     short loc_18097C216
0x18097c1a9  mov     r14, rdi
0x18097c1ac  jmp     short loc_18097C209
0x18097c1ae  mov     rcx, [rsi+10h]
0x18097c1b2  movzx   ecx, word ptr [rcx+rdi*2]; C
0x18097c1b6  call    cs:__imp_iswspace
0x18097c1bc  mov     rdi, [rbp+arg_0]
0x18097c1c0  test    eax, eax
0x18097c1c2  jnz     short loc_18097C216
0x18097c1c4  mov     rdx, [rsi+10h]
0x18097c1c8  movzx   eax, word ptr [rdx+rdi*2]
0x18097c1cc  sub     ax, 22h ; '"'
0x18097c1d0  cmp     ax, r13w
0x18097c1d4  ja      short loc_18097C1E6
0x18097c1d6  mov     rcx, 4000000014000021h
0x18097c1e0  bt      rcx, rax
0x18097c1e4  jb      short loc_18097C216
0x18097c1e6  mov     rcx, [rbp+ui]
0x18097c1ea  lea     rax, [rcx-2]
0x18097c1ee  cmp     rdi, rax
0x18097c1f1  jnz     short loc_18097C202
0x18097c1f3  cmp     word ptr [rdx+rdi*2], 2Fh ; '/'
0x18097c1f8  jnz     short loc_18097C202
0x18097c1fa  cmp     [rdx+rdi*2+2], r13w
0x18097c200  jz      short loc_18097C216
0x18097c202  inc     rdi
0x18097c205  mov     [rbp+arg_0], rdi
0x18097c209  cmp     rdi, rcx
0x18097c20c  jb      short loc_18097C1AE
0x18097c20e  jmp     short loc_18097C216
0x18097c210  mov     r14, rbx
0x18097c213  mov     rdi, rbx
0x18097c216  mov     rax, [rsi+10h]
0x18097c21a  xor     ecx, ecx
0x18097c21c  mov     [rax+rbx*2], cx
0x18097c220  mov     rax, [rsi+10h]
0x18097c224  mov     [rax+rdi*2], cx
0x18097c228  mov     rcx, [rsi+10h]
0x18097c22c  lea     rax, [rcx+r15*2]
0x18097c230  xor     r15d, r15d
0x18097c233  cmp     [rax], r15w
0x18097c237  jz      short loc_18097C270
0x18097c239  lea     rcx, [rcx+r14*2]
0x18097c23d  mov     [rbp+arg_8], rcx
0x18097c241  mov     [rbp+arg_18], rax
0x18097c245  mov     rdx, [r12+8]
0x18097c24a  cmp     rdx, [r12+10h]
0x18097c24f  jz      short loc_18097C260
0x18097c251  mov     [rdx], rax
0x18097c254  mov     [rdx+8], rcx
0x18097c258  add     qword ptr [r12+8], 10h
0x18097c25e  jmp     short loc_18097C270
0x18097c260  lea     r9, [rbp+arg_8]
0x18097c264  lea     r8, [rbp+arg_18]
0x18097c268  mov     rcx, r12
0x18097c26b  call    ??$_Emplace_reallocate@PEA_WPEA_W@?$vector@U?$pair@PEA_WPEA_W@std@@V?$allocator@U?$pair@PEA_WPEA_W@std@@@2@@std@@AEAAPEAU?$pair@PEA_WPEA_W@1@QEAU21@$$QEAPEA_W1@Z; std::vector<std::pair<wchar_t *,wchar_t *>>::_Emplace_reallocate<wchar_t *,wchar_t *>(std::pair<wchar_t *,wchar_t *> * const,wchar_t * &&,wchar_t * &&)
0x18097c270  lea     rbx, [rdi+1]
0x18097c274  mov     [rbp+arg_0], rbx
0x18097c278  mov     rcx, [rbp+ui]
0x18097c27c  cmp     rbx, rcx
0x18097c27f  mov     edi, 1
0x18097c284  jb      loc_18097C086
0x18097c28a  jmp     loc_18097C496
0x18097c28f  mov     ebx, 1
0x18097c294  mov     rax, [rbp+ui]
0x18097c298  cmp     [rbp+arg_0], rax
0x18097c29c  jnb     loc_18097C496
0x18097c2a2  lea     rcx, [rbp+var_28]
0x18097c2a6  call    ??R_lambda_1_@?1???0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z@QEBA@XZ; `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)'::`2'::_lambda_1_::operator()(void)
0x18097c2ab  mov     r14, [rbp+arg_0]
0x18097c2af  mov     [rbp+arg_8], r14
0x18097c2b3  cmp     r14, [rbp+ui]
0x18097c2b7  jnb     loc_18097C496
0x18097c2bd  mov     rcx, [rsi+10h]
0x18097c2c1  cmp     word ptr [rcx+r14*2], 3Eh ; '>'
0x18097c2c7  jz      loc_18097C496
0x18097c2cd  cmp     word ptr [rcx+r14*2], 2Fh ; '/'
0x18097c2d3  jz      loc_18097C496
0x18097c2d9  mov     rdi, r14
0x18097c2dc  movzx   ecx, word ptr [rcx+rdi*2]; C
0x18097c2e0  call    cs:__imp_iswspace
0x18097c2e6  mov     rdi, [rbp+arg_0]
0x18097c2ea  test    eax, eax
0x18097c2ec  jnz     short loc_18097C312
0x18097c2ee  mov     rcx, [rsi+10h]
0x18097c2f2  movzx   eax, word ptr [rcx+rdi*2]
0x18097c2f6  cmp     ax, 2Fh ; '/'
0x18097c2fa  jz      short loc_18097C312
0x18097c2fc  sub     ax, 3Dh ; '='
0x18097c300  cmp     ax, bx
0x18097c303  jbe     short loc_18097C312
0x18097c305  inc     rdi
0x18097c308  mov     [rbp+arg_0], rdi
0x18097c30c  cmp     rdi, [rbp+ui]
0x18097c310  jb      short loc_18097C2DC
0x18097c312  lea     rcx, [rbp+var_28]
0x18097c316  call    ??R_lambda_1_@?1???0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z@QEBA@XZ; `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)'::`2'::_lambda_1_::operator()(void)
0x18097c31b  mov     rcx, [rbp+arg_0]
0x18097c31f  cmp     rcx, [rbp+ui]
0x18097c323  jnb     loc_18097C422
0x18097c329  mov     rax, [rsi+10h]
0x18097c32d  cmp     word ptr [rax+rcx*2], 3Dh ; '='
0x18097c332  jnz     loc_18097C422
0x18097c338  add     rcx, rbx
0x18097c33b  mov     [rbp+arg_0], rcx
0x18097c33f  lea     rcx, [rbp+var_28]
0x18097c343  call    ??R_lambda_1_@?1???0MSOToSAXAttrsAdapter@Art@@QEAA@PEA_W_K@Z@QEBA@XZ; `Art::MSOToSAXAttrsAdapter::MSOToSAXAttrsAdapter(wchar_t *,unsigned __int64)'::`2'::_lambda_1_::operator()(void)
0x18097c348  mov     rdx, [rbp+arg_0]
0x18097c34c  mov     rax, [rbp+ui]
0x18097c350  cmp     rdx, rax
0x18097c353  jnb     short loc_18097C3D3
0x18097c355  mov     r10, [rsi+10h]
0x18097c359  movzx   ecx, word ptr [r10+rdx*2]
0x18097c35e  cmp     cx, 22h ; '"'
0x18097c362  jz      short loc_18097C36A
0x18097c364  cmp     cx, 27h ; '''
0x18097c368  jnz     short loc_18097C3D3
0x18097c36a  lea     rbx, [rdx+1]
0x18097c36e  mov     [rbp+arg_0], rbx
0x18097c372  mov     rdx, rbx
0x18097c375  mov     r9, rbx
0x18097c378  cmp     rbx, rax
0x18097c37b  jnb     short loc_18097C3BD
0x18097c37d  lea     r8, [rbx+1]
0x18097c381  mov     r11, rbx
0x18097c384  mov     r14, rbx
0x18097c387  mov     r12, r8
0x18097c38a  mov     r15, r8
0x18097c38d  mov     r13, r8
0x18097c390  mov     r9, r14
0x18097c393  cmp     [r10+r11*2], cx
0x18097c398  jz      short loc_18097C3B2
0x18097c39a  mov     rdx, r8
0x18097c39d  mov     [rbp+arg_0], r8
0x18097c3a1  inc     r8
0x18097c3a4  mov     r11, rdx
0x18097c3a7  mov     r14, rdx
0x18097c3aa  mov     r9, rdx
0x18097c3ad  cmp     rdx, rax
0x18097c3b0  jb      short loc_18097C387
0x18097c3b2  mov     r14, [rbp+arg_8]
0x18097c3b6  lea     r12, [rsi+18h]
0x18097c3ba  xor     r15d, r15d
  ... truncated ...
```
