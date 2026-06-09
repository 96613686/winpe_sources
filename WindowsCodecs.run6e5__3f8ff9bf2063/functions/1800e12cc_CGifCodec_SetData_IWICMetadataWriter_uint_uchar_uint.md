# CGifCodec::SetData(IWICMetadataWriter *,uint,uchar *,uint)

- ea: `0x1800e12cc`
- end: `0x1800e1382`
- name: `?SetData@CGifCodec@@IEAAJPEAUIWICMetadataWriter@@IPEAEI@Z`
- size: `182`
- prototype: `int(CGifCodec *__hidden this, struct IWICMetadataWriter *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e0b98`

## callees

- `0x1800bb784`
- `0x1800e12cc`
- `0x1800e1388`
- `0x18017b528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e1314`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e1314`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e136f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e136f`

## pseudocode

```c
__int64 __fastcall CGifCodec::SetData(CGifCodec *this, struct IWICMetadataWriter *a2, __int64 a3, unsigned __int8 *a4)
{
  bool v6; // zf
  unsigned int v7; // ebx
  int v8; // ecx
  BYTE *v9; // rax
  CGifCodec *v10; // rcx
  int v11; // eax
  struct tagPROPVARIANT Size; // [rsp+20h] [rbp-28h] BYREF

  memset(&Size, 0, sizeof(Size));
  if ( !a2 )
  {
    v6 = (_DWORD)g_doStackCaptures == 0;
    v7 = -2147024809;
    goto LABEL_3;
  }
  Size.vt = 4113;
  Size.lVal = 6;
  v9 = (BYTE *)CoTaskMemAlloc(6u);
  Size.bstrblobVal.pData = v9;
  if ( !v9 )
  {
    v6 = (_DWORD)g_doStackCaptures == 0;
    v7 = -2147024882;
LABEL_3:
    if ( !v6 )
    {
      v8 = v7;
LABEL_10:
      DoStackCapture(v8);
      goto LABEL_11;
    }
    goto LABEL_11;
  }
  memcpy_0(v9, a4, Size.ulVal);
  v11 = CGifCodec::SetData(v10, a2, 1u, &Size);
  v7 = v11;
  if ( v11 < 0 && (_DWORD)g_doStackCaptures )
  {
    v8 = v11;
    goto LABEL_10;
  }
LABEL_11:
  PropVariantClear((PROPVARIANT *)&Size);
  return v7;
}

```

## disassembly

```asm
0x1800e12cc  mov     [rsp+arg_0], rbx
0x1800e12d1  push    rdi
0x1800e12d2  sub     rsp, 40h
0x1800e12d6  xor     eax, eax
0x1800e12d8  xorps   xmm0, xmm0
0x1800e12db  mov     [rsp+48h+var_18], rax
0x1800e12e0  mov     rdi, r9
0x1800e12e3  mov     rbx, rdx
0x1800e12e6  movups  xmmword ptr [rsp+48h+Size], xmm0
0x1800e12eb  test    rdx, rdx
0x1800e12ee  jnz     short loc_1800E1301
0x1800e12f0  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800e12f6  mov     ebx, 80070057h
0x1800e12fb  jz      short loc_1800E136A
0x1800e12fd  mov     ecx, ebx
0x1800e12ff  jmp     short loc_1800E1365
0x1800e1301  mov     eax, 1011h
0x1800e1306  mov     ecx, 6; cb
0x1800e130b  mov     word ptr [rsp+48h+Size], ax
0x1800e1310  mov     dword ptr [rsp+48h+Size+8], ecx
0x1800e1314  call    cs:__imp_CoTaskMemAlloc
0x1800e131a  mov     [rsp+48h+var_18], rax
0x1800e131f  test    rax, rax
0x1800e1322  jnz     short loc_1800E1331
0x1800e1324  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800e132a  mov     ebx, 8007000Eh
0x1800e132f  jmp     short loc_1800E12FB
0x1800e1331  mov     r8d, dword ptr [rsp+48h+Size+8]; Size
0x1800e1336  mov     rdx, rdi; Src
0x1800e1339  mov     rcx, rax; void *
0x1800e133c  call    memcpy_0
0x1800e1341  lea     r9, [rsp+48h+Size]; struct tagPROPVARIANT *
0x1800e1346  mov     r8d, 1; unsigned int
0x1800e134c  mov     rdx, rbx; struct IWICMetadataWriter *
0x1800e134f  call    ?SetData@CGifCodec@@IEAAJPEAUIWICMetadataWriter@@IPEAUtagPROPVARIANT@@@Z; CGifCodec::SetData(IWICMetadataWriter *,uint,tagPROPVARIANT *)
0x1800e1354  mov     ebx, eax
0x1800e1356  test    eax, eax
0x1800e1358  jns     short loc_1800E136A
0x1800e135a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800e1361  jz      short loc_1800E136A
0x1800e1363  mov     ecx, eax; int
0x1800e1365  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800e136a  lea     rcx, [rsp+48h+Size]; pvar
0x1800e136f  call    cs:__imp_PropVariantClear
0x1800e1375  mov     eax, ebx
0x1800e1377  mov     rbx, [rsp+48h+arg_0]
0x1800e137c  add     rsp, 40h
0x1800e1380  pop     rdi
0x1800e1381  retn
```
