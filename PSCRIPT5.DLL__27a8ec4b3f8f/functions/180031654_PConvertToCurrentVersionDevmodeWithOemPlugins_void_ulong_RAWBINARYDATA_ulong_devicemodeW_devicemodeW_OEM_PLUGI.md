# PConvertToCurrentVersionDevmodeWithOemPlugins(void *,ulong,_RAWBINARYDATA *,ulong,_devicemodeW *,_devicemodeW *,_OEM_PLUGINS *,ulong *)

- ea: `0x180031654`
- end: `0x1800319da`
- name: `?PConvertToCurrentVersionDevmodeWithOemPlugins@@YAPEAU_devicemodeW@@PEAXKPEAU_RAWBINARYDATA@@KPEAU1@2PEAU_OEM_PLUGINS@@PEAK@Z`
- size: `902`
- prototype: `struct _devicemodeW *__fastcall(void *, unsigned int, struct _RAWBINARYDATA *, __int64, struct _devicemodeW *Src, struct _devicemodeW *, struct _OEM_PLUGINS *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180032054`

## callees

- `0x180031004`
- `0x180031654`
- `0x1800319e0`
- `0x180031c70`
- `0x180031dec`
- `0x18005de70`
- `0x18005e0c4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800319b3`
- `KERNEL32!LocalFree` at `0x1800319b3`
- `KERNEL32!LocalAlloc` at `0x1800316f3`
- `KERNEL32!LocalAlloc` at `0x1800316f3`

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
  __int64 v10; // r9
  unsigned int v11; // eax
  size_t v12; // rbp
  struct _devicemodeW *v13; // rbx
  struct _devicemodeW *v14; // rsi
  int v15; // r15d
  int v16; // r14d
  size_t dmSize; // r8
  __int64 v18; // r9
  unsigned int dmDriverExtra; // edi
  unsigned __int16 *v20; // r9
  int v21; // edx
  int v22; // eax
  unsigned __int16 v23; // ax
  struct _devicemodeW *v24; // rcx
  struct _devicemodeW *v25; // r12
  __int64 v26; // rdx
  _OWORD *v27; // rax
  __int128 v28; // xmm1
  size_t Size[9]; // [rsp+40h] [rbp-48h] BYREF
  int v32; // [rsp+A8h] [rbp+20h] BYREF

  v8 = a2;
  LODWORD(Size[0]) = 0;
  v32 = 0;
  *a8 = 0;
  if ( (int)IsRawBinaryDataFromGPD((__int64)a3, &v32) < 0 )
    return 0;
  if ( v32 )
    return 0;
  if ( !(unsigned int)BCalcTotalOEMDMSize(v10, (__int64 *)a7, Size) )
    return 0;
  v11 = v8 + 976;
  if ( (unsigned int)v8 >= 0xFFFFFC30 )
    return 0;
  v12 = LODWORD(Size[0]);
  if ( v11 + LODWORD(Size[0]) < v11 )
    return 0;
  v13 = (struct _devicemodeW *)LocalAlloc(0x40u, v11 + LODWORD(Size[0]));
  if ( !v13 )
    return 0;
  v14 = Src;
  v15 = 0;
  v16 = 0;
  dmSize = 220;
  if ( Src->dmSize <= 0xDCu )
    dmSize = Src->dmSize;
  memcpy_0(v13, Src, dmSize);
  v13->dmSpecVersion = 1025;
  v13->dmSize = 220;
  v18 = v14->dmSize;
  v32 = 0;
  dmDriverExtra = v14->dmDriverExtra;
  v20 = (WCHAR *)((char *)v14->dmDeviceName + v18);
  if ( v20 && dmDriverExtra >= 4 && *(_DWORD *)v20 == 1431193924 )
    v16 = 1;
  if ( v14->dmDriverVersion >= 0x501u )
  {
    if ( (unsigned __int16)dmDriverExtra >= 0x2C4u && *(_DWORD *)v20 == 1447645776 )
    {
      v21 = v20[57];
      v22 = v20[74];
      LOWORD(v32) = v20[74];
      if ( (unsigned __int16)v21 >= 0x2C4u && v21 + v22 <= dmDriverExtra )
      {
        if ( (unsigned __int16)dmDriverExtra > (unsigned __int16)v21 )
          LOWORD(dmDriverExtra) = v21;
        v23 = 756;
        v15 = 1;
        if ( (unsigned __int16)dmDriverExtra > 0x2F4u )
          goto LABEL_26;
        goto LABEL_25;
      }
    }
LABEL_32:
    v25 = a6;
    v24 = v13 + 1;
    v26 = 5;
    v27 = (_OWORD *)((char *)a6->dmDeviceName + a6->dmSize);
    do
    {
      *(_OWORD *)v24->dmDeviceName = *v27;
      *(_OWORD *)&v24->dmDeviceName[8] = v27[1];
      *(_OWORD *)&v24->dmDeviceName[16] = v27[2];
      *(_OWORD *)&v24->dmDeviceName[24] = v27[3];
      *(_OWORD *)&v24->dmSpecVersion = v27[4];
      *(union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C *)((char *)&v24->76 + 4) = (union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C)v27[5];
      *(_OWORD *)&v24->dmYResolution = v27[6];
      v28 = v27[7];
      v27 += 8;
      *(_OWORD *)&v24->dmFormName[5] = v28;
      v24 = (struct _devicemodeW *)((char *)v24 + 128);
      --v26;
    }
    while ( v26 );
    *(_OWORD *)v24->dmDeviceName = *v27;
    *(_OWORD *)&v24->dmDeviceName[8] = v27[1];
    *(_OWORD *)&v24->dmDeviceName[16] = v27[2];
    *(_OWORD *)&v24->dmDeviceName[24] = v27[3];
    *(_OWORD *)&v24->dmSpecVersion = v27[4];
    *(union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C *)((char *)&v24->76 + 4) = (union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C)v27[5];
    *(_OWORD *)&v24->dmYResolution = v27[6];
    *(_DWORD *)&v24->dmFormName[5] = *((_DWORD *)v27 + 28);
    goto LABEL_29;
  }
  if ( v14->dmDriverVersion != 1024 || (_WORD)dmDriverExtra != 180 || *(_DWORD *)v20 != 1447645776 )
    goto LABEL_32;
LABEL_25:
  v23 = dmDriverExtra;
LABEL_26:
  memcpy_0(&v13[1], v20, v23);
  if ( v15 )
    ValidateDocOptions((__int64)a3, (__int64)&v13->dmMediaType + v13->dmSize);
  v25 = a6;
LABEL_29:
  v13->dmDriverVersion = 1539;
  if ( v16 )
  {
    if ( v13->dmMediaType >= 0x100 )
      v13->dmMediaType = 1;
LABEL_36:
    if ( !(_DWORD)v12
      || (memcpy_0((char *)&v13[4].dmYResolution + v8, (char *)&v25[4].dmYResolution + v8, v12), !v15)
      || !(_WORD)v32
      || v14->dmDriverExtra <= (unsigned __int16)dmDriverExtra
      || (unsigned int)BConvertOemPluginDevmode(
                         a1,
                         v13,
                         v14,
                         (struct _OEM_DMEXTRAHEADER *)((char *)&v13[4].dmYResolution + v8),
                         (struct _OEM_DMEXTRAHEADER *)((char *)v14 + v14->dmSize + (unsigned __int16)dmDriverExtra),
                         (unsigned __int16)v32,
                         (__int64)a7) )
    {
      *a8 = v12;
      return v13;
    }
    goto LABEL_42;
  }
  if ( (int)PatchDevmodeSizeFieldsAndJTHdr(v24, v13, v8, v12, 0) >= 0 )
    goto LABEL_36;
LABEL_42:
  LocalFree(v13);
  return 0;
}

```

## disassembly

```asm
0x180031654  mov     r11, rsp
0x180031657  mov     [r11+10h], rbx
0x18003165b  mov     [r11+20h], r9d
0x18003165f  mov     [r11+8], rcx
0x180031663  push    rbp
0x180031664  push    rsi
0x180031665  push    rdi
0x180031666  push    r12
0x180031668  push    r13
0x18003166a  push    r14
0x18003166c  push    r15
0x18003166e  sub     rsp, 50h
0x180031672  mov     rax, [rsp+88h+arg_38]
0x18003167a  xor     edi, edi
0x18003167c  mov     r13d, edx
0x18003167f  mov     r9, rcx
0x180031682  lea     rdx, [r11+20h]
0x180031686  mov     dword ptr [rsp+88h+Size], edi
0x18003168a  mov     rcx, r8
0x18003168d  mov     [r11+20h], edi
0x180031691  mov     [rax], edi
0x180031693  mov     r12, r8
0x180031696  call    IsRawBinaryDataFromGPD
0x18003169b  test    eax, eax
0x18003169d  js      loc_1800319BF
0x1800316a3  cmp     [rsp+88h+arg_18], edi
0x1800316aa  jnz     loc_1800319BF
0x1800316b0  mov     rdx, [rsp+88h+arg_30]
0x1800316b8  lea     r8, [rsp+88h+Size]
0x1800316bd  mov     rcx, r9
0x1800316c0  call    BCalcTotalOEMDMSize
0x1800316c5  test    eax, eax
0x1800316c7  jz      loc_1800319BF
0x1800316cd  lea     eax, [r13+3D0h]
0x1800316d4  cmp     eax, 3D0h
0x1800316d9  jb      loc_1800319BF
0x1800316df  mov     ebp, dword ptr [rsp+88h+Size]
0x1800316e3  lea     ecx, [rax+rbp]
0x1800316e6  cmp     ecx, eax
0x1800316e8  jb      loc_1800319BF
0x1800316ee  mov     edx, ecx; uBytes
0x1800316f0  lea     ecx, [rdi+40h]; uFlags
0x1800316f3  call    cs:__imp_LocalAlloc
0x1800316fa  nop     dword ptr [rax+rax+00h]
0x1800316ff  mov     rbx, rax
0x180031702  test    rax, rax
0x180031705  jz      loc_1800319BF
0x18003170b  mov     rsi, [rsp+88h+Src]
0x180031713  mov     eax, 0DCh
0x180031718  mov     r15d, edi
0x18003171b  mov     r14d, edi
0x18003171e  mov     r8d, eax
0x180031721  cmp     ax, [rsi+44h]
0x180031725  jb      short loc_18003172C
0x180031727  movzx   r8d, word ptr [rsi+44h]; Size
0x18003172c  mov     rdx, rsi; Src
0x18003172f  mov     rcx, rbx; void *
0x180031732  call    memcpy_0
0x180031737  mov     word ptr [rbx+40h], 401h
0x18003173d  mov     r10d, 1
0x180031743  mov     word ptr [rbx+44h], 0DCh
0x180031749  movzx   r9d, word ptr [rsi+44h]
0x18003174e  mov     [rsp+88h+arg_18], edi
0x180031755  movzx   edi, word ptr [rsi+46h]
0x180031759  add     r9, rsi
0x18003175c  jz      short loc_18003176E
0x18003175e  cmp     edi, 4
0x180031761  jb      short loc_18003176E
0x180031763  cmp     dword ptr [r9], 554E4944h
0x18003176a  cmovz   r14d, r10d
0x18003176e  mov     eax, 501h
0x180031773  cmp     [rsi+42h], ax
0x180031777  jb      short loc_1800317D4
0x180031779  mov     ecx, 2C4h
0x18003177e  cmp     di, cx
0x180031781  jb      loc_18003185C
0x180031787  cmp     dword ptr [r9], 56495250h
0x18003178e  jnz     loc_18003185C
0x180031794  movzx   edx, word ptr [r9+72h]
0x180031799  movzx   eax, word ptr [r9+94h]
0x1800317a1  mov     word ptr [rsp+88h+arg_18], ax
0x1800317a9  cmp     dx, cx
0x1800317ac  jb      loc_18003185C
0x1800317b2  lea     ecx, [rdx+rax]
0x1800317b5  cmp     ecx, edi
0x1800317b7  ja      loc_18003185C
0x1800317bd  cmp     di, dx
0x1800317c0  jbe     short loc_1800317C5
0x1800317c2  movzx   edi, dx
0x1800317c5  mov     eax, 2F4h
0x1800317ca  mov     r15d, r10d
0x1800317cd  cmp     ax, di
0x1800317d0  jnb     short loc_1800317F2
0x1800317d2  jmp     short loc_1800317F5
0x1800317d4  mov     eax, 400h
0x1800317d9  cmp     [rsi+42h], ax
0x1800317dd  jnz     short loc_18003185C
0x1800317df  mov     eax, 0B4h
0x1800317e4  cmp     di, ax
0x1800317e7  jnz     short loc_18003185C
0x1800317e9  cmp     dword ptr [r9], 56495250h
0x1800317f0  jnz     short loc_18003185C
0x1800317f2  movzx   eax, di
0x1800317f5  movzx   r8d, ax; Size
0x1800317f9  lea     rcx, [rbx+0DCh]; void *
0x180031800  mov     rdx, r9; Src
0x180031803  call    memcpy_0
0x180031808  test    r15d, r15d
0x18003180b  jz      short loc_180031823
0x18003180d  movzx   edx, word ptr [rbx+44h]
0x180031811  mov     rcx, r12
0x180031814  add     rdx, 0C4h
0x18003181b  add     rdx, rbx
0x18003181e  call    ValidateDocOptions
0x180031823  mov     r12, [rsp+88h+arg_28]
0x18003182b  mov     r10d, 1
0x180031831  mov     word ptr [rbx+42h], 603h
0x180031837  test    r14d, r14d
0x18003183a  jz      loc_180031907
0x180031840  cmp     dword ptr [rbx+0C4h], 100h
0x18003184a  jb      loc_180031925
0x180031850  mov     [rbx+0C4h], r10d
0x180031857  jmp     loc_180031925
0x18003185c  mov     r12, [rsp+88h+arg_28]
0x180031864  lea     rcx, [rbx+0DCh]
0x18003186b  mov     edx, 5
0x180031870  movzx   eax, word ptr [r12+44h]
0x180031876  add     rax, r12
0x180031879  lea     r8d, [rdx+7Bh]
0x18003187d  movups  xmm0, xmmword ptr [rax]
0x180031880  movups  xmmword ptr [rcx], xmm0
0x180031883  movups  xmm1, xmmword ptr [rax+10h]
0x180031887  movups  xmmword ptr [rcx+10h], xmm1
0x18003188b  movups  xmm0, xmmword ptr [rax+20h]
0x18003188f  movups  xmmword ptr [rcx+20h], xmm0
0x180031893  movups  xmm1, xmmword ptr [rax+30h]
0x180031897  movups  xmmword ptr [rcx+30h], xmm1
0x18003189b  movups  xmm0, xmmword ptr [rax+40h]
0x18003189f  movups  xmmword ptr [rcx+40h], xmm0
0x1800318a3  movups  xmm1, xmmword ptr [rax+50h]
0x1800318a7  movups  xmmword ptr [rcx+50h], xmm1
0x1800318ab  movups  xmm0, xmmword ptr [rax+60h]
0x1800318af  movups  xmmword ptr [rcx+60h], xmm0
0x1800318b3  movups  xmm1, xmmword ptr [rax+70h]
0x1800318b7  add     rax, r8
0x1800318ba  movups  xmmword ptr [rcx+70h], xmm1
0x1800318be  add     rcx, r8
0x1800318c1  sub     rdx, r10
0x1800318c4  jnz     short loc_18003187D
0x1800318c6  movups  xmm0, xmmword ptr [rax]
0x1800318c9  movups  xmmword ptr [rcx], xmm0
0x1800318cc  movups  xmm1, xmmword ptr [rax+10h]
0x1800318d0  movups  xmmword ptr [rcx+10h], xmm1
0x1800318d4  movups  xmm0, xmmword ptr [rax+20h]
0x1800318d8  movups  xmmword ptr [rcx+20h], xmm0
0x1800318dc  movups  xmm1, xmmword ptr [rax+30h]
0x1800318e0  movups  xmmword ptr [rcx+30h], xmm1
0x1800318e4  movups  xmm0, xmmword ptr [rax+40h]
0x1800318e8  movups  xmmword ptr [rcx+40h], xmm0
0x1800318ec  movups  xmm1, xmmword ptr [rax+50h]
0x1800318f0  movups  xmmword ptr [rcx+50h], xmm1
0x1800318f4  movups  xmm0, xmmword ptr [rax+60h]
0x1800318f8  movups  xmmword ptr [rcx+60h], xmm0
0x1800318fc  mov     eax, [rax+70h]
0x1800318ff  mov     [rcx+70h], eax
0x180031902  jmp     loc_180031831
0x180031907  mov     r9d, ebp; unsigned int
0x18003190a  mov     dword ptr [rsp+88h+var_68], 0; int
0x180031912  mov     r8d, r13d; unsigned int
0x180031915  mov     rdx, rbx; struct _devicemodeW *
0x180031918  call    ?PatchDevmodeSizeFieldsAndJTHdr@@YAJPEAXPEAU_devicemodeW@@KKH@Z; PatchDevmodeSizeFieldsAndJTHdr(void *,_devicemodeW *,ulong,ulong,int)
0x18003191d  test    eax, eax
0x18003191f  js      loc_1800319B0
0x180031925  test    ebp, ebp
0x180031927  jz      short loc_1800319A1
0x180031929  lea     r14, [rbx+r13]
0x18003192d  mov     r8, rbp; Size
0x180031930  lea     rdx, [r13+3D0h]
0x180031937  add     rdx, r12; Src
0x18003193a  lea     rcx, [r14+3D0h]; void *
0x180031941  call    memcpy_0
0x180031946  test    r15d, r15d
0x180031949  jz      short loc_1800319A1
0x18003194b  mov     eax, [rsp+88h+arg_18]
0x180031952  test    ax, ax
0x180031955  jz      short loc_1800319A1
0x180031957  cmp     [rsi+46h], di
0x18003195b  jbe     short loc_1800319A1
0x18003195d  movzx   edx, ax
0x180031960  lea     r9, [r14+3D0h]; struct _OEM_DMEXTRAHEADER *
0x180031967  movzx   eax, word ptr [rsi+44h]
0x18003196b  mov     r8, rsi; struct _devicemodeW *
0x18003196e  add     rax, rsi
0x180031971  movzx   ecx, di
0x180031974  add     rcx, rax
0x180031977  mov     rax, [rsp+88h+arg_30]
0x18003197f  mov     [rsp+88h+var_58], rax; __int64
0x180031984  mov     [rsp+88h+var_60], edx; int
0x180031988  mov     rdx, rbx; struct _devicemodeW *
0x18003198b  mov     [rsp+88h+var_68], rcx; struct _OEM_DMEXTRAHEADER *
0x180031990  mov     rcx, [rsp+88h+arg_0]; void *
0x180031998  call    BConvertOemPluginDevmode
0x18003199d  test    eax, eax
0x18003199f  jz      short loc_1800319B0
0x1800319a1  mov     rax, [rsp+88h+arg_38]
0x1800319a9  mov     [rax], ebp
0x1800319ab  mov     rax, rbx
0x1800319ae  jmp     short loc_1800319C1
0x1800319b0  mov     rcx, rbx; hMem
0x1800319b3  call    cs:__imp_LocalFree
0x1800319ba  nop     dword ptr [rax+rax+00h]
0x1800319bf  xor     eax, eax
0x1800319c1  mov     rbx, [rsp+88h+arg_8]
0x1800319c9  add     rsp, 50h
0x1800319cd  pop     r15
0x1800319cf  pop     r14
0x1800319d1  pop     r13
0x1800319d3  pop     r12
0x1800319d5  pop     rdi
0x1800319d6  pop     rsi
0x1800319d7  pop     rbp
0x1800319d8  retn
```
