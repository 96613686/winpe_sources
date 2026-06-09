# CreateNotify

- ea: `0x1800091c0`
- end: `0x180009218`
- name: `CreateNotify`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f7c`
- `0x1800091c0`

## pseudocode

```c
__int64 __fastcall CreateNotify(_QWORD *a1)
{
  _DWORD *v2; // rax

  v2 = operator new(0x38u);
  if ( v2 )
  {
    v2[2] = 1;
    *(_QWORD *)v2 = &CNotify::`vftable';
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
    *((_QWORD *)v2 + 4) = 0;
    v2[10] = 0;
    *((_QWORD *)v2 + 6) = 0;
  }
  else
  {
    v2 = 0;
  }
  *a1 = v2;
  return v2 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x1800091c0  push    rbx
0x1800091c2  sub     rsp, 20h
0x1800091c6  mov     rbx, rcx
0x1800091c9  mov     ecx, 38h ; '8'; Size
0x1800091ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800091d3  xor     edx, edx
0x1800091d5  test    rax, rax
0x1800091d8  jz      short loc_180009200
0x1800091da  lea     rcx, ??_7CNotify@@6B@; const CNotify::`vftable'
0x1800091e1  mov     dword ptr [rax+8], 1
0x1800091e8  mov     [rax], rcx
0x1800091eb  mov     [rax+10h], rdx
0x1800091ef  mov     [rax+18h], rdx
0x1800091f3  mov     [rax+20h], rdx
0x1800091f7  mov     [rax+28h], edx
0x1800091fa  mov     [rax+30h], rdx
0x1800091fe  jmp     short loc_180009203
0x180009200  mov     rax, rdx
0x180009203  mov     [rbx], rax
0x180009206  neg     rax
0x180009209  sbb     eax, eax
0x18000920b  not     eax
0x18000920d  and     eax, 8007000Eh
0x180009212  add     rsp, 20h
0x180009216  pop     rbx
0x180009217  retn
```
