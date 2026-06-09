# CPropertyCache::DispatchGetProperty(ulong,tagVARIANT *)

- ea: `0x180010104`
- end: `0x1800102d8`
- name: `?DispatchGetProperty@CPropertyCache@@IEAAJKPEAUtagVARIANT@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned int, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180010e80`

## callees

- `0x180010104`
- `0x180010968`
- `0x180010cd8`
- `0x1800184ac`
- `0x180018518`
- `0x1800186d0`
- `0x18001b3ec`
- `0x18001b524`
- `0x18001d66a`
- `0x18001d6c0`

## pseudocode

```c
__int64 __fastcall CPropertyCache::DispatchGetProperty(unsigned __int16 **this, unsigned int a2, struct tagVARIANT *a3)
{
  __int64 v4; // rsi
  int Schema; // ebx
  unsigned __int16 *v8; // r12
  unsigned int v9; // r9d
  unsigned int v10; // r14d
  unsigned __int16 *v11; // rdx
  int v12; // eax
  struct _iistype *v13; // rsi
  int v14; // eax
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v16; // [rsp+44h] [rbp-BCh] BYREF
  struct _iistype *v17; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v18[264]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = a2;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  memset_0(v18, 0, 0x208u);
  Schema = CPropertyCache::LoadSchema((CPropertyCache *)this);
  if ( Schema < 0 )
    goto LABEL_23;
  if ( !a3 )
    return 2147614735LL;
  if ( (unsigned int)v4 >= *((_DWORD *)this + 25) )
    return 2147614723LL;
  v8 = &this[11][260 * v4];
  Schema = IIsSchema::LookupSyntaxID((IIsSchema *)this[9], v8, &v16);
  if ( Schema < 0 )
    goto LABEL_23;
  v10 = v16;
  if ( ((v16 - 5) & 0xFFFFFFFD) == 0 )
  {
    Schema = IIsSchema::LookupFlagPropName((IIsSchema *)this[9], v8, v18, v9);
    if ( Schema < 0 )
      goto LABEL_23;
  }
  v11 = v18;
  if ( ((v10 - 5) & 0xFFFFFFFD) != 0 )
    v11 = v8;
  v12 = CPropertyCache::getproperty((IIsSchema **)this, v11, &v16, &v15, &v17);
  v13 = v17;
  Schema = v12;
  if ( v12 >= 0 )
  {
    *(_DWORD *)v17 = v10;
    if ( v10 == 5 )
    {
      v14 = IISTypeToVarTypeCopy((struct IIsSchema *)this[9], v8, v13, a3, 1, this[10]);
    }
    else if ( v15 == 1 && ((v10 - 4) & 0xFFFFFFFB) != 0 )
    {
      v14 = IISTypeToVarTypeCopy((struct IIsSchema *)this[9], v8, v13, a3, 0, this[10]);
    }
    else
    {
      v14 = IISTypeToVarTypeCopyConstruct((struct IIsSchema *)this[9], v8, v13, v15, a3, 0, this[10]);
    }
    Schema = v14;
  }
  if ( v13 )
    IISTypeFreeIISObjects(v13, v15);
  if ( Schema < 0 )
LABEL_23:
    a3->vt = 10;
  return (unsigned int)Schema;
}

```

## disassembly

```asm
0x180010104  push    rbp
0x180010106  push    rbx
0x180010107  push    rsi
0x180010108  push    rdi
0x180010109  push    r12
0x18001010b  push    r14
0x18001010d  push    r15
0x18001010f  lea     rbp, [rsp-170h]
0x180010117  sub     rsp, 270h
0x18001011e  mov     rax, cs:__security_cookie
0x180010125  xor     rax, rsp
0x180010128  mov     [rbp+1A0h+var_40], rax
0x18001012f  mov     r15, r8
0x180010132  mov     esi, edx
0x180010134  mov     rdi, rcx
0x180010137  mov     [rsp+2A0h+var_25C], 0
0x18001013f  xor     edx, edx; Val
0x180010141  mov     [rsp+2A0h+var_260], 0
0x180010149  mov     r8d, 208h; Size
0x18001014f  mov     [rsp+2A0h+var_258], 0
0x180010158  lea     rcx, [rsp+2A0h+var_250]; void *
0x18001015d  call    memset_0
0x180010162  mov     rcx, rdi; this
0x180010165  call    ?LoadSchema@CPropertyCache@@IEAAJXZ; CPropertyCache::LoadSchema(void)
0x18001016a  mov     ebx, eax
0x18001016c  test    eax, eax
0x18001016e  js      loc_1800102AF
0x180010174  test    r15, r15
0x180010177  jnz     short loc_180010183
0x180010179  mov     eax, 8002000Fh
0x18001017e  jmp     loc_1800102B7
0x180010183  cmp     esi, [rdi+64h]
0x180010186  jb      short loc_180010192
0x180010188  mov     eax, 80020003h
0x18001018d  jmp     loc_1800102B7
0x180010192  mov     rcx, [rdi+48h]; this
0x180010196  lea     r8, [rsp+2A0h+var_25C]; unsigned int *
0x18001019b  imul    r12, rsi, 208h
0x1800101a2  add     r12, [rdi+58h]
0x1800101a6  mov     rdx, r12; unsigned __int16 *
0x1800101a9  call    ?LookupSyntaxID@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::LookupSyntaxID(ushort const *,ulong *)
0x1800101ae  mov     ebx, eax
0x1800101b0  test    eax, eax
0x1800101b2  js      loc_1800102AF
0x1800101b8  mov     r14d, [rsp+2A0h+var_25C]
0x1800101bd  mov     esi, 0FFFFFFFDh
0x1800101c2  lea     eax, [r14-5]
0x1800101c6  test    esi, eax
0x1800101c8  jnz     short loc_1800101E5
0x1800101ca  mov     rcx, [rdi+48h]; this
0x1800101ce  lea     r8, [rsp+2A0h+var_250]; unsigned __int16 *
0x1800101d3  mov     rdx, r12; unsigned __int16 *
0x1800101d6  call    ?LookupFlagPropName@IIsSchema@@QEAAJPEBGPEAGK@Z; IIsSchema::LookupFlagPropName(ushort const *,ushort *,ulong)
0x1800101db  mov     ebx, eax
0x1800101dd  test    eax, eax
0x1800101df  js      loc_1800102AF
0x1800101e5  lea     eax, [r14-5]
0x1800101e9  mov     rcx, rdi; this
0x1800101ec  test    esi, eax
0x1800101ee  lea     rdx, [rsp+2A0h+var_250]
0x1800101f3  lea     rax, [rsp+2A0h+var_258]
0x1800101f8  cmovnz  rdx, r12; unsigned __int16 *
0x1800101fc  mov     [rsp+2A0h+pvarg], rax; struct _iistype **
0x180010201  lea     r9, [rsp+2A0h+var_260]; unsigned int *
0x180010206  lea     r8, [rsp+2A0h+var_25C]; unsigned int *
0x18001020b  call    ?getproperty@CPropertyCache@@QEAAJPEAGPEAK1PEAPEAU_iistype@@@Z; CPropertyCache::getproperty(ushort *,ulong *,ulong *,_iistype * *)
0x180010210  mov     rsi, [rsp+2A0h+var_258]
0x180010215  mov     ebx, eax
0x180010217  test    eax, eax
0x180010219  js      short loc_18001029A
0x18001021b  mov     [rsi], r14d
0x18001021e  cmp     r14d, 5
0x180010222  jnz     short loc_180010249
0x180010224  mov     rax, [rdi+50h]
0x180010228  mov     [rsp+2A0h+var_278], rax; unsigned __int16 *
0x18001022d  mov     dword ptr [rsp+2A0h+pvarg], 1; int
0x180010235  mov     rcx, [rdi+48h]; struct IIsSchema *
0x180010239  mov     r9, r15; struct tagVARIANT *
0x18001023c  mov     r8, rsi; struct _iistype *
0x18001023f  mov     rdx, r12; unsigned __int16 *
0x180010242  call    ?IISTypeToVarTypeCopy@@YAJPEAVIIsSchema@@PEAGPEAU_iistype@@PEAUtagVARIANT@@HPEBG@Z; IISTypeToVarTypeCopy(IIsSchema *,ushort *,_iistype *,tagVARIANT *,int,ushort const *)
0x180010247  jmp     short loc_180010298
0x180010249  cmp     [rsp+2A0h+var_260], 1
0x18001024e  jnz     short loc_18001026E
0x180010250  lea     eax, [r14-4]
0x180010254  test    eax, 0FFFFFFFBh
0x180010259  jz      short loc_18001026E
0x18001025b  mov     rax, [rdi+50h]
0x18001025f  mov     [rsp+2A0h+var_278], rax
0x180010264  mov     dword ptr [rsp+2A0h+pvarg], 0
0x18001026c  jmp     short loc_180010235
0x18001026e  mov     rax, [rdi+50h]
0x180010272  mov     r8, rsi; struct _iistype *
0x180010275  mov     r9d, [rsp+2A0h+var_260]; unsigned int
0x18001027a  mov     rdx, r12; unsigned __int16 *
0x18001027d  mov     rcx, [rdi+48h]; struct IIsSchema *
0x180010281  mov     [rsp+2A0h+var_270], rax; unsigned __int16 *
0x180010286  mov     dword ptr [rsp+2A0h+var_278], 0; int
0x18001028e  mov     [rsp+2A0h+pvarg], r15; pvarg
0x180010293  call    ?IISTypeToVarTypeCopyConstruct@@YAJPEAVIIsSchema@@PEAGPEAU_iistype@@KPEAUtagVARIANT@@HPEBG@Z; IISTypeToVarTypeCopyConstruct(IIsSchema *,ushort *,_iistype *,ulong,tagVARIANT *,int,ushort const *)
0x180010298  mov     ebx, eax
0x18001029a  test    rsi, rsi
0x18001029d  jz      short loc_1800102AB
0x18001029f  mov     edx, [rsp+2A0h+var_260]; unsigned int
0x1800102a3  mov     rcx, rsi; struct _iistype *
0x1800102a6  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x1800102ab  test    ebx, ebx
0x1800102ad  jns     short loc_1800102B5
0x1800102af  mov     word ptr [r15], 0Ah
0x1800102b5  mov     eax, ebx
0x1800102b7  mov     rcx, [rbp+1A0h+var_40]
0x1800102be  xor     rcx, rsp; StackCookie
0x1800102c1  call    __security_check_cookie
0x1800102c6  add     rsp, 270h
0x1800102cd  pop     r15
0x1800102cf  pop     r14
0x1800102d1  pop     r12
0x1800102d3  pop     rdi
0x1800102d4  pop     rsi
0x1800102d5  pop     rbx
0x1800102d6  pop     rbp
0x1800102d7  retn
```
