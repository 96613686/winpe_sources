# CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)

- ea: `0x180006610`
- end: `0x18000667a`
- name: `?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ`
- size: `106`
- prototype: `_BYTE *__fastcall(__int64)`
- caller_count: `25`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003ca4`
- `0x1800052f8`
- `0x180006324`
- `0x1800065f4`
- `0x180006680`
- `0x1800091d0`
- `0x18000d3a8`
- `0x18000df38`
- `0x18000e148`
- `0x1800135d0`
- `0x180014900`
- `0x18001a640`
- `0x18001e4f0`
- `0x180022290`
- `0x180026a80`
- `0x180029690`
- `0x18002a9e0`
- `0x18002d090`
- `0x180034058`
- `0x180035064`
- `0x18003c4e0`
- `0x18003c62c`
- `0x180046040`
- `0x180046920`
- `0x180046d90`

## callees

- `0x180006610`
- `0x180012210`
- `0x18004d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_BYTE *__fastcall CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(__int64 a1)
{
  _BYTE *result; // rax
  __int64 v3; // rcx
  void *v4; // rcx

  result = *(_BYTE **)(a1 + 8);
  if ( result )
  {
    v3 = *(unsigned int *)(a1 + 16);
    if ( (_DWORD)v3 )
    {
      do
      {
        *result++ = 0;
        --v3;
      }
      while ( v3 );
    }
    v4 = *(void **)(a1 + 8);
    if ( *(_QWORD *)a1 )
      (*(void (__fastcall **)(void *))a1)(v4);
    else
      VaultFreeInternal(v4);
    result = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 0;
  }
  else
  {
    *(_DWORD *)(a1 + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006610  push    rbx
0x180006612  sub     rsp, 20h
0x180006616  mov     rax, [rcx+8]
0x18000661a  mov     rbx, rcx
0x18000661d  test    rax, rax
0x180006620  jz      short loc_180006671
0x180006622  mov     ecx, [rcx+10h]
0x180006625  test    ecx, ecx
0x180006627  jz      short loc_18000663D
0x180006629  nop     dword ptr [rax+00000000h]
0x180006630  mov     byte ptr [rax], 0
0x180006633  lea     rax, [rax+1]
0x180006637  sub     rcx, 1
0x18000663b  jnz     short loc_180006630
0x18000663d  mov     rax, [rbx]
0x180006640  mov     rcx, [rbx+8]; hMem
0x180006644  test    rax, rax
0x180006647  jz      short loc_18000665D
0x180006649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000664e  xor     eax, eax
0x180006650  mov     [rbx+8], rax
0x180006654  mov     [rbx+10h], eax
0x180006657  add     rsp, 20h
0x18000665b  pop     rbx
0x18000665c  retn
0x18000665d  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180006662  xor     eax, eax
0x180006664  mov     [rbx+8], rax
0x180006668  mov     [rbx+10h], eax
0x18000666b  add     rsp, 20h
0x18000666f  pop     rbx
0x180006670  retn
0x180006671  mov     [rcx+10h], eax
0x180006674  add     rsp, 20h
0x180006678  pop     rbx
0x180006679  retn
```
