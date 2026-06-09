# MbbAdapterGetRequestManager(_MINIPORT_ADAPTER_CONTEXT *)

- ea: `0x140003124`
- end: `0x1400031d0`
- name: `?MbbAdapterGetRequestManager@@YAPEAU_MBB_REQUEST_MANAGER@@PEAU_MINIPORT_ADAPTER_CONTEXT@@@Z`
- size: `172`
- prototype: `struct _MBB_REQUEST_MANAGER *__fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x140002024`
- `0x140002278`
- `0x1400024cc`
- `0x140003534`
- `0x140003744`
- `0x140003ab0`
- `0x140003d30`
- `0x140004004`
- `0x14000431c`
- `0x14000459c`
- `0x140004844`
- `0x14000ada0`
- `0x14000f478`
- `0x140011e94`
- `0x140013c08`
- `0x1400174d8`
- `0x14001ea18`

## callees

- `0x140003124`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400031b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400031b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003132`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003132`

## pseudocode

```c
struct _MBB_REQUEST_MANAGER *__fastcall MbbAdapterGetRequestManager(PKSPIN_LOCK SpinLock)
{
  KSPIN_LOCK v2; // rbp
  KIRQL v3; // al
  KSPIN_LOCK v4; // rdi
  char v5; // si

  v2 = 0;
  v3 = KeAcquireSpinLockRaiseToDpc(SpinLock);
  v4 = SpinLock[131];
  *((_BYTE *)SpinLock + 8) = v3;
  if ( v4 )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2528))(
      WdfDriverGlobals,
      *(_QWORD *)(v4 + 224));
    if ( *(_DWORD *)(v4 + 236) )
    {
      v5 = 0;
    }
    else
    {
      v5 = 1;
      ++*(_DWORD *)(v4 + 232);
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 2536))(
      WdfDriverGlobals,
      *(_QWORD *)(v4 + 224));
    if ( v5 )
      v2 = SpinLock[131];
  }
  KeReleaseSpinLock(SpinLock, *((_BYTE *)SpinLock + 8));
  return (struct _MBB_REQUEST_MANAGER *)v2;
}

```

## disassembly

```asm
0x140003124  push    rbx
0x140003126  push    rbp
0x140003127  push    rsi
0x140003128  push    rdi
0x140003129  sub     rsp, 28h
0x14000312d  mov     rbx, rcx
0x140003130  xor     ebp, ebp
0x140003132  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003139  nop     dword ptr [rax+rax+00h]
0x14000313e  mov     rdi, [rbx+418h]
0x140003145  mov     [rbx+8], al
0x140003148  test    rdi, rdi
0x14000314b  jz      short loc_1400031B1
0x14000314d  mov     rax, cs:WdfFunctions_01031
0x140003154  mov     rdx, [rdi+0E0h]
0x14000315b  mov     rcx, cs:WdfDriverGlobals
0x140003162  mov     rax, [rax+9E0h]
0x140003169  call    _guard_dispatch_icall
0x14000316e  cmp     [rdi+0ECh], ebp
0x140003174  jnz     short loc_140003181
0x140003176  lea     esi, [rbp+1]
0x140003179  add     [rdi+0E8h], esi
0x14000317f  jmp     short loc_140003184
0x140003181  xor     sil, sil
0x140003184  mov     rax, cs:WdfFunctions_01031
0x14000318b  mov     rdx, [rdi+0E0h]
0x140003192  mov     rcx, cs:WdfDriverGlobals
0x140003199  mov     rax, [rax+9E8h]
0x1400031a0  call    _guard_dispatch_icall
0x1400031a5  test    sil, sil
0x1400031a8  jz      short loc_1400031B1
0x1400031aa  mov     rbp, [rbx+418h]
0x1400031b1  mov     dl, [rbx+8]; NewIrql
0x1400031b4  mov     rcx, rbx; SpinLock
0x1400031b7  call    cs:__imp_KeReleaseSpinLock
0x1400031be  nop     dword ptr [rax+rax+00h]
0x1400031c3  mov     rax, rbp
0x1400031c6  add     rsp, 28h
0x1400031ca  pop     rdi
0x1400031cb  pop     rsi
0x1400031cc  pop     rbp
0x1400031cd  pop     rbx
0x1400031ce  retn
```
