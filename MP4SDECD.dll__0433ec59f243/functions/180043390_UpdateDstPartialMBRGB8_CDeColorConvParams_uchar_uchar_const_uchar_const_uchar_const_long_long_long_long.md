# UpdateDstPartialMBRGB8(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x180043390`
- end: `0x1800434b0`
- name: `?UpdateDstPartialMBRGB8@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `288`
- prototype: `void __usercall(struct CDeColorConvParams *@<rcx>, unsigned __int8 *@<rdx>, const unsigned __int8 *@<r8>, const unsigned __int8 *@<r9>, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x18002b32e`
- `0x18002b394`
- `0x1800415e0`
- `0x180043390`
- `0x180045805`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180043455`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180043463`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180043455`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180043463`

## pseudocode

```c
void __fastcall UpdateDstPartialMBRGB8(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        unsigned __int8 *a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  int v11; // r15d
  unsigned __int8 *v12; // rdi
  __int64 v13; // rcx
  unsigned __int64 v14; // rsi
  unsigned __int8 Src[256]; // [rsp+40h] [rbp-148h] BYREF

  UpdateDstMBRGB8(a1, Src, a3, a4, a5, a6, a7, 16);
  v11 = 0;
  v12 = Src;
  if ( a9 > 0 )
  {
    v13 = *((unsigned int *)a1 + 19);
    do
    {
      if ( a8 )
      {
        if ( !a2 )
          goto LABEL_11;
        v14 = (int)v13;
        if ( v12 && (int)v13 >= (unsigned __int64)a8 )
        {
          memcpy_0(a2, v12, a8);
        }
        else
        {
          memset_0(a2, 0, (int)v13);
          if ( !v12 )
          {
LABEL_11:
            *(_DWORD *)_o__errno(v13) = 22;
            goto LABEL_12;
          }
          if ( v14 < a8 )
          {
            *(_DWORD *)_o__errno(v13) = 34;
LABEL_12:
            invalid_parameter_noinfo();
          }
        }
      }
      v13 = *((int *)a1 + 19);
      v12 += 16;
      a2 += v13;
      ++v11;
    }
    while ( v11 < a9 );
  }
}

```

## disassembly

```asm
0x180043390  push    rbx
0x180043392  push    rbp
0x180043393  push    rsi
0x180043394  push    rdi
0x180043395  push    r13
0x180043397  push    r15
0x180043399  sub     rsp, 158h
0x1800433a0  mov     rax, cs:__security_cookie
0x1800433a7  xor     rax, rsp
0x1800433aa  mov     [rsp+188h+var_48], rax
0x1800433b2  mov     eax, [rsp+188h+arg_30]
0x1800433b9  mov     r13, rcx
0x1800433bc  mov     rcx, [rsp+188h+arg_20]
0x1800433c4  mov     rbx, rdx
0x1800433c7  mov     [rsp+188h+var_150], 10h; int
0x1800433cf  lea     rdx, [rsp+188h+Src]; unsigned __int8 *
0x1800433d4  mov     [rsp+188h+var_158], eax; int
0x1800433d8  mov     eax, [rsp+188h+arg_28]
0x1800433df  mov     [rsp+188h+var_160], eax; int
0x1800433e3  mov     [rsp+188h+var_168], rcx; unsigned __int8 *
0x1800433e8  mov     rcx, r13; struct CDeColorConvParams *
0x1800433eb  call    ?UpdateDstMBRGB8@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBRGB8(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x1800433f0  xor     r15d, r15d
0x1800433f3  lea     rdi, [rsp+188h+Src]
0x1800433f8  cmp     [rsp+188h+arg_40], r15d
0x180043400  jle     loc_180043490
0x180043406  mov     ecx, [r13+4Ch]
0x18004340a  cmp     [rsp+188h+arg_38], 0
0x180043412  jz      short loc_180043474
0x180043414  test    rbx, rbx
0x180043417  jz      short loc_180043463
0x180043419  movsxd  rbp, [rsp+188h+arg_38]
0x180043421  movsxd  rsi, ecx
0x180043424  test    rdi, rdi
0x180043427  jz      short loc_18004343E
0x180043429  cmp     rsi, rbp
0x18004342c  jb      short loc_18004343E
0x18004342e  mov     r8, rbp; Size
0x180043431  mov     rdx, rdi; Src
0x180043434  mov     rcx, rbx; void *
0x180043437  call    memcpy_0
0x18004343c  jmp     short loc_180043474
0x18004343e  mov     r8, rsi; Size
0x180043441  xor     edx, edx; Val
0x180043443  mov     rcx, rbx; void *
0x180043446  call    memset_0
0x18004344b  test    rdi, rdi
0x18004344e  jz      short loc_180043463
0x180043450  cmp     rsi, rbp
0x180043453  jnb     short loc_180043474
0x180043455  call    cs:__imp__o__errno
0x18004345b  mov     dword ptr [rax], 22h ; '"'
0x180043461  jmp     short loc_18004346F
0x180043463  call    cs:__imp__o__errno
0x180043469  mov     dword ptr [rax], 16h
0x18004346f  call    _invalid_parameter_noinfo
0x180043474  movsxd  rcx, dword ptr [r13+4Ch]
0x180043478  add     rdi, 10h
0x18004347c  add     rbx, rcx
0x18004347f  inc     r15d
0x180043482  cmp     r15d, [rsp+188h+arg_40]
0x18004348a  jl      loc_18004340A
0x180043490  mov     rcx, [rsp+188h+var_48]
0x180043498  xor     rcx, rsp; StackCookie
0x18004349b  call    __security_check_cookie
0x1800434a0  add     rsp, 158h
0x1800434a7  pop     r15
0x1800434a9  pop     r13
0x1800434ab  pop     rdi
0x1800434ac  pop     rsi
0x1800434ad  pop     rbp
0x1800434ae  pop     rbx
0x1800434af  retn
```
