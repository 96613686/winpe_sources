# WispLattice::AllocBuffers(ulong,ulong,ulong,ulong,ulong,ulong)

- ea: `0x18007f918`
- end: `0x18007fab7`
- name: `?AllocBuffers@WispLattice@@QEAAJKKKKKK@Z`
- size: `415`
- prototype: `__int64 __fastcall(WispLattice *__hidden this, SIZE_T cb, SIZE_T, SIZE_T, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800405a4`

## callees

- `0x18007f918`
- `0x180083580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fa12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fa24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fa3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f9fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fa12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fa24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007fa3d`

## pseudocode

```c
__int64 __fastcall WispLattice::AllocBuffers(
        WispLattice *this,
        SIZE_T cb,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned int *v7; // rax
  unsigned int v11; // ebp
  LPVOID v12; // rax
  _QWORD *v13; // rcx
  LPVOID v14; // rdx
  __int64 result; // rax

  v7 = *(unsigned int **)this;
  v11 = cb;
  if ( !*(_QWORD *)this )
    return 2147500035LL;
  if ( *v7 > 0x4924924 || v7[8] > 0x3FFFFFFF || v7[4] > 0xFFFFFFF || a5 > 0x7FFFFFF || a6 > 0x1FFFFFFF || a7 > 0x6666666 )
    return 2147549183LL;
  *(_QWORD *)(*(_QWORD *)this + 8LL) = CoTaskMemAlloc(56LL * *v7);
  *(_QWORD *)(*(_QWORD *)this + 40LL) = CoTaskMemAlloc(4LL * *(unsigned int *)(*(_QWORD *)this + 32LL));
  *(_QWORD *)(*(_QWORD *)this + 48LL) = CoTaskMemAlloc(4LL * *(unsigned int *)(*(_QWORD *)this + 32LL));
  *(_QWORD *)(*(_QWORD *)this + 24LL) = CoTaskMemAlloc(16LL * *(unsigned int *)(*(_QWORD *)this + 16LL));
  *((_QWORD *)this + 2) = CoTaskMemAlloc(a3);
  *((_QWORD *)this + 1) = CoTaskMemAlloc(v11);
  *((_QWORD *)this + 3) = CoTaskMemAlloc(a4);
  *((_DWORD *)this + 21) = a4;
  *((_QWORD *)this + 4) = CoTaskMemAlloc(32LL * a5);
  *((_QWORD *)this + 5) = CoTaskMemAlloc(8LL * a6);
  v12 = CoTaskMemAlloc(40LL * a7);
  v13 = *(_QWORD **)this;
  v14 = v12;
  *((_QWORD *)this + 6) = v12;
  if ( !v13[1]
    || !v13[5]
    || !v13[6]
    || !v13[3]
    || !*((_QWORD *)this + 2)
    || !*((_QWORD *)this + 1)
    || !*((_QWORD *)this + 3)
    || !*((_QWORD *)this + 4)
    || !*((_QWORD *)this + 5)
    || (result = 0, !v14) )
  {
    WispLattice::Reset(this);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18007f918  push    rbx
0x18007f91a  push    rbp
0x18007f91b  push    rsi
0x18007f91c  push    rdi
0x18007f91d  sub     rsp, 28h
0x18007f921  mov     rax, [rcx]
0x18007f924  mov     rbx, rcx
0x18007f927  mov     edi, r9d
0x18007f92a  mov     esi, r8d
0x18007f92d  mov     ebp, edx
0x18007f92f  test    rax, rax
0x18007f932  jz      loc_18007FAA9
0x18007f938  cmp     dword ptr [rax], 4924924h
0x18007f93e  ja      loc_18007FAA2
0x18007f944  cmp     dword ptr [rax+20h], 3FFFFFFFh
0x18007f94b  ja      loc_18007FAA2
0x18007f951  cmp     dword ptr [rax+10h], 0FFFFFFFh
0x18007f958  ja      loc_18007FAA2
0x18007f95e  cmp     [rsp+48h+arg_20], 7FFFFFFh
0x18007f966  ja      loc_18007FAA2
0x18007f96c  cmp     [rsp+48h+arg_28], 1FFFFFFFh
0x18007f974  ja      loc_18007FAA2
0x18007f97a  cmp     [rsp+48h+arg_30], 6666666h
0x18007f985  ja      loc_18007FAA2
0x18007f98b  mov     eax, [rax]
0x18007f98d  imul    rcx, rax, 38h ; '8'; cb
0x18007f991  call    cs:__imp_CoTaskMemAlloc
0x18007f997  mov     rcx, [rbx]
0x18007f99a  mov     [rcx+8], rax
0x18007f99e  mov     rax, [rbx]
0x18007f9a1  mov     ecx, [rax+20h]
0x18007f9a4  shl     rcx, 2; cb
0x18007f9a8  call    cs:__imp_CoTaskMemAlloc
0x18007f9ae  mov     rcx, [rbx]
0x18007f9b1  mov     [rcx+28h], rax
0x18007f9b5  mov     rax, [rbx]
0x18007f9b8  mov     ecx, [rax+20h]
0x18007f9bb  shl     rcx, 2; cb
0x18007f9bf  call    cs:__imp_CoTaskMemAlloc
0x18007f9c5  mov     rcx, [rbx]
0x18007f9c8  mov     [rcx+30h], rax
0x18007f9cc  mov     rax, [rbx]
0x18007f9cf  mov     ecx, [rax+10h]
0x18007f9d2  shl     rcx, 4; cb
0x18007f9d6  call    cs:__imp_CoTaskMemAlloc
0x18007f9dc  mov     rcx, [rbx]
0x18007f9df  mov     [rcx+18h], rax
0x18007f9e3  mov     ecx, esi; cb
0x18007f9e5  call    cs:__imp_CoTaskMemAlloc
0x18007f9eb  mov     ecx, ebp; cb
0x18007f9ed  mov     [rbx+10h], rax
0x18007f9f1  call    cs:__imp_CoTaskMemAlloc
0x18007f9f7  mov     ecx, edi; cb
0x18007f9f9  mov     [rbx+8], rax
0x18007f9fd  call    cs:__imp_CoTaskMemAlloc
0x18007fa03  mov     ecx, [rsp+48h+arg_20]
0x18007fa07  shl     rcx, 5; cb
0x18007fa0b  mov     [rbx+18h], rax
0x18007fa0f  mov     [rbx+54h], edi
0x18007fa12  call    cs:__imp_CoTaskMemAlloc
0x18007fa18  mov     ecx, [rsp+48h+arg_28]
0x18007fa1c  shl     rcx, 3; cb
0x18007fa20  mov     [rbx+20h], rax
0x18007fa24  call    cs:__imp_CoTaskMemAlloc
0x18007fa2a  mov     [rbx+28h], rax
0x18007fa2e  mov     eax, [rsp+48h+arg_30]
0x18007fa35  lea     rcx, [rax+rax*4]
0x18007fa39  shl     rcx, 3; cb
0x18007fa3d  call    cs:__imp_CoTaskMemAlloc
0x18007fa43  mov     rcx, [rbx]
0x18007fa46  mov     rdx, rax
0x18007fa49  mov     [rbx+30h], rax
0x18007fa4d  cmp     qword ptr [rcx+8], 0
0x18007fa52  jz      short loc_18007FA93
0x18007fa54  cmp     qword ptr [rcx+28h], 0
0x18007fa59  jz      short loc_18007FA93
0x18007fa5b  cmp     qword ptr [rcx+30h], 0
0x18007fa60  jz      short loc_18007FA93
0x18007fa62  cmp     qword ptr [rcx+18h], 0
0x18007fa67  jz      short loc_18007FA93
0x18007fa69  cmp     qword ptr [rbx+10h], 0
0x18007fa6e  jz      short loc_18007FA93
0x18007fa70  cmp     qword ptr [rbx+8], 0
0x18007fa75  jz      short loc_18007FA93
0x18007fa77  cmp     qword ptr [rbx+18h], 0
0x18007fa7c  jz      short loc_18007FA93
0x18007fa7e  cmp     qword ptr [rbx+20h], 0
0x18007fa83  jz      short loc_18007FA93
0x18007fa85  cmp     qword ptr [rbx+28h], 0
0x18007fa8a  jz      short loc_18007FA93
0x18007fa8c  xor     eax, eax
0x18007fa8e  test    rdx, rdx
0x18007fa91  jnz     short loc_18007FAAE
0x18007fa93  mov     rcx, rbx; this
0x18007fa96  call    ?Reset@WispLattice@@QEAAXXZ; WispLattice::Reset(void)
0x18007fa9b  mov     eax, 8007000Eh
0x18007faa0  jmp     short loc_18007FAAE
0x18007faa2  mov     eax, 8000FFFFh
0x18007faa7  jmp     short loc_18007FAAE
0x18007faa9  mov     eax, 80004003h
0x18007faae  add     rsp, 28h
0x18007fab2  pop     rdi
0x18007fab3  pop     rsi
0x18007fab4  pop     rbp
0x18007fab5  pop     rbx
0x18007fab6  retn
```
