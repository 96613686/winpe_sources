# ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)

- ea: `0x100421170`
- end: `0x100421238`
- name: `??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `545`
- callee_count: `1`
- tags: ``

## callers

- `0x100401840`
- `0x100401880`
- `0x1004018c0`
- `0x100401900`
- `0x100401980`
- `0x1004019e0`
- `0x100401a10`
- `0x100401a70`
- `0x100401b10`
- `0x100401e40`
- `0x100401ed0`
- `0x100401f70`
- `0x100401fd0`
- `0x1004021a0`
- `0x1004032e0`
- `0x100403590`
- `0x100403710`
- `0x100403880`
- `0x100403b50`
- `0x100403ec0`
- `0x1004041e0`
- `0x100404240`
- `0x100404cb0`
- `0x1004055f0`
- `0x100405d40`
- `0x100405df0`
- `0x100405e60`
- `0x1004061b0`
- `0x100406250`
- `0x1004062c0`
- `0x100408d50`
- `0x100408db0`
- `0x1004099b0`
- `0x100409b80`
- `0x100409c40`
- `0x10040a140`
- `0x10040a420`
- `0x10040a760`
- `0x10040a860`
- `0x10040acd0`
- `0x10040b0a0`
- `0x10040b560`
- `0x10040d510`
- `0x10040d590`
- `0x10040d5f0`
- `0x10040d670`
- `0x10040d800`
- `0x10040db80`
- `0x10040ddc0`
- `0x10040de70`

## callees

- `0x100421170`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004211c7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100421218`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004211c7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100421218`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(
        __int64 a1)
{
  __int64 i; // rbx
  void *v3; // rdx
  void *v4; // rdx

  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 4); i = (unsigned int)(i + 1) )
  {
    v3 = *(void **)(*(_QWORD *)(a1 + 8) + 8 * i);
    if ( g_SOSHost )
      (*(void (__fastcall **)(_QWORD, void *))(*g_SOSMemObj + 128LL))(g_SOSMemObj, v3);
    else
      free(v3);
    if ( (i & 0x3FFF) == 0x3FFF && OSYieldCallback )
      OSYieldCallback();
  }
  v4 = *(void **)(a1 + 8);
  if ( g_SOSHost )
  {
    if ( v4 )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(v4);
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x100421170  mov     [rsp+arg_0], rcx
0x100421175  push    rdi
0x100421176  sub     rsp, 30h
0x10042117a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100421183  mov     [rsp+38h+arg_8], rbx
0x100421188  mov     rdi, rcx
0x10042118b  xor     ebx, ebx
0x10042118d  cmp     [rcx+4], ebx
0x100421190  jbe     short loc_1004211F0
0x100421192  nop     dword ptr [rax+00h]
0x100421196  nop     word ptr [rax+rax+00000000h]
0x1004211a0  mov     rax, [rdi+8]
0x1004211a4  mov     rdx, [rax+rbx*8]
0x1004211a8  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x1004211b0  jz      short loc_1004211C4
0x1004211b2  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x1004211b9  mov     rax, [rcx]
0x1004211bc  call    qword ptr [rax+80h]
0x1004211c2  jmp     short loc_1004211CD
0x1004211c4  mov     rcx, rdx; Block
0x1004211c7  call    cs:__imp_free
0x1004211cd  mov     eax, ebx
0x1004211cf  and     eax, 3FFFh
0x1004211d4  cmp     eax, 3FFFh
0x1004211d9  jnz     short loc_1004211E9
0x1004211db  mov     rax, cs:?OSYieldCallback@@3P6AXXZEA; void (*OSYieldCallback)(void)
0x1004211e2  test    rax, rax
0x1004211e5  jz      short loc_1004211E9
0x1004211e7  call    rax ; void (*OSYieldCallback)(void)
0x1004211e9  inc     ebx
0x1004211eb  cmp     ebx, [rdi+4]
0x1004211ee  jb      short loc_1004211A0
0x1004211f0  mov     rdx, [rdi+8]
0x1004211f4  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x1004211fc  jz      short loc_100421215
0x1004211fe  test    rdx, rdx
0x100421201  jz      short loc_10042121E
0x100421203  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10042120a  mov     rax, [rcx]
0x10042120d  call    qword ptr [rax+80h]
0x100421213  jmp     short loc_10042121E
0x100421215  mov     rcx, rdx; Block
0x100421218  call    cs:__imp_free
0x10042121e  mov     qword ptr [rdi+8], 0
0x100421226  mov     qword ptr [rdi], 0
0x10042122d  mov     rbx, [rsp+38h+arg_8]
0x100421232  add     rsp, 30h
0x100421236  pop     rdi
0x100421237  retn
```
