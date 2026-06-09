# CMetadataPngIccpReaderWriter::HrWriteProfileData(IStream *,unsigned __int64,ulong *)

- ea: `0x1800cbac0`
- end: `0x1800cbbfa`
- name: `?HrWriteProfileData@CMetadataPngIccpReaderWriter@@MEAAJPEAUIStream@@_KPEAK@Z`
- size: `314`
- prototype: `int(CMetadataPngIccpReaderWriter *__hidden this, struct IStream *, unsigned __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cb880`

## callees

- `0x180025d00`
- `0x1800267d8`
- `0x18004c958`
- `0x18004ce08`
- `0x1800bb784`
- `0x1800cbac0`
- `0x1800e3c04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cbadd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cbadd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cbbe4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cbbe4`

## pseudocode

```c
__int64 __fastcall CMetadataPngIccpReaderWriter::HrWriteProfileData(
        CMetadataPngIccpReaderWriter *this,
        struct IStream *a2,
        SIZE_T a3,
        unsigned int *a4)
{
  unsigned int v6; // edi
  void *v8; // rsi
  unsigned int v9; // ebx
  int v10; // r8d
  int v11; // eax
  int v12; // ecx
  __int64 v14; // [rsp+40h] [rbp-88h] BYREF
  int v15; // [rsp+48h] [rbp-80h]
  void *v16; // [rsp+50h] [rbp-78h]
  unsigned int v17; // [rsp+58h] [rbp-70h]

  v6 = a3;
  v8 = CoTaskMemAlloc(a3);
  if ( v8 )
  {
    memset_0(&v14, 0, 0x58u);
    if ( (unsigned int)deflateInit2_((unsigned int)&v14, -1, v10, 15, 8, 0, (__int64)"1.3.1", 88)
      || (v14 = *((_QWORD *)this + 21),
          v15 = *((_DWORD *)this + 44),
          v16 = v8,
          v17 = v6,
          (unsigned int)deflate(&v14, 4) != 1)
      || v15
      || v17
      || (unsigned int)deflateEnd(&v14) )
    {
      v9 = -2003292304;
      if ( (_DWORD)g_doStackCaptures )
      {
        v12 = -2003292304;
LABEL_16:
        DoStackCapture(v12);
      }
    }
    else
    {
      v11 = WriteFullBufferToStream(a2, v8, v6);
      v9 = v11;
      if ( v11 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_17;
        v12 = v11;
        goto LABEL_16;
      }
      *a4 = v6;
    }
LABEL_17:
    CoTaskMemFree(v8);
    return v9;
  }
  v9 = -2147024882;
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(-2147024882);
  return v9;
}

```

## disassembly

```asm
0x1800cbac0  push    rbx
0x1800cbac2  push    rbp
0x1800cbac3  push    rsi
0x1800cbac4  push    rdi
0x1800cbac5  push    r14
0x1800cbac7  sub     rsp, 0A0h
0x1800cbace  mov     rbx, rcx
0x1800cbad1  mov     r14, r9
0x1800cbad4  mov     rcx, r8; cb
0x1800cbad7  mov     rdi, r8
0x1800cbada  mov     rbp, rdx
0x1800cbadd  call    cs:__imp_CoTaskMemAlloc
0x1800cbae3  mov     rsi, rax
0x1800cbae6  test    rax, rax
0x1800cbae9  jnz     short loc_1800CBB08
0x1800cbaeb  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800cbaf1  mov     ebx, 8007000Eh
0x1800cbaf6  jz      loc_1800CBBEA
0x1800cbafc  mov     ecx, ebx; int
0x1800cbafe  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800cbb03  jmp     loc_1800CBBEA
0x1800cbb08  xor     edx, edx; Val
0x1800cbb0a  lea     rcx, [rsp+0C8h+var_88]; void *
0x1800cbb0f  lea     r8d, [rdx+58h]; Size
0x1800cbb13  call    memset_0
0x1800cbb18  mov     [rsp+0C8h+var_90], 58h ; 'X'
0x1800cbb20  lea     rax, a131; "1.3.1"
0x1800cbb27  mov     [rsp+0C8h+var_98], rax
0x1800cbb2c  lea     rcx, [rsp+0C8h+var_88]
0x1800cbb31  mov     [rsp+0C8h+var_A0], 0
0x1800cbb39  mov     r9d, 0Fh
0x1800cbb3f  or      edx, 0FFFFFFFFh
0x1800cbb42  mov     [rsp+0C8h+var_A8], 8
0x1800cbb4a  call    deflateInit2_
0x1800cbb4f  test    eax, eax
0x1800cbb51  jnz     short loc_1800CBBCC
0x1800cbb53  mov     rax, [rbx+0A8h]
0x1800cbb5a  lea     rcx, [rsp+0C8h+var_88]
0x1800cbb5f  mov     [rsp+0C8h+var_88], rax
0x1800cbb64  mov     edx, 4
0x1800cbb69  mov     eax, [rbx+0B0h]
0x1800cbb6f  mov     [rsp+0C8h+var_80], eax
0x1800cbb73  mov     [rsp+0C8h+var_78], rsi
0x1800cbb78  mov     [rsp+0C8h+var_70], edi
0x1800cbb7c  call    deflate
0x1800cbb81  cmp     eax, 1
0x1800cbb84  jnz     short loc_1800CBBCC
0x1800cbb86  cmp     [rsp+0C8h+var_80], 0
0x1800cbb8b  jnz     short loc_1800CBBCC
0x1800cbb8d  cmp     [rsp+0C8h+var_70], 0
0x1800cbb92  jnz     short loc_1800CBBCC
0x1800cbb94  lea     rcx, [rsp+0C8h+var_88]
0x1800cbb99  call    deflateEnd
0x1800cbb9e  test    eax, eax
0x1800cbba0  jnz     short loc_1800CBBCC
0x1800cbba2  mov     r8d, edi; unsigned int
0x1800cbba5  mov     rdx, rsi; void *
0x1800cbba8  mov     rcx, rbp; struct IStream *
0x1800cbbab  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800cbbb0  mov     ebx, eax
0x1800cbbb2  test    eax, eax
0x1800cbbb4  jns     short loc_1800CBBC7
0x1800cbbb6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800cbbbd  jz      short loc_1800CBBC3
0x1800cbbbf  mov     ecx, eax
0x1800cbbc1  jmp     short loc_1800CBBDC
0x1800cbbc3  test    eax, eax
0x1800cbbc5  js      short loc_1800CBBE1
0x1800cbbc7  mov     [r14], edi
0x1800cbbca  jmp     short loc_1800CBBE1
0x1800cbbcc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800cbbd3  mov     ebx, 88982F70h
0x1800cbbd8  jz      short loc_1800CBBE1
0x1800cbbda  mov     ecx, ebx; int
0x1800cbbdc  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800cbbe1  mov     rcx, rsi; pv
0x1800cbbe4  call    cs:__imp_CoTaskMemFree
0x1800cbbea  mov     eax, ebx
0x1800cbbec  add     rsp, 0A0h
0x1800cbbf3  pop     r14
0x1800cbbf5  pop     rdi
0x1800cbbf6  pop     rsi
0x1800cbbf7  pop     rbp
0x1800cbbf8  pop     rbx
0x1800cbbf9  retn
```
