# VfsCtxTableElementInsert

- ea: `0x140005400`
- end: `0x140005593`
- name: `VfsCtxTableElementInsert`
- size: `403`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table, PVOID Buffer, CLONG BufferSize, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005674`

## callees

- `0x140005400`
- `0x140005704`
- `0x1400057ec`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140005580`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140005580`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000543a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000543a`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400054af`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400054af`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000554a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400149cf`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000554a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400149cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005566`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005566`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000555a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000555a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005494`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005494`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005483`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005483`

## pseudocode

```c
__int64 __fastcall VfsCtxTableElementInsert(PRTL_AVL_TABLE Table, PVOID Buffer, CLONG BufferSize, _QWORD *a4)
{
  int v8; // eax
  struct _ERESOURCE *RightChild; // rbx
  char *inserted; // rax
  _DWORD *v12; // rdi
  int v13; // ebx
  unsigned __int8 NewElement[4]; // [rsp+20h] [rbp-28h] BYREF
  int v15; // [rsp+24h] [rbp-24h]
  char *v16; // [rsp+28h] [rbp-20h]

  NewElement[0] = 0;
  if ( (*(_DWORD *)&Table[1].BalancedRoot.Balance & 1) != 0 )
    v8 = ExAcquireRundownProtection((PEX_RUNDOWN_REF)&Table[1].BalancedRoot.LeftChild);
  else
    v8 = 1;
  if ( !v8 )
    return 3221225473LL;
  v15 = 0;
  v16 = 0;
  RightChild = (struct _ERESOURCE *)Table[1].BalancedRoot.RightChild;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(RightChild, 1u);
  inserted = (char *)RtlInsertElementGenericTableAvl(Table, Buffer, BufferSize, NewElement);
  v12 = inserted;
  v16 = inserted;
  if ( !inserted )
  {
    v13 = -1073741670;
    v15 = -1073741670;
    goto LABEL_18;
  }
  if ( !NewElement[0] )
  {
    v13 = -1073741771;
    v15 = -1073741771;
    v12 = 0;
    v16 = 0;
    goto LABEL_18;
  }
  if ( *(_DWORD *)&Table[1].BalancedRoot.Reserved[3] )
  {
    v13 = VfsCtxTableInitialize((PRTL_AVL_TABLE)(inserted + 96));
    if ( v13 >= 0 )
    {
      v12[20] = 1;
      v12[21] |= 1u;
      v13 = 0;
    }
    v15 = v13;
    if ( v13 < 0 )
      goto LABEL_18;
    ++v12[20];
  }
  else
  {
    v13 = VfsPkgCtxInitialize(inserted);
    v15 = v13;
    if ( v13 < 0 )
      goto LABEL_18;
    ++v12[8];
  }
  *a4 = v12;
LABEL_18:
  if ( v13 < 0 && v12 )
    RtlDeleteElementGenericTableAvl(Table, Buffer);
  ExReleaseResourceLite((PERESOURCE)Table[1].BalancedRoot.RightChild);
  KeLeaveCriticalRegion();
  if ( (*(_DWORD *)&Table[1].BalancedRoot.Balance & 1) != 0 )
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)&Table[1].BalancedRoot.LeftChild);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140005400  mov     rax, rsp
0x140005403  mov     [rax+18h], rbx
0x140005407  mov     [rax+20h], rsi
0x14000540b  mov     [rax+10h], rdx
0x14000540f  mov     [rax+8], rcx
0x140005413  push    rdi
0x140005414  push    r14
0x140005416  push    r15
0x140005418  sub     rsp, 30h
0x14000541c  mov     r15, r9
0x14000541f  mov     edi, r8d
0x140005422  mov     r14, rdx
0x140005425  mov     rsi, rcx
0x140005428  mov     byte ptr [rax-28h], 0
0x14000542c  mov     eax, [rcx+80h]
0x140005432  test    al, 1
0x140005434  jz      short loc_14000544B
0x140005436  add     rcx, 70h ; 'p'; RunRef
0x14000543a  call    cs:__imp_ExAcquireRundownProtection
0x140005441  nop     dword ptr [rax+rax+00h]
0x140005446  movzx   eax, al
0x140005449  jmp     short loc_140005450
0x14000544b  mov     eax, 1
0x140005450  test    eax, eax
0x140005452  jnz     short loc_14000546E
0x140005454  mov     eax, 0C0000001h
0x140005459  mov     rbx, [rsp+48h+arg_10]
0x14000545e  mov     rsi, [rsp+48h+arg_18]
0x140005463  add     rsp, 30h
0x140005467  pop     r15
0x140005469  pop     r14
0x14000546b  pop     rdi
0x14000546c  retn
0x14000546e  mov     [rsp+48h+var_24], 0
0x140005476  mov     [rsp+48h+var_20], 0
0x14000547f  mov     rbx, [rsi+78h]
0x140005483  call    cs:__imp_KeEnterCriticalRegion
0x14000548a  nop     dword ptr [rax+rax+00h]
0x14000548f  mov     dl, 1; Wait
0x140005491  mov     rcx, rbx; Resource
0x140005494  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000549b  nop     dword ptr [rax+rax+00h]
0x1400054a0  nop
0x1400054a1  lea     r9, [rsp+48h+NewElement]; NewElement
0x1400054a6  mov     r8d, edi; BufferSize
0x1400054a9  mov     rdx, r14; Buffer
0x1400054ac  mov     rcx, rsi; Table
0x1400054af  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1400054b6  nop     dword ptr [rax+rax+00h]
0x1400054bb  mov     rdi, rax
0x1400054be  mov     [rsp+48h+var_20], rax
0x1400054c3  test    rax, rax
0x1400054c6  jnz     short loc_1400054D3
0x1400054c8  mov     ebx, 0C000009Ah
0x1400054cd  mov     [rsp+48h+var_24], ebx
0x1400054d1  jmp     short loc_14000553B
0x1400054d3  cmp     [rsp+48h+NewElement], 0
0x1400054d8  jnz     short loc_1400054EC
0x1400054da  mov     ebx, 0C0000035h
0x1400054df  mov     [rsp+48h+var_24], ebx
0x1400054e3  xor     edi, edi
0x1400054e5  mov     [rsp+48h+var_20], rdi
0x1400054ea  jmp     short loc_14000553B
0x1400054ec  cmp     dword ptr [rsi+84h], 0
0x1400054f3  jnz     short loc_14000550C
0x1400054f5  mov     rcx, rdi
0x1400054f8  call    VfsPkgCtxInitialize
0x1400054fd  mov     ebx, eax
0x1400054ff  mov     [rsp+48h+var_24], eax
0x140005503  test    eax, eax
0x140005505  js      short loc_14000553B
0x140005507  inc     dword ptr [rdi+20h]
0x14000550a  jmp     short loc_140005538
0x14000550c  lea     rcx, [rax+60h]; Table
0x140005510  xor     r8d, r8d
0x140005513  xor     edx, edx
0x140005515  call    VfsCtxTableInitialize
0x14000551a  mov     ebx, eax
0x14000551c  test    eax, eax
0x14000551e  js      short loc_14000552D
0x140005520  mov     dword ptr [rdi+50h], 1
0x140005527  or      dword ptr [rdi+54h], 1
0x14000552b  xor     ebx, ebx
0x14000552d  mov     [rsp+48h+var_24], ebx
0x140005531  test    ebx, ebx
0x140005533  js      short loc_14000553B
0x140005535  inc     dword ptr [rdi+50h]
0x140005538  mov     [r15], rdi
0x14000553b  test    ebx, ebx
0x14000553d  jns     short loc_140005556
0x14000553f  test    rdi, rdi
0x140005542  jz      short loc_140005556
0x140005544  mov     rdx, r14; Buffer
0x140005547  mov     rcx, rsi; Table
0x14000554a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140005551  nop     dword ptr [rax+rax+00h]
0x140005556  mov     rcx, [rsi+78h]; Resource
0x14000555a  call    cs:__imp_ExReleaseResourceLite
0x140005561  nop     dword ptr [rax+rax+00h]
0x140005566  call    cs:__imp_KeLeaveCriticalRegion
0x14000556d  nop     dword ptr [rax+rax+00h]
0x140005572  mov     eax, [rsi+80h]
0x140005578  test    al, 1
0x14000557a  jz      short loc_14000558C
0x14000557c  lea     rcx, [rsi+70h]; RunRef
0x140005580  call    cs:__imp_ExReleaseRundownProtection
0x140005587  nop     dword ptr [rax+rax+00h]
0x14000558c  mov     eax, ebx
0x14000558e  jmp     loc_140005459
0x1400149b1  push    rbp
0x1400149b3  sub     rsp, 20h
0x1400149b7  mov     rbp, rdx
0x1400149ba  cmp     dword ptr [rbp+24h], 0
0x1400149be  jge     short loc_1400149DC
0x1400149c0  cmp     qword ptr [rbp+28h], 0
0x1400149c5  jz      short loc_1400149DC
0x1400149c7  mov     rdx, [rbp+58h]; Buffer
0x1400149cb  mov     rcx, [rbp+50h]; Table
0x1400149cf  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400149d6  nop     dword ptr [rax+rax+00h]
0x1400149db  nop
0x1400149dc  add     rsp, 20h
0x1400149e0  pop     rbp
0x1400149e1  retn
```
