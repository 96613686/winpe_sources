# MbaeHashCalculator::Calculate(ushort *)

- ea: `0x180006810`
- end: `0x1800069d5`
- name: `?Calculate@MbaeHashCalculator@@QEAAJPEAG@Z`
- size: `453`
- prototype: `__int64 __fastcall(MbaeHashCalculator *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006340`

## callees

- `0x180006810`
- `0x180008ff0`
- `0x18000b6f4`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x180006946`
- `bcrypt!BCryptFinishHash` at `0x180006946`
- `bcrypt!BCryptDestroyHash` at `0x180006957`
- `bcrypt!BCryptDestroyHash` at `0x180006957`
- `bcrypt!BCryptHashData` at `0x180006907`
- `bcrypt!BCryptHashData` at `0x180006907`
- `bcrypt!BCryptCreateHash` at `0x1800068ed`
- `bcrypt!BCryptCreateHash` at `0x1800068ed`

## pseudocode

```c
__int64 __fastcall MbaeHashCalculator::Calculate(MbaeHashCalculator *this, unsigned __int16 *a2)
{
  PVOID *v4; // rcx
  _WORD *v6; // rcx
  __int64 v7; // rax
  __int64 v9; // rdi
  NTSTATUS v10; // esi
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp+8h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_feb619c85fea375a922233db6a92786b_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  phHash = 0;
  if ( *(_BYTE *)this )
  {
    **((_WORD **)this + 14) = 0;
    v6 = (_WORD *)*((_QWORD *)this + 15);
    if ( v6 )
      *v6 = 0;
    v7 = -1;
    while ( a2[++v7] != 0 )
      ;
    v9 = 2 * v7;
    v10 = BCryptCreateHash(
            *((BCRYPT_ALG_HANDLE *)this + 9),
            &phHash,
            *((PUCHAR *)this + 11),
            *((_DWORD *)this + 20),
            0,
            0,
            0);
    if ( v10 >= 0 )
      v10 = BCryptHashData(phHash, (PUCHAR)a2, v9, 0);
    for ( ; v9; --v9 )
    {
      *(_BYTE *)a2 = 0;
      a2 = (unsigned __int16 *)((char *)a2 + 1);
    }
    if ( v10 < 0 || (v10 = BCryptFinishHash(phHash, *((PUCHAR *)this + 13), *((_DWORD *)this + 24), 0), v10 < 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_feb619c85fea375a922233db6a92786b_Traceguids,
          (unsigned int)v10);
      return v10 | 0x10000000u;
    }
    else
    {
      BCryptDestroyHash(phHash);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_feb619c85fea375a922233db6a92786b_Traceguids, 0);
      return 0;
    }
  }
  else
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
      WPP_SF_d(v4[2], 17, WPP_feb619c85fea375a922233db6a92786b_Traceguids, 2147947423LL);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x180006810  push    rbx
0x180006812  push    rbp
0x180006813  push    r14
0x180006815  sub     rsp, 40h
0x180006819  mov     rbx, rdx
0x18000681c  mov     rbp, rcx
0x18000681f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006826  lea     r14, WPP_GLOBAL_Control
0x18000682d  cmp     rcx, r14
0x180006830  jz      short loc_180006854
0x180006832  test    byte ptr [rcx+1Ch], 10h
0x180006836  jz      short loc_180006854
0x180006838  mov     rcx, [rcx+10h]
0x18000683c  lea     r8, WPP_feb619c85fea375a922233db6a92786b_Traceguids
0x180006843  mov     edx, 10h
0x180006848  call    WPP_SF_
0x18000684d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006854  xor     edx, edx
0x180006856  mov     [rsp+58h+phHash], rdx
0x18000685b  cmp     [rbp+0], dl
0x18000685e  jnz     short loc_180006894
0x180006860  cmp     rcx, r14
0x180006863  jz      short loc_180006886
0x180006865  test    byte ptr [rcx+1Ch], 10h
0x180006869  jz      short loc_180006886
0x18000686b  mov     rcx, [rcx+10h]
0x18000686f  lea     r8, WPP_feb619c85fea375a922233db6a92786b_Traceguids
0x180006876  mov     edx, 11h
0x18000687b  mov     r9d, 8007139Fh
0x180006881  call    WPP_SF_d
0x180006886  mov     eax, 8007139Fh
0x18000688b  add     rsp, 40h
0x18000688f  pop     r14
0x180006891  pop     rbp
0x180006892  pop     rbx
0x180006893  retn
0x180006894  mov     rcx, [rbp+70h]
0x180006898  mov     [rsp+58h+arg_8], rsi
0x18000689d  mov     [rsp+58h+arg_10], rdi
0x1800068a2  mov     [rcx], dx
0x1800068a5  mov     rcx, [rbp+78h]
0x1800068a9  test    rcx, rcx
0x1800068ac  jz      short loc_1800068B1
0x1800068ae  mov     [rcx], dx
0x1800068b1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800068b8  nop     dword ptr [rax+rax+00000000h]
0x1800068c0  cmp     [rbx+rax*2+2], dx
0x1800068c5  lea     rax, [rax+1]
0x1800068c9  jnz     short loc_1800068C0
0x1800068cb  mov     r9d, [rbp+50h]; cbHashObject
0x1800068cf  lea     rdi, [rax+rax]
0x1800068d3  mov     r8, [rbp+58h]; pbHashObject
0x1800068d7  mov     rcx, [rbp+48h]; hAlgorithm
0x1800068db  mov     [rsp+58h+dwFlags], edx; dwFlags
0x1800068df  mov     [rsp+58h+cbSecret], edx; cbSecret
0x1800068e3  mov     [rsp+58h+pbSecret], rdx; pbSecret
0x1800068e8  lea     rdx, [rsp+58h+phHash]; phHash
0x1800068ed  call    cs:__imp_BCryptCreateHash
0x1800068f3  mov     esi, eax
0x1800068f5  test    eax, eax
0x1800068f7  js      short loc_18000690F
0x1800068f9  mov     rcx, [rsp+58h+phHash]; hHash
0x1800068fe  mov     r8d, edi; cbInput
0x180006901  xor     r9d, r9d; dwFlags
0x180006904  mov     rdx, rbx; pbInput
0x180006907  call    cs:__imp_BCryptHashData
0x18000690d  mov     esi, eax
0x18000690f  test    rdi, rdi
0x180006912  jz      short loc_18000692D
0x180006914  nop     dword ptr [rax+00h]
0x180006918  nop     dword ptr [rax+rax+00000000h]
0x180006920  mov     byte ptr [rbx], 0
0x180006923  lea     rbx, [rbx+1]
0x180006927  sub     rdi, 1
0x18000692b  jnz     short loc_180006920
0x18000692d  mov     rdi, [rsp+58h+arg_10]
0x180006932  test    esi, esi
0x180006934  js      short loc_180006997
0x180006936  mov     r8d, [rbp+60h]; cbOutput
0x18000693a  xor     r9d, r9d; dwFlags
0x18000693d  mov     rdx, [rbp+68h]; pbOutput
0x180006941  mov     rcx, [rsp+58h+phHash]; hHash
0x180006946  call    cs:__imp_BCryptFinishHash
0x18000694c  mov     esi, eax
0x18000694e  test    eax, eax
0x180006950  js      short loc_180006997
0x180006952  mov     rcx, [rsp+58h+phHash]; hHash
0x180006957  call    cs:__imp_BCryptDestroyHash
0x18000695d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006964  cmp     rcx, r14
0x180006967  jz      short loc_180006987
0x180006969  test    byte ptr [rcx+1Ch], 10h
0x18000696d  jz      short loc_180006987
0x18000696f  mov     rcx, [rcx+10h]
0x180006973  lea     r8, WPP_feb619c85fea375a922233db6a92786b_Traceguids
0x18000697a  mov     edx, 12h
0x18000697f  xor     r9d, r9d
0x180006982  call    WPP_SF_d
0x180006987  mov     rsi, [rsp+58h+arg_8]
0x18000698c  xor     eax, eax
0x18000698e  add     rsp, 40h
0x180006992  pop     r14
0x180006994  pop     rbp
0x180006995  pop     rbx
0x180006996  retn
0x180006997  mov     rcx, cs:WPP_GLOBAL_Control
0x18000699e  cmp     rcx, r14
0x1800069a1  jz      short loc_1800069C1
0x1800069a3  test    byte ptr [rcx+1Ch], 10h
0x1800069a7  jz      short loc_1800069C1
0x1800069a9  mov     rcx, [rcx+10h]
0x1800069ad  lea     r8, WPP_feb619c85fea375a922233db6a92786b_Traceguids
0x1800069b4  mov     edx, 13h
0x1800069b9  mov     r9d, esi
0x1800069bc  call    WPP_SF_d
0x1800069c1  bts     esi, 1Ch
0x1800069c5  mov     eax, esi
0x1800069c7  mov     rsi, [rsp+58h+arg_8]
0x1800069cc  add     rsp, 40h
0x1800069d0  pop     r14
0x1800069d2  pop     rbp
0x1800069d3  pop     rbx
0x1800069d4  retn
```
