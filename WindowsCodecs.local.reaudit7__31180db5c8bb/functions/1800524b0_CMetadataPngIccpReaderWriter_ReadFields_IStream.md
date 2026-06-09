# CMetadataPngIccpReaderWriter::ReadFields(IStream *)

- ea: `0x1800524b0`
- end: `0x18005267c`
- name: `?ReadFields@CMetadataPngIccpReaderWriter@@MEAAJPEAUIStream@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(CMetadataPngIccpReaderWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180017c90`
- `0x180051560`
- `0x1800524b0`
- `0x1800542e8`
- `0x1800bd9d4`
- `0x18017e450`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005257e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005257e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052600`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052600`

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
  if ( memcmp_0(&Buf1, "iCCPcHRM", 4u) )
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
0x1800524b0  mov     [rsp-28h+arg_18], rbx
0x1800524b5  push    rbp
0x1800524b6  push    rsi
0x1800524b7  push    rdi
0x1800524b8  push    r14
0x1800524ba  push    r15
0x1800524bc  mov     rbp, rsp
0x1800524bf  sub     rsp, 30h
0x1800524c3  mov     rsi, rdx
0x1800524c6  mov     r14, rcx
0x1800524c9  mov     edx, [rcx+88h]
0x1800524cf  xor     r15d, r15d
0x1800524d2  xor     r9d, r9d
0x1800524d5  mov     [rbp+arg_8], r15d
0x1800524d9  xor     r8d, r8d
0x1800524dc  mov     dword ptr [rbp+cb], r15d
0x1800524e0  mov     rax, [rsi]
0x1800524e3  mov     rcx, rsi
0x1800524e6  mov     rax, [rax+28h]
0x1800524ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524ef  mov     ebx, eax
0x1800524f1  test    eax, eax
0x1800524f3  js      loc_180052620
0x1800524f9  lea     edi, [r15+4]
0x1800524fd  mov     rcx, rsi; struct IStream *
0x180052500  mov     r8d, edi; unsigned int
0x180052503  lea     rdx, [rbp+cb]; void *
0x180052507  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x18005250c  mov     ebx, eax
0x18005250e  test    eax, eax
0x180052510  js      loc_180052620
0x180052516  mov     ecx, dword ptr [rbp+cb]
0x180052519  mov     edx, ecx
0x18005251b  and     edx, 0FF0000h
0x180052521  mov     eax, ecx
0x180052523  shr     eax, 10h
0x180052526  or      edx, eax
0x180052528  mov     eax, ecx
0x18005252a  and     eax, 0FF00h
0x18005252f  shl     ecx, 10h
0x180052532  or      eax, ecx
0x180052534  shr     edx, 8
0x180052537  shl     eax, 8
0x18005253a  or      edx, eax
0x18005253c  mov     dword ptr [rbp+cb], edx
0x18005253f  cmp     edx, edi
0x180052541  jb      loc_180052644
0x180052547  mov     r8d, edi; unsigned int
0x18005254a  lea     rdx, [rbp+Buf1]; void *
0x18005254e  mov     rcx, rsi; struct IStream *
0x180052551  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x180052556  mov     ebx, eax
0x180052558  test    eax, eax
0x18005255a  js      loc_180052620
0x180052560  mov     r8d, edi; Size
0x180052563  lea     rdx, aIccpchrm; "iCCPcHRM"
0x18005256a  lea     rcx, [rbp+Buf1]; Buf1
0x18005256e  call    memcmp_0
0x180052573  test    eax, eax
0x180052575  jnz     loc_180052644
0x18005257b  mov     ecx, dword ptr [rbp+cb]; cb
0x18005257e  call    cs:__imp_CoTaskMemAlloc
0x180052585  nop     dword ptr [rax+rax+00h]
0x18005258a  mov     rdi, rax
0x18005258d  test    rax, rax
0x180052590  jz      loc_180052675
0x180052596  mov     r8d, dword ptr [rbp+cb]; unsigned int
0x18005259a  mov     rdx, rax; void *
0x18005259d  mov     rcx, rsi; struct IStream *
0x1800525a0  call    ?ReadFullBufferFromStream@@YAJPEAUIStream@@PEAXI@Z; ReadFullBufferFromStream(IStream *,void *,uint)
0x1800525a5  mov     ebx, eax
0x1800525a7  test    eax, eax
0x1800525a9  js      loc_180052632
0x1800525af  mov     esi, dword ptr [rbp+cb]
0x1800525b2  lea     r9, [rbp+arg_8]; unsigned int *
0x1800525b6  mov     r8d, esi; unsigned int
0x1800525b9  mov     rdx, rdi; char *
0x1800525bc  mov     rcx, r14; this
0x1800525bf  call    ?HrLoadProfileName@CMetadataPngIccpReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngIccpReaderWriter::HrLoadProfileName(uchar *,uint,ulong *)
0x1800525c4  mov     ebx, eax
0x1800525c6  test    eax, eax
0x1800525c8  js      short loc_180052632
0x1800525ca  sub     esi, [rbp+arg_8]
0x1800525cd  mov     ebx, 88982F63h
0x1800525d2  cmp     esi, 1
0x1800525d5  jb      short loc_180052656
0x1800525d7  mov     eax, [rbp+arg_8]
0x1800525da  cmp     [rax+rdi], r15b
0x1800525de  jnz     short loc_180052656
0x1800525e0  lea     rdx, [rax+1]
0x1800525e4  mov     rcx, r14; this
0x1800525e7  add     rdx, rdi; unsigned __int8 *
0x1800525ea  lea     r8d, [rsi-1]; unsigned int
0x1800525ee  lea     r9, [rbp+arg_8]; unsigned int *
0x1800525f2  call    ?HrLoadProfileData@CMetadataPngIccpReaderWriter@@MEAAJPEAEIPEAK@Z; CMetadataPngIccpReaderWriter::HrLoadProfileData(uchar *,uint,ulong *)
0x1800525f7  mov     ebx, eax
0x1800525f9  test    eax, eax
0x1800525fb  js      short loc_180052632
0x1800525fd  mov     rcx, rdi; pv
0x180052600  call    cs:__imp_CoTaskMemFree
0x180052607  nop     dword ptr [rax+rax+00h]
0x18005260c  mov     eax, ebx
0x18005260e  mov     rbx, [rsp+30h+arg_18]
0x180052613  add     rsp, 30h
0x180052617  pop     r15
0x180052619  pop     r14
0x18005261b  pop     rdi
0x18005261c  pop     rsi
0x18005261d  pop     rbp
0x18005261e  retn
0x180052620  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180052627  jz      short loc_18005260C
0x180052629  mov     ecx, eax; int
0x18005262b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180052630  jmp     short loc_18005260C
0x180052632  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180052639  jz      short loc_1800525FD
0x18005263b  mov     ecx, eax; int
0x18005263d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180052642  jmp     short loc_1800525FD
0x180052644  mov     ebx, 88982F63h
0x180052649  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180052650  jz      short loc_18005260C
0x180052652  mov     ecx, ebx
0x180052654  jmp     short loc_18005262B
0x180052656  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18005265c  test    eax, eax
0x18005265e  jz      short loc_18005266D
0x180052660  mov     ecx, ebx; int
0x180052662  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180052667  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18005266d  test    eax, eax
0x18005266f  jz      short loc_1800525FD
0x180052671  mov     ecx, ebx
0x180052673  jmp     short loc_18005263D
0x180052675  mov     ebx, 8007000Eh
0x18005267a  jmp     short loc_180052649
```
