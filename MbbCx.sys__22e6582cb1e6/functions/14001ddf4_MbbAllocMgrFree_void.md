# MbbAllocMgrFree(void *)

- ea: `0x14001ddf4`
- end: `0x14001dea9`
- name: `?MbbAllocMgrFree@@YAXPEAX@Z`
- size: `181`
- prototype: `void __fastcall(void *)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140019b6c`
- `0x140019f78`
- `0x14001ffa4`
- `0x140020330`
- `0x1400240f0`

## callees

- `0x14001ddf4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001de70`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001de70`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001de85`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001de85`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001de15`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001de15`

## pseudocode

```c
void __fastcall MbbAllocMgrFree(_QWORD *a1)
{
  _QWORD *v1; // rbx
  __int64 v2; // rdi
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rax
  _QWORD *v6; // rdx

  v1 = a1 - 6;
  v2 = *(a1 - 1);
  *(_BYTE *)(v2 + 136) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 128));
  if ( !*((_BYTE *)v1 + 32) )
  {
    v5 = *v1;
    if ( *(_QWORD **)(*v1 + 8LL) == v1 )
    {
      v6 = (_QWORD *)v1[1];
      if ( (_QWORD *)*v6 == v1 )
      {
        *v6 = v5;
        *(_QWORD *)(v5 + 8) = v6;
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v2, v1);
        goto LABEL_7;
      }
    }
LABEL_8:
    __fastfail(3u);
  }
  v3 = (_QWORD *)(v2 + 160);
  v4 = *(_QWORD *)(v2 + 160);
  if ( *(_QWORD *)(v4 + 8) != v2 + 160 )
    goto LABEL_8;
  v1[2] = v4;
  v1[3] = v3;
  *(_QWORD *)(v4 + 8) = v1 + 2;
  *v3 = v1 + 2;
LABEL_7:
  KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 128), *(_BYTE *)(v2 + 136));
}

```

## disassembly

```asm
0x14001ddf4  mov     [rsp+arg_0], rbx
0x14001ddf9  mov     [rsp+arg_8], rsi
0x14001ddfe  push    rdi
0x14001ddff  sub     rsp, 20h
0x14001de03  lea     rbx, [rcx-30h]
0x14001de07  mov     rdi, [rbx+28h]
0x14001de0b  lea     rsi, [rdi+80h]
0x14001de12  mov     rcx, rsi; SpinLock
0x14001de15  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001de1c  nop     dword ptr [rax+rax+00h]
0x14001de21  mov     [rdi+88h], al
0x14001de27  cmp     byte ptr [rbx+20h], 0
0x14001de2b  jz      short loc_14001DE51
0x14001de2d  lea     rcx, [rdi+0A0h]
0x14001de34  mov     rdx, [rcx]
0x14001de37  cmp     [rdx+8], rcx
0x14001de3b  jnz     short loc_14001DEA2
0x14001de3d  lea     rax, [rbx+10h]
0x14001de41  mov     [rax], rdx
0x14001de44  mov     [rax+8], rcx
0x14001de48  mov     [rdx+8], rax
0x14001de4c  mov     [rcx], rax
0x14001de4f  jmp     short loc_14001DE7C
0x14001de51  mov     rax, [rbx]
0x14001de54  cmp     [rax+8], rbx
0x14001de58  jnz     short loc_14001DEA2
0x14001de5a  mov     rdx, [rbx+8]
0x14001de5e  cmp     [rdx], rbx
0x14001de61  jnz     short loc_14001DEA2
0x14001de63  mov     [rdx], rax
0x14001de66  mov     rcx, rdi; Lookaside
0x14001de69  mov     [rax+8], rdx
0x14001de6d  mov     rdx, rbx; Entry
0x14001de70  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001de77  nop     dword ptr [rax+rax+00h]
0x14001de7c  mov     dl, [rdi+88h]; NewIrql
0x14001de82  mov     rcx, rsi; SpinLock
0x14001de85  call    cs:__imp_KeReleaseSpinLock
0x14001de8c  nop     dword ptr [rax+rax+00h]
0x14001de91  mov     rbx, [rsp+28h+arg_0]
0x14001de96  mov     rsi, [rsp+28h+arg_8]
0x14001de9b  add     rsp, 20h
0x14001de9f  pop     rdi
0x14001dea0  retn
0x14001dea2  mov     ecx, 3
0x14001dea7  int     29h; Win8: RtlFailFast(ecx)
```
