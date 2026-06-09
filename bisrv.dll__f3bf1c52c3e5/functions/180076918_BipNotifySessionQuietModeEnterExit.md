# BipNotifySessionQuietModeEnterExit

- ea: `0x180076918`
- end: `0x1800769dc`
- name: `BipNotifySessionQuietModeEnterExit`
- size: `196`
- prototype: `__int64 __fastcall(char, PSID pSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005d204`

## callees

- `0x180039fb8`
- `0x180076918`
- `0x1800769e4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800769c5`
- `ntdll!RtlFreeHeap` at `0x1800769c5`
- `ntdll!RtlAllocateHeap` at `0x18007694d`
- `ntdll!RtlAllocateHeap` at `0x18007694d`
- `ntdll!RtlCopySid` at `0x18007697a`
- `ntdll!RtlCopySid` at `0x18007697a`
- `ntdll!RtlLengthSid` at `0x180076935`
- `ntdll!RtlLengthSid` at `0x180076935`

## pseudocode

```c
__int64 __fastcall BipNotifySessionQuietModeEnterExit(unsigned int a1, PSID pSid, int a3, char a4)
{
  ULONG v8; // ebp
  char *Heap; // rax
  void *v10; // rdi
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // ebx

  v8 = RtlLengthSid(pSid);
  Heap = (char *)RtlAllocateHeap(BipHeap, 0, v8 + 12);
  v10 = Heap;
  if ( !Heap )
    return 3221225495LL;
  *(_DWORD *)Heap = a1;
  *((_DWORD *)Heap + 2) = a3;
  Heap[4] = a4 != 0;
  RtlCopySid(v8, Heap + 12, pSid);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_L_sid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, v14, (char *)pSid, a1);
  v15 = BipNotifySingleAndSystemSubscribers(a1, 9, v10, v8 + 12);
  RtlFreeHeap(BipHeap, 0, v10);
  return v15;
}

```

## disassembly

```asm
0x180076918  push    rbx
0x18007691a  push    rbp
0x18007691b  push    rsi
0x18007691c  push    rdi
0x18007691d  push    r12
0x18007691f  push    r14
0x180076921  push    r15
0x180076923  sub     rsp, 30h
0x180076927  mov     ebx, ecx
0x180076929  mov     r15b, r9b
0x18007692c  mov     rcx, rdx; Sid
0x18007692f  mov     r12d, r8d
0x180076932  mov     rsi, rdx
0x180076935  call    cs:__imp_RtlLengthSid
0x18007693b  mov     rcx, cs:BipHeap; HeapHandle
0x180076942  xor     edx, edx; Flags
0x180076944  mov     ebp, eax
0x180076946  lea     r14d, [rax+0Ch]
0x18007694a  mov     r8d, r14d; Size
0x18007694d  call    cs:__imp_RtlAllocateHeap
0x180076953  mov     rdi, rax
0x180076956  test    rax, rax
0x180076959  jnz     short loc_180076962
0x18007695b  mov     eax, 0C0000017h
0x180076960  jmp     short loc_1800769CD
0x180076962  mov     [rax], ebx
0x180076964  lea     rdx, [rdi+0Ch]; DestinationSid
0x180076968  mov     [rax+8], r12d
0x18007696c  test    r15b, r15b
0x18007696f  mov     r8, rsi; SourceSid
0x180076972  mov     ecx, ebp; DestinationSidLength
0x180076974  setnz   al
0x180076977  mov     [rdi+4], al
0x18007697a  call    cs:__imp_RtlCopySid
0x180076980  mov     rcx, cs:WPP_GLOBAL_Control
0x180076987  test    byte ptr [rcx+1Ch], 1
0x18007698b  jz      short loc_1800769A5
0x18007698d  cmp     byte ptr [rcx+19h], 4
0x180076991  jb      short loc_1800769A5
0x180076993  mov     rcx, [rcx+10h]; LoggerHandle
0x180076997  mov     dword ptr [rsp+68h+var_40], ebx; char
0x18007699b  mov     [rsp+68h+pSid], rsi; pSid
0x1800769a0  call    WPP_SF_L_sid_d
0x1800769a5  mov     r9d, r14d
0x1800769a8  mov     r8, rdi
0x1800769ab  mov     edx, 9
0x1800769b0  mov     ecx, ebx
0x1800769b2  call    BipNotifySingleAndSystemSubscribers
0x1800769b7  mov     rcx, cs:BipHeap; HeapHandle
0x1800769be  mov     r8, rdi; P
0x1800769c1  xor     edx, edx; Flags
0x1800769c3  mov     ebx, eax
0x1800769c5  call    cs:__imp_RtlFreeHeap
0x1800769cb  mov     eax, ebx
0x1800769cd  add     rsp, 30h
0x1800769d1  pop     r15
0x1800769d3  pop     r14
0x1800769d5  pop     r12
0x1800769d7  pop     rdi
0x1800769d8  pop     rsi
0x1800769d9  pop     rbp
0x1800769da  pop     rbx
0x1800769db  retn
```
