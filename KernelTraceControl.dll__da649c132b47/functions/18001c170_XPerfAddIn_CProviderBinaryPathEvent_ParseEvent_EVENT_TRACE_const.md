# XPerfAddIn::CProviderBinaryPathEvent::ParseEvent(_EVENT_TRACE const *)

- ea: `0x18001c170`
- end: `0x18001c2cf`
- name: `?ParseEvent@CProviderBinaryPathEvent@XPerfAddIn@@QEAAJPEBU_EVENT_TRACE@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(XPerfAddIn::CProviderBinaryPathEvent *__hidden this, const struct _EVENT_TRACE *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017b30`

## callees

- `0x1800130a8`
- `0x18001beec`
- `0x18001c170`

## pseudocode

```c
__int64 __fastcall XPerfAddIn::CProviderBinaryPathEvent::ParseEvent(
        XPerfAddIn::CProviderBinaryPathEvent *this,
        const struct _EVENT_TRACE *a2)
{
  __int64 v3; // rbx
  unsigned int *MofData; // r14
  unsigned __int64 MofLength; // rdi
  unsigned __int64 v7; // r12
  unsigned int *v8; // r14
  unsigned __int64 v9; // rdi
  __int64 v10; // r15
  unsigned __int64 v11; // rax
  unsigned int *v12; // r13
  unsigned int *v13; // r14
  unsigned __int64 v14; // rdi
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int128 v19; // [rsp+30h] [rbp-38h] BYREF

  v3 = 0;
  if ( !a2->MofData )
    return 1;
  MofData = (unsigned int *)a2->MofData;
  MofLength = a2->MofLength;
  if ( MofLength < 4 )
    return 1;
  v7 = *MofData;
  v8 = MofData + 1;
  v9 = MofLength - 4;
  v10 = (unsigned int)v7;
  v11 = 16LL * (unsigned int)v7;
  if ( v9 < v11 )
    return 1;
  v12 = v8;
  v13 = &v8[v11 / 4];
  v14 = v9 - v11;
  v19 = 0u;
  v15 = *((_QWORD *)this + 1);
  if ( v15 )
    v16 = (*((_QWORD *)this + 2) - v15) >> 4;
  else
    v16 = 0;
  if ( v16 >= v7 )
  {
    if ( v15 )
    {
      if ( v7 < (*((_QWORD *)this + 2) - v15) >> 4 )
      {
        v18 = v15 + 16 * v7;
        if ( v18 != *((_QWORD *)this + 2) )
          *((_QWORD *)this + 2) = v18;
      }
    }
  }
  else
  {
    if ( v15 )
      v17 = (*((_QWORD *)this + 2) - v15) >> 4;
    else
      v17 = 0;
    std::vector<_GUID>::_Insert_n(this, *((_QWORD *)this + 2), v7 - v17, &v19, -2);
  }
  if ( (_DWORD)v7 )
  {
    do
    {
      *(_OWORD *)(v3 * 4 + *((_QWORD *)this + 1)) = *(_OWORD *)&v12[v3];
      v3 += 4;
      --v10;
    }
    while ( v10 );
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 32, v13, (unsigned int)(v14 >> 1));
  return 0;
}

```

## disassembly

```asm
0x18001c170  mov     rax, rsp
0x18001c173  push    rdi
0x18001c174  push    r12
0x18001c176  push    r13
0x18001c178  push    r14
0x18001c17a  push    r15
0x18001c17c  sub     rsp, 40h
0x18001c180  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18001c188  mov     [rax+8], rbx
0x18001c18c  mov     [rax+18h], rsi
0x18001c190  mov     rsi, rcx
0x18001c193  xor     ebx, ebx
0x18001c195  cmp     [rdx+48h], rbx
0x18001c199  jnz     short loc_18001C1A3
0x18001c19b  lea     eax, [rbx+1]
0x18001c19e  jmp     loc_18001C2B4
0x18001c1a3  mov     r14, [rdx+48h]
0x18001c1a7  mov     edi, [rdx+50h]
0x18001c1aa  cmp     rdi, 4
0x18001c1ae  jnb     short loc_18001C1BA
0x18001c1b0  mov     eax, 1
0x18001c1b5  jmp     loc_18001C2B4
0x18001c1ba  mov     r12d, [r14]
0x18001c1bd  add     r14, 4
0x18001c1c1  sub     rdi, 4
0x18001c1c5  mov     r15d, r12d
0x18001c1c8  mov     eax, r12d
0x18001c1cb  shl     rax, 4
0x18001c1cf  cmp     rdi, rax
0x18001c1d2  jnb     short loc_18001C1DE
0x18001c1d4  mov     eax, 1
0x18001c1d9  jmp     loc_18001C2B4
0x18001c1de  mov     r13, r14
0x18001c1e1  add     r14, rax
0x18001c1e4  sub     rdi, rax
0x18001c1e7  xor     eax, eax
0x18001c1e9  mov     qword ptr [rsp+68h+var_38], rax
0x18001c1ee  mov     qword ptr [rsp+68h+var_38+8], rax
0x18001c1f3  movaps  xmm0, [rsp+68h+var_38]
0x18001c1f8  movdqa  [rsp+68h+var_38], xmm0
0x18001c1fe  mov     rax, [rcx+8]
0x18001c202  test    rax, rax
0x18001c205  jnz     short loc_18001C20C
0x18001c207  mov     rcx, rbx
0x18001c20a  jmp     short loc_18001C217
0x18001c20c  mov     rcx, [rcx+10h]
0x18001c210  sub     rcx, rax
0x18001c213  sar     rcx, 4
0x18001c217  cmp     rcx, r12
0x18001c21a  jnb     short loc_18001C24A
0x18001c21c  test    rax, rax
0x18001c21f  jnz     short loc_18001C226
0x18001c221  mov     rcx, rbx
0x18001c224  jmp     short loc_18001C231
0x18001c226  mov     rcx, [rsi+10h]
0x18001c22a  sub     rcx, rax
0x18001c22d  sar     rcx, 4
0x18001c231  mov     r8, r12
0x18001c234  sub     r8, rcx
0x18001c237  lea     r9, [rsp+68h+var_38]
0x18001c23c  mov     rdx, [rsi+10h]
0x18001c240  mov     rcx, rsi
0x18001c243  call    ?_Insert_n@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@IEAAXV?$_Vector_iterator@U_GUID@@V?$allocator@U_GUID@@@std@@@2@_KAEBU_GUID@@@Z; std::vector<_GUID>::_Insert_n(std::_Vector_iterator<_GUID>,unsigned __int64,_GUID const &)
0x18001c248  jmp     short loc_18001C275
0x18001c24a  test    rax, rax
0x18001c24d  jz      short loc_18001C275
0x18001c24f  mov     rdx, [rsi+10h]
0x18001c253  mov     rcx, rdx
0x18001c256  sub     rcx, rax
0x18001c259  sar     rcx, 4
0x18001c25d  cmp     r12, rcx
0x18001c260  jnb     short loc_18001C275
0x18001c262  mov     rcx, r12
0x18001c265  shl     rcx, 4
0x18001c269  add     rcx, rax
0x18001c26c  cmp     rcx, rdx
0x18001c26f  jz      short loc_18001C275
0x18001c271  mov     [rsi+10h], rcx
0x18001c275  test    r12d, r12d
0x18001c278  jz      short loc_18001C292
0x18001c27a  mov     rax, [rsi+8]
0x18001c27e  movups  xmm0, xmmword ptr [rbx+r13]
0x18001c283  movdqu  xmmword ptr [rbx+rax], xmm0
0x18001c288  lea     rbx, [rbx+10h]
0x18001c28c  sub     r15, 1
0x18001c290  jnz     short loc_18001C27A
0x18001c292  shr     rdi, 1
0x18001c295  lea     rcx, [rsi+20h]
0x18001c299  mov     r8d, edi
0x18001c29c  mov     rdx, r14
0x18001c29f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001c2a4  nop
0x18001c2a5  xor     eax, eax
0x18001c2a7  jmp     short loc_18001C2B4
0x18001c2a9  mov     eax, 8007000Eh
0x18001c2ae  jmp     short loc_18001C2B4
0x18001c2b0  mov     eax, [rsp+68h+arg_8]
0x18001c2b4  lea     r11, [rsp+68h+var_28]
0x18001c2b9  mov     rbx, [r11+30h]
0x18001c2bd  mov     rsi, [r11+40h]
0x18001c2c1  mov     rsp, r11
0x18001c2c4  pop     r15
0x18001c2c6  pop     r14
0x18001c2c8  pop     r13
0x18001c2ca  pop     r12
0x18001c2cc  pop     rdi
0x18001c2cd  retn
```
