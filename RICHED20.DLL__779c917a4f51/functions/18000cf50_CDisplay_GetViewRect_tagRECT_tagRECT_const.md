# CDisplay::GetViewRect(tagRECT &,tagRECT const *)

- ea: `0x18000cf50`
- end: `0x18000d49a`
- name: `?GetViewRect@CDisplay@@QEAAXAEAUtagRECT@@PEBU2@@Z`
- size: `1354`
- prototype: `void __fastcall(CDisplay *__hidden this, struct tagRECT *, const struct tagRECT *)`
- caller_count: `27`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c070`
- `0x18000e200`
- `0x18000feb0`
- `0x18001dc00`
- `0x1800385d0`
- `0x18003a3b4`
- `0x18003e9b0`
- `0x180044160`
- `0x18005519c`
- `0x180056764`
- `0x1800569c4`
- `0x180056b70`
- `0x180056fb0`
- `0x1800579f0`
- `0x1800587b0`
- `0x180058950`
- `0x180058e50`
- `0x1800592b0`
- `0x18005bc94`
- `0x18005c674`
- `0x18006e564`
- `0x18007fab0`
- `0x18007fe10`
- `0x1800807d8`
- `0x1800828d0`
- `0x1800884d0`
- `0x180089480`

## callees

- `0x18000cf50`
- `0x18000d4a0`
- `0x18000d53c`
- `0x180035dd0`
- `0x180038bd0`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18000d061`
- `KERNEL32!MulDiv` at `0x18000d2f8`
- `KERNEL32!MulDiv` at `0x18000d30c`
- `KERNEL32!MulDiv` at `0x18000d328`
- `KERNEL32!MulDiv` at `0x18000d33c`
- `KERNEL32!MulDiv` at `0x18000d353`
- `KERNEL32!MulDiv` at `0x18000d364`
- `KERNEL32!MulDiv` at `0x18000d37b`
- `KERNEL32!MulDiv` at `0x18000d3e3`
- `KERNEL32!MulDiv` at `0x18000d408`
- `KERNEL32!MulDiv` at `0x18000d42d`
- `KERNEL32!MulDiv` at `0x18000d061`
- `KERNEL32!MulDiv` at `0x18000d2f8`
- `KERNEL32!MulDiv` at `0x18000d30c`
- `KERNEL32!MulDiv` at `0x18000d328`
- `KERNEL32!MulDiv` at `0x18000d33c`
- `KERNEL32!MulDiv` at `0x18000d353`
- `KERNEL32!MulDiv` at `0x18000d364`
- `KERNEL32!MulDiv` at `0x18000d37b`
- `KERNEL32!MulDiv` at `0x18000d3e3`
- `KERNEL32!MulDiv` at `0x18000d408`
- `KERNEL32!MulDiv` at `0x18000d42d`

## pseudocode

```c
void __fastcall CDisplay::GetViewRect(CDisplay *this, struct tagRECT *a2, const struct tagRECT *a3)
{
  __int64 v5; // rax
  int v6; // r9d
  int v7; // esi
  int v8; // r12d
  __int64 v9; // rax
  int v10; // esi
  int v11; // edx
  int v12; // edx
  int v13; // r13d
  int ZoomDenominator; // eax
  __int64 v15; // rcx
  int v16; // edx
  int v17; // edx
  __int64 v18; // rax
  int v19; // r12d
  int v20; // esi
  int v21; // edx
  int v22; // edx
  int v23; // eax
  int v24; // ecx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  int v29; // r12d
  int v30; // esi
  int v31; // edx
  int v32; // edx
  int v33; // edx
  int v34; // eax
  int v35; // edx
  int v36; // eax
  int v37; // edx
  int v38; // eax
  int nNumber; // [rsp+20h] [rbp-38h] BYREF
  int v40[2]; // [rsp+28h] [rbp-30h] BYREF
  int v41; // [rsp+30h] [rbp-28h] BYREF
  int v42; // [rsp+34h] [rbp-24h]
  int v43[4]; // [rsp+38h] [rbp-20h] BYREF

  if ( a3 )
    *a2 = *a3;
  else
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 48LL) + 192LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 48LL));
  *((_DWORD *)this + 17) = a2->bottom - a2->top;
  v5 = *((_QWORD *)this + 2);
  *(_OWORD *)v43 = 0;
  if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v5 + 48) + 200LL))(*(_QWORD *)(v5 + 48), v43) < 0 )
  {
    v19 = 0;
    v13 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
    v23 = 0;
    v24 = _mm_cvtsi128_si32((__m128i)0LL);
    goto LABEL_49;
  }
  v6 = v43[0];
  v7 = v43[2];
  v8 = v43[1];
  nNumber = v43[0];
  v42 = v43[2];
  v41 = v43[3];
  if ( !v43[0] )
  {
    nNumber = 0;
    goto LABEL_20;
  }
  v9 = *((_QWORD *)this + 2);
  if ( !*(_WORD *)(v9 + 204) )
  {
    v10 = *((_DWORD *)this + 19);
    if ( v10 )
    {
      v35 = *((__int16 *)this + 19);
      if ( v35 == 2540 )
      {
LABEL_9:
        v6 = nNumber;
        if ( v10 <= 0 )
          v10 = 1;
        goto LABEL_11;
      }
      v36 = MulDiv(v10, v35, 2540);
    }
    else
    {
      v10 = *((_DWORD *)this + 17);
      *(_QWORD *)v40 = 0;
      if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v9 + 48) + 272LL))(*(_QWORD *)(v9 + 48), v40) < 0 )
      {
LABEL_8:
        v9 = *((_QWORD *)this + 2);
        goto LABEL_9;
      }
      v36 = CW32System::MulDiv(v40[1], *((__int16 *)this + 19), 2540);
    }
    v10 = v36;
    goto LABEL_8;
  }
  v10 = *(unsigned __int16 *)(v9 + 204);
LABEL_11:
  v11 = *(unsigned __int16 *)(v9 + 202);
  if ( !*(_WORD *)(v9 + 202) )
  {
    v11 = 1;
    if ( *((int *)this + 17) > 0 )
      v11 = *((_DWORD *)this + 17);
  }
  if ( v11 != v10 )
  {
    v6 = MulDiv(v6, v11, v10);
    nNumber = v6;
  }
  v12 = *((__int16 *)this + 18);
  if ( v12 != 2540 && v6 )
    nNumber = MulDiv(v6, v12, 2540);
  v7 = v42;
LABEL_20:
  if ( v8 )
  {
    v13 = v43[1];
    ZoomDenominator = CDisplay::GetZoomDenominator(this);
    v15 = *((_QWORD *)this + 2);
    v16 = *(unsigned __int16 *)(v15 + 202);
    if ( !*(_WORD *)(v15 + 202) )
    {
      v16 = 1;
      if ( *((int *)this + 17) > 0 )
        v16 = *((_DWORD *)this + 17);
    }
    if ( v16 != ZoomDenominator && (!ZoomDenominator || v13) )
      v13 = MulDiv(v13, v16, ZoomDenominator);
    v17 = *((__int16 *)this + 19);
    if ( v17 != 2540 && v13 )
      v13 = MulDiv(v13, v17, 2540);
  }
  else
  {
    v13 = 0;
  }
  if ( v7 )
  {
    v18 = *((_QWORD *)this + 2);
    v19 = v43[2];
    if ( *(_WORD *)(v18 + 204) )
    {
      v20 = *(unsigned __int16 *)(v18 + 204);
LABEL_37:
      v21 = *(unsigned __int16 *)(v18 + 202);
      if ( !*(_WORD *)(v18 + 202) )
      {
        v21 = 1;
        if ( *((int *)this + 17) > 0 )
          v21 = *((_DWORD *)this + 17);
      }
      if ( v21 != v20 && v19 )
        v19 = MulDiv(v19, v21, v20);
      v22 = *((__int16 *)this + 18);
      if ( v22 != 2540 && v19 )
        v19 = MulDiv(v19, v22, 2540);
      goto LABEL_46;
    }
    v20 = *((_DWORD *)this + 19);
    if ( v20 )
    {
      v37 = *((__int16 *)this + 19);
      if ( v37 == 2540 )
      {
LABEL_35:
        if ( v20 <= 0 )
          v20 = 1;
        goto LABEL_37;
      }
      v38 = MulDiv(v20, v37, 2540);
    }
    else
    {
      v20 = *((_DWORD *)this + 17);
      *(_QWORD *)v40 = 0;
      if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v18 + 48) + 272LL))(*(_QWORD *)(v18 + 48), v40) < 0 )
      {
LABEL_34:
        v18 = *((_QWORD *)this + 2);
        goto LABEL_35;
      }
      v38 = CW32System::MulDiv(v40[1], *((__int16 *)this + 19), 2540);
    }
    v20 = v38;
    goto LABEL_34;
  }
  v19 = 0;
LABEL_46:
  if ( v41 )
    v23 = CDisplay::HimetricYtoDY(this, v43[3]);
  else
    v23 = 0;
  v24 = nNumber;
LABEL_49:
  a2->left += v24;
  a2->top += v13;
  a2->right -= v19;
  a2->bottom -= v23;
  v25 = *((_QWORD *)this + 2);
  if ( (*(_DWORD *)(v25 + 180) & 0x2000000) != 0 )
  {
    v26 = *(_QWORD *)(v25 + 48);
    v41 = 0;
    nNumber = 0;
    (*(void (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v26 + 400LL))(v26, &v41, &nNumber);
    if ( (nNumber & 0x4000) != 0 )
    {
      a2->right -= CDisplay::GetSelBarInPixels(this);
      return;
    }
  }
  v27 = *((_QWORD *)this + 2);
  nNumber = 0;
  (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v27 + 48) + 328LL))(*(_QWORD *)(v27 + 48), &nNumber);
  v28 = *((_QWORD *)this + 2);
  v29 = nNumber;
  if ( !*(_WORD *)(v28 + 204) )
  {
    v30 = *((_DWORD *)this + 19);
    if ( v30 )
    {
      v33 = *((__int16 *)this + 19);
      if ( v33 == 2540 )
      {
LABEL_55:
        if ( v30 <= 0 )
          v30 = 1;
        goto LABEL_57;
      }
      v34 = MulDiv(v30, v33, 2540);
    }
    else
    {
      v30 = *((_DWORD *)this + 17);
      *(_QWORD *)v40 = 0;
      if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v28 + 48) + 272LL))(*(_QWORD *)(v28 + 48), v40) < 0 )
      {
LABEL_54:
        v28 = *((_QWORD *)this + 2);
        goto LABEL_55;
      }
      v34 = CW32System::MulDiv(v40[1], *((__int16 *)this + 19), 2540);
    }
    v30 = v34;
    goto LABEL_54;
  }
  v30 = *(unsigned __int16 *)(v28 + 204);
LABEL_57:
  v31 = *(unsigned __int16 *)(v28 + 202);
  if ( !*(_WORD *)(v28 + 202) )
  {
    v31 = 1;
    if ( *((int *)this + 17) > 0 )
      v31 = *((_DWORD *)this + 17);
  }
  if ( v31 != v30 && v29 )
    v29 = MulDiv(v29, v31, v30);
  v32 = *((__int16 *)this + 18);
  if ( v32 != 2540 )
  {
    if ( v29 )
      v29 = MulDiv(v29, v32, 2540);
  }
  a2->left += v29;
}

```

## disassembly

```asm
0x18000cf50  push    rbp
0x18000cf52  push    rbx
0x18000cf53  push    rdi
0x18000cf54  push    r12
0x18000cf56  push    r13
0x18000cf58  push    r14
0x18000cf5a  mov     rbp, rsp
0x18000cf5d  sub     rsp, 58h
0x18000cf61  mov     rax, cs:__security_cookie
0x18000cf68  xor     rax, rsp
0x18000cf6b  mov     [rbp+var_10], rax
0x18000cf6f  mov     rbx, rdx
0x18000cf72  mov     rdi, rcx
0x18000cf75  test    r8, r8
0x18000cf78  jz      loc_18000D39E
0x18000cf7e  movups  xmm0, xmmword ptr [r8]
0x18000cf82  movups  xmmword ptr [rdx], xmm0
0x18000cf85  mov     eax, [rbx+0Ch]
0x18000cf88  lea     rdx, [rbp+var_20]
0x18000cf8c  sub     eax, [rbx+4]
0x18000cf8f  xorps   xmm0, xmm0
0x18000cf92  mov     [rdi+44h], eax
0x18000cf95  mov     rax, [rdi+10h]
0x18000cf99  movups  xmmword ptr [rbp+var_20], xmm0
0x18000cf9d  mov     [rsp+58h+arg_10], rsi
0x18000cfa5  mov     [rsp+58h+var_8], r15
0x18000cfaa  mov     rcx, [rax+30h]
0x18000cfae  mov     rax, [rcx]
0x18000cfb1  mov     rax, [rax+0C8h]
0x18000cfb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfbd  xor     r15d, r15d
0x18000cfc0  test    eax, eax
0x18000cfc2  js      loc_18000D2D3
0x18000cfc8  mov     r9d, [rbp+var_20]
0x18000cfcc  mov     esi, [rbp+var_20+8]
0x18000cfcf  mov     eax, [rbp+var_20+0Ch]
0x18000cfd2  mov     r12d, [rbp+var_20+4]
0x18000cfd6  mov     [rbp+nNumber], r9d
0x18000cfda  mov     [rbp+var_24], esi
0x18000cfdd  mov     [rbp+var_28], eax
0x18000cfe0  test    r9d, r9d
0x18000cfe3  jz      loc_18000D45E
0x18000cfe9  mov     rax, [rdi+10h]
0x18000cfed  movzx   ecx, word ptr [rax+0CCh]
0x18000cff4  test    cx, cx
0x18000cff7  jnz     loc_18000D390
0x18000cffd  mov     esi, [rdi+4Ch]
0x18000d000  test    esi, esi
0x18000d002  jnz     loc_18000D3F0
0x18000d008  mov     esi, [rdi+44h]
0x18000d00b  lea     rdx, [rbp+var_30]
0x18000d00f  mov     qword ptr [rbp+var_30], r15
0x18000d013  mov     rcx, [rax+30h]
0x18000d017  mov     rax, [rcx]
0x18000d01a  mov     rax, [rax+110h]
0x18000d021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d026  test    eax, eax
0x18000d028  jns     loc_18000D44A
0x18000d02e  mov     rax, [rdi+10h]
0x18000d032  mov     r9d, [rbp+nNumber]
0x18000d036  test    esi, esi
0x18000d038  jg      short loc_18000D03F
0x18000d03a  mov     esi, 1
0x18000d03f  movzx   edx, word ptr [rax+0CAh]
0x18000d046  test    edx, edx
0x18000d048  jnz     short loc_18000D057
0x18000d04a  mov     eax, [rdi+44h]
0x18000d04d  mov     edx, 1
0x18000d052  test    eax, eax
0x18000d054  cmovg   edx, eax; nNumerator
0x18000d057  cmp     edx, esi
0x18000d059  jz      short loc_18000D06D
0x18000d05b  mov     r8d, esi; nDenominator
0x18000d05e  mov     ecx, r9d; nNumber
0x18000d061  call    cs:__imp_MulDiv
0x18000d067  mov     r9d, eax
0x18000d06a  mov     [rbp+nNumber], eax
0x18000d06d  movsx   edx, word ptr [rdi+24h]; nNumerator
0x18000d071  cmp     edx, 9ECh
0x18000d077  jz      short loc_18000D082
0x18000d079  test    r9d, r9d
0x18000d07c  jnz     loc_18000D31F
0x18000d082  mov     esi, [rbp+var_24]
0x18000d085  test    r12d, r12d
0x18000d088  jz      loc_18000D317
0x18000d08e  mov     r13d, [rbp+var_20+4]
0x18000d092  mov     rcx, rdi; this
0x18000d095  call    ?GetZoomDenominator@CDisplay@@QEBAJXZ; CDisplay::GetZoomDenominator(void)
0x18000d09a  mov     rcx, [rdi+10h]
0x18000d09e  mov     r8d, eax; nDenominator
0x18000d0a1  movzx   edx, word ptr [rcx+0CAh]
0x18000d0a8  test    edx, edx
0x18000d0aa  jnz     short loc_18000D0B9
0x18000d0ac  mov     eax, [rdi+44h]
0x18000d0af  mov     edx, 1
0x18000d0b4  test    eax, eax
0x18000d0b6  cmovg   edx, eax; nNumerator
0x18000d0b9  cmp     edx, r8d
0x18000d0bc  jz      short loc_18000D0D0
0x18000d0be  test    r8d, r8d
0x18000d0c1  jz      loc_18000D361
0x18000d0c7  test    r13d, r13d
0x18000d0ca  jnz     loc_18000D361
0x18000d0d0  movsx   edx, word ptr [rdi+26h]; nNumerator
0x18000d0d4  test    r15b, r15b
0x18000d0d7  jnz     short loc_18000D0EA
0x18000d0d9  cmp     edx, 9ECh
0x18000d0df  jz      short loc_18000D0EA
0x18000d0e1  test    r13d, r13d
0x18000d0e4  jnz     loc_18000D372
0x18000d0ea  test    esi, esi
0x18000d0ec  jz      loc_18000D47B
0x18000d0f2  mov     rax, [rdi+10h]
0x18000d0f6  mov     r12d, [rbp+var_20+8]
0x18000d0fa  movzx   ecx, word ptr [rax+0CCh]
0x18000d101  test    cx, cx
0x18000d104  jnz     loc_18000D397
0x18000d10a  mov     esi, [rdi+4Ch]
0x18000d10d  test    esi, esi
0x18000d10f  jnz     loc_18000D415
0x18000d115  mov     esi, [rdi+44h]
0x18000d118  lea     rdx, [rbp+var_30]
0x18000d11c  mov     qword ptr [rbp+var_30], r15
0x18000d120  mov     rcx, [rax+30h]
0x18000d124  mov     rax, [rcx]
0x18000d127  mov     rax, [rax+110h]
0x18000d12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d133  test    eax, eax
0x18000d135  jns     loc_18000D467
0x18000d13b  mov     rax, [rdi+10h]
0x18000d13f  test    esi, esi
0x18000d141  jle     loc_18000D2C9
0x18000d147  movzx   edx, word ptr [rax+0CAh]
0x18000d14e  test    edx, edx
0x18000d150  jnz     short loc_18000D15F
0x18000d152  mov     eax, [rdi+44h]
0x18000d155  mov     edx, 1
0x18000d15a  test    eax, eax
0x18000d15c  cmovg   edx, eax; nNumerator
0x18000d15f  cmp     edx, esi
0x18000d161  jz      short loc_18000D174
0x18000d163  test    esi, esi
0x18000d165  jz      loc_18000D336
0x18000d16b  test    r12d, r12d
0x18000d16e  jnz     loc_18000D336
0x18000d174  movsx   edx, word ptr [rdi+24h]; nNumerator
0x18000d178  test    r15b, r15b
0x18000d17b  jnz     short loc_18000D18E
0x18000d17d  cmp     edx, 9ECh
0x18000d183  jz      short loc_18000D18E
0x18000d185  test    r12d, r12d
0x18000d188  jnz     loc_18000D34A
0x18000d18e  cmp     [rbp+var_28], 0
0x18000d192  jnz     loc_18000D43A
0x18000d198  mov     eax, r15d
0x18000d19b  mov     ecx, [rbp+nNumber]
0x18000d19e  add     [rbx], ecx
0x18000d1a0  add     [rbx+4], r13d
0x18000d1a4  sub     [rbx+8], r12d
0x18000d1a8  sub     [rbx+0Ch], eax
0x18000d1ab  mov     rcx, [rdi+10h]
0x18000d1af  test    dword ptr [rcx+0B4h], 2000000h
0x18000d1b9  jz      short loc_18000D1EB
0x18000d1bb  mov     rcx, [rcx+30h]
0x18000d1bf  lea     r8, [rbp+nNumber]
0x18000d1c3  mov     [rbp+var_28], r15d
0x18000d1c7  lea     rdx, [rbp+var_28]
0x18000d1cb  mov     [rbp+nNumber], r15d
0x18000d1cf  mov     rax, [rcx]
0x18000d1d2  mov     rax, [rax+190h]
0x18000d1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1de  test    [rbp+nNumber], 4000h
0x18000d1e5  jnz     loc_18000D3BA
0x18000d1eb  mov     rax, [rdi+10h]
0x18000d1ef  lea     rdx, [rbp+nNumber]
0x18000d1f3  mov     [rbp+nNumber], r15d
0x18000d1f7  lea     r13, [rdi+26h]
0x18000d1fb  mov     rcx, [rax+30h]
0x18000d1ff  mov     rax, [rcx]
0x18000d202  mov     rax, [rax+148h]
0x18000d209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d20e  mov     rax, [rdi+10h]
0x18000d212  mov     r12d, [rbp+nNumber]
0x18000d216  movzx   ecx, word ptr [rax+0CCh]
0x18000d21d  test    cx, cx
0x18000d220  jnz     loc_18000D389
0x18000d226  mov     esi, [rdi+4Ch]
0x18000d229  test    esi, esi
0x18000d22b  jnz     loc_18000D3CA
0x18000d231  mov     esi, [rdi+44h]
0x18000d234  lea     rdx, [rbp+var_30]
0x18000d238  mov     qword ptr [rbp+var_30], r15
0x18000d23c  mov     rcx, [rax+30h]
0x18000d240  mov     rax, [rcx]
0x18000d243  mov     rax, [rax+110h]
0x18000d24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d24f  test    eax, eax
0x18000d251  jns     loc_18000D483
0x18000d257  mov     rax, [rdi+10h]
0x18000d25b  test    esi, esi
0x18000d25d  jg      short loc_18000D264
0x18000d25f  mov     esi, 1
0x18000d264  movzx   edx, word ptr [rax+0CAh]
0x18000d26b  test    edx, edx
0x18000d26d  jnz     short loc_18000D27C
0x18000d26f  mov     eax, [rdi+44h]
0x18000d272  mov     edx, 1
0x18000d277  test    eax, eax
0x18000d279  cmovg   edx, eax; nNumerator
0x18000d27c  cmp     edx, esi
0x18000d27e  jz      short loc_18000D289
0x18000d280  test    esi, esi
0x18000d282  jz      short loc_18000D2F2
0x18000d284  test    r12d, r12d
0x18000d287  jnz     short loc_18000D2F2
0x18000d289  movsx   edx, word ptr [rdi+24h]; nNumerator
0x18000d28d  test    r15b, r15b
0x18000d290  jnz     short loc_18000D29F
0x18000d292  cmp     edx, 9ECh
0x18000d298  jz      short loc_18000D29F
0x18000d29a  test    r12d, r12d
0x18000d29d  jnz     short loc_18000D303
0x18000d29f  add     [rbx], r12d
0x18000d2a2  mov     r15, [rsp+58h+var_8]
0x18000d2a7  mov     rsi, [rsp+58h+arg_10]
0x18000d2af  mov     rcx, [rbp+var_10]
0x18000d2b3  xor     rcx, rsp; StackCookie
0x18000d2b6  call    __security_check_cookie
0x18000d2bb  add     rsp, 58h
0x18000d2bf  pop     r14
0x18000d2c1  pop     r13
0x18000d2c3  pop     r12
0x18000d2c5  pop     rdi
0x18000d2c6  pop     rbx
0x18000d2c7  pop     rbp
0x18000d2c8  retn
0x18000d2c9  mov     esi, 1
0x18000d2ce  jmp     loc_18000D147
0x18000d2d3  xorps   xmm0, xmm0
0x18000d2d6  xorps   xmm1, xmm1
0x18000d2d9  psrldq  xmm0, 4
0x18000d2de  mov     r12d, r15d
0x18000d2e1  movd    r13d, xmm0
0x18000d2e6  mov     eax, r15d
0x18000d2e9  movd    ecx, xmm1
0x18000d2ed  jmp     loc_18000D19E
0x18000d2f2  mov     r8d, esi; nDenominator
0x18000d2f5  mov     ecx, r12d; nNumber
0x18000d2f8  call    cs:__imp_MulDiv
0x18000d2fe  mov     r12d, eax
0x18000d301  jmp     short loc_18000D289
0x18000d303  mov     r8d, 9ECh; nDenominator
0x18000d309  mov     ecx, r12d; nNumber
0x18000d30c  call    cs:__imp_MulDiv
0x18000d312  mov     r12d, eax
0x18000d315  jmp     short loc_18000D29F
0x18000d317  mov     r13d, r15d
0x18000d31a  jmp     loc_18000D0EA
0x18000d31f  mov     r8d, 9ECh; nDenominator
0x18000d325  mov     ecx, r9d; nNumber
0x18000d328  call    cs:__imp_MulDiv
0x18000d32e  mov     [rbp+nNumber], eax
0x18000d331  jmp     loc_18000D082
0x18000d336  mov     r8d, esi; nDenominator
0x18000d339  mov     ecx, r12d; nNumber
0x18000d33c  call    cs:__imp_MulDiv
0x18000d342  mov     r12d, eax
0x18000d345  jmp     loc_18000D174
0x18000d34a  mov     r8d, 9ECh; nDenominator
0x18000d350  mov     ecx, r12d; nNumber
0x18000d353  call    cs:__imp_MulDiv
0x18000d359  mov     r12d, eax
0x18000d35c  jmp     loc_18000D18E
0x18000d361  mov     ecx, r13d; nNumber
0x18000d364  call    cs:__imp_MulDiv
0x18000d36a  mov     r13d, eax
0x18000d36d  jmp     loc_18000D0D0
0x18000d372  mov     r8d, 9ECh; nDenominator
0x18000d378  mov     ecx, r13d; nNumber
0x18000d37b  call    cs:__imp_MulDiv
0x18000d381  mov     r13d, eax
0x18000d384  jmp     loc_18000D0EA
0x18000d389  mov     esi, ecx
0x18000d38b  jmp     loc_18000D264
0x18000d390  mov     esi, ecx
0x18000d392  jmp     loc_18000D03F
0x18000d397  mov     esi, ecx
0x18000d399  jmp     loc_18000D147
0x18000d39e  mov     rax, [rcx+10h]
0x18000d3a2  mov     rcx, [rax+30h]
0x18000d3a6  mov     rax, [rcx]
0x18000d3a9  mov     rax, [rax+0C0h]
0x18000d3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3b5  jmp     loc_18000CF85
0x18000d3ba  mov     rcx, rdi; this
0x18000d3bd  call    ?GetSelBarInPixels@CDisplay@@IEAAJXZ; CDisplay::GetSelBarInPixels(void)
0x18000d3c2  sub     [rbx+8], eax
0x18000d3c5  jmp     loc_18000D2A2
0x18000d3ca  movsx   edx, word ptr [r13+0]; nNumerator
0x18000d3cf  cmp     edx, 9ECh
  ... truncated ...
```
