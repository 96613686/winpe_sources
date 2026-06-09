# CMetadataPngIccpReaderWriter::ReadFields(IStream *)

- ea: `0x180046630`
- end: `0x1800467eb`
- name: `?ReadFields@CMetadataPngIccpReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(CMetadataPngIccpReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180036cb4`
- `0x180046630`
- `0x180046800`
- `0x180046a40`
- `0x1800bb784`
- `0x18017b540`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800466fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800466fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046776`

## pseudocode

```c
__int64 __fastcall CMetadataPngIccpReaderWriter::ReadFields(CMetadataPngIccpReaderWriter *this, struct IStream *a2)
{
  __int64 v4; // rdx
  int v5; // eax
  unsigned int v6; // ebx
  char *v7; // rax
  char *v8; // rdi
  int FullBufferFromStream; // eax
  int v10; // esi
  int v11; // esi
  int v13; // ecx
  int v14; // ecx
  int v15; // eax
  SIZE_T cb; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v17; // [rsp+68h] [rbp+38h] BYREF
  char Buf1; // [rsp+70h] [rbp+40h] BYREF

  v4 = *((unsigned int *)this + 34);
  v17 = 0;
  LODWORD(cb) = 0;
  v5 = (*(__int64 (__fastcall **)(struct IStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, v4, 0, 0);
  v6 = v5;
  if ( v5 < 0 )
    goto LABEL_14;
  v5 = ReadFullBufferFromStream(a2, &cb, 4);
  v6 = v5;
  if ( v5 < 0 )
    goto LABEL_14;
  LODWORD(cb) = ((((_DWORD)cb << 16) | cb & 0xFF00) << 8) | ((WORD1(cb) | cb & 0xFF0000) >> 8);
  if ( (unsigned int)cb < 4 )
  {
LABEL_20:
    v6 = -2003292317;
LABEL_21:
    if ( !(_DWORD)g_doStackCaptures )
      return v6;
    v13 = v6;
    goto LABEL_16;
  }
  v5 = ReadFullBufferFromStream(a2, &Buf1, 4);
  v6 = v5;
  if ( v5 < 0 )
  {
LABEL_14:
    if ( !(_DWORD)g_doStackCaptures )
      return v6;
    v13 = v5;
LABEL_16:
    DoStackCapture(v13);
    return v6;
  }
  if ( memcmp_0(&Buf1, "iCCP", 4u) )
    goto LABEL_20;
  v7 = (char *)CoTaskMemAlloc((unsigned int)cb);
  v8 = v7;
  if ( !v7 )
  {
    v6 = -2147024882;
    goto LABEL_21;
  }
  FullBufferFromStream = ReadFullBufferFromStream(a2, v7, (unsigned int)cb);
  v6 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
    goto LABEL_17;
  v10 = cb;
  FullBufferFromStream = CMetadataPngIccpReaderWriter::HrLoadProfileName(this, v8, cb, &v17);
  v6 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
    goto LABEL_17;
  v11 = v10 - v17;
  v6 = -2003292317;
  if ( !v11 || v8[v17] )
  {
    v15 = (int)g_doStackCaptures;
    if ( (_DWORD)g_doStackCaptures )
    {
      DoStackCapture(-2003292317);
      v15 = (int)g_doStackCaptures;
    }
    if ( !v15 )
      goto LABEL_12;
    v14 = -2003292317;
    goto LABEL_19;
  }
  FullBufferFromStream = CMetadataPngIccpReaderWriter::HrLoadProfileData(
                           this,
                           (unsigned __int8 *)&v8[v17 + 1],
                           v11 - 1,
                           &v17);
  v6 = FullBufferFromStream;
  if ( FullBufferFromStream < 0 )
  {
LABEL_17:
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_12;
    v14 = FullBufferFromStream;
LABEL_19:
    DoStackCapture(v14);
  }
LABEL_12:
  CoTaskMemFree(v8);
  return v6;
}

```

## disassembly

```asm
0x180046630  mov     [rsp-28h+arg_18], rbx
0x180046635  push    rbp
0x180046636  push    rsi
0x180046637  push    rdi
0x180046638  push    r14
0x18004663a  push    r15
0x18004663c  mov     rbp, rsp
0x18004663f  sub     rsp, 30h
0x180046643  mov     rsi, rdx
0x180046646  mov     r14, rcx
0x180046649  mov     edx, [rcx+88h]
0x18004664f  xor     r15d, r15d
0x180046652  xor     r9d, r9d
0x180046655  mov     [rbp+arg_8], r15d
0x180046659  xor     r8d, r8d
0x18004665c  mov     dword ptr [rbp+cb], r15d
0x180046660  mov     rax, [rsi]
0x180046663  mov     rcx, rsi
0x180046666  mov     rax, [rax+28h]
0x18004666a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004666f  mov     ebx, eax
0x180046671  test    eax, eax
0x180046673  js      loc_18004678F
0x180046679  lea     edi, [r15+4]
0x18004667d  mov     rcx, rsi; struct IStream *
0x180046680  mov     r8d, edi; unsigned int
0x180046683  lea     rdx, [rbp+cb]; void *
0x180046687  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x18004668c  mov     ebx, eax
0x18004668e  test    eax, eax
0x180046690  js      loc_18004678F
0x180046696  mov     ecx, dword ptr [rbp+cb]
0x180046699  mov     edx, ecx
0x18004669b  and     edx, 0FF0000h
0x1800466a1  mov     eax, ecx
0x1800466a3  shr     eax, 10h
0x1800466a6  or      edx, eax
0x1800466a8  mov     eax, ecx
0x1800466aa  and     eax, 0FF00h
0x1800466af  shl     ecx, 10h
0x1800466b2  or      eax, ecx
0x1800466b4  shr     edx, 8
0x1800466b7  shl     eax, 8
0x1800466ba  or      edx, eax
0x1800466bc  mov     dword ptr [rbp+cb], edx
0x1800466bf  cmp     edx, edi
0x1800466c1  jb      loc_1800467B3
0x1800466c7  mov     r8d, edi; unsigned int
0x1800466ca  lea     rdx, [rbp+Buf1]; void *
0x1800466ce  mov     rcx, rsi; struct IStream *
0x1800466d1  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800466d6  mov     ebx, eax
0x1800466d8  test    eax, eax
0x1800466da  js      loc_18004678F
0x1800466e0  mov     r8d, edi; Size
0x1800466e3  lea     rdx, aIccp_0; "iCCP"
0x1800466ea  lea     rcx, [rbp+Buf1]; Buf1
0x1800466ee  call    memcmp_0
0x1800466f3  test    eax, eax
0x1800466f5  jnz     loc_1800467B3
0x1800466fb  mov     ecx, dword ptr [rbp+cb]; cb
0x1800466fe  call    cs:__imp_CoTaskMemAlloc
0x180046704  mov     rdi, rax
0x180046707  test    rax, rax
0x18004670a  jz      loc_1800467E4
0x180046710  mov     r8d, dword ptr [rbp+cb]; unsigned int
0x180046714  mov     rdx, rax; void *
0x180046717  mov     rcx, rsi; struct IStream *
0x18004671a  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x18004671f  mov     ebx, eax
0x180046721  test    eax, eax
0x180046723  js      short loc_1800467A1
0x180046725  mov     esi, dword ptr [rbp+cb]
0x180046728  lea     r9, [rbp+arg_8]; unsigned int *
0x18004672c  mov     r8d, esi; unsigned int
0x18004672f  mov     rdx, rdi; char *
0x180046732  mov     rcx, r14; this
0x180046735  call    ?HrLoadProfileName@CMetadataPngIccpReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngIccpReaderWriter::HrLoadProfileName(uchar *,uint,ulong *)
0x18004673a  mov     ebx, eax
0x18004673c  test    eax, eax
0x18004673e  js      short loc_1800467A1
0x180046740  sub     esi, [rbp+arg_8]
0x180046743  mov     ebx, 88982F63h
0x180046748  cmp     esi, 1
0x18004674b  jb      short loc_1800467C5
0x18004674d  mov     eax, [rbp+arg_8]
0x180046750  cmp     [rax+rdi], r15b
0x180046754  jnz     short loc_1800467C5
0x180046756  lea     rdx, [rax+1]
0x18004675a  mov     rcx, r14; this
0x18004675d  add     rdx, rdi; unsigned __int8 *
0x180046760  lea     r8d, [rsi-1]; unsigned int
0x180046764  lea     r9, [rbp+arg_8]; unsigned int *
0x180046768  call    ?HrLoadProfileData@CMetadataPngIccpReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngIccpReaderWriter::HrLoadProfileData(uchar *,uint,ulong *)
0x18004676d  mov     ebx, eax
0x18004676f  test    eax, eax
0x180046771  js      short loc_1800467A1
0x180046773  mov     rcx, rdi; pv
0x180046776  call    cs:__imp_CoTaskMemFree
0x18004677c  mov     eax, ebx
0x18004677e  mov     rbx, [rsp+30h+arg_18]
0x180046783  add     rsp, 30h
0x180046787  pop     r15
0x180046789  pop     r14
0x18004678b  pop     rdi
0x18004678c  pop     rsi
0x18004678d  pop     rbp
0x18004678e  retn
0x18004678f  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180046796  jz      short loc_18004677C
0x180046798  mov     ecx, eax; int
0x18004679a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004679f  jmp     short loc_18004677C
0x1800467a1  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800467a8  jz      short loc_180046773
0x1800467aa  mov     ecx, eax; int
0x1800467ac  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800467b1  jmp     short loc_180046773
0x1800467b3  mov     ebx, 88982F63h
0x1800467b8  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800467bf  jz      short loc_18004677C
0x1800467c1  mov     ecx, ebx
0x1800467c3  jmp     short loc_18004679A
0x1800467c5  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800467cb  test    eax, eax
0x1800467cd  jz      short loc_1800467DC
0x1800467cf  mov     ecx, ebx; int
0x1800467d1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800467d6  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800467dc  test    eax, eax
0x1800467de  jz      short loc_180046773
0x1800467e0  mov     ecx, ebx
0x1800467e2  jmp     short loc_1800467AC
0x1800467e4  mov     ebx, 8007000Eh
0x1800467e9  jmp     short loc_1800467B8
```
