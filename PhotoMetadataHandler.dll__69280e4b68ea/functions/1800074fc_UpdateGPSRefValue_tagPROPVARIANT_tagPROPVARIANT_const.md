# UpdateGPSRefValue(tagPROPVARIANT *,tagPROPVARIANT const *)

- ea: `0x1800074fc`
- end: `0x1800076df`
- name: `?UpdateGPSRefValue@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180006890`
- `0x180012f00`

## callees

- `0x1800074fc`
- `0x1800132dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1800075f6`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x1800075f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180007631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180007631`

## pseudocode

```c
__int64 __fastcall UpdateGPSRefValue(struct tagPROPVARIANT *a1, const struct tagPROPVARIANT *a2)
{
  LPSTR pszVal; // r8
  BSTR v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // rbp
  wint_t v10; // cx
  BYTE **p_pData; // rbx
  BYTE *v12; // rax
  BSTR bstrVal; // rax

  if ( a2->vt != 31 )
    goto LABEL_14;
  pszVal = a2->pszVal;
  if ( !pszVal )
    goto LABEL_14;
  if ( a1->vt != 31 )
  {
    if ( a1->vt != 4117 && a1->vt != 4116 )
      goto LABEL_14;
    if ( a1->lVal == 3 )
    {
      p_pData = &a1->bstrblobVal.pData;
      v12 = (BYTE *)CoTaskMemRealloc(a1->bstrblobVal.pData, 0x20u);
      if ( !v12 )
      {
        v7 = -2147024882;
LABEL_11:
        if ( g_doStackCaptures )
          DoStackCapture(v7);
        return v7;
      }
      *p_pData = v12;
      a1->lVal = 4;
    }
    else
    {
      if ( a1->lVal != 4 )
        goto LABEL_14;
      p_pData = &a1->bstrblobVal.pData;
    }
    bstrVal = a2->bstrVal;
    if ( *bstrVal != 69 )
    {
      switch ( *bstrVal )
      {
        case 'N':
          goto LABEL_46;
        case 'S':
          goto LABEL_45;
        case 'W':
          goto LABEL_44;
      }
      if ( *bstrVal != 101 )
      {
        if ( *bstrVal != 110 )
        {
          if ( *bstrVal != 115 )
          {
            if ( *bstrVal != 119 )
              goto LABEL_14;
LABEL_44:
            *((_QWORD *)a1->bstrblobVal.pData + 3) = 4;
            return 0;
          }
LABEL_45:
          *((_QWORD *)*p_pData + 3) = 2;
          return 0;
        }
LABEL_46:
        *((_QWORD *)*p_pData + 3) = 1;
        return 0;
      }
    }
    *((_QWORD *)*p_pData + 3) = 3;
    return 0;
  }
  v5 = a1->bstrVal;
  if ( v5 )
  {
    v6 = 0x7FFFFFFF;
    do
    {
      if ( !*v5 )
        break;
      ++v5;
      --v6;
    }
    while ( v6 );
    v7 = v6 == 0 ? 0x80070057 : 0;
    v8 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
    if ( !v6 )
      goto LABEL_11;
    if ( !v8 )
    {
      v7 = -2147024362;
      goto LABEL_11;
    }
    v10 = *pszVal;
    if ( v10 == 87 || v10 == 69 || v10 == 78 || v10 == 83 )
      goto LABEL_18;
    if ( v10 == 101 || v10 == 110 || v10 == 115 || v10 == 119 )
    {
      v10 = towupper(v10);
LABEL_18:
      *(_WORD *)(a1->hVal.QuadPart + 2 * v8 - 2) = v10;
      return 0;
    }
  }
LABEL_14:
  if ( g_doStackCaptures )
    DoStackCapture(-2147024809);
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x1800074fc  push    rbx
0x1800074fe  push    rbp
0x1800074ff  push    rsi
0x180007500  push    rdi
0x180007501  push    r14
0x180007503  sub     rsp, 20h
0x180007507  xor     r14d, r14d
0x18000750a  mov     rdi, rdx
0x18000750d  cmp     word ptr [rdx], 1Fh
0x180007511  mov     rsi, rcx
0x180007514  jnz     short loc_180007590
0x180007516  mov     r8, [rdx+8]
0x18000751a  test    r8, r8
0x18000751d  jz      short loc_180007590
0x18000751f  cmp     word ptr [rcx], 1Fh
0x180007523  jnz     loc_180007607
0x180007529  mov     rax, [rcx+8]
0x18000752d  test    rax, rax
0x180007530  jz      short loc_180007590
0x180007532  mov     edx, 7FFFFFFFh
0x180007537  mov     ecx, edx
0x180007539  cmp     [rax], r14w
0x18000753d  jz      short loc_180007549
0x18000753f  add     rax, 2
0x180007543  sub     rcx, 1
0x180007547  jnz     short loc_180007539
0x180007549  mov     rax, rcx
0x18000754c  mov     ebx, 80070057h
0x180007551  neg     rax
0x180007554  mov     rax, rcx
0x180007557  sbb     edi, edi
0x180007559  sub     rdx, rcx
0x18000755c  not     edi
0x18000755e  and     edi, ebx
0x180007560  neg     rax
0x180007563  sbb     rbp, rbp
0x180007566  and     rbp, rdx
0x180007569  test    rcx, rcx
0x18000756c  jz      short loc_180007579
0x18000756e  cmp     rbp, 1
0x180007572  jnb     short loc_1800075B4
0x180007574  mov     edi, 80070216h
0x180007579  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180007580  jnz     short loc_1800075A2
0x180007582  mov     eax, edi
0x180007584  add     rsp, 20h
0x180007588  pop     r14
0x18000758a  pop     rdi
0x18000758b  pop     rsi
0x18000758c  pop     rbp
0x18000758d  pop     rbx
0x18000758e  retn
0x180007590  mov     ebx, 80070057h
0x180007595  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x18000759c  jnz     short loc_1800075AB
0x18000759e  mov     edi, ebx
0x1800075a0  jmp     short loc_180007582
0x1800075a2  mov     ecx, edi; int
0x1800075a4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800075a9  jmp     short loc_180007582
0x1800075ab  mov     ecx, ebx; int
0x1800075ad  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800075b2  jmp     short loc_18000759E
0x1800075b4  movsx   ecx, byte ptr [r8]; C
0x1800075b8  cmp     cx, 57h ; 'W'
0x1800075bc  jnz     short loc_1800075CC
0x1800075be  mov     rax, [rsi+8]
0x1800075c2  mov     [rax+rbp*2-2], cx
0x1800075c7  mov     edi, r14d
0x1800075ca  jmp     short loc_180007582
0x1800075cc  cmp     cx, 45h ; 'E'
0x1800075d0  jz      short loc_1800075BE
0x1800075d2  cmp     cx, 4Eh ; 'N'
0x1800075d6  jz      short loc_1800075BE
0x1800075d8  cmp     cx, 53h ; 'S'
0x1800075dc  jz      short loc_1800075BE
0x1800075de  cmp     cx, 65h ; 'e'
0x1800075e2  jz      short loc_1800075F6
0x1800075e4  cmp     cx, 6Eh ; 'n'
0x1800075e8  jz      short loc_1800075F6
0x1800075ea  cmp     cx, 73h ; 's'
0x1800075ee  jz      short loc_1800075F6
0x1800075f0  cmp     cx, 77h ; 'w'
0x1800075f4  jnz     short loc_180007595
0x1800075f6  call    cs:__imp_towupper
0x1800075fd  nop     dword ptr [rax+rax+00h]
0x180007602  movzx   ecx, ax
0x180007605  jmp     short loc_1800075BE
0x180007607  mov     eax, 1015h
0x18000760c  cmp     [rcx], ax
0x18000760f  jz      short loc_18000761F
0x180007611  mov     eax, 1014h
0x180007616  cmp     [rcx], ax
0x180007619  jnz     loc_180007590
0x18000761f  cmp     dword ptr [rcx+8], 3
0x180007623  jnz     short loc_180007658
0x180007625  lea     rbx, [rcx+10h]
0x180007629  mov     edx, 20h ; ' '; cb
0x18000762e  mov     rcx, [rbx]; pv
0x180007631  call    cs:__imp_CoTaskMemRealloc
0x180007638  nop     dword ptr [rax+rax+00h]
0x18000763d  test    rax, rax
0x180007640  jnz     short loc_18000764C
0x180007642  mov     edi, 8007000Eh
0x180007647  jmp     loc_180007579
0x18000764c  mov     [rbx], rax
0x18000764f  mov     dword ptr [rsi+8], 4
0x180007656  jmp     short loc_180007666
0x180007658  cmp     dword ptr [rcx+8], 4
0x18000765c  jnz     loc_180007590
0x180007662  lea     rbx, [rcx+10h]
0x180007666  mov     rax, [rdi+8]
0x18000766a  cmp     word ptr [rax], 45h ; 'E'
0x18000766e  jz      short loc_1800076CF
0x180007670  cmp     word ptr [rax], 4Eh ; 'N'
0x180007674  jz      short loc_1800076BF
0x180007676  cmp     word ptr [rax], 53h ; 'S'
0x18000767a  jz      short loc_1800076AF
0x18000767c  cmp     word ptr [rax], 57h ; 'W'
0x180007680  jz      short loc_18000769E
0x180007682  cmp     word ptr [rax], 65h ; 'e'
0x180007686  jz      short loc_1800076CF
0x180007688  cmp     word ptr [rax], 6Eh ; 'n'
0x18000768c  jz      short loc_1800076BF
0x18000768e  cmp     word ptr [rax], 73h ; 's'
0x180007692  jz      short loc_1800076AF
0x180007694  cmp     word ptr [rax], 77h ; 'w'
0x180007698  jnz     loc_180007590
0x18000769e  mov     rax, [rsi+10h]
0x1800076a2  mov     qword ptr [rax+18h], 4
0x1800076aa  jmp     loc_1800075C7
0x1800076af  mov     rax, [rbx]
0x1800076b2  mov     qword ptr [rax+18h], 2
0x1800076ba  jmp     loc_1800075C7
0x1800076bf  mov     rax, [rbx]
0x1800076c2  mov     qword ptr [rax+18h], 1
0x1800076ca  jmp     loc_1800075C7
0x1800076cf  mov     rax, [rbx]
0x1800076d2  mov     qword ptr [rax+18h], 3
0x1800076da  jmp     loc_1800075C7
```
