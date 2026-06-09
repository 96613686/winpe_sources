# CDriveConfiguration::SetConfigurationStep(_BDECFG_STEP_ID)

- ea: `0x180010120`
- end: `0x180010191`
- name: `?SetConfigurationStep@CDriveConfiguration@@AEAAJW4_BDECFG_STEP_ID@@@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800101a0`

## callees

- `0x180010120`
- `0x180015010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180010139`
- `KERNEL32!EnterCriticalSection` at `0x180010139`
- `KERNEL32!LeaveCriticalSection` at `0x180010146`
- `KERNEL32!LeaveCriticalSection` at `0x180010146`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::SetConfigurationStep(__int64 a1, int a2)
{
  __int64 v3; // rsi

  v3 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  *(_DWORD *)(a1 + 16) = v3;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  if ( (_DWORD)v3 == 2 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 1256) + 24LL))(*(_QWORD *)(a1 + 1256));
  (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(a1 + 1256) + 16LL))(*(_QWORD *)(a1 + 1256), 1, v3);
  return 0;
}

```

## disassembly

```asm
0x180010120  mov     [rsp+arg_0], rbx
0x180010125  mov     [rsp+arg_8], rsi
0x18001012a  push    rdi
0x18001012b  sub     rsp, 20h
0x18001012f  mov     rdi, rcx
0x180010132  movsxd  rsi, edx
0x180010135  add     rcx, 18h; lpCriticalSection
0x180010139  call    cs:__imp_EnterCriticalSection
0x18001013f  lea     rcx, [rdi+18h]; lpCriticalSection
0x180010143  mov     [rdi+10h], esi
0x180010146  call    cs:__imp_LeaveCriticalSection
0x18001014c  cmp     esi, 2
0x18001014f  jnz     short loc_180010164
0x180010151  mov     rcx, [rdi+4E8h]
0x180010158  mov     rax, [rcx]
0x18001015b  mov     rax, [rax+18h]
0x18001015f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010164  mov     rcx, [rdi+4E8h]
0x18001016b  mov     r8, rsi
0x18001016e  mov     edx, 1
0x180010173  mov     rax, [rcx]
0x180010176  mov     rax, [rax+10h]
0x18001017a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001017f  mov     rbx, [rsp+28h+arg_0]
0x180010184  xor     eax, eax
0x180010186  mov     rsi, [rsp+28h+arg_8]
0x18001018b  add     rsp, 20h
0x18001018f  pop     rdi
0x180010190  retn
```
