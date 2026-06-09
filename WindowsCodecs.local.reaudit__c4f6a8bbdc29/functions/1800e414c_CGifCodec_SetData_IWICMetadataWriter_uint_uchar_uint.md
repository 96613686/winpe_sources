# CGifCodec::SetData(IWICMetadataWriter *,uint,uchar *,uint)

- ea: `0x1800e414c`
- end: `0x1800e420f`
- name: `?SetData@CGifCodec@@IEAAJPEAUIWICMetadataWriter@@IPEAEI@Z`
- size: `195`
- prototype: `int(CGifCodec *__hidden this, struct IWICMetadataWriter *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e39f8`

## callees

- `0x1800bd9d4`
- `0x1800e414c`
- `0x1800e4218`
- `0x18017e438`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e4194`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e4194`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e41f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e41f5`

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
0x1800e414c  mov     [rsp+arg_0], rbx
0x1800e4151  push    rdi
0x1800e4152  sub     rsp, 40h
0x1800e4156  xor     eax, eax
0x1800e4158  xorps   xmm0, xmm0
0x1800e415b  mov     [rsp+48h+var_18], rax
0x1800e4160  mov     rdi, r9
0x1800e4163  mov     rbx, rdx
0x1800e4166  movups  xmmword ptr [rsp+48h+Size], xmm0
0x1800e416b  test    rdx, rdx
0x1800e416e  jnz     short loc_1800E4181
0x1800e4170  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800e4176  mov     ebx, 80070057h
0x1800e417b  jz      short loc_1800E41F0
0x1800e417d  mov     ecx, ebx
0x1800e417f  jmp     short loc_1800E41EB
0x1800e4181  mov     eax, 1011h
0x1800e4186  mov     ecx, 6; cb
0x1800e418b  mov     word ptr [rsp+48h+Size], ax
0x1800e4190  mov     dword ptr [rsp+48h+Size+8], ecx
0x1800e4194  call    cs:__imp_CoTaskMemAlloc
0x1800e419b  nop     dword ptr [rax+rax+00h]
0x1800e41a0  mov     [rsp+48h+var_18], rax
0x1800e41a5  test    rax, rax
0x1800e41a8  jnz     short loc_1800E41B7
0x1800e41aa  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800e41b0  mov     ebx, 8007000Eh
0x1800e41b5  jmp     short loc_1800E417B
0x1800e41b7  mov     r8d, dword ptr [rsp+48h+Size+8]; Size
0x1800e41bc  mov     rdx, rdi; Src
0x1800e41bf  mov     rcx, rax; void *
0x1800e41c2  call    memcpy_0
0x1800e41c7  lea     r9, [rsp+48h+Size]; struct tagPROPVARIANT *
0x1800e41cc  mov     r8d, 1; unsigned int
0x1800e41d2  mov     rdx, rbx; struct IWICMetadataWriter *
0x1800e41d5  call    ?SetData@CGifCodec@@IEAAJPEAUIWICMetadataWriter@@IPEAUtagPROPVARIANT@@@Z; CGifCodec::SetData(IWICMetadataWriter *,uint,tagPROPVARIANT *)
0x1800e41da  mov     ebx, eax
0x1800e41dc  test    eax, eax
0x1800e41de  jns     short loc_1800E41F0
0x1800e41e0  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800e41e7  jz      short loc_1800E41F0
0x1800e41e9  mov     ecx, eax; int
0x1800e41eb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800e41f0  lea     rcx, [rsp+48h+Size]; pvar
0x1800e41f5  call    cs:__imp_PropVariantClear
0x1800e41fc  nop     dword ptr [rax+rax+00h]
0x1800e4201  mov     eax, ebx
0x1800e4203  mov     rbx, [rsp+48h+arg_0]
0x1800e4208  add     rsp, 40h
0x1800e420c  pop     rdi
0x1800e420d  retn
```
