# CMetadataRDFReaderWriter::HrSaveEx(IStream *,ulong,int,int)

- ea: `0x180004650`
- end: `0x180004740`
- name: `?HrSaveEx@CMetadataRDFReaderWriter@@UEAAJPEAUIStream@@KHH@Z`
- size: `240`
- prototype: `__int64 __usercall@<rax>(CMetadataRDFReaderWriter *__hidden this@<rcx>, struct IStream *@<rdx>, unsigned int@<r8d>, int@<r9d>, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180004650`
- `0x1800058c0`
- `0x1800058e0`
- `0x1800171c4`
- `0x18001a94c`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::HrSaveEx(
        CMetadataRDFReaderWriter *this,
        struct IStream *a2,
        __int64 a3,
        unsigned int a4,
        int a5)
{
  CMTALock *v5; // rsi
  unsigned int v9; // ebx
  int v10; // ecx
  int IsDeepMetadataDirty; // eax
  int v13; // [rsp+50h] [rbp+8h] BYREF

  v5 = (CMetadataRDFReaderWriter *)((char *)this + 40);
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 40));
  if ( !a2 )
  {
    v9 = -2147024809;
    if ( !g_doStackCaptures )
      goto LABEL_19;
    v10 = -2147024809;
    goto LABEL_4;
  }
  if ( a5 )
  {
    v13 = 0;
    IsDeepMetadataDirty = CMetadataHandler::IsDeepMetadataDirty(this, &v13);
    v9 = IsDeepMetadataDirty;
    if ( IsDeepMetadataDirty < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_19;
LABEL_14:
      v10 = IsDeepMetadataDirty;
LABEL_4:
      DoStackCapture(v10);
      goto LABEL_19;
    }
    if ( !v13 )
      goto LABEL_16;
    IsDeepMetadataDirty = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD))(*(_QWORD *)this + 232LL))(
                            this,
                            a4);
  }
  else
  {
    IsDeepMetadataDirty = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, struct IStream *, _QWORD))(*(_QWORD *)this + 240LL))(
                            this,
                            a2,
                            a4);
  }
  v9 = IsDeepMetadataDirty;
  if ( IsDeepMetadataDirty >= 0 )
  {
LABEL_16:
    if ( *((_QWORD *)this + 15) && a4 )
      (*(void (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD))(*(_QWORD *)this + 128LL))(this, 0);
    goto LABEL_19;
  }
  if ( g_doStackCaptures )
    goto LABEL_14;
LABEL_19:
  if ( v5 )
    CMTALock::Leave(v5);
  return v9;
}

```

## disassembly

```asm
0x180004650  push    rbx
0x180004652  push    rbp
0x180004653  push    rsi
0x180004654  push    rdi
0x180004655  sub     rsp, 28h
0x180004659  lea     rsi, [rcx+28h]
0x18000465d  mov     rdi, rcx
0x180004660  mov     rcx, rsi; this
0x180004663  mov     ebp, r9d
0x180004666  mov     rbx, rdx
0x180004669  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18000466e  test    rbx, rbx
0x180004671  jnz     short loc_180004691
0x180004673  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000467a  mov     ebx, 80070057h
0x18000467f  jz      loc_180004728
0x180004685  mov     ecx, ebx; int
0x180004687  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000468c  jmp     loc_180004728
0x180004691  cmp     [rsp+48h+arg_20], 0
0x180004696  mov     rcx, rdi; this
0x180004699  jz      short loc_1800046DD
0x18000469b  lea     rdx, [rsp+48h+arg_0]; int *
0x1800046a0  mov     [rsp+48h+arg_0], 0
0x1800046a8  call    ?IsDeepMetadataDirty@CMetadataHandler@@IEAAJPEAH@Z; CMetadataHandler::IsDeepMetadataDirty(int *)
0x1800046ad  mov     ebx, eax
0x1800046af  test    eax, eax
0x1800046b1  jns     short loc_1800046C0
0x1800046b3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800046ba  jnz     short loc_180004701
0x1800046bc  test    eax, eax
0x1800046be  js      short loc_180004728
0x1800046c0  cmp     [rsp+48h+arg_0], 0
0x1800046c5  jz      short loc_180004709
0x1800046c7  mov     rax, [rdi]
0x1800046ca  mov     edx, ebp
0x1800046cc  mov     rcx, rdi
0x1800046cf  mov     rax, [rax+0E8h]
0x1800046d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046db  jmp     short loc_1800046F2
0x1800046dd  mov     rax, [rdi]
0x1800046e0  mov     r8d, ebp
0x1800046e3  mov     rdx, rbx
0x1800046e6  mov     rax, [rax+0F0h]
0x1800046ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046f2  mov     ebx, eax
0x1800046f4  test    eax, eax
0x1800046f6  jns     short loc_180004709
0x1800046f8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800046ff  jz      short loc_180004705
0x180004701  mov     ecx, eax
0x180004703  jmp     short loc_180004687
0x180004705  test    eax, eax
0x180004707  js      short loc_180004728
0x180004709  cmp     qword ptr [rdi+78h], 0
0x18000470e  jz      short loc_180004728
0x180004710  test    ebp, ebp
0x180004712  jz      short loc_180004728
0x180004714  mov     rax, [rdi]
0x180004717  xor     edx, edx
0x180004719  mov     rcx, rdi
0x18000471c  mov     rax, [rax+80h]
0x180004723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004728  test    rsi, rsi
0x18000472b  jz      short loc_180004735
0x18000472d  mov     rcx, rsi; this
0x180004730  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180004735  mov     eax, ebx
0x180004737  add     rsp, 28h
0x18000473b  pop     rdi
0x18000473c  pop     rsi
0x18000473d  pop     rbp
0x18000473e  pop     rbx
0x18000473f  retn
```
