# PConvertToCurrentVersionDevmodeWithOemPlugins(void *,ulong,_RAWBINARYDATA *,ulong,_devicemodeW *,_devicemodeW *,_OEM_PLUGINS *,ulong *)

- ea: `0x180033ce0`
- end: `0x180034016`
- name: `?PConvertToCurrentVersionDevmodeWithOemPlugins@@YAPEAU_devicemodeW@@PEAXKPEAU_RAWBINARYDATA@@KPEAU1@2PEAU_OEM_PLUGINS@@PEAK@Z`
- size: `822`
- prototype: `struct _devicemodeW *(void *, unsigned int, struct _RAWBINARYDATA *, unsigned int, struct _devicemodeW *, struct _devicemodeW *, struct _OEM_PLUGINS *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180033b84`

## callees

- `0x180004550`
- `0x180033ce0`
- `0x18003401c`
- `0x1800340ac`
- `0x180035058`
- `0x180074580`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180033e97`
- `KERNEL32!LocalFree` at `0x180033e97`
- `KERNEL32!LocalAlloc` at `0x180033d8c`
- `KERNEL32!LocalAlloc` at `0x180033d8c`

## pseudocode

```c
struct _devicemodeW *__fastcall PConvertToCurrentVersionDevmodeWithOemPlugins(
        void *a1,
        unsigned int a2,
        struct _RAWBINARYDATA *a3,
        __int64 a4,
        struct _devicemodeW *Src,
        struct _devicemodeW *a6,
        struct _OEM_PLUGINS *a7,
        unsigned int *a8)
{
  __int64 v8; // r13
  int v10; // r12d
  int v11; // eax
  int v12; // r14d
  unsigned int v13; // eax
  size_t v14; // rbp
  struct _devicemodeW *v15; // rbx
  struct _devicemodeW *v16; // rdi
  size_t dmSize; // r8
  unsigned int dmDriverExtra; // esi
  unsigned __int16 *v19; // r9
  int v20; // edx
  unsigned __int16 v21; // ax
  unsigned __int16 v22; // ax
  struct _devicemodeW *v23; // rcx
  struct _devicemodeW *v24; // r15
  __int64 v26; // rax
  _OWORD *v27; // rdx
  __int128 v28; // xmm1
  size_t Size; // [rsp+98h] [rbp+20h] BYREF

  v8 = a2;
  LODWORD(Size) = 0;
  *a8 = 0;
  if ( !a3 )
    return 0;
  v10 = 1;
  v11 = 0;
  if ( *((_DWORD *)a3 + 1) == 1196442656 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    if ( *((_DWORD *)a3 + 1) != 1347437600 )
      v11 = -2147418113;
  }
  if ( v11 < 0 )
    return 0;
  if ( !v12 )
    return 0;
  if ( !(unsigned int)BCalcTotalOEMDMSize(a1, a7, &Size) )
    return 0;
  v13 = v8 + 824;
  if ( (unsigned int)v8 >= 0xFFFFFCC8 )
    return 0;
  v14 = (unsigned int)Size;
  if ( v13 + (unsigned int)Size < v13 )
    return 0;
  v15 = (struct _devicemodeW *)LocalAlloc(0x40u, v13 + (unsigned int)Size);
  if ( !v15 )
    return 0;
  v16 = Src;
  dmSize = 220;
  if ( Src->dmSize <= 0xDCu )
    dmSize = Src->dmSize;
  memcpy_0(v15, Src, dmSize);
  v15->dmSpecVersion = 1025;
  v15->dmSize = 220;
  LODWORD(Size) = 0;
  dmDriverExtra = v16->dmDriverExtra;
  if ( v16->dmDriverVersion >= 0x500u
    && (unsigned __int16)dmDriverExtra >= 0x230u
    && (v19 = (WCHAR *)((char *)v16->dmDeviceName + v16->dmSize), *(_DWORD *)v19 == 1431193924)
    && (v20 = v19[4], v21 = v19[5], LODWORD(Size) = v21, (unsigned __int16)v20 >= 0x230u)
    && v20 + (unsigned int)v21 <= dmDriverExtra )
  {
    if ( (unsigned __int16)dmDriverExtra > (unsigned __int16)v20 )
      LOWORD(dmDriverExtra) = v20;
    v22 = 604;
    if ( (unsigned __int16)dmDriverExtra <= 0x25Cu )
      v22 = dmDriverExtra;
    memcpy_0(&v15[1], v19, v22);
    GPDValidateDocOptions((__int64)a3, (__int64)&v15->dmDeviceName[24] + v15->dmSize);
    v24 = a6;
  }
  else
  {
    v24 = a6;
    v23 = v15 + 1;
    v10 = 0;
    v26 = 4;
    v27 = (_OWORD *)((char *)a6->dmDeviceName + a6->dmSize);
    do
    {
      *(_OWORD *)v23->dmDeviceName = *v27;
      *(_OWORD *)&v23->dmDeviceName[8] = v27[1];
      *(_OWORD *)&v23->dmDeviceName[16] = v27[2];
      *(_OWORD *)&v23->dmDeviceName[24] = v27[3];
      *(_OWORD *)&v23->dmSpecVersion = v27[4];
      *(union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C *)((char *)&v23->76 + 4) = (union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C)v27[5];
      *(_OWORD *)&v23->dmYResolution = v27[6];
      v28 = v27[7];
      v27 += 8;
      *(_OWORD *)&v23->dmFormName[5] = v28;
      v23 = (struct _devicemodeW *)((char *)v23 + 128);
      --v26;
    }
    while ( v26 );
    *(_OWORD *)v23->dmDeviceName = *v27;
    *(_OWORD *)&v23->dmDeviceName[8] = v27[1];
    *(_OWORD *)&v23->dmDeviceName[16] = v27[2];
    *(_OWORD *)&v23->dmDeviceName[24] = v27[3];
    *(_OWORD *)&v23->dmSpecVersion = v27[4];
    v23->76 = *(union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C *)((char *)v27 + 76);
  }
  v15->dmDriverVersion = 1539;
  if ( (int)PatchDevmodeSizeFieldsAndJTHdr(v23, v15, v8, v14, v12) < 0
    || (_DWORD)v14
    && (memcpy_0((char *)&v15[3].dmFormName[31] + v8, (char *)&v24[3].dmFormName[31] + v8, v14), v10)
    && (_WORD)Size
    && v16->dmDriverExtra > (unsigned __int16)dmDriverExtra
    && !(unsigned int)BConvertOemPluginDevmode(
                        a1,
                        v15,
                        v16,
                        (struct _OEM_DMEXTRAHEADER *)((char *)&v15[3].dmFormName[31] + v8),
                        (struct _OEM_DMEXTRAHEADER *)((char *)v16 + v16->dmSize + (unsigned __int16)dmDriverExtra),
                        (unsigned __int16)Size,
                        (__int64)a7) )
  {
    LocalFree(v15);
    return 0;
  }
  *a8 = v14;
  return v15;
}

```

## disassembly

```asm
0x180033ce0  mov     rax, rsp
0x180033ce3  mov     [rax+10h], rbx
0x180033ce7  mov     [rax+20h], r9d
0x180033ceb  mov     [rax+8], rcx
0x180033cef  push    rbp
0x180033cf0  push    rsi
0x180033cf1  push    rdi
0x180033cf2  push    r12
0x180033cf4  push    r13
0x180033cf6  push    r14
0x180033cf8  push    r15
0x180033cfa  sub     rsp, 40h
0x180033cfe  xor     esi, esi
0x180033d00  mov     r13d, edx
0x180033d03  mov     [rax+20h], esi
0x180033d06  mov     r15, r8
0x180033d09  mov     rax, [rsp+78h+arg_38]
0x180033d11  mov     [rax], esi
0x180033d13  test    r8, r8
0x180033d16  jz      loc_180033E9D
0x180033d1c  cmp     dword ptr [r8+4], 47504420h
0x180033d24  lea     r12d, [rsi+1]
0x180033d28  mov     eax, esi
0x180033d2a  jnz     loc_180033ECE
0x180033d30  mov     r14d, r12d
0x180033d33  test    eax, eax
0x180033d35  js      loc_180033E9D
0x180033d3b  test    r14d, r14d
0x180033d3e  jz      loc_180033E9D
0x180033d44  mov     rdx, [rsp+78h+arg_30]
0x180033d4c  lea     r8, [rsp+78h+Size]
0x180033d54  call    BCalcTotalOEMDMSize
0x180033d59  test    eax, eax
0x180033d5b  jz      loc_180033E9D
0x180033d61  lea     eax, [r13+338h]
0x180033d68  cmp     eax, 338h
0x180033d6d  jb      loc_180033E9D
0x180033d73  mov     ebp, dword ptr [rsp+78h+Size]
0x180033d7a  lea     ecx, [rax+rbp]
0x180033d7d  cmp     ecx, eax
0x180033d7f  jb      loc_180033E9D
0x180033d85  mov     edx, ecx; uBytes
0x180033d87  mov     ecx, 40h ; '@'; uFlags
0x180033d8c  call    cs:__imp_LocalAlloc
0x180033d92  mov     rbx, rax
0x180033d95  test    rax, rax
0x180033d98  jz      loc_180033E9D
0x180033d9e  mov     rdi, [rsp+78h+Src]
0x180033da6  mov     eax, 0DCh
0x180033dab  mov     r8d, eax
0x180033dae  cmp     ax, [rdi+44h]
0x180033db2  jb      short loc_180033DB9
0x180033db4  movzx   r8d, word ptr [rdi+44h]; Size
0x180033db9  mov     rdx, rdi; Src
0x180033dbc  mov     rcx, rbx; void *
0x180033dbf  call    memcpy_0
0x180033dc4  mov     word ptr [rbx+40h], 401h
0x180033dca  mov     eax, 500h
0x180033dcf  mov     word ptr [rbx+44h], 0DCh
0x180033dd5  mov     dword ptr [rsp+78h+Size], esi
0x180033ddc  movzx   esi, word ptr [rdi+46h]
0x180033de0  cmp     [rdi+42h], ax
0x180033de4  jb      loc_180033EE9
0x180033dea  mov     ecx, 230h
0x180033def  cmp     si, cx
0x180033df2  jb      loc_180033EE9
0x180033df8  movzx   eax, word ptr [rdi+44h]
0x180033dfc  lea     r9, [rax+rdi]
0x180033e00  cmp     dword ptr [r9], 554E4944h
0x180033e07  jnz     loc_180033EE9
0x180033e0d  movzx   edx, word ptr [r9+8]
0x180033e12  movzx   eax, word ptr [r9+0Ah]
0x180033e17  mov     dword ptr [rsp+78h+Size], eax
0x180033e1e  cmp     dx, cx
0x180033e21  jb      loc_180033EE9
0x180033e27  movzx   ecx, ax
0x180033e2a  add     ecx, edx
0x180033e2c  cmp     ecx, esi
0x180033e2e  ja      loc_180033EE9
0x180033e34  cmp     si, dx
0x180033e37  jbe     short loc_180033E3C
0x180033e39  movzx   esi, dx
0x180033e3c  mov     eax, 25Ch
0x180033e41  cmp     ax, si
0x180033e44  jb      short loc_180033E49
0x180033e46  movzx   eax, si
0x180033e49  movzx   r8d, ax; Size
0x180033e4d  lea     rcx, [rbx+0DCh]; void *
0x180033e54  mov     rdx, r9; Src
0x180033e57  call    memcpy_0
0x180033e5c  movzx   edx, word ptr [rbx+44h]
0x180033e60  mov     rcx, r15
0x180033e63  add     rdx, 30h ; '0'
0x180033e67  add     rdx, rbx
0x180033e6a  call    GPDValidateDocOptions
0x180033e6f  mov     r15, [rsp+78h+arg_28]
0x180033e77  mov     r9d, ebp; unsigned int
0x180033e7a  mov     word ptr [rbx+42h], 603h
0x180033e80  mov     r8d, r13d; unsigned int
0x180033e83  mov     dword ptr [rsp+78h+var_58], r14d; int
0x180033e88  mov     rdx, rbx; struct _devicemodeW *
0x180033e8b  call    ?PatchDevmodeSizeFieldsAndJTHdr@@YAJPEAXPEAU_devicemodeW@@KKH@Z; PatchDevmodeSizeFieldsAndJTHdr(void *,_devicemodeW *,ulong,ulong,int)
0x180033e90  test    eax, eax
0x180033e92  jns     short loc_180033EB7
0x180033e94  mov     rcx, rbx; hMem
0x180033e97  call    cs:__imp_LocalFree
0x180033e9d  xor     eax, eax
0x180033e9f  mov     rbx, [rsp+78h+arg_8]
0x180033ea7  add     rsp, 40h
0x180033eab  pop     r15
0x180033ead  pop     r14
0x180033eaf  pop     r13
0x180033eb1  pop     r12
0x180033eb3  pop     rdi
0x180033eb4  pop     rsi
0x180033eb5  pop     rbp
0x180033eb6  retn
0x180033eb7  test    ebp, ebp
0x180033eb9  jnz     loc_180033F89
0x180033ebf  mov     rax, [rsp+78h+arg_38]
0x180033ec7  mov     [rax], ebp
0x180033ec9  mov     rax, rbx
0x180033ecc  jmp     short loc_180033E9F
0x180033ece  cmp     dword ptr [r8+4], 50504420h
0x180033ed6  mov     r14d, esi
0x180033ed9  jz      loc_180033D33
0x180033edf  mov     eax, 8000FFFFh
0x180033ee4  jmp     loc_180033D33
0x180033ee9  mov     r15, [rsp+78h+arg_28]
0x180033ef1  lea     rcx, [rbx+0DCh]
0x180033ef8  xor     r12d, r12d
0x180033efb  movzx   edx, word ptr [r15+44h]
0x180033f00  lea     eax, [r12+4]
0x180033f05  add     rdx, r15
0x180033f08  lea     r8d, [rax+7Ch]
0x180033f0c  movups  xmm0, xmmword ptr [rdx]
0x180033f0f  movups  xmmword ptr [rcx], xmm0
0x180033f12  movups  xmm1, xmmword ptr [rdx+10h]
0x180033f16  movups  xmmword ptr [rcx+10h], xmm1
0x180033f1a  movups  xmm0, xmmword ptr [rdx+20h]
0x180033f1e  movups  xmmword ptr [rcx+20h], xmm0
0x180033f22  movups  xmm1, xmmword ptr [rdx+30h]
0x180033f26  movups  xmmword ptr [rcx+30h], xmm1
0x180033f2a  movups  xmm0, xmmword ptr [rdx+40h]
0x180033f2e  movups  xmmword ptr [rcx+40h], xmm0
0x180033f32  movups  xmm1, xmmword ptr [rdx+50h]
0x180033f36  movups  xmmword ptr [rcx+50h], xmm1
0x180033f3a  movups  xmm0, xmmword ptr [rdx+60h]
0x180033f3e  movups  xmmword ptr [rcx+60h], xmm0
0x180033f42  movups  xmm1, xmmword ptr [rdx+70h]
0x180033f46  add     rdx, r8
0x180033f49  movups  xmmword ptr [rcx+70h], xmm1
0x180033f4d  add     rcx, r8
0x180033f50  sub     rax, 1
0x180033f54  jnz     short loc_180033F0C
0x180033f56  movups  xmm0, xmmword ptr [rdx]
0x180033f59  movups  xmmword ptr [rcx], xmm0
0x180033f5c  movups  xmm1, xmmword ptr [rdx+10h]
0x180033f60  movups  xmmword ptr [rcx+10h], xmm1
0x180033f64  movups  xmm0, xmmword ptr [rdx+20h]
0x180033f68  movups  xmmword ptr [rcx+20h], xmm0
0x180033f6c  movups  xmm1, xmmword ptr [rdx+30h]
0x180033f70  movups  xmmword ptr [rcx+30h], xmm1
0x180033f74  movups  xmm0, xmmword ptr [rdx+40h]
0x180033f78  movups  xmmword ptr [rcx+40h], xmm0
0x180033f7c  movups  xmm1, xmmword ptr [rdx+4Ch]
0x180033f80  movups  xmmword ptr [rcx+4Ch], xmm1
0x180033f84  jmp     loc_180033E77
0x180033f89  lea     r14, [rbx+r13]
0x180033f8d  mov     r8, rbp; Size
0x180033f90  lea     rdx, [r13+338h]
0x180033f97  add     rdx, r15; Src
0x180033f9a  lea     rcx, [r14+338h]; void *
0x180033fa1  call    memcpy_0
0x180033fa6  test    r12d, r12d
0x180033fa9  jz      loc_180033EBF
0x180033faf  mov     eax, dword ptr [rsp+78h+Size]
0x180033fb6  test    ax, ax
0x180033fb9  jz      loc_180033EBF
0x180033fbf  cmp     [rdi+46h], si
0x180033fc3  jbe     loc_180033EBF
0x180033fc9  movzx   edx, ax
0x180033fcc  lea     r9, [r14+338h]; struct _OEM_DMEXTRAHEADER *
0x180033fd3  movzx   eax, word ptr [rdi+44h]
0x180033fd7  mov     r8, rdi; struct _devicemodeW *
0x180033fda  add     rax, rdi
0x180033fdd  movzx   ecx, si
0x180033fe0  add     rcx, rax
0x180033fe3  mov     rax, [rsp+78h+arg_30]
0x180033feb  mov     [rsp+78h+var_48], rax; __int64
0x180033ff0  mov     [rsp+78h+var_50], edx; int
0x180033ff4  mov     rdx, rbx; struct _devicemodeW *
0x180033ff7  mov     [rsp+78h+var_58], rcx; struct _OEM_DMEXTRAHEADER *
0x180033ffc  mov     rcx, [rsp+78h+arg_0]; void *
0x180034004  call    BConvertOemPluginDevmode
0x180034009  test    eax, eax
0x18003400b  jz      loc_180033E94
0x180034011  jmp     loc_180033EBF
```
