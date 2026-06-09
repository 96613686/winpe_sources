# CMetadataPngItxtReaderWriter::HrLoadText(uchar *,uint,ulong *)

- ea: `0x1801ae050`
- end: `0x1801ae2a5`
- name: `?HrLoadText@CMetadataPngItxtReaderWriter@@MEAAJPEAEIPEAK@Z`
- size: `597`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800456c0`

## callees

- `0x180047e68`
- `0x18004bcf0`
- `0x18004c484`
- `0x18006ac40`
- `0x1800ac1f0`
- `0x1800bb784`
- `0x1800e3c04`
- `0x18017b528`
- `0x1801ae050`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae0b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae15c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae1ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae0b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae15c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae1ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae1cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae217`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae222`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae1cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae217`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae222`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae282`

## pseudocode

```c
__int64 __fastcall CMetadataPngItxtReaderWriter::HrLoadText(
        CMetadataPngItxtReaderWriter *this,
        unsigned __int8 *a2,
        UINT a3,
        unsigned int *a4)
{
  bool v4; // zf
  unsigned int *v5; // rsi
  unsigned __int8 *v7; // r14
  unsigned __int64 v9; // rbx
  HRESULT v10; // eax
  UINT v11; // r12d
  void *v12; // rsi
  unsigned int v13; // ebx
  unsigned __int8 *v14; // rdi
  size_t v15; // rbx
  int v16; // eax
  unsigned __int8 *v17; // rax
  unsigned __int8 *v18; // r14
  unsigned __int8 *v19; // rax
  unsigned __int8 *v20; // r14
  int v21; // eax
  unsigned __int8 *v23; // [rsp+38h] [rbp-39h] BYREF
  UINT v24; // [rsp+40h] [rbp-31h]
  void *v25; // [rsp+48h] [rbp-29h]
  UINT v26; // [rsp+50h] [rbp-21h]
  SIZE_T cb; // [rsp+54h] [rbp-1Dh]
  UINT puResult; // [rsp+D8h] [rbp+67h] BYREF
  unsigned __int8 *v29; // [rsp+E0h] [rbp+6Fh]
  unsigned int *v30; // [rsp+F0h] [rbp+7Fh]

  v30 = a4;
  v29 = a2;
  v4 = *((_BYTE *)this + 168) == 1;
  v5 = a4;
  v7 = a2;
  puResult = 0;
  v9 = a3;
  if ( v4 )
  {
    v10 = ULongLongToUInt(2LL * a3, &puResult);
    v11 = puResult;
    if ( v10 < 0 )
      v11 = a3;
    v12 = CoTaskMemAlloc(v11);
    if ( !v12 )
    {
      v13 = -2147024882;
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2147024882);
      return v13;
    }
    v14 = 0;
    memset_0(&v23, 0, 0x58u);
    if ( (unsigned int)inflateInit2_(&v23, 15, "1.3.1", 88) )
    {
      v13 = -2003292304;
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2003292304);
    }
    else
    {
      v15 = 0;
      v23 = v7;
      v24 = a3;
LABEL_11:
      v26 = v11;
      v25 = v12;
      while ( 1 )
      {
        v16 = inflate(&v23, 2);
        if ( v16 == 1 )
          break;
        if ( v16 )
          goto LABEL_24;
        if ( !v26 )
        {
          v17 = (unsigned __int8 *)CoTaskMemAlloc((unsigned int)cb);
          v18 = v17;
          if ( !v17 )
            goto LABEL_19;
          if ( v14 )
          {
            memcpy_0(v17, v14, v15);
            CoTaskMemFree(v14);
          }
          v14 = v18;
          memcpy_0(&v18[v15], v12, (unsigned int)cb - v15);
          v15 = (unsigned int)cb;
          goto LABEL_11;
        }
      }
      v19 = (unsigned __int8 *)CoTaskMemAlloc((unsigned int)cb);
      v20 = v19;
      if ( !v19 )
      {
LABEL_19:
        v13 = -2147024882;
        goto LABEL_25;
      }
      if ( v14 )
      {
        memcpy_0(v19, v14, v15);
        CoTaskMemFree(v14);
      }
      v14 = v20;
      memcpy_0(&v20[v15], v12, (unsigned int)cb - v15);
      v9 = (unsigned int)cb;
      if ( !(unsigned int)inflateEnd(&v23) )
      {
        CoTaskMemFree(v12);
        v7 = v29;
        v5 = v30;
        goto LABEL_31;
      }
LABEL_24:
      v13 = -2003292304;
LABEL_25:
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v13);
      v7 = v29;
    }
    CoTaskMemFree(v12);
  }
  else
  {
    v14 = a2;
LABEL_31:
    v21 = CMetadataPngItxtReaderWriter::ConvertMultiByteToWideChar(
            this,
            (char *)v14,
            v9,
            (unsigned __int16 **)this + 26,
            (unsigned __int64 *)this + 27);
    v13 = v21;
    if ( v21 >= 0 )
    {
      *v5 = a3;
    }
    else if ( (_DWORD)g_doStackCaptures )
    {
      DoStackCapture(v21);
    }
  }
  if ( v14 && v14 != v7 )
    CoTaskMemFree(v14);
  return v13;
}

```

## disassembly

```asm
0x1801ae050  mov     rax, rsp
0x1801ae053  mov     [rax+18h], rbx
0x1801ae057  mov     [rax+20h], r9
0x1801ae05b  mov     [rax+10h], rdx
0x1801ae05f  push    rbp
0x1801ae060  push    rsi
0x1801ae061  push    rdi
0x1801ae062  push    r12
0x1801ae064  push    r13
0x1801ae066  push    r14
0x1801ae068  push    r15
0x1801ae06a  lea     rbp, [rax-5Fh]
0x1801ae06e  sub     rsp, 90h
0x1801ae075  cmp     byte ptr [rcx+0A8h], 1
0x1801ae07c  mov     rsi, r9
0x1801ae07f  mov     r15d, r8d
0x1801ae082  mov     r14, rdx
0x1801ae085  mov     r13, rcx
0x1801ae088  mov     [rbp+57h+puResult], 0
0x1801ae08f  mov     ebx, r8d
0x1801ae092  jnz     loc_1801AE232
0x1801ae098  lea     rcx, [r15+r15]; ullOperand
0x1801ae09c  lea     rdx, [rbp+57h+puResult]; puResult
0x1801ae0a0  call    ULongLongToUInt
0x1801ae0a5  mov     r12d, [rbp+57h+puResult]
0x1801ae0a9  test    eax, eax
0x1801ae0ab  cmovs   r12d, r15d
0x1801ae0af  mov     ecx, r12d; cb
0x1801ae0b2  call    cs:__imp_CoTaskMemAlloc
0x1801ae0b8  mov     rsi, rax
0x1801ae0bb  test    rax, rax
0x1801ae0be  jnz     short loc_1801AE0DD
0x1801ae0c0  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1801ae0c6  mov     ebx, 8007000Eh
0x1801ae0cb  jz      loc_1801AE288
0x1801ae0d1  mov     ecx, ebx; int
0x1801ae0d3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801ae0d8  jmp     loc_1801AE288
0x1801ae0dd  xor     edi, edi
0x1801ae0df  lea     rcx, [rbp+57h+var_90]; void *
0x1801ae0e3  xor     edx, edx; Val
0x1801ae0e5  lea     ebx, [rdi+58h]
0x1801ae0e8  mov     r8d, ebx; Size
0x1801ae0eb  call    memset_0
0x1801ae0f0  mov     r9d, ebx
0x1801ae0f3  lea     r8, a131; "1.3.1"
0x1801ae0fa  lea     edx, [rdi+0Fh]
0x1801ae0fd  lea     rcx, [rbp+57h+var_90]
0x1801ae101  call    inflateInit2_
0x1801ae106  test    eax, eax
0x1801ae108  jz      short loc_1801AE127
0x1801ae10a  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1801ae110  mov     ebx, 88982F70h
0x1801ae115  jz      loc_1801AE214
0x1801ae11b  mov     ecx, ebx; int
0x1801ae11d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801ae122  jmp     loc_1801AE214
0x1801ae127  xor     ebx, ebx
0x1801ae129  mov     [rbp+57h+var_90], r14
0x1801ae12d  mov     [rbp+57h+var_88], r15d
0x1801ae131  mov     [rbp+57h+var_78], r12d
0x1801ae135  mov     [rbp+57h+var_80], rsi
0x1801ae139  mov     edx, 2
0x1801ae13e  lea     rcx, [rbp+57h+var_90]
0x1801ae142  call    inflate
0x1801ae147  cmp     eax, 1
0x1801ae14a  jz      short loc_1801AE1A8
0x1801ae14c  test    eax, eax
0x1801ae14e  jnz     loc_1801AE1FB
0x1801ae154  cmp     [rbp+57h+var_78], eax
0x1801ae157  jnz     short loc_1801AE139
0x1801ae159  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x1801ae15c  call    cs:__imp_CoTaskMemAlloc
0x1801ae162  mov     r14, rax
0x1801ae165  test    rax, rax
0x1801ae168  jz      short loc_1801AE1A1
0x1801ae16a  test    rdi, rdi
0x1801ae16d  jz      short loc_1801AE186
0x1801ae16f  mov     r8, rbx; Size
0x1801ae172  mov     rdx, rdi; Src
0x1801ae175  mov     rcx, rax; void *
0x1801ae178  call    memcpy_0
0x1801ae17d  mov     rcx, rdi; pv
0x1801ae180  call    cs:__imp_CoTaskMemFree
0x1801ae186  mov     r8d, dword ptr [rbp+57h+cb]
0x1801ae18a  lea     rcx, [r14+rbx]; void *
0x1801ae18e  sub     r8, rbx; Size
0x1801ae191  mov     rdx, rsi; Src
0x1801ae194  mov     rdi, r14
0x1801ae197  call    memcpy_0
0x1801ae19c  mov     ebx, dword ptr [rbp+57h+cb]
0x1801ae19f  jmp     short loc_1801AE131
0x1801ae1a1  mov     ebx, 8007000Eh
0x1801ae1a6  jmp     short loc_1801AE200
0x1801ae1a8  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x1801ae1ab  call    cs:__imp_CoTaskMemAlloc
0x1801ae1b1  mov     r14, rax
0x1801ae1b4  test    rax, rax
0x1801ae1b7  jz      short loc_1801AE1A1
0x1801ae1b9  test    rdi, rdi
0x1801ae1bc  jz      short loc_1801AE1D5
0x1801ae1be  mov     r8, rbx; Size
0x1801ae1c1  mov     rdx, rdi; Src
0x1801ae1c4  mov     rcx, rax; void *
0x1801ae1c7  call    memcpy_0
0x1801ae1cc  mov     rcx, rdi; pv
0x1801ae1cf  call    cs:__imp_CoTaskMemFree
0x1801ae1d5  mov     r8d, dword ptr [rbp+57h+cb]
0x1801ae1d9  lea     rcx, [r14+rbx]; void *
0x1801ae1dd  sub     r8, rbx; Size
0x1801ae1e0  mov     rdx, rsi; Src
0x1801ae1e3  mov     rdi, r14
0x1801ae1e6  call    memcpy_0
0x1801ae1eb  mov     ebx, dword ptr [rbp+57h+cb]
0x1801ae1ee  lea     rcx, [rbp+57h+var_90]
0x1801ae1f2  call    inflateEnd
0x1801ae1f7  test    eax, eax
0x1801ae1f9  jz      short loc_1801AE21F
0x1801ae1fb  mov     ebx, 88982F70h
0x1801ae200  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801ae207  jz      short loc_1801AE210
0x1801ae209  mov     ecx, ebx; int
0x1801ae20b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801ae210  mov     r14, [rbp+57h+arg_8]
0x1801ae214  mov     rcx, rsi; pv
0x1801ae217  call    cs:__imp_CoTaskMemFree
0x1801ae21d  jmp     short loc_1801AE275
0x1801ae21f  mov     rcx, rsi; pv
0x1801ae222  call    cs:__imp_CoTaskMemFree
0x1801ae228  mov     r14, [rbp+57h+arg_8]
0x1801ae22c  mov     rsi, [rbp+57h+arg_18]
0x1801ae230  jmp     short loc_1801AE235
0x1801ae232  mov     rdi, r14
0x1801ae235  lea     rax, [r13+0D8h]
0x1801ae23c  mov     r8, rbx; unsigned __int64
0x1801ae23f  lea     r9, [r13+0D0h]; unsigned __int16 **
0x1801ae246  mov     [rsp+20h], rax; unsigned __int64 *
0x1801ae24b  mov     rdx, rdi; char *
0x1801ae24e  mov     rcx, r13; this
0x1801ae251  call    ?ConvertMultiByteToWideChar@CMetadataPngItxtReaderWriter@@MEAAJPEAD_KPEAPEAGPEA_K@Z; CMetadataPngItxtReaderWriter::ConvertMultiByteToWideChar(char *,unsigned __int64,ushort * *,unsigned __int64 *)
0x1801ae256  mov     ebx, eax
0x1801ae258  test    eax, eax
0x1801ae25a  jns     short loc_1801AE272
0x1801ae25c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801ae263  jz      short loc_1801AE26E
0x1801ae265  mov     ecx, eax; int
0x1801ae267  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801ae26c  jmp     short loc_1801AE275
0x1801ae26e  test    eax, eax
0x1801ae270  js      short loc_1801AE275
0x1801ae272  mov     [rsi], r15d
0x1801ae275  test    rdi, rdi
0x1801ae278  jz      short loc_1801AE288
0x1801ae27a  cmp     rdi, r14
0x1801ae27d  jz      short loc_1801AE288
0x1801ae27f  mov     rcx, rdi; pv
0x1801ae282  call    cs:__imp_CoTaskMemFree
0x1801ae288  mov     eax, ebx
0x1801ae28a  mov     rbx, [rsp+0C0h+arg_10]
0x1801ae292  add     rsp, 90h
0x1801ae299  pop     r15
0x1801ae29b  pop     r14
0x1801ae29d  pop     r13
0x1801ae29f  pop     r12
0x1801ae2a1  pop     rdi
0x1801ae2a2  pop     rsi
0x1801ae2a3  pop     rbp
0x1801ae2a4  retn
```
