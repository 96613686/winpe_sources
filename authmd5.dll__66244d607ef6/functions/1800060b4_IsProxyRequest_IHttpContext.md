# IsProxyRequest(IHttpContext *)

- ea: `0x1800060b4`
- end: `0x180006196`
- name: `?IsProxyRequest@@YAHPEAVIHttpContext@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct IHttpContext *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e00`

## callees

- `0x1800060b4`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall IsProxyRequest(struct IHttpContext *a1)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  _BYTE *v5; // rcx
  __int64 v6; // rax
  _BYTE *v7; // rdx
  char v8; // al

  v2 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  if ( (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 16LL))(v2, 8) )
    return 1;
  v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  if ( (*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v3 + 24LL))(v3, "Forward", 0) )
    return 1;
  v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v5 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 16LL))(v4, 40);
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    v7 = &v5[(unsigned int)v6 - 3];
    while ( v5 < v7 )
    {
      if ( ((*v5 - 86) & 0xDF) == 0 && v5[1] == 105 && v5[2] == 97 )
      {
        v8 = v5[3];
        if ( v8 == 32 || v8 == 58 )
          return 1;
      }
      ++v5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800060b4  push    rbx
0x1800060b6  sub     rsp, 20h
0x1800060ba  mov     rax, [rcx]
0x1800060bd  mov     rbx, rcx
0x1800060c0  mov     rax, [rax+18h]
0x1800060c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c9  xor     r8d, r8d
0x1800060cc  mov     rcx, rax
0x1800060cf  mov     rdx, [rax]
0x1800060d2  mov     rax, [rdx+10h]
0x1800060d6  lea     edx, [r8+8]
0x1800060da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060df  test    rax, rax
0x1800060e2  jnz     loc_18000618B
0x1800060e8  mov     rax, [rbx]
0x1800060eb  mov     rcx, rbx
0x1800060ee  mov     rax, [rax+18h]
0x1800060f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f7  mov     r9, rax
0x1800060fa  lea     rdx, aForward; "Forward"
0x180006101  xor     r8d, r8d
0x180006104  mov     rcx, [rax]
0x180006107  mov     rax, [rcx+18h]
0x18000610b  mov     rcx, r9
0x18000610e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006113  test    rax, rax
0x180006116  jnz     short loc_18000618B
0x180006118  mov     rax, [rbx]
0x18000611b  mov     rcx, rbx
0x18000611e  mov     rax, [rax+18h]
0x180006122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006127  mov     r9, rax
0x18000612a  xor     r8d, r8d
0x18000612d  mov     rcx, [rax]
0x180006130  lea     edx, [r8+28h]
0x180006134  mov     rax, [rcx+10h]
0x180006138  mov     rcx, r9
0x18000613b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006140  mov     rcx, rax
0x180006143  test    rax, rax
0x180006146  jz      short loc_180006187
0x180006148  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000614c  inc     rax
0x18000614f  cmp     byte ptr [rcx+rax], 0
0x180006153  jnz     short loc_18000614C
0x180006155  mov     edx, eax
0x180006157  add     rdx, 0FFFFFFFFFFFFFFFDh
0x18000615b  add     rdx, rcx
0x18000615e  jmp     short loc_180006182
0x180006160  mov     al, [rcx]
0x180006162  sub     al, 56h ; 'V'
0x180006164  test    al, 0DFh
0x180006166  jnz     short loc_18000617F
0x180006168  cmp     byte ptr [rcx+1], 69h ; 'i'
0x18000616c  jnz     short loc_18000617F
0x18000616e  cmp     byte ptr [rcx+2], 61h ; 'a'
0x180006172  jnz     short loc_18000617F
0x180006174  mov     al, [rcx+3]
0x180006177  cmp     al, 20h ; ' '
0x180006179  jz      short loc_18000618B
0x18000617b  cmp     al, 3Ah ; ':'
0x18000617d  jz      short loc_18000618B
0x18000617f  inc     rcx
0x180006182  cmp     rcx, rdx
0x180006185  jb      short loc_180006160
0x180006187  xor     eax, eax
0x180006189  jmp     short loc_180006190
0x18000618b  mov     eax, 1
0x180006190  add     rsp, 20h
0x180006194  pop     rbx
0x180006195  retn
```
