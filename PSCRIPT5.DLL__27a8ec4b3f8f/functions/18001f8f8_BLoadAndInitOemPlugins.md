# BLoadAndInitOemPlugins

- ea: `0x18001f8f8`
- end: `0x18001fb9e`
- name: `BLoadAndInitOemPlugins`
- size: `678`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004240`

## callees

- `0x18001f8f8`
- `0x18003148c`
- `0x1800321e4`
- `0x18003224c`
- `0x18005f010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18001f98a`
- `KERNEL32!LocalAlloc` at `0x18001f98a`

## pseudocode

```c
__int64 __fastcall BLoadAndInitOemPlugins(__int64 a1)
{
  __int64 v1; // rdx
  unsigned __int64 v3; // rax
  int v4; // r8d
  HLOCAL v6; // rax
  __int64 v7; // rax
  int v8; // esi
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // eax
  unsigned int (__fastcall *v13)(__int64, __int64, __int128 *); // rax
  int v14; // ecx
  __int64 i; // r8
  int v16; // edx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int128 v21; // [rsp+30h] [rbp-10h] BYREF
  int v22; // [rsp+60h] [rbp+20h] BYREF

  v1 = *(_QWORD *)(a1 + 696);
  v22 = 0;
  v21 = 0;
  *(_QWORD *)(a1 + 56) = &off_180060310;
  v3 = PGetOemPluginInfo(a1, *(const wchar_t **)(v1 + 24), v1);
  *(_QWORD *)(a1 + 3464) = v3;
  if ( v3 && (unsigned int)BLoadOEMPluginModulesInternal(a1, v3, v4) )
  {
    **(_QWORD **)(a1 + 3464) = a1;
    if ( !*(_DWORD *)(*(_QWORD *)(a1 + 3464) + 8LL) )
      return 1;
    v6 = LocalAlloc(0x40u, 0x300u);
    *(_QWORD *)(a1 + 3472) = v6;
    if ( v6 )
    {
      v7 = *(_QWORD *)(a1 + 3464);
      v8 = *(_DWORD *)(v7 + 8);
      v9 = v7 + 24;
      if ( !v8 )
        return 1;
      while ( 1 )
      {
        v10 = *(_QWORD *)(v9 + 32);
        if ( !v10 )
          goto LABEL_37;
        *(_QWORD *)(a1 + 32) = v10;
        *(_QWORD *)(a1 + 8) = *(_QWORD *)(v9 + 40);
        *(_QWORD *)(a1 + 48) = *(_QWORD *)(v9 + 56);
        v21 = 0;
        v11 = *(_QWORD *)(v9 + 72);
        if ( !v11 )
          break;
        if ( (*(_QWORD *)(v9 + 80) != *(_QWORD *)&IID_IPrintOemPS.Data1
           || *(_QWORD *)(v9 + 88) != *(_QWORD *)IID_IPrintOemPS.Data4)
          && (*(_QWORD *)(v9 + 80) != *(_QWORD *)&IID_IPrintOemPS2.Data1
           || *(_QWORD *)(v9 + 88) != *(_QWORD *)IID_IPrintOemPS2.Data4) )
        {
          return 1;
        }
        v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v11 + 40LL))(
                v11,
                0x10000,
                16,
                &v21);
        if ( v12 != -2147467263 )
        {
          if ( v12 < 0 )
            return 1;
LABEL_21:
          *(_DWORD *)(v9 + 48) |= 1u;
          if ( !*(_QWORD *)(v9 + 72) && (_DWORD)v21 != 0x10000 )
            return 1;
          v14 = DWORD1(v21);
          for ( i = *((_QWORD *)&v21 + 1); v14; i += 16 )
          {
            v22 = --v14;
            v16 = 0;
            do
            {
              if ( LODWORD(qword_180066830[v16]) == *(_DWORD *)i )
                break;
              ++v16;
            }
            while ( LODWORD(qword_180066830[v16]) );
            v17 = SHIDWORD(qword_180066830[v16]);
            if ( (int)v17 >= 0 )
            {
              v18 = *(_QWORD *)(a1 + 3472);
              v19 = 2 * v17;
              if ( !*(_QWORD *)(v18 + 8 * v19) )
              {
                *(_QWORD *)(v18 + 8 * v19) = *(_QWORD *)(i + 8);
                *(_QWORD *)(*(_QWORD *)(a1 + 3472) + 8 * v19 + 8) = v9;
                v14 = v22;
              }
            }
          }
          v22 = v14 - 1;
          v20 = *(_QWORD *)(v9 + 72);
          if ( v20
            && (*(_DWORD *)(a1 + 3480) & 0x10000) == 0
            && *(_QWORD *)(v9 + 80) == *(_QWORD *)&IID_IPrintOemPS2.Data1
            && *(_QWORD *)(v9 + 88) == *(_QWORD *)IID_IPrintOemPS2.Data4
            && !(*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int *))(*(_QWORD *)v20 + 96LL))(
                  v20,
                  0,
                  0,
                  0,
                  &v22) )
          {
            *(_DWORD *)(a1 + 3480) |= 0x10000u;
            *(_DWORD *)(v9 + 48) |= 8u;
          }
        }
LABEL_37:
        v9 += 176;
        if ( !--v8 )
          return 1;
      }
      if ( (*(_BYTE *)(v9 + 100) & 4) != 0 )
        v13 = *(unsigned int (__fastcall **)(__int64, __int64, __int128 *))(v9 + 120);
      else
        v13 = (unsigned int (__fastcall *)(__int64, __int64, __int128 *))PGetOemEntrypointAddress(v9, 2u);
      if ( !v13 )
        goto LABEL_37;
      if ( !v13(0x10000, 16, &v21) )
        return 1;
      goto LABEL_21;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001f8f8  mov     [rsp-18h+arg_8], rbx
0x18001f8fd  mov     [rsp-18h+arg_10], rsi
0x18001f902  push    rbp
0x18001f903  push    rdi
0x18001f904  push    r15
0x18001f906  mov     rbp, rsp
0x18001f909  sub     rsp, 40h
0x18001f90d  mov     rdx, [rcx+2B8h]
0x18001f914  lea     rax, off_180060310
0x18001f91b  xorps   xmm0, xmm0
0x18001f91e  mov     [rbp+arg_0], 0
0x18001f925  movups  [rbp+var_10], xmm0
0x18001f929  mov     [rcx+38h], rax
0x18001f92d  mov     r8, rdx
0x18001f930  mov     rdx, [rdx+18h]
0x18001f934  mov     rdi, rcx
0x18001f937  call    PGetOemPluginInfo
0x18001f93c  mov     [rdi+0D88h], rax
0x18001f943  test    rax, rax
0x18001f946  jz      loc_18001FB88
0x18001f94c  mov     rdx, rax
0x18001f94f  mov     rcx, rdi
0x18001f952  call    BLoadOEMPluginModulesInternal
0x18001f957  test    eax, eax
0x18001f959  jz      loc_18001FB88
0x18001f95f  mov     rax, [rdi+0D88h]
0x18001f966  mov     [rax], rdi
0x18001f969  mov     rax, [rdi+0D88h]
0x18001f970  cmp     dword ptr [rax+8], 0
0x18001f974  jnz     short loc_18001F980
0x18001f976  mov     eax, 1
0x18001f97b  jmp     loc_18001FB8A
0x18001f980  mov     edx, 300h; uBytes
0x18001f985  mov     ecx, 40h ; '@'; uFlags
0x18001f98a  call    cs:__imp_LocalAlloc
0x18001f991  nop     dword ptr [rax+rax+00h]
0x18001f996  mov     [rdi+0D90h], rax
0x18001f99d  test    rax, rax
0x18001f9a0  jz      loc_18001FB88
0x18001f9a6  mov     rax, [rdi+0D88h]
0x18001f9ad  mov     esi, [rax+8]
0x18001f9b0  lea     rbx, [rax+18h]
0x18001f9b4  test    esi, esi
0x18001f9b6  jz      short loc_18001F976
0x18001f9b8  mov     r15d, 10000h
0x18001f9be  mov     rax, [rbx+20h]
0x18001f9c2  test    rax, rax
0x18001f9c5  jz      loc_18001FB73
0x18001f9cb  mov     [rdi+20h], rax
0x18001f9cf  xorps   xmm0, xmm0
0x18001f9d2  mov     rax, [rbx+28h]
0x18001f9d6  mov     [rdi+8], rax
0x18001f9da  mov     rax, [rbx+38h]
0x18001f9de  mov     [rdi+30h], rax
0x18001f9e2  movups  [rbp+var_10], xmm0
0x18001f9e6  mov     rcx, [rbx+48h]
0x18001f9ea  test    rcx, rcx
0x18001f9ed  jz      short loc_18001FA59
0x18001f9ef  mov     rax, [rbx+50h]
0x18001f9f3  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x18001f9fa  jnz     short loc_18001FA09
0x18001f9fc  mov     rax, [rbx+58h]
0x18001fa00  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x18001fa07  jz      short loc_18001FA2B
0x18001fa09  mov     rax, [rbx+50h]
0x18001fa0d  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18001fa14  jnz     loc_18001F976
0x18001fa1a  mov     rax, [rbx+58h]
0x18001fa1e  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x18001fa25  jnz     loc_18001F976
0x18001fa2b  mov     rax, [rcx]
0x18001fa2e  lea     r9, [rbp+var_10]
0x18001fa32  mov     r8d, 10h
0x18001fa38  mov     edx, r15d
0x18001fa3b  mov     rax, [rax+28h]
0x18001fa3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa44  cmp     eax, 80004001h
0x18001fa49  jz      loc_18001FB73
0x18001fa4f  test    eax, eax
0x18001fa51  js      loc_18001F976
0x18001fa57  jmp     short loc_18001FA94
0x18001fa59  test    byte ptr [rbx+64h], 4
0x18001fa5d  jz      short loc_18001FA65
0x18001fa5f  mov     rax, [rbx+78h]
0x18001fa63  jmp     short loc_18001FA72
0x18001fa65  mov     edx, 2
0x18001fa6a  mov     rcx, rbx
0x18001fa6d  call    PGetOemEntrypointAddress
0x18001fa72  test    rax, rax
0x18001fa75  jz      loc_18001FB73
0x18001fa7b  lea     r8, [rbp+var_10]
0x18001fa7f  mov     edx, 10h
0x18001fa84  mov     ecx, r15d
0x18001fa87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa8c  test    eax, eax
0x18001fa8e  jz      loc_18001F976
0x18001fa94  or      dword ptr [rbx+30h], 1
0x18001fa98  cmp     qword ptr [rbx+48h], 0
0x18001fa9d  jnz     short loc_18001FAA9
0x18001fa9f  cmp     dword ptr [rbp+var_10], r15d
0x18001faa3  jnz     loc_18001F976
0x18001faa9  mov     ecx, dword ptr [rbp+var_10+4]
0x18001faac  mov     r8, qword ptr [rbp+var_10+8]
0x18001fab0  test    ecx, ecx
0x18001fab2  jz      short loc_18001FB16
0x18001fab4  lea     r10, qword_180066830
0x18001fabb  dec     ecx
0x18001fabd  mov     [rbp+arg_0], ecx
0x18001fac0  xor     edx, edx
0x18001fac2  mov     r9d, [r8]
0x18001fac5  movsxd  rax, edx
0x18001fac8  cmp     [r10+rax*8], r9d
0x18001facc  jz      short loc_18001FADA
0x18001face  inc     edx
0x18001fad0  movsxd  rax, edx
0x18001fad3  cmp     dword ptr [r10+rax*8], 0
0x18001fad8  jnz     short loc_18001FAC5
0x18001fada  movsxd  rax, edx
0x18001fadd  movsxd  rdx, dword ptr [r10+rax*8+4]
0x18001fae2  test    edx, edx
0x18001fae4  js      short loc_18001FB0E
0x18001fae6  mov     r9, [rdi+0D90h]
0x18001faed  add     rdx, rdx
0x18001faf0  cmp     qword ptr [r9+rdx*8], 0
0x18001faf5  jnz     short loc_18001FB0E
0x18001faf7  mov     rax, [r8+8]
0x18001fafb  mov     [r9+rdx*8], rax
0x18001faff  mov     rax, [rdi+0D90h]
0x18001fb06  mov     [rax+rdx*8+8], rbx
0x18001fb0b  mov     ecx, [rbp+arg_0]
0x18001fb0e  add     r8, 10h
0x18001fb12  test    ecx, ecx
0x18001fb14  jnz     short loc_18001FABB
0x18001fb16  dec     ecx
0x18001fb18  mov     [rbp+arg_0], ecx
0x18001fb1b  mov     rcx, [rbx+48h]
0x18001fb1f  test    rcx, rcx
0x18001fb22  jz      short loc_18001FB73
0x18001fb24  test    [rdi+0D98h], r15d
0x18001fb2b  jnz     short loc_18001FB73
0x18001fb2d  mov     rax, [rbx+50h]
0x18001fb31  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18001fb38  jnz     short loc_18001FB73
0x18001fb3a  mov     rax, [rbx+58h]
0x18001fb3e  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x18001fb45  jnz     short loc_18001FB73
0x18001fb47  mov     rax, [rcx]
0x18001fb4a  lea     rdx, [rbp+arg_0]
0x18001fb4e  mov     [rsp+40h+var_20], rdx
0x18001fb53  xor     r9d, r9d
0x18001fb56  xor     r8d, r8d
0x18001fb59  xor     edx, edx
0x18001fb5b  mov     rax, [rax+60h]
0x18001fb5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb64  test    eax, eax
0x18001fb66  jnz     short loc_18001FB73
0x18001fb68  or      [rdi+0D98h], r15d
0x18001fb6f  or      dword ptr [rbx+30h], 8
0x18001fb73  add     rbx, 0B0h
0x18001fb7a  add     esi, 0FFFFFFFFh
0x18001fb7d  jnz     loc_18001F9BE
0x18001fb83  jmp     loc_18001F976
0x18001fb88  xor     eax, eax
0x18001fb8a  mov     rbx, [rsp+40h+arg_8]
0x18001fb8f  mov     rsi, [rsp+40h+arg_10]
0x18001fb94  add     rsp, 40h
0x18001fb98  pop     r15
0x18001fb9a  pop     rdi
0x18001fb9b  pop     rbp
0x18001fb9c  retn
```
