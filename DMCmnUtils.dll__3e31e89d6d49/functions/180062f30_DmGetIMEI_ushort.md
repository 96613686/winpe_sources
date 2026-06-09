# DmGetIMEI(ushort * *)

- ea: `0x180062f30`
- end: `0x1800631d3`
- name: `?DmGetIMEI@@YAJPEAPEAG@Z`
- size: `675`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180007270`
- `0x180007bfe`
- `0x1800583e8`
- `0x180062f30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180063145`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180063145`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006310e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006310e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180063042`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180063042`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800631a0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x1800631a0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180062fa6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180062fa6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800630f2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180063172`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180063188`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800630f2`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180063172`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180063188`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180062fe9`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180062fe9`

## pseudocode

```c
__int64 __fastcall DmGetIMEI(unsigned __int16 **a1)
{
  signed int v2; // ebx
  signed int v3; // eax
  bool v4; // cc
  _OWORD *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // rdx
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int64 v20; // rax
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // r11
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh] BYREF
  _DWORD *v28; // [rsp+58h] [rbp-A8h] BYREF
  char v29; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v30[126]; // [rsp+C4h] [rbp-3Ch] BYREF

  v26 = 0;
  v25 = 0;
  v28 = 0;
  v24 = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  *a1 = 0;
  v3 = WwanOpenHandle(1, 0, &v26, &v25);
  v2 = v3;
  if ( v3 != 1062 )
  {
    v4 = v3 <= 0;
    if ( !v3 )
    {
      v3 = WwanEnumerateInterfaces(v25, 0, &v28);
      v2 = v3;
      v4 = v3 <= 0;
      if ( !v3 )
      {
        if ( !*v28 )
        {
          v2 = -2147024894;
          goto LABEL_20;
        }
        v27 = 0;
        v3 = WwanQueryInterface(v25, v28 + 1, 7, 0, &v27, &v24, 0, 0);
        v2 = v3;
        v4 = v3 <= 0;
        if ( !v3 )
        {
          v5 = (_OWORD *)(v24 + 552);
          if ( v24 == -552 )
          {
            *(_DWORD *)_o__errno() = 22;
            invalid_parameter_noinfo();
            v2 = -2147024774;
          }
          else
          {
            v6 = (unsigned int)(v2 + 2);
            v7 = (unsigned int)(v2 + 128);
            v8 = &v29;
            do
            {
              v9 = v5[1];
              *(_OWORD *)v8 = *v5;
              v10 = v5[2];
              *((_OWORD *)v8 + 1) = v9;
              v11 = v5[3];
              *((_OWORD *)v8 + 2) = v10;
              v12 = v5[4];
              *((_OWORD *)v8 + 3) = v11;
              v13 = v5[5];
              *((_OWORD *)v8 + 4) = v12;
              v14 = v5[6];
              *((_OWORD *)v8 + 5) = v13;
              v15 = v5[7];
              v5 = (_OWORD *)((char *)v5 + v7);
              *((_OWORD *)v8 + 6) = v14;
              *((_OWORD *)v8 + 7) = v15;
              v8 += v7;
              --v6;
            }
            while ( v6 );
            v16 = v5[1];
            *(_OWORD *)v8 = *v5;
            v17 = v5[2];
            *((_OWORD *)v8 + 1) = v16;
            v18 = v5[3];
            *((_OWORD *)v8 + 2) = v17;
            v19 = v5[4];
            v20 = *((_QWORD *)v5 + 10);
            *((_OWORD *)v8 + 3) = v18;
            *((_OWORD *)v8 + 4) = v19;
            *((_QWORD *)v8 + 10) = v20;
            WwanFreeMemory();
            v24 = 0;
            v21 = (unsigned __int16 *)LocalAlloc(0, 0x24u);
            if ( v21 )
            {
              v2 = StringCchCopyW(v21, 0x12u, v30);
              if ( v2 >= 0 )
                *a1 = v22;
            }
            else
            {
              v2 = -2147024882;
            }
          }
          goto LABEL_20;
        }
      }
    }
    if ( !v4 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    goto LABEL_20;
  }
  v2 = -2147023834;
LABEL_20:
  if ( v24 )
    WwanFreeMemory();
  if ( v28 )
    WwanFreeMemory();
  if ( v25 )
    WwanCloseHandle(v25, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180062f30  mov     [rsp-8+arg_8], rbx
0x180062f35  mov     [rsp-8+arg_10], rdi
0x180062f3a  push    rbp
0x180062f3b  lea     rbp, [rsp-0D0h]
0x180062f43  sub     rsp, 1D0h
0x180062f4a  mov     rax, cs:__security_cookie
0x180062f51  xor     rax, rsp
0x180062f54  mov     [rbp+0D0h+var_10], rax
0x180062f5b  mov     [rsp+1D0h+var_180], 0
0x180062f63  mov     rdi, rcx
0x180062f66  mov     [rsp+1D0h+var_188], 0
0x180062f6f  mov     [rsp+1D0h+var_178], 0
0x180062f78  mov     [rsp+1D0h+var_190], 0
0x180062f81  test    rcx, rcx
0x180062f84  jnz     short loc_180062F90
0x180062f86  mov     ebx, 80070057h
0x180062f8b  jmp     loc_1800631AC
0x180062f90  xor     edx, edx
0x180062f92  mov     qword ptr [rcx], 0
0x180062f99  lea     r9, [rsp+1D0h+var_188]
0x180062f9e  lea     r8, [rsp+1D0h+var_180]
0x180062fa3  lea     ecx, [rdx+1]
0x180062fa6  call    cs:__imp_WwanOpenHandle
0x180062fad  nop     dword ptr [rax+rax+00h]
0x180062fb2  mov     ebx, eax
0x180062fb4  cmp     eax, 426h
0x180062fb9  jnz     short loc_180062FC5
0x180062fbb  mov     ebx, 80070426h
0x180062fc0  jmp     loc_180063168
0x180062fc5  test    eax, eax
0x180062fc7  jz      short loc_180062FDD
0x180062fc9  jle     loc_180063168
0x180062fcf  movzx   ebx, ax
0x180062fd2  or      ebx, 80070000h
0x180062fd8  jmp     loc_180063168
0x180062fdd  mov     rcx, [rsp+1D0h+var_188]
0x180062fe2  lea     r8, [rsp+1D0h+var_178]
0x180062fe7  xor     edx, edx
0x180062fe9  call    cs:__imp_WwanEnumerateInterfaces
0x180062ff0  nop     dword ptr [rax+rax+00h]
0x180062ff5  mov     ebx, eax
0x180062ff7  test    eax, eax
0x180062ff9  jnz     short loc_180062FC9
0x180062ffb  mov     rcx, [rsp+1D0h+var_178]
0x180063000  cmp     [rcx], eax
0x180063002  jbe     loc_180063163
0x180063008  mov     [rsp+1D0h+var_17C], eax
0x18006300c  lea     rdx, [rcx+4]
0x180063010  mov     rcx, [rsp+1D0h+var_188]
0x180063015  lea     rax, [rsp+1D0h+var_190]
0x18006301a  mov     [rsp+1D0h+var_198], 0
0x180063023  lea     r8d, [rbx+7]
0x180063027  mov     [rsp+1D0h+var_1A0], 0
0x180063030  xor     r9d, r9d
0x180063033  mov     [rsp+1D0h+var_1A8], rax
0x180063038  lea     rax, [rsp+1D0h+var_17C]
0x18006303d  mov     [rsp+1D0h+var_1B0], rax
0x180063042  call    cs:__imp_WwanQueryInterface
0x180063049  nop     dword ptr [rax+rax+00h]
0x18006304e  mov     ebx, eax
0x180063050  test    eax, eax
0x180063052  jnz     loc_180062FC9
0x180063058  mov     rcx, [rsp+1D0h+var_190]
0x18006305d  lea     rax, [rcx+228h]
0x180063064  test    rax, rax
0x180063067  jz      loc_180063145
0x18006306d  lea     r8d, [rbx+2]
0x180063071  lea     r9d, [r8+7Eh]
0x180063075  lea     rdx, [rsp+1D0h+var_170]
0x18006307a  movups  xmm0, xmmword ptr [rax]
0x18006307d  movups  xmm1, xmmword ptr [rax+10h]
0x180063081  movups  xmmword ptr [rdx], xmm0
0x180063084  movups  xmm0, xmmword ptr [rax+20h]
0x180063088  movups  xmmword ptr [rdx+10h], xmm1
0x18006308c  movups  xmm1, xmmword ptr [rax+30h]
0x180063090  movups  xmmword ptr [rdx+20h], xmm0
0x180063094  movups  xmm0, xmmword ptr [rax+40h]
0x180063098  movups  xmmword ptr [rdx+30h], xmm1
0x18006309c  movups  xmm1, xmmword ptr [rax+50h]
0x1800630a0  movups  xmmword ptr [rdx+40h], xmm0
0x1800630a4  movups  xmm0, xmmword ptr [rax+60h]
0x1800630a8  movups  xmmword ptr [rdx+50h], xmm1
0x1800630ac  movups  xmm1, xmmword ptr [rax+70h]
0x1800630b0  add     rax, r9
0x1800630b3  movups  xmmword ptr [rdx+60h], xmm0
0x1800630b7  movups  xmmword ptr [rdx+70h], xmm1
0x1800630bb  add     rdx, r9
0x1800630be  sub     r8, 1
0x1800630c2  jnz     short loc_18006307A
0x1800630c4  movups  xmm0, xmmword ptr [rax]
0x1800630c7  movups  xmm1, xmmword ptr [rax+10h]
0x1800630cb  movups  xmmword ptr [rdx], xmm0
0x1800630ce  movups  xmm0, xmmword ptr [rax+20h]
0x1800630d2  movups  xmmword ptr [rdx+10h], xmm1
0x1800630d6  movups  xmm1, xmmword ptr [rax+30h]
0x1800630da  movups  xmmword ptr [rdx+20h], xmm0
0x1800630de  movups  xmm0, xmmword ptr [rax+40h]
0x1800630e2  mov     rax, [rax+50h]
0x1800630e6  movups  xmmword ptr [rdx+30h], xmm1
0x1800630ea  movups  xmmword ptr [rdx+40h], xmm0
0x1800630ee  mov     [rdx+50h], rax
0x1800630f2  call    cs:__imp_WwanFreeMemory
0x1800630f9  nop     dword ptr [rax+rax+00h]
0x1800630fe  mov     edx, 24h ; '$'; uBytes
0x180063103  mov     [rsp+1D0h+var_190], 0
0x18006310c  xor     ecx, ecx; uFlags
0x18006310e  call    cs:__imp_LocalAlloc
0x180063115  nop     dword ptr [rax+rax+00h]
0x18006311a  mov     r11, rax
0x18006311d  test    rax, rax
0x180063120  jnz     short loc_180063129
0x180063122  mov     ebx, 8007000Eh
0x180063127  jmp     short loc_180063168
0x180063129  lea     r8, [rbp+0D0h+var_10C]; unsigned __int16 *
0x18006312d  mov     edx, 12h; unsigned __int64
0x180063132  mov     rcx, r11; unsigned __int16 *
0x180063135  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006313a  mov     ebx, eax
0x18006313c  test    eax, eax
0x18006313e  js      short loc_180063168
0x180063140  mov     [rdi], r11
0x180063143  jmp     short loc_180063168
0x180063145  call    cs:__imp__o__errno
0x18006314c  nop     dword ptr [rax+rax+00h]
0x180063151  mov     dword ptr [rax], 16h
0x180063157  call    _invalid_parameter_noinfo
0x18006315c  mov     ebx, 8007007Ah
0x180063161  jmp     short loc_180063168
0x180063163  mov     ebx, 80070002h
0x180063168  mov     rcx, [rsp+1D0h+var_190]
0x18006316d  test    rcx, rcx
0x180063170  jz      short loc_18006317E
0x180063172  call    cs:__imp_WwanFreeMemory
0x180063179  nop     dword ptr [rax+rax+00h]
0x18006317e  mov     rcx, [rsp+1D0h+var_178]
0x180063183  test    rcx, rcx
0x180063186  jz      short loc_180063194
0x180063188  call    cs:__imp_WwanFreeMemory
0x18006318f  nop     dword ptr [rax+rax+00h]
0x180063194  mov     rcx, [rsp+1D0h+var_188]
0x180063199  test    rcx, rcx
0x18006319c  jz      short loc_1800631AC
0x18006319e  xor     edx, edx
0x1800631a0  call    cs:__imp_WwanCloseHandle
0x1800631a7  nop     dword ptr [rax+rax+00h]
0x1800631ac  mov     eax, ebx
0x1800631ae  mov     rcx, [rbp+0D0h+var_10]
0x1800631b5  xor     rcx, rsp; StackCookie
0x1800631b8  call    __security_check_cookie
0x1800631bd  lea     r11, [rsp+1D0h+var_s0]
0x1800631c5  mov     rbx, [r11+18h]
0x1800631c9  mov     rdi, [r11+20h]
0x1800631cd  mov     rsp, r11
0x1800631d0  pop     rbp
0x1800631d1  retn
```
