# WriteFixed

- ea: `0x180052608`
- end: `0x180052751`
- name: `WriteFixed`
- size: `329`
- prototype: `__int64 __fastcall(_JBTYPE *, int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800548bc`

## callees

- `0x180001f20`
- `0x18004f8e4`
- `0x180050684`
- `0x1800509e8`
- `0x180052608`
- `0x180052fd8`

## pseudocode

```c
void __fastcall WriteFixed(_JBTYPE *a1, int a2, int a3)
{
  unsigned __int16 v6; // ax
  int v7; // edx
  __int16 v8; // ax
  unsigned int v9; // ecx
  unsigned int v10; // eax
  int v11; // r8d
  unsigned int v12; // ecx
  unsigned int v13; // eax
  int v14; // edi
  int v15; // r10d
  int v16; // r11d
  unsigned int v17; // ecx
  int v18; // edx
  int v19; // ecx
  int v20; // eax
  char v21[32]; // [rsp+20h] [rbp-48h] BYREF

  if ( (_WORD)a2 )
  {
    v7 = -a2;
    v8 = v7;
    if ( a2 >= 0 )
      v8 = a2;
    v9 = (unsigned __int16)(10 * v8);
    v10 = 0x10000 - v9;
    if ( v9 <= 0x8000 )
      v10 = v9;
    if ( v10 >= 0x40 )
    {
      if ( a2 >= 0 )
        LOWORD(v7) = a2;
      v12 = (unsigned __int16)(100 * v7);
      v13 = 0x10000 - v12;
      if ( v12 <= 0x8000 )
        v13 = (unsigned __int16)(100 * v7);
      if ( v13 >= 0x40 )
      {
        v14 = 1;
        v15 = -a2;
        v16 = 0xFFFF;
        if ( a2 >= 0 )
          LOWORD(v15) = a2;
        v11 = 2;
        while ( 1 )
        {
          v17 = (unsigned __int16)(v11 * v15);
          v18 = 0x10000 - v17;
          if ( v17 <= 0x8000 )
            v18 = (unsigned __int16)(v11 * v15);
          if ( v18 < 64 )
            break;
          v19 = v16;
          v20 = v11;
          if ( v18 < v16 )
            v16 = v18;
          if ( v18 >= v19 )
            v20 = v14;
          ++v11;
          v14 = v20;
          if ( v11 >= 200 )
          {
            v11 = v20;
            break;
          }
        }
      }
      else
      {
        v11 = 100;
      }
    }
    else
    {
      v11 = 10;
    }
    v6 = ConvertFixedDiv(a2, (__int64)v21, v11);
  }
  else
  {
    v6 = IntToCharstr(a2 >> 16, v21);
  }
  if ( !v6 )
    XCF_FatalErrorHandler(a1, 17);
  WriteT1Data((__int64)a1, v21, v6, a3);
}

```

## disassembly

```asm
0x180052608  mov     [rsp+arg_10], rbx
0x18005260d  push    rbp
0x18005260e  push    rsi
0x18005260f  push    rdi
0x180052610  sub     rsp, 50h
0x180052614  mov     rax, cs:__security_cookie
0x18005261b  xor     rax, rsp
0x18005261e  mov     [rsp+68h+var_28], rax
0x180052623  mov     esi, r8d
0x180052626  mov     r9d, edx
0x180052629  mov     rbx, rcx
0x18005262c  test    dx, dx
0x18005262f  jnz     short loc_180052647
0x180052631  sar     r9d, 10h
0x180052635  lea     rdx, [rsp+68h+var_48]
0x18005263a  mov     ecx, r9d
0x18005263d  call    IntToCharstr
0x180052642  jmp     loc_18005270F
0x180052647  neg     edx
0x180052649  test    r9d, r9d
0x18005264c  mov     eax, edx
0x18005264e  cmovns  eax, r9d
0x180052652  lea     eax, [rax+rax*4]
0x180052655  add     eax, eax
0x180052657  movzx   ecx, ax
0x18005265a  mov     eax, 10000h
0x18005265f  sub     eax, ecx
0x180052661  cmp     ecx, 8000h
0x180052667  cmovbe  eax, ecx
0x18005266a  cmp     eax, 40h ; '@'
0x18005266d  jnb     short loc_18005267A
0x18005266f  mov     r8d, 0Ah
0x180052675  jmp     loc_180052702
0x18005267a  test    r9d, r9d
0x18005267d  cmovns  edx, r9d
0x180052681  imul    eax, edx, 64h ; 'd'
0x180052684  movzx   ecx, ax
0x180052687  mov     eax, 10000h
0x18005268c  sub     eax, ecx
0x18005268e  cmp     ecx, 8000h
0x180052694  cmovbe  eax, ecx
0x180052697  cmp     eax, 40h ; '@'
0x18005269a  jnb     short loc_1800526A4
0x18005269c  mov     r8d, 64h ; 'd'
0x1800526a2  jmp     short loc_180052702
0x1800526a4  mov     r10d, r9d
0x1800526a7  mov     edi, 1
0x1800526ac  neg     r10d
0x1800526af  mov     r11d, 0FFFFh
0x1800526b5  test    r9d, r9d
0x1800526b8  cmovns  r10d, r9d
0x1800526bc  lea     r8d, [rdi+1]
0x1800526c0  mov     eax, r10d
0x1800526c3  mov     edx, 10000h
0x1800526c8  imul    eax, r8d
0x1800526cc  movzx   ecx, ax
0x1800526cf  sub     edx, ecx
0x1800526d1  cmp     ecx, 8000h
0x1800526d7  cmovbe  edx, ecx
0x1800526da  cmp     edx, 40h ; '@'
0x1800526dd  jl      short loc_180052702
0x1800526df  cmp     edx, r11d
0x1800526e2  mov     ecx, r11d
0x1800526e5  mov     eax, r8d
0x1800526e8  cmovl   r11d, edx
0x1800526ec  cmp     edx, ecx
0x1800526ee  cmovge  eax, edi
0x1800526f1  inc     r8d
0x1800526f4  mov     edi, eax
0x1800526f6  cmp     r8d, 0C8h
0x1800526fd  jl      short loc_1800526C0
0x1800526ff  mov     r8d, eax
0x180052702  lea     rdx, [rsp+68h+var_48]
0x180052707  mov     ecx, r9d
0x18005270a  call    ConvertFixedDiv
0x18005270f  mov     rcx, rbx
0x180052712  test    ax, ax
0x180052715  jz      short loc_180052746
0x180052717  movzx   r8d, ax
0x18005271b  lea     rdx, [rsp+68h+var_48]
0x180052720  mov     r9d, esi
0x180052723  call    WriteT1Data
0x180052728  mov     rcx, [rsp+68h+var_28]
0x18005272d  xor     rcx, rsp; StackCookie
0x180052730  call    __security_check_cookie
0x180052735  mov     rbx, [rsp+68h+arg_10]
0x18005273d  add     rsp, 50h
0x180052741  pop     rdi
0x180052742  pop     rsi
0x180052743  pop     rbp
0x180052744  retn
0x180052746  mov     edx, 11h
0x18005274b  call    XCF_FatalErrorHandler
```
