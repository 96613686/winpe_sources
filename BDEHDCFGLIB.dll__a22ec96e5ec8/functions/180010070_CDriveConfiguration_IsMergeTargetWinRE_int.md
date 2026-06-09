# CDriveConfiguration::IsMergeTargetWinRE(int *)

- ea: `0x180010070`
- end: `0x18001009f`
- name: `?IsMergeTargetWinRE@CDriveConfiguration@@QEAAJPEAH@Z`
- size: `47`
- prototype: `__int64 __fastcall(const WCHAR *this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180007824`
- `0x180010070`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::IsMergeTargetWinRE(const WCHAR *this, int *a2)
{
  if ( !a2 )
    return 2147500035LL;
  if ( *((_DWORD *)this + 16) == 2 )
    return BdeCfgIsRecoveryPartitionType(this + 300, a2);
  return 3231711259LL;
}

```

## disassembly

```asm
0x180010070  sub     rsp, 28h
0x180010074  test    rdx, rdx
0x180010077  jnz     short loc_180010080
0x180010079  mov     eax, 80004003h
0x18001007e  jmp     short loc_18001009A
0x180010080  cmp     dword ptr [rcx+40h], 2
0x180010084  jz      short loc_18001008D
0x180010086  mov     eax, 0C0A0001Bh
0x18001008b  jmp     short loc_18001009A
0x18001008d  add     rcx, 258h; lpFileName
0x180010094  call    ?BdeCfgIsRecoveryPartitionType@@YAJPEBGPEAH@Z; BdeCfgIsRecoveryPartitionType(ushort const *,int *)
0x180010099  nop
0x18001009a  add     rsp, 28h
0x18001009e  retn
0x180014149  push    rbp
0x18001414b  sub     rsp, 20h
0x18001414f  mov     rbp, rdx
0x180014152  add     rsp, 20h
0x180014156  pop     rbp
0x180014157  retn
```
