# WdipReadParameterFromMessageBuffer(_DPS_MESSAGE *,unsigned __int64,uchar * *)

- ea: `0x180017d7c`
- end: `0x1800180eb`
- name: `?WdipReadParameterFromMessageBuffer@@YAPEAU__WDIP_PARAMETER@@PEAU_DPS_MESSAGE@@_KPEAPEAE@Z`
- size: `879`
- prototype: `struct __WDIP_PARAMETER *__fastcall(struct _DPS_MESSAGE *, unsigned __int64, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800096c0`

## callees

- `0x1800013a0`
- `0x180009090`
- `0x180009660`
- `0x18000a856`
- `0x180017d7c`
- `0x180018b49`

## string_xrefs

- `0x180017dc5`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x1800180a3`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x180017dbe`: `WdipReadParameterFromMessageBuffer`
- `0x1800180aa`: `WdipReadParameterFromMessageBuffer`

## pseudocode

```c
struct __WDIP_PARAMETER *__fastcall WdipReadParameterFromMessageBuffer(
        struct _DPS_MESSAGE *a1,
        unsigned __int64 a2,
        unsigned __int8 **a3)
{
  __int64 v3; // r14
  int v7; // r8d
  __int64 v8; // rax
  __int64 v9; // rbp
  int v10; // r8d
  int v11; // eax
  struct _DPS_MESSAGE *v12; // rcx
  signed __int64 v13; // rdx
  char *v14; // r9
  __int128 v15; // xmm0
  struct _DPS_MESSAGE *v16; // r8
  __int128 v17; // xmm0
  struct _DPS_MESSAGE *v18; // r8
  int v19; // eax
  struct _DPS_MESSAGE *v20; // r8
  int v21; // eax
  struct _DPS_MESSAGE *v22; // r8
  int v23; // eax
  bool v24; // zf
  unsigned __int8 *v25; // rcx
  size_t v26; // r14
  unsigned int v27; // eax
  size_t v28; // r15
  void *v29; // rax
  unsigned __int64 v30; // r15
  unsigned int *v31; // rdx
  __int64 v32; // rcx
  void *v33; // rax
  size_t v34; // r8
  __int64 v36; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  if ( !*a3 )
  {
    v7 = 171;
LABEL_3:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (__int64)L"WdipReadParameterFromMessageBuffer",
      v7,
      (const wchar_t *)L"Error = %d",
      87);
    return (struct __WDIP_PARAMETER *)v3;
  }
  if ( !a1 )
  {
    v7 = 172;
    goto LABEL_3;
  }
  v8 = WdipAlloc(64);
  v36 = v8;
  v9 = v8;
  if ( !v8 )
  {
    v10 = 175;
    v11 = 14;
    goto LABEL_64;
  }
  v12 = (struct _DPS_MESSAGE *)*a3;
  *(_QWORD *)(v8 + 48) = 0;
  *(_QWORD *)(v8 + 56) = 0;
  if ( v12
    && v12 >= a1
    && (v13 = v12 - a1, v12 - a1 <= a2)
    && (v14 = (char *)(a2 + a1 - v12), (unsigned __int64)v14 >= 0x10) )
  {
    v15 = *(_OWORD *)v12;
    v16 = (struct _DPS_MESSAGE *)((char *)v12 + 16);
    *a3 = (unsigned __int8 *)v12 + 16;
    *(_OWORD *)v8 = v15;
    if ( v12 == (struct _DPS_MESSAGE *)-16LL || v16 < a1 || v13 + 16 > a2 || (unsigned __int64)(v14 - 16) < 0x10 )
    {
      v10 = 195;
    }
    else
    {
      v17 = *(_OWORD *)v16;
      v18 = (struct _DPS_MESSAGE *)((char *)v12 + 32);
      *a3 = (unsigned __int8 *)v12 + 32;
      *(_OWORD *)(v8 + 16) = v17;
      if ( v12 == (struct _DPS_MESSAGE *)-32LL || v18 < a1 || v13 + 32 > a2 || (unsigned __int64)(v14 - 32) < 4 )
      {
        v10 = 206;
      }
      else
      {
        v19 = *(_DWORD *)v18;
        v20 = (struct _DPS_MESSAGE *)((char *)v12 + 36);
        *(_DWORD *)(v9 + 32) = v19;
        *a3 = (unsigned __int8 *)v12 + 36;
        if ( v12 == (struct _DPS_MESSAGE *)-36LL || v20 < a1 || v13 + 36 > a2 || (unsigned __int64)(v14 - 36) < 4 )
        {
          v10 = 217;
        }
        else
        {
          v21 = *(_DWORD *)v20;
          v22 = (struct _DPS_MESSAGE *)((char *)v12 + 40);
          *(_DWORD *)(v9 + 36) = v21;
          *a3 = (unsigned __int8 *)v12 + 40;
          if ( v12 == (struct _DPS_MESSAGE *)-40LL || v22 < a1 || v13 + 40 > a2 || (unsigned __int64)(v14 - 40) < 4 )
          {
            v10 = 228;
          }
          else
          {
            v23 = *(_DWORD *)v22;
            v24 = (struct _DPS_MESSAGE *)((char *)v12 + 44) == 0;
            v25 = (unsigned __int8 *)v12 + 44;
            *a3 = v25;
            *(_DWORD *)(v9 + 44) = v23;
            if ( v24
              || v25 < (unsigned __int8 *)a1
              || v25 - (unsigned __int8 *)a1 > a2
              || a2 + a1 - (struct _DPS_MESSAGE *)v25 < 4 )
            {
              v10 = 239;
            }
            else
            {
              v26 = *(unsigned int *)v25;
              *a3 = v25 + 4;
              v27 = v26 + 2;
              if ( (int)v26 + 2 < (unsigned int)v26 )
              {
                v10 = 255;
                v11 = 534;
LABEL_39:
                v3 = 0;
                goto LABEL_64;
              }
              v28 = v27;
              v29 = (void *)WdipAlloc(v27);
              *(_QWORD *)(v9 + 48) = v29;
              if ( !v29 )
              {
                v10 = 258;
LABEL_42:
                v11 = 14;
                goto LABEL_39;
              }
              memset_0(v29, 0, v28);
              v30 = (unsigned __int64)*a3;
              if ( *a3
                && v30 >= (unsigned __int64)a1
                && v30 - (unsigned __int64)a1 <= a2
                && v26 <= (unsigned __int64)a1 + a2 - v30 )
              {
                memcpy_0(*(void **)(v9 + 48), *a3, v26);
                v31 = (unsigned int *)(v30 + v26);
                *a3 = (unsigned __int8 *)(v30 + v26);
                if ( v30 + v26
                  && v31 >= (unsigned int *)a1
                  && v30 - (_QWORD)a1 + v26 <= a2
                  && (unsigned __int64)a1 + a2 - v26 - v30 >= 4 )
                {
                  v32 = *v31;
                  *(_DWORD *)(v9 + 40) = v32;
                  *a3 = (unsigned __int8 *)(v31 + 1);
                  v33 = (void *)WdipAlloc(v32);
                  *(_QWORD *)(v9 + 56) = v33;
                  if ( !v33 )
                  {
                    v10 = 284;
                    goto LABEL_42;
                  }
                  if ( *a3 )
                  {
                    if ( *a3 >= (unsigned __int8 *)a1 && *a3 - (unsigned __int8 *)a1 <= a2 )
                    {
                      v34 = *(unsigned int *)(v9 + 40);
                      if ( v34 <= a2 + a1 - (struct _DPS_MESSAGE *)*a3 )
                      {
                        memcpy_0(v33, *a3, v34);
                        v3 = v9;
                        *a3 += *(unsigned int *)(v9 + 40);
                        return (struct __WDIP_PARAMETER *)v3;
                      }
                    }
                  }
                  v10 = 290;
                }
                else
                {
                  v10 = 276;
                }
              }
              else
              {
                v10 = 265;
              }
              v3 = 0;
            }
          }
        }
      }
    }
  }
  else
  {
    v10 = 184;
  }
  v11 = 111;
LABEL_64:
  WdipTraceError(
    (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
    (__int64)L"WdipReadParameterFromMessageBuffer",
    v10,
    (const wchar_t *)L"Error = %d",
    v11);
  if ( v9 )
    WdipDeleteParameter(&v36);
  return (struct __WDIP_PARAMETER *)v3;
}

```

## disassembly

```asm
0x180017d7c  mov     [rsp+arg_0], rbx
0x180017d81  push    rbp
0x180017d82  push    rsi
0x180017d83  push    rdi
0x180017d84  push    r12
0x180017d86  push    r13
0x180017d88  push    r14
0x180017d8a  push    r15
0x180017d8c  sub     rsp, 30h
0x180017d90  xor     r14d, r14d
0x180017d93  mov     rsi, r8
0x180017d96  mov     rdi, rdx
0x180017d99  mov     rbx, rcx
0x180017d9c  mov     [rsp+68h+arg_10], r14
0x180017da4  cmp     [r8], r14
0x180017da7  jnz     short loc_180017DD6
0x180017da9  mov     r8d, 0ABh; int
0x180017daf  lea     r9, aErrorD; "Error = %d"
0x180017db6  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x180017dbe  lea     rdx, aWdipreadparame_1; "WdipReadParameterFromMessageBuffer"
0x180017dc5  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180017dcc  call    WdipTraceError
0x180017dd1  jmp     loc_1800180D3
0x180017dd6  test    rbx, rbx
0x180017dd9  jnz     short loc_180017DE3
0x180017ddb  mov     r8d, 0ACh
0x180017de1  jmp     short loc_180017DAF
0x180017de3  mov     ecx, 40h ; '@'
0x180017de8  call    WdipAlloc
0x180017ded  mov     [rsp+68h+arg_18], rax
0x180017df5  mov     rbp, rax
0x180017df8  test    rax, rax
0x180017dfb  jnz     short loc_180017E0B
0x180017dfd  mov     r8d, 0AFh
0x180017e03  lea     eax, [rbp+0Eh]
0x180017e06  jmp     loc_1800180A3
0x180017e0b  mov     rcx, [rsi]
0x180017e0e  mov     [rax+30h], r14
0x180017e12  mov     [rax+38h], r14
0x180017e16  test    rcx, rcx
0x180017e19  jz      loc_180018098
0x180017e1f  cmp     rcx, rbx
0x180017e22  jb      loc_180018098
0x180017e28  mov     rdx, rcx
0x180017e2b  sub     rdx, rbx
0x180017e2e  cmp     rdx, rdi
0x180017e31  ja      loc_180018098
0x180017e37  mov     r9, rbx
0x180017e3a  sub     r9, rcx
0x180017e3d  add     r9, rdi
0x180017e40  cmp     r9, 10h
0x180017e44  jb      loc_180018098
0x180017e4a  movups  xmm0, xmmword ptr [rcx]
0x180017e4d  lea     r8, [rcx+10h]
0x180017e51  mov     [rsi], r8
0x180017e54  movdqu  xmmword ptr [rax], xmm0
0x180017e58  test    r8, r8
0x180017e5b  jz      short loc_180017E6B
0x180017e5d  cmp     r8, rbx
0x180017e60  jb      short loc_180017E6B
0x180017e62  lea     rax, [rdx+10h]
0x180017e66  cmp     rax, rdi
0x180017e69  jbe     short loc_180017E76
0x180017e6b  mov     r8d, 0C3h
0x180017e71  jmp     loc_18001809E
0x180017e76  lea     rax, [r9-10h]
0x180017e7a  cmp     rax, 10h
0x180017e7e  jb      short loc_180017E6B
0x180017e80  movups  xmm0, xmmword ptr [r8]
0x180017e84  lea     r8, [rcx+20h]
0x180017e88  mov     [rsi], r8
0x180017e8b  movdqu  xmmword ptr [rbp+10h], xmm0
0x180017e90  test    r8, r8
0x180017e93  jz      short loc_180017EA3
0x180017e95  cmp     r8, rbx
0x180017e98  jb      short loc_180017EA3
0x180017e9a  lea     rax, [rdx+20h]
0x180017e9e  cmp     rax, rdi
0x180017ea1  jbe     short loc_180017EAE
0x180017ea3  mov     r8d, 0CEh
0x180017ea9  jmp     loc_18001809E
0x180017eae  lea     rax, [r9-20h]
0x180017eb2  cmp     rax, 4
0x180017eb6  jb      short loc_180017EA3
0x180017eb8  mov     eax, [r8]
0x180017ebb  lea     r8, [rcx+24h]
0x180017ebf  mov     [rbp+20h], eax
0x180017ec2  mov     [rsi], r8
0x180017ec5  test    r8, r8
0x180017ec8  jz      short loc_180017ED8
0x180017eca  cmp     r8, rbx
0x180017ecd  jb      short loc_180017ED8
0x180017ecf  lea     rax, [rdx+24h]
0x180017ed3  cmp     rax, rdi
0x180017ed6  jbe     short loc_180017EE3
0x180017ed8  mov     r8d, 0D9h
0x180017ede  jmp     loc_18001809E
0x180017ee3  lea     rax, [r9-24h]
0x180017ee7  cmp     rax, 4
0x180017eeb  jb      short loc_180017ED8
0x180017eed  mov     eax, [r8]
0x180017ef0  lea     r8, [rcx+28h]
0x180017ef4  mov     [rbp+24h], eax
0x180017ef7  mov     [rsi], r8
0x180017efa  test    r8, r8
0x180017efd  jz      short loc_180017F0D
0x180017eff  cmp     r8, rbx
0x180017f02  jb      short loc_180017F0D
0x180017f04  lea     rax, [rdx+28h]
0x180017f08  cmp     rax, rdi
0x180017f0b  jbe     short loc_180017F18
0x180017f0d  mov     r8d, 0E4h
0x180017f13  jmp     loc_18001809E
0x180017f18  lea     rax, [r9-28h]
0x180017f1c  cmp     rax, 4
0x180017f20  jb      short loc_180017F0D
0x180017f22  mov     eax, [r8]
0x180017f25  add     rcx, 2Ch ; ','
0x180017f29  mov     [rsi], rcx
0x180017f2c  mov     [rbp+2Ch], eax
0x180017f2f  jz      short loc_180017F41
0x180017f31  cmp     rcx, rbx
0x180017f34  jb      short loc_180017F41
0x180017f36  mov     rax, rcx
0x180017f39  sub     rax, rbx
0x180017f3c  cmp     rax, rdi
0x180017f3f  jbe     short loc_180017F4C
0x180017f41  mov     r8d, 0EFh
0x180017f47  jmp     loc_18001809E
0x180017f4c  mov     rax, rbx
0x180017f4f  sub     rax, rcx
0x180017f52  add     rax, rdi
0x180017f55  cmp     rax, 4
0x180017f59  jb      short loc_180017F41
0x180017f5b  mov     r14d, [rcx]
0x180017f5e  lea     rax, [rcx+4]
0x180017f62  mov     [rsi], rax
0x180017f65  lea     eax, [r14+2]
0x180017f69  cmp     eax, r14d
0x180017f6c  jnb     short loc_180017F86
0x180017f6e  mov     r8d, 0FFh
0x180017f74  mov     eax, 216h
0x180017f79  mov     r14, [rsp+68h+arg_10]
0x180017f81  jmp     loc_1800180A3
0x180017f86  mov     ecx, eax
0x180017f88  mov     r15d, eax
0x180017f8b  call    WdipAlloc
0x180017f90  mov     [rbp+30h], rax
0x180017f94  test    rax, rax
0x180017f97  jnz     short loc_180017FA6
0x180017f99  mov     r8d, 102h
0x180017f9f  mov     eax, 0Eh
0x180017fa4  jmp     short loc_180017F79
0x180017fa6  mov     r8, r15; Size
0x180017fa9  xor     edx, edx; Val
0x180017fab  mov     rcx, rax; void *
0x180017fae  call    memset_0
0x180017fb3  mov     r15, [rsi]
0x180017fb6  test    r15, r15
0x180017fb9  jz      short loc_180017FCB
0x180017fbb  cmp     r15, rbx
0x180017fbe  jb      short loc_180017FCB
0x180017fc0  mov     r12, r15
0x180017fc3  sub     r12, rbx
0x180017fc6  cmp     r12, rdi
0x180017fc9  jbe     short loc_180017FDE
0x180017fcb  mov     r8d, 109h
0x180017fd1  mov     r14, [rsp+68h+arg_10]
0x180017fd9  jmp     loc_18001809E
0x180017fde  mov     r13, r14
0x180017fe1  mov     r14, rbx
0x180017fe4  sub     r14, r15
0x180017fe7  lea     rax, [r14+rdi]
0x180017feb  cmp     r13, rax
0x180017fee  ja      short loc_180017FCB
0x180017ff0  mov     rcx, [rbp+30h]; void *
0x180017ff4  mov     r8, r13; Size
0x180017ff7  mov     rdx, r15; Src
0x180017ffa  call    memcpy_0
0x180017fff  lea     rdx, [r15+r13]
0x180018003  mov     [rsi], rdx
0x180018006  test    rdx, rdx
0x180018009  jz      short loc_180018019
0x18001800b  cmp     rdx, rbx
0x18001800e  jb      short loc_180018019
0x180018010  lea     rax, [r12+r13]
0x180018014  cmp     rax, rdi
0x180018017  jbe     short loc_180018021
0x180018019  mov     r8d, 114h
0x18001801f  jmp     short loc_180017FD1
0x180018021  sub     r14, r13
0x180018024  add     r14, rdi
0x180018027  cmp     r14, 4
0x18001802b  jb      short loc_180018019
0x18001802d  mov     ecx, [rdx]
0x18001802f  lea     rax, [rdx+4]
0x180018033  mov     [rbp+28h], ecx
0x180018036  mov     [rsi], rax
0x180018039  call    WdipAlloc
0x18001803e  mov     [rbp+38h], rax
0x180018042  mov     rcx, rax; void *
0x180018045  test    rax, rax
0x180018048  jnz     short loc_180018055
0x18001804a  mov     r8d, 11Ch
0x180018050  jmp     loc_180017F9F
0x180018055  cmp     qword ptr [rsi], 0
0x180018059  jz      short loc_18001806B
0x18001805b  cmp     [rsi], rbx
0x18001805e  jb      short loc_18001806B
0x180018060  mov     rax, [rsi]
0x180018063  sub     rax, rbx
0x180018066  cmp     rax, rdi
0x180018069  jbe     short loc_180018076
0x18001806b  mov     r8d, 122h
0x180018071  jmp     loc_180017FD1
0x180018076  sub     rbx, [rsi]
0x180018079  mov     r8d, [rbp+28h]; Size
0x18001807d  add     rbx, rdi
0x180018080  cmp     r8, rbx
0x180018083  ja      short loc_18001806B
0x180018085  mov     rdx, [rsi]; Src
0x180018088  call    memcpy_0
0x18001808d  mov     eax, [rbp+28h]
0x180018090  mov     r14, rbp
0x180018093  add     [rsi], rax
0x180018096  jmp     short loc_1800180D3
0x180018098  mov     r8d, 0B8h; int
0x18001809e  mov     eax, 6Fh ; 'o'
0x1800180a3  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800180aa  lea     rdx, aWdipreadparame_1; "WdipReadParameterFromMessageBuffer"
0x1800180b1  lea     r9, aErrorD; "Error = %d"
0x1800180b8  mov     dword ptr [rsp+68h+Args], eax; Args
0x1800180bc  call    WdipTraceError
0x1800180c1  test    rbp, rbp
0x1800180c4  jz      short loc_1800180D3
0x1800180c6  lea     rcx, [rsp+68h+arg_18]
0x1800180ce  call    WdipDeleteParameter
0x1800180d3  mov     rbx, [rsp+68h+arg_0]
0x1800180d8  mov     rax, r14
0x1800180db  add     rsp, 30h
0x1800180df  pop     r15
0x1800180e1  pop     r14
0x1800180e3  pop     r13
0x1800180e5  pop     r12
0x1800180e7  pop     rdi
0x1800180e8  pop     rsi
0x1800180e9  pop     rbp
0x1800180ea  retn
```
