# CPropertyCache::LoadSchema(void)

- ea: `0x180010968`
- end: `0x1800109bd`
- name: `?LoadSchema@CPropertyCache@@IEAAJXZ`
- size: `85`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180006b00`
- `0x180010104`
- `0x1800102e0`
- `0x1800103bc`
- `0x180010714`
- `0x1800107f0`
- `0x180010cd8`
- `0x180010ecc`
- `0x1800111b4`

## callees

- `0x180010968`
- `0x18001364c`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CPropertyCache::LoadSchema(CPropertyCache *this)
{
  unsigned int inited; // ebx
  struct IMSAdminBaseW *v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  if ( *((_QWORD *)this + 9) )
  {
    return 1;
  }
  else
  {
    inited = InitServerInfo(
               (CPropertyCache *)((char *)this + 48),
               *((const unsigned __int16 **)this + 10),
               &v3,
               (struct IIsSchema **)this + 9);
    if ( v3 )
      ((void (__fastcall *)(struct IMSAdminBaseW *))v3->lpVtbl->Release)(v3);
  }
  return inited;
}

```

## disassembly

```asm
0x180010968  push    rbx
0x18001096a  sub     rsp, 20h
0x18001096e  lea     r9, [rcx+48h]; struct IIsSchema **
0x180010972  mov     [rsp+28h+arg_0], 0
0x18001097b  cmp     qword ptr [r9], 0
0x18001097f  mov     rdx, rcx
0x180010982  jnz     short loc_1800109B0
0x180010984  mov     rdx, [rdx+50h]; unsigned __int16 *
0x180010988  lea     r8, [rsp+28h+arg_0]; struct IMSAdminBaseW **
0x18001098d  add     rcx, 30h ; '0'; struct CCredentials *
0x180010991  call    ?InitServerInfo@@YAJAEAVCCredentials@@PEBGPEAPEAUIMSAdminBaseW@@PEAPEAVIIsSchema@@@Z; InitServerInfo(CCredentials &,ushort const *,IMSAdminBaseW * *,IIsSchema * *)
0x180010996  mov     rcx, [rsp+28h+arg_0]
0x18001099b  mov     ebx, eax
0x18001099d  test    rcx, rcx
0x1800109a0  jz      short loc_1800109B5
0x1800109a2  mov     rdx, [rcx]
0x1800109a5  mov     rax, [rdx+10h]
0x1800109a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ae  jmp     short loc_1800109B5
0x1800109b0  mov     ebx, 1
0x1800109b5  mov     eax, ebx
0x1800109b7  add     rsp, 20h
0x1800109bb  pop     rbx
0x1800109bc  retn
```
