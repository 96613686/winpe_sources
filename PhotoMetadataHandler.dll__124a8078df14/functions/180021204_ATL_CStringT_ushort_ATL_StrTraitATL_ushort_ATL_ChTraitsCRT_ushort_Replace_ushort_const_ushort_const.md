# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x180021204`
- end: `0x180021416`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `530`
- prototype: `__int64 __fastcall(const wchar_t **, const wchar_t *, const void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180020a30`

## callees

- `0x18000b5e0`
- `0x18000b618`
- `0x180010e60`
- `0x180010eac`
- `0x18001a528`
- `0x180021204`
- `0x18002141c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002126d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002128a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180021316`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800213b4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002126d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002128a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180021316`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800213b4`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        const wchar_t **a1,
        const wchar_t *a2,
        const void *a3)
{
  const wchar_t **v3; // rsi
  __int64 result; // rax
  __int64 v6; // r8
  __int64 v7; // r14
  int v8; // eax
  const wchar_t *v9; // rbx
  int v10; // ebp
  int v11; // r13d
  unsigned __int64 v12; // r12
  wchar_t *v13; // rax
  __int64 v14; // rdi
  __int64 v15; // r9
  const wchar_t *v16; // r8
  __int64 v17; // r12
  __int64 v18; // rdx
  const wchar_t *v19; // r13
  const wchar_t *v20; // rdi
  wchar_t *v21; // rax
  rsize_t v22; // rsi
  int v23; // ebx
  errno_t v24; // eax
  errno_t v25; // eax
  int v26; // [rsp+20h] [rbp-58h]
  unsigned int v27; // [rsp+24h] [rbp-54h]
  wchar_t *Destination; // [rsp+28h] [rbp-50h]
  unsigned __int64 v29; // [rsp+30h] [rbp-48h]
  int v32; // [rsp+98h] [rbp+20h]

  v3 = a1;
  result = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(a2);
  v7 = (int)result;
  if ( (_DWORD)result )
  {
    v8 = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v6);
    v9 = *v3;
    v10 = 0;
    v11 = v8;
    v32 = v8;
    v26 = 0;
    v12 = (unsigned __int64)&(*v3)[*((int *)*v3 - 4)];
    if ( (unsigned __int64)*v3 < v12 )
    {
      do
      {
        v13 = wcsstr(v9, a2);
        if ( v13 )
        {
          v14 = v7;
          do
          {
            v9 = &v13[v14];
            ++v10;
            v13 = wcsstr(&v13[v14], a2);
          }
          while ( v13 );
          v26 = v10;
        }
        v9 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v9) + 1);
      }
      while ( (unsigned __int64)v9 < v12 );
      if ( v10 > 0 )
      {
        v16 = *v3;
        v17 = *((int *)*v3 - 4);
        v27 = v17 + v10 * (v11 - v7);
        v18 = v27;
        if ( (int)v27 <= (int)v17 )
          v18 = (unsigned int)v17;
        if ( (int)((*((_DWORD *)*v3 - 3) - v18) | (1 - *((_DWORD *)v16 - 2))) < 0 )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v3, v18, v16, v15);
        v19 = *v3;
        v20 = *v3;
        v29 = (unsigned __int64)&(*v3)[v17];
        if ( (unsigned __int64)*v3 < v29 )
        {
          do
          {
            v21 = wcsstr(v20, a2);
            Destination = v21;
            if ( v21 )
            {
              v22 = v32;
              do
              {
                v20 = &v21[v22];
                v23 = v17 - (v21 - v19) - v7;
                v24 = memmove_s(&v21[v22], 2LL * v23, &v21[v7], 2LL * v23);
                ATL::AtlCrtErrorCheck(v24);
                v25 = memcpy_s(Destination, v22 * 2, a3, v22 * 2);
                ATL::AtlCrtErrorCheck(v25);
                Destination[v23 + v32] = 0;
                LODWORD(v17) = v32 - v7 + v17;
                v21 = wcsstr(v20, a2);
                Destination = v21;
              }
              while ( v21 );
            }
            v20 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v20) + 1);
          }
          while ( (unsigned __int64)v20 < v29 );
          v3 = a1;
          v10 = v26;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetLength(v3, v27, v16, v15);
      }
    }
    return (unsigned int)v10;
  }
  return result;
}

```

## disassembly

```asm
0x180021204  mov     [rsp+arg_8], rbx
0x180021209  mov     [rsp+Source], r8
0x18002120e  mov     [rsp+arg_0], rcx
0x180021213  push    rbp
0x180021214  push    rsi
0x180021215  push    rdi
0x180021216  push    r12
0x180021218  push    r13
0x18002121a  push    r14
0x18002121c  push    r15
0x18002121e  sub     rsp, 40h
0x180021222  mov     rsi, rcx
0x180021225  mov     r15, rdx
0x180021228  mov     rcx, rdx
0x18002122b  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x180021230  movsxd  r14, eax
0x180021233  test    eax, eax
0x180021235  jz      loc_1800213FE
0x18002123b  mov     rcx, r8
0x18002123e  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x180021243  mov     rbx, [rsi]
0x180021246  xor     ebp, ebp
0x180021248  mov     r13d, eax
0x18002124b  mov     [rsp+78h+arg_18], eax
0x180021252  mov     [rsp+78h+var_58], ebp
0x180021256  movsxd  rcx, dword ptr [rbx-10h]
0x18002125a  lea     r12, [rbx+rcx*2]
0x18002125e  cmp     rbx, r12
0x180021261  jnb     loc_1800213FC
0x180021267  mov     rdx, r15; SubStr
0x18002126a  mov     rcx, rbx; Str
0x18002126d  call    cs:__imp_wcsstr
0x180021273  test    rax, rax
0x180021276  jz      short loc_180021299
0x180021278  mov     rdi, r14
0x18002127b  add     rdi, rdi
0x18002127e  lea     rbx, [rdi+rax]
0x180021282  mov     rdx, r15; SubStr
0x180021285  mov     rcx, rbx; Str
0x180021288  inc     ebp
0x18002128a  call    cs:__imp_wcsstr
0x180021290  test    rax, rax
0x180021293  jnz     short loc_18002127E
0x180021295  mov     [rsp+78h+var_58], ebp
0x180021299  mov     rcx, rbx
0x18002129c  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x1800212a1  inc     eax
0x1800212a3  cdqe
0x1800212a5  lea     rbx, [rbx+rax*2]
0x1800212a9  cmp     rbx, r12
0x1800212ac  jb      short loc_180021267
0x1800212ae  test    ebp, ebp
0x1800212b0  jle     loc_1800213FC
0x1800212b6  mov     r8, [rsi]
0x1800212b9  mov     eax, r13d
0x1800212bc  sub     eax, r14d
0x1800212bf  mov     ecx, 1
0x1800212c4  imul    eax, ebp
0x1800212c7  movsxd  r12, dword ptr [r8-10h]
0x1800212cb  add     eax, r12d
0x1800212ce  cmp     eax, r12d
0x1800212d1  mov     [rsp+78h+var_54], eax
0x1800212d5  mov     edx, eax
0x1800212d7  mov     eax, [r8-0Ch]
0x1800212db  cmovle  edx, r12d
0x1800212df  sub     ecx, [r8-8]
0x1800212e3  sub     eax, edx
0x1800212e5  or      ecx, eax
0x1800212e7  jge     short loc_1800212F1
0x1800212e9  mov     rcx, rsi
0x1800212ec  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800212f1  mov     r13, [rsi]
0x1800212f4  lea     rax, ds:0[r12*2]
0x1800212fc  add     rax, r13
0x1800212ff  mov     rdi, r13
0x180021302  mov     [rsp+78h+var_48], rax
0x180021307  cmp     r13, rax
0x18002130a  jnb     loc_1800213F0
0x180021310  mov     rdx, r15; SubStr
0x180021313  mov     rcx, rdi; Str
0x180021316  call    cs:__imp_wcsstr
0x18002131c  mov     [rsp+78h+Destination], rax
0x180021321  test    rax, rax
0x180021324  jz      loc_1800213C8
0x18002132a  movsxd  rsi, [rsp+78h+arg_18]
0x180021332  mov     rbp, r14
0x180021335  add     rbp, rbp
0x180021338  add     rsi, rsi
0x18002133b  mov     rcx, rax
0x18002133e  lea     rdi, [rsi+rax]
0x180021342  sub     rcx, r13
0x180021345  lea     r8, [rax+rbp]; Source
0x180021349  sar     rcx, 1
0x18002134c  mov     ebx, r12d
0x18002134f  sub     ebx, ecx
0x180021351  mov     rcx, rdi; Destination
0x180021354  sub     ebx, r14d
0x180021357  movsxd  rdx, ebx
0x18002135a  add     rdx, rdx; DestinationSize
0x18002135d  mov     r9, rdx; SourceSize
0x180021360  call    memmove_s
0x180021365  mov     ecx, eax; int
0x180021367  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002136c  mov     r8, [rsp+78h+Source]; Source
0x180021374  mov     r9, rsi; SourceSize
0x180021377  mov     rcx, [rsp+78h+Destination]; Destination
0x18002137c  mov     rdx, rsi; DestinationSize
0x18002137f  call    memcpy_s
0x180021384  mov     ecx, eax; int
0x180021386  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002138b  mov     r8d, [rsp+78h+arg_18]
0x180021393  mov     rdx, [rsp+78h+Destination]
0x180021398  lea     eax, [rbx+r8]
0x18002139c  movsxd  rcx, eax
0x18002139f  xor     eax, eax
0x1800213a1  mov     [rdx+rcx*2], ax
0x1800213a5  mov     eax, r8d
0x1800213a8  sub     eax, r14d
0x1800213ab  mov     rdx, r15; SubStr
0x1800213ae  mov     rcx, rdi; Str
0x1800213b1  add     r12d, eax
0x1800213b4  call    cs:__imp_wcsstr
0x1800213ba  mov     [rsp+78h+Destination], rax
0x1800213bf  test    rax, rax
0x1800213c2  jnz     loc_18002133B
0x1800213c8  mov     rcx, rdi
0x1800213cb  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x1800213d0  inc     eax
0x1800213d2  movsxd  rcx, eax
0x1800213d5  lea     rdi, [rdi+rcx*2]
0x1800213d9  cmp     rdi, [rsp+78h+var_48]
0x1800213de  jb      loc_180021310
0x1800213e4  mov     rsi, [rsp+78h+arg_0]
0x1800213ec  mov     ebp, [rsp+78h+var_58]
0x1800213f0  mov     edx, [rsp+78h+var_54]
0x1800213f4  mov     rcx, rsi
0x1800213f7  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800213fc  mov     eax, ebp
0x1800213fe  mov     rbx, [rsp+78h+arg_8]
0x180021406  add     rsp, 40h
0x18002140a  pop     r15
0x18002140c  pop     r14
0x18002140e  pop     r13
0x180021410  pop     r12
0x180021412  pop     rdi
0x180021413  pop     rsi
0x180021414  pop     rbp
0x180021415  retn
```
