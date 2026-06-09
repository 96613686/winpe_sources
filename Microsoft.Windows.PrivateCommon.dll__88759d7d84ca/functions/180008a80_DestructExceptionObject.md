# __DestructExceptionObject

- ea: `0x180008a80`
- end: `0x180008af4`
- name: `__DestructExceptionObject`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008c3c`
- `0x1800095ac`
- `0x18000a530`

## callees

- `0x180008a80`
- `0x180008af4`
- `0x180008fc8`
- `0x18000b5fe`
- `0x18000b930`

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
0x180008a80  test    rcx, rcx
0x180008a83  jz      short locret_180008AF3
0x180008a85  mov     [rsp+arg_8], dl
0x180008a89  sub     rsp, 48h
0x180008a8d  cmp     dword ptr [rcx], 0E06D7363h
0x180008a93  jnz     short loc_180008AEF
0x180008a95  cmp     dword ptr [rcx+18h], 4
0x180008a99  jnz     short loc_180008AEF
0x180008a9b  mov     eax, [rcx+20h]
0x180008a9e  cmp     eax, 19930520h
0x180008aa3  jz      short loc_180008AAF
0x180008aa5  add     eax, 0E66CFADFh
0x180008aaa  cmp     eax, 1
0x180008aad  ja      short loc_180008AEF
0x180008aaf  mov     rax, [rcx+30h]
0x180008ab3  test    rax, rax
0x180008ab6  jz      short loc_180008AEF
0x180008ab8  movsxd  rdx, dword ptr [rax+4]
0x180008abc  test    edx, edx
0x180008abe  jz      short loc_180008AD1
0x180008ac0  add     rdx, [rcx+38h]; void *
0x180008ac4  mov     rcx, [rcx+28h]; void *
0x180008ac8  call    ?_CallMemberFunction0@@YAXQEAX0@Z; _CallMemberFunction0(void * const,void * const)
0x180008acd  jmp     short loc_180008AEF
0x180008acf  jmp     short loc_180008AEF
0x180008ad1  test    byte ptr [rax], 10h
0x180008ad4  jz      short loc_180008AEF
0x180008ad6  mov     rax, [rcx+28h]
0x180008ada  mov     rcx, [rax]
0x180008add  test    rcx, rcx
0x180008ae0  jz      short loc_180008AEF
0x180008ae2  mov     rax, [rcx]
0x180008ae5  mov     rax, [rax+10h]
0x180008ae9  call    cs:__guard_dispatch_icall_fptr
0x180008aef  add     rsp, 48h
0x180008af3  retn
0x18000cae1  push    rbx
0x18000cae3  push    rbp
0x18000cae4  sub     rsp, 28h
0x18000cae8  mov     rbp, rdx
0x18000caeb  mov     [rbp+30h], rcx
0x18000caef  cmp     byte ptr [rbp+58h], 0
0x18000caf3  jz      short loc_18000CB61
0x18000caf5  mov     rax, [rbp+30h]
0x18000caf9  mov     rcx, [rax]
0x18000cafc  mov     [rbp+28h], rcx
0x18000cb00  mov     rax, [rbp+28h]
0x18000cb04  cmp     dword ptr [rax], 0E06D7363h
0x18000cb0a  jnz     short loc_18000CB61
0x18000cb0c  mov     rax, [rbp+28h]
0x18000cb10  cmp     dword ptr [rax+18h], 4
0x18000cb14  jnz     short loc_18000CB61
0x18000cb16  mov     rax, [rbp+28h]
0x18000cb1a  cmp     dword ptr [rax+20h], 19930520h
0x18000cb21  jz      short loc_18000CB3D
0x18000cb23  mov     rax, [rbp+28h]
0x18000cb27  cmp     dword ptr [rax+20h], 19930521h
0x18000cb2e  jz      short loc_18000CB3D
0x18000cb30  mov     rax, [rbp+28h]
0x18000cb34  cmp     dword ptr [rax+20h], 19930522h
0x18000cb3b  jnz     short loc_18000CB61
0x18000cb3d  call    __vcrt_getptd
0x18000cb42  mov     rcx, [rbp+28h]
0x18000cb46  mov     [rax+20h], rcx
0x18000cb4a  mov     rax, [rbp+30h]
0x18000cb4e  mov     rbx, [rax+8]
0x18000cb52  call    __vcrt_getptd
0x18000cb57  mov     [rax+28h], rbx
0x18000cb5b  call    terminate_0
0x18000cb61  mov     dword ptr [rbp+20h], 0
0x18000cb68  mov     eax, [rbp+20h]
0x18000cb6b  add     rsp, 28h
0x18000cb6f  pop     rbp
0x18000cb70  pop     rbx
0x18000cb71  retn
```
