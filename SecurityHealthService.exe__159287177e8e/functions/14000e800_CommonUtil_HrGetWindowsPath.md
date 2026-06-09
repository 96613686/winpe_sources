# CommonUtil::HrGetWindowsPath

- ea: `0x14000e800`
- end: `0x14000e8ae`
- name: `CommonUtil::HrGetWindowsPath`
- size: `174`
- prototype: `__int64 __fastcall(__int64 (__fastcall *)(void *, _QWORD), _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000eb7c`

## callees

- `0x1400015f4`
- `0x140005578`
- `0x14000e800`
- `0x140011234`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrGetWindowsPath(__int64 (__fastcall *a1)(void *, _QWORD), _QWORD *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // edi
  int v11; // ebx
  _WORD *v12; // rbx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  unsigned int LastFailure; // edi
  __int64 v19; // rax
  void *v20; // [rsp+50h] [rbp+8h] BYREF

  *a2 = 0;
  v4 = a1(0, 0);
  v9 = v4;
  if ( !v4 )
    return HrGetLastFailure(v6, v5, v7, v8);
  v20 = 0;
  v11 = CommonUtil::MpNewBuffer<unsigned short>(&v20, v4);
  if ( v11 >= 0 )
  {
    v12 = v20;
    v13 = a1(v20, v9);
    v17 = v9 - 1;
    if ( v13 == (_DWORD)v17 )
    {
      v19 = (unsigned int)(v13 - 1);
      if ( v12[v19] == 92 )
        v12[(unsigned int)v19] = 0;
      *a2 = v12;
      return 0;
    }
    else
    {
      LastFailure = HrGetLastFailure(v17, v14, v15, v16);
      if ( v12 )
        operator delete(v12);
      return LastFailure;
    }
  }
  else
  {
    if ( v20 )
      operator delete(v20);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x14000e800  push    rbx
0x14000e802  push    rbp
0x14000e803  push    rsi
0x14000e804  push    rdi
0x14000e805  sub     rsp, 28h
0x14000e809  mov     rbp, rcx
0x14000e80c  mov     qword ptr [rdx], 0
0x14000e813  mov     rsi, rdx
0x14000e816  mov     rax, rbp
0x14000e819  xor     edx, edx
0x14000e81b  xor     ecx, ecx
0x14000e81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e822  mov     edi, eax
0x14000e824  test    eax, eax
0x14000e826  jnz     short loc_14000E82F
0x14000e828  call    HrGetLastFailure
0x14000e82d  jmp     short loc_14000E8A5
0x14000e82f  mov     rdx, rdi
0x14000e832  mov     [rsp+48h+arg_0], 0
0x14000e83b  lea     rcx, [rsp+48h+arg_0]
0x14000e840  call    ??$MpNewBuffer@G@CommonUtil@@YAJPEAPEAG_K@Z; CommonUtil::MpNewBuffer<ushort>(ushort * *,unsigned __int64)
0x14000e845  mov     ebx, eax
0x14000e847  test    eax, eax
0x14000e849  jns     short loc_14000E85E
0x14000e84b  mov     rcx, [rsp+48h+arg_0]; void *
0x14000e850  test    rcx, rcx
0x14000e853  jz      short loc_14000E85A
0x14000e855  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e85a  mov     eax, ebx
0x14000e85c  jmp     short loc_14000E8A5
0x14000e85e  mov     rbx, [rsp+48h+arg_0]
0x14000e863  mov     edx, edi
0x14000e865  mov     rcx, rbx
0x14000e868  mov     rax, rbp
0x14000e86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e870  lea     ecx, [rdi-1]
0x14000e873  cmp     eax, ecx
0x14000e875  jz      short loc_14000E88F
0x14000e877  call    HrGetLastFailure
0x14000e87c  mov     edi, eax
0x14000e87e  test    rbx, rbx
0x14000e881  jz      short loc_14000E88B
0x14000e883  mov     rcx, rbx; void *
0x14000e886  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e88b  mov     eax, edi
0x14000e88d  jmp     short loc_14000E8A5
0x14000e88f  dec     eax
0x14000e891  mov     ecx, eax
0x14000e893  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x14000e898  jnz     short loc_14000E8A0
0x14000e89a  xor     eax, eax
0x14000e89c  mov     [rbx+rcx*2], ax
0x14000e8a0  mov     [rsi], rbx
0x14000e8a3  xor     eax, eax
0x14000e8a5  add     rsp, 28h
0x14000e8a9  pop     rdi
0x14000e8aa  pop     rsi
0x14000e8ab  pop     rbp
0x14000e8ac  pop     rbx
0x14000e8ad  retn
```
