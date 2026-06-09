# __acrt_fp_strflt_to_string

- ea: `0x1400165a0`
- end: `0x1400166b0`
- name: `__acrt_fp_strflt_to_string`
- size: `272`
- prototype: `__int64 __fastcall(char *Dst, unsigned __int64, int, unsigned int *, unsigned int, int, __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140012438`
- `0x140012720`
- `0x140012950`

## callees

- `0x140004614`
- `0x1400164d0`
- `0x1400165a0`
- `0x14001db10`

## pseudocode

```c
__int64 __fastcall _acrt_fp_strflt_to_string(
        char *Dst,
        unsigned __int64 a2,
        int a3,
        unsigned int *a4,
        unsigned int a5,
        int a6,
        __crt_cached_ptd_host *a7)
{
  unsigned int v9; // ebx
  int v11; // eax
  char *v12; // rcx
  char *v13; // rbx
  char *v14; // rdx
  char v15; // al
  __int64 v16; // r8

  if ( !Dst || !a2 )
    goto LABEL_2;
  v11 = 0;
  *Dst = 0;
  if ( a3 > 0 )
    v11 = a3;
  if ( a2 <= v11 + 1 )
  {
    v9 = 34;
    goto LABEL_3;
  }
  if ( !a4 )
  {
LABEL_2:
    v9 = 22;
LABEL_3:
    *((_DWORD *)a7 + 11) = v9;
    *((_BYTE *)a7 + 48) = 1;
    sub_140004614(0, 0, 0, 0, 0, a7);
    return v9;
  }
  v12 = (char *)*((_QWORD *)a4 + 1);
  v13 = Dst + 1;
  v14 = v12;
  *Dst = 48;
  while ( a3 > 0 )
  {
    v15 = *v14;
    if ( *v14 )
      ++v14;
    else
      v15 = 48;
    *v13++ = v15;
    --a3;
  }
  *v13 = 0;
  if ( a3 >= 0 && (unsigned __int8)should_round_up(v12, v14, *a4, a5, a6) )
  {
    while ( *--v13 == 57 )
      *v13 = 48;
    ++*v13;
  }
  if ( *Dst == 49 )
  {
    ++a4[1];
  }
  else
  {
    v16 = -1;
    do
      ++v16;
    while ( Dst[v16 + 1] );
    memmove(Dst, Dst + 1, v16 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x1400165a0  mov     [rsp+arg_0], rbx
0x1400165a5  mov     [rsp+arg_8], rbp
0x1400165aa  mov     [rsp+arg_10], rsi
0x1400165af  push    rdi
0x1400165b0  sub     rsp, 30h
0x1400165b4  mov     rdi, r9
0x1400165b7  mov     rsi, rcx
0x1400165ba  test    rcx, rcx
0x1400165bd  jnz     short loc_1400165F1
0x1400165bf  mov     ebx, 16h
0x1400165c4  mov     rax, [rsp+38h+arg_30]
0x1400165c9  xor     r9d, r9d; LineNo
0x1400165cc  mov     [rsp+38h+var_10], rax; __crt_cached_ptd_host *
0x1400165d1  xor     r8d, r8d; FileName
0x1400165d4  and     [rsp+38h+var_18], 0
0x1400165da  xor     edx, edx; FunctionName
0x1400165dc  xor     ecx, ecx; Expression
0x1400165de  mov     [rax+2Ch], ebx
0x1400165e1  mov     byte ptr [rax+30h], 1
0x1400165e5  call    sub_140004614
0x1400165ea  mov     eax, ebx
0x1400165ec  jmp     loc_14001669B
0x1400165f1  test    rdx, rdx
0x1400165f4  jz      short loc_1400165BF
0x1400165f6  xor     eax, eax
0x1400165f8  mov     byte ptr [rcx], 0
0x1400165fb  test    r8d, r8d
0x1400165fe  cmovg   eax, r8d
0x140016602  inc     eax
0x140016604  cdqe
0x140016606  cmp     rdx, rax
0x140016609  ja      short loc_140016612
0x14001660b  mov     ebx, 22h ; '"'
0x140016610  jmp     short loc_1400165C4
0x140016612  test    rdi, rdi
0x140016615  jz      short loc_1400165BF
0x140016617  mov     rcx, [r9+8]
0x14001661b  lea     rbx, [rsi+1]
0x14001661f  mov     rdx, rcx
0x140016622  mov     byte ptr [rsi], 30h ; '0'
0x140016625  jmp     short loc_14001663C
0x140016627  mov     al, [rdx]
0x140016629  test    al, al
0x14001662b  jz      short loc_140016632
0x14001662d  inc     rdx
0x140016630  jmp     short loc_140016634
0x140016632  mov     al, 30h ; '0'
0x140016634  mov     [rbx], al
0x140016636  inc     rbx
0x140016639  dec     r8d
0x14001663c  test    r8d, r8d
0x14001663f  jg      short loc_140016627
0x140016641  mov     byte ptr [rbx], 0
0x140016644  js      short loc_140016671
0x140016646  mov     eax, [rsp+38h+arg_28]
0x14001664a  mov     r9d, [rsp+38h+arg_20]
0x14001664f  mov     r8d, [rdi]
0x140016652  mov     dword ptr [rsp+38h+var_18], eax
0x140016656  call    ?should_round_up@@YA_NQEBD0HW4__acrt_has_trailing_digits@@W4__acrt_rounding_mode@@@Z
0x14001665b  test    al, al
0x14001665d  jz      short loc_140016671
0x14001665f  jmp     short loc_140016664
0x140016661  mov     byte ptr [rbx], 30h ; '0'
0x140016664  dec     rbx
0x140016667  mov     al, [rbx]
0x140016669  cmp     al, 39h ; '9'
0x14001666b  jz      short loc_140016661
0x14001666d  inc     al
0x14001666f  mov     [rbx], al
0x140016671  cmp     byte ptr [rsi], 31h ; '1'
0x140016674  jnz     short loc_14001667B
0x140016676  inc     dword ptr [rdi+4]
0x140016679  jmp     short loc_140016699
0x14001667b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001667f  inc     r8
0x140016682  cmp     byte ptr [r8+rsi+1], 0
0x140016688  jnz     short loc_14001667F
0x14001668a  inc     r8; MaxCount
0x14001668d  lea     rdx, [rsi+1]; Src
0x140016691  mov     rcx, rsi; Dst
0x140016694  call    memmove
0x140016699  xor     eax, eax
0x14001669b  mov     rbx, [rsp+38h+arg_0]
0x1400166a0  mov     rbp, [rsp+38h+arg_8]
0x1400166a5  mov     rsi, [rsp+38h+arg_10]
0x1400166aa  add     rsp, 30h
0x1400166ae  pop     rdi
0x1400166af  retn
```
