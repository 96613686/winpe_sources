# CDetourDis::CopyEvex(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x180031c20`
- end: `0x180031d56`
- name: `?CopyEvex@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `310`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180031540`
- `0x180031c20`
- `0x180032080`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyEvex(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  char v5; // [rsp+30h] [rbp-18h]
  unsigned __int8 v6; // [rsp+31h] [rbp-17h]

  v6 = a4[1];
  if ( (v6 & 0xC) != 0 )
    return CDetourDis::Invalid(this, (const struct CDetourDis::COPYENTRY *)&qword_1800621C0, a3, a4);
  v5 = a4[2];
  if ( (v5 & 4) != 4 )
    return CDetourDis::Invalid(this, (const struct CDetourDis::COPYENTRY *)&qword_1800621C0, a3, a4);
  *(_DWORD *)a3 = *(_DWORD *)a4;
  *((_DWORD *)this + 4) = 1;
  *((_DWORD *)this + 2) |= v5 < 0;
  return CDetourDis::CopyVexEvexCommon(this, v6 & 3, a3 + 4, a4 + 4, v5 & 3);
}

```

## disassembly

```asm
0x180031c20  mov     [rsp+arg_18], r9
0x180031c25  mov     [rsp+arg_10], r8
0x180031c2a  mov     [rsp+arg_8], rdx
0x180031c2f  mov     [rsp+arg_0], rcx
0x180031c34  sub     rsp, 48h
0x180031c38  mov     eax, 1
0x180031c3d  imul    rax, 1
0x180031c41  mov     rcx, [rsp+48h+arg_18]
0x180031c46  movzx   eax, byte ptr [rcx+rax]
0x180031c4a  mov     [rsp+48h+var_17], al
0x180031c4e  movzx   eax, [rsp+48h+var_17]
0x180031c53  and     eax, 0Ch
0x180031c56  test    eax, eax
0x180031c58  jz      short loc_180031C7A
0x180031c5a  mov     r9, [rsp+48h+arg_18]; unsigned __int8 *
0x180031c5f  mov     r8, [rsp+48h+arg_10]; unsigned __int8 *
0x180031c64  lea     rdx, qword_1800621C0; struct CDetourDis::COPYENTRY *
0x180031c6b  mov     rcx, [rsp+48h+arg_0]; this
0x180031c70  call    ?Invalid@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z; CDetourDis::Invalid(CDetourDis::COPYENTRY const *,uchar *,uchar *)
0x180031c75  jmp     loc_180031D51
0x180031c7a  mov     eax, 1
0x180031c7f  imul    rax, 2
0x180031c83  mov     rcx, [rsp+48h+arg_18]
0x180031c88  movzx   eax, byte ptr [rcx+rax]
0x180031c8c  mov     [rsp+48h+var_18], al
0x180031c90  movzx   eax, [rsp+48h+var_18]
0x180031c95  and     eax, 4
0x180031c98  cmp     eax, 4
0x180031c9b  jz      short loc_180031CBD
0x180031c9d  mov     r9, [rsp+48h+arg_18]; unsigned __int8 *
0x180031ca2  mov     r8, [rsp+48h+arg_10]; unsigned __int8 *
0x180031ca7  lea     rdx, qword_1800621C0; struct CDetourDis::COPYENTRY *
0x180031cae  mov     rcx, [rsp+48h+arg_0]; this
0x180031cb3  call    ?Invalid@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z; CDetourDis::Invalid(CDetourDis::COPYENTRY const *,uchar *,uchar *)
0x180031cb8  jmp     loc_180031D51
0x180031cbd  mov     rax, [rsp+48h+arg_10]
0x180031cc2  mov     rcx, [rsp+48h+arg_18]
0x180031cc7  mov     ecx, [rcx]
0x180031cc9  mov     [rax], ecx
0x180031ccb  mov     rax, [rsp+48h+arg_0]
0x180031cd0  mov     dword ptr [rax+10h], 1
0x180031cd7  movzx   eax, [rsp+48h+var_18]
0x180031cdc  and     eax, 80h
0x180031ce1  test    eax, eax
0x180031ce3  jz      short loc_180031CEF
0x180031ce5  mov     [rsp+48h+var_14], 1
0x180031ced  jmp     short loc_180031CF7
0x180031cef  mov     [rsp+48h+var_14], 0
0x180031cf7  mov     rax, [rsp+48h+arg_0]
0x180031cfc  mov     ecx, [rsp+48h+var_14]
0x180031d00  mov     eax, [rax+8]
0x180031d03  or      eax, ecx
0x180031d05  mov     rcx, [rsp+48h+arg_0]
0x180031d0a  mov     [rcx+8], eax
0x180031d0d  movzx   eax, [rsp+48h+var_18]
0x180031d12  and     eax, 3
0x180031d15  mov     rcx, [rsp+48h+arg_18]
0x180031d1a  add     rcx, 4
0x180031d1e  mov     rdx, [rsp+48h+arg_10]
0x180031d23  add     rdx, 4
0x180031d27  movzx   r8d, [rsp+48h+var_17]
0x180031d2d  and     r8d, 3
0x180031d31  mov     [rsp+48h+var_10], r8d
0x180031d36  mov     [rsp+48h+var_28], al; char
0x180031d3a  mov     r9, rcx; unsigned __int8 *
0x180031d3d  mov     r8, rdx; unsigned __int8 *
0x180031d40  mov     eax, [rsp+48h+var_10]
0x180031d44  movzx   edx, al; unsigned __int8
0x180031d47  mov     rcx, [rsp+48h+arg_0]; this
0x180031d4c  call    ?CopyVexEvexCommon@CDetourDis@@IEAAPEAEEPEAE0E@Z; CDetourDis::CopyVexEvexCommon(uchar,uchar *,uchar *,uchar)
0x180031d51  add     rsp, 48h
0x180031d55  retn
```
