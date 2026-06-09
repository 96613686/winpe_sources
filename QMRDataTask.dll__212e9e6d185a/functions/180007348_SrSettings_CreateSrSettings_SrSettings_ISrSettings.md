# SrSettings::CreateSrSettings(SrSettings::ISrSettings * *)

- ea: `0x180007348`
- end: `0x180007473`
- name: `?CreateSrSettings@SrSettings@@YAJPEAPEAUISrSettings@1@@Z`
- size: `299`
- prototype: `__int64 __fastcall(SrSettings *__hidden this, struct SrSettings::ISrSettings **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003140`

## callees

- `0x180001404`
- `0x180001d06`
- `0x180007348`
- `0x1800142d2`

## pseudocode

```c
__int64 __fastcall SrSettings::CreateSrSettings(SrSettings *this, struct SrSettings::ISrSettings **a2)
{
  _WORD *v4; // rax
  _WORD *v5; // rbx
  _BYTE Src[3752]; // [rsp+20h] [rbp-EA8h] BYREF

  if ( !this )
    return 2147942487LL;
  v4 = operator new(0xF78u);
  v5 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = &SrSettings::CSrSettings::`vftable';
    v4[12] = 0;
    *((_QWORD *)v4 + 1) = v4 + 12;
    *((_QWORD *)v4 + 2) = v4 + 12;
    v4[28] = 0;
    *((_QWORD *)v4 + 5) = v4 + 28;
    *((_QWORD *)v4 + 6) = v4 + 28;
    v4[44] = 0;
    *((_QWORD *)v4 + 9) = v4 + 44;
    *((_QWORD *)v4 + 10) = v4 + 44;
    v4[60] = 0;
    *((_QWORD *)v4 + 13) = v4 + 60;
    *((_QWORD *)v4 + 14) = v4 + 60;
    v4[76] = 0;
    *((_QWORD *)v4 + 17) = v4 + 76;
    *((_QWORD *)v4 + 18) = v4 + 76;
    *((_QWORD *)v4 + 21) = v4 + 84;
    *((_QWORD *)v4 + 22) = v4 + 84;
    *((_QWORD *)v4 + 23) = v4 + 84;
    *((_QWORD *)v4 + 24) = 0;
    v4[1972] = 0;
    *((_BYTE *)v4 + 3946) = 0;
    *((_QWORD *)v4 + 494) = 0;
    memset_0(Src, 0, 0xEA0u);
    memcpy_0(v5 + 100, Src, 0xEA0u);
    *(_QWORD *)this = v5;
    return v5 == 0 ? 0x8007000E : 0;
  }
  else
  {
    *(_QWORD *)this = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180007348  mov     [rsp+arg_8], rbx
0x18000734d  push    rdi
0x18000734e  sub     rsp, 0EC0h
0x180007355  mov     rdi, rcx
0x180007358  test    rcx, rcx
0x18000735b  jnz     short loc_180007367
0x18000735d  mov     eax, 80070057h
0x180007362  jmp     loc_180007462
0x180007367  mov     ecx, 0F78h; Size
0x18000736c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007371  mov     [rsp+0EC8h+arg_0], rax
0x180007379  mov     rbx, rax
0x18000737c  test    rax, rax
0x18000737f  jz      loc_180007456
0x180007385  xor     ecx, ecx
0x180007387  lea     rdx, [rbx+18h]
0x18000738b  lea     rax, ??_7CSrSettings@SrSettings@@6B@; const SrSettings::CSrSettings::`vftable'
0x180007392  mov     r8d, 0EA0h; Size
0x180007398  mov     [rbx], rax
0x18000739b  xor     eax, eax
0x18000739d  mov     [rdx], cx
0x1800073a0  lea     rcx, [rbx+38h]
0x1800073a4  mov     [rbx+8], rdx
0x1800073a8  mov     [rbx+10h], rdx
0x1800073ac  xor     edx, edx; Val
0x1800073ae  mov     [rcx], ax
0x1800073b1  mov     [rbx+28h], rcx
0x1800073b5  mov     [rbx+30h], rcx
0x1800073b9  lea     rcx, [rbx+58h]
0x1800073bd  mov     [rcx], ax
0x1800073c0  mov     [rbx+48h], rcx
0x1800073c4  mov     [rbx+50h], rcx
0x1800073c8  lea     rcx, [rbx+78h]
0x1800073cc  mov     [rcx], ax
0x1800073cf  mov     [rbx+68h], rcx
0x1800073d3  mov     [rbx+70h], rcx
0x1800073d7  lea     rcx, [rbx+98h]
0x1800073de  mov     [rcx], ax
0x1800073e1  lea     rax, [rbx+0A8h]
0x1800073e8  mov     [rbx+88h], rcx
0x1800073ef  mov     [rbx+90h], rcx
0x1800073f6  lea     rcx, [rsp+0EC8h+Src]; void *
0x1800073fb  mov     [rax], rax
0x1800073fe  mov     [rax+8], rax
0x180007402  mov     [rax+10h], rax
0x180007406  mov     qword ptr [rax+18h], 0
0x18000740e  mov     word ptr [rbx+0F68h], 0
0x180007417  mov     byte ptr [rbx+0F6Ah], 0
0x18000741e  mov     qword ptr [rbx+0F70h], 0
0x180007429  call    memset_0
0x18000742e  lea     rcx, [rbx+0C8h]; void *
0x180007435  mov     r8d, 0EA0h; Size
0x18000743b  lea     rdx, [rsp+0EC8h+Src]; Src
0x180007440  call    memcpy_0
0x180007445  mov     [rdi], rbx
0x180007448  neg     rbx
0x18000744b  sbb     eax, eax
0x18000744d  not     eax
0x18000744f  and     eax, 8007000Eh
0x180007454  jmp     short loc_180007462
0x180007456  mov     qword ptr [rdi], 0
0x18000745d  mov     eax, 8007000Eh
0x180007462  mov     rbx, [rsp+0EC8h+arg_8]
0x18000746a  add     rsp, 0EC0h
0x180007471  pop     rdi
0x180007472  retn
```
