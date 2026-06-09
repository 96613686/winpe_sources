# EncryptDumpStream(IUnknown *,IUnknown *,unsigned __int64)

- ea: `0x180002440`
- end: `0x1800025c4`
- name: `?EncryptDumpStream@@YAJPEAUIUnknown@@0_K@Z`
- size: `388`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IUnknown *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x180002340`

## callees

- `0x180001424`
- `0x180001430`
- `0x1800021b0`
- `0x1800022e8`
- `0x180002440`
- `0x1800025cc`
- `0x1800027e0`
- `0x180002954`
- `0x180002a00`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall EncryptDumpStream(struct IUnknown *a1, struct IUnknown *a2, __int64 a3)
{
  char *v6; // rax
  CDumpWriter *v7; // rbx
  int v8; // edi
  __int64 v9; // rcx
  int v10; // eax
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v13[4]; // [rsp+38h] [rbp-20h] BYREF
  int v14; // [rsp+A8h] [rbp+50h] BYREF

  v13[0] = 0;
  v12 = 0;
  v6 = (char *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = (CDumpWriter *)v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 2) = 0;
    *(_OWORD *)(v6 + 24) = 0;
    *(_OWORD *)(v6 + 40) = 0;
    *(_OWORD *)(v6 + 56) = 0;
    *((_QWORD *)v6 + 9) = 0;
    *((_QWORD *)v6 + 10) = 0;
    *((_QWORD *)v6 + 11) = 0;
    *((_QWORD *)v6 + 12) = 0;
    *((_QWORD *)v6 + 13) = 0;
  }
  else
  {
    v7 = 0;
  }
  v13[1] = v7;
  if ( v7 )
  {
    v8 = tlx::queryinterface_unique<ISequentialStream,IUnknown>(v13, a1);
    if ( v8 >= 0 )
    {
      v8 = tlx::queryinterface_unique<ISequentialStream,IUnknown>(&v12, a2);
      if ( v8 >= 0 )
      {
        v9 = v12;
        *(_QWORD *)v7 = v13[0];
        *((_QWORD *)v7 + 1) = v9;
        *((_QWORD *)v7 + 2) = a3;
        v8 = CDumpWriter::SetupKeys(v7);
        if ( v8 >= 0 )
        {
          v8 = CDumpWriter::WriteHeader(v7);
          if ( v8 >= 0 )
          {
            v14 = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, const UCHAR *, __int64, int *))(**((_QWORD **)v7 + 1) + 32LL))(
                    *((_QWORD *)v7 + 1),
                    "RSA1",
                    539,
                    &v14);
            v8 = v10;
            if ( v14 == 539 )
            {
              if ( v10 >= 0 )
              {
                v8 = CDumpWriter::WriteSymmetricKey(v7);
                if ( v8 >= 0 )
                  v8 = CDumpWriter::WriteDumpContents(v7);
              }
            }
            else
            {
              v8 = -2147418113;
            }
          }
        }
      }
    }
  }
  else
  {
    v8 = -2147024882;
  }
  if ( v7 )
  {
    CDumpWriter::~CDumpWriter(v7);
    operator delete(v7, 0x70u);
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v13[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002440  push    rbp
0x180002442  push    rbx
0x180002443  push    rsi
0x180002444  push    rdi
0x180002445  push    r14
0x180002447  push    r15
0x180002449  mov     rbp, rsp
0x18000244c  sub     rsp, 58h
0x180002450  mov     r14, r8
0x180002453  mov     rsi, rdx
0x180002456  mov     rdi, rcx
0x180002459  xor     r15d, r15d
0x18000245c  mov     [rbp+var_20], r15
0x180002460  mov     [rbp+var_28], r15
0x180002464  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000246b  lea     ecx, [r15+70h]; unsigned __int64
0x18000246f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002474  mov     rbx, rax
0x180002477  test    rax, rax
0x18000247a  jz      short loc_1800024AC
0x18000247c  mov     [rax], r15
0x18000247f  mov     [rax+8], r15
0x180002483  mov     [rax+10h], r15
0x180002487  xorps   xmm0, xmm0
0x18000248a  movups  xmmword ptr [rax+18h], xmm0
0x18000248e  movups  xmmword ptr [rax+28h], xmm0
0x180002492  movups  xmmword ptr [rax+38h], xmm0
0x180002496  mov     [rax+48h], r15
0x18000249a  mov     [rax+50h], r15
0x18000249e  mov     [rax+58h], r15
0x1800024a2  mov     [rax+60h], r15
0x1800024a6  mov     [rax+68h], r15
0x1800024aa  jmp     short loc_1800024AF
0x1800024ac  mov     rbx, r15
0x1800024af  mov     [rbp+var_18], rbx
0x1800024b3  test    rbx, rbx
0x1800024b6  jnz     short loc_1800024C2
0x1800024b8  mov     edi, 8007000Eh
0x1800024bd  jmp     loc_18000256E
0x1800024c2  mov     rdx, rdi
0x1800024c5  lea     rcx, [rbp+var_20]
0x1800024c9  call    ??$queryinterface_unique@UISequentialStream@@UIUnknown@@@tlx@@YAJPEAV?$unique_ptr@UISequentialStream@@Urelease_delete@tlx@@@utl@@AEAUIUnknown@@AEBU_GUID@@@Z; tlx::queryinterface_unique<ISequentialStream,IUnknown>(utl::unique_ptr<ISequentialStream,tlx::release_delete> *,IUnknown &,_GUID const &)
0x1800024ce  mov     edi, eax
0x1800024d0  test    eax, eax
0x1800024d2  js      loc_18000256E
0x1800024d8  mov     rdx, rsi
0x1800024db  lea     rcx, [rbp+var_28]
0x1800024df  call    ??$queryinterface_unique@UISequentialStream@@UIUnknown@@@tlx@@YAJPEAV?$unique_ptr@UISequentialStream@@Urelease_delete@tlx@@@utl@@AEAUIUnknown@@AEBU_GUID@@@Z; tlx::queryinterface_unique<ISequentialStream,IUnknown>(utl::unique_ptr<ISequentialStream,tlx::release_delete> *,IUnknown &,_GUID const &)
0x1800024e4  mov     edi, eax
0x1800024e6  test    eax, eax
0x1800024e8  js      loc_18000256E
0x1800024ee  mov     rcx, [rbp+var_28]
0x1800024f2  mov     rax, [rbp+var_20]
0x1800024f6  mov     [rbx], rax
0x1800024f9  mov     [rbx+8], rcx
0x1800024fd  mov     [rbx+10h], r14
0x180002501  mov     rcx, rbx; this
0x180002504  call    ?SetupKeys@CDumpWriter@@AEAAJXZ; CDumpWriter::SetupKeys(void)
0x180002509  mov     edi, eax
0x18000250b  test    eax, eax
0x18000250d  js      short loc_18000256E
0x18000250f  mov     rcx, rbx; this
0x180002512  call    ?WriteHeader@CDumpWriter@@AEAAJXZ; CDumpWriter::WriteHeader(void)
0x180002517  mov     edi, eax
0x180002519  test    eax, eax
0x18000251b  js      short loc_18000256E
0x18000251d  mov     [rbp+arg_18], r15d
0x180002521  mov     rcx, [rbx+8]
0x180002525  mov     rax, [rcx]
0x180002528  lea     r9, [rbp+arg_18]
0x18000252c  mov     esi, 21Bh
0x180002531  mov     r8d, esi
0x180002534  lea     rdx, aRsa1; "RSA1"
0x18000253b  mov     rax, [rax+20h]
0x18000253f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002544  mov     edi, eax
0x180002546  cmp     [rbp+arg_18], esi
0x180002549  jz      short loc_180002552
0x18000254b  mov     edi, 8000FFFFh
0x180002550  jmp     short loc_18000256E
0x180002552  test    eax, eax
0x180002554  js      short loc_18000256E
0x180002556  mov     rcx, rbx; this
0x180002559  call    ?WriteSymmetricKey@CDumpWriter@@AEAAJXZ; CDumpWriter::WriteSymmetricKey(void)
0x18000255e  mov     edi, eax
0x180002560  test    eax, eax
0x180002562  js      short loc_18000256E
0x180002564  mov     rcx, rbx; this
0x180002567  call    ?WriteDumpContents@CDumpWriter@@AEAAJXZ; CDumpWriter::WriteDumpContents(void)
0x18000256c  mov     edi, eax
0x18000256e  test    rbx, rbx
0x180002571  jz      short loc_180002589
0x180002573  mov     rcx, rbx; this
0x180002576  call    ??1CDumpWriter@@QEAA@XZ; CDumpWriter::~CDumpWriter(void)
0x18000257b  mov     edx, 70h ; 'p'; unsigned __int64
0x180002580  mov     rcx, rbx; void *
0x180002583  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002588  nop
0x180002589  mov     rcx, [rbp+var_28]
0x18000258d  test    rcx, rcx
0x180002590  jz      short loc_18000259F
0x180002592  mov     rax, [rcx]
0x180002595  mov     rax, [rax+10h]
0x180002599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000259e  nop
0x18000259f  mov     rcx, [rbp+var_20]
0x1800025a3  test    rcx, rcx
0x1800025a6  jz      short loc_1800025B5
0x1800025a8  mov     rax, [rcx]
0x1800025ab  mov     rax, [rax+10h]
0x1800025af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b4  nop
0x1800025b5  mov     eax, edi
0x1800025b7  add     rsp, 58h
0x1800025bb  pop     r15
0x1800025bd  pop     r14
0x1800025bf  pop     rdi
0x1800025c0  pop     rsi
0x1800025c1  pop     rbx
0x1800025c2  pop     rbp
0x1800025c3  retn
```
