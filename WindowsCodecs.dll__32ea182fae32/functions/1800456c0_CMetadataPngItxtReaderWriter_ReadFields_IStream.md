# CMetadataPngItxtReaderWriter::ReadFields(IStream *)

- ea: `0x1800456c0`
- end: `0x1800459ed`
- name: `?ReadFields@CMetadataPngItxtReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `813`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180020e7c`
- `0x1800456c0`
- `0x180045a00`
- `0x180045b10`
- `0x180045e5c`
- `0x1800bb784`
- `0x1800c2c80`
- `0x18017b540`
- `0x1801ae050`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800458e5`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800458e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045797`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045797`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045870`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045870`

## string_xrefs

- `0x1800458de`: `XML:com.adobe.xmp`

## pseudocode

```c
__int64 __fastcall CMetadataPngItxtReaderWriter::ReadFields(CMetadataPngItxtReaderWriter *this, struct IStream *a2)
{
  __int64 v2; // rax
  int v5; // eax
  unsigned int v6; // ebx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rsi
  int Key; // eax
  int v10; // edi
  unsigned int v11; // edi
  int v12; // eax
  bool v13; // zf
  int v14; // ecx
  int v15; // ecx
  unsigned int v17; // edi
  unsigned __int8 *v18; // r12
  unsigned int v19; // edi
  char *v20; // r12
  UINT v21; // edi
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rcx
  unsigned __int8 v26; // al
  ULONGLONG pullResult; // [rsp+30h] [rbp-10h] BYREF
  union _ULARGE_INTEGER v28; // [rsp+38h] [rbp-8h] BYREF
  size_t Size; // [rsp+88h] [rbp+48h] BYREF
  SIZE_T cb; // [rsp+90h] [rbp+50h] BYREF
  char Buf1; // [rsp+98h] [rbp+58h] BYREF

  v2 = *(_QWORD *)a2;
  LODWORD(Size) = 0;
  LODWORD(cb) = 0;
  v5 = (*(__int64 (__fastcall **)(struct IStream *, SIZE_T *, __int64, size_t *))(v2 + 24))(a2, &cb, 4, &Size);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( (_DWORD)Size != 4 )
      goto LABEL_41;
    LODWORD(cb) = ((((_DWORD)cb << 16) | cb & 0xFF00) << 8) | ((WORD1(cb) | cb & 0xFF0000) >> 8);
    if ( (unsigned int)cb < 6 )
      goto LABEL_17;
    v5 = (*(__int64 (__fastcall **)(struct IStream *, char *, __int64, size_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           &Buf1,
           4,
           &Size);
    v6 = v5;
    if ( v5 >= 0 )
    {
      if ( (_DWORD)Size == 4 )
      {
        if ( !memcmp_0(&Buf1, "iTXt", 4u) )
        {
          v7 = (unsigned __int8 *)CoTaskMemAlloc((unsigned int)cb);
          v8 = v7;
          if ( v7 )
          {
            Key = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int8 *, _QWORD, size_t *))(*(_QWORD *)a2 + 24LL))(
                    a2,
                    v7,
                    (unsigned int)cb,
                    &Size);
            v6 = Key;
            if ( Key < 0 )
              goto LABEL_24;
            v10 = cb;
            if ( (_DWORD)Size != (_DWORD)cb )
            {
              v13 = (_DWORD)g_doStackCaptures == 0;
              v6 = -2003292317;
              goto LABEL_15;
            }
            Key = CMetadataPngItxtReaderWriter::HrLoadKey(this, v8, cb, (unsigned int *)&Size);
            v6 = Key;
            if ( Key < 0 )
              goto LABEL_24;
            v11 = v10 - Size;
            v6 = -2003292317;
            if ( v11 < 2
              || (v25 = (unsigned int)Size, v26 = v8[(unsigned int)Size], (*((_BYTE *)this + 168) = v26) != 0)
              && (v26 != 1 || v8[v25 + 1]) )
            {
              v12 = (int)g_doStackCaptures;
              if ( (_DWORD)g_doStackCaptures )
              {
                DoStackCapture(-2003292317);
                v12 = (int)g_doStackCaptures;
              }
              v13 = v12 == 0;
LABEL_15:
              if ( !v13 )
              {
                v14 = -2003292317;
LABEL_26:
                DoStackCapture(v14);
              }
LABEL_27:
              CoTaskMemFree(v8);
              return v6;
            }
            LODWORD(Size) = 2;
            v17 = v11 - 2;
            v18 = &v8[v25 + 2];
            Key = CMetadataPngItxtReaderWriter::HrLoadLanguageTag(this, v18, v17, (unsigned int *)&Size);
            v6 = Key;
            if ( Key < 0 )
              goto LABEL_24;
            v19 = v17 - Size;
            v20 = (char *)&v18[(unsigned int)Size];
            Key = CMetadataPngItxtReaderWriter::HrLoadTranslatedKey(this, v20, v19, (unsigned int *)&Size);
            v6 = Key;
            if ( Key < 0 )
            {
              if ( !(_DWORD)g_doStackCaptures )
                goto LABEL_27;
              goto LABEL_25;
            }
            v21 = v19 - Size;
            if ( !v21 )
              goto LABEL_27;
            v22 = *((_QWORD *)this + 19);
            v23 = (unsigned int)Size;
            if ( !v22 || (unsigned int)_o__stricmp(v22, "XML:com.adobe.xmp") || *((_BYTE *)this + 168) )
            {
              Key = CMetadataPngItxtReaderWriter::HrLoadText(
                      this,
                      (unsigned __int8 *)&v20[v23],
                      v21,
                      (unsigned int *)&Size);
            }
            else
            {
              v24 = *(_QWORD *)a2;
              pullResult = 0;
              Key = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, ULONGLONG *))(v24 + 40))(
                      a2,
                      0,
                      1,
                      &pullResult);
              v6 = Key;
              if ( Key < 0 )
                goto LABEL_24;
              v28.QuadPart = v21;
              Key = ULongLongSub(pullResult, v21, &pullResult);
              v6 = Key;
              if ( Key < 0 )
                goto LABEL_24;
              Key = CMetadataPngItxtReaderWriter::LoadEmbeddedXMP(
                      this,
                      a2,
                      (const union _ULARGE_INTEGER *)&pullResult,
                      &v28);
            }
            v6 = Key;
            if ( Key >= 0 )
              goto LABEL_27;
LABEL_24:
            if ( !(_DWORD)g_doStackCaptures )
              goto LABEL_27;
LABEL_25:
            v14 = Key;
            goto LABEL_26;
          }
          v6 = -2147024882;
LABEL_18:
          if ( (_DWORD)g_doStackCaptures )
          {
            v15 = v6;
LABEL_22:
            DoStackCapture(v15);
            return v6;
          }
          return v6;
        }
LABEL_17:
        v6 = -2003292317;
        goto LABEL_18;
      }
LABEL_41:
      v6 = -2003292304;
      goto LABEL_18;
    }
  }
  if ( (_DWORD)g_doStackCaptures )
  {
    v15 = v5;
    goto LABEL_22;
  }
  return v6;
}

```

## disassembly

```asm
0x1800456c0  mov     [rsp-38h+arg_0], rbx
0x1800456c5  push    rbp
0x1800456c6  push    rsi
0x1800456c7  push    rdi
0x1800456c8  push    r12
0x1800456ca  push    r13
0x1800456cc  push    r14
0x1800456ce  push    r15
0x1800456d0  mov     rbp, rsp
0x1800456d3  sub     rsp, 40h
0x1800456d7  mov     rax, [rdx]
0x1800456da  lea     r9, [rbp+Size]
0x1800456de  xor     r13d, r13d
0x1800456e1  mov     r15, rdx
0x1800456e4  mov     r14, rcx
0x1800456e7  mov     dword ptr [rbp+Size], r13d
0x1800456eb  lea     rdx, [rbp+cb]
0x1800456ef  mov     dword ptr [rbp+cb], r13d
0x1800456f3  mov     rax, [rax+18h]
0x1800456f7  mov     rcx, r15
0x1800456fa  lea     edi, [r13+4]
0x1800456fe  mov     r8d, edi
0x180045701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045706  mov     ebx, eax
0x180045708  test    eax, eax
0x18004570a  js      loc_180045833
0x180045710  cmp     dword ptr [rbp+Size], edi
0x180045713  jnz     loc_180045983
0x180045719  mov     ecx, dword ptr [rbp+cb]
0x18004571c  mov     edx, ecx
0x18004571e  and     edx, 0FF0000h
0x180045724  mov     eax, ecx
0x180045726  shr     eax, 10h
0x180045729  or      edx, eax
0x18004572b  mov     eax, ecx
0x18004572d  and     eax, 0FF00h
0x180045732  shl     ecx, 10h
0x180045735  or      eax, ecx
0x180045737  shr     edx, 8
0x18004573a  shl     eax, 8
0x18004573d  or      edx, eax
0x18004573f  mov     dword ptr [rbp+cb], edx
0x180045742  cmp     edx, 6
0x180045745  jb      loc_180045821
0x18004574b  mov     rax, [r15]
0x18004574e  lea     r9, [rbp+Size]
0x180045752  mov     r8d, edi
0x180045755  lea     rdx, [rbp+Buf1]
0x180045759  mov     rcx, r15
0x18004575c  mov     rax, [rax+18h]
0x180045760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045765  mov     ebx, eax
0x180045767  test    eax, eax
0x180045769  js      loc_180045833
0x18004576f  cmp     dword ptr [rbp+Size], edi
0x180045772  jnz     loc_180045983
0x180045778  mov     r8d, dword ptr [rbp+Size]; Size
0x18004577c  lea     rdx, aItxt_0; "iTXt"
0x180045783  lea     rcx, [rbp+Buf1]; Buf1
0x180045787  call    memcmp_0
0x18004578c  test    eax, eax
0x18004578e  jnz     loc_180045821
0x180045794  mov     ecx, dword ptr [rbp+cb]; cb
0x180045797  call    cs:__imp_CoTaskMemAlloc
0x18004579d  mov     rsi, rax
0x1800457a0  test    rax, rax
0x1800457a3  jz      loc_18004598D
0x1800457a9  mov     rax, [r15]
0x1800457ac  lea     r9, [rbp+Size]
0x1800457b0  mov     r8d, dword ptr [rbp+cb]
0x1800457b4  mov     rdx, rsi
0x1800457b7  mov     rcx, r15
0x1800457ba  mov     rax, [rax+18h]
0x1800457be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800457c3  mov     ebx, eax
0x1800457c5  test    eax, eax
0x1800457c7  js      loc_18004585D
0x1800457cd  mov     edi, dword ptr [rbp+cb]
0x1800457d0  cmp     dword ptr [rbp+Size], edi
0x1800457d3  jnz     loc_180045997
0x1800457d9  lea     r9, [rbp+Size]; unsigned int *
0x1800457dd  mov     r8d, edi; unsigned int
0x1800457e0  mov     rdx, rsi; unsigned __int8 *
0x1800457e3  mov     rcx, r14; this
0x1800457e6  call    ?HrLoadKey@CMetadataPngItxtReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngItxtReaderWriter::HrLoadKey(uchar *,uint,ulong *)
0x1800457eb  mov     ebx, eax
0x1800457ed  test    eax, eax
0x1800457ef  js      short loc_18004585D
0x1800457f1  sub     edi, dword ptr [rbp+Size]
0x1800457f4  mov     ebx, 88982F63h
0x1800457f9  cmp     edi, 2
0x1800457fc  jnb     loc_1800459A8
0x180045802  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180045808  test    eax, eax
0x18004580a  jz      short loc_180045819
0x18004580c  mov     ecx, ebx; int
0x18004580e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180045813  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180045819  test    eax, eax
0x18004581b  jz      short loc_18004586D
0x18004581d  mov     ecx, ebx
0x18004581f  jmp     short loc_180045868
0x180045821  mov     ebx, 88982F63h
0x180045826  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18004582d  jz      short loc_180045843
0x18004582f  mov     ecx, ebx
0x180045831  jmp     short loc_18004583E
0x180045833  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18004583a  jz      short loc_180045843
0x18004583c  mov     ecx, eax; int
0x18004583e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180045843  mov     eax, ebx
0x180045845  mov     rbx, [rsp+40h+arg_0]
0x18004584d  add     rsp, 40h
0x180045851  pop     r15
0x180045853  pop     r14
0x180045855  pop     r13
0x180045857  pop     r12
0x180045859  pop     rdi
0x18004585a  pop     rsi
0x18004585b  pop     rbp
0x18004585c  retn
0x18004585d  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180045864  jz      short loc_18004586D
0x180045866  mov     ecx, eax; int
0x180045868  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004586d  mov     rcx, rsi; pv
0x180045870  call    cs:__imp_CoTaskMemFree
0x180045876  jmp     short loc_180045843
0x180045878  mov     dword ptr [rbp+Size], 2
0x18004587f  lea     r12, [rcx+2]
0x180045883  add     edi, 0FFFFFFFEh
0x180045886  add     r12, rsi
0x180045889  lea     r9, [rbp+Size]; unsigned int *
0x18004588d  mov     rdx, r12; unsigned __int8 *
0x180045890  mov     r8d, edi; unsigned int
0x180045893  mov     rcx, r14; this
0x180045896  call    ?HrLoadLanguageTag@CMetadataPngItxtReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngItxtReaderWriter::HrLoadLanguageTag(uchar *,uint,ulong *)
0x18004589b  mov     ebx, eax
0x18004589d  test    eax, eax
0x18004589f  js      short loc_18004585D
0x1800458a1  mov     eax, dword ptr [rbp+Size]
0x1800458a4  lea     r9, [rbp+Size]; unsigned int *
0x1800458a8  sub     edi, dword ptr [rbp+Size]
0x1800458ab  add     r12, rax
0x1800458ae  mov     rdx, r12; char *
0x1800458b1  mov     r8d, edi; unsigned int
0x1800458b4  mov     rcx, r14; this
0x1800458b7  call    ?HrLoadTranslatedKey@CMetadataPngItxtReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngItxtReaderWriter::HrLoadTranslatedKey(uchar *,uint,ulong *)
0x1800458bc  mov     ebx, eax
0x1800458be  test    eax, eax
0x1800458c0  js      loc_180045969
0x1800458c6  sub     edi, dword ptr [rbp+Size]
0x1800458c9  jz      short loc_18004586D
0x1800458cb  mov     rcx, [r14+98h]
0x1800458d2  mov     ebx, dword ptr [rbp+Size]
0x1800458d5  test    rcx, rcx
0x1800458d8  jz      loc_1800459D5
0x1800458de  lea     rdx, aXmlComAdobeXmp; "XML:com.adobe.xmp"
0x1800458e5  call    cs:__imp__o__stricmp
0x1800458eb  test    eax, eax
0x1800458ed  jnz     loc_1800459D5
0x1800458f3  cmp     [r14+0A8h], r13b
0x1800458fa  jnz     loc_1800459D5
0x180045900  mov     rax, [r15]
0x180045903  lea     r9, [rbp+pullResult]
0x180045907  mov     rdx, r13
0x18004590a  mov     [rbp+pullResult], r13
0x18004590e  mov     r8d, 1
0x180045914  mov     rcx, r15
0x180045917  mov     rax, [rax+28h]
0x18004591b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045920  mov     ebx, eax
0x180045922  test    eax, eax
0x180045924  js      loc_18004585D
0x18004592a  mov     rcx, [rbp+pullResult]; ullMinuend
0x18004592e  lea     r8, [rbp+pullResult]; pullResult
0x180045932  mov     edx, edi; ullSubtrahend
0x180045934  mov     qword ptr [rbp+var_8], rdx
0x180045938  call    ULongLongSub
0x18004593d  mov     ebx, eax
0x18004593f  test    eax, eax
0x180045941  js      loc_18004585D
0x180045947  lea     r9, [rbp+var_8]; union _ULARGE_INTEGER *
0x18004594b  mov     rdx, r15; struct IStream *
0x18004594e  lea     r8, [rbp+pullResult]; union _ULARGE_INTEGER *
0x180045952  mov     rcx, r14; this
0x180045955  call    ?LoadEmbeddedXMP@CMetadataPngItxtReaderWriter@@IEAAJPEAUIStream@@AEBT_ULARGE_INTEGER@@1@Z; CMetadataPngItxtReaderWriter::LoadEmbeddedXMP(IStream *,_ULARGE_INTEGER const &,_ULARGE_INTEGER const &)
0x18004595a  mov     ebx, eax
0x18004595c  test    eax, eax
0x18004595e  jns     loc_18004586D
0x180045964  jmp     loc_18004585D
0x180045969  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180045970  jnz     loc_180045866
0x180045976  test    eax, eax
0x180045978  jns     loc_1800458C6
0x18004597e  jmp     loc_18004586D
0x180045983  mov     ebx, 88982F70h
0x180045988  jmp     loc_180045826
0x18004598d  mov     ebx, 8007000Eh
0x180045992  jmp     loc_180045826
0x180045997  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18004599e  mov     ebx, 88982F63h
0x1800459a3  jmp     loc_18004581B
0x1800459a8  mov     ecx, dword ptr [rbp+Size]
0x1800459ab  mov     al, [rcx+rsi]
0x1800459ae  mov     [r14+0A8h], al
0x1800459b5  test    al, al
0x1800459b7  jz      loc_180045878
0x1800459bd  cmp     al, 1
0x1800459bf  jnz     loc_180045802
0x1800459c5  cmp     [rcx+rsi+1], r13b
0x1800459ca  jz      loc_180045878
0x1800459d0  jmp     loc_180045802
0x1800459d5  lea     rdx, [r12+rbx]; unsigned __int8 *
0x1800459d9  mov     r8d, edi; unsigned int
0x1800459dc  lea     r9, [rbp+Size]; unsigned int *
0x1800459e0  mov     rcx, r14; this
0x1800459e3  call    ?HrLoadText@CMetadataPngItxtReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngItxtReaderWriter::HrLoadText(uchar *,uint,ulong *)
0x1800459e8  jmp     loc_18004595A
```
