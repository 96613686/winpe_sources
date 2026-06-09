# ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)

- ea: `0x14001d0dc`
- end: `0x14001d1e6`
- name: `?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z`
- size: `266`
- prototype: `int __fastcall(ARI::ProcessToken::SysAppId *this, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001d320`

## callees

- `0x14001d0dc`
- `0x14001d2cc`
- `0x14001e060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14001d12e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14001d12e`

## pseudocode

```c
int __fastcall ARI::ProcessToken::SysAppId::GetAppUserModelId(
        ARI::ProcessToken::SysAppId *this,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *a2,
        _DWORD *a3,
        unsigned int *a4)
{
  unsigned int v6; // edi
  int result; // eax
  unsigned __int16 *v9; // rbx
  const wchar_t *v10; // rcx
  wchar_t *v11; // rax
  _BYTE *v12; // rcx
  int v13; // r14d
  __int64 v14; // rax
  __int64 v15; // rbp
  int v16; // r13d
  size_t v17; // rbx
  _BYTE *v18; // rax
  __int64 v19; // rcx
  unsigned __int16 *v20; // [rsp+20h] [rbp-68h] BYREF
  __int64 v21; // [rsp+28h] [rbp-60h]
  _BYTE *v22; // [rsp+30h] [rbp-58h]

  LODWORD(v20) = 0;
  v6 = (unsigned int)a2;
  result = ARI::ProcessToken::SysAppId::GetPackageRelativeApplicationId(this, 0, (unsigned int)&v20, 0, v20);
  if ( result == 122 )
  {
    v9 = (unsigned __int16 *)*((_QWORD *)this + 4);
    v10 = (const wchar_t *)*((_QWORD *)v9 + 1);
    LODWORD(v21) = *v9 >> 1;
    v11 = wcschr(v10, 0x5Fu);
    v12 = (_BYTE *)*((_QWORD *)v9 + 1);
    v13 = (int)v20;
    v14 = ((char *)(v11 + 1) - v12) >> 1;
    v22 = v12;
    v15 = (unsigned int)(v14 + 13);
    v16 = v14 + 14;
    if ( v6 < (int)v14 + 14
      || (v17 = 2LL * (unsigned int)v14,
          memcpy_0(a4, v12, v17),
          v18 = v22,
          v19 = (unsigned int)(v21 - 13),
          *(_OWORD *)((char *)a4 + v17) = *(_OWORD *)&v22[2 * v19],
          *(_OWORD *)((char *)a4 + v17 + 10) = *(_OWORD *)&v18[2 * v19 + 10],
          *((_WORD *)a4 + v15) = 0,
          v6 < v13 + v16) )
    {
      result = 122;
      *a3 = v13 + v16;
    }
    else
    {
      *((_WORD *)a4 + v15) = 33;
      ARI::ProcessToken::SysAppId::GetPackageRelativeApplicationId(
        this,
        (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)(v6 - (unsigned int)v15 - 1),
        (unsigned int)&v20,
        (unsigned int *)((char *)a4 + 2 * (unsigned int)v15 + 2),
        v20);
      *a3 = v15 + v13 + 1;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001d0dc  push    rbx
0x14001d0de  push    rbp
0x14001d0df  push    rsi
0x14001d0e0  push    rdi
0x14001d0e1  push    r12
0x14001d0e3  push    r13
0x14001d0e5  push    r14
0x14001d0e7  push    r15
0x14001d0e9  sub     rsp, 48h
0x14001d0ed  mov     rsi, r9
0x14001d0f0  mov     dword ptr [rsp+88h+var_68], 0; unsigned __int16 *
0x14001d0f8  mov     r12, r8
0x14001d0fb  mov     edi, edx
0x14001d0fd  xor     r9d, r9d; unsigned int *
0x14001d100  lea     r8, [rsp+88h+var_68]; unsigned int
0x14001d105  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x14001d107  mov     r15, rcx
0x14001d10a  call    ?GetPackageRelativeApplicationId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetPackageRelativeApplicationId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x14001d10f  cmp     eax, 7Ah ; 'z'
0x14001d112  jnz     loc_14001D1D5
0x14001d118  mov     rbx, [r15+20h]
0x14001d11c  mov     edx, 5Fh ; '_'; Ch
0x14001d121  movzx   eax, word ptr [rbx]
0x14001d124  mov     rcx, [rbx+8]; Str
0x14001d128  shr     eax, 1
0x14001d12a  mov     dword ptr [rsp+88h+var_60], eax
0x14001d12e  call    cs:__imp_wcschr
0x14001d134  mov     rcx, [rbx+8]
0x14001d138  add     rax, 2
0x14001d13c  mov     r14d, dword ptr [rsp+88h+var_68]
0x14001d141  sub     rax, rcx
0x14001d144  sar     rax, 1
0x14001d147  mov     [rsp+88h+var_58], rcx
0x14001d14c  lea     ebp, [rax+0Dh]
0x14001d14f  lea     r13d, [rbp+1]
0x14001d153  cmp     edi, r13d
0x14001d156  jb      short loc_14001D1C8
0x14001d158  mov     eax, eax
0x14001d15a  mov     rdx, rcx; Src
0x14001d15d  mov     rcx, rsi; void *
0x14001d160  lea     rbx, [rax+rax]
0x14001d164  mov     r8, rbx; Size
0x14001d167  call    memcpy_0
0x14001d16c  mov     rcx, [rsp+88h+var_60]
0x14001d171  mov     rax, [rsp+88h+var_58]
0x14001d176  add     ecx, 0FFFFFFF3h
0x14001d179  movups  xmm0, xmmword ptr [rax+rcx*2]
0x14001d17d  movups  xmmword ptr [rbx+rsi], xmm0
0x14001d181  movups  xmm1, xmmword ptr [rax+rcx*2+0Ah]
0x14001d186  xor     eax, eax
0x14001d188  mov     ecx, ebp
0x14001d18a  movups  xmmword ptr [rbx+rsi+0Ah], xmm1
0x14001d18f  mov     [rsi+rbp*2], ax
0x14001d193  lea     eax, [r14+r13]
0x14001d197  cmp     edi, eax
0x14001d199  jb      short loc_14001D1C8
0x14001d19b  inc     rcx
0x14001d19e  mov     word ptr [rsi+rbp*2], 21h ; '!'
0x14001d1a4  sub     edi, ebp
0x14001d1a6  lea     r8, [rsp+88h+var_68]; unsigned int
0x14001d1ab  lea     r9, [rsi+rcx*2]; unsigned int *
0x14001d1af  mov     rcx, r15; this
0x14001d1b2  lea     edx, [rdi-1]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x14001d1b5  call    ?GetPackageRelativeApplicationId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetPackageRelativeApplicationId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x14001d1ba  lea     eax, [r14+1]
0x14001d1be  add     eax, ebp
0x14001d1c0  mov     [r12], eax
0x14001d1c4  xor     eax, eax
0x14001d1c6  jmp     short loc_14001D1D5
0x14001d1c8  lea     ecx, [r14+r13]
0x14001d1cc  mov     eax, 7Ah ; 'z'
0x14001d1d1  mov     [r12], ecx
0x14001d1d5  add     rsp, 48h
0x14001d1d9  pop     r15
0x14001d1db  pop     r14
0x14001d1dd  pop     r13
0x14001d1df  pop     r12
0x14001d1e1  pop     rdi
0x14001d1e2  pop     rsi
0x14001d1e3  pop     rbp
0x14001d1e4  pop     rbx
0x14001d1e5  retn
```
