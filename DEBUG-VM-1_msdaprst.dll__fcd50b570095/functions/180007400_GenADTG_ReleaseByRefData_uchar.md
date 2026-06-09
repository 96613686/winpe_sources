# GenADTG::ReleaseByRefData(uchar *)

- ea: `0x180007400`
- end: `0x18000748e`
- name: `?ReleaseByRefData@GenADTG@@AEAAXPEAE@Z`
- size: `142`
- prototype: `void __fastcall(GenADTG *__hidden this, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180008c10`
- `0x18002e84b`

## callees

- `0x180007400`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000745b`
- `ole32!CoTaskMemFree` at `0x18000745b`

## pseudocode

```c
void __fastcall GenADTG::ReleaseByRefData(GenADTG *this, unsigned __int8 *a2)
{
  int v2; // ebp
  __int64 v5; // rbx
  __int64 v6; // r14
  unsigned int v7; // ecx
  int v8; // eax
  __int64 v9; // rbx

  if ( a2 )
  {
    v2 = 0;
    if ( *((_WORD *)this + 32) )
    {
      do
      {
        v5 = *((_QWORD *)this + 7);
        v6 = 88LL * v2;
        if ( (*(_WORD *)(v5 + v6 + 84) & 0x4000) != 0 )
        {
          v7 = *(_DWORD *)&a2[*(_QWORD *)(v5 + v6 + 24)];
          if ( v7 <= 0xD )
          {
            v8 = 8209;
            if ( _bittest(&v8, v7) )
            {
              v9 = *(_QWORD *)(v5 + v6 + 8);
              CoTaskMemFree(*(LPVOID *)&a2[v9]);
              *(_QWORD *)&a2[v9] = 0;
            }
          }
          *(_DWORD *)&a2[*(_QWORD *)(*((_QWORD *)this + 7) + v6 + 24)] = 3;
        }
        ++v2;
      }
      while ( v2 < *((unsigned __int16 *)this + 32) );
    }
  }
}

```

## disassembly

```asm
0x180007400  test    rdx, rdx
0x180007403  jz      locret_18000748D
0x180007409  push    rbx
0x18000740a  push    rbp
0x18000740b  push    rsi
0x18000740c  push    rdi
0x18000740d  push    r14
0x18000740f  sub     rsp, 20h
0x180007413  xor     ebp, ebp
0x180007415  xor     eax, eax
0x180007417  mov     rdi, rdx
0x18000741a  mov     rsi, rcx
0x18000741d  cmp     ax, [rcx+40h]
0x180007421  jnb     short loc_180007483
0x180007423  mov     rbx, [rsi+38h]
0x180007427  movsxd  rax, ebp
0x18000742a  imul    r14, rax, 58h ; 'X'
0x18000742e  mov     eax, 4000h
0x180007433  test    [rbx+r14+54h], ax
0x180007439  jz      short loc_180007479
0x18000743b  mov     rax, [rbx+r14+18h]
0x180007440  mov     ecx, [rdi+rax]
0x180007443  cmp     ecx, 0Dh
0x180007446  ja      short loc_180007469
0x180007448  mov     eax, 2011h
0x18000744d  bt      eax, ecx
0x180007450  jnb     short loc_180007469
0x180007452  mov     rbx, [rbx+r14+8]
0x180007457  mov     rcx, [rbx+rdi]; pv
0x18000745b  call    cs:__imp_CoTaskMemFree
0x180007461  mov     qword ptr [rbx+rdi], 0
0x180007469  mov     rax, [rsi+38h]
0x18000746d  mov     rcx, [rax+r14+18h]
0x180007472  mov     dword ptr [rdi+rcx], 3
0x180007479  movzx   eax, word ptr [rsi+40h]
0x18000747d  inc     ebp
0x18000747f  cmp     ebp, eax
0x180007481  jl      short loc_180007423
0x180007483  add     rsp, 20h
0x180007487  pop     r14
0x180007489  pop     rdi
0x18000748a  pop     rsi
0x18000748b  pop     rbp
0x18000748c  pop     rbx
0x18000748d  retn
```
