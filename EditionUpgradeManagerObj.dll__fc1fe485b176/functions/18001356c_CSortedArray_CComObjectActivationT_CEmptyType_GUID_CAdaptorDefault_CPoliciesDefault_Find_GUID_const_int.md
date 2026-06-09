# CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(_GUID const &,int *)

- ea: `0x18001356c`
- end: `0x18001366d`
- name: `?Find@?$CSortedArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NAEBU_GUID@@PEAH@Z`
- size: `257`
- prototype: `char __fastcall(__int64, const void *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014800`
- `0x180017bc0`

## callees

- `0x18001356c`
- `0x180022950`

## pseudocode

```c
char __fastcall CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(
        __int64 a1,
        const void *a2,
        int *a3)
{
  int v3; // r14d
  int *v5; // rdi
  int v6; // ebp
  unsigned int v7; // esi
  char v8; // bl
  __int64 v9; // rdi
  signed int v10; // r13d
  __int64 v12; // [rsp+60h] [rbp+8h]

  v3 = *(_DWORD *)(a1 + 4);
  v5 = a3;
  v12 = *(_QWORD *)(a1 + 8);
  if ( v3 )
  {
    v6 = 0;
    v7 = *(_DWORD *)(a1 + 4);
    if ( v3 <= 0 )
      goto LABEL_10;
    v8 = 1;
    v9 = *(_QWORD *)(a1 + 8);
    do
    {
      v10 = (v7 >> 1) + v6;
      if ( memcmp_0((const void *)(*(_QWORD *)(v9 + 8LL * v10) + 4LL), a2, 0x10u) < 0 )
      {
        v6 = v10 + 1;
        v7 += -1 - (v7 >> 1);
      }
      else
      {
        v7 >>= 1;
      }
    }
    while ( (int)v7 > 0 );
    v5 = a3;
    if ( v6 >= v3 || memcmp_0(a2, (const void *)(*(_QWORD *)(v12 + 8LL * v6) + 4LL), 0x10u) < 0 )
LABEL_10:
      v8 = 0;
    if ( v5 )
      *v5 = v6;
  }
  else
  {
    v8 = 0;
    if ( a3 )
      *a3 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18001356c  mov     [rsp+arg_8], rbx
0x180013571  mov     [rsp+arg_10], r8
0x180013576  push    rbp
0x180013577  push    rsi
0x180013578  push    rdi
0x180013579  push    r12
0x18001357b  push    r13
0x18001357d  push    r14
0x18001357f  push    r15
0x180013581  sub     rsp, 20h
0x180013585  mov     r14d, [rcx+4]
0x180013589  mov     r12, rdx
0x18001358c  mov     rdx, [rcx+8]
0x180013590  mov     rdi, r8
0x180013593  mov     [rsp+58h+arg_0], rdx
0x180013598  test    r14d, r14d
0x18001359b  jz      loc_180013648
0x1800135a1  xor     ebp, ebp
0x1800135a3  mov     esi, r14d
0x1800135a6  test    r14d, r14d
0x1800135a9  jle     loc_18001363D
0x1800135af  lea     ebx, [rbp+1]
0x1800135b2  mov     rdi, rdx
0x1800135b5  mov     r15d, esi
0x1800135b8  mov     r8d, 10h; Size
0x1800135be  shr     r15d, 1
0x1800135c1  mov     rdx, r12; Buf2
0x1800135c4  lea     r13d, [r15+rbp]
0x1800135c8  movsxd  rax, r13d
0x1800135cb  mov     rcx, [rdi+rax*8]
0x1800135cf  add     rcx, 4; Buf1
0x1800135d3  call    memcmp_0
0x1800135d8  mov     ecx, eax
0x1800135da  test    eax, eax
0x1800135dc  jle     short loc_1800135E2
0x1800135de  mov     eax, ebx
0x1800135e0  jmp     short loc_1800135E8
0x1800135e2  xor     eax, eax
0x1800135e4  test    ecx, ecx
0x1800135e6  js      short loc_1800135F1
0x1800135e8  test    eax, eax
0x1800135ea  js      short loc_1800135F1
0x1800135ec  mov     esi, r15d
0x1800135ef  jmp     short loc_1800135FD
0x1800135f1  or      eax, 0FFFFFFFFh
0x1800135f4  lea     ebp, [r13+1]
0x1800135f8  sub     eax, r15d
0x1800135fb  add     esi, eax
0x1800135fd  test    esi, esi
0x1800135ff  jg      short loc_1800135B5
0x180013601  mov     rdi, [rsp+58h+arg_10]
0x180013606  cmp     ebp, r14d
0x180013609  jge     short loc_18001363D
0x18001360b  mov     rdx, [rsp+58h+arg_0]
0x180013610  mov     r8d, 10h; Size
0x180013616  movsxd  rax, ebp
0x180013619  mov     rcx, r12; Buf1
0x18001361c  mov     rdx, [rdx+rax*8]
0x180013620  add     rdx, 4; Buf2
0x180013624  call    memcmp_0
0x180013629  mov     ecx, eax
0x18001362b  test    eax, eax
0x18001362d  jle     short loc_180013633
0x18001362f  mov     eax, ebx
0x180013631  jmp     short loc_180013639
0x180013633  xor     eax, eax
0x180013635  test    ecx, ecx
0x180013637  js      short loc_18001363D
0x180013639  test    eax, eax
0x18001363b  jns     short loc_18001363F
0x18001363d  xor     bl, bl
0x18001363f  test    rdi, rdi
0x180013642  jz      short loc_180013656
0x180013644  mov     [rdi], ebp
0x180013646  jmp     short loc_180013656
0x180013648  xor     bl, bl
0x18001364a  test    r8, r8
0x18001364d  jz      short loc_180013656
0x18001364f  mov     dword ptr [r8], 0
0x180013656  mov     al, bl
0x180013658  mov     rbx, [rsp+58h+arg_8]
0x18001365d  add     rsp, 20h
0x180013661  pop     r15
0x180013663  pop     r14
0x180013665  pop     r13
0x180013667  pop     r12
0x180013669  pop     rdi
0x18001366a  pop     rsi
0x18001366b  pop     rbp
0x18001366c  retn
```
