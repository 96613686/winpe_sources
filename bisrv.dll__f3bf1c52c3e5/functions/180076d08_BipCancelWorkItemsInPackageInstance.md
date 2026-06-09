# BipCancelWorkItemsInPackageInstance

- ea: `0x180076d08`
- end: `0x180076ed4`
- name: `BipCancelWorkItemsInPackageInstance`
- size: `460`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007b260`
- `0x18007b620`

## callees

- `0x180016918`
- `0x180016ce0`
- `0x18004df58`
- `0x180076d08`
- `0x180078488`
- `0x180095010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180076e8d`
- `ntdll!RtlFreeHeap` at `0x180076e8d`
- `ntdll!TpReleaseWork` at `0x180076eb2`
- `ntdll!TpReleaseWork` at `0x180076eb2`
- `ntdll!TpPostWork` at `0x180076ea7`
- `ntdll!TpPostWork` at `0x180076ea7`
- `ntdll!TpAllocWork` at `0x180076e75`
- `ntdll!TpAllocWork` at `0x180076e75`
- `ntdll!RtlAllocateHeap` at `0x180076e12`
- `ntdll!RtlAllocateHeap` at `0x180076e12`
- `ntdll!RtlEqualSid` at `0x180076d7e`
- `ntdll!RtlEqualSid` at `0x180076d7e`

## pseudocode

```c
__int64 __fastcall BipCancelWorkItemsInPackageInstance(
        __int64 a1,
        unsigned __int8 (__fastcall *a2)(__int64),
        volatile signed __int32 *a3,
        void *a4,
        unsigned int a5,
        char a6)
{
  __int64 v6; // r13
  int v9; // r15d
  int v12; // ebp
  __int64 NextWorkItemInternal; // rbx
  __int64 v14; // r9
  void *v15; // rcx
  int v16; // eax
  _QWORD **v17; // r14
  _QWORD *v18; // rbx
  _DWORD *v19; // rdi
  _QWORD *Heap; // rax
  void *v21; // rsi
  int v22; // eax
  _QWORD v24[11]; // [rsp+20h] [rbp-58h] BYREF
  int v25; // [rsp+80h] [rbp+8h] BYREF

  v6 = *(_QWORD *)(a1 + 16);
  v24[0] = 0;
  v9 = 0;
  v25 = 0;
  v12 = 0;
  NextWorkItemInternal = BipPackageGetNextWorkItemInternal(v6, 0);
  if ( !NextWorkItemInternal )
  {
LABEL_13:
    if ( a3 )
    {
      v17 = (_QWORD **)(a1 + 24);
      v18 = *v17;
      while ( v18 != v17 )
      {
        v19 = v18;
        v18 = (_QWORD *)*v18;
        if ( v19[29] )
        {
          Heap = RtlAllocateHeap(BipHeap, 0, 0x18u);
          v21 = Heap;
          if ( Heap )
          {
            *((_DWORD *)Heap + 5) = v9;
            *Heap = v19;
            *((_DWORD *)Heap + 4) = 4;
            Heap[1] = a3;
            v22 = TpAllocWork(v24, &BipWaitForTaskCompletionCallback, Heap, 0);
            if ( v22 >= 0 )
            {
              _InterlockedIncrement(a3);
              ++v19[22];
              v19[12] |= 0x200u;
              TpPostWork(v24[0]);
              TpReleaseWork(v24[0]);
            }
            else
            {
              v12 = v22;
              RtlFreeHeap(BipHeap, 0, v21);
            }
          }
          else
          {
            v12 = -1073741801;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_400eacf2c1af3ce8cd24b90f12d3a29b_Traceguids);
          }
        }
      }
    }
    return (unsigned int)v12;
  }
  do
  {
    if ( (!a2 || !a2(NextWorkItemInternal))
      && (!a4 || (v15 = *(void **)(*(_QWORD *)(NextWorkItemInternal + 72) + 176LL)) != 0 && RtlEqualSid(v15, a4)) )
    {
      LOBYTE(v14) = a6;
      v16 = BipCancelWorkItem(NextWorkItemInternal, *(unsigned int *)(a1 + 40), a5, v14);
      if ( v16 >= 0 )
        BipDetermineCancellationTimeout(NextWorkItemInternal, &v25);
      else
        v12 = v16;
    }
    NextWorkItemInternal = BipPackageGetNextWorkItemInternal(v6, NextWorkItemInternal);
  }
  while ( NextWorkItemInternal );
  if ( v12 >= 0 )
  {
    v9 = v25;
    goto LABEL_13;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180076d08  mov     rax, rsp
0x180076d0b  push    rbx
0x180076d0c  push    rbp
0x180076d0d  push    rsi
0x180076d0e  push    rdi
0x180076d0f  push    r12
0x180076d11  push    r13
0x180076d13  push    r14
0x180076d15  push    r15
0x180076d17  sub     rsp, 38h
0x180076d1b  mov     r13, [rcx+10h]
0x180076d1f  mov     rsi, rdx
0x180076d22  mov     r14, rcx
0x180076d25  mov     qword ptr [rax-58h], 0
0x180076d2d  xor     r15d, r15d
0x180076d30  mov     rcx, r13
0x180076d33  xor     edx, edx
0x180076d35  mov     [rax+8], r15d
0x180076d39  mov     rdi, r9
0x180076d3c  mov     r12, r8
0x180076d3f  xor     ebp, ebp
0x180076d41  call    BipPackageGetNextWorkItemInternal
0x180076d46  mov     rbx, rax
0x180076d49  test    rax, rax
0x180076d4c  jz      loc_180076DDF
0x180076d52  test    rsi, rsi
0x180076d55  jz      short loc_180076D66
0x180076d57  mov     rcx, rbx
0x180076d5a  mov     rax, rsi
0x180076d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d62  test    al, al
0x180076d64  jnz     short loc_180076DBC
0x180076d66  test    rdi, rdi
0x180076d69  jz      short loc_180076D88
0x180076d6b  mov     rax, [rbx+48h]
0x180076d6f  mov     rcx, [rax+0B0h]; Sid1
0x180076d76  test    rcx, rcx
0x180076d79  jz      short loc_180076DBC
0x180076d7b  mov     rdx, rdi; Sid2
0x180076d7e  call    cs:__imp_RtlEqualSid
0x180076d84  test    al, al
0x180076d86  jz      short loc_180076DBC
0x180076d88  mov     r9b, [rsp+78h+arg_28]
0x180076d90  mov     rcx, rbx
0x180076d93  mov     r8d, [rsp+78h+arg_20]
0x180076d9b  mov     edx, [r14+28h]
0x180076d9f  call    BipCancelWorkItem
0x180076da4  test    eax, eax
0x180076da6  jns     short loc_180076DAC
0x180076da8  mov     ebp, eax
0x180076daa  jmp     short loc_180076DBC
0x180076dac  lea     rdx, [rsp+78h+arg_0]
0x180076db4  mov     rcx, rbx
0x180076db7  call    BipDetermineCancellationTimeout
0x180076dbc  mov     rdx, rbx
0x180076dbf  mov     rcx, r13
0x180076dc2  call    BipPackageGetNextWorkItemInternal
0x180076dc7  mov     rbx, rax
0x180076dca  test    rax, rax
0x180076dcd  jnz     short loc_180076D52
0x180076dcf  test    ebp, ebp
0x180076dd1  js      loc_180076EC1
0x180076dd7  mov     r15d, [rsp+78h+arg_0]
0x180076ddf  test    r12, r12
0x180076de2  jz      loc_180076EC1
0x180076de8  add     r14, 18h
0x180076dec  mov     rbx, [r14]
0x180076def  jmp     loc_180076EB8
0x180076df4  mov     rdi, rbx
0x180076df7  mov     rbx, [rbx]
0x180076dfa  mov     eax, [rdi+74h]
0x180076dfd  test    eax, eax
0x180076dff  jz      loc_180076EB8
0x180076e05  mov     rcx, cs:BipHeap; HeapHandle
0x180076e0c  xor     edx, edx; Flags
0x180076e0e  lea     r8d, [rdx+18h]; Size
0x180076e12  call    cs:__imp_RtlAllocateHeap
0x180076e18  mov     rsi, rax
0x180076e1b  test    rax, rax
0x180076e1e  jnz     short loc_180076E51
0x180076e20  mov     ebp, 0C0000017h
0x180076e25  mov     rcx, cs:WPP_GLOBAL_Control
0x180076e2c  test    byte ptr [rcx+1Ch], 1
0x180076e30  jz      loc_180076EB8
0x180076e36  cmp     byte ptr [rcx+19h], 2
0x180076e3a  jb      short loc_180076EB8
0x180076e3c  mov     rcx, [rcx+10h]
0x180076e40  lea     edx, [rax+0Bh]
0x180076e43  lea     r8, WPP_400eacf2c1af3ce8cd24b90f12d3a29b_Traceguids
0x180076e4a  call    WPP_SF_
0x180076e4f  jmp     short loc_180076EB8
0x180076e51  xor     r9d, r9d
0x180076e54  mov     [rax+14h], r15d
0x180076e58  mov     r8, rsi
0x180076e5b  mov     [rax], rdi
0x180076e5e  lea     rdx, BipWaitForTaskCompletionCallback
0x180076e65  mov     dword ptr [rax+10h], 4
0x180076e6c  lea     rcx, [rsp+78h+var_58]
0x180076e71  mov     [rax+8], r12
0x180076e75  call    cs:__imp_TpAllocWork
0x180076e7b  test    eax, eax
0x180076e7d  jns     short loc_180076E95
0x180076e7f  mov     rcx, cs:BipHeap; HeapHandle
0x180076e86  mov     r8, rsi; P
0x180076e89  xor     edx, edx; Flags
0x180076e8b  mov     ebp, eax
0x180076e8d  call    cs:__imp_RtlFreeHeap
0x180076e93  jmp     short loc_180076EB8
0x180076e95  lock inc dword ptr [r12]
0x180076e9a  inc     dword ptr [rdi+58h]
0x180076e9d  bts     dword ptr [rdi+30h], 9
0x180076ea2  mov     rcx, [rsp+78h+var_58]
0x180076ea7  call    cs:__imp_TpPostWork
0x180076ead  mov     rcx, [rsp+78h+var_58]
0x180076eb2  call    cs:__imp_TpReleaseWork
0x180076eb8  cmp     rbx, r14
0x180076ebb  jnz     loc_180076DF4
0x180076ec1  mov     eax, ebp
0x180076ec3  add     rsp, 38h
0x180076ec7  pop     r15
0x180076ec9  pop     r14
0x180076ecb  pop     r13
0x180076ecd  pop     r12
0x180076ecf  pop     rdi
0x180076ed0  pop     rsi
0x180076ed1  pop     rbp
0x180076ed2  pop     rbx
0x180076ed3  retn
```
