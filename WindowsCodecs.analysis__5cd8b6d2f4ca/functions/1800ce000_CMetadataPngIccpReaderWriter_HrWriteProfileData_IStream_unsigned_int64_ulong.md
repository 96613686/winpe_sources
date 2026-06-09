# CMetadataPngIccpReaderWriter::HrWriteProfileData(IStream *,unsigned __int64,ulong *)

- ea: `0x1800ce000`
- end: `0x1800ce147`
- name: `?HrWriteProfileData@CMetadataPngIccpReaderWriter@@MEAAJPEAUIStream@@_KPEAK@Z`
- size: `327`
- prototype: `__int64 __fastcall(CMetadataPngIccpReaderWriter *this, struct IStream *, SIZE_T, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cddc0`

## callees

- `0x18001e0b4`
- `0x18001e570`
- `0x180055dbc`
- `0x180056898`
- `0x1800bd9d4`
- `0x1800ce000`
- `0x1800e6af4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce01d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce01d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce12a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce12a`

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
0x1800ce000  push    rbx
0x1800ce002  push    rbp
0x1800ce003  push    rsi
0x1800ce004  push    rdi
0x1800ce005  push    r14
0x1800ce007  sub     rsp, 0A0h
0x1800ce00e  mov     rbx, rcx
0x1800ce011  mov     r14, r9
0x1800ce014  mov     rcx, r8; cb
0x1800ce017  mov     rdi, r8
0x1800ce01a  mov     rbp, rdx
0x1800ce01d  call    cs:__imp_CoTaskMemAlloc
0x1800ce024  nop     dword ptr [rax+rax+00h]
0x1800ce029  mov     rsi, rax
0x1800ce02c  test    rax, rax
0x1800ce02f  jnz     short loc_1800CE04E
0x1800ce031  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800ce037  mov     ebx, 8007000Eh
0x1800ce03c  jz      loc_1800CE136
0x1800ce042  mov     ecx, ebx; int
0x1800ce044  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800ce049  jmp     loc_1800CE136
0x1800ce04e  xor     edx, edx; Val
0x1800ce050  lea     rcx, [rsp+0C8h+var_88]; void *
0x1800ce055  lea     r8d, [rdx+58h]; Size
0x1800ce059  call    memset_0
0x1800ce05e  mov     [rsp+0C8h+var_90], 58h ; 'X'
0x1800ce066  lea     rax, a131; "1.3.1"
0x1800ce06d  mov     [rsp+0C8h+var_98], rax
0x1800ce072  lea     rcx, [rsp+0C8h+var_88]
0x1800ce077  mov     [rsp+0C8h+var_A0], 0
0x1800ce07f  mov     r9d, 0Fh
0x1800ce085  or      edx, 0FFFFFFFFh
0x1800ce088  mov     [rsp+0C8h+var_A8], 8
0x1800ce090  call    deflateInit2_
0x1800ce095  test    eax, eax
0x1800ce097  jnz     short loc_1800CE112
0x1800ce099  mov     rax, [rbx+0A8h]
0x1800ce0a0  lea     rcx, [rsp+0C8h+var_88]
0x1800ce0a5  mov     [rsp+0C8h+var_88], rax
0x1800ce0aa  mov     edx, 4
0x1800ce0af  mov     eax, [rbx+0B0h]
0x1800ce0b5  mov     [rsp+0C8h+var_80], eax
0x1800ce0b9  mov     [rsp+0C8h+var_78], rsi
0x1800ce0be  mov     [rsp+0C8h+var_70], edi
0x1800ce0c2  call    deflate
0x1800ce0c7  cmp     eax, 1
0x1800ce0ca  jnz     short loc_1800CE112
0x1800ce0cc  cmp     [rsp+0C8h+var_80], 0
0x1800ce0d1  jnz     short loc_1800CE112
0x1800ce0d3  cmp     [rsp+0C8h+var_70], 0
0x1800ce0d8  jnz     short loc_1800CE112
0x1800ce0da  lea     rcx, [rsp+0C8h+var_88]
0x1800ce0df  call    deflateEnd
0x1800ce0e4  test    eax, eax
0x1800ce0e6  jnz     short loc_1800CE112
0x1800ce0e8  mov     r8d, edi; unsigned int
0x1800ce0eb  mov     rdx, rsi; void *
0x1800ce0ee  mov     rcx, rbp; struct IStream *
0x1800ce0f1  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800ce0f6  mov     ebx, eax
0x1800ce0f8  test    eax, eax
0x1800ce0fa  jns     short loc_1800CE10D
0x1800ce0fc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800ce103  jz      short loc_1800CE109
0x1800ce105  mov     ecx, eax
0x1800ce107  jmp     short loc_1800CE122
0x1800ce109  test    eax, eax
0x1800ce10b  js      short loc_1800CE127
0x1800ce10d  mov     [r14], edi
0x1800ce110  jmp     short loc_1800CE127
0x1800ce112  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800ce119  mov     ebx, 88982F70h
0x1800ce11e  jz      short loc_1800CE127
0x1800ce120  mov     ecx, ebx; int
0x1800ce122  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800ce127  mov     rcx, rsi; pv
0x1800ce12a  call    cs:__imp_CoTaskMemFree
0x1800ce131  nop     dword ptr [rax+rax+00h]
0x1800ce136  mov     eax, ebx
0x1800ce138  add     rsp, 0A0h
0x1800ce13f  pop     r14
0x1800ce141  pop     rdi
0x1800ce142  pop     rsi
0x1800ce143  pop     rbp
0x1800ce144  pop     rbx
0x1800ce145  retn
```
