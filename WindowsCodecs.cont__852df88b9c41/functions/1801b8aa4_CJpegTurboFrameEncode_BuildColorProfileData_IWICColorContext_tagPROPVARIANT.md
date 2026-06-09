# CJpegTurboFrameEncode::BuildColorProfileData(IWICColorContext *,tagPROPVARIANT *)

- ea: `0x1801b8aa4`
- end: `0x1801b8df5`
- name: `?BuildColorProfileData@CJpegTurboFrameEncode@@AEAAJPEAUIWICColorContext@@PEAUtagPROPVARIANT@@@Z`
- size: `849`
- prototype: `__int64 __fastcall(CJpegTurboFrameEncode *__hidden this, struct IWICColorContext *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e9f4`

## callees

- `0x18006ac40`
- `0x1800bb784`
- `0x18017b534`
- `0x1801b8aa4`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b8bfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b8bfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b8ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b8ddc`

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
0x1801b8aa4  mov     [rsp+arg_10], r8
0x1801b8aa9  mov     [rsp+puResult], rcx
0x1801b8aae  push    rbx
0x1801b8aaf  push    rbp
0x1801b8ab0  push    rsi
0x1801b8ab1  push    rdi
0x1801b8ab2  push    r12
0x1801b8ab4  push    r13
0x1801b8ab6  push    r14
0x1801b8ab8  push    r15
0x1801b8aba  sub     rsp, 48h
0x1801b8abe  xor     r13d, r13d
0x1801b8ac1  mov     r14, r8
0x1801b8ac4  mov     r12, rdx
0x1801b8ac7  mov     ebp, r13d
0x1801b8aca  test    rdx, rdx
0x1801b8acd  jnz     short loc_1801B8AD9
0x1801b8acf  mov     ebx, 80070057h
0x1801b8ad4  jmp     loc_1801B8DC9
0x1801b8ad9  test    r8, r8
0x1801b8adc  jz      short loc_1801B8ACF
0x1801b8ade  xor     eax, eax
0x1801b8ae0  mov     [rsp+88h+arg_8], r13d
0x1801b8ae8  xorps   xmm0, xmm0
0x1801b8aeb  lea     r9, [rsp+88h+arg_8]
0x1801b8af3  movups  xmmword ptr [r8], xmm0
0x1801b8af7  mov     [r8+10h], rax
0x1801b8afb  mov     rcx, r12
0x1801b8afe  mov     rax, [rdx]
0x1801b8b01  xor     r8d, r8d
0x1801b8b04  xor     edx, edx
0x1801b8b06  mov     rax, [rax+38h]
0x1801b8b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8b0f  mov     ebx, eax
0x1801b8b11  test    eax, eax
0x1801b8b13  jns     short loc_1801B8B29
0x1801b8b15  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1801b8b1c  jz      loc_1801B8DD9
0x1801b8b22  mov     ecx, eax
0x1801b8b24  jmp     loc_1801B8DD4
0x1801b8b29  mov     esi, [rsp+88h+arg_8]
0x1801b8b30  mov     r8d, 0EFF0h
0x1801b8b36  cmp     esi, 0FFEFh
0x1801b8b3c  ja      short loc_1801B8B5D
0x1801b8b3e  lea     r15d, [rsi+12h]
0x1801b8b42  mov     [rsp+88h+arg_18], r15d
0x1801b8b4a  cmp     r15d, esi
0x1801b8b4d  jb      loc_1801B8DC4
0x1801b8b53  mov     edi, 1
0x1801b8b58  jmp     loc_1801B8BF9
0x1801b8b5d  lea     edi, [rsi+0EFEFh]
0x1801b8b63  cmp     edi, esi
0x1801b8b65  jb      loc_1801B8DC4
0x1801b8b6b  mov     dword ptr [rsp+88h+puResult], edi
0x1801b8b72  mov     ecx, 1123469Fh
0x1801b8b77  mov     eax, ecx
0x1801b8b79  mul     edi
0x1801b8b7b  sub     edi, edx
0x1801b8b7d  shr     edi, 1
0x1801b8b7f  add     edi, edx
0x1801b8b81  shr     edi, 0Fh
0x1801b8b84  cmp     edi, 0FFh
0x1801b8b8a  jb      short loc_1801B8B96
0x1801b8b8c  mov     ebx, 88982F8Fh
0x1801b8b91  jmp     loc_1801B8DC9
0x1801b8b96  mov     eax, ecx
0x1801b8b98  lea     ecx, [rdi-1]
0x1801b8b9b  mul     esi
0x1801b8b9d  mov     eax, esi
0x1801b8b9f  sub     eax, edx
0x1801b8ba1  shr     eax, 1
0x1801b8ba3  add     eax, edx
0x1801b8ba5  lea     rdx, [rsp+88h+puResult]; puResult
0x1801b8bad  shr     eax, 0Fh
0x1801b8bb0  imul    eax, 0EFF0h
0x1801b8bb6  sub     esi, eax
0x1801b8bb8  cmovz   esi, r8d
0x1801b8bbc  imul    rcx, 0F002h; ullOperand
0x1801b8bc3  call    ULongLongToUInt
0x1801b8bc8  mov     ebx, eax
0x1801b8bca  test    eax, eax
0x1801b8bcc  js      loc_1801B8B15
0x1801b8bd2  mov     eax, dword ptr [rsp+88h+puResult]
0x1801b8bd9  lea     ecx, [rax+rsi]
0x1801b8bdc  cmp     ecx, eax
0x1801b8bde  jb      loc_1801B8DC4
0x1801b8be4  lea     r15d, [rcx+12h]
0x1801b8be8  mov     [rsp+88h+arg_18], r15d
0x1801b8bf0  cmp     r15d, ecx
0x1801b8bf3  jb      loc_1801B8DC4
0x1801b8bf9  mov     ecx, r15d; cb
0x1801b8bfc  call    cs:__imp_CoTaskMemAlloc
0x1801b8c02  mov     rbp, rax
0x1801b8c05  test    rax, rax
0x1801b8c08  jnz     short loc_1801B8C14
0x1801b8c0a  mov     ebx, 8007000Eh
0x1801b8c0f  jmp     loc_1801B8DC9
0x1801b8c14  mov     edx, [rsp+88h+arg_8]
0x1801b8c1b  lea     r8, [rax+12h]
0x1801b8c1f  mov     rax, [r12]
0x1801b8c23  lea     r9, [rsp+88h+arg_8]
0x1801b8c2b  mov     rcx, r12
0x1801b8c2e  mov     rax, [rax+38h]
0x1801b8c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8c37  mov     ebx, eax
0x1801b8c39  test    eax, eax
0x1801b8c3b  jns     short loc_1801B8C52
0x1801b8c3d  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1801b8c44  jnz     loc_1801B8B22
0x1801b8c4a  test    eax, eax
0x1801b8c4c  js      loc_1801B8DD9
0x1801b8c52  cmp     edi, 1
0x1801b8c55  jnz     loc_1801B8CDD
0x1801b8c5b  mov     r9b, dil
0x1801b8c5e  test    dil, dil
0x1801b8c61  jz      loc_1801B8DB1
0x1801b8c67  mov     r10d, 100h
0x1801b8c6d  lea     r13d, [rdi+0Fh]
0x1801b8c71  lea     r11d, [r10-1]
0x1801b8c75  movzx   ecx, word ptr [rsp+88h+arg_8]
0x1801b8c7d  movzx   eax, r9b
0x1801b8c81  dec     eax
0x1801b8c83  imul    eax, 0F002h
0x1801b8c89  lea     edx, [rcx+r13]
0x1801b8c8d  add     cx, r13w
0x1801b8c91  shr     edx, 8
0x1801b8c94  and     dx, r11w
0x1801b8c98  movzx   ecx, cx
0x1801b8c9b  imul    ecx, r10d
0x1801b8c9f  mov     r8d, eax
0x1801b8ca2  mov     word ptr [rax+rbp], 0E2FFh
0x1801b8ca8  or      dx, cx
0x1801b8cab  mov     [rax+rbp+2], dx
0x1801b8cb0  movsd   xmm0, cs:qword_18024AAC0
0x1801b8cb8  movsd   qword ptr [rax+rbp+4], xmm0
0x1801b8cbe  mov     eax, cs:dword_18024AAC8
0x1801b8cc4  mov     [r8+rbp+0Ch], eax
0x1801b8cc9  mov     [r8+rbp+10h], r9b
0x1801b8cce  mov     [r8+rbp+11h], dil
0x1801b8cd3  add     r9b, r11b
0x1801b8cd6  jnz     short loc_1801B8C75
0x1801b8cd8  jmp     loc_1801B8DA6
0x1801b8cdd  mov     r12b, dil
0x1801b8ce0  test    dil, dil
0x1801b8ce3  jz      loc_1801B8DB1
0x1801b8ce9  mov     r13d, 10h
0x1801b8cef  mov     r15d, 100h
0x1801b8cf5  movzx   ecx, r12b
0x1801b8cf9  lea     edx, [rcx-1]
0x1801b8cfc  imul    r9d, edx, 0F002h
0x1801b8d03  mov     [rsp+88h+var_58], r9
0x1801b8d08  cmp     edi, ecx
0x1801b8d0a  jz      short loc_1801B8D13
0x1801b8d0c  mov     eax, 0EFF0h
0x1801b8d11  jmp     short loc_1801B8D16
0x1801b8d13  movzx   eax, si
0x1801b8d16  imul    edx, 0EFF0h
0x1801b8d1c  mov     word ptr [rsp+88h+puResult], ax
0x1801b8d24  movzx   r8d, ax; Size
0x1801b8d28  lea     rax, [rbp+12h]
0x1801b8d2c  lea     rcx, [r9+rax]; void *
0x1801b8d30  add     rdx, rax; Src
0x1801b8d33  call    memmove_0
0x1801b8d38  mov     r8, [rsp+88h+var_58]
0x1801b8d3d  mov     r9d, 0FFh
0x1801b8d43  movzx   ecx, word ptr [rsp+88h+puResult]
0x1801b8d4b  mov     word ptr [r8+rbp], 0E2FFh
0x1801b8d52  lea     edx, [rcx+r13]
0x1801b8d56  add     cx, r13w
0x1801b8d5a  shr     edx, 8
0x1801b8d5d  and     dx, r9w
0x1801b8d61  movzx   ecx, cx
0x1801b8d64  imul    ecx, r15d
0x1801b8d68  or      dx, cx
0x1801b8d6b  mov     [r8+rbp+2], dx
0x1801b8d71  movsd   xmm0, cs:qword_18024AAC0
0x1801b8d79  movsd   qword ptr [r8+rbp+4], xmm0
0x1801b8d80  mov     eax, cs:dword_18024AAC8
0x1801b8d86  mov     [r8+rbp+0Ch], eax
0x1801b8d8b  mov     [r8+rbp+10h], r12b
0x1801b8d90  mov     [r8+rbp+11h], dil
0x1801b8d95  add     r12b, r9b
0x1801b8d98  jnz     loc_1801B8CF5
0x1801b8d9e  mov     r15d, [rsp+88h+arg_18]
0x1801b8da6  mov     r14, [rsp+88h+arg_10]
0x1801b8dae  xor     r13d, r13d
0x1801b8db1  mov     [r14+10h], rbp
0x1801b8db5  mov     rbp, r13
0x1801b8db8  mov     word ptr [r14], 41h ; 'A'
0x1801b8dbe  mov     [r14+8], r15d
0x1801b8dc2  jmp     short loc_1801B8DD9
0x1801b8dc4  mov     ebx, 80070216h
0x1801b8dc9  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1801b8dd0  jz      short loc_1801B8DD9
0x1801b8dd2  mov     ecx, ebx; int
0x1801b8dd4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b8dd9  mov     rcx, rbp; pv
0x1801b8ddc  call    cs:__imp_CoTaskMemFree
0x1801b8de2  mov     eax, ebx
0x1801b8de4  add     rsp, 48h
0x1801b8de8  pop     r15
0x1801b8dea  pop     r14
0x1801b8dec  pop     r13
0x1801b8dee  pop     r12
0x1801b8df0  pop     rdi
0x1801b8df1  pop     rsi
0x1801b8df2  pop     rbp
0x1801b8df3  pop     rbx
0x1801b8df4  retn
```
