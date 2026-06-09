# FwpsL2DispatchTableAndGlobalsSet0

- ea: `0x18001c240`
- end: `0x18001c2ea`
- name: `FwpsL2DispatchTableAndGlobalsSet0`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, installer_update`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001c2a3`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001c2a3`

## pseudocode

```c
__int64 *__fastcall FwpsL2DispatchTableAndGlobalsSet0(_OWORD *a1)
{
  _OWORD *v1; // rax
  __int64 *result; // rax

  v1 = qword_180048108;
  *(_OWORD *)qword_180048108 = *a1;
  v1[1] = a1[1];
  v1[2] = a1[2];
  v1[3] = a1[3];
  v1[4] = a1[4];
  v1[5] = a1[5];
  ExInitializeNPagedLookasideList(&stru_180048140, 0, 0, 0x200u, 0x18u, 0x63707746u, 0);
  qword_1800481D0 = (__int64)&qword_1800481C8;
  qword_1800481C8 = (__int64)&qword_1800481C8;
  result = &qword_1800481D8;
  qword_1800481E0 = (__int64)&qword_1800481D8;
  qword_1800481D8 = (__int64)&qword_1800481D8;
  _InterlockedAdd(&gFwpL2, 0x3FFFFFFFu);
  return result;
}

```

## disassembly

```asm
0x18001c240  sub     rsp, 48h
0x18001c244  movups  xmm0, xmmword ptr [rcx]
0x18001c247  mov     rax, cs:qword_180048108
0x18001c24e  mov     r9d, 200h; Flags
0x18001c254  xor     r8d, r8d; Free
0x18001c257  xor     edx, edx; Allocate
0x18001c259  movups  xmmword ptr [rax], xmm0
0x18001c25c  movups  xmm1, xmmword ptr [rcx+10h]
0x18001c260  movups  xmmword ptr [rax+10h], xmm1
0x18001c264  movups  xmm0, xmmword ptr [rcx+20h]
0x18001c268  movups  xmmword ptr [rax+20h], xmm0
0x18001c26c  movups  xmm1, xmmword ptr [rcx+30h]
0x18001c270  movups  xmmword ptr [rax+30h], xmm1
0x18001c274  movups  xmm0, xmmword ptr [rcx+40h]
0x18001c278  movups  xmmword ptr [rax+40h], xmm0
0x18001c27c  movups  xmm1, xmmword ptr [rcx+50h]
0x18001c280  lea     rcx, stru_180048140; Lookaside
0x18001c287  movups  xmmword ptr [rax+50h], xmm1
0x18001c28b  xor     eax, eax
0x18001c28d  mov     [rsp+48h+Depth], ax; Depth
0x18001c292  mov     [rsp+48h+Tag], 63707746h; Tag
0x18001c29a  mov     [rsp+48h+Size], 18h; Size
0x18001c2a3  call    cs:__imp_ExInitializeNPagedLookasideList
0x18001c2aa  nop     dword ptr [rax+rax+00h]
0x18001c2af  lea     rax, qword_1800481C8
0x18001c2b6  mov     cs:qword_1800481D0, rax
0x18001c2bd  mov     cs:qword_1800481C8, rax
0x18001c2c4  lea     rax, qword_1800481D8
0x18001c2cb  mov     cs:qword_1800481E0, rax
0x18001c2d2  mov     cs:qword_1800481D8, rax
0x18001c2d9  lock add cs:gFwpL2, 3FFFFFFFh
0x18001c2e4  add     rsp, 48h
0x18001c2e8  retn
```
