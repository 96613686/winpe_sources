# ATL::CComBSTR::Append(ushort const *,int)

- ea: `0x14000f710`
- end: `0x14000f7bc`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBGH@Z`
- size: `172`
- prototype: `__int64 __fastcall(const void **this, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000f3f0`
- `0x14000f4ac`
- `0x14000f528`
- `0x14000f590`

## callees

- `0x14000f710`

## import_xrefs

- `msvcrt!memcpy` at `0x14000f774`
- `msvcrt!memcpy` at `0x14000f78a`
- `msvcrt!memcpy` at `0x14000f774`
- `msvcrt!memcpy` at `0x14000f78a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14000f755`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14000f755`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f79d`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f79d`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f742`
- `OLEAUT32!__imp_SysStringLen` at `0x14000f742`

## pseudocode

```c
__int64 __fastcall ATL::CComBSTR::Append(const void **this, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  OLECHAR *v7; // rcx
  signed int v8; // ebx
  signed int v9; // ebp
  BSTR v10; // rax
  BSTR v11; // r14

  v3 = a3;
  if ( !a2 )
    return a3 != 0 ? 0x80070057 : 0;
  v7 = (OLECHAR *)*this;
  if ( v7 )
    v8 = SysStringLen(v7);
  else
    v8 = 0;
  v9 = v8 + v3;
  if ( v8 + (int)v3 < v8 )
    return 2147942414LL;
  v10 = SysAllocStringLen(0, v9);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  if ( *this )
    memcpy(v10, *this, 2LL * v8);
  memcpy(&v11[v8], a2, 2 * v3);
  v11[v9] = 0;
  SysFreeString((BSTR)*this);
  result = 0;
  *this = v11;
  return result;
}

```

## disassembly

```asm
0x14000f710  push    rbx
0x14000f712  push    rbp
0x14000f713  push    rsi
0x14000f714  push    rdi
0x14000f715  push    r14
0x14000f717  push    r15
0x14000f719  sub     rsp, 28h
0x14000f71d  movsxd  rdi, r8d
0x14000f720  mov     r15, rdx
0x14000f723  mov     rsi, rcx
0x14000f726  test    rdx, rdx
0x14000f729  jnz     short loc_14000F736
0x14000f72b  neg     edi
0x14000f72d  sbb     eax, eax
0x14000f72f  and     eax, 80070057h
0x14000f734  jmp     short loc_14000F7AF
0x14000f736  mov     rcx, [rcx]; pbstr
0x14000f739  test    rcx, rcx
0x14000f73c  jnz     short loc_14000F742
0x14000f73e  xor     ebx, ebx
0x14000f740  jmp     short loc_14000F74A
0x14000f742  call    cs:__imp_SysStringLen
0x14000f748  mov     ebx, eax
0x14000f74a  lea     ebp, [rbx+rdi]
0x14000f74d  cmp     ebp, ebx
0x14000f74f  jl      short loc_14000F7AA
0x14000f751  mov     edx, ebp; ui
0x14000f753  xor     ecx, ecx; strIn
0x14000f755  call    cs:__imp_SysAllocStringLen
0x14000f75b  mov     r14, rax
0x14000f75e  test    rax, rax
0x14000f761  jz      short loc_14000F7AA
0x14000f763  mov     rdx, [rsi]; Src
0x14000f766  test    rdx, rdx
0x14000f769  jz      short loc_14000F77A
0x14000f76b  movsxd  r8, ebx
0x14000f76e  mov     rcx, rax; void *
0x14000f771  add     r8, r8; Size
0x14000f774  call    cs:__imp_memcpy
0x14000f77a  movsxd  rax, ebx
0x14000f77d  mov     r8, rdi
0x14000f780  add     r8, r8; Size
0x14000f783  mov     rdx, r15; Src
0x14000f786  lea     rcx, [r14+rax*2]; void *
0x14000f78a  call    cs:__imp_memcpy
0x14000f790  movsxd  rcx, ebp
0x14000f793  xor     eax, eax
0x14000f795  mov     [r14+rcx*2], ax
0x14000f79a  mov     rcx, [rsi]; bstrString
0x14000f79d  call    cs:__imp_SysFreeString
0x14000f7a3  xor     eax, eax
0x14000f7a5  mov     [rsi], r14
0x14000f7a8  jmp     short loc_14000F7AF
0x14000f7aa  mov     eax, 8007000Eh
0x14000f7af  add     rsp, 28h
0x14000f7b3  pop     r15
0x14000f7b5  pop     r14
0x14000f7b7  pop     rdi
0x14000f7b8  pop     rsi
0x14000f7b9  pop     rbp
0x14000f7ba  pop     rbx
0x14000f7bb  retn
```
