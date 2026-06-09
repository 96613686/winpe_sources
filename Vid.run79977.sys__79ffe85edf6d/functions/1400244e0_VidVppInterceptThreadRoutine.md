# VidVppInterceptThreadRoutine

- ea: `0x1400244e0`
- end: `0x1400245e5`
- name: `VidVppInterceptThreadRoutine`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001a20`
- `0x140021c60`
- `0x1400244e0`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140024538`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140024538`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400245a8`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400245a8`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400245c0`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400245c0`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x140024544`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x140024563`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x140024544`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x140024563`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024583`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024583`

## pseudocode

```c
NTSTATUS __fastcall VidVppInterceptThreadRoutine(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v4; // rdx
  _GROUP_AFFINITY Affinity; // [rsp+30h] [rbp-28h] BYREF

  v1 = *((unsigned __int8 *)a1 + 12);
  v2 = *a1;
  Affinity = 0;
  Affinity.Group = *(_WORD *)(v2 + 16 * v1 + 2184);
  Affinity.Mask = *(_QWORD *)(v2 + 16 * (v1 + 136));
  KeSetSystemGroupAffinityThread(&Affinity, 0);
  KeReenterRetpolinedCode();
  while ( 1 )
  {
    KeWaitForSingleObject(a1 + 44, Executive, 0, 0, 0);
    if ( *((_DWORD *)a1 + 94) )
      break;
    LOBYTE(v4) = 1;
    VidInterceptProcess(a1, v4);
    KeReenterRetpolinedCode();
  }
  if ( *((_DWORD *)a1 + 98) )
  {
    KeUnstackDetachProcess((PRKAPC_STATE)(a1 + 50));
    *((_DWORD *)a1 + 98) = 0;
  }
  return PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x1400244e0  mov     [rsp+arg_8], rbx
0x1400244e5  push    rdi
0x1400244e6  sub     rsp, 50h
0x1400244ea  mov     rax, cs:__security_cookie
0x1400244f1  xor     rax, rsp
0x1400244f4  mov     [rsp+58h+var_18], rax
0x1400244f9  movzx   edx, byte ptr [rcx+0Ch]
0x1400244fd  xorps   xmm0, xmm0
0x140024500  mov     r8, [rcx]
0x140024503  mov     eax, edx
0x140024505  add     rax, rax
0x140024508  mov     rbx, rcx
0x14002450b  movups  xmmword ptr [rsp+58h+Affinity.Mask], xmm0
0x140024510  lea     rcx, [rsp+58h+Affinity]; Affinity
0x140024515  movzx   eax, word ptr [r8+rax*8+888h]
0x14002451e  mov     [rsp+58h+Affinity.Group], ax
0x140024523  lea     rax, [rdx+88h]
0x14002452a  add     rax, rax
0x14002452d  xor     edx, edx; PreviousAffinity
0x14002452f  mov     rax, [r8+rax*8]
0x140024533  mov     [rsp+58h+Affinity.Mask], rax
0x140024538  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14002453f  nop     dword ptr [rax+rax+00h]
0x140024544  call    cs:__imp_KeReenterRetpolinedCode
0x14002454b  nop     dword ptr [rax+rax+00h]
0x140024550  lea     rdi, [rbx+160h]
0x140024557  jmp     short loc_14002456F
0x140024559  mov     dl, 1
0x14002455b  mov     rcx, rbx
0x14002455e  call    VidInterceptProcess
0x140024563  call    cs:__imp_KeReenterRetpolinedCode
0x14002456a  nop     dword ptr [rax+rax+00h]
0x14002456f  xor     r9d, r9d; Alertable
0x140024572  mov     [rsp+58h+Timeout], 0; Timeout
0x14002457b  xor     r8d, r8d; WaitMode
0x14002457e  xor     edx, edx; WaitReason
0x140024580  mov     rcx, rdi; Object
0x140024583  call    cs:__imp_KeWaitForSingleObject
0x14002458a  nop     dword ptr [rax+rax+00h]
0x14002458f  cmp     dword ptr [rbx+178h], 0
0x140024596  jz      short loc_140024559
0x140024598  cmp     dword ptr [rbx+188h], 0
0x14002459f  jz      short loc_1400245BE
0x1400245a1  lea     rcx, [rbx+190h]; ApcState
0x1400245a8  call    cs:__imp_KeUnstackDetachProcess
0x1400245af  nop     dword ptr [rax+rax+00h]
0x1400245b4  mov     dword ptr [rbx+188h], 0
0x1400245be  xor     ecx, ecx; ExitStatus
0x1400245c0  call    cs:__imp_PsTerminateSystemThread
0x1400245c7  nop     dword ptr [rax+rax+00h]
0x1400245cc  mov     rcx, [rsp+58h+var_18]
0x1400245d1  xor     rcx, rsp; StackCookie
0x1400245d4  call    __security_check_cookie
0x1400245d9  mov     rbx, [rsp+58h+arg_8]
0x1400245de  add     rsp, 50h
0x1400245e2  pop     rdi
0x1400245e3  retn
```
