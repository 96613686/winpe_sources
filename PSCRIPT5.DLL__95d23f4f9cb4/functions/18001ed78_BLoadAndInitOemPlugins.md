# BLoadAndInitOemPlugins

- ea: `0x18001ed78`
- end: `0x18001f017`
- name: `BLoadAndInitOemPlugins`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800041a0`

## callees

- `0x18001ed78`
- `0x18002fea0`
- `0x180030bcc`
- `0x180030c2c`
- `0x18005d010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18001ee0a`
- `KERNEL32!LocalAlloc` at `0x18001ee0a`

## pseudocode

```c
__int64 __fastcall BLoadAndInitOemPlugins(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v3; // rax
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
  *(_QWORD *)(a1 + 56) = &off_18005E310;
  v3 = PGetOemPluginInfo(a1, *(void **)(v1 + 24), v1);
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
              if ( LODWORD(qword_180064850[v16]) == *(_DWORD *)i )
                break;
              ++v16;
            }
            while ( LODWORD(qword_180064850[v16]) );
            v17 = SHIDWORD(qword_180064850[v16]);
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
        v13 = (unsigned int (__fastcall *)(__int64, __int64, __int128 *))PGetOemEntrypointAddress(v9, 2);
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
0x18001ed78  mov     [rsp-18h+arg_8], rbx
0x18001ed7d  mov     [rsp-18h+arg_10], rsi
0x18001ed82  push    rbp
0x18001ed83  push    rdi
0x18001ed84  push    r15
0x18001ed86  mov     rbp, rsp
0x18001ed89  sub     rsp, 40h
0x18001ed8d  mov     rdx, [rcx+2B8h]
0x18001ed94  lea     rax, off_18005E310
0x18001ed9b  xorps   xmm0, xmm0
0x18001ed9e  mov     [rbp+arg_0], 0
0x18001eda5  movups  [rbp+var_10], xmm0
0x18001eda9  mov     [rcx+38h], rax
0x18001edad  mov     r8, rdx
0x18001edb0  mov     rdx, [rdx+18h]
0x18001edb4  mov     rdi, rcx
0x18001edb7  call    PGetOemPluginInfo
0x18001edbc  mov     [rdi+0D88h], rax
0x18001edc3  test    rax, rax
0x18001edc6  jz      loc_18001F002
0x18001edcc  mov     rdx, rax
0x18001edcf  mov     rcx, rdi
0x18001edd2  call    BLoadOEMPluginModulesInternal
0x18001edd7  test    eax, eax
0x18001edd9  jz      loc_18001F002
0x18001eddf  mov     rax, [rdi+0D88h]
0x18001ede6  mov     [rax], rdi
0x18001ede9  mov     rax, [rdi+0D88h]
0x18001edf0  cmp     dword ptr [rax+8], 0
0x18001edf4  jnz     short loc_18001EE00
0x18001edf6  mov     eax, 1
0x18001edfb  jmp     loc_18001F004
0x18001ee00  mov     edx, 300h; uBytes
0x18001ee05  mov     ecx, 40h ; '@'; uFlags
0x18001ee0a  call    cs:__imp_LocalAlloc
0x18001ee10  mov     [rdi+0D90h], rax
0x18001ee17  test    rax, rax
0x18001ee1a  jz      loc_18001F002
0x18001ee20  mov     rax, [rdi+0D88h]
0x18001ee27  mov     esi, [rax+8]
0x18001ee2a  lea     rbx, [rax+18h]
0x18001ee2e  test    esi, esi
0x18001ee30  jz      short loc_18001EDF6
0x18001ee32  mov     r15d, 10000h
0x18001ee38  mov     rax, [rbx+20h]
0x18001ee3c  test    rax, rax
0x18001ee3f  jz      loc_18001EFED
0x18001ee45  mov     [rdi+20h], rax
0x18001ee49  xorps   xmm0, xmm0
0x18001ee4c  mov     rax, [rbx+28h]
0x18001ee50  mov     [rdi+8], rax
0x18001ee54  mov     rax, [rbx+38h]
0x18001ee58  mov     [rdi+30h], rax
0x18001ee5c  movups  [rbp+var_10], xmm0
0x18001ee60  mov     rcx, [rbx+48h]
0x18001ee64  test    rcx, rcx
0x18001ee67  jz      short loc_18001EED3
0x18001ee69  mov     rax, [rbx+50h]
0x18001ee6d  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x18001ee74  jnz     short loc_18001EE83
0x18001ee76  mov     rax, [rbx+58h]
0x18001ee7a  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x18001ee81  jz      short loc_18001EEA5
0x18001ee83  mov     rax, [rbx+50h]
0x18001ee87  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18001ee8e  jnz     loc_18001EDF6
0x18001ee94  mov     rax, [rbx+58h]
0x18001ee98  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x18001ee9f  jnz     loc_18001EDF6
0x18001eea5  mov     rax, [rcx]
0x18001eea8  lea     r9, [rbp+var_10]
0x18001eeac  mov     r8d, 10h
0x18001eeb2  mov     edx, r15d
0x18001eeb5  mov     rax, [rax+28h]
0x18001eeb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eebe  cmp     eax, 80004001h
0x18001eec3  jz      loc_18001EFED
0x18001eec9  test    eax, eax
0x18001eecb  js      loc_18001EDF6
0x18001eed1  jmp     short loc_18001EF0E
0x18001eed3  test    byte ptr [rbx+64h], 4
0x18001eed7  jz      short loc_18001EEDF
0x18001eed9  mov     rax, [rbx+78h]
0x18001eedd  jmp     short loc_18001EEEC
0x18001eedf  mov     edx, 2
0x18001eee4  mov     rcx, rbx
0x18001eee7  call    PGetOemEntrypointAddress
0x18001eeec  test    rax, rax
0x18001eeef  jz      loc_18001EFED
0x18001eef5  lea     r8, [rbp+var_10]
0x18001eef9  mov     edx, 10h
0x18001eefe  mov     ecx, r15d
0x18001ef01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef06  test    eax, eax
0x18001ef08  jz      loc_18001EDF6
0x18001ef0e  or      dword ptr [rbx+30h], 1
0x18001ef12  cmp     qword ptr [rbx+48h], 0
0x18001ef17  jnz     short loc_18001EF23
0x18001ef19  cmp     dword ptr [rbp+var_10], r15d
0x18001ef1d  jnz     loc_18001EDF6
0x18001ef23  mov     ecx, dword ptr [rbp+var_10+4]
0x18001ef26  mov     r8, qword ptr [rbp+var_10+8]
0x18001ef2a  test    ecx, ecx
0x18001ef2c  jz      short loc_18001EF90
0x18001ef2e  lea     r10, qword_180064850
0x18001ef35  dec     ecx
0x18001ef37  mov     [rbp+arg_0], ecx
0x18001ef3a  xor     edx, edx
0x18001ef3c  mov     r9d, [r8]
0x18001ef3f  movsxd  rax, edx
0x18001ef42  cmp     [r10+rax*8], r9d
0x18001ef46  jz      short loc_18001EF54
0x18001ef48  inc     edx
0x18001ef4a  movsxd  rax, edx
0x18001ef4d  cmp     dword ptr [r10+rax*8], 0
0x18001ef52  jnz     short loc_18001EF3F
0x18001ef54  movsxd  rax, edx
0x18001ef57  movsxd  rdx, dword ptr [r10+rax*8+4]
0x18001ef5c  test    edx, edx
0x18001ef5e  js      short loc_18001EF88
0x18001ef60  mov     r9, [rdi+0D90h]
0x18001ef67  add     rdx, rdx
0x18001ef6a  cmp     qword ptr [r9+rdx*8], 0
0x18001ef6f  jnz     short loc_18001EF88
0x18001ef71  mov     rax, [r8+8]
0x18001ef75  mov     [r9+rdx*8], rax
0x18001ef79  mov     rax, [rdi+0D90h]
0x18001ef80  mov     [rax+rdx*8+8], rbx
0x18001ef85  mov     ecx, [rbp+arg_0]
0x18001ef88  add     r8, 10h
0x18001ef8c  test    ecx, ecx
0x18001ef8e  jnz     short loc_18001EF35
0x18001ef90  dec     ecx
0x18001ef92  mov     [rbp+arg_0], ecx
0x18001ef95  mov     rcx, [rbx+48h]
0x18001ef99  test    rcx, rcx
0x18001ef9c  jz      short loc_18001EFED
0x18001ef9e  test    [rdi+0D98h], r15d
0x18001efa5  jnz     short loc_18001EFED
0x18001efa7  mov     rax, [rbx+50h]
0x18001efab  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18001efb2  jnz     short loc_18001EFED
0x18001efb4  mov     rax, [rbx+58h]
0x18001efb8  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x18001efbf  jnz     short loc_18001EFED
0x18001efc1  mov     rax, [rcx]
0x18001efc4  lea     rdx, [rbp+arg_0]
0x18001efc8  mov     [rsp+40h+var_20], rdx
0x18001efcd  xor     r9d, r9d
0x18001efd0  xor     r8d, r8d
0x18001efd3  xor     edx, edx
0x18001efd5  mov     rax, [rax+60h]
0x18001efd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efde  test    eax, eax
0x18001efe0  jnz     short loc_18001EFED
0x18001efe2  or      [rdi+0D98h], r15d
0x18001efe9  or      dword ptr [rbx+30h], 8
0x18001efed  add     rbx, 0B0h
0x18001eff4  add     esi, 0FFFFFFFFh
0x18001eff7  jnz     loc_18001EE38
0x18001effd  jmp     loc_18001EDF6
0x18001f002  xor     eax, eax
0x18001f004  mov     rbx, [rsp+40h+arg_8]
0x18001f009  mov     rsi, [rsp+40h+arg_10]
0x18001f00e  add     rsp, 40h
0x18001f012  pop     r15
0x18001f014  pop     rdi
0x18001f015  pop     rbp
0x18001f016  retn
```
