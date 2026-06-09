# PConvertToCurrentVersionDevmodeWithOemPlugins(void *,ulong,_RAWBINARYDATA *,ulong,_devicemodeW *,_devicemodeW *,_OEM_PLUGINS *,ulong *)

- ea: `0x18003005c`
- end: `0x1800303e6`
- name: `?PConvertToCurrentVersionDevmodeWithOemPlugins@@YAPEAU_devicemodeW@@PEAXKPEAU_RAWBINARYDATA@@KPEAU1@2PEAU_OEM_PLUGINS@@PEAK@Z`
- size: `906`
- prototype: `struct _devicemodeW *__fastcall(void *, unsigned int, struct _RAWBINARYDATA *, unsigned int, struct _devicemodeW *Src, struct _devicemodeW *, struct _OEM_PLUGINS *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180030a2c`

## callees

- `0x18003005c`
- `0x1800303ec`
- `0x180030650`
- `0x1800307cc`
- `0x18005c1e0`
- `0x18005c434`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800303c6`
- `KERNEL32!LocalFree` at `0x1800303c6`
- `KERNEL32!LocalAlloc` at `0x18003011c`
- `KERNEL32!LocalAlloc` at `0x18003011c`

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
  int v10; // r9d
  int v11; // eax
  unsigned int v12; // eax
  size_t v13; // rbp
  struct _devicemodeW *v14; // rax
  struct _devicemodeW *v15; // rbx
  struct _devicemodeW *v16; // rsi
  int v17; // r12d
  int v18; // r15d
  size_t dmSize; // r8
  __int64 v20; // r9
  unsigned int dmDriverExtra; // edi
  unsigned __int16 *v22; // r9
  struct _devicemodeW *v23; // r13
  int v24; // edx
  int v25; // eax
  unsigned __int16 v26; // ax
  struct _devicemodeW *v27; // rcx
  __int64 v28; // rdx
  _OWORD *v29; // rax
  __int128 v30; // xmm1
  char *v31; // r14
  size_t Size; // [rsp+98h] [rbp+20h] BYREF

  LODWORD(Size) = 0;
  *a8 = 0;
  if ( !a3 )
    return 0;
  v10 = 0;
  if ( *((_DWORD *)a3 + 1) == 1196442656 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    if ( *((_DWORD *)a3 + 1) != 1347437600 )
      v10 = -2147418113;
  }
  if ( v10 < 0 )
    return 0;
  if ( v11 )
    return 0;
  if ( !(unsigned int)BCalcTotalOEMDMSize(a1, a7, &Size) )
    return 0;
  v12 = a2 + 976;
  if ( a2 >= 0xFFFFFC30 )
    return 0;
  v13 = (unsigned int)Size;
  if ( v12 + (unsigned int)Size < v12 )
    return 0;
  v14 = (struct _devicemodeW *)LocalAlloc(0x40u, v12 + (unsigned int)Size);
  v15 = v14;
  if ( !v14 )
    return 0;
  v16 = Src;
  v17 = 0;
  v18 = 0;
  dmSize = 220;
  if ( Src->dmSize <= 0xDCu )
    dmSize = Src->dmSize;
  memcpy_0(v14, Src, dmSize);
  v15->dmSpecVersion = 1025;
  v15->dmSize = 220;
  v20 = v16->dmSize;
  dmDriverExtra = v16->dmDriverExtra;
  LODWORD(Size) = 0;
  v22 = (WCHAR *)((char *)v16->dmDeviceName + v20);
  if ( v22 && dmDriverExtra >= 4 && *(_DWORD *)v22 == 1431193924 )
    v18 = 1;
  v23 = a6;
  if ( v16->dmDriverVersion >= 0x501u )
  {
    if ( (unsigned __int16)dmDriverExtra >= 0x2C4u && *(_DWORD *)v22 == 1447645776 )
    {
      v24 = v22[57];
      v25 = v22[74];
      LOWORD(Size) = v22[74];
      if ( (unsigned __int16)v24 >= 0x2C4u && v24 + v25 <= dmDriverExtra )
      {
        if ( (unsigned __int16)dmDriverExtra > (unsigned __int16)v24 )
          LOWORD(dmDriverExtra) = v24;
        v26 = 756;
        v17 = 1;
        if ( (unsigned __int16)dmDriverExtra > 0x2F4u )
          goto LABEL_31;
        goto LABEL_30;
      }
    }
LABEL_33:
    v27 = v15 + 1;
    v28 = 5;
    v29 = (_OWORD *)((char *)a6->dmDeviceName + a6->dmSize);
    do
    {
      *(_OWORD *)v27->dmDeviceName = *v29;
      *(_OWORD *)&v27->dmDeviceName[8] = v29[1];
      *(_OWORD *)&v27->dmDeviceName[16] = v29[2];
      *(_OWORD *)&v27->dmDeviceName[24] = v29[3];
      *(_OWORD *)&v27->dmSpecVersion = v29[4];
      *(union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C *)((char *)&v27->76 + 4) = (union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C)v29[5];
      *(_OWORD *)&v27->dmYResolution = v29[6];
      v30 = v29[7];
      v29 += 8;
      *(_OWORD *)&v27->dmFormName[5] = v30;
      v27 = (struct _devicemodeW *)((char *)v27 + 128);
      --v28;
    }
    while ( v28 );
    *(_OWORD *)v27->dmDeviceName = *v29;
    *(_OWORD *)&v27->dmDeviceName[8] = v29[1];
    *(_OWORD *)&v27->dmDeviceName[16] = v29[2];
    *(_OWORD *)&v27->dmDeviceName[24] = v29[3];
    *(_OWORD *)&v27->dmSpecVersion = v29[4];
    *(union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C *)((char *)&v27->76 + 4) = (union _devicemodeW::$5A39A2C3BB0B1D2D5888DFEE2BA0B23C)v29[5];
    *(_OWORD *)&v27->dmYResolution = v29[6];
    *(_DWORD *)&v27->dmFormName[5] = *((_DWORD *)v29 + 28);
    goto LABEL_36;
  }
  if ( v16->dmDriverVersion != 1024 || (_WORD)dmDriverExtra != 180 || *(_DWORD *)v22 != 1447645776 )
    goto LABEL_33;
LABEL_30:
  v26 = dmDriverExtra;
LABEL_31:
  memcpy_0(&v15[1], v22, v26);
  if ( v17 )
    ValidateDocOptions(a3, (char *)&v15->dmMediaType + v15->dmSize);
LABEL_36:
  v15->dmDriverVersion = 1539;
  if ( v18 )
  {
    if ( v15->dmMediaType >= 0x100 )
      v15->dmMediaType = 1;
LABEL_40:
    if ( !(_DWORD)v13
      || (v31 = (char *)v15 + a2, memcpy_0(v31 + 976, (char *)&v23[4].dmYResolution + a2, v13), !v17)
      || !(_WORD)Size
      || v16->dmDriverExtra <= (unsigned __int16)dmDriverExtra
      || (unsigned int)BConvertOemPluginDevmode(
                         a1,
                         v15,
                         v16,
                         (struct _OEM_DMEXTRAHEADER *)(v31 + 976),
                         (struct _OEM_DMEXTRAHEADER *)((char *)v16 + (unsigned __int16)dmDriverExtra + v16->dmSize),
                         (unsigned __int16)Size,
                         (__int64)a7) )
    {
      *a8 = v13;
      return v15;
    }
    goto LABEL_46;
  }
  if ( (int)PatchDevmodeSizeFieldsAndJTHdr(v27, v15, a2, v13, 0) >= 0 )
    goto LABEL_40;
LABEL_46:
  LocalFree(v15);
  return 0;
}

```

## disassembly

```asm
0x18003005c  mov     rax, rsp
0x18003005f  mov     [rax+18h], rbx
0x180030063  mov     [rax+20h], r9d
0x180030067  mov     [rax+10h], edx
0x18003006a  mov     [rax+8], rcx
0x18003006e  push    rbp
0x18003006f  push    rsi
0x180030070  push    rdi
0x180030071  push    r12
0x180030073  push    r13
0x180030075  push    r14
0x180030077  push    r15
0x180030079  sub     rsp, 40h
0x18003007d  xor     r13d, r13d
0x180030080  mov     r14, r8
0x180030083  mov     [rax+20h], r13d
0x180030087  mov     ebx, edx
0x180030089  mov     rax, [rsp+78h+arg_38]
0x180030091  mov     [rax], r13d
0x180030094  test    r8, r8
0x180030097  jz      loc_1800303CC
0x18003009d  cmp     dword ptr [r8+4], 47504420h
0x1800300a5  mov     r9d, r13d
0x1800300a8  jz      short loc_1800300BF
0x1800300aa  cmp     dword ptr [r8+4], 50504420h
0x1800300b2  mov     eax, r13d
0x1800300b5  jz      short loc_1800300C4
0x1800300b7  mov     r9d, 8000FFFFh
0x1800300bd  jmp     short loc_1800300C4
0x1800300bf  mov     eax, 1
0x1800300c4  test    r9d, r9d
0x1800300c7  js      loc_1800303CC
0x1800300cd  test    eax, eax
0x1800300cf  jnz     loc_1800303CC
0x1800300d5  mov     rdx, [rsp+78h+arg_30]
0x1800300dd  lea     r8, [rsp+78h+Size]
0x1800300e5  call    BCalcTotalOEMDMSize
0x1800300ea  test    eax, eax
0x1800300ec  jz      loc_1800303CC
0x1800300f2  lea     eax, [rbx+3D0h]
0x1800300f8  cmp     eax, 3D0h
0x1800300fd  jb      loc_1800303CC
0x180030103  mov     ebp, dword ptr [rsp+78h+Size]
0x18003010a  lea     ecx, [rax+rbp]
0x18003010d  cmp     ecx, eax
0x18003010f  jb      loc_1800303CC
0x180030115  mov     edx, ecx; uBytes
0x180030117  mov     ecx, 40h ; '@'; uFlags
0x18003011c  call    cs:__imp_LocalAlloc
0x180030122  mov     rbx, rax
0x180030125  test    rax, rax
0x180030128  jz      loc_1800303CC
0x18003012e  mov     rsi, [rsp+78h+Src]
0x180030136  mov     edi, 0DCh
0x18003013b  mov     r12d, r13d
0x18003013e  mov     r15d, r13d
0x180030141  mov     r8d, edi
0x180030144  cmp     di, [rsi+44h]
0x180030148  jb      short loc_18003014F
0x18003014a  movzx   r8d, word ptr [rsi+44h]; Size
0x18003014f  mov     rdx, rsi; Src
0x180030152  mov     rcx, rbx; void *
0x180030155  call    memcpy_0
0x18003015a  mov     word ptr [rbx+40h], 401h
0x180030160  mov     r8d, 1
0x180030166  mov     [rbx+44h], di
0x18003016a  movzx   r9d, word ptr [rsi+44h]
0x18003016f  movzx   edi, word ptr [rsi+46h]
0x180030173  mov     dword ptr [rsp+78h+Size], r13d
0x18003017b  add     r9, rsi
0x18003017e  jz      short loc_180030190
0x180030180  cmp     edi, 4
0x180030183  jb      short loc_180030190
0x180030185  cmp     dword ptr [r9], 554E4944h
0x18003018c  cmovz   r15d, r8d
0x180030190  mov     r13, [rsp+78h+arg_28]
0x180030198  mov     eax, 501h
0x18003019d  cmp     [rsi+42h], ax
0x1800301a1  jb      short loc_1800301F6
0x1800301a3  mov     ecx, 2C4h
0x1800301a8  cmp     di, cx
0x1800301ab  jb      loc_18003024E
0x1800301b1  cmp     dword ptr [r9], 56495250h
0x1800301b8  jnz     loc_18003024E
0x1800301be  movzx   edx, word ptr [r9+72h]
0x1800301c3  movzx   eax, word ptr [r9+94h]
0x1800301cb  mov     word ptr [rsp+78h+Size], ax
0x1800301d3  cmp     dx, cx
0x1800301d6  jb      short loc_18003024E
0x1800301d8  lea     ecx, [rdx+rax]
0x1800301db  cmp     ecx, edi
0x1800301dd  ja      short loc_18003024E
0x1800301df  cmp     di, dx
0x1800301e2  jbe     short loc_1800301E7
0x1800301e4  movzx   edi, dx
0x1800301e7  mov     eax, 2F4h
0x1800301ec  mov     r12d, r8d
0x1800301ef  cmp     ax, di
0x1800301f2  jnb     short loc_180030214
0x1800301f4  jmp     short loc_180030217
0x1800301f6  mov     eax, 400h
0x1800301fb  cmp     [rsi+42h], ax
0x1800301ff  jnz     short loc_18003024E
0x180030201  mov     eax, 0B4h
0x180030206  cmp     di, ax
0x180030209  jnz     short loc_18003024E
0x18003020b  cmp     dword ptr [r9], 56495250h
0x180030212  jnz     short loc_18003024E
0x180030214  movzx   eax, di
0x180030217  movzx   r8d, ax; Size
0x18003021b  lea     rcx, [rbx+0DCh]; void *
0x180030222  mov     rdx, r9; Src
0x180030225  call    memcpy_0
0x18003022a  test    r12d, r12d
0x18003022d  jz      loc_1800302EC
0x180030233  movzx   edx, word ptr [rbx+44h]
0x180030237  mov     rcx, r14
0x18003023a  add     rdx, 0C4h
0x180030241  add     rdx, rbx
0x180030244  call    ValidateDocOptions
0x180030249  jmp     loc_1800302EC
0x18003024e  movzx   eax, word ptr [r13+44h]
0x180030253  lea     rcx, [rbx+0DCh]
0x18003025a  mov     edx, 5
0x18003025f  add     rax, r13
0x180030262  lea     r8d, [rdx+7Bh]
0x180030266  movups  xmm0, xmmword ptr [rax]
0x180030269  movups  xmmword ptr [rcx], xmm0
0x18003026c  movups  xmm1, xmmword ptr [rax+10h]
0x180030270  movups  xmmword ptr [rcx+10h], xmm1
0x180030274  movups  xmm0, xmmword ptr [rax+20h]
0x180030278  movups  xmmword ptr [rcx+20h], xmm0
0x18003027c  movups  xmm1, xmmword ptr [rax+30h]
0x180030280  movups  xmmword ptr [rcx+30h], xmm1
0x180030284  movups  xmm0, xmmword ptr [rax+40h]
0x180030288  movups  xmmword ptr [rcx+40h], xmm0
0x18003028c  movups  xmm1, xmmword ptr [rax+50h]
0x180030290  movups  xmmword ptr [rcx+50h], xmm1
0x180030294  movups  xmm0, xmmword ptr [rax+60h]
0x180030298  movups  xmmword ptr [rcx+60h], xmm0
0x18003029c  movups  xmm1, xmmword ptr [rax+70h]
0x1800302a0  add     rax, r8
0x1800302a3  movups  xmmword ptr [rcx+70h], xmm1
0x1800302a7  add     rcx, r8; void *
0x1800302aa  sub     rdx, 1
0x1800302ae  jnz     short loc_180030266
0x1800302b0  movups  xmm0, xmmword ptr [rax]
0x1800302b3  movups  xmmword ptr [rcx], xmm0
0x1800302b6  movups  xmm1, xmmword ptr [rax+10h]
0x1800302ba  movups  xmmword ptr [rcx+10h], xmm1
0x1800302be  movups  xmm0, xmmword ptr [rax+20h]
0x1800302c2  movups  xmmword ptr [rcx+20h], xmm0
0x1800302c6  movups  xmm1, xmmword ptr [rax+30h]
0x1800302ca  movups  xmmword ptr [rcx+30h], xmm1
0x1800302ce  movups  xmm0, xmmword ptr [rax+40h]
0x1800302d2  movups  xmmword ptr [rcx+40h], xmm0
0x1800302d6  movups  xmm1, xmmword ptr [rax+50h]
0x1800302da  movups  xmmword ptr [rcx+50h], xmm1
0x1800302de  movups  xmm0, xmmword ptr [rax+60h]
0x1800302e2  movups  xmmword ptr [rcx+60h], xmm0
0x1800302e6  mov     eax, [rax+70h]
0x1800302e9  mov     [rcx+70h], eax
0x1800302ec  mov     r14d, [rsp+78h+arg_8]
0x1800302f4  mov     word ptr [rbx+42h], 603h
0x1800302fa  test    r15d, r15d
0x1800302fd  jz      short loc_180030317
0x1800302ff  cmp     dword ptr [rbx+0C4h], 100h
0x180030309  jb      short loc_180030335
0x18003030b  mov     dword ptr [rbx+0C4h], 1
0x180030315  jmp     short loc_180030335
0x180030317  xor     r15d, r15d
0x18003031a  mov     r9d, ebp; unsigned int
0x18003031d  mov     r8d, r14d; unsigned int
0x180030320  mov     dword ptr [rsp+78h+var_58], r15d; int
0x180030325  mov     rdx, rbx; struct _devicemodeW *
0x180030328  call    ?PatchDevmodeSizeFieldsAndJTHdr@@YAJPEAXPEAU_devicemodeW@@KKH@Z; PatchDevmodeSizeFieldsAndJTHdr(void *,_devicemodeW *,ulong,ulong,int)
0x18003032d  test    eax, eax
0x18003032f  js      loc_1800303C3
0x180030335  test    ebp, ebp
0x180030337  jz      short loc_1800303B4
0x180030339  mov     eax, r14d
0x18003033c  lea     rdx, [r13+3D0h]
0x180030343  mov     r8, rbp; Size
0x180030346  add     rdx, rax; Src
0x180030349  lea     r14, [rax+rbx]
0x18003034d  lea     rcx, [r14+3D0h]; void *
0x180030354  call    memcpy_0
0x180030359  test    r12d, r12d
0x18003035c  jz      short loc_1800303B4
0x18003035e  mov     eax, dword ptr [rsp+78h+Size]
0x180030365  test    ax, ax
0x180030368  jz      short loc_1800303B4
0x18003036a  cmp     [rsi+46h], di
0x18003036e  jbe     short loc_1800303B4
0x180030370  movzx   ecx, word ptr [rsi+44h]
0x180030374  lea     r9, [r14+3D0h]; struct _OEM_DMEXTRAHEADER *
0x18003037b  movzx   edx, ax
0x18003037e  mov     r8, rsi; struct _devicemodeW *
0x180030381  movzx   eax, di
0x180030384  add     rax, rsi
0x180030387  add     rcx, rax
0x18003038a  mov     rax, [rsp+78h+arg_30]
0x180030392  mov     [rsp+78h+var_48], rax; __int64
0x180030397  mov     [rsp+78h+var_50], edx; int
0x18003039b  mov     rdx, rbx; struct _devicemodeW *
0x18003039e  mov     [rsp+78h+var_58], rcx; struct _OEM_DMEXTRAHEADER *
0x1800303a3  mov     rcx, [rsp+78h+arg_0]; void *
0x1800303ab  call    BConvertOemPluginDevmode
0x1800303b0  test    eax, eax
0x1800303b2  jz      short loc_1800303C3
0x1800303b4  mov     rax, [rsp+78h+arg_38]
0x1800303bc  mov     [rax], ebp
0x1800303be  mov     rax, rbx
0x1800303c1  jmp     short loc_1800303CE
0x1800303c3  mov     rcx, rbx; hMem
0x1800303c6  call    cs:__imp_LocalFree
0x1800303cc  xor     eax, eax
0x1800303ce  mov     rbx, [rsp+78h+arg_10]
0x1800303d6  add     rsp, 40h
0x1800303da  pop     r15
0x1800303dc  pop     r14
0x1800303de  pop     r13
0x1800303e0  pop     r12
0x1800303e2  pop     rdi
0x1800303e3  pop     rsi
0x1800303e4  pop     rbp
0x1800303e5  retn
```
