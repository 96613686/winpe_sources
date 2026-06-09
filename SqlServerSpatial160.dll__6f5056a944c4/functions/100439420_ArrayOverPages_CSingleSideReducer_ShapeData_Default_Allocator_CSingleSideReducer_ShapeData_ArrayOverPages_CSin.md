# ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(void)

- ea: `0x100439420`
- end: `0x1004394e8`
- name: `??1?$ArrayOverPages@UShapeData@CSingleSideReducer@@V?$Default_Allocator@UShapeData@CSingleSideReducer@@@@@@QEAA@XZ`
- size: `200`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x100437180`
- `0x1004373d0`
- `0x100437700`
- `0x100476dcc`
- `0x100476e28`
- `0x100476e50`

## callees

- `0x100439420`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x100439477`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004394c8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100439477`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004394c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(
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
0x100439420  mov     [rsp+arg_0], rcx
0x100439425  push    rdi
0x100439426  sub     rsp, 30h
0x10043942a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100439433  mov     [rsp+38h+arg_8], rbx
0x100439438  mov     rdi, rcx
0x10043943b  xor     ebx, ebx
0x10043943d  cmp     [rcx+4], ebx
0x100439440  jbe     short loc_1004394A0
0x100439442  nop     dword ptr [rax+00h]
0x100439446  nop     word ptr [rax+rax+00000000h]
0x100439450  mov     rax, [rdi+8]
0x100439454  mov     rdx, [rax+rbx*8]
0x100439458  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x100439460  jz      short loc_100439474
0x100439462  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100439469  mov     rax, [rcx]
0x10043946c  call    qword ptr [rax+80h]
0x100439472  jmp     short loc_10043947D
0x100439474  mov     rcx, rdx; Block
0x100439477  call    cs:__imp_free
0x10043947d  mov     eax, ebx
0x10043947f  and     eax, 3FFFh
0x100439484  cmp     eax, 3FFFh
0x100439489  jnz     short loc_100439499
0x10043948b  mov     rax, cs:?OSYieldCallback@@3P6AXXZEA; void (*OSYieldCallback)(void)
0x100439492  test    rax, rax
0x100439495  jz      short loc_100439499
0x100439497  call    rax ; void (*OSYieldCallback)(void)
0x100439499  inc     ebx
0x10043949b  cmp     ebx, [rdi+4]
0x10043949e  jb      short loc_100439450
0x1004394a0  mov     rdx, [rdi+8]
0x1004394a4  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x1004394ac  jz      short loc_1004394C5
0x1004394ae  test    rdx, rdx
0x1004394b1  jz      short loc_1004394CE
0x1004394b3  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x1004394ba  mov     rax, [rcx]
0x1004394bd  call    qword ptr [rax+80h]
0x1004394c3  jmp     short loc_1004394CE
0x1004394c5  mov     rcx, rdx; Block
0x1004394c8  call    cs:__imp_free
0x1004394ce  mov     qword ptr [rdi+8], 0
0x1004394d6  mov     qword ptr [rdi], 0
0x1004394dd  mov     rbx, [rsp+38h+arg_8]
0x1004394e2  add     rsp, 30h
0x1004394e6  pop     rdi
0x1004394e7  retn
```
