# Streaming::Context::StreamingBitMap::CreateInstance(void *,ulong,appv::shared::kernel::auto_ptr<Streaming::Context::StreamingBitMap,appv::shared::kernel::AllocDelete<Streaming::Context::StreamingBitMap>> &)

- ea: `0x14000f7cc`
- end: `0x14000f89a`
- name: `?CreateInstance@StreamingBitMap@Context@Streaming@@SAJPEAXKAEAV?$auto_ptr@VStreamingBitMap@Context@Streaming@@U?$AllocDelete@VStreamingBitMap@Context@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(void *, unsigned int, Streaming::Context::StreamingBitMap **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b0bc`

## callees

- `0x14000f6e8`
- `0x14000f770`
- `0x14000f7cc`
- `0x14000f988`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f850`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f88a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f850`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f88a`
- `ntoskrnl!ExAllocatePool2` at `0x14000f7ff`
- `ntoskrnl!ExAllocatePool2` at `0x14000f7ff`

## pseudocode

```c
__int64 __fastcall Streaming::Context::StreamingBitMap::CreateInstance(
        void *a1,
        unsigned int a2,
        Streaming::Context::StreamingBitMap **a3)
{
  unsigned int v6; // edi
  Streaming::Context::StreamingBitMap *Pool2; // rax
  Streaming::Context::StreamingBitMap *v8; // rax
  Streaming::Context::StreamingBitMap *v9; // rbx
  int inited; // eax
  unsigned int v11; // esi
  Streaming::Context::StreamingBitMap *v13; // rdi
  int v14; // [rsp+58h] [rbp+20h] BYREF

  v6 = -1073741670;
  v14 = -1073741670;
  Pool2 = (Streaming::Context::StreamingBitMap *)ExAllocatePool2(256, 64, 1668507251);
  if ( !Pool2 )
    return v6;
  v8 = Streaming::Context::StreamingBitMap::StreamingBitMap(Pool2, &v14);
  v9 = v8;
  if ( !v8 )
    return v6;
  v6 = v14;
  if ( v14 < 0 )
  {
LABEL_6:
    Streaming::Context::StreamingBitMap::~StreamingBitMap(v9);
    ExFreePoolWithTag(v9, 0);
    return v6;
  }
  inited = Streaming::Context::StreamingBitMap::InitBitMap((PRTL_BITMAP)v8, a1, a2);
  v11 = inited;
  if ( inited < 0 )
  {
    v6 = inited;
    goto LABEL_6;
  }
  v13 = *a3;
  *a3 = v9;
  if ( v13 )
  {
    Streaming::Context::StreamingBitMap::~StreamingBitMap(v13);
    ExFreePoolWithTag(v13, 0);
  }
  return v11;
}

```

## disassembly

```asm
0x14000f7cc  mov     [rsp+arg_0], rbx
0x14000f7d1  mov     [rsp+arg_8], rbp
0x14000f7d6  push    rsi
0x14000f7d7  push    rdi
0x14000f7d8  push    r14
0x14000f7da  sub     rsp, 20h
0x14000f7de  mov     r14, r8
0x14000f7e1  mov     esi, edx
0x14000f7e3  mov     rbp, rcx
0x14000f7e6  mov     edi, 0C000009Ah
0x14000f7eb  mov     edx, 40h ; '@'
0x14000f7f0  mov     [rsp+38h+arg_18], edi
0x14000f7f4  mov     ecx, 100h
0x14000f7f9  mov     r8d, 63736673h
0x14000f7ff  call    cs:__imp_ExAllocatePool2
0x14000f806  nop     dword ptr [rax+rax+00h]
0x14000f80b  test    rax, rax
0x14000f80e  jz      short loc_14000F85C
0x14000f810  lea     rdx, [rsp+38h+arg_18]; int *
0x14000f815  mov     rcx, rax; this
0x14000f818  call    ??0StreamingBitMap@Context@Streaming@@QEAA@AEAJ@Z; Streaming::Context::StreamingBitMap::StreamingBitMap(long &)
0x14000f81d  mov     rbx, rax
0x14000f820  test    rax, rax
0x14000f823  jz      short loc_14000F85C
0x14000f825  mov     edi, [rsp+38h+arg_18]
0x14000f829  test    edi, edi
0x14000f82b  js      short loc_14000F843
0x14000f82d  mov     r8d, esi; unsigned int
0x14000f830  mov     rdx, rbp; void *
0x14000f833  mov     rcx, rax; BitMapHeader
0x14000f836  call    ?InitBitMap@StreamingBitMap@Context@Streaming@@QEAAJPEAXK@Z; Streaming::Context::StreamingBitMap::InitBitMap(void *,ulong)
0x14000f83b  mov     esi, eax
0x14000f83d  test    eax, eax
0x14000f83f  jns     short loc_14000F872
0x14000f841  mov     edi, eax
0x14000f843  mov     rcx, rbx; this
0x14000f846  call    ??1StreamingBitMap@Context@Streaming@@QEAA@XZ; Streaming::Context::StreamingBitMap::~StreamingBitMap(void)
0x14000f84b  xor     edx, edx; Tag
0x14000f84d  mov     rcx, rbx; P
0x14000f850  call    cs:__imp_ExFreePoolWithTag
0x14000f857  nop     dword ptr [rax+rax+00h]
0x14000f85c  mov     eax, edi
0x14000f85e  mov     rbx, [rsp+38h+arg_0]
0x14000f863  mov     rbp, [rsp+38h+arg_8]
0x14000f868  add     rsp, 20h
0x14000f86c  pop     r14
0x14000f86e  pop     rdi
0x14000f86f  pop     rsi
0x14000f870  retn
0x14000f872  mov     rdi, [r14]
0x14000f875  mov     [r14], rbx
0x14000f878  test    rdi, rdi
0x14000f87b  jz      short loc_14000F896
0x14000f87d  mov     rcx, rdi; this
0x14000f880  call    ??1StreamingBitMap@Context@Streaming@@QEAA@XZ; Streaming::Context::StreamingBitMap::~StreamingBitMap(void)
0x14000f885  xor     edx, edx; Tag
0x14000f887  mov     rcx, rdi; P
0x14000f88a  call    cs:__imp_ExFreePoolWithTag
0x14000f891  nop     dword ptr [rax+rax+00h]
0x14000f896  mov     eax, esi
0x14000f898  jmp     short loc_14000F85E
```
