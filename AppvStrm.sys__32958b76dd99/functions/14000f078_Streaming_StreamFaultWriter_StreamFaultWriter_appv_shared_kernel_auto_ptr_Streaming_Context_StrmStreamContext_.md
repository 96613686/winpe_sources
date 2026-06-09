# Streaming::StreamFaultWriter::StreamFaultWriter(appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &,_FLT_INSTANCE *,void *,__int64 &,ulong &,uint,long &)

- ea: `0x14000f078`
- end: `0x14000f19c`
- name: `??0StreamFaultWriter@Streaming@@QEAA@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@PEAU_FLT_INSTANCE@@PEAXAEA_JAEAKIAEAJ@Z`
- size: `292`
- prototype: `__int64 __fastcall(__int64, PFLT_CONTEXT *, struct _FLT_INSTANCE *, const void *, const wchar_t **, _DWORD *, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c4ac`

## callees

- `0x140004ab8`
- `0x140005e3c`
- `0x14000f078`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000f11a`
- `ntoskrnl!ExAllocatePool2` at `0x14000f11a`
- `FLTMGR!FltReferenceContext` at `0x14000f149`
- `FLTMGR!FltReferenceContext` at `0x14000f149`
- `FLTMGR!FltReleaseContext` at `0x14000f160`
- `FLTMGR!FltReleaseContext` at `0x14000f160`

## pseudocode

```c
__int64 __fastcall Streaming::StreamFaultWriter::StreamFaultWriter(
        __int64 a1,
        PFLT_CONTEXT *a2,
        struct _FLT_INSTANCE *a3,
        const void *a4,
        const wchar_t **a5,
        _DWORD *a6,
        int a7,
        int *a8)
{
  appv::shared::kernel::event *v12; // rcx
  const wchar_t *v13; // rdx
  int v14; // eax
  Streaming::InstanceContextFactory *v15; // rcx
  int Context; // eax
  void *Pool2; // rax
  PFLT_CONTEXT v18; // rdi

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 32) = *a6;
  v12 = (appv::shared::kernel::event *)(a1 + 40);
  *(_BYTE *)v12 = 0;
  *((_QWORD *)v12 + 1) = 0;
  *((_QWORD *)v12 + 2) = 0;
  *(_DWORD *)(a1 + 64) = a7;
  v13 = *a5;
  *(_QWORD *)(a1 + 24) = *a5;
  *(_DWORD *)(a1 + 36) = -1073741536;
  v14 = appv::shared::kernel::event::create(v12, v13, (bool)a3);
  *a8 = v14;
  if ( v14 >= 0 )
  {
    Context = Streaming::InstanceContextFactory::GetContext(v15, a3, (struct Streaming::InstanceContext *)(a1 + 8));
    *a8 = Context;
    if ( Context >= 0 )
    {
      Pool2 = (void *)ExAllocatePool2(256, (unsigned int)*a6, 1684432499);
      *(_QWORD *)(a1 + 16) = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, a4, (unsigned int)*a6);
        FltReferenceContext(*a2);
        v18 = *a2;
        if ( *(_QWORD *)a1 )
          FltReleaseContext(*(PFLT_CONTEXT *)a1);
        *(_QWORD *)a1 = v18;
      }
      else
      {
        *a8 = -1073741670;
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14000f078  mov     [rsp+arg_8], rbx
0x14000f07d  mov     [rsp+arg_10], rsi
0x14000f082  mov     [rsp+arg_0], rcx
0x14000f087  push    rdi
0x14000f088  push    r12
0x14000f08a  push    r13
0x14000f08c  push    r14
0x14000f08e  push    r15
0x14000f090  sub     rsp, 20h
0x14000f094  mov     r13, r9
0x14000f097  mov     r12, r8
0x14000f09a  mov     rsi, rdx
0x14000f09d  mov     rbx, rcx
0x14000f0a0  xor     edx, edx
0x14000f0a2  mov     [rcx], rdx
0x14000f0a5  mov     [rcx+8], rdx
0x14000f0a9  mov     [rcx+10h], rdx
0x14000f0ad  mov     r14, [rsp+48h+arg_28]
0x14000f0b2  mov     eax, [r14]
0x14000f0b5  mov     [rcx+20h], eax
0x14000f0b8  add     rcx, 28h ; '('; this
0x14000f0bc  mov     [rcx], dl
0x14000f0be  mov     [rcx+8], rdx
0x14000f0c2  mov     [rcx+10h], rdx
0x14000f0c6  mov     eax, [rsp+48h+arg_30]
0x14000f0cd  mov     [rbx+40h], eax
0x14000f0d0  mov     rax, [rsp+48h+arg_20]
0x14000f0d5  mov     rdx, [rax]; wchar_t *
0x14000f0d8  mov     [rbx+18h], rdx
0x14000f0dc  mov     dword ptr [rbx+24h], 0C0000120h
0x14000f0e3  call    ?create@event@kernel@shared@appv@@QEAAJPEB_W_N@Z; appv::shared::kernel::event::create(wchar_t const *,bool)
0x14000f0e8  mov     rdi, [rsp+48h+arg_38]
0x14000f0f0  mov     [rdi], eax
0x14000f0f2  test    eax, eax
0x14000f0f4  js      loc_14000F180
0x14000f0fa  lea     r8, [rbx+8]; struct Streaming::InstanceContext *
0x14000f0fe  mov     rdx, r12; struct _FLT_INSTANCE *
0x14000f101  call    ?GetContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContext(_FLT_INSTANCE *,Streaming::InstanceContext &)
0x14000f106  mov     [rdi], eax
0x14000f108  test    eax, eax
0x14000f10a  js      short loc_14000F180
0x14000f10c  mov     edx, [r14]
0x14000f10f  mov     ecx, 100h
0x14000f114  mov     r8d, 64666673h
0x14000f11a  call    cs:__imp_ExAllocatePool2
0x14000f121  nop     dword ptr [rax+rax+00h]
0x14000f126  mov     [rbx+10h], rax
0x14000f12a  test    rax, rax
0x14000f12d  jnz     short loc_14000F137
0x14000f12f  mov     dword ptr [rdi], 0C000009Ah
0x14000f135  jmp     short loc_14000F180
0x14000f137  mov     r8d, [r14]; Size
0x14000f13a  mov     rdx, r13; Src
0x14000f13d  mov     rcx, rax; void *
0x14000f140  call    memmove
0x14000f145  nop
0x14000f146  mov     rcx, [rsi]; Context
0x14000f149  call    cs:__imp_FltReferenceContext
0x14000f150  nop     dword ptr [rax+rax+00h]
0x14000f155  mov     rdi, [rsi]
0x14000f158  mov     rcx, [rbx]; Context
0x14000f15b  test    rcx, rcx
0x14000f15e  jz      short loc_14000F16C
0x14000f160  call    cs:__imp_FltReleaseContext
0x14000f167  nop     dword ptr [rax+rax+00h]
0x14000f16c  mov     [rbx], rdi
0x14000f16f  jmp     short loc_14000F180
0x14000f171  mov     rcx, [rsp+48h+arg_38]
0x14000f179  mov     [rcx], eax
0x14000f17b  mov     rbx, [rsp+48h+arg_0]
0x14000f180  mov     rax, rbx
0x14000f183  mov     rbx, [rsp+48h+arg_8]
0x14000f188  mov     rsi, [rsp+48h+arg_10]
0x14000f18d  add     rsp, 20h
0x14000f191  pop     r15
0x14000f193  pop     r14
0x14000f195  pop     r13
0x14000f197  pop     r12
0x14000f199  pop     rdi
0x14000f19a  retn
```
