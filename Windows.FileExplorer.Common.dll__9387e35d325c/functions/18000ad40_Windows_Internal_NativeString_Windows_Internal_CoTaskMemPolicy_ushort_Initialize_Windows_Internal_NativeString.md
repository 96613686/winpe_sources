# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)

- ea: `0x18000ad40`
- end: `0x18000af60`
- name: `?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z`
- size: `544`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000acc0`
- `0x18003dd40`

## callees

- `0x18000ad40`
- `0x18000b9b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ade5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ade5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000aecf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000aecf`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v2; // rax
  __int64 v3; // r9
  _WORD *v5; // rbx
  unsigned __int64 v6; // rbp
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  int v10; // r8d
  _WORD *v11; // rdx
  unsigned __int64 v12; // rcx
  _WORD *v13; // rax
  unsigned __int64 v15; // rsi
  LPVOID v16; // rax

  v2 = *(_QWORD *)(a2 + 8);
  v3 = -1;
  if ( v2 != -1 )
  {
    v5 = *(_WORD **)a2;
    if ( *(_QWORD *)a2 )
      goto LABEL_6;
LABEL_46:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
    return 0;
  }
  if ( !*(_QWORD *)a2 )
    goto LABEL_46;
  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v2) );
  v5 = *(_WORD **)a2;
LABEL_6:
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  if ( v2 == -1 )
  {
    v2 = v6;
  }
  else if ( v2 < v6 )
  {
    v6 = v2;
  }
  v7 = v2 + 1;
  if ( v2 + 1 < v2 )
    return 2147942934LL;
  v8 = *(_QWORD *)(a1 + 16);
  if ( v8 == -1 )
  {
    if ( *(_QWORD *)(a1 + 8) == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v3;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v3) );
      }
      else
      {
        v3 = 0;
      }
      *(_QWORD *)(a1 + 8) = v3;
    }
    else
    {
      v3 = *(_QWORD *)(a1 + 8);
    }
    v8 = v3 + 1;
    if ( !*(_QWORD *)a1 )
      v8 = 0;
    *(_QWORD *)(a1 + 16) = v8;
  }
  if ( v8 )
  {
    v10 = 0;
    if ( v7 <= v8 )
      goto LABEL_17;
    v15 = 2 * v8;
    if ( is_mul_ok(v8, 2u) )
    {
      if ( v8 > 0x800 )
        v15 = v8 + 2048;
      if ( v7 > v15 )
        v15 = v2 + 1;
      v16 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v15);
      if ( !v16 )
        return 2147942414LL;
      *(_QWORD *)(a1 + 16) = v15;
      v10 = 0;
      *(_QWORD *)a1 = v16;
      goto LABEL_18;
    }
    return 2147942934LL;
  }
  if ( !is_mul_ok(v7, 2u) )
    return 2147942934LL;
  v9 = CoTaskMemAlloc(2 * v7);
  if ( v9 )
  {
    *(_QWORD *)(a1 + 16) = v7;
    v10 = 0;
    *(_QWORD *)a1 = v9;
    *v9 = 0;
LABEL_18:
    if ( v7 )
    {
      v11 = *(_WORD **)a1;
      if ( v7 > 0x7FFFFFFF || v6 > 0x7FFFFFFE )
      {
        *v11 = 0;
      }
      else
      {
        v12 = v6;
        do
        {
          if ( !v12 )
            break;
          if ( !*v5 )
            break;
          *v11++ = *v5++;
          --v12;
          --v7;
        }
        while ( v7 );
        v13 = v11 - 1;
        if ( v7 )
          v13 = v11;
        *v13 = 0;
      }
    }
    *(_QWORD *)(a1 + 8) = v6;
    return (unsigned int)v10;
  }
  v10 = -2147024882;
LABEL_17:
  if ( v10 >= 0 )
    goto LABEL_18;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000ad40  push    rbx
0x18000ad42  push    r14
0x18000ad44  push    r15
0x18000ad46  sub     rsp, 20h
0x18000ad4a  mov     rax, [rdx+8]
0x18000ad4e  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18000ad55  mov     r14, rcx
0x18000ad58  cmp     rax, r9
0x18000ad5b  jnz     loc_18000AEF9
0x18000ad61  mov     r8, [rdx]
0x18000ad64  test    r8, r8
0x18000ad67  jz      loc_18000AF05
0x18000ad6d  mov     rax, r9
0x18000ad70  inc     rax
0x18000ad73  cmp     word ptr [r8+rax*2], 0
0x18000ad79  jnz     short loc_18000AD70
0x18000ad7b  mov     rbx, r8
0x18000ad7e  mov     [rsp+38h+arg_0], rbp
0x18000ad83  mov     rbp, r9
0x18000ad86  mov     [rsp+38h+arg_18], rdi
0x18000ad8b  nop     dword ptr [rax+rax+00h]
0x18000ad90  inc     rbp
0x18000ad93  cmp     word ptr [rbx+rbp*2], 0
0x18000ad98  jnz     short loc_18000AD90
0x18000ad9a  cmp     rax, r9
0x18000ad9d  jnz     loc_18000AE8E
0x18000ada3  mov     rax, rbp
0x18000ada6  lea     rdi, [rax+1]
0x18000adaa  cmp     rdi, rax
0x18000adad  jb      loc_18000AE80
0x18000adb3  mov     rcx, [rcx+10h]
0x18000adb7  xor     r15d, r15d
0x18000adba  cmp     rcx, r9
0x18000adbd  jz      loc_18000AF1A
0x18000adc3  mov     [rsp+38h+arg_10], rsi
0x18000adc8  test    rcx, rcx
0x18000adcb  jnz     loc_18000AE9A
0x18000add1  mov     eax, 2
0x18000add6  mul     rdi
0x18000add9  test    rdx, rdx
0x18000addc  jnz     loc_18000AE87
0x18000ade2  mov     rcx, rax; cb
0x18000ade5  call    cs:__imp_CoTaskMemAlloc
0x18000adeb  test    rax, rax
0x18000adee  jz      short loc_18000AE00
0x18000adf0  mov     [r14+10h], rdi
0x18000adf4  mov     r8d, r15d
0x18000adf7  mov     [r14], rax
0x18000adfa  mov     [rax], r15w
0x18000adfe  jmp     short loc_18000AE0B
0x18000ae00  mov     r8d, 8007000Eh
0x18000ae06  test    r8d, r8d
0x18000ae09  js      short loc_18000AE64
0x18000ae0b  test    rdi, rdi
0x18000ae0e  jz      short loc_18000AE60
0x18000ae10  mov     rdx, [r14]
0x18000ae13  cmp     rdi, 7FFFFFFFh
0x18000ae1a  ja      loc_18000AF57
0x18000ae20  cmp     rbp, 7FFFFFFEh
0x18000ae27  ja      loc_18000AF57
0x18000ae2d  mov     rcx, rbp
0x18000ae30  test    rcx, rcx
0x18000ae33  jz      short loc_18000AE51
0x18000ae35  movzx   eax, word ptr [rbx]
0x18000ae38  test    ax, ax
0x18000ae3b  jz      short loc_18000AE51
0x18000ae3d  mov     [rdx], ax
0x18000ae40  add     rbx, 2
0x18000ae44  add     rdx, 2
0x18000ae48  dec     rcx
0x18000ae4b  sub     rdi, 1
0x18000ae4f  jnz     short loc_18000AE30
0x18000ae51  test    rdi, rdi
0x18000ae54  lea     rax, [rdx-2]
0x18000ae58  cmovnz  rax, rdx
0x18000ae5c  mov     [rax], r15w
0x18000ae60  mov     [r14+8], rbp
0x18000ae64  mov     eax, r8d
0x18000ae67  mov     rsi, [rsp+38h+arg_10]
0x18000ae6c  mov     rbp, [rsp+38h+arg_0]
0x18000ae71  mov     rdi, [rsp+38h+arg_18]
0x18000ae76  add     rsp, 20h
0x18000ae7a  pop     r15
0x18000ae7c  pop     r14
0x18000ae7e  pop     rbx
0x18000ae7f  retn
0x18000ae80  mov     eax, 80070216h
0x18000ae85  jmp     short loc_18000AE6C
0x18000ae87  mov     eax, 80070216h
0x18000ae8c  jmp     short loc_18000AE67
0x18000ae8e  cmp     rax, rbp
0x18000ae91  cmovb   rbp, rax
0x18000ae95  jmp     loc_18000ADA6
0x18000ae9a  mov     r8d, r15d
0x18000ae9d  cmp     rdi, rcx
0x18000aea0  jbe     loc_18000AE06
0x18000aea6  mov     eax, 2
0x18000aeab  mul     rcx
0x18000aeae  mov     rsi, rax
0x18000aeb1  test    rdx, rdx
0x18000aeb4  jnz     short loc_18000AE87
0x18000aeb6  sub     rax, rcx
0x18000aeb9  cmp     rax, 800h
0x18000aebf  ja      short loc_18000AEE1
0x18000aec1  mov     rcx, [r14]; pv
0x18000aec4  cmp     rdi, rsi
0x18000aec7  cmova   rsi, rdi
0x18000aecb  lea     rdx, [rsi+rsi]; cb
0x18000aecf  call    cs:__imp_CoTaskMemRealloc
0x18000aed5  test    rax, rax
0x18000aed8  jnz     short loc_18000AEEA
0x18000aeda  mov     eax, 8007000Eh
0x18000aedf  jmp     short loc_18000AE67
0x18000aee1  lea     rsi, [rcx+800h]
0x18000aee8  jmp     short loc_18000AEC1
0x18000aeea  mov     [r14+10h], rsi
0x18000aeee  mov     r8d, r15d
0x18000aef1  mov     [r14], rax
0x18000aef4  jmp     loc_18000AE0B
0x18000aef9  mov     rbx, [rdx]
0x18000aefc  test    rbx, rbx
0x18000aeff  jnz     loc_18000AD7E
0x18000af05  xor     r15d, r15d
0x18000af08  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000af0d  mov     eax, r15d
0x18000af10  add     rsp, 20h
0x18000af14  pop     r15
0x18000af16  pop     r14
0x18000af18  pop     rbx
0x18000af19  retn
0x18000af1a  mov     rax, [r14+8]
0x18000af1e  cmp     rax, r9
0x18000af21  jnz     short loc_18000AF40
0x18000af23  mov     rax, [r14]
0x18000af26  test    rax, rax
0x18000af29  jnz     short loc_18000AF30
0x18000af2b  mov     r9, r15
0x18000af2e  jmp     short loc_18000AF3A
0x18000af30  inc     r9
0x18000af33  cmp     [rax+r9*2], r15w
0x18000af38  jnz     short loc_18000AF30
0x18000af3a  mov     [r14+8], r9
0x18000af3e  jmp     short loc_18000AF43
0x18000af40  mov     r9, rax
0x18000af43  cmp     [r14], r15
0x18000af46  lea     rcx, [r9+1]
0x18000af4a  cmovz   rcx, r15
0x18000af4e  mov     [r14+10h], rcx
0x18000af52  jmp     loc_18000ADC3
0x18000af57  mov     [rdx], r15w
0x18000af5b  jmp     loc_18000AE60
```
