# CommonUtil::HrGetWindowsPath

- ea: `0x14000d778`
- end: `0x14000d826`
- name: `CommonUtil::HrGetWindowsPath`
- size: `174`
- prototype: `__int64 __fastcall(__int64 (__fastcall *)(void *, _QWORD), _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d968`

## callees

- `0x140001614`
- `0x14000d6b0`
- `0x14000d778`
- `0x14000f7c8`
- `0x140011010`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrGetWindowsPath(__int64 (__fastcall *a1)(void *, _QWORD), _QWORD *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned int v8; // edi
  int v10; // ebx
  _WORD *v11; // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx
  unsigned int LastFailure; // edi
  __int64 v17; // rax
  void *v18; // [rsp+50h] [rbp+8h] BYREF

  *a2 = 0;
  v4 = a1(0, 0);
  v8 = v4;
  if ( !v4 )
    return HrGetLastFailure(v6, v5, v7);
  v18 = 0;
  v10 = CommonUtil::MpNewBuffer<unsigned short>(&v18, v4);
  if ( v10 >= 0 )
  {
    v11 = v18;
    v12 = a1(v18, v8);
    v15 = v8 - 1;
    if ( v12 == (_DWORD)v15 )
    {
      v17 = (unsigned int)(v12 - 1);
      if ( v11[v17] == 92 )
        v11[(unsigned int)v17] = 0;
      *a2 = v11;
      return 0;
    }
    else
    {
      LastFailure = HrGetLastFailure(v15, v13, v14);
      if ( v11 )
        operator delete(v11);
      return LastFailure;
    }
  }
  else
  {
    if ( v18 )
      operator delete(v18);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x14000d778  push    rbx
0x14000d77a  push    rbp
0x14000d77b  push    rsi
0x14000d77c  push    rdi
0x14000d77d  sub     rsp, 28h
0x14000d781  mov     rbp, rcx
0x14000d784  mov     qword ptr [rdx], 0
0x14000d78b  mov     rsi, rdx
0x14000d78e  mov     rax, rbp
0x14000d791  xor     edx, edx
0x14000d793  xor     ecx, ecx
0x14000d795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d79a  mov     edi, eax
0x14000d79c  test    eax, eax
0x14000d79e  jnz     short loc_14000D7A7
0x14000d7a0  call    HrGetLastFailure
0x14000d7a5  jmp     short loc_14000D81D
0x14000d7a7  mov     rdx, rdi
0x14000d7aa  mov     [rsp+48h+arg_0], 0
0x14000d7b3  lea     rcx, [rsp+48h+arg_0]
0x14000d7b8  call    ??$MpNewBuffer@G@CommonUtil@@YAJPEAPEAG_K@Z; CommonUtil::MpNewBuffer<ushort>(ushort * *,unsigned __int64)
0x14000d7bd  mov     ebx, eax
0x14000d7bf  test    eax, eax
0x14000d7c1  jns     short loc_14000D7D6
0x14000d7c3  mov     rcx, [rsp+48h+arg_0]; void *
0x14000d7c8  test    rcx, rcx
0x14000d7cb  jz      short loc_14000D7D2
0x14000d7cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d7d2  mov     eax, ebx
0x14000d7d4  jmp     short loc_14000D81D
0x14000d7d6  mov     rbx, [rsp+48h+arg_0]
0x14000d7db  mov     edx, edi
0x14000d7dd  mov     rcx, rbx
0x14000d7e0  mov     rax, rbp
0x14000d7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7e8  lea     ecx, [rdi-1]
0x14000d7eb  cmp     eax, ecx
0x14000d7ed  jz      short loc_14000D807
0x14000d7ef  call    HrGetLastFailure
0x14000d7f4  mov     edi, eax
0x14000d7f6  test    rbx, rbx
0x14000d7f9  jz      short loc_14000D803
0x14000d7fb  mov     rcx, rbx; void *
0x14000d7fe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d803  mov     eax, edi
0x14000d805  jmp     short loc_14000D81D
0x14000d807  dec     eax
0x14000d809  mov     ecx, eax
0x14000d80b  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x14000d810  jnz     short loc_14000D818
0x14000d812  xor     eax, eax
0x14000d814  mov     [rbx+rcx*2], ax
0x14000d818  mov     [rsi], rbx
0x14000d81b  xor     eax, eax
0x14000d81d  add     rsp, 28h
0x14000d821  pop     rdi
0x14000d822  pop     rsi
0x14000d823  pop     rbp
0x14000d824  pop     rbx
0x14000d825  retn
```
