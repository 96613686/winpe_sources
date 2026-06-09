# CPimcTablet::RefreshCursorInfo(void)

- ea: `0x180008eb0`
- end: `0x1800094f1`
- name: `?RefreshCursorInfo@CPimcTablet@@UEAAJXZ`
- size: `1601`
- prototype: `__int64 __fastcall(CPimcTablet *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180008eb0`
- `0x18000953c`
- `0x18000d44c`
- `0x18000d488`
- `0x18000e0cc`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180009238`
- `ole32!CoTaskMemAlloc` at `0x180009336`
- `ole32!CoTaskMemAlloc` at `0x180009400`
- `ole32!CoTaskMemAlloc` at `0x180009238`
- `ole32!CoTaskMemAlloc` at `0x180009336`
- `ole32!CoTaskMemAlloc` at `0x180009400`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CPimcTablet::RefreshCursorInfo(CPimcTablet *this)
{
  __int64 v2; // rcx
  unsigned int *v3; // r14
  signed int v4; // esi
  unsigned __int64 v5; // rbx
  void *v6; // rdi
  CPimcTablet *v7; // rbx
  unsigned int v8; // r15d
  _QWORD *v9; // r12
  unsigned __int64 v10; // rdi
  void *v11; // rbx
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rcx
  _QWORD *v15; // rax
  char *v16; // rdi
  __int64 v17; // rcx
  const wchar_t *v18; // rax
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rbx
  _WORD *v22; // rax
  _WORD *v23; // rdx
  unsigned __int64 v24; // rbx
  unsigned __int64 v25; // rcx
  char *v26; // r14
  __int16 v27; // ax
  _OWORD *v28; // rax
  __int64 v29; // r15
  char *v30; // r14
  __int64 v31; // rcx
  const wchar_t *v32; // rax
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rbx
  _WORD *v36; // rax
  _WORD *v37; // rdx
  unsigned __int64 v38; // rbx
  unsigned __int64 v39; // rcx
  char *v40; // r8
  __int16 v41; // ax
  __int128 v42; // xmm0
  const wchar_t *v43; // rax
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rbx
  _WORD *v47; // rax
  _WORD *v48; // rdx
  unsigned __int64 v49; // rbx
  unsigned __int64 v50; // rcx
  char *v51; // r8
  __int16 v52; // ax
  __int64 v54; // [rsp+20h] [rbp-28h]
  __int64 v55; // [rsp+28h] [rbp-20h]
  char *v56; // [rsp+38h] [rbp-10h]
  char *v58; // [rsp+98h] [rbp+50h] BYREF
  __int64 v59; // [rsp+A0h] [rbp+58h] BYREF
  __int64 v60; // [rsp+A8h] [rbp+60h] BYREF

  v59 = 0;
  v60 = 0;
  CPimcTablet::ReleaseCursorInfo(this);
  v2 = *((_QWORD *)this + 3);
  v3 = (unsigned int *)((char *)this + 52);
  if ( !v2 )
  {
    *v3 = 1;
    v15 = operator new[](8u);
    *v15 = 0;
    *((_QWORD *)this + 7) = v15;
    v4 = v15 == 0 ? 0x8007000E : 0;
    if ( v15 )
    {
      v16 = (char *)operator new(0x20u);
      v58 = v16;
      *(_QWORD *)v16 = 0;
      *((_QWORD *)v16 + 1) = 0;
      *((_DWORD *)v16 + 4) = 0;
      *((_QWORD *)v16 + 3) = 0;
      **((_QWORD **)this + 7) = v16;
      v17 = 0x7FFFFFFF;
      v18 = L"Mouse";
      while ( *v18 )
      {
        ++v18;
        if ( !--v17 )
        {
LABEL_27:
          v4 = -2147024809;
          goto LABEL_82;
        }
      }
      v19 = 0x7FFFFFFF - v17;
      v20 = 0x7FFFFFFF - v17 + 1;
      if ( v20 >= v19 && (v21 = 2 * v20, is_mul_ok(v20, 2u)) )
      {
        v22 = CoTaskMemAlloc(2 * v20);
        v23 = v22;
        *(_QWORD *)v16 = v22;
        v4 = v22 == 0 ? 0x8007000E : 0;
        if ( v22 )
        {
          v24 = v21 >> 1;
          if ( v24 )
          {
            if ( v24 <= 0x7FFFFFFF )
            {
              v25 = 2147483646 - v24;
              v26 = (char *)((char *)L"Mouse" - (char *)v22);
              do
              {
                if ( !(v25 + v24) )
                  goto LABEL_40;
                v27 = *(_WORD *)((char *)v23 + (_QWORD)v26);
                if ( !v27 )
                  break;
                *v23++ = v27;
                --v24;
              }
              while ( v24 );
              if ( !v24 )
                --v23;
LABEL_40:
              *v23 = 0;
            }
            else
            {
              *v22 = 0;
            }
          }
          *((_QWORD *)v16 + 1) = 1;
          *((_DWORD *)v16 + 4) = 2;
          v28 = operator new[](0x10u);
          *v28 = 0;
          *((_QWORD *)v16 + 3) = v28;
          v29 = 0;
          while ( 1 )
          {
            v30 = (char *)operator new(0x18u);
            v58 = v30;
            *(_QWORD *)v30 = 0;
            *(_OWORD *)(v30 + 8) = 0;
            v31 = 0x7FFFFFFF;
            if ( v29 )
            {
              v43 = L"Barrel Switch";
              while ( *v43 )
              {
                ++v43;
                if ( !--v31 )
                  goto LABEL_27;
              }
              v44 = 0x7FFFFFFF - v31;
              v45 = 0x7FFFFFFF - v31 + 1;
              if ( v45 < v44 )
                goto LABEL_81;
              v46 = 2 * v45;
              if ( !is_mul_ok(v45, 2u) )
                goto LABEL_81;
              v47 = CoTaskMemAlloc(2 * v45);
              v48 = v47;
              *(_QWORD *)v30 = v47;
              v4 = v47 == 0 ? 0x8007000E : 0;
              if ( !v47 )
                goto LABEL_82;
              v49 = v46 >> 1;
              if ( v49 )
              {
                if ( v49 <= 0x7FFFFFFF )
                {
                  v50 = 2147483646 - v49;
                  v51 = (char *)((char *)L"Barrel Switch" - (char *)v47);
                  while ( v50 + v49 )
                  {
                    v52 = *(_WORD *)((char *)v48 + (_QWORD)v51);
                    if ( v52 )
                    {
                      *v48++ = v52;
                      if ( --v49 )
                        continue;
                    }
                    if ( !v49 )
                      --v48;
                    break;
                  }
                  *v48 = 0;
                }
                else
                {
                  *v47 = 0;
                }
              }
              v42 = xmmword_1800181F0;
            }
            else
            {
              v32 = L"Tip Switch";
              while ( *v32 )
              {
                ++v32;
                if ( !--v31 )
                  goto LABEL_27;
              }
              v33 = 0x7FFFFFFF - v31;
              v34 = 0x7FFFFFFF - v31 + 1;
              if ( v34 < v33 )
                goto LABEL_81;
              v35 = 2 * v34;
              if ( !is_mul_ok(v34, 2u) )
                goto LABEL_81;
              v36 = CoTaskMemAlloc(2 * v34);
              v37 = v36;
              *(_QWORD *)v30 = v36;
              v4 = v36 == 0 ? 0x8007000E : 0;
              if ( !v36 )
                goto LABEL_82;
              v38 = v35 >> 1;
              if ( v38 )
              {
                if ( v38 <= 0x7FFFFFFF )
                {
                  v39 = 2147483646 - v38;
                  v40 = (char *)((char *)L"Tip Switch" - (char *)v36);
                  while ( v39 + v38 )
                  {
                    v41 = *(_WORD *)((char *)v37 + (_QWORD)v40);
                    if ( v41 )
                    {
                      *v37++ = v41;
                      if ( --v38 )
                        continue;
                    }
                    if ( !v38 )
                      --v37;
                    break;
                  }
                  *v37 = 0;
                }
                else
                {
                  *v36 = 0;
                }
              }
              v42 = xmmword_1800181E0;
            }
            *(_OWORD *)(v30 + 8) = v42;
            *(_QWORD *)(*((_QWORD *)v16 + 3) + 8 * v29++) = v30;
            if ( v29 >= 2 )
              goto LABEL_84;
          }
        }
      }
      else
      {
LABEL_81:
        v4 = -2147024362;
      }
    }
    goto LABEL_82;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v2 + 80LL))(v2, (char *)this + 52);
  if ( v4 < 0 )
  {
LABEL_82:
    v7 = this;
    goto LABEL_83;
  }
  v5 = saturated_mul(*v3, 8u);
  v6 = operator new[](v5);
  memset_0(v6, 0, v5);
  v7 = this;
  *((_QWORD *)this + 7) = v6;
  v4 = v6 == 0 ? 0x8007000E : 0;
  if ( v6 )
  {
    v8 = 0;
    if ( !*v3 )
      goto LABEL_84;
    while ( 1 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)v7 + 3) + 88LL))(
             *((_QWORD *)v7 + 3),
             v8,
             &v59);
      if ( v4 < 0 )
        break;
      v9 = operator new(0x20u);
      *v9 = 0;
      v9[1] = 0;
      *((_DWORD *)v9 + 4) = 0;
      v9[3] = 0;
      *(_QWORD *)(*((_QWORD *)this + 7) + 8LL * v8) = v9;
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v59 + 24LL))(v59, v9);
      if ( v4 < 0 )
        goto LABEL_82;
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v59 + 40LL))(v59, v9 + 1);
      if ( v4 < 0 )
        goto LABEL_82;
      v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v59 + 32LL))(v59);
      if ( v4 < 0 )
        goto LABEL_82;
      *((_DWORD *)v9 + 3) = v4 == 0;
      v4 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v59 + 56LL))(v59, &v58);
      if ( v4 < 0 )
        goto LABEL_82;
      *((_DWORD *)v9 + 4) = (_DWORD)v58;
      v10 = saturated_mul((unsigned int)v58, 8u);
      v11 = operator new[](v10);
      memset_0(v11, 0, v10);
      v9[3] = v11;
      v12 = 0;
      if ( (_DWORD)v58 )
      {
        do
        {
          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v59 + 64LL))(v59, v12, &v60);
          if ( v4 < 0 )
            goto LABEL_82;
          v56 = (char *)operator new(0x18u);
          *(_QWORD *)v56 = 0;
          *(_OWORD *)(v56 + 8) = 0;
          *(_QWORD *)(v9[3] + 8LL * v12) = v56;
          v4 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v60 + 24LL))(v60, v56);
          if ( v4 < 0 )
            goto LABEL_82;
          v4 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v60 + 32LL))(v60, v56 + 8);
          if ( v4 < 0 )
            goto LABEL_82;
          if ( v60 )
          {
            v13 = v60;
            v54 = v60;
            v60 = 0;
            if ( v54 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
        }
        while ( ++v12 < (unsigned int)v58 );
      }
      if ( v59 )
      {
        v14 = v59;
        v55 = v59;
        v59 = 0;
        if ( v55 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      ++v8;
      v7 = this;
      if ( v8 >= *v3 )
        goto LABEL_84;
    }
  }
LABEL_83:
  CPimcTablet::ReleaseCursorInfo(v7);
LABEL_84:
  if ( v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  if ( v59 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008eb0  mov     [rsp-40h+arg_0], rcx
0x180008eb5  push    rbp
0x180008eb6  push    rbx
0x180008eb7  push    rsi
0x180008eb8  push    rdi
0x180008eb9  push    r12
0x180008ebb  push    r13
0x180008ebd  push    r14
0x180008ebf  push    r15
0x180008ec1  mov     rbp, rsp
0x180008ec4  sub     rsp, 48h
0x180008ec8  mov     rsi, rcx
0x180008ecb  xor     r13d, r13d
0x180008ece  mov     [rbp+arg_10], r13
0x180008ed2  mov     [rbp+arg_18], r13
0x180008ed6  call    ?ReleaseCursorInfo@CPimcTablet@@QEAAXXZ; CPimcTablet::ReleaseCursorInfo(void)
0x180008edb  mov     rcx, [rsi+18h]
0x180008edf  lea     r14, [rsi+34h]
0x180008ee3  test    rcx, rcx
0x180008ee6  jz      loc_18000917D
0x180008eec  mov     rax, [rcx]
0x180008eef  mov     rdx, r14
0x180008ef2  mov     rax, [rax+50h]
0x180008ef6  call    cs:__guard_dispatch_icall_fptr
0x180008efc  mov     esi, eax
0x180008efe  test    eax, eax
0x180008f00  js      loc_1800094A4
0x180008f06  mov     ecx, [r14]
0x180008f09  mov     r13d, 8
0x180008f0f  mov     eax, r13d
0x180008f12  mul     rcx
0x180008f15  mov     rbx, rax
0x180008f18  lea     rax, [r13-9]
0x180008f1c  cmovo   rbx, rax
0x180008f20  mov     rcx, rbx; unsigned __int64
0x180008f23  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008f28  mov     rdi, rax
0x180008f2b  mov     r8, rbx; Size
0x180008f2e  xor     edx, edx; Val
0x180008f30  mov     rcx, rax; void *
0x180008f33  call    memset_0
0x180008f38  mov     rbx, [rbp+arg_0]
0x180008f3c  mov     [rbx+38h], rdi
0x180008f40  mov     rcx, rdi
0x180008f43  neg     rcx
0x180008f46  sbb     esi, esi
0x180008f48  not     esi
0x180008f4a  and     esi, 8007000Eh
0x180008f50  test    rdi, rdi
0x180008f53  jz      loc_1800094A8
0x180008f59  xor     edi, edi
0x180008f5b  mov     r15d, edi
0x180008f5e  cmp     [r14], edi
0x180008f61  jbe     loc_1800094B1
0x180008f67  mov     rcx, [rbx+18h]
0x180008f6b  mov     rax, [rcx]
0x180008f6e  lea     r8, [rbp+arg_10]
0x180008f72  mov     edx, r15d
0x180008f75  mov     rax, [rax+58h]
0x180008f79  call    cs:__guard_dispatch_icall_fptr
0x180008f7f  mov     esi, eax
0x180008f81  test    eax, eax
0x180008f83  js      loc_1800094A8
0x180008f89  mov     ecx, 20h ; ' '; Size
0x180008f8e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008f93  mov     r12, rax
0x180008f96  mov     [rbp+var_18], rax
0x180008f9a  mov     [rax], rdi
0x180008f9d  and     qword ptr [rax+8], 0
0x180008fa2  mov     [rax+10h], edi
0x180008fa5  mov     [rax+18h], rdi
0x180008fa9  mov     ecx, r15d
0x180008fac  mov     rax, [rbp+arg_0]
0x180008fb0  mov     rax, [rax+38h]
0x180008fb4  mov     [rax+rcx*8], r12
0x180008fb8  mov     rcx, [rbp+arg_10]
0x180008fbc  mov     rax, [rcx]
0x180008fbf  mov     rdx, r12
0x180008fc2  mov     rax, [rax+18h]
0x180008fc6  call    cs:__guard_dispatch_icall_fptr
0x180008fcc  mov     esi, eax
0x180008fce  test    eax, eax
0x180008fd0  js      loc_1800094A4
0x180008fd6  mov     rcx, [rbp+arg_10]
0x180008fda  mov     rax, [rcx]
0x180008fdd  lea     rdx, [r12+8]
0x180008fe2  mov     rax, [rax+28h]
0x180008fe6  call    cs:__guard_dispatch_icall_fptr
0x180008fec  mov     esi, eax
0x180008fee  test    eax, eax
0x180008ff0  js      loc_1800094A4
0x180008ff6  mov     rcx, [rbp+arg_10]
0x180008ffa  mov     rax, [rcx]
0x180008ffd  mov     rax, [rax+20h]
0x180009001  call    cs:__guard_dispatch_icall_fptr
0x180009007  mov     esi, eax
0x180009009  test    eax, eax
0x18000900b  js      loc_1800094A4
0x180009011  mov     eax, edi
0x180009013  test    esi, esi
0x180009015  setz    al
0x180009018  mov     [r12+0Ch], eax
0x18000901d  mov     rcx, [rbp+arg_10]
0x180009021  mov     rax, [rcx]
0x180009024  lea     rdx, [rbp+arg_8]
0x180009028  mov     rax, [rax+38h]
0x18000902c  call    cs:__guard_dispatch_icall_fptr
0x180009032  mov     esi, eax
0x180009034  test    eax, eax
0x180009036  js      loc_1800094A4
0x18000903c  mov     eax, dword ptr [rbp+arg_8]
0x18000903f  mov     [r12+10h], eax
0x180009044  mov     ecx, dword ptr [rbp+arg_8]
0x180009047  mov     rax, r13
0x18000904a  mul     rcx
0x18000904d  mov     rdi, rax
0x180009050  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009057  cmovo   rdi, rax
0x18000905b  mov     rcx, rdi; unsigned __int64
0x18000905e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009063  mov     rbx, rax
0x180009066  mov     r8, rdi; Size
0x180009069  xor     edx, edx; Val
0x18000906b  mov     rcx, rax; void *
0x18000906e  call    memset_0
0x180009073  mov     [r12+18h], rbx
0x180009078  xor     edi, edi
0x18000907a  mov     ebx, edi
0x18000907c  cmp     dword ptr [rbp+arg_8], edi
0x18000907f  jbe     loc_180009140
0x180009085  mov     rcx, [rbp+arg_10]
0x180009089  mov     rax, [rcx]
0x18000908c  lea     r8, [rbp+arg_18]
0x180009090  mov     edx, ebx
0x180009092  mov     rax, [rax+40h]
0x180009096  call    cs:__guard_dispatch_icall_fptr
0x18000909c  mov     esi, eax
0x18000909e  test    eax, eax
0x1800090a0  js      loc_1800094A4
0x1800090a6  mov     ecx, 18h; Size
0x1800090ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800090b0  mov     r8, rax
0x1800090b3  mov     [rbp+var_10], rax
0x1800090b7  mov     [rax], rdi
0x1800090ba  lea     rdi, [rax+8]
0x1800090be  xorps   xmm0, xmm0
0x1800090c1  movups  xmmword ptr [rdi], xmm0
0x1800090c4  mov     edx, ebx
0x1800090c6  mov     rcx, [r12+18h]
0x1800090cb  mov     [rcx+rdx*8], rax
0x1800090cf  mov     rcx, [rbp+arg_18]
0x1800090d3  mov     rax, [rcx]
0x1800090d6  mov     rdx, r8
0x1800090d9  mov     rax, [rax+18h]
0x1800090dd  call    cs:__guard_dispatch_icall_fptr
0x1800090e3  mov     esi, eax
0x1800090e5  test    eax, eax
0x1800090e7  js      loc_1800094A4
0x1800090ed  mov     rcx, [rbp+arg_18]
0x1800090f1  mov     rax, [rcx]
0x1800090f4  mov     rdx, rdi
0x1800090f7  mov     rax, [rax+20h]
0x1800090fb  call    cs:__guard_dispatch_icall_fptr
0x180009101  mov     esi, eax
0x180009103  xor     edi, edi
0x180009105  test    eax, eax
0x180009107  js      loc_1800094A4
0x18000910d  cmp     [rbp+arg_18], rdi
0x180009111  jz      short loc_180009135
0x180009113  mov     [rbp+var_28], rdi
0x180009117  mov     rcx, [rbp+arg_18]
0x18000911b  mov     [rbp+var_28], rcx
0x18000911f  mov     [rbp+arg_18], rdi
0x180009123  test    rcx, rcx
0x180009126  jz      short loc_180009135
0x180009128  mov     rax, [rcx]
0x18000912b  mov     rax, [rax+10h]
0x18000912f  call    cs:__guard_dispatch_icall_fptr
0x180009135  inc     ebx
0x180009137  cmp     ebx, dword ptr [rbp+arg_8]
0x18000913a  jb      loc_180009085
0x180009140  cmp     [rbp+arg_10], rdi
0x180009144  jz      short loc_180009168
0x180009146  mov     [rbp+var_20], rdi
0x18000914a  mov     rcx, [rbp+arg_10]
0x18000914e  mov     [rbp+var_20], rcx
0x180009152  mov     [rbp+arg_10], rdi
0x180009156  test    rcx, rcx
0x180009159  jz      short loc_180009168
0x18000915b  mov     rax, [rcx]
0x18000915e  mov     rax, [rax+10h]
0x180009162  call    cs:__guard_dispatch_icall_fptr
0x180009168  inc     r15d
0x18000916b  cmp     r15d, [r14]
0x18000916e  mov     rbx, [rbp+arg_0]
0x180009172  jb      loc_180008F67
0x180009178  jmp     loc_1800094B1
0x18000917d  mov     dword ptr [r14], 1
0x180009184  mov     ecx, 8; unsigned __int64
0x180009189  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000918e  xor     ecx, ecx
0x180009190  mov     [rax], rcx
0x180009193  mov     [rsi+38h], rax
0x180009197  mov     rcx, rax
0x18000919a  neg     rcx
0x18000919d  sbb     esi, esi
0x18000919f  not     esi
0x1800091a1  mov     r12d, 8007000Eh
0x1800091a7  and     esi, r12d
0x1800091aa  xor     r13d, r13d
0x1800091ad  test    rax, rax
0x1800091b0  jz      loc_1800094A4
0x1800091b6  lea     ecx, [r13+20h]; Size
0x1800091ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800091bf  mov     rdi, rax
0x1800091c2  mov     [rbp+arg_8], rax
0x1800091c6  mov     [rax], r13
0x1800091c9  mov     [rax+8], r13
0x1800091cd  mov     [rax+10h], r13d
0x1800091d1  mov     [rax+18h], r13
0x1800091d5  mov     rax, [rbp+arg_0]
0x1800091d9  mov     rax, [rax+38h]
0x1800091dd  mov     [rax], rdi
0x1800091e0  mov     r8d, 7FFFFFFFh
0x1800091e6  mov     ecx, r8d
0x1800091e9  lea     r14, aMouse; "Mouse"
0x1800091f0  mov     rax, r14
0x1800091f3  lea     r15d, [r13+2]
0x1800091f7  cmp     [rax], r13w
0x1800091fb  jz      short loc_180009210
0x1800091fd  add     rax, r15
0x180009200  sub     rcx, 1
0x180009204  jnz     short loc_1800091F7
0x180009206  mov     esi, 80070057h
0x18000920b  jmp     loc_1800094A4
0x180009210  mov     rax, r8
0x180009213  sub     rax, rcx
0x180009216  lea     rcx, [rax+1]
0x18000921a  cmp     rcx, rax
0x18000921d  jb      loc_18000949F
0x180009223  mov     rax, r15
0x180009226  mul     rcx
0x180009229  mov     rbx, rax
0x18000922c  test    rdx, rdx
0x18000922f  jnz     loc_18000949F
0x180009235  mov     rcx, rax; cb
0x180009238  call    cs:__imp_CoTaskMemAlloc
0x18000923e  mov     rdx, rax
0x180009241  mov     [rdi], rax
0x180009244  mov     rcx, rax
0x180009247  neg     rcx
0x18000924a  sbb     esi, esi
0x18000924c  not     esi
0x18000924e  and     esi, r12d
0x180009251  test    rax, rax
0x180009254  jz      loc_1800094A4
0x18000925a  shr     rbx, 1
0x18000925d  mov     esi, 7FFFFFFFh
0x180009262  jz      short loc_1800092A5
0x180009264  cmp     rbx, rsi
0x180009267  jbe     short loc_18000926F
0x180009269  mov     [rax], r13w
0x18000926d  jmp     short loc_1800092A5
0x18000926f  mov     ecx, 7FFFFFFEh
0x180009274  sub     rcx, rbx
0x180009277  sub     r14, rax
0x18000927a  lea     rax, [rcx+rbx]
0x18000927e  test    rax, rax
0x180009281  jz      short loc_1800092A1
0x180009283  movzx   eax, word ptr [r14+rdx]
0x180009288  test    ax, ax
0x18000928b  jz      short loc_180009299
0x18000928d  mov     [rdx], ax
0x180009290  add     rdx, r15
0x180009293  sub     rbx, 1
0x180009297  jnz     short loc_18000927A
0x180009299  test    rbx, rbx
0x18000929c  jnz     short loc_1800092A1
0x18000929e  sub     rdx, r15
0x1800092a1  mov     [rdx], r13w
0x1800092a5  mov     qword ptr [rdi+8], 1
0x1800092ad  mov     [rdi+10h], r15d
0x1800092b1  mov     ecx, 10h; unsigned __int64
0x1800092b6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800092bb  xorps   xmm0, xmm0
0x1800092be  movups  xmmword ptr [rax], xmm0
0x1800092c1  mov     [rdi+18h], rax
0x1800092c5  mov     r15, r13
0x1800092c8  mov     ecx, 18h; Size
0x1800092cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800092d2  mov     r14, rax
0x1800092d5  mov     [rbp+arg_8], rax
0x1800092d9  mov     [rax], r13
0x1800092dc  xorps   xmm0, xmm0
0x1800092df  movups  xmmword ptr [rax+8], xmm0
0x1800092e3  mov     rcx, rsi
0x1800092e6  test    r15, r15
0x1800092e9  jnz     loc_1800093B9
0x1800092ef  lea     rax, aTipSwitch; "Tip Switch"
0x1800092f6  cmp     [rax], r13w
  ... truncated ...
```
