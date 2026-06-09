# CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>(void)

- ea: `0x10041e710`
- end: `0x10041e763`
- name: `??1?$CAutoArray@PEAVCLineSegmentIntersection@RobustIntersections@@$0A@V?$SOS_Or_CRT_Allocator@PEAVCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ`
- size: `83`
- prototype: ``
- caller_count: `140`
- callee_count: `1`
- tags: ``

## callers

- `0x10046a38c`
- `0x10046a961`
- `0x10046a9f4`
- `0x10046ab54`
- `0x10046ae24`
- `0x10046aec7`
- `0x10046b094`
- `0x10046b137`
- `0x10046b520`
- `0x10046b9dc`
- `0x10046ba0c`
- `0x10046ba30`
- `0x10046ba5c`
- `0x10046bbec`
- `0x10046bc28`
- `0x10046bc5c`
- `0x10046bd6c`
- `0x10046bd7f`
- `0x10046bd92`
- `0x10046bdec`
- `0x10046bdff`
- `0x10046be12`
- `0x10046c069`
- `0x10046c0ee`
- `0x10046c17c`
- `0x10046c18c`
- `0x10046c19c`
- `0x10046c1ec`
- `0x10046c2a8`
- `0x10046c2b4`
- `0x10046c2f0`
- `0x10046c7c0`
- `0x10046c7dc`
- `0x10046ce58`
- `0x10046ce70`
- `0x10046ce90`
- `0x10046cebc`
- `0x10046cecc`
- `0x10046cf1c`
- `0x10046cf2c`
- `0x10046cf58`
- `0x10046cfcf`
- `0x10046d03e`
- `0x10046d18c`
- `0x10046d7ac`
- `0x10046d7bc`
- `0x10046dcb1`
- `0x10046df7c`
- `0x10046e208`
- `0x10046e224`

## callees

- `0x10041e710`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x10041e74e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10041e74e`

## pseudocode

```c
__int64 __fastcall CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>::~CAutoArray<RobustIntersections::CLineSegmentIntersection *,0,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection *>>(
        _QWORD *a1)
{
  void *v2; // rdx
  __int64 result; // rax

  v2 = (void *)a1[1];
  if ( g_SOSHost )
  {
    if ( v2 )
    {
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
      result = 0;
      a1[1] = 0;
      *a1 = 0;
      return result;
    }
  }
  else
  {
    free(v2);
  }
  result = 0;
  a1[1] = 0;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x10041e710  push    rbx
0x10041e712  sub     rsp, 20h
0x10041e716  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10041e71e  mov     rbx, rcx
0x10041e721  mov     rdx, [rcx+8]
0x10041e725  jz      short loc_10041E74B
0x10041e727  test    rdx, rdx
0x10041e72a  jz      short loc_10041E754
0x10041e72c  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10041e733  mov     rax, [rcx]
0x10041e736  call    qword ptr [rax+80h]
0x10041e73c  xor     eax, eax
0x10041e73e  mov     [rbx+8], rax
0x10041e742  mov     [rbx], rax
0x10041e745  add     rsp, 20h
0x10041e749  pop     rbx
0x10041e74a  retn
0x10041e74b  mov     rcx, rdx; Block
0x10041e74e  call    cs:__imp_free
0x10041e754  xor     eax, eax
0x10041e756  mov     [rbx+8], rax
0x10041e75a  mov     [rbx], rax
0x10041e75d  add     rsp, 20h
0x10041e761  pop     rbx
0x10041e762  retn
```
