# UbpmpScheduleCalendarRepetitionsAtRegistrationTime

- ea: `0x180015a50`
- end: `0x180015b87`
- name: `UbpmpScheduleCalendarRepetitionsAtRegistrationTime`
- size: `311`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180015b90`

## callees

- `0x1800150c0`
- `0x180015a50`
- `0x180024d08`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180015b5e`
- `ntdll!RtlFreeHeap` at `0x180015b5e`
- `DABAPI!DabGetLastScheduledRunTime` at `0x180015ade`
- `DABAPI!DabGetLastScheduledRunTime` at `0x180015ade`

## pseudocode

```c
__int64 __fastcall UbpmpScheduleCalendarRepetitionsAtRegistrationTime(struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  unsigned __int16 v4; // bx
  __int64 v5; // rax
  __int64 v6; // rcx
  unsigned int LastScheduledRunTime; // ebp
  unsigned __int64 v8; // r8
  struct _FILETIME v10; // [rsp+68h] [rbp+10h] BYREF
  struct _UBPM_REPETITION_CONTEXT *v11; // [rsp+70h] [rbp+18h] BYREF

  v11 = 0;
  v10 = 0;
  v2 = UbpmAlloc(0x3Cu);
  v3 = v2;
  if ( !v2 )
    return 14;
  v4 = 0;
  v2[3] = 0;
  *((_DWORD *)v2 + 4) = 0;
  while ( 1 )
  {
    v5 = *((_QWORD *)a1 + 3);
    if ( (unsigned int)v4 >= *(_DWORD *)(v5 + 20) )
      break;
    v6 = *(_QWORD *)(v5 + 24);
    if ( *(_DWORD *)(v6 + 48LL * v4) == 1 && *(_DWORD *)(*(_QWORD *)(v6 + 48LL * v4 + 8) + 56LL) == 4 )
    {
      LastScheduledRunTime = DabGetLastScheduledRunTime(*((_QWORD *)a1 + 4) + 8 * (v4 + 4 * (v4 + 1LL)), &v10);
      if ( LastScheduledRunTime )
        goto LABEL_13;
      if ( v10.dwLowDateTime || v10.dwHighDateTime )
      {
        v8 = _InterlockedIncrement64((volatile signed __int64 *)&g_ullCollectionId);
        v3[6] = v8;
        LastScheduledRunTime = UbpmpScheduleRepetitionSeries(a1, v4, v8, v3, 0x3Cu, &v10, &v11);
        if ( LastScheduledRunTime )
          goto LABEL_13;
      }
    }
    ++v4;
  }
  LastScheduledRunTime = 0;
LABEL_13:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  return LastScheduledRunTime;
}

```

## disassembly

```asm
0x180015a50  push    rsi
0x180015a52  push    rdi
0x180015a53  push    r14
0x180015a55  sub     rsp, 40h
0x180015a59  mov     rsi, rcx
0x180015a5c  xor     r14d, r14d
0x180015a5f  mov     ecx, 3Ch ; '<'; Size
0x180015a64  mov     [rsp+58h+arg_10], r14
0x180015a69  mov     qword ptr [rsp+58h+arg_8.dwLowDateTime], r14
0x180015a6e  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180015a73  mov     rdi, rax
0x180015a76  test    rax, rax
0x180015a79  jz      loc_180015B80
0x180015a7f  mov     [rsp+58h+arg_0], rbx
0x180015a84  mov     ebx, r14d
0x180015a87  mov     [rsp+58h+arg_18], rbp
0x180015a8c  mov     [rax+18h], r14
0x180015a90  mov     [rax+10h], r14d
0x180015a94  mov     rax, [rsi+18h]
0x180015a98  movzx   ecx, bx
0x180015a9b  cmp     ecx, [rax+14h]
0x180015a9e  jnb     loc_180015B49
0x180015aa4  mov     rcx, [rax+18h]
0x180015aa8  movzx   r8d, bx
0x180015aac  lea     rdx, [r8+r8*2]
0x180015ab0  add     rdx, rdx
0x180015ab3  cmp     dword ptr [rcx+rdx*8], 1
0x180015ab7  jz      short loc_180015ABE
0x180015ab9  inc     bx
0x180015abc  jmp     short loc_180015A94
0x180015abe  mov     rax, [rcx+rdx*8+8]
0x180015ac3  cmp     dword ptr [rax+38h], 4
0x180015ac7  jnz     short loc_180015AB9
0x180015ac9  mov     rax, [rsi+20h]
0x180015acd  lea     rcx, [r8+1]
0x180015ad1  lea     rcx, [r8+rcx*4]
0x180015ad5  lea     rdx, [rsp+58h+arg_8]
0x180015ada  lea     rcx, [rax+rcx*8]
0x180015ade  call    cs:__imp_DabGetLastScheduledRunTime
0x180015ae5  nop     dword ptr [rax+rax+00h]
0x180015aea  mov     ebp, eax
0x180015aec  test    eax, eax
0x180015aee  jnz     short loc_180015B4C
0x180015af0  cmp     [rsp+58h+arg_8.dwLowDateTime], r14d
0x180015af5  jnz     short loc_180015AFE
0x180015af7  cmp     [rsp+58h+arg_8.dwHighDateTime], r14d
0x180015afc  jz      short loc_180015AB9
0x180015afe  mov     r8d, 1
0x180015b04  lock xadd cs:?g_ullCollectionId@@3_KC, r8; unsigned __int64 volatile g_ullCollectionId
0x180015b0d  lea     rax, [rsp+58h+arg_10]
0x180015b12  inc     r8; unsigned __int64
0x180015b15  mov     [rsp+58h+var_28], rax; struct _UBPM_REPETITION_CONTEXT **
0x180015b1a  mov     r9, rdi; void *
0x180015b1d  lea     rax, [rsp+58h+arg_8]
0x180015b22  mov     [rdi+30h], r8
0x180015b26  mov     [rsp+58h+var_30], rax; struct _FILETIME *
0x180015b2b  movzx   edx, bx; unsigned __int16
0x180015b2e  mov     rcx, rsi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180015b31  mov     [rsp+58h+var_38], 3Ch ; '<'; unsigned int
0x180015b39  call    ?UbpmpScheduleRepetitionSeries@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@G_KPEAXKPEAU_FILETIME@@PEAPEAU_UBPM_REPETITION_CONTEXT@@@Z; UbpmpScheduleRepetitionSeries(_UBPM_TRIGGER_CONSUMER_BLOCK *,ushort,unsigned __int64,void *,ulong,_FILETIME *,_UBPM_REPETITION_CONTEXT * *)
0x180015b3e  mov     ebp, eax
0x180015b40  test    eax, eax
0x180015b42  jnz     short loc_180015B4C
0x180015b44  jmp     loc_180015AB9
0x180015b49  mov     ebp, r14d
0x180015b4c  mov     rcx, gs:60h
0x180015b55  mov     r8, rdi; P
0x180015b58  xor     edx, edx; Flags
0x180015b5a  mov     rcx, [rcx+30h]; HeapHandle
0x180015b5e  call    cs:__imp_RtlFreeHeap
0x180015b65  nop     dword ptr [rax+rax+00h]
0x180015b6a  mov     rbx, [rsp+58h+arg_0]
0x180015b6f  mov     eax, ebp
0x180015b71  mov     rbp, [rsp+58h+arg_18]
0x180015b76  add     rsp, 40h
0x180015b7a  pop     r14
0x180015b7c  pop     rdi
0x180015b7d  pop     rsi
0x180015b7e  retn
0x180015b80  mov     eax, 0Eh
0x180015b85  jmp     short loc_180015B76
```
