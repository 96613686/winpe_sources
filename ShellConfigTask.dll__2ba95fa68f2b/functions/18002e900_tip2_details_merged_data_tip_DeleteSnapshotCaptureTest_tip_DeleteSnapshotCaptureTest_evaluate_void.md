# tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::evaluate(void)

- ea: `0x18002e900`
- end: `0x18002e9a3`
- name: `?evaluate@?$merged_data@U_tip_DeleteSnapshotCaptureTest@@U1@@details@tip2@@EEAAXXZ`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002e900`

## string_xrefs

- `0x18002e90c`: `reason::failed_to_delete_snapshot_capture`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_DeleteSnapshotCaptureTest,_tip_DeleteSnapshotCaptureTest>::evaluate(
        __int64 a1)
{
  const char *v1; // rax
  char v2; // r8
  const char *v3; // r9
  __int64 result; // rax

  if ( *(int *)(a1 + 272) >= 0 )
  {
    result = *(_QWORD *)(a1 + 264);
    if ( (*(_DWORD *)(result + 56) & 0x200) != 0 )
    {
      if ( *(_BYTE *)(result + 152) )
        return result;
      *(_BYTE *)(result + 152) = 1;
      *(_WORD *)(result + 154) = 0x8000;
    }
    else
    {
      if ( *(_BYTE *)(result + 152) )
        return result;
      *(_BYTE *)(result + 152) = 3;
      *(_WORD *)(result + 154) = 16385;
    }
    *(_QWORD *)(result + 160) = 0;
  }
  else
  {
    v1 = "reason::failed_to_delete_snapshot_capture";
    v2 = 114;
    v3 = "reason::failed_to_delete_snapshot_capture";
    do
    {
      ++v1;
      if ( v2 == 58 )
        v3 = v1;
      v2 = *v1;
    }
    while ( *v1 );
    result = *(_QWORD *)(a1 + 264);
    if ( !*(_BYTE *)(result + 152) )
    {
      *(_BYTE *)(result + 152) = 3;
      *(_WORD *)(result + 154) = 1;
      *(_QWORD *)(result + 160) = v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002e900  xor     r10d, r10d
0x18002e903  cmp     [rcx+110h], r10d
0x18002e90a  jge     short loc_18002E957
0x18002e90c  lea     rax, aReasonFailedTo_1; "reason::failed_to_delete_snapshot_captu"...
0x18002e913  mov     r8b, 72h ; 'r'
0x18002e916  mov     r9, rax
0x18002e919  lea     edx, [r10+1]
0x18002e91d  add     rax, rdx
0x18002e920  cmp     r8b, 3Ah ; ':'
0x18002e924  jnz     short loc_18002E929
0x18002e926  mov     r9, rax
0x18002e929  mov     r8b, [rax]
0x18002e92c  test    r8b, r8b
0x18002e92f  jnz     short loc_18002E91D
0x18002e931  mov     rax, [rcx+108h]
0x18002e938  cmp     [rax+98h], r10b
0x18002e93f  jnz     short locret_18002E9A2
0x18002e941  mov     byte ptr [rax+98h], 3
0x18002e948  mov     [rax+9Ah], dx
0x18002e94f  mov     [rax+0A0h], r9
0x18002e956  retn
0x18002e957  mov     rax, [rcx+108h]
0x18002e95e  test    dword ptr [rax+38h], 200h
0x18002e965  jnz     short loc_18002E982
0x18002e967  cmp     [rax+98h], r10b
0x18002e96e  jnz     short locret_18002E9A2
0x18002e970  mov     byte ptr [rax+98h], 3
0x18002e977  mov     word ptr [rax+9Ah], 4001h
0x18002e980  jmp     short loc_18002E99B
0x18002e982  cmp     [rax+98h], r10b
0x18002e989  jnz     short locret_18002E9A2
0x18002e98b  mov     byte ptr [rax+98h], 1
0x18002e992  mov     word ptr [rax+9Ah], 8000h
0x18002e99b  mov     [rax+0A0h], r10
0x18002e9a2  retn
```
