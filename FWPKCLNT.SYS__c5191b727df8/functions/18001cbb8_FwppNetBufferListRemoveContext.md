# FwppNetBufferListRemoveContext

- ea: `0x18001cbb8`
- end: `0x18001cd64`
- name: `FwppNetBufferListRemoveContext`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800056d0`

## callees

- `0x180006a1c`
- `0x180006c88`
- `0x180006ce0`
- `0x180006e74`
- `0x180006f00`
- `0x180007cc0`
- `0x18001cbb8`
- `0x18001f76c`
- `0x180020400`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x18001cc4b`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x18001cc4b`

## pseudocode

```c
__int64 __fastcall FwppNetBufferListRemoveContext(__int64 a1)
{
  __int64 v2; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v3; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v4; // rcx
  __int64 *v5; // rbx
  __int64 *v6; // rax
  __int64 v7; // rcx
  _BYTE *v8; // rdi
  int v9; // eax
  __int64 *v11; // [rsp+40h] [rbp-30h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v12; // [rsp+48h] [rbp-28h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-20h] BYREF
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v14; // [rsp+90h] [rbp+20h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !(unsigned __int8)FwppIsFastNblTag() )
  {
    LOBYTE(v2) = 1;
    v12 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)&v11;
    v11 = (__int64 *)&v11;
    WfpObjectManagerLock(&unk_180048680, v2, &LockHandle);
    while ( 1 )
    {
      v14 = 0;
      if ( !(unsigned int)WfpHashtableIteratorGetNext(&qword_1800486C8, &v14) )
        break;
      v3 = v14 - 1;
      if ( LODWORD(v14[-1].Linkage.Flink) != 2 || v14 == (PRTL_DYNAMIC_HASH_TABLE_ENTRY)24 )
        break;
      if ( v14[-4].Signature == a1 )
      {
        RtlRemoveEntryHashTable(&HashTable, v14, 0);
        LOBYTE(v3[4].Signature) = 1;
        v4 = v12;
        if ( (__int64 **)v12->Linkage.Flink != &v11 )
LABEL_22:
          __fastfail(3u);
        v3[3].Linkage.Blink = &v12->Linkage;
        v3[3].Linkage.Flink = (struct _LIST_ENTRY *)&v11;
        v4->Linkage.Flink = &v3[3].Linkage;
        v12 = v3 + 3;
      }
    }
    WfpObjectManagerUnlock(&unk_180048680, &LockHandle);
    while ( 1 )
    {
      v5 = v11;
      if ( v11 == (__int64 *)&v11 )
        break;
      if ( (__int64 **)v11[1] != &v11 )
        goto LABEL_22;
      v6 = (__int64 *)*v11;
      if ( *(__int64 **)(*v11 + 8) != v11 )
        goto LABEL_22;
      v11 = (__int64 *)*v11;
      v6[1] = (__int64)&v11;
      WfpAcquireSpinLock((PKSPIN_LOCK)v5 - 3, &LockHandle);
      v8 = (char *)v5 + 41;
      if ( *((_BYTE *)v5 + 43) )
        *v8 = 1;
      else
        *((_BYTE *)v5 + 42) = 1;
      WfpReleaseSpinLock(v7, &LockHandle);
      if ( !*v8 )
      {
        v9 = *((_DWORD *)v5 - 20);
        if ( v9 )
        {
          if ( v9 == 1 )
            ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))*(v5 - 11))(
              5,
              0,
              0,
              *((unsigned __int16 *)v5 - 71),
              *(v5 - 17),
              *(v5 - 16));
        }
        else
        {
          ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))*(v5 - 12))(
            5,
            0,
            0,
            *((unsigned __int16 *)v5 - 71),
            *(v5 - 17),
            *(v5 - 16));
        }
      }
      WfpObjectDereference(v5 - 9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001cbb8  mov     [rsp-8+arg_0], rbx
0x18001cbbd  mov     [rsp-8+arg_8], rdi
0x18001cbc2  push    rbp
0x18001cbc3  mov     rbp, rsp
0x18001cbc6  sub     rsp, 70h
0x18001cbca  xor     eax, eax
0x18001cbcc  xorps   xmm0, xmm0
0x18001cbcf  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x18001cbd3  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x18001cbd7  mov     rdi, rcx
0x18001cbda  call    FwppIsFastNblTag
0x18001cbdf  test    al, al
0x18001cbe1  jnz     loc_18001CD4F
0x18001cbe7  lea     rax, [rbp+var_30]
0x18001cbeb  mov     dl, 1
0x18001cbed  mov     [rbp+var_28], rax
0x18001cbf1  lea     r8, [rbp+LockHandle]
0x18001cbf5  lea     rax, [rbp+var_30]
0x18001cbf9  lea     rcx, unk_180048680
0x18001cc00  mov     [rbp+var_30], rax
0x18001cc04  call    WfpObjectManagerLock
0x18001cc09  lea     rdx, [rbp+arg_10]
0x18001cc0d  mov     [rbp+arg_10], 0
0x18001cc15  lea     rcx, qword_1800486C8
0x18001cc1c  call    WfpHashtableIteratorGetNext
0x18001cc21  test    eax, eax
0x18001cc23  jz      short loc_18001CC84
0x18001cc25  mov     rbx, [rbp+arg_10]
0x18001cc29  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18001cc2d  cmp     dword ptr [rbx], 2
0x18001cc30  jnz     short loc_18001CC84
0x18001cc32  test    rbx, rbx
0x18001cc35  jz      short loc_18001CC84
0x18001cc37  cmp     [rbx-38h], rdi
0x18001cc3b  jnz     short loc_18001CC09
0x18001cc3d  lea     rdx, [rbx+18h]; Entry
0x18001cc41  xor     r8d, r8d; Context
0x18001cc44  lea     rcx, HashTable; HashTable
0x18001cc4b  call    cs:__imp_RtlRemoveEntryHashTable
0x18001cc52  nop     dword ptr [rax+rax+00h]
0x18001cc57  mov     byte ptr [rbx+70h], 1
0x18001cc5b  lea     rax, [rbp+var_30]
0x18001cc5f  mov     rcx, [rbp+var_28]
0x18001cc63  cmp     [rcx], rax
0x18001cc66  jnz     loc_18001CD48
0x18001cc6c  lea     rax, [rbx+48h]
0x18001cc70  mov     [rbx+50h], rcx
0x18001cc74  lea     rdx, [rbp+var_30]
0x18001cc78  mov     [rax], rdx
0x18001cc7b  mov     [rcx], rax
0x18001cc7e  mov     [rbp+var_28], rax
0x18001cc82  jmp     short loc_18001CC09
0x18001cc84  lea     rdx, [rbp+LockHandle]
0x18001cc88  lea     rcx, unk_180048680
0x18001cc8f  call    WfpObjectManagerUnlock
0x18001cc94  mov     rbx, [rbp+var_30]
0x18001cc98  lea     rax, [rbp+var_30]
0x18001cc9c  cmp     rbx, rax
0x18001cc9f  jz      loc_18001CD4F
0x18001cca5  lea     rax, [rbp+var_30]
0x18001cca9  cmp     [rbx+8], rax
0x18001ccad  jnz     loc_18001CD48
0x18001ccb3  mov     rax, [rbx]
0x18001ccb6  cmp     [rax+8], rbx
0x18001ccba  jnz     loc_18001CD48
0x18001ccc0  lea     rcx, [rbp+var_30]
0x18001ccc4  mov     [rbp+var_30], rax
0x18001ccc8  mov     [rax+8], rcx
0x18001cccc  lea     rdx, [rbp+LockHandle]; LockHandle
0x18001ccd0  lea     rcx, [rbx-18h]; SpinLock
0x18001ccd4  call    WfpAcquireSpinLock
0x18001ccd9  cmp     byte ptr [rbx+2Bh], 0
0x18001ccdd  lea     rdi, [rbx+29h]
0x18001cce1  jz      short loc_18001CCE8
0x18001cce3  mov     byte ptr [rdi], 1
0x18001cce6  jmp     short loc_18001CCEC
0x18001cce8  mov     byte ptr [rbx+2Ah], 1
0x18001ccec  lea     rdx, [rbp+LockHandle]
0x18001ccf0  call    WfpReleaseSpinLock
0x18001ccf5  cmp     byte ptr [rdi], 0
0x18001ccf8  jnz     short loc_18001CD3A
0x18001ccfa  mov     eax, [rbx-50h]
0x18001ccfd  test    eax, eax
0x18001ccff  jnz     short loc_18001CD07
0x18001cd01  mov     rax, [rbx-60h]
0x18001cd05  jmp     short loc_18001CD10
0x18001cd07  cmp     eax, 1
0x18001cd0a  jnz     short loc_18001CD3A
0x18001cd0c  mov     rax, [rbx-58h]
0x18001cd10  mov     rcx, [rbx-80h]
0x18001cd14  xor     edx, edx
0x18001cd16  movzx   r9d, word ptr [rbx-8Eh]
0x18001cd1e  xor     r8d, r8d
0x18001cd21  mov     [rsp+70h+var_48], rcx
0x18001cd26  mov     rcx, [rbx-88h]
0x18001cd2d  mov     [rsp+70h+var_50], rcx
0x18001cd32  lea     ecx, [rdx+5]
0x18001cd35  call    _guard_dispatch_icall
0x18001cd3a  lea     rcx, [rbx-48h]
0x18001cd3e  call    WfpObjectDereference
0x18001cd43  jmp     loc_18001CC94
0x18001cd48  mov     ecx, 3
0x18001cd4d  int     29h; Win8: RtlFailFast(ecx)
0x18001cd4f  lea     r11, [rsp+70h+var_s0]
0x18001cd54  xor     eax, eax
0x18001cd56  mov     rbx, [r11+10h]
0x18001cd5a  mov     rdi, [r11+18h]
0x18001cd5e  mov     rsp, r11
0x18001cd61  pop     rbp
0x18001cd62  retn
```
