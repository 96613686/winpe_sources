# TVector<TRefPtr<CMonitorNode>>::~TVector<TRefPtr<CMonitorNode>>(void)

- ea: `0x180009f38`
- end: `0x180009f7b`
- name: `??1?$TVector@V?$TRefPtr@VCMonitorNode@@@@@@QEAA@XZ`
- size: `67`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c09a`
- `0x18000c0ac`
- `0x18000c0d4`

## callees

- `0x180002498`
- `0x180009f38`

## import_xrefs

- `msvcrt!free` at `0x180009f6a`
- `msvcrt!free` at `0x180009f6a`

## pseudocode

```c
void __fastcall TVector<TRefPtr<CMonitorNode>>::~TVector<TRefPtr<CMonitorNode>>(__int64 a1)
{
  __int64 *i; // rbx
  void *v3; // rcx

  for ( i = *(__int64 **)(a1 + 8); i != *(__int64 **)(a1 + 16); ++i )
    TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(i);
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    free(v3);
}

```

## disassembly

```asm
0x180009f38  mov     [rsp+arg_0], rbx
0x180009f3d  push    rdi
0x180009f3e  sub     rsp, 20h
0x180009f42  mov     rbx, [rcx+8]
0x180009f46  mov     rdi, rcx
0x180009f49  cmp     rbx, [rcx+10h]
0x180009f4d  jz      short loc_180009F61
0x180009f4f  mov     rcx, rbx
0x180009f52  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x180009f57  add     rbx, 8
0x180009f5b  cmp     rbx, [rdi+10h]
0x180009f5f  jnz     short loc_180009F4F
0x180009f61  mov     rcx, [rdi+8]; Block
0x180009f65  test    rcx, rcx
0x180009f68  jz      short loc_180009F70
0x180009f6a  call    cs:__imp_free
0x180009f70  mov     rbx, [rsp+28h+arg_0]
0x180009f75  add     rsp, 20h
0x180009f79  pop     rdi
0x180009f7a  retn
```
