# WsGetUserEntry

- ea: `0x180009f80`
- end: `0x18000a059`
- name: `WsGetUserEntry`
- size: `217`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800012a0`
- `0x180001710`
- `0x1800299a4`

## callees

- `0x180009f80`
- `0x18002ef08`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x18000a036`
- `ntdll!RtlCopyLuid` at `0x18000a04b`
- `ntdll!RtlCopyLuid` at `0x18000a036`
- `ntdll!RtlCopyLuid` at `0x18000a04b`

## pseudocode

```c
__int64 __fastcall WsGetUserEntry(
        __int64 a1,
        struct _LUID *a2,
        unsigned int *LowPart,
        __int64 a4,
        struct _LUID *SourceLuid)
{
  unsigned int *v5; // r14
  struct _LUID *v6; // rdi
  unsigned int v8; // ebp
  __int64 i; // rbx
  __int64 result; // rax
  __int64 v11; // rbx

  v5 = LowPart;
  v6 = a2;
  v8 = -1;
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 112); i = (unsigned int)(i + 1) )
  {
    LowPart = (unsigned int *)v6->LowPart;
    a2 = (struct _LUID *)(*(_QWORD *)a1 + 24 * i);
    if ( *v6 == *(_QWORD *)&a2[1] || *v6 == *(_QWORD *)&a2[2] )
    {
      *v5 = i;
      return 0;
    }
    if ( v8 == -1 && !*(_QWORD *)a2 )
      v8 = i;
  }
  if ( !(_DWORD)a4 )
    return 2221;
  if ( v8 != -1 )
  {
LABEL_19:
    v11 = 24LL * v8;
    RtlCopyLuid((PLUID)(v11 + *(_QWORD *)a1 + 8LL), v6);
    RtlCopyLuid((PLUID)(v11 + *(_QWORD *)a1 + 16LL), SourceLuid);
    *v5 = v8;
    return 0;
  }
  result = WsGrowTable(a1, a2, LowPart, a4);
  if ( !(_DWORD)result )
  {
    v8 = i;
    goto LABEL_19;
  }
  return result;
}

```

## disassembly

```asm
0x180009f80  push    rbx
0x180009f82  push    rbp
0x180009f83  push    rsi
0x180009f84  push    rdi
0x180009f85  push    r14
0x180009f87  sub     rsp, 20h
0x180009f8b  mov     r10d, [rcx+70h]
0x180009f8f  mov     r14, r8
0x180009f92  mov     rdi, rdx
0x180009f95  mov     rsi, rcx
0x180009f98  mov     ebp, 0FFFFFFFFh
0x180009f9d  xor     ebx, ebx
0x180009f9f  nop
0x180009fa0  cmp     ebx, r10d
0x180009fa3  jnb     short loc_180009FE9
0x180009fa5  mov     rax, [rsi]
0x180009fa8  lea     rcx, [rbx+rbx*2]
0x180009fac  mov     r8d, [rdi]
0x180009faf  lea     rdx, [rax+rcx*8]
0x180009fb3  cmp     r8d, [rdx+8]
0x180009fb7  jz      short loc_180009FC8
0x180009fb9  cmp     r8d, [rdx+10h]
0x180009fbd  jz      short loc_180009FFE
0x180009fbf  cmp     ebp, 0FFFFFFFFh
0x180009fc2  jz      short loc_180009FE0
0x180009fc4  inc     ebx
0x180009fc6  jmp     short loc_180009FA0
0x180009fc8  mov     eax, [rdx+0Ch]
0x180009fcb  cmp     [rdi+4], eax
0x180009fce  jnz     short loc_180009FB9
0x180009fd0  mov     [r14], ebx
0x180009fd3  xor     eax, eax
0x180009fd5  add     rsp, 20h
0x180009fd9  pop     r14
0x180009fdb  pop     rdi
0x180009fdc  pop     rsi
0x180009fdd  pop     rbp
0x180009fde  pop     rbx
0x180009fdf  retn
0x180009fe0  cmp     qword ptr [rdx], 0
0x180009fe4  cmovz   ebp, ebx
0x180009fe7  jmp     short loc_180009FC4
0x180009fe9  test    r9d, r9d
0x180009fec  jnz     short loc_18000A008
0x180009fee  mov     eax, 8ADh
0x180009ff3  add     rsp, 20h
0x180009ff7  pop     r14
0x180009ff9  pop     rdi
0x180009ffa  pop     rsi
0x180009ffb  pop     rbp
0x180009ffc  pop     rbx
0x180009ffd  retn
0x180009ffe  mov     eax, [rdx+14h]
0x18000a001  cmp     [rdi+4], eax
0x18000a004  jnz     short loc_180009FBF
0x18000a006  jmp     short loc_180009FD0
0x18000a008  cmp     ebp, 0FFFFFFFFh
0x18000a00b  jnz     short loc_18000A01B
0x18000a00d  mov     rcx, rsi
0x18000a010  call    WsGrowTable
0x18000a015  test    eax, eax
0x18000a017  jnz     short loc_180009FD5
0x18000a019  mov     ebp, ebx
0x18000a01b  mov     eax, ebp
0x18000a01d  mov     rdx, rdi; SourceLuid
0x18000a020  lea     rcx, [rax+rax*2]
0x18000a024  lea     rbx, ds:0[rcx*8]
0x18000a02c  mov     rcx, [rsi]
0x18000a02f  add     rcx, 8
0x18000a033  add     rcx, rbx; DestinationLuid
0x18000a036  call    cs:__imp_RtlCopyLuid
0x18000a03c  mov     rcx, [rsi]
0x18000a03f  mov     rdx, [rsp+48h+SourceLuid]; SourceLuid
0x18000a044  add     rcx, 10h
0x18000a048  add     rcx, rbx; DestinationLuid
0x18000a04b  call    cs:__imp_RtlCopyLuid
0x18000a051  mov     [r14], ebp
0x18000a054  jmp     loc_180009FD3
```
