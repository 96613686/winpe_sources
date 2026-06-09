# CMetadataPngItxtReaderWriter::ReadFields(IStream *)

- ea: `0x180050860`
- end: `0x180050ba0`
- name: `?ReadFields@CMetadataPngItxtReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180046a78`
- `0x180050508`
- `0x180050860`
- `0x180050bb0`
- `0x180050cc0`
- `0x1800bd9d4`
- `0x1800c5020`
- `0x18017e450`
- `0x1801b1670`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180050a92`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180050a92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050937`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050937`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050a17`

## string_xrefs

- `0x180050a8b`: `XML:com.adobe.xmp`

## pseudocode

```c
__int64 __fastcall CMetadataPngItxtReaderWriter::ReadFields(CMetadataPngItxtReaderWriter *this, struct IStream *a2)
{
  __int64 v2; // rax
  int v5; // eax
  unsigned int v6; // ebx
  unsigned __int8 *v7; // rax
  unsigned __int8 *v8; // rsi
  HRESULT Key; // eax
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
  unsigned int v21; // edi
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
0x180050860  mov     [rsp-38h+arg_0], rbx
0x180050865  push    rbp
0x180050866  push    rsi
0x180050867  push    rdi
0x180050868  push    r12
0x18005086a  push    r13
0x18005086c  push    r14
0x18005086e  push    r15
0x180050870  mov     rbp, rsp
0x180050873  sub     rsp, 40h
0x180050877  mov     rax, [rdx]
0x18005087a  lea     r9, [rbp+Size]
0x18005087e  xor     r13d, r13d
0x180050881  mov     r15, rdx
0x180050884  mov     r14, rcx
0x180050887  mov     dword ptr [rbp+Size], r13d
0x18005088b  lea     rdx, [rbp+cb]
0x18005088f  mov     dword ptr [rbp+cb], r13d
0x180050893  mov     rax, [rax+18h]
0x180050897  mov     rcx, r15
0x18005089a  lea     edi, [r13+4]
0x18005089e  mov     r8d, edi
0x1800508a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508a6  mov     ebx, eax
0x1800508a8  test    eax, eax
0x1800508aa  js      loc_1800509D9
0x1800508b0  cmp     dword ptr [rbp+Size], edi
0x1800508b3  jnz     loc_180050B36
0x1800508b9  mov     ecx, dword ptr [rbp+cb]
0x1800508bc  mov     edx, ecx
0x1800508be  and     edx, 0FF0000h
0x1800508c4  mov     eax, ecx
0x1800508c6  shr     eax, 10h
0x1800508c9  or      edx, eax
0x1800508cb  mov     eax, ecx
0x1800508cd  and     eax, 0FF00h
0x1800508d2  shl     ecx, 10h
0x1800508d5  or      eax, ecx
0x1800508d7  shr     edx, 8
0x1800508da  shl     eax, 8
0x1800508dd  or      edx, eax
0x1800508df  mov     dword ptr [rbp+cb], edx
0x1800508e2  cmp     edx, 6
0x1800508e5  jb      loc_1800509C7
0x1800508eb  mov     rax, [r15]
0x1800508ee  lea     r9, [rbp+Size]
0x1800508f2  mov     r8d, edi
0x1800508f5  lea     rdx, [rbp+Buf1]
0x1800508f9  mov     rcx, r15
0x1800508fc  mov     rax, [rax+18h]
0x180050900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050905  mov     ebx, eax
0x180050907  test    eax, eax
0x180050909  js      loc_1800509D9
0x18005090f  cmp     dword ptr [rbp+Size], edi
0x180050912  jnz     loc_180050B36
0x180050918  mov     r8d, dword ptr [rbp+Size]; Size
0x18005091c  lea     rdx, aItxt_0; "iTXt"
0x180050923  lea     rcx, [rbp+Buf1]; Buf1
0x180050927  call    memcmp_0
0x18005092c  test    eax, eax
0x18005092e  jnz     loc_1800509C7
0x180050934  mov     ecx, dword ptr [rbp+cb]; cb
0x180050937  call    cs:__imp_CoTaskMemAlloc
0x18005093e  nop     dword ptr [rax+rax+00h]
0x180050943  mov     rsi, rax
0x180050946  test    rax, rax
0x180050949  jz      loc_180050B40
0x18005094f  mov     rax, [r15]
0x180050952  lea     r9, [rbp+Size]
0x180050956  mov     r8d, dword ptr [rbp+cb]
0x18005095a  mov     rdx, rsi
0x18005095d  mov     rcx, r15
0x180050960  mov     rax, [rax+18h]
0x180050964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050969  mov     ebx, eax
0x18005096b  test    eax, eax
0x18005096d  js      loc_180050A04
0x180050973  mov     edi, dword ptr [rbp+cb]
0x180050976  cmp     dword ptr [rbp+Size], edi
0x180050979  jnz     loc_180050B4A
0x18005097f  lea     r9, [rbp+Size]; unsigned int *
0x180050983  mov     r8d, edi; unsigned int
0x180050986  mov     rdx, rsi; unsigned __int8 *
0x180050989  mov     rcx, r14; this
0x18005098c  call    ?HrLoadKey@CMetadataPngItxtReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngItxtReaderWriter::HrLoadKey(uchar *,uint,ulong *)
0x180050991  mov     ebx, eax
0x180050993  test    eax, eax
0x180050995  js      short loc_180050A04
0x180050997  sub     edi, dword ptr [rbp+Size]
0x18005099a  mov     ebx, 88982F63h
0x18005099f  cmp     edi, 2
0x1800509a2  jnb     loc_180050B5B
0x1800509a8  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800509ae  test    eax, eax
0x1800509b0  jz      short loc_1800509BF
0x1800509b2  mov     ecx, ebx; int
0x1800509b4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800509b9  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800509bf  test    eax, eax
0x1800509c1  jz      short loc_180050A14
0x1800509c3  mov     ecx, ebx
0x1800509c5  jmp     short loc_180050A0F
0x1800509c7  mov     ebx, 88982F63h
0x1800509cc  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800509d3  jz      short loc_1800509E9
0x1800509d5  mov     ecx, ebx
0x1800509d7  jmp     short loc_1800509E4
0x1800509d9  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800509e0  jz      short loc_1800509E9
0x1800509e2  mov     ecx, eax; int
0x1800509e4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800509e9  mov     eax, ebx
0x1800509eb  mov     rbx, [rsp+40h+arg_0]
0x1800509f3  add     rsp, 40h
0x1800509f7  pop     r15
0x1800509f9  pop     r14
0x1800509fb  pop     r13
0x1800509fd  pop     r12
0x1800509ff  pop     rdi
0x180050a00  pop     rsi
0x180050a01  pop     rbp
0x180050a02  retn
0x180050a04  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180050a0b  jz      short loc_180050A14
0x180050a0d  mov     ecx, eax; int
0x180050a0f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180050a14  mov     rcx, rsi; pv
0x180050a17  call    cs:__imp_CoTaskMemFree
0x180050a1e  nop     dword ptr [rax+rax+00h]
0x180050a23  jmp     short loc_1800509E9
0x180050a25  mov     dword ptr [rbp+Size], 2
0x180050a2c  lea     r12, [rcx+2]
0x180050a30  add     edi, 0FFFFFFFEh
0x180050a33  add     r12, rsi
0x180050a36  lea     r9, [rbp+Size]; unsigned int *
0x180050a3a  mov     rdx, r12; unsigned __int8 *
0x180050a3d  mov     r8d, edi; unsigned int
0x180050a40  mov     rcx, r14; this
0x180050a43  call    ?HrLoadLanguageTag@CMetadataPngItxtReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngItxtReaderWriter::HrLoadLanguageTag(uchar *,uint,ulong *)
0x180050a48  mov     ebx, eax
0x180050a4a  test    eax, eax
0x180050a4c  js      short loc_180050A04
0x180050a4e  mov     eax, dword ptr [rbp+Size]
0x180050a51  lea     r9, [rbp+Size]; unsigned int *
0x180050a55  sub     edi, dword ptr [rbp+Size]
0x180050a58  add     r12, rax
0x180050a5b  mov     rdx, r12; char *
0x180050a5e  mov     r8d, edi; unsigned int
0x180050a61  mov     rcx, r14; this
0x180050a64  call    ?HrLoadTranslatedKey@CMetadataPngItxtReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngItxtReaderWriter::HrLoadTranslatedKey(uchar *,uint,ulong *)
0x180050a69  mov     ebx, eax
0x180050a6b  test    eax, eax
0x180050a6d  js      loc_180050B1C
0x180050a73  sub     edi, dword ptr [rbp+Size]
0x180050a76  jz      short loc_180050A14
0x180050a78  mov     rcx, [r14+98h]
0x180050a7f  mov     ebx, dword ptr [rbp+Size]
0x180050a82  test    rcx, rcx
0x180050a85  jz      loc_180050B88
0x180050a8b  lea     rdx, aXmlComAdobeXmp; "XML:com.adobe.xmp"
0x180050a92  call    cs:__imp__o__stricmp
0x180050a99  nop     dword ptr [rax+rax+00h]
0x180050a9e  test    eax, eax
0x180050aa0  jnz     loc_180050B88
0x180050aa6  cmp     [r14+0A8h], r13b
0x180050aad  jnz     loc_180050B88
0x180050ab3  mov     rax, [r15]
0x180050ab6  lea     r9, [rbp+pullResult]
0x180050aba  mov     rdx, r13
0x180050abd  mov     [rbp+pullResult], r13
0x180050ac1  mov     r8d, 1
0x180050ac7  mov     rcx, r15
0x180050aca  mov     rax, [rax+28h]
0x180050ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ad3  mov     ebx, eax
0x180050ad5  test    eax, eax
0x180050ad7  js      loc_180050A04
0x180050add  mov     rcx, [rbp+pullResult]; ullMinuend
0x180050ae1  lea     r8, [rbp+pullResult]; pullResult
0x180050ae5  mov     edx, edi; ullSubtrahend
0x180050ae7  mov     qword ptr [rbp+var_8], rdx
0x180050aeb  call    ULongLongSub
0x180050af0  mov     ebx, eax
0x180050af2  test    eax, eax
0x180050af4  js      loc_180050A04
0x180050afa  lea     r9, [rbp+var_8]; union _ULARGE_INTEGER *
0x180050afe  mov     rdx, r15; struct IStream *
0x180050b01  lea     r8, [rbp+pullResult]; union _ULARGE_INTEGER *
0x180050b05  mov     rcx, r14; this
0x180050b08  call    ?LoadEmbeddedXMP@CMetadataPngItxtReaderWriter@@IEAAJPEAUIStream@@AEBT_ULARGE_INTEGER@@1@Z; CMetadataPngItxtReaderWriter::LoadEmbeddedXMP(IStream *,_ULARGE_INTEGER const &,_ULARGE_INTEGER const &)
0x180050b0d  mov     ebx, eax
0x180050b0f  test    eax, eax
0x180050b11  jns     loc_180050A14
0x180050b17  jmp     loc_180050A04
0x180050b1c  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180050b23  jnz     loc_180050A0D
0x180050b29  test    eax, eax
0x180050b2b  jns     loc_180050A73
0x180050b31  jmp     loc_180050A14
0x180050b36  mov     ebx, 88982F70h
0x180050b3b  jmp     loc_1800509CC
0x180050b40  mov     ebx, 8007000Eh
0x180050b45  jmp     loc_1800509CC
0x180050b4a  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180050b51  mov     ebx, 88982F63h
0x180050b56  jmp     loc_1800509C1
0x180050b5b  mov     ecx, dword ptr [rbp+Size]
0x180050b5e  mov     al, [rcx+rsi]
0x180050b61  mov     [r14+0A8h], al
0x180050b68  test    al, al
0x180050b6a  jz      loc_180050A25
0x180050b70  cmp     al, 1
0x180050b72  jnz     loc_1800509A8
0x180050b78  cmp     [rcx+rsi+1], r13b
0x180050b7d  jz      loc_180050A25
0x180050b83  jmp     loc_1800509A8
0x180050b88  lea     rdx, [r12+rbx]; unsigned __int8 *
0x180050b8c  mov     r8d, edi; unsigned int
0x180050b8f  lea     r9, [rbp+Size]; unsigned int *
0x180050b93  mov     rcx, r14; this
0x180050b96  call    ?HrLoadText@CMetadataPngItxtReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngItxtReaderWriter::HrLoadText(uchar *,uint,ulong *)
0x180050b9b  jmp     loc_180050B0D
```
