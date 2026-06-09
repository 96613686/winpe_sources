# OpenRPCDebugClientCallInfoEnumeration(ulong,ulong,int,ulong,void * *)

- ea: `0x180009844`
- end: `0x1800098db`
- name: `?OpenRPCDebugClientCallInfoEnumeration@@YAJKKHKPEAPEAX@Z`
- size: `151`
- prototype: `__int64 __fastcall(int, int, int, unsigned int, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180007b30`
- `0x180007bc0`

## callees

- `0x180002a00`
- `0x180005f48`
- `0x180009844`
- `0x180009df8`
- `0x18000a404`

## pseudocode

```c
__int64 __fastcall OpenRPCDebugClientCallInfoEnumeration(int a1, int a2, int a3, unsigned int a4, void **a5)
{
  void **v9; // rax
  void **v10; // rbx
  unsigned int v12; // eax
  unsigned int v13; // edi
  unsigned int v14; // eax

  *a5 = 0;
  v9 = (void **)operator new(0x18u);
  v10 = v9;
  if ( !v9 )
    return 14;
  *(_DWORD *)v9 = a1;
  *((_DWORD *)v9 + 1) = a2;
  *((_DWORD *)v9 + 3) = a4;
  *((_DWORD *)v9 + 2) = a3;
  if ( !a4 )
  {
    v14 = OpenRPCSystemWideCellEnumeration(v9 + 2);
    if ( v14 )
    {
      v13 = v14;
      goto LABEL_10;
    }
    goto LABEL_7;
  }
  v12 = OpenRPCServerDebugInfo(a4, v9 + 2);
  v13 = v12;
  if ( v12 != 2 )
  {
    if ( v12 )
      goto LABEL_10;
LABEL_7:
    *a5 = v10;
    return 0;
  }
  v13 = 1;
LABEL_10:
  operator delete(v10);
  return v13;
}

```

## disassembly

```asm
0x180009844  push    rbx
0x180009846  push    rbp
0x180009847  push    rsi
0x180009848  push    rdi
0x180009849  push    r14
0x18000984b  push    r15
0x18000984d  sub     rsp, 28h
0x180009851  mov     rsi, [rsp+58h+arg_20]
0x180009859  mov     r15d, ecx
0x18000985c  mov     ecx, 18h; unsigned __int64
0x180009861  mov     edi, r9d
0x180009864  mov     ebp, r8d
0x180009867  mov     r14d, edx
0x18000986a  mov     qword ptr [rsi], 0
0x180009871  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009876  mov     rbx, rax
0x180009879  test    rax, rax
0x18000987c  jnz     short loc_180009883
0x18000987e  lea     eax, [rbx+0Eh]
0x180009881  jmp     short loc_1800098B7
0x180009883  mov     [rax], r15d
0x180009886  lea     rcx, [rax+10h]; void **
0x18000988a  mov     [rax+4], r14d
0x18000988e  mov     [rax+0Ch], edi
0x180009891  mov     [rax+8], ebp
0x180009894  test    edi, edi
0x180009896  jz      short loc_1800098C4
0x180009898  mov     rdx, rcx; void **
0x18000989b  mov     ecx, edi; unsigned int
0x18000989d  call    ?OpenRPCServerDebugInfo@@YAJKPEAPEAX@Z; OpenRPCServerDebugInfo(ulong,void * *)
0x1800098a2  mov     edi, eax
0x1800098a4  cmp     eax, 2
0x1800098a7  jnz     short loc_1800098AE
0x1800098a9  lea     edi, [rax-1]
0x1800098ac  jmp     short loc_1800098CF
0x1800098ae  test    eax, eax
0x1800098b0  jnz     short loc_1800098CF
0x1800098b2  mov     [rsi], rbx
0x1800098b5  xor     eax, eax
0x1800098b7  add     rsp, 28h
0x1800098bb  pop     r15
0x1800098bd  pop     r14
0x1800098bf  pop     rdi
0x1800098c0  pop     rsi
0x1800098c1  pop     rbp
0x1800098c2  pop     rbx
0x1800098c3  retn
0x1800098c4  call    ?OpenRPCSystemWideCellEnumeration@@YAJPEAPEAX@Z; OpenRPCSystemWideCellEnumeration(void * *)
0x1800098c9  test    eax, eax
0x1800098cb  jz      short loc_1800098B2
0x1800098cd  mov     edi, eax
0x1800098cf  mov     rcx, rbx; void *
0x1800098d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800098d7  mov     eax, edi
0x1800098d9  jmp     short loc_1800098B7
```
