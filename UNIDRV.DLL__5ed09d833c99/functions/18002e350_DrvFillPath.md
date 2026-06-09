# DrvFillPath

- ea: `0x18002e350`
- end: `0x18002e5bf`
- name: `DrvFillPath`
- size: `623`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, BRUSHOBJ *pbo, POINTL *pptlBrushOrg, MIX mix, FLONG flOptions)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180017148`
- `0x18002e350`
- `0x18002e5c8`
- `0x180077010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002e5ac`
- `KERNEL32!SetLastError` at `0x18002e5ac`
- `GDI32!EngFillPath` at `0x18002e58f`
- `GDI32!EngFillPath` at `0x18002e58f`

## pseudocode

```c
BOOL __stdcall DrvFillPath(
        SURFOBJ *pso,
        PATHOBJ *ppo,
        CLIPOBJ *pco,
        BRUSHOBJ *pbo,
        POINTL *pptlBrushOrg,
        MIX mix,
        FLONG flOptions)
{
  DHPDEV dhpdev; // rbx
  SURFOBJ *v11; // rsi
  int v12; // eax
  __int64 v13; // r10
  __int64 v14; // r10
  int v15; // r12d
  __int64 v16; // rax
  __int64 v17; // rdi
  BOOL result; // eax
  int v19; // r12d

  dhpdev = pso->dhpdev;
  v11 = pso;
  if ( dhpdev
    && dhpdev == *((DHPDEV *)dhpdev + 8)
    && dhpdev == *((DHPDEV *)dhpdev + 553)
    && *((_DWORD *)dhpdev + 18) == 1919968374 )
  {
    if ( *((_QWORD *)dhpdev + 13) )
      v11 = (SURFOBJ *)*((_QWORD *)dhpdev + 13);
    v12 = *((_DWORD *)dhpdev + 29);
    if ( (v12 & 0x40000) != 0 )
    {
      CheckDrawingExtent((__int64)v11, &pco->rclBounds.left, 2);
      v12 = *((_DWORD *)dhpdev + 29);
      if ( (v12 & 0x80000) == 0 )
        return 1;
    }
    v13 = *((_QWORD *)dhpdev + 237);
    if ( v13 )
    {
      if ( *(_QWORD *)(v13 + 192) )
      {
        v19 = *((_DWORD *)dhpdev + 476);
        if ( v19 != 12 )
        {
          *((_DWORD *)dhpdev + 476) = 12;
          *((_QWORD *)dhpdev + 4) = *(_QWORD *)(*(_QWORD *)(v13 + 200) + 32LL);
          *((_QWORD *)dhpdev + 1) = *(_QWORD *)(*(_QWORD *)(v13 + 200) + 40LL);
          *((_QWORD *)dhpdev + 6) = *(_QWORD *)(*(_QWORD *)(v13 + 200) + 56LL);
          result = (*(__int64 (__fastcall **)(SURFOBJ *, PATHOBJ *, CLIPOBJ *, BRUSHOBJ *, POINTL *, MIX, FLONG))(v13 + 192))(
                     v11,
                     ppo,
                     pco,
                     pbo,
                     pptlBrushOrg,
                     mix,
                     flOptions);
          *((_DWORD *)dhpdev + 476) = v19;
          return result;
        }
      }
    }
    v14 = *((_QWORD *)dhpdev + 523);
    if ( v14 )
    {
      if ( *(_QWORD *)(v14 + 296) )
      {
        v15 = *((_DWORD *)dhpdev + 1048);
        if ( v15 != 12 )
        {
          v16 = *((_QWORD *)dhpdev + 522);
          v17 = *((_QWORD *)dhpdev + 1);
          *((_DWORD *)dhpdev + 1048) = 12;
          *((_QWORD *)dhpdev + 1) = v16;
          result = (*(__int64 (__fastcall **)(SURFOBJ *, PATHOBJ *, CLIPOBJ *, BRUSHOBJ *, POINTL *, MIX, FLONG))(v14 + 296))(
                     v11,
                     ppo,
                     pco,
                     pbo,
                     pptlBrushOrg,
                     mix,
                     flOptions);
          *((_DWORD *)dhpdev + 1048) = v15;
          *((_QWORD *)dhpdev + 1) = v17;
          return result;
        }
      }
    }
    if ( (v12 & 0x40000) != 0 )
    {
      return 1;
    }
    else if ( ((_DWORD)dhpdev[28] & 0x20000000) != 0 )
    {
      return 0;
    }
    else
    {
      CheckBitmapSurface(v11, &pco->rclBounds.left, (__int64)pco, (__int64)pbo);
      return EngFillPath(v11, ppo, pco, pbo, pptlBrushOrg, mix, flOptions);
    }
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18002e350  mov     [rsp+arg_10], rbx
0x18002e355  mov     [rsp+arg_18], rbp
0x18002e35a  push    rsi
0x18002e35b  push    r14
0x18002e35d  push    r15
0x18002e35f  sub     rsp, 40h
0x18002e363  mov     rbx, [rcx+10h]
0x18002e367  mov     r14, r9
0x18002e36a  mov     rbp, r8
0x18002e36d  mov     r15, rdx
0x18002e370  mov     rsi, rcx
0x18002e373  test    rbx, rbx
0x18002e376  jz      loc_18002E5A7
0x18002e37c  cmp     rbx, [rbx+40h]
0x18002e380  jnz     loc_18002E5A7
0x18002e386  cmp     rbx, [rbx+1148h]
0x18002e38d  jnz     loc_18002E5A7
0x18002e393  cmp     dword ptr [rbx+48h], 72706476h
0x18002e39a  jnz     loc_18002E5A7
0x18002e3a0  mov     rax, [rbx+68h]
0x18002e3a4  test    rax, rax
0x18002e3a7  mov     [rsp+58h+arg_0], rdi
0x18002e3ac  mov     [rsp+58h+arg_8], r12
0x18002e3b1  cmovnz  rsi, rax
0x18002e3b5  mov     eax, [rbx+74h]
0x18002e3b8  bt      eax, 12h
0x18002e3bc  jb      loc_18002E51C
0x18002e3c2  mov     r10, [rbx+768h]
0x18002e3c9  test    r10, r10
0x18002e3cc  jnz     loc_18002E47F
0x18002e3d2  mov     r10, [rbx+1058h]
0x18002e3d9  test    r10, r10
0x18002e3dc  jz      loc_18002E545
0x18002e3e2  cmp     qword ptr [r10+128h], 0
0x18002e3ea  jz      loc_18002E545
0x18002e3f0  mov     r12d, [rbx+1060h]
0x18002e3f7  cmp     r12d, 0Ch
0x18002e3fb  jz      loc_18002E545
0x18002e401  mov     ecx, [rsp+58h+flOptions]
0x18002e408  mov     r9, r14
0x18002e40b  mov     rax, [rbx+1050h]
0x18002e412  mov     r8, rbp
0x18002e415  mov     rdi, [rbx+8]
0x18002e419  mov     rdx, r15
0x18002e41c  mov     [rsp+58h+var_28], ecx
0x18002e420  mov     ecx, [rsp+58h+mix]
0x18002e427  mov     [rsp+58h+var_30], ecx
0x18002e42b  mov     rcx, [rsp+58h+pptlBrushOrg]
0x18002e433  mov     [rsp+58h+var_38], rcx
0x18002e438  mov     rcx, rsi
0x18002e43b  mov     dword ptr [rbx+1060h], 0Ch
0x18002e445  mov     [rbx+8], rax
0x18002e449  mov     rax, [r10+128h]
0x18002e450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e455  mov     [rbx+1060h], r12d
0x18002e45c  mov     [rbx+8], rdi
0x18002e460  mov     r12, [rsp+58h+arg_8]
0x18002e465  mov     rdi, [rsp+58h+arg_0]
0x18002e46a  mov     rbx, [rsp+58h+arg_10]
0x18002e46f  mov     rbp, [rsp+58h+arg_18]
0x18002e474  add     rsp, 40h
0x18002e478  pop     r15
0x18002e47a  pop     r14
0x18002e47c  pop     rsi
0x18002e47d  retn
0x18002e47f  cmp     qword ptr [r10+0C0h], 0
0x18002e487  jz      loc_18002E3D2
0x18002e48d  mov     r12d, [rbx+770h]
0x18002e494  cmp     r12d, 0Ch
0x18002e498  jz      loc_18002E3D2
0x18002e49e  mov     dword ptr [rbx+770h], 0Ch
0x18002e4a8  mov     r9, r14
0x18002e4ab  mov     rax, [r10+0C8h]
0x18002e4b2  mov     r8, rbp
0x18002e4b5  mov     rcx, [rax+20h]
0x18002e4b9  mov     [rbx+20h], rcx
0x18002e4bd  mov     rax, [r10+0C8h]
0x18002e4c4  mov     rcx, [rax+28h]
0x18002e4c8  mov     [rbx+8], rcx
0x18002e4cc  mov     rcx, rsi
0x18002e4cf  mov     rax, [r10+0C8h]
0x18002e4d6  mov     rdx, [rax+38h]
0x18002e4da  mov     [rbx+30h], rdx
0x18002e4de  mov     edx, [rsp+58h+flOptions]
0x18002e4e5  mov     rax, [r10+0C0h]
0x18002e4ec  mov     [rsp+58h+var_28], edx
0x18002e4f0  mov     edx, [rsp+58h+mix]
0x18002e4f7  mov     [rsp+58h+var_30], edx
0x18002e4fb  mov     rdx, [rsp+58h+pptlBrushOrg]
0x18002e503  mov     [rsp+58h+var_38], rdx
0x18002e508  mov     rdx, r15
0x18002e50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e510  mov     [rbx+770h], r12d
0x18002e517  jmp     loc_18002E460
0x18002e51c  mov     r8d, 2
0x18002e522  lea     rdx, [rbp+4]
0x18002e526  mov     rcx, rsi
0x18002e529  call    CheckDrawingExtent
0x18002e52e  mov     eax, [rbx+74h]
0x18002e531  bt      eax, 13h
0x18002e535  jb      loc_18002E3C2
0x18002e53b  mov     eax, 1
0x18002e540  jmp     loc_18002E460
0x18002e545  bt      eax, 12h
0x18002e549  jb      short loc_18002E53B
0x18002e54b  test    dword ptr [rbx+70h], 20000000h
0x18002e552  jnz     short loc_18002E5A0
0x18002e554  lea     rdx, [rbp+4]
0x18002e558  mov     rcx, rsi
0x18002e55b  call    CheckBitmapSurface
0x18002e560  mov     eax, [rsp+58h+flOptions]
0x18002e567  mov     r9, r14; pbo
0x18002e56a  mov     [rsp+58h+var_28], eax; flOptions
0x18002e56e  mov     r8, rbp; pco
0x18002e571  mov     eax, [rsp+58h+mix]
0x18002e578  mov     rdx, r15; ppo
0x18002e57b  mov     [rsp+58h+var_30], eax; mix
0x18002e57f  mov     rcx, rsi; pso
0x18002e582  mov     rax, [rsp+58h+pptlBrushOrg]
0x18002e58a  mov     [rsp+58h+var_38], rax; pptlBrushOrg
0x18002e58f  call    cs:__imp_EngFillPath
0x18002e596  nop     dword ptr [rax+rax+00h]
0x18002e59b  jmp     loc_18002E460
0x18002e5a0  xor     eax, eax
0x18002e5a2  jmp     loc_18002E460
0x18002e5a7  mov     ecx, 57h ; 'W'; dwErrCode
0x18002e5ac  call    cs:__imp_SetLastError
0x18002e5b3  nop     dword ptr [rax+rax+00h]
0x18002e5b8  xor     eax, eax
0x18002e5ba  jmp     loc_18002E46A
```
