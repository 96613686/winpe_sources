# ScheduledUmpMessage::operator=(ScheduledUmpMessage &&)

- ea: `0x18000a99c`
- end: `0x18000aa66`
- name: `??4ScheduledUmpMessage@@QEAAAEAU0@$$QEAU0@@Z`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18000a08c`
- `0x18000a1e4`

## callees

- `0x180002024`
- `0x18000a99c`

## pseudocode

```c
__int64 __fastcall ScheduledUmpMessage::operator=(__int64 a1, __int64 a2)
{
  char **v2; // rsi
  char **v3; // rbx
  char *v5; // rax
  char *v6; // rcx

  v2 = (char **)(a2 + 16);
  *(_QWORD *)a1 = *(_QWORD *)a2;
  v3 = (char **)(a1 + 16);
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 8);
  *(_DWORD *)(a1 + 12) = *(_DWORD *)(a2 + 12);
  if ( a1 + 16 != a2 + 16 )
  {
    v5 = *v3;
    if ( *v3 )
    {
      if ( *(_QWORD *)(a1 + 32) - (_QWORD)v5 < 0x1000u )
      {
        v6 = *v3;
      }
      else
      {
        v6 = (char *)*((_QWORD *)v5 - 1);
        if ( (unsigned __int64)(v5 - v6 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v6);
      *v3 = 0;
      v3[1] = 0;
      v3[2] = 0;
    }
    *v3 = *v2;
    v3[1] = v2[1];
    v3[2] = v2[2];
    *v2 = 0;
    v2[1] = 0;
    v2[2] = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000a99c  mov     [rsp+arg_0], rbx
0x18000a9a1  mov     [rsp+arg_8], rsi
0x18000a9a6  push    rdi
0x18000a9a7  sub     rsp, 20h
0x18000a9ab  mov     rax, [rdx]
0x18000a9ae  lea     rsi, [rdx+10h]
0x18000a9b2  mov     [rcx], rax
0x18000a9b5  lea     rbx, [rcx+10h]
0x18000a9b9  mov     eax, [rdx+8]
0x18000a9bc  mov     rdi, rcx
0x18000a9bf  mov     [rcx+8], eax
0x18000a9c2  mov     eax, [rdx+0Ch]
0x18000a9c5  mov     [rcx+0Ch], eax
0x18000a9c8  cmp     rbx, rsi
0x18000a9cb  jz      loc_18000AA53
0x18000a9d1  mov     rax, [rbx]
0x18000a9d4  test    rax, rax
0x18000a9d7  jz      short loc_18000AA26
0x18000a9d9  mov     rdx, [rbx+10h]
0x18000a9dd  sub     rdx, rax
0x18000a9e0  cmp     rdx, 1000h
0x18000a9e7  jb      short loc_18000AA07
0x18000a9e9  mov     rcx, [rax-8]
0x18000a9ed  sub     rax, rcx
0x18000a9f0  sub     rax, 8
0x18000a9f4  cmp     rax, 1Fh
0x18000a9f8  ja      short loc_18000AA00
0x18000a9fa  add     rdx, 27h ; '''
0x18000a9fe  jmp     short loc_18000AA0A
0x18000aa00  mov     ecx, 5
0x18000aa05  int     29h; Win8: RtlFailFast(ecx)
0x18000aa07  mov     rcx, rax; Block
0x18000aa0a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aa0f  mov     qword ptr [rbx], 0
0x18000aa16  mov     qword ptr [rbx+8], 0
0x18000aa1e  mov     qword ptr [rbx+10h], 0
0x18000aa26  mov     rax, [rsi]
0x18000aa29  mov     [rbx], rax
0x18000aa2c  mov     rax, [rsi+8]
0x18000aa30  mov     [rbx+8], rax
0x18000aa34  mov     rax, [rsi+10h]
0x18000aa38  mov     [rbx+10h], rax
0x18000aa3c  mov     qword ptr [rsi], 0
0x18000aa43  mov     qword ptr [rsi+8], 0
0x18000aa4b  mov     qword ptr [rsi+10h], 0
0x18000aa53  mov     rbx, [rsp+28h+arg_0]
0x18000aa58  mov     rax, rdi
0x18000aa5b  mov     rsi, [rsp+28h+arg_8]
0x18000aa60  add     rsp, 20h
0x18000aa64  pop     rdi
0x18000aa65  retn
```
