# UpdateDstPartialMBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001db30`
- end: `0x18001dc06`
- name: `?UpdateDstPartialMBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `214`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800018b0`
- `0x18001d140`
- `0x18001db30`
- `0x180021005`

## pseudocode

```c
void __fastcall UpdateDstPartialMBYUY2(
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
  int v11; // esi
  unsigned __int8 *i; // rdi
  unsigned __int8 Src[512]; // [rsp+40h] [rbp-238h] BYREF

  UpdateDstMBYUY2(Src, a3, a4, a5, a6, a7, 32);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, (int)(2 * (a8 & 0xFFFFFFFE)));
    i += 32;
    a2 += *((int *)a1 + 16);
  }
}

```

## disassembly

```asm
0x18001db30  mov     [rsp+arg_0], rbx
0x18001db35  push    rbp
0x18001db36  push    rsi
0x18001db37  push    rdi
0x18001db38  push    r12
0x18001db3a  push    r14
0x18001db3c  sub     rsp, 250h
0x18001db43  mov     rax, cs:__security_cookie
0x18001db4a  xor     rax, rsp
0x18001db4d  mov     [rsp+278h+var_38], rax
0x18001db55  mov     eax, [rsp+278h+arg_30]
0x18001db5c  mov     r11, r9
0x18001db5f  mov     r14d, [rsp+278h+arg_38]
0x18001db67  mov     r10, r8
0x18001db6a  mov     r9, [rsp+278h+arg_20]; unsigned __int8 *
0x18001db72  mov     rbx, rdx
0x18001db75  mov     [rsp+278h+var_248], 20h ; ' '; int
0x18001db7d  mov     r12, rcx
0x18001db80  mov     [rsp+278h+var_250], eax; int
0x18001db84  lea     rcx, [rsp+278h+Src]; unsigned __int8 *
0x18001db89  mov     eax, [rsp+278h+arg_28]
0x18001db90  mov     r8, r11; unsigned __int8 *
0x18001db93  mov     rdx, r10; unsigned __int8 *
0x18001db96  mov     [rsp+278h+var_258], eax; int
0x18001db9a  and     r14d, 0FFFFFFFEh
0x18001db9e  call    ?UpdateDstMBYUY2@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBYUY2(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001dba3  xor     esi, esi
0x18001dba5  lea     rdi, [rsp+278h+Src]
0x18001dbaa  cmp     [rsp+278h+arg_40], esi
0x18001dbb1  jle     short loc_18001DBDF
0x18001dbb3  lea     eax, [r14+r14]
0x18001dbb7  movsxd  rbp, eax
0x18001dbba  mov     r8, rbp; Size
0x18001dbbd  mov     rdx, rdi; Src
0x18001dbc0  mov     rcx, rbx; void *
0x18001dbc3  call    memcpy_0
0x18001dbc8  movsxd  rax, dword ptr [r12+40h]
0x18001dbcd  add     rdi, 20h ; ' '
0x18001dbd1  add     rbx, rax
0x18001dbd4  inc     esi
0x18001dbd6  cmp     esi, [rsp+278h+arg_40]
0x18001dbdd  jl      short loc_18001DBBA
0x18001dbdf  mov     rcx, [rsp+278h+var_38]
0x18001dbe7  xor     rcx, rsp; StackCookie
0x18001dbea  call    __security_check_cookie
0x18001dbef  mov     rbx, [rsp+278h+arg_0]
0x18001dbf7  add     rsp, 250h
0x18001dbfe  pop     r14
0x18001dc00  pop     r12
0x18001dc02  pop     rdi
0x18001dc03  pop     rsi
0x18001dc04  pop     rbp
0x18001dc05  retn
```
