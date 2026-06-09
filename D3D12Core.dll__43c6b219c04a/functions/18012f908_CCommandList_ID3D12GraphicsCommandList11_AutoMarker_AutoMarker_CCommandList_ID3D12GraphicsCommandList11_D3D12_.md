# CCommandList<ID3D12GraphicsCommandList11>::AutoMarker::AutoMarker(CCommandList<ID3D12GraphicsCommandList11> *,D3D12_MARKER_API)

- ea: `0x18012f908`
- end: `0x18012f981`
- name: `??0AutoMarker@?$CCommandList@UID3D12GraphicsCommandList11@@@@QEAA@PEAV1@W4D3D12_MARKER_API@@@Z`
- size: `121`
- prototype: ``
- caller_count: `72`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1801303f8`
- `0x1801306e0`
- `0x1801309c8`
- `0x180130cb0`
- `0x180239d44`
- `0x180239d68`
- `0x18023c704`
- `0x18023c928`
- `0x180249480`
- `0x180249590`
- `0x1802496a0`
- `0x180249780`
- `0x180249820`
- `0x1802498c0`
- `0x180249960`
- `0x180249a30`
- `0x18024a6e0`
- `0x18024abb0`
- `0x18024b550`
- `0x18024b810`
- `0x18024b940`
- `0x18024bae0`
- `0x18024be30`
- `0x18024bf80`
- `0x18024c0e0`
- `0x18024d7b0`
- `0x18024d8f0`
- `0x18024d970`
- `0x18024db80`
- `0x18024dc00`
- `0x18024e1d0`
- `0x18024e240`
- `0x18024e2f0`
- `0x18024e360`
- `0x18024e3d0`
- `0x18024e440`
- `0x18024e520`
- `0x18024e7d0`
- `0x18024e840`
- `0x18024e8b0`
- `0x18024e920`
- `0x18024ecb0`
- `0x18024ee80`
- `0x18024f260`
- `0x18024f3a0`
- `0x18024f4e0`
- `0x18024f620`
- `0x18024f7d0`
- `0x18024f850`
- `0x18024f930`

## callees

- `0x1800754d8`
- `0x18012f908`
- `0x180131070`
- `0x180131818`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012f951`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012f951`

## pseudocode

```c
_QWORD *__fastcall CCommandList<ID3D12GraphicsCommandList11>::AutoMarker::AutoMarker(
        _QWORD *a1,
        __int64 a2,
        enum D3D12_MARKER_API a3)
{
  SMarkerData *v3; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v7; // r9d
  union _LARGE_INTEGER v9; // [rsp+40h] [rbp+8h] BYREF

  v3 = (SMarkerData *)(a2 + 304);
  *a1 = a2;
  if ( *(_BYTE *)(a2 + 360) )
  {
    v9.QuadPart = 0;
    while ( !SMarkerData::CapacityForBatchedDataAndMatchingQPC(v3, &v9, a3) )
      CCastableCommandList<ID3D12VideoProcessCommandList4>::FlushMarkerData(*a1);
    CurrentThreadId = GetCurrentThreadId();
    SMarkerData::PushBackBatchedData(v3, a3, &v9, v7, CurrentThreadId);
    ++*((_QWORD *)v3 + 2);
  }
  return a1;
}

```

## disassembly

```asm
0x18012f908  mov     [rsp+arg_8], rbx
0x18012f90d  mov     [rsp+arg_10], rsi
0x18012f912  push    rdi
0x18012f913  sub     rsp, 30h
0x18012f917  lea     rbx, [rdx+130h]
0x18012f91e  mov     [rcx], rdx
0x18012f921  cmp     byte ptr [rbx+38h], 0
0x18012f925  mov     esi, r8d
0x18012f928  mov     rdi, rcx
0x18012f92b  jz      short loc_18012F96E
0x18012f92d  mov     qword ptr [rsp+38h+arg_0], 0
0x18012f936  jmp     short loc_18012F940
0x18012f938  mov     rcx, [rdi]
0x18012f93b  call    ?FlushMarkerData@?$CCastableCommandList@UID3D12VideoProcessCommandList4@@@@IEAAXXZ; CCastableCommandList<ID3D12VideoProcessCommandList4>::FlushMarkerData(void)
0x18012f940  lea     rdx, [rsp+38h+arg_0]; union _LARGE_INTEGER *
0x18012f945  mov     rcx, rbx; this
0x18012f948  call    ?CapacityForBatchedDataAndMatchingQPC@SMarkerData@@QEBA_NAEAT_LARGE_INTEGER@@I@Z; SMarkerData::CapacityForBatchedDataAndMatchingQPC(_LARGE_INTEGER &,uint)
0x18012f94d  test    al, al
0x18012f94f  jz      short loc_18012F938
0x18012f951  call    cs:__imp_GetCurrentThreadId
0x18012f957  lea     r8, [rsp+38h+arg_0]; union _LARGE_INTEGER *
0x18012f95c  mov     edx, esi; enum D3D12_MARKER_API
0x18012f95e  mov     rcx, rbx; this
0x18012f961  mov     [rsp+38h+var_18], eax; unsigned int
0x18012f965  call    ?PushBackBatchedData@SMarkerData@@QEAAPEAXW4D3D12_MARKER_API@@AEBT_LARGE_INTEGER@@IK@Z; SMarkerData::PushBackBatchedData(D3D12_MARKER_API,_LARGE_INTEGER const &,uint,ulong)
0x18012f96a  inc     qword ptr [rbx+10h]
0x18012f96e  mov     rbx, [rsp+38h+arg_8]
0x18012f973  mov     rax, rdi
0x18012f976  mov     rsi, [rsp+38h+arg_10]
0x18012f97b  add     rsp, 30h
0x18012f97f  pop     rdi
0x18012f980  retn
```
