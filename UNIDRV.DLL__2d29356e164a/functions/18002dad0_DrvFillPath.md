# DrvFillPath

- ea: `0x18002dad0`
- end: `0x18002dd32`
- name: `DrvFillPath`
- size: `610`
- prototype: `BOOL __stdcall(SURFOBJ *pso, PATHOBJ *ppo, CLIPOBJ *pco, BRUSHOBJ *pbo, POINTL *pptlBrushOrg, MIX mix, FLONG flOptions)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180016e6c`
- `0x18002dad0`
- `0x18002dd38`
- `0x180075010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002dd25`
- `KERNEL32!SetLastError` at `0x18002dd25`
- `GDI32!EngFillPath` at `0x18002dd0e`
- `GDI32!EngFillPath` at `0x18002dd0e`

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
      CheckBitmapSurface(v11, &pco->rclBounds.left);
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
0x18002dad0  mov     [rsp+arg_10], rbx
0x18002dad5  mov     [rsp+arg_18], rbp
0x18002dada  push    rsi
0x18002dadb  push    r14
0x18002dadd  push    r15
0x18002dadf  sub     rsp, 40h
0x18002dae3  mov     rbx, [rcx+10h]
0x18002dae7  mov     r14, r9
0x18002daea  mov     rbp, r8
0x18002daed  mov     r15, rdx
0x18002daf0  mov     rsi, rcx
0x18002daf3  test    rbx, rbx
0x18002daf6  jz      loc_18002DD20
0x18002dafc  cmp     rbx, [rbx+40h]
0x18002db00  jnz     loc_18002DD20
0x18002db06  cmp     rbx, [rbx+1148h]
0x18002db0d  jnz     loc_18002DD20
0x18002db13  cmp     dword ptr [rbx+48h], 72706476h
0x18002db1a  jnz     loc_18002DD20
0x18002db20  mov     rax, [rbx+68h]
0x18002db24  test    rax, rax
0x18002db27  mov     [rsp+58h+arg_0], rdi
0x18002db2c  mov     [rsp+58h+arg_8], r12
0x18002db31  cmovnz  rsi, rax
0x18002db35  mov     eax, [rbx+74h]
0x18002db38  bt      eax, 12h
0x18002db3c  jb      loc_18002DC9B
0x18002db42  mov     r10, [rbx+768h]
0x18002db49  test    r10, r10
0x18002db4c  jnz     loc_18002DBFE
0x18002db52  mov     r10, [rbx+1058h]
0x18002db59  test    r10, r10
0x18002db5c  jz      loc_18002DCC4
0x18002db62  cmp     qword ptr [r10+128h], 0
0x18002db6a  jz      loc_18002DCC4
0x18002db70  mov     r12d, [rbx+1060h]
0x18002db77  cmp     r12d, 0Ch
0x18002db7b  jz      loc_18002DCC4
0x18002db81  mov     ecx, [rsp+58h+flOptions]
0x18002db88  mov     r9, r14
0x18002db8b  mov     rax, [rbx+1050h]
0x18002db92  mov     r8, rbp
0x18002db95  mov     rdi, [rbx+8]
0x18002db99  mov     rdx, r15
0x18002db9c  mov     [rsp+58h+var_28], ecx
0x18002dba0  mov     ecx, [rsp+58h+mix]
0x18002dba7  mov     [rsp+58h+var_30], ecx
0x18002dbab  mov     rcx, [rsp+58h+pptlBrushOrg]
0x18002dbb3  mov     [rsp+58h+var_38], rcx
0x18002dbb8  mov     rcx, rsi
0x18002dbbb  mov     dword ptr [rbx+1060h], 0Ch
0x18002dbc5  mov     [rbx+8], rax
0x18002dbc9  mov     rax, [r10+128h]
0x18002dbd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbd5  mov     [rbx+1060h], r12d
0x18002dbdc  mov     [rbx+8], rdi
0x18002dbe0  mov     r12, [rsp+58h+arg_8]
0x18002dbe5  mov     rdi, [rsp+58h+arg_0]
0x18002dbea  mov     rbx, [rsp+58h+arg_10]
0x18002dbef  mov     rbp, [rsp+58h+arg_18]
0x18002dbf4  add     rsp, 40h
0x18002dbf8  pop     r15
0x18002dbfa  pop     r14
0x18002dbfc  pop     rsi
0x18002dbfd  retn
0x18002dbfe  cmp     qword ptr [r10+0C0h], 0
0x18002dc06  jz      loc_18002DB52
0x18002dc0c  mov     r12d, [rbx+770h]
0x18002dc13  cmp     r12d, 0Ch
0x18002dc17  jz      loc_18002DB52
0x18002dc1d  mov     dword ptr [rbx+770h], 0Ch
0x18002dc27  mov     r9, r14
0x18002dc2a  mov     rax, [r10+0C8h]
0x18002dc31  mov     r8, rbp
0x18002dc34  mov     rcx, [rax+20h]
0x18002dc38  mov     [rbx+20h], rcx
0x18002dc3c  mov     rax, [r10+0C8h]
0x18002dc43  mov     rcx, [rax+28h]
0x18002dc47  mov     [rbx+8], rcx
0x18002dc4b  mov     rcx, rsi
0x18002dc4e  mov     rax, [r10+0C8h]
0x18002dc55  mov     rdx, [rax+38h]
0x18002dc59  mov     [rbx+30h], rdx
0x18002dc5d  mov     edx, [rsp+58h+flOptions]
0x18002dc64  mov     rax, [r10+0C0h]
0x18002dc6b  mov     [rsp+58h+var_28], edx
0x18002dc6f  mov     edx, [rsp+58h+mix]
0x18002dc76  mov     [rsp+58h+var_30], edx
0x18002dc7a  mov     rdx, [rsp+58h+pptlBrushOrg]
0x18002dc82  mov     [rsp+58h+var_38], rdx
0x18002dc87  mov     rdx, r15
0x18002dc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc8f  mov     [rbx+770h], r12d
0x18002dc96  jmp     loc_18002DBE0
0x18002dc9b  mov     r8d, 2
0x18002dca1  lea     rdx, [rbp+4]
0x18002dca5  mov     rcx, rsi
0x18002dca8  call    CheckDrawingExtent
0x18002dcad  mov     eax, [rbx+74h]
0x18002dcb0  bt      eax, 13h
0x18002dcb4  jb      loc_18002DB42
0x18002dcba  mov     eax, 1
0x18002dcbf  jmp     loc_18002DBE0
0x18002dcc4  bt      eax, 12h
0x18002dcc8  jb      short loc_18002DCBA
0x18002dcca  test    dword ptr [rbx+70h], 20000000h
0x18002dcd1  jnz     short loc_18002DD19
0x18002dcd3  lea     rdx, [rbp+4]
0x18002dcd7  mov     rcx, rsi
0x18002dcda  call    CheckBitmapSurface
0x18002dcdf  mov     eax, [rsp+58h+flOptions]
0x18002dce6  mov     r9, r14; pbo
0x18002dce9  mov     [rsp+58h+var_28], eax; flOptions
0x18002dced  mov     r8, rbp; pco
0x18002dcf0  mov     eax, [rsp+58h+mix]
0x18002dcf7  mov     rdx, r15; ppo
0x18002dcfa  mov     [rsp+58h+var_30], eax; mix
0x18002dcfe  mov     rcx, rsi; pso
0x18002dd01  mov     rax, [rsp+58h+pptlBrushOrg]
0x18002dd09  mov     [rsp+58h+var_38], rax; pptlBrushOrg
0x18002dd0e  call    cs:__imp_EngFillPath
0x18002dd14  jmp     loc_18002DBE0
0x18002dd19  xor     eax, eax
0x18002dd1b  jmp     loc_18002DBE0
0x18002dd20  mov     ecx, 57h ; 'W'; dwErrCode
0x18002dd25  call    cs:__imp_SetLastError
0x18002dd2b  xor     eax, eax
0x18002dd2d  jmp     loc_18002DBEA
```
