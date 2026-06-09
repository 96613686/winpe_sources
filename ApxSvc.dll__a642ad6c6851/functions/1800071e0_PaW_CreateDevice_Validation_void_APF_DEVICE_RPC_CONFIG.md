# PaW_CreateDevice_Validation(void * *,APF_DEVICE_RPC_CONFIG *)

- ea: `0x1800071e0`
- end: `0x1800073ae`
- name: `?PaW_CreateDevice_Validation@@YAJPEAPEAXPEAUAPF_DEVICE_RPC_CONFIG@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(void **, struct APF_DEVICE_RPC_CONFIG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000630c`

## callees

- `0x180001560`
- `0x1800071e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007317`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180007317`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800072ff`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800072ff`

## pseudocode

```c
__int64 __fastcall PaW_CreateDevice_Validation(void **a1, struct APF_DEVICE_RPC_CONFIG *a2)
{
  unsigned int v3; // ebp
  __int64 v4; // rsi
  const GUID *v5; // rdi
  __int64 v6; // rcx
  unsigned int v7; // ecx
  OLECHAR sz[8]; // [rsp+20h] [rbp-78h] BYREF
  __int128 v10; // [rsp+30h] [rbp-68h]
  __int128 v11; // [rsp+40h] [rbp-58h]
  _OWORD v12[2]; // [rsp+50h] [rbp-48h]

  v3 = -2147024809;
  *(_OWORD *)sz = *(_OWORD *)L"{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}";
  v11 = *(_OWORD *)L"xxx-xxxx-xxxxxxxxxxxx}";
  v10 = *(_OWORD *)L"x-xxxx-xxxx-xxxx-xxxxxxxxxxxx}";
  v12[0] = *(_OWORD *)L"-xxxxxxxxxxxx}";
  *(_OWORD *)((char *)v12 + 14) = *(_OWORD *)L"xxxxxx}";
  if ( a1 )
  {
    v4 = (__int64)*a1;
    if ( *a1 )
    {
      if ( *((_WORD *)a2 + 28) == 1118
        && *((_WORD *)a2 + 29) == 1
        && *((_WORD *)a2 + 32) == 1
        && *((_QWORD *)a2 + 3) == PAW_DEVICE_CLASS_GUID
        && *((_QWORD *)a2 + 4) == 0xFF3250759F79A586uLL )
      {
        v5 = (const GUID *)((char *)a2 + 8);
        if ( (*((_QWORD *)a2 + 1) || *((_QWORD *)a2 + 2))
          && *(_QWORD *)&v5->Data1 == *((_QWORD *)a2 + 5)
          && *((_QWORD *)a2 + 2) == *((_QWORD *)a2 + 6)
          && *((_DWORD *)a2 + 15) == v5->Data1 )
        {
          if ( StringFromGUID2(v5, sz, 39) )
          {
            v6 = *((_QWORD *)a2 + 9);
            if ( v6 )
            {
              if ( !(unsigned int)_o__wcsicmp(v6, sz) )
              {
                v7 = 0;
                while ( *(_QWORD *)(v4 + 16LL * v7) || *(_QWORD *)(v4 + 16LL * v7 + 8) )
                {
                  if ( (*(_QWORD *)(v4 + 16LL * v7) != *(_QWORD *)&v5->Data1
                     || *(_QWORD *)(v4 + 16LL * v7 + 8) != *(_QWORD *)v5->Data4)
                    && ++v7 < 0x32 )
                  {
                    continue;
                  }
                  if ( v7 == 50 )
                    return (unsigned int)-1073741478;
                  break;
                }
                if ( !*(_QWORD *)(v4 + 16LL * v7) && !*(_QWORD *)(v4 + 16LL * v7 + 8) )
                  *(GUID *)(v4 + 16LL * v7) = *v5;
                return 0;
              }
            }
          }
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800071e0  mov     [rsp+arg_10], rbx
0x1800071e5  mov     [rsp+arg_18], rbp
0x1800071ea  push    rsi
0x1800071eb  push    rdi
0x1800071ec  push    r14
0x1800071ee  sub     rsp, 80h
0x1800071f5  mov     rax, cs:__security_cookie
0x1800071fc  xor     rax, rsp
0x1800071ff  mov     [rsp+98h+var_28], rax
0x180007204  movaps  xmm0, xmmword ptr cs:aXxxxxxxxXxxxXx; "{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}"
0x18000720b  mov     rbx, rdx
0x18000720e  movaps  xmm1, xmmword ptr cs:aXxxxxxxxXxxxXx+10h; "x-xxxx-xxxx-xxxx-xxxxxxxxxxxx}"
0x180007215  mov     ebp, 80070057h
0x18000721a  movaps  xmmword ptr [rsp+98h+sz], xmm0
0x18000721f  movaps  xmm0, xmmword ptr cs:aXxxxxxxxXxxxXx+20h; "xxx-xxxx-xxxxxxxxxxxx}"
0x180007226  movaps  [rsp+98h+var_58], xmm0
0x18000722b  movaps  [rsp+98h+var_68], xmm1
0x180007230  movaps  xmm1, xmmword ptr cs:aXxxxxxxxXxxxXx+30h; "-xxxxxxxxxxxx}"
0x180007237  movaps  xmmword ptr [rsp+98h+var_48], xmm1
0x18000723c  movups  xmm0, xmmword ptr cs:aXxxxxxxxXxxxXx+3Eh; "xxxxxx}"
0x180007243  movups  xmmword ptr [rsp+98h+var_48+0Eh], xmm0
0x180007248  test    rcx, rcx
0x18000724b  jz      loc_180007387
0x180007251  mov     rsi, [rcx]
0x180007254  test    rsi, rsi
0x180007257  jz      loc_180007387
0x18000725d  mov     eax, 45Eh
0x180007262  cmp     [rdx+38h], ax
0x180007266  jnz     loc_180007387
0x18000726c  mov     r14d, 1
0x180007272  cmp     [rdx+3Ah], r14w
0x180007277  jnz     loc_180007387
0x18000727d  cmp     [rdx+40h], r14w
0x180007282  jnz     loc_180007387
0x180007288  mov     rax, [rdx+18h]
0x18000728c  cmp     rax, cs:PAW_DEVICE_CLASS_GUID
0x180007293  jnz     loc_180007387
0x180007299  mov     rax, [rdx+20h]
0x18000729d  cmp     rax, cs:qword_18000B4B8
0x1800072a4  jnz     loc_180007387
0x1800072aa  lea     rdi, [rdx+8]
0x1800072ae  mov     rax, [rdi]
0x1800072b1  cmp     rax, cs:qword_18000B4C0
0x1800072b8  jnz     short loc_1800072CB
0x1800072ba  mov     rax, [rdi+8]
0x1800072be  cmp     rax, cs:qword_18000B4C8
0x1800072c5  jz      loc_180007387
0x1800072cb  mov     rax, [rdi]
0x1800072ce  cmp     rax, [rdx+28h]
0x1800072d2  jnz     loc_180007387
0x1800072d8  mov     rax, [rdi+8]
0x1800072dc  cmp     rax, [rdx+30h]
0x1800072e0  jnz     loc_180007387
0x1800072e6  mov     eax, [rdi]
0x1800072e8  cmp     [rdx+3Ch], eax
0x1800072eb  jnz     loc_180007387
0x1800072f1  mov     r8d, 27h ; '''; cchMax
0x1800072f7  lea     rdx, [rsp+98h+sz]; lpsz
0x1800072fc  mov     rcx, rdi; rguid
0x1800072ff  call    cs:__imp_StringFromGUID2
0x180007305  test    eax, eax
0x180007307  jz      short loc_180007387
0x180007309  mov     rcx, [rbx+48h]
0x18000730d  test    rcx, rcx
0x180007310  jz      short loc_180007387
0x180007312  lea     rdx, [rsp+98h+sz]
0x180007317  call    cs:__imp__o__wcsicmp
0x18000731d  test    eax, eax
0x18000731f  jnz     short loc_180007387
0x180007321  mov     r8, cs:qword_18000B4C8
0x180007328  xor     ecx, ecx
0x18000732a  mov     r9, cs:qword_18000B4C0
0x180007331  mov     edx, ecx
0x180007333  add     rdx, rdx
0x180007336  cmp     [rsi+rdx*8], r9
0x18000733a  jnz     short loc_180007343
0x18000733c  cmp     [rsi+rdx*8+8], r8
0x180007341  jz      short loc_18000736B
0x180007343  mov     rax, [rsi+rdx*8]
0x180007347  cmp     rax, [rdi]
0x18000734a  jnz     short loc_180007357
0x18000734c  mov     rax, [rsi+rdx*8+8]
0x180007351  cmp     rax, [rdi+8]
0x180007355  jz      short loc_18000735F
0x180007357  add     ecx, r14d
0x18000735a  cmp     ecx, 32h ; '2'
0x18000735d  jb      short loc_180007331
0x18000735f  cmp     ecx, 32h ; '2'
0x180007362  jnz     short loc_18000736B
0x180007364  mov     ebp, 0C000015Ah
0x180007369  jmp     short loc_180007387
0x18000736b  mov     eax, ecx
0x18000736d  add     rax, rax
0x180007370  cmp     [rsi+rax*8], r9
0x180007374  jnz     short loc_180007385
0x180007376  cmp     [rsi+rax*8+8], r8
0x18000737b  jnz     short loc_180007385
0x18000737d  movups  xmm0, xmmword ptr [rdi]
0x180007380  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x180007385  xor     ebp, ebp
0x180007387  mov     eax, ebp
0x180007389  mov     rcx, [rsp+98h+var_28]
0x18000738e  xor     rcx, rsp; StackCookie
0x180007391  call    __security_check_cookie
0x180007396  lea     r11, [rsp+98h+var_18]
0x18000739e  mov     rbx, [r11+30h]
0x1800073a2  mov     rbp, [r11+38h]
0x1800073a6  mov     rsp, r11
0x1800073a9  pop     r14
0x1800073ab  pop     rdi
0x1800073ac  pop     rsi
0x1800073ad  retn
```
