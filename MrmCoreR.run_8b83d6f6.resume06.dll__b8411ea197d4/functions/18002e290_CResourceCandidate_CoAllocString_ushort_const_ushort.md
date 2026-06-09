# CResourceCandidate::_CoAllocString(ushort const *,ushort * *)

- ea: `0x18002e290`
- end: `0x18002e423`
- name: `?_CoAllocString@CResourceCandidate@@SAJPEBGPEAPEAG@Z`
- size: `403`
- prototype: `static int(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `18`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180032780`
- `0x18003a7e0`
- `0x18003aa8c`
- `0x180051ed0`
- `0x180052a30`
- `0x18006f930`
- `0x180074710`
- `0x18008b660`
- `0x18008b6e0`
- `0x18008b800`
- `0x18008bcd0`
- `0x18008bf20`
- `0x18008c290`
- `0x18008cc10`
- `0x18008e1d0`
- `0x18008e540`
- `0x18008e7e0`
- `0x18008ed68`

## callees

- `0x18002c8d0`
- `0x18002e290`
- `0x18008a6a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e2ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e2ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e37d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e37d`

## string_xrefs

- `0x18002e366`: `onecoreuap\base\mrt\runtime\com\dllsrv\resourcecandidate.cpp`
- `0x18002e3a0`: `onecoreuap\base\mrt\runtime\com\dllsrv\resourcecandidate.cpp`
- `0x18002e3c8`: `onecoreuap\base\mrt\runtime\com\dllsrv\resourcecandidate.cpp`
- `0x18002e3f4`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall CResourceCandidate::_CoAllocString(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        __int64 a3,
        const char *a4)
{
  const unsigned __int16 *v5; // rbx
  __int64 v6; // rdi
  unsigned __int64 v7; // rdi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  __int64 v10; // rax
  unsigned __int16 *v11; // rdx
  unsigned __int16 *v12; // rcx
  unsigned int v13; // ebx
  __int64 result; // rax
  int v15; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = a1;
  if ( a1 && a2 )
  {
    v6 = -1;
    *a2 = 0;
    do
      ++v6;
    while ( a1[v6] );
    v7 = v6 + 1;
    if ( v7 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        a4);
    v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7 + 2);
    v9 = v8;
    if ( !v8 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\resourcecandidate.cpp",
        (const char *)0x8007000ELL,
        v15);
      return 2147942414LL;
    }
    *v8 = 0;
    v8[v7] = 0;
    if ( v7 )
    {
      if ( v7 > 0x7FFFFFFF )
      {
        v13 = -2147024809;
        *v8 = 0;
      }
      else
      {
        v10 = 2147483646;
        v11 = v9;
        do
        {
          if ( !v10 )
            break;
          if ( !*v5 )
            break;
          *v11++ = *v5++;
          --v10;
          --v7;
        }
        while ( v7 );
        v12 = v11 - 1;
        v13 = -2147024774;
        if ( v7 )
          v12 = v11;
        result = 0;
        if ( v7 )
          v13 = 0;
        *v12 = 0;
        if ( v7 )
        {
          *a2 = v9;
          return result;
        }
      }
    }
    else
    {
      v13 = -2147024809;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\resourcecandidate.cpp",
      (const char *)v13,
      v15);
    CoTaskMemFree(v9);
    return v13;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\resourcecandidate.cpp",
      (const char *)0x80070057LL,
      v15);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002e290  mov     [rsp+arg_10], rbx
0x18002e295  push    r14; int
0x18002e297  sub     rsp, 20h
0x18002e29b  mov     r14, rdx
0x18002e29e  mov     rbx, rcx
0x18002e2a1  test    rcx, rcx
0x18002e2a4  jz      loc_18002E3C3
0x18002e2aa  test    rdx, rdx
0x18002e2ad  jz      loc_18002E3C3
0x18002e2b3  mov     [rsp+28h+arg_8], rdi
0x18002e2b8  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18002e2bf  mov     qword ptr [rdx], 0
0x18002e2c6  inc     rdi
0x18002e2c9  cmp     word ptr [rcx+rdi*2], 0
0x18002e2ce  jnz     short loc_18002E2C6
0x18002e2d0  inc     rdi
0x18002e2d3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002e2d7  jz      loc_18002E3EF
0x18002e2dd  lea     rcx, ds:2[rdi*2]; cb
0x18002e2e5  mov     [rsp+28h+arg_0], rsi
0x18002e2ea  call    cs:__imp_CoTaskMemAlloc
0x18002e2f0  mov     rsi, rax
0x18002e2f3  test    rax, rax
0x18002e2f6  jz      loc_18002E39B
0x18002e2fc  xor     ecx, ecx
0x18002e2fe  mov     [rax], cx
0x18002e301  mov     [rax+rdi*2], cx
0x18002e305  test    rdi, rdi
0x18002e308  jz      loc_18002E410
0x18002e30e  cmp     rdi, 7FFFFFFFh
0x18002e315  ja      loc_18002E406
0x18002e31b  mov     eax, 7FFFFFFEh
0x18002e320  mov     rdx, rsi
0x18002e323  test    rax, rax
0x18002e326  jz      short loc_18002E344
0x18002e328  movzx   ecx, word ptr [rbx]
0x18002e32b  test    cx, cx
0x18002e32e  jz      short loc_18002E344
0x18002e330  mov     [rdx], cx
0x18002e333  add     rbx, 2
0x18002e337  add     rdx, 2
0x18002e33b  dec     rax
0x18002e33e  sub     rdi, 1
0x18002e342  jnz     short loc_18002E323
0x18002e344  test    rdi, rdi
0x18002e347  lea     rcx, [rdx-2]
0x18002e34b  mov     ebx, 8007007Ah
0x18002e350  cmovnz  rcx, rdx
0x18002e354  xor     eax, eax
0x18002e356  test    rdi, rdi
0x18002e359  cmovnz  ebx, eax
0x18002e35c  mov     [rcx], ax
0x18002e35f  jnz     short loc_18002E3BE
0x18002e361  mov     rcx, [rsp+28h]; this
0x18002e366  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x18002e36d  mov     r9d, ebx; char *
0x18002e370  mov     edx, 13Bh; void *
0x18002e375  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e37a  mov     rcx, rsi; pv
0x18002e37d  call    cs:__imp_CoTaskMemFree
0x18002e383  mov     eax, ebx
0x18002e385  mov     rsi, [rsp+28h+arg_0]
0x18002e38a  mov     rdi, [rsp+28h+arg_8]
0x18002e38f  mov     rbx, [rsp+28h+arg_10]
0x18002e394  add     rsp, 20h
0x18002e398  pop     r14
0x18002e39a  retn
0x18002e39b  mov     rcx, [rsp+28h]; this
0x18002e3a0  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x18002e3a7  mov     r9d, 8007000Eh; char *
0x18002e3ad  mov     edx, 139h; void *
0x18002e3b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e3b7  mov     eax, 8007000Eh
0x18002e3bc  jmp     short loc_18002E385
0x18002e3be  mov     [r14], rsi
0x18002e3c1  jmp     short loc_18002E385
0x18002e3c3  mov     rcx, [rsp+28h]; this
0x18002e3c8  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x18002e3cf  mov     ebx, 80070057h
0x18002e3d4  mov     edx, 132h; void *
0x18002e3d9  mov     r9d, ebx; char *
0x18002e3dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e3e1  mov     eax, ebx
0x18002e3e3  mov     rbx, [rsp+28h+arg_10]
0x18002e3e8  add     rsp, 20h
0x18002e3ec  pop     r14
0x18002e3ee  retn
0x18002e3ef  mov     rcx, [rsp+28h]; this
0x18002e3f4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002e3fb  mov     edx, 0F89h; void *
0x18002e400  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002e406  mov     ebx, 80070057h
0x18002e40b  jmp     loc_1800C1860
0x18002e410  mov     ebx, 80070057h
0x18002e415  test    rdi, rdi
0x18002e418  jz      loc_18002E361
0x18002e41e  jmp     loc_1800C1860
0x1800c1860  mov     [rax], cx
0x1800c1863  jmp     loc_18002E361
```
