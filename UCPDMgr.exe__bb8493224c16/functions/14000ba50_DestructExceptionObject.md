# __DestructExceptionObject

- ea: `0x14000ba50`
- end: `0x14000bac3`
- name: `__DestructExceptionObject`
- size: `115`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000bc38`
- `0x14000c4a4`
- `0x14000d4b0`

## callees

- `0x14000a377`
- `0x14000ba50`
- `0x14000bacc`
- `0x14000be88`
- `0x14000f4d0`

## pseudocode

```c
void __fastcall _DestructExceptionObject(__int64 a1)
{
  int v1; // eax
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx

  if ( a1 )
  {
    if ( *(_DWORD *)a1 == -529697949 && *(_DWORD *)(a1 + 24) == 4 )
    {
      v1 = *(_DWORD *)(a1 + 32);
      if ( v1 == 429065504 || (unsigned int)(v1 - 429065505) <= 1 )
      {
        v2 = *(_QWORD *)(a1 + 48);
        if ( v2 )
        {
          v3 = *(int *)(v2 + 4);
          if ( (_DWORD)v3 )
          {
            ((void (__fastcall *)(_QWORD))(*(_QWORD *)(a1 + 56) + v3))(*(_QWORD *)(a1 + 40));
          }
          else if ( (*(_BYTE *)v2 & 0x10) != 0 )
          {
            v4 = **(_QWORD **)(a1 + 40);
            if ( v4 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14000ba50  test    rcx, rcx
0x14000ba53  jz      short locret_14000BAC2
0x14000ba55  mov     [rsp+arg_8], dl
0x14000ba59  sub     rsp, 48h
0x14000ba5d  cmp     dword ptr [rcx], 0E06D7363h
0x14000ba63  jnz     short loc_14000BABE
0x14000ba65  cmp     dword ptr [rcx+18h], 4
0x14000ba69  jnz     short loc_14000BABE
0x14000ba6b  mov     eax, [rcx+20h]
0x14000ba6e  cmp     eax, 19930520h
0x14000ba73  jz      short loc_14000BA7F
0x14000ba75  add     eax, 0E66CFADFh
0x14000ba7a  cmp     eax, 1
0x14000ba7d  ja      short loc_14000BABE
0x14000ba7f  mov     rax, [rcx+30h]
0x14000ba83  test    rax, rax
0x14000ba86  jz      short loc_14000BABE
0x14000ba88  movsxd  rdx, dword ptr [rax+4]
0x14000ba8c  test    edx, edx
0x14000ba8e  jz      short loc_14000BAA1
0x14000ba90  add     rdx, [rcx+38h]; void *
0x14000ba94  mov     rcx, [rcx+28h]; void *
0x14000ba98  call    ?_CallMemberFunction0@@YAXQEAX0@Z; _CallMemberFunction0(void * const,void * const)
0x14000ba9d  jmp     short loc_14000BABE
0x14000ba9f  jmp     short loc_14000BABE
0x14000baa1  test    byte ptr [rax], 10h
0x14000baa4  jz      short loc_14000BABE
0x14000baa6  mov     rax, [rcx+28h]
0x14000baaa  mov     rcx, [rax]
0x14000baad  test    rcx, rcx
0x14000bab0  jz      short loc_14000BABE
0x14000bab2  mov     rax, [rcx]
0x14000bab5  mov     rax, [rax+10h]
0x14000bab9  call    _guard_dispatch_icall
0x14000babe  add     rsp, 48h
0x14000bac2  retn
0x140010080  push    rbx
0x140010082  push    rbp
0x140010083  sub     rsp, 28h
0x140010087  mov     rbp, rdx
0x14001008a  mov     [rbp+30h], rcx
0x14001008e  cmp     byte ptr [rbp+58h], 0
0x140010092  jz      short loc_140010100
0x140010094  mov     rax, [rbp+30h]
0x140010098  mov     rcx, [rax]
0x14001009b  mov     [rbp+28h], rcx
0x14001009f  mov     rax, [rbp+28h]
0x1400100a3  cmp     dword ptr [rax], 0E06D7363h
0x1400100a9  jnz     short loc_140010100
0x1400100ab  mov     rax, [rbp+28h]
0x1400100af  cmp     dword ptr [rax+18h], 4
0x1400100b3  jnz     short loc_140010100
0x1400100b5  mov     rax, [rbp+28h]
0x1400100b9  cmp     dword ptr [rax+20h], 19930520h
0x1400100c0  jz      short loc_1400100DC
0x1400100c2  mov     rax, [rbp+28h]
0x1400100c6  cmp     dword ptr [rax+20h], 19930521h
0x1400100cd  jz      short loc_1400100DC
0x1400100cf  mov     rax, [rbp+28h]
0x1400100d3  cmp     dword ptr [rax+20h], 19930522h
0x1400100da  jnz     short loc_140010100
0x1400100dc  call    __vcrt_getptd
0x1400100e1  mov     rcx, [rbp+28h]
0x1400100e5  mov     [rax+20h], rcx
0x1400100e9  mov     rax, [rbp+30h]
0x1400100ed  mov     rbx, [rax+8]
0x1400100f1  call    __vcrt_getptd
0x1400100f6  mov     [rax+28h], rbx
0x1400100fa  call    _o_terminate_0
0x1400100ff  nop
0x140010100  mov     dword ptr [rbp+20h], 0
0x140010107  mov     eax, [rbp+20h]
0x14001010a  add     rsp, 28h
0x14001010e  pop     rbp
0x14001010f  pop     rbx
0x140010110  retn
```
