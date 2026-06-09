# Windows::CopyFromWstringToLpolestr::copy(ushort * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const *)

- ea: `0x180033734`
- end: `0x1800337c4`
- name: `?copy@CopyFromWstringToLpolestr@Windows@@SAJPEAPEAGPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `144`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004b2dc`
- `0x1800928a0`

## callees

- `0x180033734`
- `0x1800337cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033772`

## pseudocode

```c
__int64 __fastcall Windows::CopyFromWstringToLpolestr::copy(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rax
  const unsigned __int16 *v4; // rdi
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rax
  unsigned int v8; // ebx

  *a1 = 0;
  v3 = *((_QWORD *)a2 + 2) + 1LL;
  v4 = a2;
  if ( v3 > 0xFFFFFFFF )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    v5 = (unsigned int)v3;
    v6 = 8LL * (unsigned int)v3;
    if ( v6 <= 0xFFFFFFFF && (v7 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v6), (*a1 = v7) != 0) )
    {
      v8 = 0;
      if ( *((_QWORD *)v4 + 3) > 7u )
        v4 = *(const unsigned __int16 **)v4;
      if ( !ocscpy_s(v7, v5, v4) )
        return (unsigned int)-2147467259;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180033734  mov     [rsp+arg_0], rbx
0x180033739  mov     [rsp+arg_8], rsi
0x18003373e  push    rdi
0x18003373f  sub     rsp, 20h
0x180033743  mov     qword ptr [rcx], 0
0x18003374a  mov     rbx, rcx
0x18003374d  mov     rax, [rdx+10h]
0x180033751  mov     ecx, 0FFFFFFFFh
0x180033756  inc     rax
0x180033759  mov     rdi, rdx
0x18003375c  cmp     rax, rcx
0x18003375f  ja      short loc_1800337AD
0x180033761  mov     esi, eax
0x180033763  lea     rax, ds:0[rsi*8]
0x18003376b  cmp     rax, rcx
0x18003376e  ja      short loc_1800337A6
0x180033770  mov     ecx, eax; cb
0x180033772  call    cs:__imp_CoTaskMemAlloc
0x180033778  mov     [rbx], rax
0x18003377b  test    rax, rax
0x18003377e  jz      short loc_1800337A6
0x180033780  xor     ebx, ebx
0x180033782  cmp     qword ptr [rdi+18h], 7
0x180033787  jbe     short loc_18003378C
0x180033789  mov     rdi, [rdi]
0x18003378c  mov     r8, rdi; unsigned __int16 *
0x18003378f  mov     rdx, rsi; unsigned __int64
0x180033792  mov     rcx, rax; unsigned __int16 *
0x180033795  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18003379a  test    al, al
0x18003379c  mov     ecx, 80004005h
0x1800337a1  cmovz   ebx, ecx
0x1800337a4  jmp     short loc_1800337B2
0x1800337a6  mov     ebx, 8007000Eh
0x1800337ab  jmp     short loc_1800337B2
0x1800337ad  mov     ebx, 80070216h
0x1800337b2  mov     rsi, [rsp+28h+arg_8]
0x1800337b7  mov     eax, ebx
0x1800337b9  mov     rbx, [rsp+28h+arg_0]
0x1800337be  add     rsp, 20h
0x1800337c2  pop     rdi
0x1800337c3  retn
```
