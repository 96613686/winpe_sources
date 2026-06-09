# CJpegTurboFrameEncode::BuildColorProfileData(IWICColorContext *,tagPROPVARIANT *)

- ea: `0x1801bc308`
- end: `0x1801bc666`
- name: `?BuildColorProfileData@CJpegTurboFrameEncode@@AEAAJPEAUIWICColorContext@@PEAUtagPROPVARIANT@@@Z`
- size: `862`
- prototype: `__int64 __fastcall(CJpegTurboFrameEncode *__hidden this, struct IWICColorContext *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044678`

## callees

- `0x180039480`
- `0x1800bd9d4`
- `0x18017e444`
- `0x1801bc308`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801bc460`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801bc460`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bc646`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801bc646`

## pseudocode

```c
__int64 __fastcall CJpegTurboFrameEncode::BuildColorProfileData(
        CJpegTurboFrameEncode *this,
        struct IWICColorContext *a2,
        struct tagPROPVARIANT *a3)
{
  struct tagPROPVARIANT *v3; // r14
  char *v5; // rbp
  unsigned int v6; // ebx
  HRESULT v7; // eax
  int v8; // ecx
  unsigned int v9; // esi
  unsigned int v10; // r15d
  unsigned int v11; // edi
  unsigned int v12; // ecx
  char *v13; // rax
  unsigned __int8 v14; // r9
  __int64 v15; // rax
  unsigned int v16; // edx
  __int16 v17; // cx
  unsigned __int8 v18; // r12
  int v19; // edx
  unsigned __int16 v20; // ax
  __int16 v21; // cx
  __int64 v23; // [rsp+30h] [rbp-58h]
  CJpegTurboFrameEncode *puResult; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v25; // [rsp+98h] [rbp+10h] BYREF
  struct tagPROPVARIANT *v26; // [rsp+A0h] [rbp+18h]
  unsigned int v27; // [rsp+A8h] [rbp+20h]

  v26 = a3;
  puResult = this;
  v3 = a3;
  v5 = 0;
  if ( !a2 || !a3 )
  {
    v6 = -2147024809;
    goto LABEL_36;
  }
  v25 = 0;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v7 = ((__int64 (__fastcall *)(struct IWICColorContext *, _QWORD, _QWORD, unsigned int *))a2->lpVtbl->GetProfileBytes)(
         a2,
         0,
         0,
         &v25);
  v6 = v7;
  if ( v7 < 0 )
    goto LABEL_5;
  LOWORD(v9) = v25;
  if ( v25 <= 0xFFEF )
  {
    v10 = v25 + 18;
    v27 = v25 + 18;
    if ( v25 + 18 >= v25 )
    {
      v11 = 1;
      goto LABEL_18;
    }
    goto LABEL_35;
  }
  if ( v25 + 61423 < v25 )
    goto LABEL_35;
  LODWORD(puResult) = v25 + 61423;
  v11 = (v25 + 61423) / 0xEFF0;
  if ( v11 >= 0xFF )
  {
    v6 = -2003292273;
    goto LABEL_36;
  }
  v9 = v25 % 0xEFF0;
  if ( !(v25 % 0xEFF0) )
    v9 = 61424;
  v7 = ULongLongToUInt(61442LL * (v11 - 1), (UINT *)&puResult);
  v6 = v7;
  if ( v7 >= 0 )
  {
    v12 = (_DWORD)puResult + v9;
    if ( (unsigned int)puResult + v9 >= (unsigned int)puResult )
    {
      v10 = v12 + 18;
      v27 = v12 + 18;
      if ( v12 + 18 >= v12 )
      {
LABEL_18:
        v13 = (char *)CoTaskMemAlloc(v10);
        v5 = v13;
        if ( !v13 )
        {
          v6 = -2147024882;
          goto LABEL_36;
        }
        v7 = ((__int64 (__fastcall *)(struct IWICColorContext *, _QWORD, char *, unsigned int *))a2->lpVtbl->GetProfileBytes)(
               a2,
               v25,
               v13 + 18,
               &v25);
        v6 = v7;
        if ( v7 < 0 )
        {
          if ( !(_DWORD)g_doStackCaptures )
            goto LABEL_39;
          goto LABEL_6;
        }
        if ( v11 == 1 )
        {
          v14 = 1;
          do
          {
            v15 = 61442 * ((unsigned int)v14 - 1);
            v16 = ((unsigned int)(unsigned __int16)v25 + 16) >> 8;
            v17 = ((_WORD)v25 + 16) << 8;
            *(_WORD *)&v5[v15] = -7425;
            *(_WORD *)&v5[v15 + 2] = v17 | (unsigned __int8)v16;
            strcpy(&v5[v15 + 4], "ICC_PROFILE");
            v5[v15 + 16] = v14;
            v5[v15 + 17] = 1;
            --v14;
          }
          while ( v14 );
        }
        else
        {
          v18 = v11;
          if ( !(_BYTE)v11 )
          {
LABEL_34:
            v3->bstrblobVal.pData = (BYTE *)v5;
            v5 = 0;
            v3->vt = 65;
            v3->lVal = v10;
            goto LABEL_39;
          }
          do
          {
            v19 = v18 - 1;
            v23 = (unsigned int)(61442 * v19);
            if ( v11 == v18 )
              v20 = v9;
            else
              v20 = -4112;
            LOWORD(puResult) = v20;
            memmove_0(&v5[61442 * v19 + 18], &v5[61424 * v19 + 18], v20);
            v21 = (__int16)puResult;
            *(_WORD *)&v5[v23] = -7425;
            *(_WORD *)&v5[v23 + 2] = ((v21 + 16) << 8) | (unsigned __int8)((unsigned __int16)(v21 + 16) >> 8);
            strcpy(&v5[v23 + 4], "ICC_PROFILE");
            v5[v23 + 16] = v18;
            v5[v23 + 17] = v11;
            --v18;
          }
          while ( v18 );
          v10 = v27;
        }
        v3 = v26;
        goto LABEL_34;
      }
    }
LABEL_35:
    v6 = -2147024362;
LABEL_36:
    if ( (_DWORD)g_doStackCaptures )
    {
      v8 = v6;
      goto LABEL_38;
    }
    goto LABEL_39;
  }
LABEL_5:
  if ( (_DWORD)g_doStackCaptures )
  {
LABEL_6:
    v8 = v7;
LABEL_38:
    DoStackCapture(v8);
  }
LABEL_39:
  CoTaskMemFree(v5);
  return v6;
}

```

## disassembly

```asm
0x1801bc308  mov     [rsp+arg_10], r8
0x1801bc30d  mov     [rsp+puResult], rcx
0x1801bc312  push    rbx
0x1801bc313  push    rbp
0x1801bc314  push    rsi
0x1801bc315  push    rdi
0x1801bc316  push    r12
0x1801bc318  push    r13
0x1801bc31a  push    r14
0x1801bc31c  push    r15
0x1801bc31e  sub     rsp, 48h
0x1801bc322  xor     r13d, r13d
0x1801bc325  mov     r14, r8
0x1801bc328  mov     r12, rdx
0x1801bc32b  mov     ebp, r13d
0x1801bc32e  test    rdx, rdx
0x1801bc331  jnz     short loc_1801BC33D
0x1801bc333  mov     ebx, 80070057h
0x1801bc338  jmp     loc_1801BC633
0x1801bc33d  test    r8, r8
0x1801bc340  jz      short loc_1801BC333
0x1801bc342  xor     eax, eax
0x1801bc344  mov     [rsp+88h+arg_8], r13d
0x1801bc34c  xorps   xmm0, xmm0
0x1801bc34f  lea     r9, [rsp+88h+arg_8]
0x1801bc357  movups  xmmword ptr [r8], xmm0
0x1801bc35b  mov     [r8+10h], rax
0x1801bc35f  mov     rcx, r12
0x1801bc362  mov     rax, [rdx]
0x1801bc365  xor     r8d, r8d
0x1801bc368  xor     edx, edx
0x1801bc36a  mov     rax, [rax+38h]
0x1801bc36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc373  mov     ebx, eax
0x1801bc375  test    eax, eax
0x1801bc377  jns     short loc_1801BC38D
0x1801bc379  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1801bc380  jz      loc_1801BC643
0x1801bc386  mov     ecx, eax
0x1801bc388  jmp     loc_1801BC63E
0x1801bc38d  mov     esi, [rsp+88h+arg_8]
0x1801bc394  mov     r8d, 0EFF0h
0x1801bc39a  cmp     esi, 0FFEFh
0x1801bc3a0  ja      short loc_1801BC3C1
0x1801bc3a2  lea     r15d, [rsi+12h]
0x1801bc3a6  mov     [rsp+88h+arg_18], r15d
0x1801bc3ae  cmp     r15d, esi
0x1801bc3b1  jb      loc_1801BC62E
0x1801bc3b7  mov     edi, 1
0x1801bc3bc  jmp     loc_1801BC45D
0x1801bc3c1  lea     edi, [rsi+0EFEFh]
0x1801bc3c7  cmp     edi, esi
0x1801bc3c9  jb      loc_1801BC62E
0x1801bc3cf  mov     dword ptr [rsp+88h+puResult], edi
0x1801bc3d6  mov     ecx, 1123469Fh
0x1801bc3db  mov     eax, ecx
0x1801bc3dd  mul     edi
0x1801bc3df  sub     edi, edx
0x1801bc3e1  shr     edi, 1
0x1801bc3e3  add     edi, edx
0x1801bc3e5  shr     edi, 0Fh
0x1801bc3e8  cmp     edi, 0FFh
0x1801bc3ee  jb      short loc_1801BC3FA
0x1801bc3f0  mov     ebx, 88982F8Fh
0x1801bc3f5  jmp     loc_1801BC633
0x1801bc3fa  mov     eax, ecx
0x1801bc3fc  lea     ecx, [rdi-1]
0x1801bc3ff  mul     esi
0x1801bc401  mov     eax, esi
0x1801bc403  sub     eax, edx
0x1801bc405  shr     eax, 1
0x1801bc407  add     eax, edx
0x1801bc409  lea     rdx, [rsp+88h+puResult]; puResult
0x1801bc411  shr     eax, 0Fh
0x1801bc414  imul    eax, 0EFF0h
0x1801bc41a  sub     esi, eax
0x1801bc41c  cmovz   esi, r8d
0x1801bc420  imul    rcx, 0F002h; ullOperand
0x1801bc427  call    ULongLongToUInt
0x1801bc42c  mov     ebx, eax
0x1801bc42e  test    eax, eax
0x1801bc430  js      loc_1801BC379
0x1801bc436  mov     eax, dword ptr [rsp+88h+puResult]
0x1801bc43d  lea     ecx, [rax+rsi]
0x1801bc440  cmp     ecx, eax
0x1801bc442  jb      loc_1801BC62E
0x1801bc448  lea     r15d, [rcx+12h]
0x1801bc44c  mov     [rsp+88h+arg_18], r15d
0x1801bc454  cmp     r15d, ecx
0x1801bc457  jb      loc_1801BC62E
0x1801bc45d  mov     ecx, r15d; cb
0x1801bc460  call    cs:__imp_CoTaskMemAlloc
0x1801bc467  nop     dword ptr [rax+rax+00h]
0x1801bc46c  mov     rbp, rax
0x1801bc46f  test    rax, rax
0x1801bc472  jnz     short loc_1801BC47E
0x1801bc474  mov     ebx, 8007000Eh
0x1801bc479  jmp     loc_1801BC633
0x1801bc47e  mov     edx, [rsp+88h+arg_8]
0x1801bc485  lea     r8, [rax+12h]
0x1801bc489  mov     rax, [r12]
0x1801bc48d  lea     r9, [rsp+88h+arg_8]
0x1801bc495  mov     rcx, r12
0x1801bc498  mov     rax, [rax+38h]
0x1801bc49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc4a1  mov     ebx, eax
0x1801bc4a3  test    eax, eax
0x1801bc4a5  jns     short loc_1801BC4BC
0x1801bc4a7  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1801bc4ae  jnz     loc_1801BC386
0x1801bc4b4  test    eax, eax
0x1801bc4b6  js      loc_1801BC643
0x1801bc4bc  cmp     edi, 1
0x1801bc4bf  jnz     loc_1801BC547
0x1801bc4c5  mov     r9b, dil
0x1801bc4c8  test    dil, dil
0x1801bc4cb  jz      loc_1801BC61B
0x1801bc4d1  mov     r10d, 100h
0x1801bc4d7  lea     r13d, [rdi+0Fh]
0x1801bc4db  lea     r11d, [r10-1]
0x1801bc4df  movzx   ecx, word ptr [rsp+88h+arg_8]
0x1801bc4e7  movzx   eax, r9b
0x1801bc4eb  dec     eax
0x1801bc4ed  imul    eax, 0F002h
0x1801bc4f3  lea     edx, [rcx+r13]
0x1801bc4f7  add     cx, r13w
0x1801bc4fb  shr     edx, 8
0x1801bc4fe  and     dx, r11w
0x1801bc502  movzx   ecx, cx
0x1801bc505  imul    ecx, r10d
0x1801bc509  mov     r8d, eax
0x1801bc50c  mov     word ptr [rax+rbp], 0E2FFh
0x1801bc512  or      dx, cx
0x1801bc515  mov     [rax+rbp+2], dx
0x1801bc51a  movsd   xmm0, cs:qword_18024EA20
0x1801bc522  movsd   qword ptr [rax+rbp+4], xmm0
0x1801bc528  mov     eax, cs:dword_18024EA28
0x1801bc52e  mov     [r8+rbp+0Ch], eax
0x1801bc533  mov     [r8+rbp+10h], r9b
0x1801bc538  mov     [r8+rbp+11h], dil
0x1801bc53d  add     r9b, r11b
0x1801bc540  jnz     short loc_1801BC4DF
0x1801bc542  jmp     loc_1801BC610
0x1801bc547  mov     r12b, dil
0x1801bc54a  test    dil, dil
0x1801bc54d  jz      loc_1801BC61B
0x1801bc553  mov     r13d, 10h
0x1801bc559  mov     r15d, 100h
0x1801bc55f  movzx   ecx, r12b
0x1801bc563  lea     edx, [rcx-1]
0x1801bc566  imul    r9d, edx, 0F002h
0x1801bc56d  mov     [rsp+88h+var_58], r9
0x1801bc572  cmp     edi, ecx
0x1801bc574  jz      short loc_1801BC57D
0x1801bc576  mov     eax, 0EFF0h
0x1801bc57b  jmp     short loc_1801BC580
0x1801bc57d  movzx   eax, si
0x1801bc580  imul    edx, 0EFF0h
0x1801bc586  mov     word ptr [rsp+88h+puResult], ax
0x1801bc58e  movzx   r8d, ax; Size
0x1801bc592  lea     rax, [rbp+12h]
0x1801bc596  lea     rcx, [r9+rax]; void *
0x1801bc59a  add     rdx, rax; Src
0x1801bc59d  call    memmove_0
0x1801bc5a2  mov     r8, [rsp+88h+var_58]
0x1801bc5a7  mov     r9d, 0FFh
0x1801bc5ad  movzx   ecx, word ptr [rsp+88h+puResult]
0x1801bc5b5  mov     word ptr [r8+rbp], 0E2FFh
0x1801bc5bc  lea     edx, [rcx+r13]
0x1801bc5c0  add     cx, r13w
0x1801bc5c4  shr     edx, 8
0x1801bc5c7  and     dx, r9w
0x1801bc5cb  movzx   ecx, cx
0x1801bc5ce  imul    ecx, r15d
0x1801bc5d2  or      dx, cx
0x1801bc5d5  mov     [r8+rbp+2], dx
0x1801bc5db  movsd   xmm0, cs:qword_18024EA20
0x1801bc5e3  movsd   qword ptr [r8+rbp+4], xmm0
0x1801bc5ea  mov     eax, cs:dword_18024EA28
0x1801bc5f0  mov     [r8+rbp+0Ch], eax
0x1801bc5f5  mov     [r8+rbp+10h], r12b
0x1801bc5fa  mov     [r8+rbp+11h], dil
0x1801bc5ff  add     r12b, r9b
0x1801bc602  jnz     loc_1801BC55F
0x1801bc608  mov     r15d, [rsp+88h+arg_18]
0x1801bc610  mov     r14, [rsp+88h+arg_10]
0x1801bc618  xor     r13d, r13d
0x1801bc61b  mov     [r14+10h], rbp
0x1801bc61f  mov     rbp, r13
0x1801bc622  mov     word ptr [r14], 41h ; 'A'
0x1801bc628  mov     [r14+8], r15d
0x1801bc62c  jmp     short loc_1801BC643
0x1801bc62e  mov     ebx, 80070216h
0x1801bc633  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1801bc63a  jz      short loc_1801BC643
0x1801bc63c  mov     ecx, ebx; int
0x1801bc63e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801bc643  mov     rcx, rbp; pv
0x1801bc646  call    cs:__imp_CoTaskMemFree
0x1801bc64d  nop     dword ptr [rax+rax+00h]
0x1801bc652  mov     eax, ebx
0x1801bc654  add     rsp, 48h
0x1801bc658  pop     r15
0x1801bc65a  pop     r14
0x1801bc65c  pop     r13
0x1801bc65e  pop     r12
0x1801bc660  pop     rdi
0x1801bc661  pop     rsi
0x1801bc662  pop     rbp
0x1801bc663  pop     rbx
0x1801bc664  retn
```
