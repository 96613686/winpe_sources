# CDetourDis::CopyVex3(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x180031b10`
- end: `0x180031c14`
- name: `?CopyVex3@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `260`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180031b10`
- `0x180032010`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyVex3(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  *a3 = *a4;
  a3[1] = a4[1];
  a3[2] = a4[2];
  *((_DWORD *)this + 2) |= (a4[2] & 0x80u) != 0;
  return CDetourDis::CopyVexCommon(this, a4[1] & 0x1F, a3 + 3, a4 + 3);
}

```

## disassembly

```asm
0x180031b10  mov     [rsp+arg_18], r9
0x180031b15  mov     [rsp+arg_10], r8
0x180031b1a  mov     [rsp+arg_8], rdx
0x180031b1f  mov     [rsp+arg_0], rcx
0x180031b24  sub     rsp, 38h
0x180031b28  mov     eax, 1
0x180031b2d  imul    rax, 0
0x180031b31  mov     ecx, 1
0x180031b36  imul    rcx, 0
0x180031b3a  mov     rdx, [rsp+38h+arg_10]
0x180031b3f  mov     r8, [rsp+38h+arg_18]
0x180031b44  movzx   eax, byte ptr [r8+rax]
0x180031b49  mov     [rdx+rcx], al
0x180031b4c  mov     eax, 1
0x180031b51  imul    rax, 1
0x180031b55  mov     ecx, 1
0x180031b5a  imul    rcx, 1
0x180031b5e  mov     rdx, [rsp+38h+arg_10]
0x180031b63  mov     r8, [rsp+38h+arg_18]
0x180031b68  movzx   eax, byte ptr [r8+rax]
0x180031b6d  mov     [rdx+rcx], al
0x180031b70  mov     eax, 1
0x180031b75  imul    rax, 2
0x180031b79  mov     ecx, 1
0x180031b7e  imul    rcx, 2
0x180031b82  mov     rdx, [rsp+38h+arg_10]
0x180031b87  mov     r8, [rsp+38h+arg_18]
0x180031b8c  movzx   eax, byte ptr [r8+rax]
0x180031b91  mov     [rdx+rcx], al
0x180031b94  mov     eax, 1
0x180031b99  imul    rax, 2
0x180031b9d  mov     rcx, [rsp+38h+arg_18]
0x180031ba2  movzx   eax, byte ptr [rcx+rax]
0x180031ba6  and     eax, 80h
0x180031bab  test    eax, eax
0x180031bad  jz      short loc_180031BB9
0x180031baf  mov     [rsp+38h+var_18], 1
0x180031bb7  jmp     short loc_180031BC1
0x180031bb9  mov     [rsp+38h+var_18], 0
0x180031bc1  mov     rax, [rsp+38h+arg_0]
0x180031bc6  mov     ecx, [rsp+38h+var_18]
0x180031bca  mov     eax, [rax+8]
0x180031bcd  or      eax, ecx
0x180031bcf  mov     rcx, [rsp+38h+arg_0]
0x180031bd4  mov     [rcx+8], eax
0x180031bd7  mov     rax, [rsp+38h+arg_18]
0x180031bdc  add     rax, 3
0x180031be0  mov     rcx, [rsp+38h+arg_10]
0x180031be5  add     rcx, 3
0x180031be9  mov     edx, 1
0x180031bee  imul    rdx, 1
0x180031bf2  mov     r8, [rsp+38h+arg_18]
0x180031bf7  movzx   edx, byte ptr [r8+rdx]
0x180031bfc  and     edx, 1Fh; unsigned __int8
0x180031bff  mov     r9, rax; unsigned __int8 *
0x180031c02  mov     r8, rcx; unsigned __int8 *
0x180031c05  mov     rcx, [rsp+38h+arg_0]; this
0x180031c0a  call    ?CopyVexCommon@CDetourDis@@IEAAPEAEEPEAE0@Z; CDetourDis::CopyVexCommon(uchar,uchar *,uchar *)
0x180031c0f  add     rsp, 38h
0x180031c13  retn
```
