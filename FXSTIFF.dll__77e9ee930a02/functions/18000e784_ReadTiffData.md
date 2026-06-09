# ReadTiffData

- ea: `0x18000e784`
- end: `0x18000ea5b`
- name: `ReadTiffData`
- size: `727`
- prototype: `char *__fastcall(_DWORD *, unsigned int, _DWORD *, unsigned int *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e268`

## callees

- `0x180009600`
- `0x180009f04`
- `0x180009f34`
- `0x18000d990`
- `0x18000e784`
- `0x18000edfc`
- `0x18000f128`
- `0x18000f1c8`
- `0x180018992`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e814`
- `KERNEL32!GetLastError` at `0x18000e910`
- `KERNEL32!GetLastError` at `0x18000e814`
- `KERNEL32!GetLastError` at `0x18000e910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall ReadTiffData(_DWORD *a1, unsigned int a2, _DWORD *a3, unsigned int *a4, _DWORD *a5, _DWORD *a6)
{
  unsigned int *v6; // r12
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rbx
  DWORD LastError; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r9
  int v17; // r15d
  unsigned int v18; // edi
  size_t v19; // rbx
  unsigned __int64 v20; // rax
  __int64 v21; // rax
  char *v22; // rbp
  __int64 v23; // rbx
  DWORD v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r9
  void *v28; // r14
  char *v29; // r15
  unsigned int v30; // r12d
  unsigned int v32; // [rsp+30h] [rbp-68h] BYREF
  int v33; // [rsp+38h] [rbp-60h]
  int v34; // [rsp+3Ch] [rbp-5Ch]
  int v35; // [rsp+40h] [rbp-58h]
  char *v36; // [rsp+48h] [rbp-50h]

  v6 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids);
  }
  if ( !(unsigned int)TiffSeekToPage((__int64)a1, a2, 2) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    v14 = 11;
    v15 = v12;
    v16 = LastError;
    goto LABEL_10;
  }
  v17 = a1[391];
  v18 = a1[392];
  v33 = v17;
  v19 = (unsigned int)(v17 + 7) >> 3;
  v20 = v19 * v18;
  if ( v20 > 0xFFFFFFFF )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, v18, (unsigned int)(v17 + 7) >> 3);
    }
    return 0;
  }
  v34 = a1[421];
  v35 = a1[422];
  v21 = pMemAlloc((unsigned int)v20);
  v36 = (char *)v21;
  v22 = (char *)v21;
  if ( !v21 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v14 = 15;
    v16 = v18 * (unsigned int)v19;
LABEL_10:
    WPP_SF_d(v15, v14, &WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids, v16);
    return 0;
  }
  v32 = v18;
  if ( !(unsigned int)TiffUncompressMmrPage((__int64)a1, v21, (unsigned int)v19 * v18, &v32) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    v23 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v24 = GetLastError();
    v25 = 16;
    v26 = v23;
    v27 = v24;
LABEL_27:
    WPP_SF_d(v26, v25, &WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids, v27);
LABEL_28:
    pMemFree(v22);
    return 0;
  }
  v28 = (void *)pMemAlloc((unsigned int)(v17 + 7) >> 3);
  if ( !v28 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_28;
    }
    v26 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v25 = 17;
    v27 = (unsigned int)v19;
    goto LABEL_27;
  }
  if ( v18 >> 1 )
  {
    v29 = &v22[(unsigned int)v19 * (v18 - 1)];
    v30 = 0;
    do
    {
      memcpy_0(v28, v22, v19);
      memcpy_0(v22, v29, v19);
      memcpy_0(v29, v28, v19);
      v22 += v19;
      v29 -= v19;
      ++v30;
    }
    while ( v30 < v18 >> 1 );
    v22 = v36;
    v6 = a4;
    v17 = v33;
  }
  pMemFree(v28);
  if ( a3 )
    *a3 = v17;
  if ( v6 )
    *v6 = v18;
  if ( a5 )
    *a5 = v34;
  if ( a6 )
    *a6 = v35;
  return v22;
}

```

## disassembly

```asm
0x18000e784  mov     [rsp+arg_18], r9
0x18000e789  push    rbx
0x18000e78a  push    rbp
0x18000e78b  push    rsi
0x18000e78c  push    rdi
0x18000e78d  push    r12
0x18000e78f  push    r13
0x18000e791  push    r14
0x18000e793  push    r15
0x18000e795  sub     rsp, 58h
0x18000e799  mov     r12, r9
0x18000e79c  mov     r13, r8
0x18000e79f  mov     ebx, edx
0x18000e7a1  mov     rsi, rcx
0x18000e7a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7ab  lea     r14, WPP_GLOBAL_Control
0x18000e7b2  mov     ebp, 2
0x18000e7b7  cmp     rcx, r14
0x18000e7ba  jz      short loc_18000E7DB
0x18000e7bc  test    [rcx+1Ch], bpl
0x18000e7c0  jz      short loc_18000E7DB
0x18000e7c2  cmp     byte ptr [rcx+19h], 5
0x18000e7c6  jb      short loc_18000E7DB
0x18000e7c8  mov     rcx, [rcx+10h]
0x18000e7cc  lea     edx, [rbp+8]
0x18000e7cf  lea     r8, WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids
0x18000e7d6  call    WPP_SF_
0x18000e7db  mov     r8d, ebp
0x18000e7de  mov     edx, ebx
0x18000e7e0  mov     rcx, rsi
0x18000e7e3  call    TiffSeekToPage
0x18000e7e8  test    eax, eax
0x18000e7ea  jnz     short loc_18000E83C
0x18000e7ec  mov     rbx, cs:WPP_GLOBAL_Control
0x18000e7f3  cmp     rbx, r14
0x18000e7f6  jz      loc_18000EA47
0x18000e7fc  test    [rbx+1Ch], bpl
0x18000e800  jz      loc_18000EA47
0x18000e806  cmp     [rbx+19h], bpl
0x18000e80a  jb      loc_18000EA47
0x18000e810  mov     rbx, [rbx+10h]
0x18000e814  call    cs:__imp_GetLastError
0x18000e81b  nop     dword ptr [rax+rax+00h]
0x18000e820  mov     edx, 0Bh
0x18000e825  mov     rcx, rbx
0x18000e828  mov     r9d, eax
0x18000e82b  lea     r8, WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids
0x18000e832  call    WPP_SF_d
0x18000e837  jmp     loc_18000EA47
0x18000e83c  mov     r15d, [rsi+61Ch]
0x18000e843  mov     ecx, 0FFFFFFFFh
0x18000e848  mov     edi, [rsi+620h]
0x18000e84e  mov     eax, edi
0x18000e850  mov     [rsp+98h+var_60], r15d
0x18000e855  lea     ebx, [r15+7]
0x18000e859  shr     ebx, 3
0x18000e85c  imul    rax, rbx
0x18000e860  cmp     rax, rcx
0x18000e863  ja      loc_18000EA1F
0x18000e869  mov     r14d, eax
0x18000e86c  mov     eax, [rsi+694h]
0x18000e872  mov     ecx, r14d; dwBytes
0x18000e875  mov     [rsp+98h+var_5C], eax
0x18000e879  mov     eax, [rsi+698h]
0x18000e87f  mov     [rsp+98h+var_58], eax
0x18000e883  call    pMemAlloc
0x18000e888  mov     [rsp+98h+var_50], rax
0x18000e88d  mov     rbp, rax
0x18000e890  test    rax, rax
0x18000e893  jnz     short loc_18000E8D2
0x18000e895  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e89c  lea     rax, WPP_GLOBAL_Control
0x18000e8a3  cmp     rcx, rax
0x18000e8a6  jz      loc_18000EA47
0x18000e8ac  test    byte ptr [rcx+1Ch], 2
0x18000e8b0  jz      loc_18000EA47
0x18000e8b6  cmp     byte ptr [rcx+19h], 2
0x18000e8ba  jb      loc_18000EA47
0x18000e8c0  mov     rcx, [rcx+10h]
0x18000e8c4  lea     edx, [rbp+0Fh]
0x18000e8c7  imul    ebx, edi
0x18000e8ca  mov     r9d, ebx
0x18000e8cd  jmp     loc_18000E82B
0x18000e8d2  lea     r9, [rsp+98h+var_68]
0x18000e8d7  mov     [rsp+98h+var_68], edi
0x18000e8db  mov     r8d, r14d
0x18000e8de  mov     rdx, rbp
0x18000e8e1  mov     rcx, rsi
0x18000e8e4  call    TiffUncompressMmrPage
0x18000e8e9  test    eax, eax
0x18000e8eb  jnz     short loc_18000E929
0x18000e8ed  mov     rbx, cs:WPP_GLOBAL_Control
0x18000e8f4  lea     rax, WPP_GLOBAL_Control
0x18000e8fb  cmp     rbx, rax
0x18000e8fe  jz      short loc_18000E96F
0x18000e900  test    byte ptr [rbx+1Ch], 2
0x18000e904  jz      short loc_18000E96F
0x18000e906  cmp     byte ptr [rbx+19h], 2
0x18000e90a  jb      short loc_18000E96F
0x18000e90c  mov     rbx, [rbx+10h]
0x18000e910  call    cs:__imp_GetLastError
0x18000e917  nop     dword ptr [rax+rax+00h]
0x18000e91c  mov     edx, 10h
0x18000e921  mov     rcx, rbx
0x18000e924  mov     r9d, eax
0x18000e927  jmp     short loc_18000E963
0x18000e929  mov     rcx, rbx; dwBytes
0x18000e92c  call    pMemAlloc
0x18000e931  mov     r14, rax
0x18000e934  test    rax, rax
0x18000e937  jnz     short loc_18000E97C
0x18000e939  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e940  lea     rax, WPP_GLOBAL_Control
0x18000e947  cmp     rcx, rax
0x18000e94a  jz      short loc_18000E96F
0x18000e94c  test    byte ptr [rcx+1Ch], 2
0x18000e950  jz      short loc_18000E96F
0x18000e952  cmp     byte ptr [rcx+19h], 2
0x18000e956  jb      short loc_18000E96F
0x18000e958  mov     rcx, [rcx+10h]
0x18000e95c  lea     edx, [r14+11h]
0x18000e960  mov     r9d, ebx
0x18000e963  lea     r8, WPP_a3050d5391c739eeac73b1d5d94208ce_Traceguids
0x18000e96a  call    WPP_SF_d
0x18000e96f  mov     rcx, rbp; lpMem
0x18000e972  call    pMemFree
0x18000e977  jmp     loc_18000EA47
0x18000e97c  mov     esi, edi
0x18000e97e  shr     esi, 1
0x18000e980  jz      short loc_18000E9DA
0x18000e982  lea     r15d, [rdi-1]
0x18000e986  imul    r15d, ebx
0x18000e98a  add     r15, rbp
0x18000e98d  xor     r12d, r12d
0x18000e990  mov     r8, rbx; Size
0x18000e993  mov     rdx, rbp; Src
0x18000e996  mov     rcx, r14; void *
0x18000e999  call    memcpy_0
0x18000e99e  mov     r8, rbx; Size
0x18000e9a1  mov     rdx, r15; Src
0x18000e9a4  mov     rcx, rbp; void *
0x18000e9a7  call    memcpy_0
0x18000e9ac  mov     r8, rbx; Size
0x18000e9af  mov     rdx, r14; Src
0x18000e9b2  mov     rcx, r15; void *
0x18000e9b5  call    memcpy_0
0x18000e9ba  add     rbp, rbx
0x18000e9bd  sub     r15, rbx
0x18000e9c0  inc     r12d
0x18000e9c3  cmp     r12d, esi
0x18000e9c6  jb      short loc_18000E990
0x18000e9c8  mov     rbp, [rsp+98h+var_50]
0x18000e9cd  mov     r12, [rsp+98h+arg_18]
0x18000e9d5  mov     r15d, [rsp+98h+var_60]
0x18000e9da  mov     rcx, r14; lpMem
0x18000e9dd  call    pMemFree
0x18000e9e2  test    r13, r13
0x18000e9e5  jz      short loc_18000E9EB
0x18000e9e7  mov     [r13+0], r15d
0x18000e9eb  test    r12, r12
0x18000e9ee  jz      short loc_18000E9F4
0x18000e9f0  mov     [r12], edi
0x18000e9f4  mov     rax, [rsp+98h+arg_20]
0x18000e9fc  test    rax, rax
0x18000e9ff  jz      short loc_18000EA07
0x18000ea01  mov     ecx, [rsp+98h+var_5C]
0x18000ea05  mov     [rax], ecx
0x18000ea07  mov     rax, [rsp+98h+arg_28]
0x18000ea0f  test    rax, rax
0x18000ea12  jz      short loc_18000EA1A
0x18000ea14  mov     ecx, [rsp+98h+var_58]
0x18000ea18  mov     [rax], ecx
0x18000ea1a  mov     rax, rbp
0x18000ea1d  jmp     short loc_18000EA49
0x18000ea1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea26  cmp     rcx, r14
0x18000ea29  jz      short loc_18000EA47
0x18000ea2b  test    [rcx+1Ch], bpl
0x18000ea2f  jz      short loc_18000EA47
0x18000ea31  cmp     [rcx+19h], bpl
0x18000ea35  jb      short loc_18000EA47
0x18000ea37  mov     rcx, [rcx+10h]
0x18000ea3b  mov     r9d, edi
0x18000ea3e  mov     [rsp+98h+var_78], ebx
0x18000ea42  call    WPP_SF_LL
0x18000ea47  xor     eax, eax
0x18000ea49  add     rsp, 58h
0x18000ea4d  pop     r15
0x18000ea4f  pop     r14
0x18000ea51  pop     r13
0x18000ea53  pop     r12
0x18000ea55  pop     rdi
0x18000ea56  pop     rsi
0x18000ea57  pop     rbp
0x18000ea58  pop     rbx
0x18000ea59  retn
```
