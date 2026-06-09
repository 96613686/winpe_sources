# CfpReferenceSyncRoot

- ea: `0x18000b218`
- end: `0x18000b27d`
- name: `CfpReferenceSyncRoot`
- size: `101`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1800031d0`
- `0x180005710`
- `0x180005ba0`
- `0x180005f20`
- `0x180007cf0`
- `0x18000b8e0`
- `0x18000eb80`
- `0x180018404`

## callees

- `0x18000b218`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000b26e`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000b26e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000b22b`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000b22b`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000b23d`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000b23d`

## pseudocode

```c
volatile signed __int64 *__fastcall CfpReferenceSyncRoot(volatile signed __int64 *a1)
{
  volatile signed __int64 *v1; // rbx
  volatile signed __int64 *Buffer; // [rsp+30h] [rbp+8h] BYREF

  Buffer = a1;
  v1 = 0;
  RtlAcquireSRWLockShared(&qword_180028CF8);
  if ( RtlLookupElementGenericTableAvl(&stru_180028C90, &Buffer) )
  {
    v1 = Buffer;
    if ( _InterlockedIncrement64(Buffer) <= 1 )
      __fastfail(0xEu);
  }
  RtlReleaseSRWLockShared(&qword_180028CF8);
  return v1;
}

```

## disassembly

```asm
0x18000b218  mov     [rsp+Buffer], rcx
0x18000b21d  push    rbx
0x18000b21e  sub     rsp, 20h
0x18000b222  lea     rcx, qword_180028CF8
0x18000b229  xor     ebx, ebx
0x18000b22b  call    cs:__imp_RtlAcquireSRWLockShared
0x18000b231  lea     rdx, [rsp+28h+Buffer]; Buffer
0x18000b236  lea     rcx, stru_180028C90; Table
0x18000b23d  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000b243  test    rax, rax
0x18000b246  jz      short loc_18000B267
0x18000b248  mov     rbx, [rsp+28h+Buffer]
0x18000b24d  mov     edx, 1
0x18000b252  lock xadd [rbx], rdx
0x18000b257  inc     rdx
0x18000b25a  cmp     rdx, 1
0x18000b25e  jg      short loc_18000B267
0x18000b260  mov     ecx, 0Eh
0x18000b265  int     29h; Win8: RtlFailFast(ecx)
0x18000b267  lea     rcx, qword_180028CF8
0x18000b26e  call    cs:__imp_RtlReleaseSRWLockShared
0x18000b274  mov     rax, rbx
0x18000b277  add     rsp, 20h
0x18000b27b  pop     rbx
0x18000b27c  retn
```
