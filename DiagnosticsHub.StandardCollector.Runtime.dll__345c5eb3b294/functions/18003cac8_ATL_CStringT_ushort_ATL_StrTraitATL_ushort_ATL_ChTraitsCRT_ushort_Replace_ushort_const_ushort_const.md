# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)

- ea: `0x18003cac8`
- end: `0x18003cd51`
- name: `?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z`
- size: `649`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003ae24`

## callees

- `0x180002354`
- `0x180002604`
- `0x18003cac8`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x18003cc84`
- `VCRUNTIME140!memcpy` at `0x18003cc84`
- `VCRUNTIME140!memmove` at `0x18003cc60`
- `VCRUNTIME140!memmove` at `0x18003cc60`
- `VCRUNTIME140!wcsstr` at `0x18003cb44`
- `VCRUNTIME140!wcsstr` at `0x18003cb62`
- `VCRUNTIME140!wcsstr` at `0x18003cbfa`
- `VCRUNTIME140!wcsstr` at `0x18003ccb9`
- `VCRUNTIME140!wcsstr` at `0x18003cb44`
- `VCRUNTIME140!wcsstr` at `0x18003cb62`
- `VCRUNTIME140!wcsstr` at `0x18003cbfa`
- `VCRUNTIME140!wcsstr` at `0x18003ccb9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18003cd34`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18003cd34`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18003cd40`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18003cd40`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003caf0`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003cb13`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003cb75`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003cce3`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003caf0`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003cb13`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003cb75`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003cce3`

## pseudocode

```c
size_t __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        const wchar_t **a1)
{
  size_t result; // rax
  int v3; // r15d
  int v4; // eax
  const wchar_t *v5; // rbx
  int v6; // ebp
  unsigned __int64 v7; // rdi
  wchar_t *i; // rax
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // r13
  __int64 v12; // rdx
  int v13; // edi
  const wchar_t *v14; // r12
  const wchar_t *v15; // rbx
  wchar_t *v16; // rsi
  __int64 v17; // rdx
  size_t v18; // r15
  wchar_t *v19; // rdx
  wchar_t *v20; // rax
  int v21; // eax
  __int64 v22; // [rsp+20h] [rbp-48h]
  unsigned __int64 v23; // [rsp+28h] [rbp-40h]
  int v24; // [rsp+78h] [rbp+10h]
  int v25; // [rsp+80h] [rbp+18h]
  int v26; // [rsp+88h] [rbp+20h]

  result = wcslen(L"\\Framework64\\");
  v26 = result;
  v3 = result;
  if ( (_DWORD)result )
  {
    v4 = wcslen(L"\\Framework\\");
    v5 = *a1;
    v6 = 0;
    v24 = v4;
    v7 = (unsigned __int64)&(*a1)[*((int *)*a1 - 4)];
    if ( (unsigned __int64)*a1 < v7 )
    {
      do
      {
        for ( i = wcsstr(v5, L"\\Framework64\\"); i; i = wcsstr(v5, L"\\Framework64\\") )
        {
          v5 = &i[v3];
          ++v6;
        }
        if ( v5 )
          v10 = wcslen(v5);
        else
          v10 = 0;
        v5 += v10 + 1;
      }
      while ( (unsigned __int64)v5 < v7 );
      if ( v6 > 0 )
      {
        v11 = *((int *)*a1 - 4);
        v12 = (unsigned int)v11;
        v13 = v11 + v6 * (v24 - v3);
        if ( v13 > (int)v11 )
          v12 = (unsigned int)v13;
        if ( (int)v12 >= 0 )
        {
          _mm_lfence();
          if ( (int)((*((_DWORD *)*a1 - 3) - v12) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
          {
            _mm_lfence();
            ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v12, v9);
          }
          v14 = *a1;
          v15 = *a1;
          v23 = (unsigned __int64)&(*a1)[v11];
          if ( (unsigned __int64)*a1 >= v23 )
            goto LABEL_32;
          _mm_lfence();
          do
          {
            v16 = wcsstr(v15, L"\\Framework64\\");
            if ( !v16 )
              goto LABEL_28;
            v17 = v3;
            v18 = v24;
            v22 = v17;
            do
            {
              v19 = &v16[v17];
              v15 = &v16[v18];
              v25 = v11 - (v16 - v14) - v26;
              if ( 2LL * v25 )
              {
                if ( !v15 || !v19 )
                {
LABEL_37:
                  *_errno() = 22;
                  _invalid_parameter_noinfo();
                  goto LABEL_38;
                }
                memmove(&v16[v18], v19, 2LL * v25);
              }
              if ( v18 * 2 )
              {
                if ( !v16 )
                  goto LABEL_37;
                memcpy(v16, L"\\Framework\\", v18 * 2);
              }
              LODWORD(v11) = v24 - v26 + v11;
              v16[v24 + v25] = 0;
              v20 = wcsstr(&v16[v18], L"\\Framework64\\");
              v17 = v22;
              v16 = v20;
            }
            while ( v20 );
            v3 = v26;
LABEL_28:
            if ( v15 )
              v21 = wcslen(v15);
            else
              v21 = 0;
            v15 += v21 + 1;
          }
          while ( (unsigned __int64)v15 < v23 );
LABEL_32:
          if ( v13 >= 0 && v13 <= *((_DWORD *)*a1 - 3) )
          {
            *((_DWORD *)*a1 - 4) = v13;
            (*a1)[v13] = 0;
            return (unsigned int)v6;
          }
        }
LABEL_38:
        ATL::AtlThrowImpl(-2147024809);
      }
    }
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x18003cac8  mov     [rsp+arg_0], rbx
0x18003cacd  mov     [rsp+arg_10], r8
0x18003cad2  mov     [rsp+arg_8], rdx
0x18003cad7  push    rbp
0x18003cad8  push    rsi
0x18003cad9  push    rdi
0x18003cada  push    r12
0x18003cadc  push    r13
0x18003cade  push    r14
0x18003cae0  push    r15
0x18003cae2  sub     rsp, 30h
0x18003cae6  mov     r14, rcx
0x18003cae9  lea     rcx, aFramework64; "\\Framework64\\"
0x18003caf0  call    cs:__imp_wcslen
0x18003caf6  xor     r13d, r13d
0x18003caf9  mov     [rsp+68h+arg_18], rax
0x18003cb01  mov     r15, rax
0x18003cb04  test    eax, eax
0x18003cb06  jz      loc_18003CD1F
0x18003cb0c  lea     rcx, aFramework; "\\Framework\\"
0x18003cb13  call    cs:__imp_wcslen
0x18003cb19  mov     rbx, [r14]
0x18003cb1c  mov     ebp, r13d
0x18003cb1f  mov     [rsp+68h+arg_8], rax
0x18003cb24  movsxd  rcx, dword ptr [rbx-10h]
0x18003cb28  lea     rdi, [rbx+rcx*2]
0x18003cb2c  cmp     rbx, rdi
0x18003cb2f  jnb     loc_18003CD1D
0x18003cb35  mov     esi, 1
0x18003cb3a  lea     rdx, aFramework64; "\\Framework64\\"
0x18003cb41  mov     rcx, rbx; Str
0x18003cb44  call    cs:__imp_wcsstr
0x18003cb4a  test    rax, rax
0x18003cb4d  jz      short loc_18003CB6D
0x18003cb4f  movsxd  r12, r15d
0x18003cb52  lea     rbx, [rax+r12*2]
0x18003cb56  add     ebp, esi
0x18003cb58  mov     rcx, rbx; Str
0x18003cb5b  lea     rdx, aFramework64; "\\Framework64\\"
0x18003cb62  call    cs:__imp_wcsstr
0x18003cb68  test    rax, rax
0x18003cb6b  jnz     short loc_18003CB52
0x18003cb6d  test    rbx, rbx
0x18003cb70  jz      short loc_18003CB7D
0x18003cb72  mov     rcx, rbx; String
0x18003cb75  call    cs:__imp_wcslen
0x18003cb7b  jmp     short loc_18003CB80
0x18003cb7d  mov     eax, r13d
0x18003cb80  inc     eax
0x18003cb82  movsxd  rcx, eax
0x18003cb85  lea     rbx, [rbx+rcx*2]
0x18003cb89  cmp     rbx, rdi
0x18003cb8c  jb      short loc_18003CB3A
0x18003cb8e  test    ebp, ebp
0x18003cb90  jle     loc_18003CD1D
0x18003cb96  mov     edi, dword ptr [rsp+68h+arg_8]
0x18003cb9a  mov     rcx, [r14]
0x18003cb9d  sub     edi, r15d
0x18003cba0  imul    edi, ebp
0x18003cba3  movsxd  r13, dword ptr [rcx-10h]
0x18003cba7  mov     edx, r13d
0x18003cbaa  add     edi, r13d
0x18003cbad  cmp     edi, r13d
0x18003cbb0  cmovg   edx, edi
0x18003cbb3  test    edx, edx
0x18003cbb5  js      loc_18003CD46
0x18003cbbb  lfence
0x18003cbbe  mov     eax, [rcx-0Ch]
0x18003cbc1  sub     esi, [rcx-8]
0x18003cbc4  sub     eax, edx
0x18003cbc6  or      esi, eax
0x18003cbc8  jge     short loc_18003CBD5
0x18003cbca  lfence
0x18003cbcd  mov     rcx, r14
0x18003cbd0  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18003cbd5  mov     r12, [r14]
0x18003cbd8  mov     rbx, r12
0x18003cbdb  lea     rax, [r12+r13*2]
0x18003cbdf  mov     [rsp+68h+var_40], rax
0x18003cbe4  cmp     r12, rax
0x18003cbe7  jnb     loc_18003CD02
0x18003cbed  lfence
0x18003cbf0  lea     rdx, aFramework64; "\\Framework64\\"
0x18003cbf7  mov     rcx, rbx; Str
0x18003cbfa  call    cs:__imp_wcsstr
0x18003cc00  xor     r9d, r9d
0x18003cc03  mov     rsi, rax
0x18003cc06  test    rax, rax
0x18003cc09  jz      loc_18003CCDB
0x18003cc0f  movsxd  rdx, r15d
0x18003cc12  movsxd  r15, dword ptr [rsp+68h+arg_8]
0x18003cc17  add     r15, r15
0x18003cc1a  mov     [rsp+68h+var_48], rdx
0x18003cc1f  mov     rcx, rsi
0x18003cc22  lea     rdx, [rsi+rdx*2]; Src
0x18003cc26  sub     rcx, r12
0x18003cc29  lea     rbx, [r15+rsi]
0x18003cc2d  sar     rcx, 1
0x18003cc30  mov     eax, r13d
0x18003cc33  sub     eax, ecx
0x18003cc35  sub     eax, dword ptr [rsp+68h+arg_18]
0x18003cc3c  movsxd  r8, eax
0x18003cc3f  mov     dword ptr [rsp+68h+arg_10], eax
0x18003cc46  add     r8, r8; Size
0x18003cc49  jz      short loc_18003CC69
0x18003cc4b  test    rbx, rbx
0x18003cc4e  jz      loc_18003CD34
0x18003cc54  test    rdx, rdx
0x18003cc57  jz      loc_18003CD34
0x18003cc5d  mov     rcx, rbx; void *
0x18003cc60  call    cs:__imp_memmove
0x18003cc66  xor     r9d, r9d
0x18003cc69  test    r15, r15
0x18003cc6c  jz      short loc_18003CC8D
0x18003cc6e  test    rsi, rsi
0x18003cc71  jz      loc_18003CD34
0x18003cc77  mov     r8, r15; Size
0x18003cc7a  lea     rdx, aFramework; "\\Framework\\"
0x18003cc81  mov     rcx, rsi; void *
0x18003cc84  call    cs:__imp_memcpy
0x18003cc8a  xor     r9d, r9d
0x18003cc8d  mov     rdx, [rsp+68h+arg_8]
0x18003cc92  mov     eax, dword ptr [rsp+68h+arg_10]
0x18003cc99  add     eax, edx
0x18003cc9b  movsxd  rcx, eax
0x18003cc9e  mov     eax, edx
0x18003cca0  sub     eax, dword ptr [rsp+68h+arg_18]
0x18003cca7  lea     rdx, aFramework64; "\\Framework64\\"
0x18003ccae  add     r13d, eax
0x18003ccb1  mov     [rsi+rcx*2], r9w
0x18003ccb6  mov     rcx, rbx; Str
0x18003ccb9  call    cs:__imp_wcsstr
0x18003ccbf  mov     rdx, [rsp+68h+var_48]
0x18003ccc4  xor     r9d, r9d
0x18003ccc7  mov     rsi, rax
0x18003ccca  test    rax, rax
0x18003cccd  jnz     loc_18003CC1F
0x18003ccd3  mov     r15, [rsp+68h+arg_18]
0x18003ccdb  test    rbx, rbx
0x18003ccde  jz      short loc_18003CCEB
0x18003cce0  mov     rcx, rbx; String
0x18003cce3  call    cs:__imp_wcslen
0x18003cce9  jmp     short loc_18003CCEE
0x18003cceb  mov     eax, r9d
0x18003ccee  inc     eax
0x18003ccf0  movsxd  rcx, eax
0x18003ccf3  lea     rbx, [rbx+rcx*2]
0x18003ccf7  cmp     rbx, [rsp+68h+var_40]
0x18003ccfc  jb      loc_18003CBF0
0x18003cd02  xor     edx, edx
0x18003cd04  test    edi, edi
0x18003cd06  js      short loc_18003CD46
0x18003cd08  mov     rax, [r14]
0x18003cd0b  cmp     edi, [rax-0Ch]
0x18003cd0e  jg      short loc_18003CD46
0x18003cd10  mov     [rax-10h], edi
0x18003cd13  mov     rax, [r14]
0x18003cd16  movsxd  rcx, edi
0x18003cd19  mov     [rax+rcx*2], dx
0x18003cd1d  mov     eax, ebp
0x18003cd1f  mov     rbx, [rsp+68h+arg_0]
0x18003cd24  add     rsp, 30h
0x18003cd28  pop     r15
0x18003cd2a  pop     r14
0x18003cd2c  pop     r13
0x18003cd2e  pop     r12
0x18003cd30  pop     rdi
0x18003cd31  pop     rsi
0x18003cd32  pop     rbp
0x18003cd33  retn
0x18003cd34  call    cs:__imp__errno
0x18003cd3a  mov     dword ptr [rax], 16h
0x18003cd40  call    cs:__imp__invalid_parameter_noinfo
0x18003cd46  mov     ecx, 80070057h; int
0x18003cd4b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
