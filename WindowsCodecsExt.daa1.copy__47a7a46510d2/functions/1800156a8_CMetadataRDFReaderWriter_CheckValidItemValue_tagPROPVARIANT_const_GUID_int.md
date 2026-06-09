# CMetadataRDFReaderWriter::CheckValidItemValue(tagPROPVARIANT const * *,_GUID *,int *)

- ea: `0x1800156a8`
- end: `0x180015951`
- name: `?CheckValidItemValue@CMetadataRDFReaderWriter@@IEAAJPEAPEBUtagPROPVARIANT@@PEAU_GUID@@PEAH@Z`
- size: `681`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, const struct tagPROPVARIANT **, struct _GUID *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002aa0`

## callees

- `0x180002920`
- `0x1800156a8`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CheckValidItemValue(
        CMetadataRDFReaderWriter *this,
        const struct tagPROPVARIANT **a2,
        struct _GUID *a3,
        int *a4)
{
  __int64 v4; // rax
  unsigned int v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rax
  int v11; // eax
  int v12; // ecx
  int v13; // eax
  __int64 v15; // [rsp+40h] [rbp-20h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h] BYREF
  CMetadataRDFReaderWriter *v17; // [rsp+50h] [rbp-10h] BYREF
  int v18; // [rsp+98h] [rbp+38h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+48h] BYREF

  v4 = (__int64)*a2;
  v15 = 0;
  *a4 = 0;
  v16 = 0;
  v19 = 0;
  v17 = 0;
  if ( !v4 )
    goto LABEL_2;
  if ( *(_WORD *)v4 != 13 )
  {
    if ( *(_WORD *)v4 == 31 )
    {
      v8 = 0;
      if ( *(_QWORD *)(v4 + 8) )
        return v8;
      goto LABEL_2;
    }
    goto LABEL_27;
  }
  v9 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v4 + 8);
  if ( !v9 )
  {
LABEL_2:
    v8 = -2147024809;
    goto LABEL_28;
  }
  v18 = 0;
  v10 = **v9;
  if ( !*((_DWORD *)this + 42) )
  {
    v11 = v10(v9, &IID_IWICMetadataReader, &v19);
    v8 = v11;
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 32LL))(v19, &v15);
      v8 = v11;
      if ( v11 >= 0 )
      {
        v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v15)(v15, &IID_IWICMetadataReaderInfo, &v16);
        v8 = v11;
        if ( v11 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int *, _QWORD))(*(_QWORD *)v16 + 144LL))(
                  v16,
                  *((_QWORD *)this + 19),
                  0,
                  0,
                  &v18,
                  0);
          goto LABEL_14;
        }
      }
    }
LABEL_7:
    if ( !g_doStackCaptures )
      goto LABEL_31;
LABEL_8:
    v12 = v11;
LABEL_30:
    DoStackCapture(v12);
    goto LABEL_31;
  }
  v11 = v10(v9, &IID_IWICMetadataWriter, &v19);
  v8 = v11;
  if ( v11 < 0 )
    goto LABEL_7;
  if ( (**(int (__fastcall ***)(__int64, GUID *, CMetadataRDFReaderWriter **))v19)(v19, &IID_IXMPCMetadataRDF, &v17) >= 0 )
  {
    v11 = CMetadataRDFReaderWriter::SetDepth(v17, *((_DWORD *)this + 50) + 1);
    v8 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 32LL))(v19, &v15);
  v8 = v11;
  if ( v11 < 0 )
    goto LABEL_7;
  v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v15)(v15, &IID_IWICMetadataWriterInfo, &v16);
  v8 = v11;
  if ( v11 < 0 )
    goto LABEL_7;
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int *))(*(_QWORD *)v16 + 144LL))(
          v16,
          *((_QWORD *)this + 19),
          0,
          0,
          &v18);
LABEL_14:
  if ( v13 >= 0 && v18 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v19 + 24LL))(v19, a3);
    v8 = v11;
    if ( v11 >= 0 )
    {
      *a4 = 1;
      goto LABEL_31;
    }
    if ( !g_doStackCaptures )
      goto LABEL_31;
    goto LABEL_8;
  }
LABEL_27:
  v8 = -2003292271;
LABEL_28:
  if ( g_doStackCaptures )
  {
    v12 = v8;
    goto LABEL_30;
  }
LABEL_31:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v17 )
    (*(void (__fastcall **)(CMetadataRDFReaderWriter *))(*(_QWORD *)v17 + 16LL))(v17);
  return v8;
}

```

## disassembly

```asm
0x1800156a8  mov     [rsp-28h+arg_0], rbx
0x1800156ad  push    rbp
0x1800156ae  push    rsi
0x1800156af  push    rdi
0x1800156b0  push    r14
0x1800156b2  push    r15
0x1800156b4  mov     rbp, rsp
0x1800156b7  sub     rsp, 60h
0x1800156bb  mov     rax, [rdx]
0x1800156be  xor     r15d, r15d
0x1800156c1  mov     [rbp+var_20], r15
0x1800156c5  mov     rsi, r9
0x1800156c8  mov     [r9], r15d
0x1800156cb  mov     r14, r8
0x1800156ce  mov     [rbp+var_18], r15
0x1800156d2  mov     rdi, rcx
0x1800156d5  mov     [rbp+arg_18], r15
0x1800156d9  mov     [rbp+var_10], r15
0x1800156dd  test    rax, rax
0x1800156e0  jnz     short loc_1800156EC
0x1800156e2  mov     ebx, 80070057h
0x1800156e7  jmp     loc_1800158CB
0x1800156ec  cmp     word ptr [rax], 0Dh
0x1800156f0  jnz     loc_1800158B2
0x1800156f6  mov     rcx, [rax+8]
0x1800156fa  test    rcx, rcx
0x1800156fd  jz      short loc_1800156E2
0x1800156ff  lea     r8, [rbp+arg_18]
0x180015703  mov     [rbp+arg_8], r15d
0x180015707  mov     rax, [rcx]
0x18001570a  mov     rax, [rax]
0x18001570d  cmp     [rdi+0A8h], r15d
0x180015714  jz      loc_180015827
0x18001571a  lea     rdx, IID_IWICMetadataWriter
0x180015721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015726  mov     ebx, eax
0x180015728  test    eax, eax
0x18001572a  jns     short loc_180015740
0x18001572c  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180015733  jz      loc_1800158DB
0x180015739  mov     ecx, eax
0x18001573b  jmp     loc_1800158D6
0x180015740  mov     rcx, [rbp+arg_18]
0x180015744  lea     r8, [rbp+var_10]
0x180015748  lea     rdx, IID_IXMPCMetadataRDF
0x18001574f  mov     rax, [rcx]
0x180015752  mov     rax, [rax]
0x180015755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001575a  test    eax, eax
0x18001575c  js      short loc_180015775
0x18001575e  mov     edx, [rdi+0C8h]
0x180015764  mov     rcx, [rbp+var_10]; this
0x180015768  inc     edx; unsigned int
0x18001576a  call    ?SetDepth@CMetadataRDFReaderWriter@@QEAAJI@Z; CMetadataRDFReaderWriter::SetDepth(uint)
0x18001576f  mov     ebx, eax
0x180015771  test    eax, eax
0x180015773  js      short loc_18001572C
0x180015775  mov     rcx, [rbp+arg_18]
0x180015779  lea     rdx, [rbp+var_20]
0x18001577d  mov     rax, [rcx]
0x180015780  mov     rax, [rax+20h]
0x180015784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015789  mov     ebx, eax
0x18001578b  test    eax, eax
0x18001578d  js      short loc_18001572C
0x18001578f  mov     rcx, [rbp+var_20]
0x180015793  lea     r8, [rbp+var_18]
0x180015797  lea     rdx, IID_IWICMetadataWriterInfo
0x18001579e  mov     rax, [rcx]
0x1800157a1  mov     rax, [rax]
0x1800157a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157a9  mov     ebx, eax
0x1800157ab  test    eax, eax
0x1800157ad  js      loc_18001572C
0x1800157b3  mov     rcx, [rbp+var_18]
0x1800157b7  lea     rdx, [rbp+arg_8]
0x1800157bb  mov     [rsp+60h+var_40], rdx
0x1800157c0  xor     r9d, r9d
0x1800157c3  mov     rdx, [rdi+98h]
0x1800157ca  xor     r8d, r8d
0x1800157cd  mov     rax, [rcx]
0x1800157d0  mov     rax, [rax+90h]
0x1800157d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157dc  test    eax, eax
0x1800157de  js      loc_1800158C6
0x1800157e4  cmp     [rbp+arg_8], r15d
0x1800157e8  jz      loc_1800158C6
0x1800157ee  mov     rcx, [rbp+arg_18]
0x1800157f2  mov     rdx, r14
0x1800157f5  mov     rax, [rcx]
0x1800157f8  mov     rax, [rax+18h]
0x1800157fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015801  mov     ebx, eax
0x180015803  test    eax, eax
0x180015805  jns     short loc_18001581C
0x180015807  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18001580e  jnz     loc_180015739
0x180015814  test    eax, eax
0x180015816  js      loc_1800158DB
0x18001581c  mov     dword ptr [rsi], 1
0x180015822  jmp     loc_1800158DB
0x180015827  lea     rdx, IID_IWICMetadataReader
0x18001582e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015833  mov     ebx, eax
0x180015835  test    eax, eax
0x180015837  js      loc_18001572C
0x18001583d  mov     rcx, [rbp+arg_18]
0x180015841  lea     rdx, [rbp+var_20]
0x180015845  mov     rax, [rcx]
0x180015848  mov     rax, [rax+20h]
0x18001584c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015851  mov     ebx, eax
0x180015853  test    eax, eax
0x180015855  js      loc_18001572C
0x18001585b  mov     rcx, [rbp+var_20]
0x18001585f  lea     r8, [rbp+var_18]
0x180015863  lea     rdx, IID_IWICMetadataReaderInfo
0x18001586a  mov     rax, [rcx]
0x18001586d  mov     rax, [rax]
0x180015870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015875  mov     ebx, eax
0x180015877  test    eax, eax
0x180015879  js      loc_18001572C
0x18001587f  mov     rcx, [rbp+var_18]
0x180015883  lea     rdx, [rbp+arg_8]
0x180015887  mov     [rsp+60h+var_38], r15
0x18001588c  xor     r9d, r9d
0x18001588f  mov     [rsp+60h+var_40], rdx
0x180015894  xor     r8d, r8d
0x180015897  mov     rdx, [rdi+98h]
0x18001589e  mov     rax, [rcx]
0x1800158a1  mov     rax, [rax+90h]
0x1800158a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158ad  jmp     loc_1800157DC
0x1800158b2  cmp     word ptr [rax], 1Fh
0x1800158b6  jnz     short loc_1800158C6
0x1800158b8  mov     ebx, r15d
0x1800158bb  cmp     [rax+8], r15
0x1800158bf  jnz     short loc_18001593B
0x1800158c1  jmp     loc_1800156E2
0x1800158c6  mov     ebx, 88982F91h
0x1800158cb  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800158d2  jz      short loc_1800158DB
0x1800158d4  mov     ecx, ebx; int
0x1800158d6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800158db  mov     rcx, [rbp+var_20]
0x1800158df  test    rcx, rcx
0x1800158e2  jz      short loc_1800158F4
0x1800158e4  mov     rax, [rcx]
0x1800158e7  mov     rax, [rax+10h]
0x1800158eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158f0  mov     [rbp+var_20], r15
0x1800158f4  mov     rcx, [rbp+var_18]
0x1800158f8  test    rcx, rcx
0x1800158fb  jz      short loc_18001590D
0x1800158fd  mov     rax, [rcx]
0x180015900  mov     rax, [rax+10h]
0x180015904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015909  mov     [rbp+var_18], r15
0x18001590d  mov     rcx, [rbp+arg_18]
0x180015911  test    rcx, rcx
0x180015914  jz      short loc_180015926
0x180015916  mov     rax, [rcx]
0x180015919  mov     rax, [rax+10h]
0x18001591d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015922  mov     [rbp+arg_18], r15
0x180015926  mov     rcx, [rbp+var_10]
0x18001592a  test    rcx, rcx
0x18001592d  jz      short loc_18001593B
0x18001592f  mov     rdx, [rcx]
0x180015932  mov     rax, [rdx+10h]
0x180015936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001593b  mov     eax, ebx
0x18001593d  mov     rbx, [rsp+60h+arg_0]
0x180015945  add     rsp, 60h
0x180015949  pop     r15
0x18001594b  pop     r14
0x18001594d  pop     rdi
0x18001594e  pop     rsi
0x18001594f  pop     rbp
0x180015950  retn
```
