# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x1800222b4`
- end: `0x1800224df`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180021a98`

## callees

- `0x18000bb40`
- `0x18000bb78`
- `0x180011698`
- `0x1800116e4`
- `0x18001b1ac`
- `0x1800222b4`
- `0x1800224e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002231d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180022340`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800223d2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180022476`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002231d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180022340`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800223d2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180022476`

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
  __int64 v15; // r12
  int v16; // edx
  const wchar_t *v17; // r13
  const wchar_t *v18; // rdi
  wchar_t *v19; // rax
  rsize_t v20; // rsi
  int v21; // ebx
  errno_t v22; // eax
  errno_t v23; // eax
  int v24; // [rsp+20h] [rbp-58h]
  int v25; // [rsp+24h] [rbp-54h]
  wchar_t *Destination; // [rsp+28h] [rbp-50h]
  unsigned __int64 v27; // [rsp+30h] [rbp-48h]
  int v30; // [rsp+98h] [rbp+20h]

  v3 = a1;
  result = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(a2);
  v7 = (int)result;
  if ( (_DWORD)result )
  {
    v8 = ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v6);
    v9 = *v3;
    v10 = 0;
    v11 = v8;
    v30 = v8;
    v24 = 0;
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
          v24 = v10;
        }
        v9 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v9) + 1);
      }
      while ( (unsigned __int64)v9 < v12 );
      if ( v10 > 0 )
      {
        v15 = *((int *)*v3 - 4);
        v25 = v15 + v10 * (v11 - v7);
        v16 = v25;
        if ( v25 <= (int)v15 )
          v16 = *((_DWORD *)*v3 - 4);
        if ( ((*((_DWORD *)*v3 - 3) - v16) | (1 - *((_DWORD *)*v3 - 2))) < 0 )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v3);
        v17 = *v3;
        v18 = *v3;
        v27 = (unsigned __int64)&(*v3)[v15];
        if ( (unsigned __int64)*v3 < v27 )
        {
          do
          {
            v19 = wcsstr(v18, a2);
            Destination = v19;
            if ( v19 )
            {
              v20 = v30;
              do
              {
                v18 = &v19[v20];
                v21 = v15 - (v19 - v17) - v7;
                v22 = memmove_s(&v19[v20], 2LL * v21, &v19[v7], 2LL * v21);
                ATL::AtlCrtErrorCheck(v22);
                v23 = memcpy_s(Destination, v20 * 2, a3, v20 * 2);
                ATL::AtlCrtErrorCheck(v23);
                Destination[v21 + v30] = 0;
                LODWORD(v15) = v30 - v7 + v15;
                v19 = wcsstr(v18, a2);
                Destination = v19;
              }
              while ( v19 );
            }
            v18 += (int)(ATL::ChTraitsCRT<unsigned short>::SafeStringLen(v18) + 1);
          }
          while ( (unsigned __int64)v18 < v27 );
          v3 = a1;
          v10 = v24;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetLength(v3, (unsigned int)v25);
      }
    }
    return (unsigned int)v10;
  }
  return result;
}

```

## disassembly

```asm
0x1800222b4  mov     [rsp+arg_8], rbx
0x1800222b9  mov     [rsp+Source], r8
0x1800222be  mov     [rsp+arg_0], rcx
0x1800222c3  push    rbp
0x1800222c4  push    rsi
0x1800222c5  push    rdi
0x1800222c6  push    r12
0x1800222c8  push    r13
0x1800222ca  push    r14
0x1800222cc  push    r15
0x1800222ce  sub     rsp, 40h
0x1800222d2  mov     rsi, rcx
0x1800222d5  mov     r15, rdx
0x1800222d8  mov     rcx, rdx
0x1800222db  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x1800222e0  movsxd  r14, eax
0x1800222e3  test    eax, eax
0x1800222e5  jz      loc_1800224C6
0x1800222eb  mov     rcx, r8
0x1800222ee  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x1800222f3  mov     rbx, [rsi]
0x1800222f6  xor     ebp, ebp
0x1800222f8  mov     r13d, eax
0x1800222fb  mov     [rsp+78h+arg_18], eax
0x180022302  mov     [rsp+78h+var_58], ebp
0x180022306  movsxd  rcx, dword ptr [rbx-10h]
0x18002230a  lea     r12, [rbx+rcx*2]
0x18002230e  cmp     rbx, r12
0x180022311  jnb     loc_1800224C4
0x180022317  mov     rdx, r15; SubStr
0x18002231a  mov     rcx, rbx; Str
0x18002231d  call    cs:__imp_wcsstr
0x180022324  nop     dword ptr [rax+rax+00h]
0x180022329  test    rax, rax
0x18002232c  jz      short loc_180022355
0x18002232e  mov     rdi, r14
0x180022331  add     rdi, rdi
0x180022334  lea     rbx, [rdi+rax]
0x180022338  mov     rdx, r15; SubStr
0x18002233b  mov     rcx, rbx; Str
0x18002233e  inc     ebp
0x180022340  call    cs:__imp_wcsstr
0x180022347  nop     dword ptr [rax+rax+00h]
0x18002234c  test    rax, rax
0x18002234f  jnz     short loc_180022334
0x180022351  mov     [rsp+78h+var_58], ebp
0x180022355  mov     rcx, rbx
0x180022358  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x18002235d  inc     eax
0x18002235f  cdqe
0x180022361  lea     rbx, [rbx+rax*2]
0x180022365  cmp     rbx, r12
0x180022368  jb      short loc_180022317
0x18002236a  test    ebp, ebp
0x18002236c  jle     loc_1800224C4
0x180022372  mov     r8, [rsi]
0x180022375  mov     eax, r13d
0x180022378  sub     eax, r14d
0x18002237b  mov     ecx, 1
0x180022380  imul    eax, ebp
0x180022383  movsxd  r12, dword ptr [r8-10h]
0x180022387  add     eax, r12d
0x18002238a  cmp     eax, r12d
0x18002238d  mov     [rsp+78h+var_54], eax
0x180022391  mov     edx, eax
0x180022393  mov     eax, [r8-0Ch]
0x180022397  cmovle  edx, r12d
0x18002239b  sub     ecx, [r8-8]
0x18002239f  sub     eax, edx
0x1800223a1  or      ecx, eax
0x1800223a3  jge     short loc_1800223AD
0x1800223a5  mov     rcx, rsi
0x1800223a8  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800223ad  mov     r13, [rsi]
0x1800223b0  lea     rax, ds:0[r12*2]
0x1800223b8  add     rax, r13
0x1800223bb  mov     rdi, r13
0x1800223be  mov     [rsp+78h+var_48], rax
0x1800223c3  cmp     r13, rax
0x1800223c6  jnb     loc_1800224B8
0x1800223cc  mov     rdx, r15; SubStr
0x1800223cf  mov     rcx, rdi; Str
0x1800223d2  call    cs:__imp_wcsstr
0x1800223d9  nop     dword ptr [rax+rax+00h]
0x1800223de  mov     [rsp+78h+Destination], rax
0x1800223e3  test    rax, rax
0x1800223e6  jz      loc_180022490
0x1800223ec  movsxd  rsi, [rsp+78h+arg_18]
0x1800223f4  mov     rbp, r14
0x1800223f7  add     rbp, rbp
0x1800223fa  add     rsi, rsi
0x1800223fd  mov     rcx, rax
0x180022400  lea     rdi, [rsi+rax]
0x180022404  sub     rcx, r13
0x180022407  lea     r8, [rax+rbp]; Source
0x18002240b  sar     rcx, 1
0x18002240e  mov     ebx, r12d
0x180022411  sub     ebx, ecx
0x180022413  mov     rcx, rdi; Destination
0x180022416  sub     ebx, r14d
0x180022419  movsxd  rdx, ebx
0x18002241c  add     rdx, rdx; DestinationSize
0x18002241f  mov     r9, rdx; SourceSize
0x180022422  call    memmove_s
0x180022427  mov     ecx, eax; int
0x180022429  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002242e  mov     r8, [rsp+78h+Source]; Source
0x180022436  mov     r9, rsi; SourceSize
0x180022439  mov     rcx, [rsp+78h+Destination]; Destination
0x18002243e  mov     rdx, rsi; DestinationSize
0x180022441  call    memcpy_s
0x180022446  mov     ecx, eax; int
0x180022448  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002244d  mov     r8d, [rsp+78h+arg_18]
0x180022455  mov     rdx, [rsp+78h+Destination]
0x18002245a  lea     eax, [rbx+r8]
0x18002245e  movsxd  rcx, eax
0x180022461  xor     eax, eax
0x180022463  mov     [rdx+rcx*2], ax
0x180022467  mov     eax, r8d
0x18002246a  sub     eax, r14d
0x18002246d  mov     rdx, r15; SubStr
0x180022470  mov     rcx, rdi; Str
0x180022473  add     r12d, eax
0x180022476  call    cs:__imp_wcsstr
0x18002247d  nop     dword ptr [rax+rax+00h]
0x180022482  mov     [rsp+78h+Destination], rax
0x180022487  test    rax, rax
0x18002248a  jnz     loc_1800223FD
0x180022490  mov     rcx, rdi
0x180022493  call    ?SafeStringLen@?$ChTraitsCRT@G@ATL@@SAHPEBG@Z; ATL::ChTraitsCRT<ushort>::SafeStringLen(ushort const *)
0x180022498  inc     eax
0x18002249a  movsxd  rcx, eax
0x18002249d  lea     rdi, [rdi+rcx*2]
0x1800224a1  cmp     rdi, [rsp+78h+var_48]
0x1800224a6  jb      loc_1800223CC
0x1800224ac  mov     rsi, [rsp+78h+arg_0]
0x1800224b4  mov     ebp, [rsp+78h+var_58]
0x1800224b8  mov     edx, [rsp+78h+var_54]
0x1800224bc  mov     rcx, rsi
0x1800224bf  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800224c4  mov     eax, ebp
0x1800224c6  mov     rbx, [rsp+78h+arg_8]
0x1800224ce  add     rsp, 40h
0x1800224d2  pop     r15
0x1800224d4  pop     r14
0x1800224d6  pop     r13
0x1800224d8  pop     r12
0x1800224da  pop     rdi
0x1800224db  pop     rsi
0x1800224dc  pop     rbp
0x1800224dd  retn
```
