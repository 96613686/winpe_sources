# GetConsistentPackageFlags(void *,ulong *,uint *,uint *,_CLASSPATHTYPE *,ulong *,ushort *)

- ea: `0x180021fa0`
- end: `0x1800220ef`
- name: `?GetConsistentPackageFlags@@YAJPEAXPEAKPEAI2PEAW4_CLASSPATHTYPE@@1PEAG@Z`
- size: `335`
- prototype: `__int64 __fastcall(void *, unsigned int *, unsigned int *, unsigned int *, enum _CLASSPATHTYPE *, unsigned int *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f0b0`
- `0x18001fa10`
- `0x1800208c4`
- `0x180022e00`

## callees

- `0x180021fa0`
- `0x180024218`

## import_xrefs

- `adsldpc!ADSIGetObjectAttributes` at `0x180021fec`
- `adsldpc!ADSIGetObjectAttributes` at `0x180021fec`
- `adsldpc!FreeADsMem` at `0x1800220da`
- `adsldpc!FreeADsMem` at `0x1800220da`

## pseudocode

```c
__int64 __fastcall GetConsistentPackageFlags(
        void *a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        enum _CLASSPATHTYPE *a5,
        unsigned int *a6,
        unsigned __int16 *a7)
{
  void *v7; // r10
  int v11; // ebx
  unsigned int PropertyFromAttr; // eax
  __int64 v13; // rax
  int v14; // ecx
  int v15; // edx
  unsigned int v16; // edx
  unsigned __int16 *v17; // rax
  LPVOID pMem; // [rsp+30h] [rbp-18h] BYREF
  const unsigned __int16 *v20; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v21; // [rsp+80h] [rbp+38h] BYREF

  v7 = 0;
  v21 = 0;
  pMem = 0;
  v20 = L"packageFlags";
  if ( !a1 )
  {
    v11 = 0;
LABEL_9:
    v14 = 0;
    goto LABEL_10;
  }
  v11 = ADSIGetObjectAttributes(a1, &v20, 1, &pMem, &v21);
  if ( v11 < 0 )
  {
    v7 = pMem;
    goto LABEL_26;
  }
  PropertyFromAttr = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v21, L"packageFlags");
  v7 = pMem;
  if ( PropertyFromAttr >= v21 )
  {
    v11 = -2147221143;
    goto LABEL_26;
  }
  v13 = 32LL * PropertyFromAttr;
  if ( !*(_DWORD *)((char *)pMem + v13 + 24) )
    goto LABEL_9;
  v14 = *(_DWORD *)(*(_QWORD *)((char *)pMem + v13 + 16) + 8LL);
LABEL_10:
  if ( a2 )
    v15 = *a2;
  else
    v15 = v14;
  v16 = v14 & 0xE00C0010 | v15;
  if ( a3 )
  {
    if ( *a3 )
      v16 |= 0x40000u;
    else
      v16 &= ~0x40000u;
  }
  if ( a4 )
    v16 = v16 & 0xFFF7FFFF | (*a4 != 5 ? 0x80000 : 0);
  if ( a5 )
    v16 = v16 & 0x1FFFFFFF | (*(_DWORD *)a5 << 29);
  *a6 = v16;
  v17 = a7;
  if ( a7 )
  {
    *(_DWORD *)(a7 + 1) = 0;
    *v17 = 82;
    if ( (v16 & 8) != 0 )
      *v17++ = 80;
    if ( (v16 & 0x400) != 0 )
      *v17 = 65;
  }
LABEL_26:
  if ( v7 )
    FreeADsMem(v7);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180021fa0  push    rbp
0x180021fa2  push    rbx
0x180021fa3  push    rsi
0x180021fa4  push    rdi
0x180021fa5  push    r12
0x180021fa7  push    r14
0x180021fa9  mov     rbp, rsp
0x180021fac  sub     rsp, 48h
0x180021fb0  xor     r10d, r10d
0x180021fb3  mov     [rbp+arg_0], 0
0x180021fba  mov     [rbp+pMem], r10
0x180021fbe  lea     r12, aPackageflags; "packageFlags"
0x180021fc5  mov     [rbp+var_10], r12
0x180021fc9  mov     rdi, r9
0x180021fcc  mov     r14, r8
0x180021fcf  mov     rsi, rdx
0x180021fd2  test    rcx, rcx
0x180021fd5  jz      short loc_18002203B
0x180021fd7  lea     rax, [rbp+arg_0]
0x180021fdb  lea     r9, [rbp+pMem]
0x180021fdf  mov     [rsp+48h+var_28], rax
0x180021fe4  lea     r8d, [r10+1]
0x180021fe8  lea     rdx, [rbp+var_10]
0x180021fec  call    cs:__imp_ADSIGetObjectAttributes
0x180021ff2  mov     ebx, eax
0x180021ff4  test    eax, eax
0x180021ff6  js      short loc_180022032
0x180021ff8  mov     edx, [rbp+arg_0]; unsigned int
0x180021ffb  mov     r8, r12; unsigned __int16 *
0x180021ffe  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x180022002  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x180022007  mov     r10, [rbp+pMem]
0x18002200b  cmp     eax, [rbp+arg_0]
0x18002200e  jnb     short loc_180022028
0x180022010  mov     eax, eax
0x180022012  shl     rax, 5
0x180022016  cmp     dword ptr [rax+r10+18h], 0
0x18002201c  jz      short loc_18002203D
0x18002201e  mov     rax, [rax+r10+10h]
0x180022023  mov     ecx, [rax+8]
0x180022026  jmp     short loc_18002203F
0x180022028  mov     ebx, 80040169h
0x18002202d  jmp     loc_1800220D2
0x180022032  mov     r10, [rbp+pMem]
0x180022036  jmp     loc_1800220D2
0x18002203b  xor     ebx, ebx
0x18002203d  xor     ecx, ecx
0x18002203f  test    rsi, rsi
0x180022042  jz      short loc_180022048
0x180022044  mov     edx, [rsi]
0x180022046  jmp     short loc_18002204A
0x180022048  mov     edx, ecx
0x18002204a  and     ecx, 0E00C0010h
0x180022050  or      edx, ecx
0x180022052  test    r14, r14
0x180022055  jz      short loc_180022067
0x180022057  cmp     dword ptr [r14], 0
0x18002205b  jz      short loc_180022063
0x18002205d  bts     edx, 12h
0x180022061  jmp     short loc_180022067
0x180022063  btr     edx, 12h
0x180022067  test    rdi, rdi
0x18002206a  jz      short loc_180022085
0x18002206c  mov     eax, [rdi]
0x18002206e  sub     eax, 5
0x180022071  neg     eax
0x180022073  mov     eax, edx
0x180022075  sbb     ecx, ecx
0x180022077  btr     eax, 13h
0x18002207b  and     ecx, 80000h
0x180022081  mov     edx, ecx
0x180022083  or      edx, eax
0x180022085  mov     rcx, [rbp+arg_20]
0x180022089  test    rcx, rcx
0x18002208c  jz      short loc_18002209E
0x18002208e  mov     ecx, [rcx]
0x180022090  mov     eax, edx
0x180022092  shl     ecx, 1Dh
0x180022095  and     eax, 1FFFFFFFh
0x18002209a  mov     edx, ecx
0x18002209c  or      edx, eax
0x18002209e  mov     rax, [rbp+arg_28]
0x1800220a2  mov     [rax], edx
0x1800220a4  mov     rax, [rbp+arg_30]
0x1800220a8  test    rax, rax
0x1800220ab  jz      short loc_1800220D2
0x1800220ad  mov     dword ptr [rax+2], 0
0x1800220b4  mov     word ptr [rax], 52h ; 'R'
0x1800220b9  test    dl, 8
0x1800220bc  jz      short loc_1800220C7
0x1800220be  mov     word ptr [rax], 50h ; 'P'
0x1800220c3  add     rax, 2
0x1800220c7  bt      edx, 0Ah
0x1800220cb  jnb     short loc_1800220D2
0x1800220cd  mov     word ptr [rax], 41h ; 'A'
0x1800220d2  test    r10, r10
0x1800220d5  jz      short loc_1800220E0
0x1800220d7  mov     rcx, r10; pMem
0x1800220da  call    cs:__imp_FreeADsMem
0x1800220e0  mov     eax, ebx
0x1800220e2  add     rsp, 48h
0x1800220e6  pop     r14
0x1800220e8  pop     r12
0x1800220ea  pop     rdi
0x1800220eb  pop     rsi
0x1800220ec  pop     rbx
0x1800220ed  pop     rbp
0x1800220ee  retn
```
