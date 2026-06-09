# BthServiceAllowedByPolicy

- ea: `0x1400071e0`
- end: `0x1400072a1`
- name: `BthServiceAllowedByPolicy`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x140019058`

## callees

- `0x1400071e0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400071f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007233`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400071f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007233`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007213`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007287`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007213`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007287`

## pseudocode

```c
__int64 __fastcall BthServiceAllowedByPolicy(_QWORD *a1)
{
  KIRQL v2; // al
  bool v3; // bl
  unsigned int v5; // ebx
  KIRQL v6; // al
  unsigned int v7; // ecx
  _QWORD *v8; // rdx

  v2 = KeAcquireSpinLockRaiseToDpc(&g_PolicyLock);
  v3 = dword_1400152AC != 0;
  KeReleaseSpinLock(&g_PolicyLock, v2);
  if ( !v3 )
    return 1;
  v5 = 0;
  v6 = KeAcquireSpinLockRaiseToDpc(&g_PolicyLock);
  v7 = 0;
  if ( dword_1400152AC )
  {
    while ( 1 )
    {
      v8 = (char *)xmmword_140015290 + 16 * v7;
      if ( *a1 == *v8 && a1[1] == v8[1] )
        break;
      if ( ++v7 >= dword_1400152AC )
        goto LABEL_9;
    }
    v5 = 1;
  }
LABEL_9:
  KeReleaseSpinLock(&g_PolicyLock, v6);
  return v5;
}

```

## disassembly

```asm
0x1400071e0  mov     [rsp+arg_0], rbx
0x1400071e5  push    rdi
0x1400071e6  sub     rsp, 20h
0x1400071ea  mov     rdi, rcx
0x1400071ed  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x1400071f4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400071fb  nop     dword ptr [rax+rax+00h]
0x140007200  cmp     cs:dword_1400152AC, 0
0x140007207  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x14000720e  mov     dl, al; NewIrql
0x140007210  setnz   bl
0x140007213  call    cs:__imp_KeReleaseSpinLock
0x14000721a  nop     dword ptr [rax+rax+00h]
0x14000721f  test    bl, bl
0x140007221  jnz     short loc_14000722A
0x140007223  mov     eax, 1
0x140007228  jmp     short loc_140007295
0x14000722a  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x140007231  xor     ebx, ebx
0x140007233  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000723a  nop     dword ptr [rax+rax+00h]
0x14000723f  mov     r8d, cs:dword_1400152AC
0x140007246  xor     ecx, ecx
0x140007248  mov     r9b, al
0x14000724b  test    r8d, r8d
0x14000724e  jz      short loc_14000727D
0x140007250  mov     rax, [rdi]
0x140007253  mov     edx, ecx
0x140007255  shl     rdx, 4
0x140007259  add     rdx, qword ptr cs:xmmword_140015290
0x140007260  cmp     rax, [rdx]
0x140007263  jnz     short loc_14000726F
0x140007265  mov     rax, [rdi+8]
0x140007269  cmp     rax, [rdx+8]
0x14000726d  jz      short loc_140007278
0x14000726f  inc     ecx
0x140007271  cmp     ecx, r8d
0x140007274  jb      short loc_140007250
0x140007276  jmp     short loc_14000727D
0x140007278  mov     ebx, 1
0x14000727d  mov     dl, r9b; NewIrql
0x140007280  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x140007287  call    cs:__imp_KeReleaseSpinLock
0x14000728e  nop     dword ptr [rax+rax+00h]
0x140007293  mov     eax, ebx
0x140007295  mov     rbx, [rsp+28h+arg_0]
0x14000729a  add     rsp, 20h
0x14000729e  pop     rdi
0x14000729f  retn
```
