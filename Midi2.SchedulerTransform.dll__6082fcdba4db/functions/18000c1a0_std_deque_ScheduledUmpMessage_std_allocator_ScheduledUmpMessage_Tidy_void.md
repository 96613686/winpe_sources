# std::deque<ScheduledUmpMessage,std::allocator<ScheduledUmpMessage>>::_Tidy(void)

- ea: `0x18000c1a0`
- end: `0x18000c275`
- name: `?_Tidy@?$deque@UScheduledUmpMessage@@V?$allocator@UScheduledUmpMessage@@@std@@@std@@AEAAXXZ`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18000ba70`
- `0x18000c694`

## callees

- `0x180002024`
- `0x18000a83c`
- `0x18000c1a0`

## pseudocode

```c
void __fastcall std::deque<ScheduledUmpMessage>::_Tidy(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v4; // rdi
  void *v5; // rcx
  __int64 v6; // rcx
  void *v7; // rax

  while ( 1 )
  {
    v2 = a1[4];
    if ( !v2 )
      break;
    std::vector<unsigned char>::~vector<unsigned char>(*(_QWORD *)(a1[1] + 8 * ((a1[2] - 1LL) & (a1[3] - 1LL + v2))) + 16LL);
    if ( a1[4]-- == 1 )
      a1[3] = 0;
  }
  if ( a1[1] )
  {
    v4 = a1[2];
    while ( v4 > 0 )
    {
      --v4;
      v5 = *(void **)(a1[1] + 8 * v4);
      if ( v5 )
        operator delete(v5);
    }
    v6 = a1[1];
    if ( (unsigned __int64)(8LL * a1[2]) < 0x1000 )
    {
      v7 = (void *)a1[1];
    }
    else
    {
      v7 = *(void **)(v6 - 8);
      if ( (unsigned __int64)(v6 - (_QWORD)v7 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v7);
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18000c1a0  mov     [rsp+arg_8], rbx
0x18000c1a5  push    rdi
0x18000c1a6  sub     rsp, 20h
0x18000c1aa  mov     rbx, rcx
0x18000c1ad  mov     rcx, [rbx+20h]
0x18000c1b1  test    rcx, rcx
0x18000c1b4  jz      short loc_18000C1EC
0x18000c1b6  mov     rax, [rbx+18h]
0x18000c1ba  dec     rax
0x18000c1bd  add     rcx, rax
0x18000c1c0  mov     rax, [rbx+10h]
0x18000c1c4  dec     rax
0x18000c1c7  and     rcx, rax
0x18000c1ca  mov     rax, [rbx+8]
0x18000c1ce  mov     rcx, [rax+rcx*8]
0x18000c1d2  add     rcx, 10h
0x18000c1d6  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000c1db  sub     qword ptr [rbx+20h], 1
0x18000c1e0  jnz     short loc_18000C1AD
0x18000c1e2  mov     qword ptr [rbx+18h], 0
0x18000c1ea  jmp     short loc_18000C1AD
0x18000c1ec  cmp     qword ptr [rbx+8], 0
0x18000c1f1  jz      short loc_18000C26A
0x18000c1f3  mov     rdi, [rbx+10h]
0x18000c1f7  jmp     short loc_18000C213
0x18000c1f9  mov     rax, [rbx+8]
0x18000c1fd  dec     rdi
0x18000c200  mov     rcx, [rax+rdi*8]; Block
0x18000c204  test    rcx, rcx
0x18000c207  jz      short loc_18000C213
0x18000c209  mov     edx, 28h ; '('
0x18000c20e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c213  test    rdi, rdi
0x18000c216  jg      short loc_18000C1F9
0x18000c218  mov     rax, [rbx+10h]
0x18000c21c  mov     rcx, [rbx+8]
0x18000c220  lea     rdx, ds:0[rax*8]
0x18000c228  cmp     rdx, 1000h
0x18000c22f  jb      short loc_18000C24F
0x18000c231  mov     rax, [rcx-8]
0x18000c235  sub     rcx, rax
0x18000c238  sub     rcx, 8
0x18000c23c  cmp     rcx, 1Fh
0x18000c240  ja      short loc_18000C248
0x18000c242  add     rdx, 27h ; '''
0x18000c246  jmp     short loc_18000C252
0x18000c248  mov     ecx, 5
0x18000c24d  int     29h; Win8: RtlFailFast(ecx)
0x18000c24f  mov     rax, rcx
0x18000c252  mov     rcx, rax; Block
0x18000c255  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c25a  mov     qword ptr [rbx+8], 0
0x18000c262  mov     qword ptr [rbx+10h], 0
0x18000c26a  mov     rbx, [rsp+28h+arg_8]
0x18000c26f  add     rsp, 20h
0x18000c273  pop     rdi
0x18000c274  retn
```
