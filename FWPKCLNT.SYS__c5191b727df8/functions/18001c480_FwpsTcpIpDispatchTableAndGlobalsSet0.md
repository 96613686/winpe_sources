# FwpsTcpIpDispatchTableAndGlobalsSet0

- ea: `0x18001c480`
- end: `0x18001c595`
- name: `FwpsTcpIpDispatchTableAndGlobalsSet0`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x18001c480`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001c563`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001c563`

## pseudocode

```c
__int64 *__fastcall FwpsTcpIpDispatchTableAndGlobalsSet0(_OWORD *a1, void *a2, ULONG a3)
{
  _OWORD *v3; // r9
  __int64 v4; // rax
  __int128 v5; // xmm1
  __int64 *result; // rax

  v3 = qword_180048208;
  v4 = 2;
  do
  {
    *v3 = *a1;
    v3[1] = a1[1];
    v3[2] = a1[2];
    v3[3] = a1[3];
    v3[4] = a1[4];
    v3[5] = a1[5];
    v3[6] = a1[6];
    v5 = a1[7];
    a1 += 8;
    v3[7] = v5;
    v3 += 8;
    --v4;
  }
  while ( v4 );
  *v3 = *a1;
  v3[1] = a1[1];
  v3[2] = a1[2];
  v3[3] = a1[3];
  v3[4] = a1[4];
  v3[5] = a1[5];
  v3[6] = a1[6];
  *((_QWORD *)v3 + 14) = *((_QWORD *)a1 + 14);
  WPP_MAIN_CB.DeviceExtension = a2;
  WPP_MAIN_CB.DeviceType = a3;
  ExInitializeNPagedLookasideList(&stru_180048240, 0, 0, 0x200u, 0x18u, 0x63707746u, 0);
  result = &qword_1800482C8;
  qword_1800482D0 = (__int64)&qword_1800482C8;
  qword_1800482C8 = (__int64)&qword_1800482C8;
  _InterlockedAdd(&gFwpTcpIp, 0x3FFFFFFFu);
  return result;
}

```

## disassembly

```asm
0x18001c480  sub     rsp, 48h
0x18001c484  mov     r9, cs:qword_180048208
0x18001c48b  mov     eax, 2
0x18001c490  lea     r10d, [rax+7Eh]
0x18001c494  movups  xmm0, xmmword ptr [rcx]
0x18001c497  movups  xmmword ptr [r9], xmm0
0x18001c49b  movups  xmm1, xmmword ptr [rcx+10h]
0x18001c49f  movups  xmmword ptr [r9+10h], xmm1
0x18001c4a4  movups  xmm0, xmmword ptr [rcx+20h]
0x18001c4a8  movups  xmmword ptr [r9+20h], xmm0
0x18001c4ad  movups  xmm1, xmmword ptr [rcx+30h]
0x18001c4b1  movups  xmmword ptr [r9+30h], xmm1
0x18001c4b6  movups  xmm0, xmmword ptr [rcx+40h]
0x18001c4ba  movups  xmmword ptr [r9+40h], xmm0
0x18001c4bf  movups  xmm1, xmmword ptr [rcx+50h]
0x18001c4c3  movups  xmmword ptr [r9+50h], xmm1
0x18001c4c8  movups  xmm0, xmmword ptr [rcx+60h]
0x18001c4cc  movups  xmmword ptr [r9+60h], xmm0
0x18001c4d1  movups  xmm1, xmmword ptr [rcx+70h]
0x18001c4d5  add     rcx, r10
0x18001c4d8  movups  xmmword ptr [r9+70h], xmm1
0x18001c4dd  add     r9, r10
0x18001c4e0  sub     rax, 1
0x18001c4e4  jnz     short loc_18001C494
0x18001c4e6  movups  xmm0, xmmword ptr [rcx]
0x18001c4e9  movups  xmmword ptr [r9], xmm0
0x18001c4ed  movups  xmm1, xmmword ptr [rcx+10h]
0x18001c4f1  movups  xmmword ptr [r9+10h], xmm1
0x18001c4f6  movups  xmm0, xmmword ptr [rcx+20h]
0x18001c4fa  movups  xmmword ptr [r9+20h], xmm0
0x18001c4ff  movups  xmm1, xmmword ptr [rcx+30h]
0x18001c503  movups  xmmword ptr [r9+30h], xmm1
0x18001c508  movups  xmm0, xmmword ptr [rcx+40h]
0x18001c50c  movups  xmmword ptr [r9+40h], xmm0
0x18001c511  movups  xmm1, xmmword ptr [rcx+50h]
0x18001c515  movups  xmmword ptr [r9+50h], xmm1
0x18001c51a  movups  xmm0, xmmword ptr [rcx+60h]
0x18001c51e  movups  xmmword ptr [r9+60h], xmm0
0x18001c523  mov     rax, [rcx+70h]
0x18001c527  lea     rcx, stru_180048240; Lookaside
0x18001c52e  mov     [r9+70h], rax
0x18001c532  xor     eax, eax
0x18001c534  mov     [rsp+48h+Depth], ax; Depth
0x18001c539  mov     r9d, 200h; Flags
0x18001c53f  mov     cs:WPP_MAIN_CB.DeviceExtension, rdx
0x18001c546  xor     edx, edx; Allocate
0x18001c548  mov     cs:WPP_MAIN_CB.DeviceType, r8d
0x18001c54f  xor     r8d, r8d; Free
0x18001c552  mov     [rsp+48h+Tag], 63707746h; Tag
0x18001c55a  mov     [rsp+48h+Size], 18h; Size
0x18001c563  call    cs:__imp_ExInitializeNPagedLookasideList
0x18001c56a  nop     dword ptr [rax+rax+00h]
0x18001c56f  lea     rax, qword_1800482C8
0x18001c576  mov     cs:qword_1800482D0, rax
0x18001c57d  mov     cs:qword_1800482C8, rax
0x18001c584  lock add cs:gFwpTcpIp, 3FFFFFFFh
0x18001c58f  add     rsp, 48h
0x18001c593  retn
```
