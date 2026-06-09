# appv::shared::kernel::auto_ptr<Streaming::StrmCreateContext,appv::shared::kernel::AllocDelete<Streaming::StrmCreateContext>>::~auto_ptr<Streaming::StrmCreateContext,appv::shared::kernel::AllocDelete<Streaming::StrmCreateContext>>(void)

- ea: `0x1400016fc`
- end: `0x140001763`
- name: `??1?$auto_ptr@UStrmCreateContext@Streaming@@U?$AllocDelete@UStrmCreateContext@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@QEAA@XZ`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001780`

## callees

- `0x1400016fc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000171c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001733`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001744`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000171c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001733`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001744`

## pseudocode

```c
void __fastcall appv::shared::kernel::auto_ptr<Streaming::StrmCreateContext,appv::shared::kernel::AllocDelete<Streaming::StrmCreateContext>>::~auto_ptr<Streaming::StrmCreateContext,appv::shared::kernel::AllocDelete<Streaming::StrmCreateContext>>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v3; // rcx
  void *v4; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = (void *)v1[6];
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
    v4 = (void *)v1[2];
    if ( v4 )
      ExFreePoolWithTag(v4, 0);
    ExFreePoolWithTag(v1, 0);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x1400016fc  mov     [rsp+arg_0], rbx
0x140001701  push    rdi
0x140001702  sub     rsp, 20h
0x140001706  mov     rbx, [rcx]
0x140001709  mov     rdi, rcx
0x14000170c  test    rbx, rbx
0x14000170f  jz      short loc_140001757
0x140001711  mov     rcx, [rbx+30h]; P
0x140001715  test    rcx, rcx
0x140001718  jz      short loc_140001728
0x14000171a  xor     edx, edx; Tag
0x14000171c  call    cs:__imp_ExFreePoolWithTag
0x140001723  nop     dword ptr [rax+rax+00h]
0x140001728  mov     rcx, [rbx+10h]; P
0x14000172c  test    rcx, rcx
0x14000172f  jz      short loc_14000173F
0x140001731  xor     edx, edx; Tag
0x140001733  call    cs:__imp_ExFreePoolWithTag
0x14000173a  nop     dword ptr [rax+rax+00h]
0x14000173f  xor     edx, edx; Tag
0x140001741  mov     rcx, rbx; P
0x140001744  call    cs:__imp_ExFreePoolWithTag
0x14000174b  nop     dword ptr [rax+rax+00h]
0x140001750  mov     qword ptr [rdi], 0
0x140001757  mov     rbx, [rsp+28h+arg_0]
0x14000175c  add     rsp, 20h
0x140001760  pop     rdi
0x140001761  retn
```
