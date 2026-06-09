# AggregateWaitHandle::AddHandle(void *)

- ea: `0x180025b80`
- end: `0x180025ce0`
- name: `?AddHandle@AggregateWaitHandle@@QEAAJPEAX@Z`
- size: `352`
- prototype: `__int64 __fastcall(AggregateWaitHandle *__hidden this, void *)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025940`
- `0x180026260`
- `0x180028500`
- `0x180028810`
- `0x18002bb00`
- `0x180042b60`

## callees

- `0x180025b80`
- `0x18002bbd0`

## import_xrefs

- `ntdll!NtAssociateWaitCompletionPacket` at `0x180025c55`
- `ntdll!NtAssociateWaitCompletionPacket` at `0x180025c55`
- `ntdll!NtCreateWaitCompletionPacket` at `0x180025c0d`
- `ntdll!NtCreateWaitCompletionPacket` at `0x180025c0d`
- `ntdll!RtlAllocateHeap` at `0x180025bd5`
- `ntdll!RtlAllocateHeap` at `0x180025bd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025cb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025cb9`

## pseudocode

```c
__int64 __fastcall AggregateWaitHandle::AddHandle(AggregateWaitHandle *this, void *a2)
{
  char *v4; // rdi
  char *i; // rax
  __int64 result; // rax
  _OWORD *Heap; // rax
  int v8; // esi
  char **v9; // rcx
  char *v10; // rax
  HANDLE hObject; // [rsp+70h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 1) )
  {
    SipcFailFast(2147549183LL);
    JUMPOUT(0x180025CDFLL);
  }
  v4 = (char *)this + 24;
  for ( i = (char *)*((_QWORD *)this + 3); i != v4; i = *(char **)i )
  {
    if ( *((void **)i + 2) == a2 )
      return 2147942487LL;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
    if ( !Heap )
    {
      result = 2147942414LL;
LABEL_16:
      *((_QWORD *)this + 2) = 0;
      return result;
    }
    *Heap = 0;
    Heap[1] = 0;
    *((_QWORD *)this + 2) = Heap;
  }
  hObject = 0;
  v8 = NtCreateWaitCompletionPacket(&hObject, 1);
  if ( v8 >= 0 )
  {
    v8 = NtAssociateWaitCompletionPacket(hObject, *(_QWORD *)this, a2, *((_QWORD *)this + 2), 0, 0, 0, 0);
    if ( v8 >= 0 )
    {
      *(_QWORD *)(*((_QWORD *)this + 2) + 16LL) = a2;
      *(_QWORD *)(*((_QWORD *)this + 2) + 24LL) = hObject;
      v9 = (char **)*((_QWORD *)v4 + 1);
      if ( *v9 != v4 )
        __fastfail(3u);
      v10 = (char *)*((_QWORD *)this + 2);
      *(_QWORD *)v10 = v4;
      *((_QWORD *)v10 + 1) = v9;
      *v9 = v10;
      ++*((_DWORD *)v4 + 4);
      *((_QWORD *)v4 + 1) = v10;
      result = 0;
      goto LABEL_16;
    }
    CloseHandle(hObject);
  }
  return v8 | 0x10000000u;
}

```

## disassembly

```asm
0x180025b80  push    rbx
0x180025b82  push    rbp
0x180025b83  push    rsi
0x180025b84  push    rdi
0x180025b85  sub     rsp, 48h
0x180025b89  cmp     qword ptr [rcx+8], 0
0x180025b8e  mov     rbp, rdx
0x180025b91  mov     rbx, rcx
0x180025b94  jz      loc_180025CD5
0x180025b9a  lea     rdi, [rcx+18h]
0x180025b9e  mov     rax, [rdi]
0x180025ba1  cmp     rax, rdi
0x180025ba4  jz      short loc_180025BBB
0x180025ba6  cmp     [rax+10h], rbp
0x180025baa  jz      short loc_180025BB1
0x180025bac  mov     rax, [rax]
0x180025baf  jmp     short loc_180025BA1
0x180025bb1  mov     eax, 80070057h
0x180025bb6  jmp     loc_180025CCB
0x180025bbb  cmp     qword ptr [rcx+10h], 0
0x180025bc0  jnz     short loc_180025BF8
0x180025bc2  mov     rcx, gs:60h
0x180025bcb  xor     edx, edx; Flags
0x180025bcd  mov     rcx, [rcx+30h]; HeapHandle
0x180025bd1  lea     r8d, [rdx+20h]; Size
0x180025bd5  call    cs:__imp_RtlAllocateHeap
0x180025bdc  nop     dword ptr [rax+rax+00h]
0x180025be1  test    rax, rax
0x180025be4  jz      loc_180025C8C
0x180025bea  xorps   xmm0, xmm0
0x180025bed  movups  xmmword ptr [rax], xmm0
0x180025bf0  movups  xmmword ptr [rax+10h], xmm0
0x180025bf4  mov     [rbx+10h], rax
0x180025bf8  xor     r8d, r8d
0x180025bfb  mov     [rsp+68h+hObject], 0
0x180025c04  lea     rcx, [rsp+68h+hObject]
0x180025c09  lea     edx, [r8+1]
0x180025c0d  call    cs:__imp_NtCreateWaitCompletionPacket
0x180025c14  nop     dword ptr [rax+rax+00h]
0x180025c19  mov     esi, eax
0x180025c1b  test    eax, eax
0x180025c1d  js      loc_180025CC5
0x180025c23  mov     r9, [rbx+10h]
0x180025c27  mov     r8, rbp
0x180025c2a  mov     rdx, [rbx]
0x180025c2d  mov     rcx, [rsp+68h+hObject]
0x180025c32  mov     [rsp+68h+var_30], 0
0x180025c3b  mov     [rsp+68h+var_38], 0
0x180025c44  mov     [rsp+68h+var_40], 0
0x180025c4c  mov     [rsp+68h+var_48], 0
0x180025c55  call    cs:__imp_NtAssociateWaitCompletionPacket
0x180025c5c  nop     dword ptr [rax+rax+00h]
0x180025c61  mov     esi, eax
0x180025c63  test    eax, eax
0x180025c65  js      short loc_180025CB4
0x180025c67  mov     rax, [rbx+10h]
0x180025c6b  mov     [rax+10h], rbp
0x180025c6f  mov     rcx, [rbx+10h]
0x180025c73  mov     rax, [rsp+68h+hObject]
0x180025c78  mov     [rcx+18h], rax
0x180025c7c  mov     rcx, [rdi+8]
0x180025c80  cmp     [rcx], rdi
0x180025c83  jz      short loc_180025C93
0x180025c85  mov     ecx, 3
0x180025c8a  int     29h; Win8: RtlFailFast(ecx)
0x180025c8c  mov     eax, 8007000Eh
0x180025c91  jmp     short loc_180025CAA
0x180025c93  mov     rax, [rbx+10h]
0x180025c97  mov     [rax], rdi
0x180025c9a  mov     [rax+8], rcx
0x180025c9e  mov     [rcx], rax
0x180025ca1  inc     dword ptr [rdi+10h]
0x180025ca4  mov     [rdi+8], rax
0x180025ca8  xor     eax, eax
0x180025caa  mov     qword ptr [rbx+10h], 0
0x180025cb2  jmp     short loc_180025CCB
0x180025cb4  mov     rcx, [rsp+68h+hObject]; hObject
0x180025cb9  call    cs:__imp_CloseHandle
0x180025cc0  nop     dword ptr [rax+rax+00h]
0x180025cc5  bts     esi, 1Ch
0x180025cc9  mov     eax, esi
0x180025ccb  add     rsp, 48h
0x180025ccf  pop     rdi
0x180025cd0  pop     rsi
0x180025cd1  pop     rbp
0x180025cd2  pop     rbx
0x180025cd3  retn
0x180025cd5  mov     ecx, 8000FFFFh
0x180025cda  call    SipcFailFast
```
