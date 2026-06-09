# FreeDeviceServiceState(_MBB_DS_STATE *)

- ea: `0x140001f90`
- end: `0x14000201b`
- name: `?FreeDeviceServiceState@@YAXPEAU_MBB_DS_STATE@@@Z`
- size: `139`
- prototype: `void __fastcall(struct _MBB_DS_STATE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000ca94`
- `0x14002d460`

## callees

- `0x140001f90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001fa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001fdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001ffd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001fa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001fdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001ffd`

## pseudocode

```c
void __fastcall FreeDeviceServiceState(struct _MBB_DS_STATE *a1)
{
  void *v2; // rcx
  __int64 i; // rdi
  __int64 v4; // rbp
  void *v5; // rcx

  v2 = (void *)*((_QWORD *)a1 + 3);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *((_QWORD *)a1 + 3) = 0;
  }
  if ( *((_QWORD *)a1 + 1) )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)a1; i = (unsigned int)(i + 1) )
    {
      v4 = *((_QWORD *)a1 + 1);
      v5 = *(void **)(v4 + 40 * i + 32);
      if ( v5 )
      {
        ExFreePoolWithTag(v5, 0);
        *(_QWORD *)(v4 + 40 * i + 32) = 0;
      }
    }
    ExFreePoolWithTag(*((PVOID *)a1 + 1), 0);
    *((_QWORD *)a1 + 1) = 0;
  }
}

```

## disassembly

```asm
0x140001f90  push    rbx
0x140001f92  push    rbp
0x140001f93  push    rsi
0x140001f94  push    rdi
0x140001f95  sub     rsp, 28h
0x140001f99  mov     rbx, rcx
0x140001f9c  mov     rcx, [rcx+18h]; P
0x140001fa0  test    rcx, rcx
0x140001fa3  jz      short loc_140001FBB
0x140001fa5  xor     edx, edx; Tag
0x140001fa7  call    cs:__imp_ExFreePoolWithTag
0x140001fae  nop     dword ptr [rax+rax+00h]
0x140001fb3  mov     qword ptr [rbx+18h], 0
0x140001fbb  cmp     qword ptr [rbx+8], 0
0x140001fc0  jz      short loc_140002011
0x140001fc2  xor     edi, edi
0x140001fc4  cmp     [rbx], edi
0x140001fc6  jbe     short loc_140001FF7
0x140001fc8  mov     rbp, [rbx+8]
0x140001fcc  lea     rsi, [rdi+rdi*4]
0x140001fd0  mov     rcx, [rbp+rsi*8+20h]; P
0x140001fd5  test    rcx, rcx
0x140001fd8  jz      short loc_140001FF1
0x140001fda  xor     edx, edx; Tag
0x140001fdc  call    cs:__imp_ExFreePoolWithTag
0x140001fe3  nop     dword ptr [rax+rax+00h]
0x140001fe8  mov     qword ptr [rbp+rsi*8+20h], 0
0x140001ff1  inc     edi
0x140001ff3  cmp     edi, [rbx]
0x140001ff5  jb      short loc_140001FC8
0x140001ff7  mov     rcx, [rbx+8]; P
0x140001ffb  xor     edx, edx; Tag
0x140001ffd  call    cs:__imp_ExFreePoolWithTag
0x140002004  nop     dword ptr [rax+rax+00h]
0x140002009  mov     qword ptr [rbx+8], 0
0x140002011  add     rsp, 28h
0x140002015  pop     rdi
0x140002016  pop     rsi
0x140002017  pop     rbp
0x140002018  pop     rbx
0x140002019  retn
```
