# PConvertToCurrentVersionDevmodeWithOemPlugins(void *,ulong,_RAWBINARYDATA *,ulong,_devicemodeW *,_devicemodeW *,_OEM_PLUGINS *,ulong *)

- ea: `0x180034678`
- end: `0x1800349bb`
- name: `?PConvertToCurrentVersionDevmodeWithOemPlugins@@YAPEAU_devicemodeW@@PEAXKPEAU_RAWBINARYDATA@@KPEAU1@2PEAU_OEM_PLUGINS@@PEAK@Z`
- size: `835`
- prototype: `struct _devicemodeW *__fastcall(void *, unsigned int, struct _RAWBINARYDATA *, __int64, struct _devicemodeW *Src, struct _devicemodeW *, struct _OEM_PLUGINS *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180034518`

## callees

- `0x180004420`
- `0x180034678`
- `0x1800349c4`
- `0x180034a58`
- `0x180035a30`
- `0x180076660`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180034835`
- `KERNEL32!LocalFree` at `0x180034835`
- `KERNEL32!LocalAlloc` at `0x180034724`
- `KERNEL32!LocalAlloc` at `0x180034724`

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
  if ( !(unsigned int)BCalcTotalOEMDMSize((__int64)a1, (__int64 *)a7, &Size) )
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
0x180034678  mov     rax, rsp
0x18003467b  mov     [rax+10h], rbx
0x18003467f  mov     [rax+20h], r9d
0x180034683  mov     [rax+8], rcx
0x180034687  push    rbp
0x180034688  push    rsi
0x180034689  push    rdi
0x18003468a  push    r12
0x18003468c  push    r13
0x18003468e  push    r14
0x180034690  push    r15
0x180034692  sub     rsp, 40h
0x180034696  xor     esi, esi
0x180034698  mov     r13d, edx
0x18003469b  mov     [rax+20h], esi
0x18003469e  mov     r15, r8
0x1800346a1  mov     rax, [rsp+78h+arg_38]
0x1800346a9  mov     [rax], esi
0x1800346ab  test    r8, r8
0x1800346ae  jz      loc_180034841
0x1800346b4  cmp     dword ptr [r8+4], 47504420h
0x1800346bc  lea     r12d, [rsi+1]
0x1800346c0  mov     eax, esi
0x1800346c2  jnz     loc_180034873
0x1800346c8  mov     r14d, r12d
0x1800346cb  test    eax, eax
0x1800346cd  js      loc_180034841
0x1800346d3  test    r14d, r14d
0x1800346d6  jz      loc_180034841
0x1800346dc  mov     rdx, [rsp+78h+arg_30]
0x1800346e4  lea     r8, [rsp+78h+Size]
0x1800346ec  call    BCalcTotalOEMDMSize
0x1800346f1  test    eax, eax
0x1800346f3  jz      loc_180034841
0x1800346f9  lea     eax, [r13+338h]
0x180034700  cmp     eax, 338h
0x180034705  jb      loc_180034841
0x18003470b  mov     ebp, dword ptr [rsp+78h+Size]
0x180034712  lea     ecx, [rax+rbp]
0x180034715  cmp     ecx, eax
0x180034717  jb      loc_180034841
0x18003471d  mov     edx, ecx; uBytes
0x18003471f  mov     ecx, 40h ; '@'; uFlags
0x180034724  call    cs:__imp_LocalAlloc
0x18003472b  nop     dword ptr [rax+rax+00h]
0x180034730  mov     rbx, rax
0x180034733  test    rax, rax
0x180034736  jz      loc_180034841
0x18003473c  mov     rdi, [rsp+78h+Src]
0x180034744  mov     eax, 0DCh
0x180034749  mov     r8d, eax
0x18003474c  cmp     ax, [rdi+44h]
0x180034750  jb      short loc_180034757
0x180034752  movzx   r8d, word ptr [rdi+44h]; Size
0x180034757  mov     rdx, rdi; Src
0x18003475a  mov     rcx, rbx; void *
0x18003475d  call    memcpy_0
0x180034762  mov     word ptr [rbx+40h], 401h
0x180034768  mov     eax, 500h
0x18003476d  mov     word ptr [rbx+44h], 0DCh
0x180034773  mov     dword ptr [rsp+78h+Size], esi
0x18003477a  movzx   esi, word ptr [rdi+46h]
0x18003477e  cmp     [rdi+42h], ax
0x180034782  jb      loc_18003488E
0x180034788  mov     ecx, 230h
0x18003478d  cmp     si, cx
0x180034790  jb      loc_18003488E
0x180034796  movzx   eax, word ptr [rdi+44h]
0x18003479a  lea     r9, [rax+rdi]
0x18003479e  cmp     dword ptr [r9], 554E4944h
0x1800347a5  jnz     loc_18003488E
0x1800347ab  movzx   edx, word ptr [r9+8]
0x1800347b0  movzx   eax, word ptr [r9+0Ah]
0x1800347b5  mov     dword ptr [rsp+78h+Size], eax
0x1800347bc  cmp     dx, cx
0x1800347bf  jb      loc_18003488E
0x1800347c5  movzx   ecx, ax
0x1800347c8  add     ecx, edx
0x1800347ca  cmp     ecx, esi
0x1800347cc  ja      loc_18003488E
0x1800347d2  cmp     si, dx
0x1800347d5  jbe     short loc_1800347DA
0x1800347d7  movzx   esi, dx
0x1800347da  mov     eax, 25Ch
0x1800347df  cmp     ax, si
0x1800347e2  jb      short loc_1800347E7
0x1800347e4  movzx   eax, si
0x1800347e7  movzx   r8d, ax; Size
0x1800347eb  lea     rcx, [rbx+0DCh]; void *
0x1800347f2  mov     rdx, r9; Src
0x1800347f5  call    memcpy_0
0x1800347fa  movzx   edx, word ptr [rbx+44h]
0x1800347fe  mov     rcx, r15
0x180034801  add     rdx, 30h ; '0'
0x180034805  add     rdx, rbx
0x180034808  call    GPDValidateDocOptions
0x18003480d  mov     r15, [rsp+78h+arg_28]
0x180034815  mov     r9d, ebp; unsigned int
0x180034818  mov     word ptr [rbx+42h], 603h
0x18003481e  mov     r8d, r13d; unsigned int
0x180034821  mov     dword ptr [rsp+78h+var_58], r14d; int
0x180034826  mov     rdx, rbx; struct _devicemodeW *
0x180034829  call    ?PatchDevmodeSizeFieldsAndJTHdr@@YAJPEAXPEAU_devicemodeW@@KKH@Z; PatchDevmodeSizeFieldsAndJTHdr(void *,_devicemodeW *,ulong,ulong,int)
0x18003482e  test    eax, eax
0x180034830  jns     short loc_18003485C
0x180034832  mov     rcx, rbx; hMem
0x180034835  call    cs:__imp_LocalFree
0x18003483c  nop     dword ptr [rax+rax+00h]
0x180034841  xor     eax, eax
0x180034843  mov     rbx, [rsp+78h+arg_8]
0x18003484b  add     rsp, 40h
0x18003484f  pop     r15
0x180034851  pop     r14
0x180034853  pop     r13
0x180034855  pop     r12
0x180034857  pop     rdi
0x180034858  pop     rsi
0x180034859  pop     rbp
0x18003485a  retn
0x18003485c  test    ebp, ebp
0x18003485e  jnz     loc_18003492E
0x180034864  mov     rax, [rsp+78h+arg_38]
0x18003486c  mov     [rax], ebp
0x18003486e  mov     rax, rbx
0x180034871  jmp     short loc_180034843
0x180034873  cmp     dword ptr [r8+4], 50504420h
0x18003487b  mov     r14d, esi
0x18003487e  jz      loc_1800346CB
0x180034884  mov     eax, 8000FFFFh
0x180034889  jmp     loc_1800346CB
0x18003488e  mov     r15, [rsp+78h+arg_28]
0x180034896  lea     rcx, [rbx+0DCh]
0x18003489d  xor     r12d, r12d
0x1800348a0  movzx   edx, word ptr [r15+44h]
0x1800348a5  lea     eax, [r12+4]
0x1800348aa  add     rdx, r15
0x1800348ad  lea     r8d, [rax+7Ch]
0x1800348b1  movups  xmm0, xmmword ptr [rdx]
0x1800348b4  movups  xmmword ptr [rcx], xmm0
0x1800348b7  movups  xmm1, xmmword ptr [rdx+10h]
0x1800348bb  movups  xmmword ptr [rcx+10h], xmm1
0x1800348bf  movups  xmm0, xmmword ptr [rdx+20h]
0x1800348c3  movups  xmmword ptr [rcx+20h], xmm0
0x1800348c7  movups  xmm1, xmmword ptr [rdx+30h]
0x1800348cb  movups  xmmword ptr [rcx+30h], xmm1
0x1800348cf  movups  xmm0, xmmword ptr [rdx+40h]
0x1800348d3  movups  xmmword ptr [rcx+40h], xmm0
0x1800348d7  movups  xmm1, xmmword ptr [rdx+50h]
0x1800348db  movups  xmmword ptr [rcx+50h], xmm1
0x1800348df  movups  xmm0, xmmword ptr [rdx+60h]
0x1800348e3  movups  xmmword ptr [rcx+60h], xmm0
0x1800348e7  movups  xmm1, xmmword ptr [rdx+70h]
0x1800348eb  add     rdx, r8
0x1800348ee  movups  xmmword ptr [rcx+70h], xmm1
0x1800348f2  add     rcx, r8
0x1800348f5  sub     rax, 1
0x1800348f9  jnz     short loc_1800348B1
0x1800348fb  movups  xmm0, xmmword ptr [rdx]
0x1800348fe  movups  xmmword ptr [rcx], xmm0
0x180034901  movups  xmm1, xmmword ptr [rdx+10h]
0x180034905  movups  xmmword ptr [rcx+10h], xmm1
0x180034909  movups  xmm0, xmmword ptr [rdx+20h]
0x18003490d  movups  xmmword ptr [rcx+20h], xmm0
0x180034911  movups  xmm1, xmmword ptr [rdx+30h]
0x180034915  movups  xmmword ptr [rcx+30h], xmm1
0x180034919  movups  xmm0, xmmword ptr [rdx+40h]
0x18003491d  movups  xmmword ptr [rcx+40h], xmm0
0x180034921  movups  xmm1, xmmword ptr [rdx+4Ch]
0x180034925  movups  xmmword ptr [rcx+4Ch], xmm1
0x180034929  jmp     loc_180034815
0x18003492e  lea     r14, [rbx+r13]
0x180034932  mov     r8, rbp; Size
0x180034935  lea     rdx, [r13+338h]
0x18003493c  add     rdx, r15; Src
0x18003493f  lea     rcx, [r14+338h]; void *
0x180034946  call    memcpy_0
0x18003494b  test    r12d, r12d
0x18003494e  jz      loc_180034864
0x180034954  mov     eax, dword ptr [rsp+78h+Size]
0x18003495b  test    ax, ax
0x18003495e  jz      loc_180034864
0x180034964  cmp     [rdi+46h], si
0x180034968  jbe     loc_180034864
0x18003496e  movzx   edx, ax
0x180034971  lea     r9, [r14+338h]; struct _OEM_DMEXTRAHEADER *
0x180034978  movzx   eax, word ptr [rdi+44h]
0x18003497c  mov     r8, rdi; struct _devicemodeW *
0x18003497f  add     rax, rdi
0x180034982  movzx   ecx, si
0x180034985  add     rcx, rax
0x180034988  mov     rax, [rsp+78h+arg_30]
0x180034990  mov     [rsp+78h+var_48], rax; __int64
0x180034995  mov     [rsp+78h+var_50], edx; int
0x180034999  mov     rdx, rbx; struct _devicemodeW *
0x18003499c  mov     [rsp+78h+var_58], rcx; struct _OEM_DMEXTRAHEADER *
0x1800349a1  mov     rcx, [rsp+78h+arg_0]; void *
0x1800349a9  call    BConvertOemPluginDevmode
0x1800349ae  test    eax, eax
0x1800349b0  jz      loc_180034832
0x1800349b6  jmp     loc_180034864
```
