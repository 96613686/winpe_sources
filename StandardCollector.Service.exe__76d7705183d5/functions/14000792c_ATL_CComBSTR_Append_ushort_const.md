# ATL::CComBSTR::Append(ushort const *)

- ea: `0x14000792c`
- end: `0x140007aae`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBG@Z`
- size: `386`
- prototype: `int(ATL::CComBSTR *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005b70`

## callees

- `0x140002e74`
- `0x14000792c`
- `0x14001473e`
- `0x140014bc0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400079cd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400079cd`
- `OLEAUT32!__imp_SysFreeString` at `0x140007a45`
- `OLEAUT32!__imp_SysFreeString` at `0x140007a45`
- `OLEAUT32!__imp_SysStringLen` at `0x140007985`
- `OLEAUT32!__imp_SysStringLen` at `0x1400079e8`
- `OLEAUT32!__imp_SysStringLen` at `0x140007985`
- `OLEAUT32!__imp_SysStringLen` at `0x1400079e8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140007a67`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140007a91`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140007a67`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140007a91`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140007a9d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140007a9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComBSTR::Append(BSTR *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdi
  UINT v6; // ecx
  __int64 v7; // rdx
  __int64 v8; // r15
  unsigned int v9; // r12d
  BSTR v10; // rsi
  BSTR v11; // r13
  OLECHAR *v12; // rcx
  __int64 v14; // [rsp+68h] [rbp+10h]
  size_t Size; // [rsp+70h] [rbp+18h]

  v4 = 0;
  if ( a2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
  }
  else
  {
    LODWORD(v5) = 0;
  }
  if ( a2 && (!*this || (_DWORD)v5) )
  {
    if ( (int)v5 < 0 )
      return (unsigned int)-2147024809;
    v6 = SysStringLen(*this);
    if ( ~v6 < (unsigned int)v5 )
      return (unsigned int)-2147024362;
    v7 = v6 + (unsigned int)v5;
    v8 = v7;
    v14 = v7;
    v9 = 2 * v7;
    if ( (unsigned __int64)(2 * v7) > 0xFFFFFFFF )
      return (unsigned int)-2147024362;
    Size = 2LL * v6;
    if ( Size > 0xFFFFFFFF )
      return (unsigned int)-2147024362;
    _mm_lfence();
    v10 = SysAllocStringLen(0, v7);
    if ( !v10 )
      return (unsigned int)-2147024882;
    if ( SysStringLen(*this) )
    {
      v11 = *this;
      if ( (_DWORD)Size )
      {
        if ( !v11 || v9 < (unsigned __int64)(unsigned int)Size )
        {
          memset_0(v10, 0, v9);
          if ( v11 )
          {
            if ( v9 >= (unsigned __int64)(unsigned int)Size )
              goto LABEL_32;
            *_errno() = 34;
LABEL_31:
            _invalid_parameter_noinfo();
LABEL_32:
            ATL::AtlThrowImpl(-2147024809);
          }
LABEL_30:
          *_errno() = 22;
          goto LABEL_31;
        }
        memcpy_0(v10, *this, (unsigned int)Size);
      }
      v8 = v14;
    }
    v12 = &v10[Size / 2];
    if ( !(2LL * (int)v5) )
    {
LABEL_24:
      v10[v8] = 0;
      SysFreeString(*this);
      *this = v10;
      return v4;
    }
    if ( v12 )
    {
      memcpy_0(v12, a2, 2LL * (int)v5);
      goto LABEL_24;
    }
    goto LABEL_30;
  }
  return v4;
}

```

## disassembly

```asm
0x14000792c  mov     [rsp+arg_0], rbx
0x140007931  push    rbp
0x140007932  push    rsi
0x140007933  push    rdi
0x140007934  push    r12
0x140007936  push    r13
0x140007938  push    r14
0x14000793a  push    r15
0x14000793c  sub     rsp, 20h
0x140007940  mov     rbp, rdx
0x140007943  mov     r14, rcx
0x140007946  xor     ebx, ebx
0x140007948  test    rdx, rdx
0x14000794b  jnz     short loc_140007951
0x14000794d  mov     edi, ebx
0x14000794f  jmp     short loc_14000795E
0x140007951  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140007955  inc     rdi
0x140007958  cmp     [rdx+rdi*2], bx
0x14000795c  jnz     short loc_140007955
0x14000795e  test    rbp, rbp
0x140007961  jz      loc_140007A7A
0x140007967  cmp     [rcx], rbx
0x14000796a  jz      short loc_140007974
0x14000796c  test    edi, edi
0x14000796e  jz      loc_140007A7A
0x140007974  test    edi, edi
0x140007976  jns     short loc_140007982
0x140007978  mov     ebx, 80070057h
0x14000797d  jmp     loc_140007A7A
0x140007982  mov     rcx, [rcx]; pbstr
0x140007985  call    cs:__imp_SysStringLen
0x14000798b  mov     ecx, eax
0x14000798d  not     eax
0x14000798f  cmp     eax, edi
0x140007991  jb      loc_140007A75
0x140007997  lea     edx, [rcx+rdi]; ui
0x14000799a  mov     r15d, edx
0x14000799d  mov     [rsp+58h+arg_8], r15
0x1400079a2  lea     r12, [rdx+rdx]
0x1400079a6  mov     r8d, 0FFFFFFFFh
0x1400079ac  cmp     r12, r8
0x1400079af  ja      loc_140007A75
0x1400079b5  mov     eax, ecx
0x1400079b7  add     rax, rax
0x1400079ba  mov     [rsp+58h+Size], rax
0x1400079bf  cmp     rax, r8
0x1400079c2  ja      loc_140007A75
0x1400079c8  lfence
0x1400079cb  xor     ecx, ecx; strIn
0x1400079cd  call    cs:__imp_SysAllocStringLen
0x1400079d3  mov     rsi, rax
0x1400079d6  test    rax, rax
0x1400079d9  jnz     short loc_1400079E5
0x1400079db  mov     ebx, 8007000Eh
0x1400079e0  jmp     loc_140007A7A
0x1400079e5  mov     rcx, [r14]; pbstr
0x1400079e8  call    cs:__imp_SysStringLen
0x1400079ee  test    eax, eax
0x1400079f0  jz      short loc_140007A1F
0x1400079f2  mov     r15d, dword ptr [rsp+58h+Size]
0x1400079f7  mov     r13, [r14]
0x1400079fa  mov     r12d, r12d
0x1400079fd  test    r15, r15
0x140007a00  jz      short loc_140007A1A
0x140007a02  test    r13, r13
0x140007a05  jz      short loc_140007A50
0x140007a07  cmp     r12, r15
0x140007a0a  jb      short loc_140007A50
0x140007a0c  mov     r8d, r15d; Size
0x140007a0f  mov     rdx, r13; Src
0x140007a12  mov     rcx, rsi; void *
0x140007a15  call    memcpy_0
0x140007a1a  mov     r15, [rsp+58h+arg_8]
0x140007a1f  movsxd  r8, edi
0x140007a22  add     r8, r8; Size
0x140007a25  mov     rcx, [rsp+58h+Size]
0x140007a2a  lea     rcx, [rsi+rcx]; void *
0x140007a2e  jz      short loc_140007A3D
0x140007a30  test    rcx, rcx
0x140007a33  jz      short loc_140007A91
0x140007a35  mov     rdx, rbp; Src
0x140007a38  call    memcpy_0
0x140007a3d  mov     [rsi+r15*2], bx
0x140007a42  mov     rcx, [r14]; bstrString
0x140007a45  call    cs:__imp_SysFreeString
0x140007a4b  mov     [r14], rsi
0x140007a4e  jmp     short loc_140007A7A
0x140007a50  mov     r8, r12; Size
0x140007a53  xor     edx, edx; Val
0x140007a55  mov     rcx, rsi; void *
0x140007a58  call    memset_0
0x140007a5d  test    r13, r13
0x140007a60  jz      short loc_140007A91
0x140007a62  cmp     r12, r15
0x140007a65  jnb     short loc_140007AA3
0x140007a67  call    cs:__imp__errno
0x140007a6d  mov     dword ptr [rax], 22h ; '"'
0x140007a73  jmp     short loc_140007A9D
0x140007a75  mov     ebx, 80070216h
0x140007a7a  mov     eax, ebx
0x140007a7c  mov     rbx, [rsp+58h+arg_0]
0x140007a81  add     rsp, 20h
0x140007a85  pop     r15
0x140007a87  pop     r14
0x140007a89  pop     r13
0x140007a8b  pop     r12
0x140007a8d  pop     rdi
0x140007a8e  pop     rsi
0x140007a8f  pop     rbp
0x140007a90  retn
0x140007a91  call    cs:__imp__errno
0x140007a97  mov     dword ptr [rax], 16h
0x140007a9d  call    cs:__imp__invalid_parameter_noinfo
0x140007aa3  mov     ecx, 80070057h; int
0x140007aa8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
