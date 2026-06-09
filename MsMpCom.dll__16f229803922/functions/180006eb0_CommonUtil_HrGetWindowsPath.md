# CommonUtil::HrGetWindowsPath

- ea: `0x180006eb0`
- end: `0x180006f60`
- name: `CommonUtil::HrGetWindowsPath`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800070b8`

## callees

- `0x180006ce4`
- `0x180006eb0`
- `0x1800090e4`
- `0x18000a010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180006f05`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006f37`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006f05`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006f37`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrGetWindowsPath(__int64 (__fastcall *a1)(_WORD *, _QWORD), _QWORD *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // edi
  int v8; // ebx
  _WORD *v9; // rbx
  int v10; // eax
  __int64 v11; // rcx
  unsigned int LastFailure; // edi
  __int64 v13; // rax
  _WORD *v14; // [rsp+50h] [rbp+8h] BYREF

  *a2 = 0;
  v4 = a1(0, 0);
  v6 = v4;
  if ( !v4 )
    return HrGetLastFailure(v5);
  v14 = 0;
  v8 = CommonUtil::MpNewBuffer<unsigned short>(&v14, v4);
  if ( v8 >= 0 )
  {
    v9 = v14;
    v10 = a1(v14, v6);
    v11 = v6 - 1;
    if ( v10 == (_DWORD)v11 )
    {
      v13 = (unsigned int)(v10 - 1);
      if ( v9[v13] == 92 )
        v9[(unsigned int)v13] = 0;
      *a2 = v9;
      return 0;
    }
    else
    {
      LastFailure = HrGetLastFailure(v11);
      if ( v9 )
        operator delete[](v9);
      return LastFailure;
    }
  }
  else
  {
    if ( v14 )
      operator delete[](v14);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x180006eb0  push    rbx
0x180006eb2  push    rbp
0x180006eb3  push    rsi
0x180006eb4  push    rdi
0x180006eb5  sub     rsp, 28h
0x180006eb9  mov     rbp, rcx
0x180006ebc  mov     qword ptr [rdx], 0
0x180006ec3  mov     rsi, rdx
0x180006ec6  mov     rax, rbp
0x180006ec9  xor     edx, edx
0x180006ecb  xor     ecx, ecx
0x180006ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed2  mov     edi, eax
0x180006ed4  test    eax, eax
0x180006ed6  jnz     short loc_180006EDF
0x180006ed8  call    HrGetLastFailure
0x180006edd  jmp     short loc_180006F57
0x180006edf  mov     rdx, rdi
0x180006ee2  mov     [rsp+48h+arg_0], 0
0x180006eeb  lea     rcx, [rsp+48h+arg_0]
0x180006ef0  call    ??$MpNewBuffer@G@CommonUtil@@YAJPEAPEAG_K@Z; CommonUtil::MpNewBuffer<ushort>(ushort * *,unsigned __int64)
0x180006ef5  mov     ebx, eax
0x180006ef7  test    eax, eax
0x180006ef9  jns     short loc_180006F0F
0x180006efb  mov     rcx, [rsp+48h+arg_0]
0x180006f00  test    rcx, rcx
0x180006f03  jz      short loc_180006F0B
0x180006f05  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006f0b  mov     eax, ebx
0x180006f0d  jmp     short loc_180006F57
0x180006f0f  mov     rbx, [rsp+48h+arg_0]
0x180006f14  mov     edx, edi
0x180006f16  mov     rcx, rbx
0x180006f19  mov     rax, rbp
0x180006f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f21  lea     ecx, [rdi-1]
0x180006f24  cmp     eax, ecx
0x180006f26  jz      short loc_180006F41
0x180006f28  call    HrGetLastFailure
0x180006f2d  mov     edi, eax
0x180006f2f  test    rbx, rbx
0x180006f32  jz      short loc_180006F3D
0x180006f34  mov     rcx, rbx
0x180006f37  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006f3d  mov     eax, edi
0x180006f3f  jmp     short loc_180006F57
0x180006f41  dec     eax
0x180006f43  mov     ecx, eax
0x180006f45  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x180006f4a  jnz     short loc_180006F52
0x180006f4c  xor     eax, eax
0x180006f4e  mov     [rbx+rcx*2], ax
0x180006f52  mov     [rsi], rbx
0x180006f55  xor     eax, eax
0x180006f57  add     rsp, 28h
0x180006f5b  pop     rdi
0x180006f5c  pop     rsi
0x180006f5d  pop     rbp
0x180006f5e  pop     rbx
0x180006f5f  retn
```
