# CSxArrayBuilder<_SR_VOLUME_PROP,&Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *),&SxDefaultInit<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *),&SxDefaultTransfer<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *,_SR_VOLUME_PROP *)>::Append(_SR_VOLUME_PROP *)

- ea: `0x14000d56c`
- end: `0x14000d680`
- name: `?Append@?$CSxArrayBuilder@U_SR_VOLUME_PROP@@$1?Free_SR_VOLUME_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SR_VOLUME_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SR_VOLUME_PROP@@@@YAX00@Z@@QEAAJPEAU_SR_VOLUME_PROP@@@Z`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000d688`

## callees

- `0x14000d56c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000d61c`
- `ole32!CoTaskMemFree` at `0x14000d61c`
- `ole32!CoTaskMemRealloc` at `0x14000d5fa`
- `ole32!CoTaskMemRealloc` at `0x14000d5fa`

## pseudocode

```c
__int64 __fastcall CSxArrayBuilder<_SR_VOLUME_PROP,&void Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *),&void SxDefaultInit<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *),&void SxDefaultTransfer<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *,_SR_VOLUME_PROP *)>::Append(
        __int64 a1,
        _OWORD *a2)
{
  int v4; // edi
  unsigned int v5; // eax
  unsigned int v6; // esi
  unsigned int v7; // ebx
  LPVOID v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx

  if ( a2 )
  {
    v5 = *(_DWORD *)(a1 + 16);
    v6 = v5 + 1;
    if ( v5 + 1 < v5 )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v4 = 0;
      if ( v6 > *(_DWORD *)(a1 + 20) )
      {
        v7 = 64;
        if ( v6 > 0x40 )
        {
          v7 = 256;
          if ( v6 > 0x100 )
          {
            v7 = 1024;
            if ( v6 > 0x400 )
            {
              v7 = 4096;
              if ( v6 > 0x1000 )
              {
                v7 = 0x4000;
                if ( v6 > 0x4000 )
                {
                  v7 = (v5 + 0x10000) & 0xFFFF0000;
                  if ( v7 < v6 )
                    v7 = v5 + 1;
                }
              }
            }
          }
        }
        if ( is_mul_ok(v7, 0x30u) )
        {
          v8 = CoTaskMemRealloc(*(LPVOID *)(a1 + 8), 48LL * v7);
          if ( v8 )
          {
            *(_QWORD *)(a1 + 8) = v8;
            *(_DWORD *)(a1 + 20) = v7;
          }
          else
          {
            v4 = -2147024882;
          }
        }
        else
        {
          v4 = -2147024362;
        }
      }
      CoTaskMemFree(0);
      if ( v4 >= 0 )
      {
        v9 = *(_QWORD *)(a1 + 8);
        v10 = 6LL * *(unsigned int *)(a1 + 16);
        *(_OWORD *)(v9 + 8 * v10) = *a2;
        *(_OWORD *)(v9 + 8 * v10 + 16) = a2[1];
        *(_OWORD *)(v9 + 8 * v10 + 32) = a2[2];
        *a2 = 0;
        a2[1] = 0;
        a2[2] = 0;
        *(_DWORD *)(a1 + 16) = v6;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000d56c  mov     [rsp+arg_0], rbx
0x14000d571  mov     [rsp+arg_10], rbp
0x14000d576  push    rsi
0x14000d577  push    rdi
0x14000d578  push    r14
0x14000d57a  sub     rsp, 20h
0x14000d57e  mov     r14, rdx
0x14000d581  mov     rbp, rcx
0x14000d584  test    rdx, rdx
0x14000d587  jnz     short loc_14000D593
0x14000d589  mov     edi, 80070057h
0x14000d58e  jmp     loc_14000D66B
0x14000d593  mov     eax, [rcx+10h]
0x14000d596  lea     esi, [rax+1]
0x14000d599  cmp     esi, eax
0x14000d59b  jb      loc_14000D666
0x14000d5a1  xor     edi, edi
0x14000d5a3  cmp     esi, [rcx+14h]
0x14000d5a6  jbe     short loc_14000D61A
0x14000d5a8  lea     ebx, [rdi+40h]
0x14000d5ab  cmp     esi, ebx
0x14000d5ad  jbe     short loc_14000D5E4
0x14000d5af  mov     ebx, 100h
0x14000d5b4  cmp     esi, ebx
0x14000d5b6  jbe     short loc_14000D5E4
0x14000d5b8  mov     ebx, 400h
0x14000d5bd  cmp     esi, ebx
0x14000d5bf  jbe     short loc_14000D5E4
0x14000d5c1  mov     ebx, 1000h
0x14000d5c6  cmp     esi, ebx
0x14000d5c8  jbe     short loc_14000D5E4
0x14000d5ca  mov     ebx, 4000h
0x14000d5cf  cmp     esi, ebx
0x14000d5d1  jbe     short loc_14000D5E4
0x14000d5d3  lea     ebx, [rsi+0FFFFh]
0x14000d5d9  and     ebx, 0FFFF0000h
0x14000d5df  cmp     ebx, esi
0x14000d5e1  cmovb   ebx, esi
0x14000d5e4  mov     ecx, ebx
0x14000d5e6  mov     eax, 30h ; '0'
0x14000d5eb  mul     rcx
0x14000d5ee  test    rdx, rdx
0x14000d5f1  jnz     short loc_14000D615
0x14000d5f3  mov     rcx, [rbp+8]; pv
0x14000d5f7  mov     rdx, rax; cb
0x14000d5fa  call    cs:__imp_CoTaskMemRealloc
0x14000d600  test    rax, rax
0x14000d603  jnz     short loc_14000D60C
0x14000d605  mov     edi, 8007000Eh
0x14000d60a  jmp     short loc_14000D61A
0x14000d60c  mov     [rbp+8], rax
0x14000d610  mov     [rbp+14h], ebx
0x14000d613  jmp     short loc_14000D61A
0x14000d615  mov     edi, 80070216h
0x14000d61a  xor     ecx, ecx; pv
0x14000d61c  call    cs:__imp_CoTaskMemFree
0x14000d622  test    edi, edi
0x14000d624  js      short loc_14000D66B
0x14000d626  mov     eax, [rbp+10h]
0x14000d629  movups  xmm0, xmmword ptr [r14]
0x14000d62d  lea     rcx, [rax+rax*2]
0x14000d631  mov     rax, [rbp+8]
0x14000d635  add     rcx, rcx
0x14000d638  movups  xmmword ptr [rax+rcx*8], xmm0
0x14000d63c  movups  xmm1, xmmword ptr [r14+10h]
0x14000d641  movups  xmmword ptr [rax+rcx*8+10h], xmm1
0x14000d646  movups  xmm0, xmmword ptr [r14+20h]
0x14000d64b  xorps   xmm1, xmm1
0x14000d64e  movups  xmmword ptr [rax+rcx*8+20h], xmm0
0x14000d653  movups  xmmword ptr [r14], xmm1
0x14000d657  movups  xmmword ptr [r14+10h], xmm1
0x14000d65c  movups  xmmword ptr [r14+20h], xmm1
0x14000d661  mov     [rbp+10h], esi
0x14000d664  jmp     short loc_14000D66B
0x14000d666  mov     edi, 80070216h
0x14000d66b  mov     rbx, [rsp+38h+arg_0]
0x14000d670  mov     eax, edi
0x14000d672  mov     rbp, [rsp+38h+arg_10]
0x14000d677  add     rsp, 20h
0x14000d67b  pop     r14
0x14000d67d  pop     rdi
0x14000d67e  pop     rsi
0x14000d67f  retn
```
