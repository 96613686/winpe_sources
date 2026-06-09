# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x180018228`
- end: `0x18001841b`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `499`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800166b4`

## callees

- `0x180002382`
- `0x1800027bd`
- `0x180003bb8`
- `0x180007724`
- `0x180015b80`
- `0x180018228`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800183ff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800183ff`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180018279`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180018305`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180018388`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180018279`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180018305`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180018388`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        __int64 *a1)
{
  const wchar_t *v1; // rbx
  int v2; // r14d
  unsigned __int64 v3; // rdi
  wchar_t *v4; // rax
  __int64 v5; // rax
  __int64 v6; // r15
  int v7; // edi
  int v8; // edx
  __int64 v9; // r12
  const wchar_t *v10; // rbx
  unsigned __int64 v11; // r13
  const void *v12; // rdx
  wchar_t *v13; // rbp
  __int64 v14; // rcx
  int v15; // r13d
  size_t v16; // r8
  __int64 v17; // rax
  unsigned __int64 v19; // [rsp+20h] [rbp-38h]
  unsigned __int64 v21; // [rsp+70h] [rbp+18h]

  v1 = (const wchar_t *)*a1;
  v2 = 0;
  v3 = *a1 + 2LL * *(int *)(*a1 - 16);
  if ( *a1 < v3 )
  {
    do
    {
      while ( 1 )
      {
        v4 = wcsstr(v1, L"\\Framework64\\");
        if ( !v4 )
          break;
        ++v2;
        v1 = v4 + 13;
      }
      if ( v1 )
      {
        v5 = -1;
        do
          ++v5;
        while ( v1[v5] );
      }
      else
      {
        LODWORD(v5) = 0;
      }
      v1 += (int)v5 + 1;
    }
    while ( (unsigned __int64)v1 < v3 );
    if ( v2 > 0 )
    {
      v6 = *(int *)(*a1 - 16);
      v7 = *(_DWORD *)(*a1 - 16) - 2 * v2;
      v8 = v7;
      if ( v7 <= (int)v6 )
        v8 = *(_DWORD *)(*a1 - 16);
      if ( ((*(_DWORD *)(*a1 - 12) - v8) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v8);
      v9 = *a1;
      v10 = (const wchar_t *)*a1;
      v11 = *a1 + 2 * v6;
      v21 = v11;
      if ( *a1 < v11 )
      {
        do
        {
          v13 = wcsstr(v10, L"\\Framework64\\");
          if ( v13 )
          {
            do
            {
              v10 = v13 + 11;
              v14 = ((__int64)v13 - v9) >> 1;
              v15 = v6 - v14 - 13;
              v16 = 2LL * v15;
              if ( v16 )
              {
                if ( v13 == (wchar_t *)-22LL || (v12 = v13 + 13, v13 == (wchar_t *)-26LL) )
                {
                  *(_DWORD *)_o__errno(v14, v12, v16, 0) = 22;
                  invalid_parameter_noinfo();
                  goto LABEL_35;
                }
                memmove_0(v13 + 11, v12, v16);
              }
              ATL::Checked::memcpy_s(
                (ATL::Checked *)v13,
                (void *)0x16,
                (unsigned __int64)L"\\Framework\\",
                (const void *)0x16,
                v19);
              LODWORD(v6) = v6 - 2;
              v13[v15 + 11] = 0;
              v13 = wcsstr(v13 + 11, L"\\Framework64\\");
            }
            while ( v13 );
            v11 = v21;
          }
          if ( v10 )
          {
            v17 = -1;
            do
              ++v17;
            while ( v10[v17] );
          }
          else
          {
            LODWORD(v17) = 0;
          }
          v10 += (int)v17 + 1;
        }
        while ( (unsigned __int64)v10 < v11 );
      }
      if ( v7 < 0 || v7 > *(_DWORD *)(*a1 - 12) )
LABEL_35:
        ATL::AtlThrowImpl(-2147024809);
      *(_DWORD *)(*a1 - 16) = v7;
      *(_WORD *)(*a1 + 2LL * v7) = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180018228  mov     [rsp+arg_8], rbx
0x18001822d  mov     [rsp+arg_10], r8
0x180018232  mov     [rsp+arg_0], rcx
0x180018237  push    rbp
0x180018238  push    rsi
0x180018239  push    rdi
0x18001823a  push    r12
0x18001823c  push    r13
0x18001823e  push    r14
0x180018240  push    r15
0x180018242  sub     rsp, 20h
0x180018246  mov     rbx, [rcx]
0x180018249  xor     eax, eax
0x18001824b  mov     r14d, eax
0x18001824e  movsxd  rax, dword ptr [rbx-10h]
0x180018252  lea     rdi, [rbx+rax*2]
0x180018256  cmp     rbx, rdi
0x180018259  jnb     loc_1800183E7
0x18001825f  mov     ebp, 1
0x180018264  xor     esi, esi
0x180018266  jmp     short loc_18001826F
0x180018268  add     r14d, ebp
0x18001826b  lea     rbx, [rax+1Ah]
0x18001826f  lea     rdx, aFramework64; "\\Framework64\\"
0x180018276  mov     rcx, rbx; Str
0x180018279  call    cs:__imp_wcsstr
0x18001827f  test    rax, rax
0x180018282  jnz     short loc_180018268
0x180018284  test    rbx, rbx
0x180018287  jz      short loc_180018298
0x180018289  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001828d  inc     rax
0x180018290  cmp     [rbx+rax*2], si
0x180018294  jnz     short loc_18001828D
0x180018296  jmp     short loc_18001829A
0x180018298  mov     eax, esi
0x18001829a  inc     eax
0x18001829c  movsxd  rcx, eax
0x18001829f  lea     rbx, [rbx+rcx*2]
0x1800182a3  cmp     rbx, rdi
0x1800182a6  jb      short loc_18001826F
0x1800182a8  mov     rsi, [rsp+58h+arg_0]
0x1800182ad  test    r14d, r14d
0x1800182b0  jle     loc_1800183E7
0x1800182b6  mov     rcx, [rsi]
0x1800182b9  lea     eax, [r14+r14]
0x1800182bd  movsxd  r15, dword ptr [rcx-10h]
0x1800182c1  mov     edi, r15d
0x1800182c4  sub     edi, eax
0x1800182c6  mov     eax, [rcx-0Ch]
0x1800182c9  cmp     edi, r15d
0x1800182cc  mov     edx, edi
0x1800182ce  cmovle  edx, r15d
0x1800182d2  sub     ebp, [rcx-8]
0x1800182d5  sub     eax, edx
0x1800182d7  or      ebp, eax
0x1800182d9  jge     short loc_1800182E3
0x1800182db  mov     rcx, rsi
0x1800182de  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800182e3  mov     r12, [rsi]
0x1800182e6  mov     rbx, r12
0x1800182e9  lea     r13, [r12+r15*2]
0x1800182ed  mov     [rsp+58h+arg_10], r13
0x1800182f2  cmp     r12, r13
0x1800182f5  jnb     loc_1800183CA
0x1800182fb  lea     rdx, aFramework64; "\\Framework64\\"
0x180018302  mov     rcx, rbx; Str
0x180018305  call    cs:__imp_wcsstr
0x18001830b  xor     r9d, r9d
0x18001830e  mov     rbp, rax
0x180018311  test    rax, rax
0x180018314  jz      loc_18001839E
0x18001831a  mov     rcx, rbp
0x18001831d  lea     rbx, [rbp+16h]
0x180018321  sub     rcx, r12
0x180018324  mov     r13d, r15d
0x180018327  sar     rcx, 1
0x18001832a  sub     r13d, ecx
0x18001832d  add     r13d, 0FFFFFFF3h
0x180018331  movsxd  r8, r13d
0x180018334  add     r8, r8; Size
0x180018337  jz      short loc_180018357
0x180018339  test    rbx, rbx
0x18001833c  jz      loc_1800183FF
0x180018342  lea     rdx, [rbp+1Ah]; Src
0x180018346  test    rdx, rdx
0x180018349  jz      loc_1800183FF
0x18001834f  mov     rcx, rbx; void *
0x180018352  call    memmove_0
0x180018357  mov     eax, 16h
0x18001835c  lea     r8, aFramework; "\\Framework\\"
0x180018363  mov     r9d, eax; void *
0x180018366  mov     edx, eax; void *
0x180018368  mov     rcx, rbp; this
0x18001836b  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180018370  movsxd  rcx, r13d
0x180018373  lea     rdx, aFramework64; "\\Framework64\\"
0x18001837a  xor     eax, eax
0x18001837c  sub     r15d, 2
0x180018380  mov     [rbp+rcx*2+16h], ax
0x180018385  mov     rcx, rbx; Str
0x180018388  call    cs:__imp_wcsstr
0x18001838e  xor     r9d, r9d
0x180018391  mov     rbp, rax
0x180018394  test    rax, rax
0x180018397  jnz     short loc_18001831A
0x180018399  mov     r13, [rsp+58h+arg_10]
0x18001839e  test    rbx, rbx
0x1800183a1  jz      short loc_1800183B3
0x1800183a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800183a7  inc     rax
0x1800183aa  cmp     [rbx+rax*2], r9w
0x1800183af  jnz     short loc_1800183A7
0x1800183b1  jmp     short loc_1800183B6
0x1800183b3  mov     eax, r9d
0x1800183b6  inc     eax
0x1800183b8  movsxd  rcx, eax
0x1800183bb  lea     rbx, [rbx+rcx*2]
0x1800183bf  cmp     rbx, r13
0x1800183c2  jb      loc_1800182FB
0x1800183c8  jmp     short loc_1800183CD
0x1800183ca  xor     r9d, r9d
0x1800183cd  test    edi, edi
0x1800183cf  js      short loc_180018410
0x1800183d1  mov     rax, [rsi]
0x1800183d4  cmp     edi, [rax-0Ch]
0x1800183d7  jg      short loc_180018410
0x1800183d9  mov     [rax-10h], edi
0x1800183dc  mov     rcx, [rsi]
0x1800183df  movsxd  rdx, edi
0x1800183e2  mov     [rcx+rdx*2], r9w
0x1800183e7  mov     rbx, [rsp+58h+arg_8]
0x1800183ec  mov     eax, r14d
0x1800183ef  add     rsp, 20h
0x1800183f3  pop     r15
0x1800183f5  pop     r14
0x1800183f7  pop     r13
0x1800183f9  pop     r12
0x1800183fb  pop     rdi
0x1800183fc  pop     rsi
0x1800183fd  pop     rbp
0x1800183fe  retn
0x1800183ff  call    cs:__imp__o__errno
0x180018405  mov     dword ptr [rax], 16h
0x18001840b  call    _invalid_parameter_noinfo
0x180018410  mov     ecx, 80070057h; int
0x180018415  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
