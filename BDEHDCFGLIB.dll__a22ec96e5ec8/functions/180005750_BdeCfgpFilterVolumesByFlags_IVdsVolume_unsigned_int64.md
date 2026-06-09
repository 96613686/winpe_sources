# BdeCfgpFilterVolumesByFlags(IVdsVolume *,unsigned __int64)

- ea: `0x180005750`
- end: `0x1800057e3`
- name: `?BdeCfgpFilterVolumesByFlags@@YAHPEAUIVdsVolume@@_K@Z`
- size: `147`
- prototype: `__int64 __fastcall(struct IVdsVolume *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180005750`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800057a8`
- `ole32!CoTaskMemFree` at `0x1800057a8`

## pseudocode

```c
__int64 __fastcall BdeCfgpFilterVolumesByFlags(struct IVdsVolume *a1, int a2)
{
  unsigned int v3; // ebx
  int v4; // esi
  _OWORD v6[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v7; // [rsp+40h] [rbp-28h]
  LPVOID pv; // [rsp+50h] [rbp-18h]

  memset(v6, 0, sizeof(v6));
  v3 = 0;
  v7 = 0;
  pv = 0;
  v4 = ((__int64 (__fastcall *)(struct IVdsVolume *, _OWORD *))a1->lpVtbl->GetProperties)(a1, v6);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 >= 0 && (DWORD2(v7) & a2) == a2 )
    return 1;
  return v3;
}

```

## disassembly

```asm
0x180005750  mov     r11, rsp
0x180005753  mov     [r11+10h], rbx
0x180005757  mov     [r11+18h], rsi
0x18000575b  push    rdi
0x18000575c  sub     rsp, 60h
0x180005760  mov     rax, cs:__security_cookie
0x180005767  xor     rax, rsp
0x18000576a  mov     [rsp+68h+var_10], rax
0x18000576f  xorps   xmm0, xmm0
0x180005772  xor     eax, eax
0x180005774  movups  [rsp+68h+var_48], xmm0
0x180005779  mov     rdi, rdx
0x18000577c  lea     rdx, [r11-48h]
0x180005780  movups  [rsp+68h+var_38], xmm0
0x180005785  xor     ebx, ebx
0x180005787  movups  [rsp+68h+var_28], xmm0
0x18000578c  mov     [r11-18h], rax
0x180005790  mov     rax, [rcx]
0x180005793  mov     rax, [rax+18h]
0x180005797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000579c  mov     rcx, [rsp+68h+pv]; pv
0x1800057a1  mov     esi, eax
0x1800057a3  test    rcx, rcx
0x1800057a6  jz      short loc_1800057AE
0x1800057a8  call    cs:__imp_CoTaskMemFree
0x1800057ae  test    esi, esi
0x1800057b0  js      short loc_1800057C2
0x1800057b2  mov     ecx, edi
0x1800057b4  mov     eax, 1
0x1800057b9  and     ecx, dword ptr [rsp+68h+var_28+8]
0x1800057bd  cmp     ecx, edi
0x1800057bf  cmovz   ebx, eax
0x1800057c2  mov     eax, ebx
0x1800057c4  mov     rcx, [rsp+68h+var_10]
0x1800057c9  xor     rcx, rsp; StackCookie
0x1800057cc  call    __security_check_cookie
0x1800057d1  lea     r11, [rsp+68h+var_8]
0x1800057d6  mov     rbx, [r11+18h]
0x1800057da  mov     rsi, [r11+20h]
0x1800057de  mov     rsp, r11
0x1800057e1  pop     rdi
0x1800057e2  retn
```
