# CMetadataPngItxtReaderWriter::HrWriteText(IStream *,unsigned __int64,ulong *)

- ea: `0x1800d3d60`
- end: `0x1800d3f52`
- name: `?HrWriteText@CMetadataPngItxtReaderWriter@@MEAAJPEAUIStream@@_KPEAK@Z`
- size: `498`
- prototype: `int(CMetadataPngItxtReaderWriter *__hidden this, struct IStream *, unsigned __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d3670`

## callees

- `0x180025d00`
- `0x1800267d8`
- `0x18004c958`
- `0x18004ce08`
- `0x1800bb784`
- `0x1800d3b60`
- `0x1800d3d60`
- `0x1800e3c04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d3dec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d3dec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3f1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3f2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3f1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3f2e`

## pseudocode

```c
__int64 __fastcall CMetadataPngItxtReaderWriter::HrWriteText(
        CMetadataPngItxtReaderWriter *this,
        struct IStream *a2,
        SIZE_T a3,
        unsigned int *a4)
{
  unsigned __int16 *v5; // rdx
  void *v6; // rdi
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // ecx
  int v13; // r8d
  int v14; // ecx
  int v15; // eax
  unsigned int v17[2]; // [rsp+40h] [rbp-39h] BYREF
  LPVOID v18; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v19; // [rsp+58h] [rbp-21h]
  void *v20; // [rsp+60h] [rbp-19h]
  int v21; // [rsp+68h] [rbp-11h]
  LPVOID pv; // [rsp+E0h] [rbp+67h] BYREF

  *(_QWORD *)v17 = 0;
  v5 = (unsigned __int16 *)*((_QWORD *)this + 26);
  v6 = 0;
  pv = 0;
  if ( !v5 )
  {
    v11 = 0;
    LODWORD(a3) = 0;
    goto LABEL_26;
  }
  v10 = CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(
          this,
          v5,
          *((_QWORD *)this + 27),
          (char **)&pv,
          (unsigned __int64 *)v17);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_28;
    goto LABEL_4;
  }
  if ( *((_BYTE *)this + 168) == 1 )
  {
    v6 = CoTaskMemAlloc(a3);
    if ( !v6 )
    {
      v11 = -2147024882;
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_28;
      v12 = -2147024882;
      goto LABEL_9;
    }
    memset_0(&v18, 0, 0x58u);
    if ( (unsigned int)deflateInit2_((unsigned int)&v18, -1, v13, 15, 8, 0, (__int64)"1.3.1", 88)
      || (v18 = pv, v19 = v17[0], v20 = v6, v21 = a3, (unsigned int)deflate(&v18, 4) != 1)
      || v19
      || v21
      || (unsigned int)deflateEnd(&v18) )
    {
      v11 = -2003292304;
      if ( !(_DWORD)g_doStackCaptures )
      {
LABEL_27:
        CoTaskMemFree(v6);
        goto LABEL_28;
      }
      v14 = -2003292304;
LABEL_13:
      DoStackCapture(v14);
      goto LABEL_27;
    }
    v15 = WriteFullBufferToStream(a2, v6, a3);
    v11 = v15;
    if ( v15 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_27;
      v14 = v15;
      goto LABEL_13;
    }
LABEL_26:
    *a4 = a3;
    if ( !v6 )
      goto LABEL_28;
    goto LABEL_27;
  }
  LODWORD(a3) = v17[0];
  v10 = WriteFullBufferToStream(a2, pv, v17[0]);
  v11 = v10;
  if ( v10 >= 0 )
    goto LABEL_26;
  if ( (_DWORD)g_doStackCaptures )
  {
LABEL_4:
    v12 = v10;
LABEL_9:
    DoStackCapture(v12);
  }
LABEL_28:
  if ( pv )
    CoTaskMemFree(pv);
  return v11;
}

```

## disassembly

```asm
0x1800d3d60  mov     [rsp-8+arg_8], rbx
0x1800d3d65  mov     [rsp-8+arg_10], rsi
0x1800d3d6a  push    rbp
0x1800d3d6b  push    rdi
0x1800d3d6c  push    r12
0x1800d3d6e  push    r14
0x1800d3d70  push    r15
0x1800d3d72  lea     rbp, [rsp-37h]
0x1800d3d77  sub     rsp, 0B0h
0x1800d3d7e  mov     r15, rdx
0x1800d3d81  mov     qword ptr [rbp+57h+var_90], 0
0x1800d3d89  mov     rdx, [rcx+0D0h]; unsigned __int16 *
0x1800d3d90  xor     edi, edi
0x1800d3d92  mov     [rbp+57h+pv], 0
0x1800d3d9a  mov     r12, r9
0x1800d3d9d  mov     rsi, r8
0x1800d3da0  mov     r14, rcx
0x1800d3da3  test    rdx, rdx
0x1800d3da6  jz      loc_1800D3F0F
0x1800d3dac  mov     r8, [rcx+0D8h]; unsigned __int64
0x1800d3db3  lea     rax, [rbp+57h+var_90]
0x1800d3db7  lea     r9, [rbp+57h+pv]; char **
0x1800d3dbb  mov     [rsp+0D0h+var_B0], rax; unsigned __int64 *
0x1800d3dc0  call    ?ConvertWideCharToMultiByte@CMetadataPngItxtReaderWriter@@MEAAJPEAG_KPEAPEADPEA_K@Z; CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(ushort *,unsigned __int64,char * *,unsigned __int64 *)
0x1800d3dc5  mov     ebx, eax
0x1800d3dc7  test    eax, eax
0x1800d3dc9  jns     short loc_1800D3DDB
0x1800d3dcb  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d3dd1  jz      loc_1800D3F25
0x1800d3dd7  mov     ecx, eax
0x1800d3dd9  jmp     short loc_1800D3E0D
0x1800d3ddb  cmp     byte ptr [r14+0A8h], 1
0x1800d3de3  jnz     loc_1800D3EE4
0x1800d3de9  mov     rcx, rsi; cb
0x1800d3dec  call    cs:__imp_CoTaskMemAlloc
0x1800d3df2  mov     rdi, rax
0x1800d3df5  test    rax, rax
0x1800d3df8  jnz     short loc_1800D3E17
0x1800d3dfa  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d3e00  mov     ebx, 8007000Eh
0x1800d3e05  jz      loc_1800D3F25
0x1800d3e0b  mov     ecx, ebx; int
0x1800d3e0d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d3e12  jmp     loc_1800D3F25
0x1800d3e17  mov     ebx, 58h ; 'X'
0x1800d3e1c  lea     rcx, [rbp+57h+var_80]; void *
0x1800d3e20  mov     r8d, ebx; Size
0x1800d3e23  xor     edx, edx; Val
0x1800d3e25  call    memset_0
0x1800d3e2a  mov     [rsp+0D0h+var_98], ebx
0x1800d3e2e  lea     rax, a131; "1.3.1"
0x1800d3e35  mov     [rsp+0D0h+var_A0], rax
0x1800d3e3a  lea     r9d, [rbx-49h]
0x1800d3e3e  mov     [rsp+0D0h+var_A8], 0
0x1800d3e46  lea     rcx, [rbp+57h+var_80]
0x1800d3e4a  or      edx, 0FFFFFFFFh
0x1800d3e4d  mov     dword ptr [rsp+0D0h+var_B0], 8
0x1800d3e55  call    deflateInit2_
0x1800d3e5a  test    eax, eax
0x1800d3e5c  jz      short loc_1800D3E7C
0x1800d3e5e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d3e65  mov     ebx, 88982F70h
0x1800d3e6a  jz      loc_1800D3F1C
0x1800d3e70  mov     ecx, ebx; int
0x1800d3e72  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d3e77  jmp     loc_1800D3F1C
0x1800d3e7c  mov     rax, [rbp+57h+pv]
0x1800d3e80  lea     rcx, [rbp+57h+var_80]
0x1800d3e84  mov     [rbp+57h+var_80], rax
0x1800d3e88  mov     edx, 4
0x1800d3e8d  mov     eax, [rbp+57h+var_90]
0x1800d3e90  mov     [rbp+57h+var_78], eax
0x1800d3e93  mov     [rbp+57h+var_70], rdi
0x1800d3e97  mov     [rbp+57h+var_68], esi
0x1800d3e9a  call    deflate
0x1800d3e9f  cmp     eax, 1
0x1800d3ea2  jnz     short loc_1800D3E5E
0x1800d3ea4  cmp     [rbp+57h+var_78], 0
0x1800d3ea8  jnz     short loc_1800D3E5E
0x1800d3eaa  cmp     [rbp+57h+var_68], 0
0x1800d3eae  jnz     short loc_1800D3E5E
0x1800d3eb0  lea     rcx, [rbp+57h+var_80]
0x1800d3eb4  call    deflateEnd
0x1800d3eb9  test    eax, eax
0x1800d3ebb  jnz     short loc_1800D3E5E
0x1800d3ebd  mov     r8d, esi; unsigned int
0x1800d3ec0  mov     rdx, rdi; void *
0x1800d3ec3  mov     rcx, r15; struct IStream *
0x1800d3ec6  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800d3ecb  mov     ebx, eax
0x1800d3ecd  test    eax, eax
0x1800d3ecf  jns     short loc_1800D3F13
0x1800d3ed1  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d3ed8  jz      short loc_1800D3EDE
0x1800d3eda  mov     ecx, eax
0x1800d3edc  jmp     short loc_1800D3E72
0x1800d3ede  test    eax, eax
0x1800d3ee0  js      short loc_1800D3F1C
0x1800d3ee2  jmp     short loc_1800D3F13
0x1800d3ee4  mov     rsi, qword ptr [rbp+57h+var_90]
0x1800d3ee8  mov     rcx, r15; struct IStream *
0x1800d3eeb  mov     rdx, [rbp+57h+pv]; void *
0x1800d3eef  mov     r8d, esi; unsigned int
0x1800d3ef2  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800d3ef7  mov     ebx, eax
0x1800d3ef9  test    eax, eax
0x1800d3efb  jns     short loc_1800D3F13
0x1800d3efd  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d3f03  jnz     loc_1800D3DD7
0x1800d3f09  test    eax, eax
0x1800d3f0b  js      short loc_1800D3F25
0x1800d3f0d  jmp     short loc_1800D3F13
0x1800d3f0f  xor     ebx, ebx
0x1800d3f11  xor     esi, esi
0x1800d3f13  mov     [r12], esi
0x1800d3f17  test    rdi, rdi
0x1800d3f1a  jz      short loc_1800D3F25
0x1800d3f1c  mov     rcx, rdi; pv
0x1800d3f1f  call    cs:__imp_CoTaskMemFree
0x1800d3f25  mov     rcx, [rbp+57h+pv]; pv
0x1800d3f29  test    rcx, rcx
0x1800d3f2c  jz      short loc_1800D3F34
0x1800d3f2e  call    cs:__imp_CoTaskMemFree
0x1800d3f34  lea     r11, [rsp+0D0h+var_20]
0x1800d3f3c  mov     eax, ebx
0x1800d3f3e  mov     rbx, [r11+38h]
0x1800d3f42  mov     rsi, [r11+40h]
0x1800d3f46  mov     rsp, r11
0x1800d3f49  pop     r15
0x1800d3f4b  pop     r14
0x1800d3f4d  pop     r12
0x1800d3f4f  pop     rdi
0x1800d3f50  pop     rbp
0x1800d3f51  retn
```
