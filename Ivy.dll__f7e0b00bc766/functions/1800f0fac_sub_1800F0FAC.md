# sub_1800F0FAC

- ea: `0x1800f0fac`
- end: `0x1800f116b`
- name: `sub_1800F0FAC`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800ee7c0`

## callees

- `0x180008f04`
- `0x180015c38`
- `0x1800347d0`
- `0x180061900`
- `0x180061910`
- `0x18007c178`
- `0x1800aa894`
- `0x1800b9d84`
- `0x1800e8510`
- `0x1800ebc08`
- `0x1800f0fac`
- `0x18016c7b0`
- `0x18016eaf0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f10b4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800f10b4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f10aa`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800f10aa`

## string_xrefs

- `0x1800f1153`: `Property URI may not be null.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall sub_1800F0FAC(__int64 a1, unsigned int a2, __int64 a3, __int64 **a4, char a5)
{
  char v9; // al
  unsigned __int64 v10; // rdx
  _QWORD *v11; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rsi
  __int64 v14; // r8
  bool v15; // di
  void *v16; // rdx
  __int64 v18; // rcx
  int v19; // eax
  char v20[8]; // [rsp+30h] [rbp-58h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-50h] BYREF
  __int128 v22; // [rsp+48h] [rbp-40h]

  if ( !a3 )
  {
    sub_180015C38(508645698);
    sub_1800B9D84(508645698, 1, "Property URI may not be null.");
  }
  v9 = sub_1800EBC08(*(_QWORD *)(a1 + 16), a3);
  v10 = 0;
  if ( !v9 )
    v10 = a2;
  v11 = *(_QWORD **)(a1 + 72);
  if ( (__int64)(v11[1] - *v11) >> 3 <= v10 )
    sub_1800347D0();
  v12 = *(_QWORD **)(*v11 + 8 * v10);
  v20[0] = 0;
  v13 = sub_1800E8510(v12);
  *(_OWORD *)Block = 0;
  v22 = 0;
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(a3 + 2 * v14) );
  sub_180008F04(Block);
  v15 = sub_1800AA894(v13 + 32, Block, a4, v20);
  if ( *((_QWORD *)&v22 + 1) > 7u )
  {
    v16 = Block[0];
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v22 + 1) + 2) >= 0x1000 )
    {
      v16 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v16 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    free(v16);
  }
  if ( !v20[0] )
    return 1;
  if ( a5 )
  {
    v18 = v12[6];
    Block[0] = (void *)v18;
    v19 = *(_DWORD *)(v18 + 128);
    if ( !v19 )
      *(_BYTE *)(v18 + 170) &= ~0x40u;
    *(_DWORD *)(v18 + 128) = v19 + 1;
    Block[1] = (void *)v18;
    sub_18007C178(v18);
    (*(void (__fastcall **)(_QWORD *, __int64))(*v12 + 248LL))(v12, 8);
    sub_180061900(&Block[1]);
    sub_180061910(Block);
  }
  return v15;
}

```

## disassembly

```asm
0x1800f0fac  push    rbx
0x1800f0fae  push    rsi
0x1800f0faf  push    rdi
0x1800f0fb0  push    r14
0x1800f0fb2  push    r15
0x1800f0fb4  sub     rsp, 60h
0x1800f0fb8  mov     rax, cs:__security_cookie
0x1800f0fbf  xor     rax, rsp
0x1800f0fc2  mov     [rsp+88h+var_30], rax
0x1800f0fc7  mov     r14, r9
0x1800f0fca  mov     rdi, r8
0x1800f0fcd  mov     esi, edx
0x1800f0fcf  mov     rbx, rcx
0x1800f0fd2  xor     r15d, r15d
0x1800f0fd5  test    r8, r8
0x1800f0fd8  jz      loc_1800F1147
0x1800f0fde  mov     rdx, rdi
0x1800f0fe1  mov     rcx, [rcx+10h]
0x1800f0fe5  call    sub_1800EBC08
0x1800f0fea  mov     edx, r15d
0x1800f0fed  test    al, al
0x1800f0fef  cmovz   edx, esi
0x1800f0ff2  mov     rax, [rbx+48h]
0x1800f0ff6  mov     rbx, [rax]
0x1800f0ff9  mov     rcx, [rax+8]
0x1800f0ffd  sub     rcx, rbx
0x1800f1000  sar     rcx, 3
0x1800f1004  cmp     rcx, rdx
0x1800f1007  jbe     loc_1800F1164
0x1800f100d  mov     rbx, [rbx+rdx*8]
0x1800f1011  mov     [rsp+88h+var_58], r15b
0x1800f1016  mov     rcx, rbx
0x1800f1019  call    sub_1800E8510
0x1800f101e  mov     rsi, rax
0x1800f1021  xorps   xmm0, xmm0
0x1800f1024  movups  xmmword ptr [rsp+88h+Block], xmm0
0x1800f1029  xorps   xmm1, xmm1
0x1800f102c  movdqu  [rsp+88h+var_40], xmm1
0x1800f1032  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f1036  inc     r8
0x1800f1039  cmp     [rdi+r8*2], r15w
0x1800f103e  jnz     short loc_1800F1036
0x1800f1040  mov     rdx, rdi
0x1800f1043  lea     rcx, [rsp+88h+Block]
0x1800f1048  call    sub_180008F04
0x1800f104d  lea     rcx, [rsi+20h]
0x1800f1051  lea     r9, [rsp+88h+var_58]
0x1800f1056  mov     r8, r14
0x1800f1059  lea     rdx, [rsp+88h+Block]
0x1800f105e  call    sub_1800AA894
0x1800f1063  mov     dil, al
0x1800f1066  mov     rcx, qword ptr [rsp+88h+var_40+8]
0x1800f106b  cmp     rcx, 7
0x1800f106f  jbe     short loc_1800F10BA
0x1800f1071  mov     rdx, [rsp+88h+Block]
0x1800f1076  mov     rax, rdx
0x1800f1079  lea     rcx, ds:2[rcx*2]
0x1800f1081  cmp     rcx, 1000h
0x1800f1088  jb      short loc_1800F10B1
0x1800f108a  mov     rdx, [rdx-8]
0x1800f108e  sub     rax, rdx
0x1800f1091  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800f1095  cmp     rax, 1Fh
0x1800f1099  jbe     short loc_1800F10B1
0x1800f109b  mov     [rsp+88h+Reserved], r15; Reserved
0x1800f10a0  xor     r9d, r9d; LineNo
0x1800f10a3  xor     r8d, r8d; FileName
0x1800f10a6  xor     edx, edx; FunctionName
0x1800f10a8  xor     ecx, ecx; Expression
0x1800f10aa  call    cs:_invoke_watson
0x1800f10b1  mov     rcx, rdx; Block
0x1800f10b4  call    cs:free
0x1800f10ba  cmp     [rsp+88h+var_58], r15b
0x1800f10bf  jnz     short loc_1800F10C5
0x1800f10c1  mov     al, 1
0x1800f10c3  jmp     short loc_1800F112E
0x1800f10c5  cmp     [rsp+88h+arg_20], r15b
0x1800f10cd  jz      short loc_1800F1127
0x1800f10cf  mov     rcx, [rbx+30h]
0x1800f10d3  mov     [rsp+88h+Block], rcx
0x1800f10d8  mov     eax, [rcx+80h]
0x1800f10de  test    eax, eax
0x1800f10e0  jnz     short loc_1800F10E9
0x1800f10e2  and     byte ptr [rcx+0AAh], 0BFh
0x1800f10e9  inc     eax
0x1800f10eb  mov     [rcx+80h], eax
0x1800f10f1  mov     [rsp+88h+Block+8], rcx
0x1800f10f6  call    sub_18007C178
0x1800f10fb  mov     rax, [rbx]
0x1800f10fe  mov     edx, 8
0x1800f1103  mov     rcx, rbx
0x1800f1106  mov     rax, [rax+0F8h]
0x1800f110d  call    cs:__guard_dispatch_icall_fptr
0x1800f1113  lea     rcx, [rsp+88h+Block+8]
0x1800f1118  call    sub_180061900
0x1800f111d  lea     rcx, [rsp+88h+Block]
0x1800f1122  call    sub_180061910
0x1800f1127  mov     al, dil
0x1800f112a  jmp     short loc_1800F112E
0x1800f112c  xor     al, al
0x1800f112e  mov     rcx, [rsp+88h+var_30]
0x1800f1133  xor     rcx, rsp; StackCookie
0x1800f1136  call    __security_check_cookie
0x1800f113b  add     rsp, 60h
0x1800f113f  pop     r15
0x1800f1141  pop     r14
0x1800f1143  pop     rdi
0x1800f1144  pop     rsi
0x1800f1145  pop     rbx
0x1800f1146  retn
0x1800f1147  mov     ebx, 1E515142h
0x1800f114c  mov     ecx, ebx
0x1800f114e  call    sub_180015C38
0x1800f1153  lea     r8, aPropertyUriMay; "Property URI may not be null."
0x1800f115a  lea     edx, [rdi+1]
0x1800f115d  mov     ecx, ebx
0x1800f115f  call    sub_1800B9D84
0x1800f1164  call    sub_1800347D0
```
