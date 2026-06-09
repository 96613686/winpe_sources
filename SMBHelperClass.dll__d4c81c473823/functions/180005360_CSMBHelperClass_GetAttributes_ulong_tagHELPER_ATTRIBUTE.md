# CSMBHelperClass::GetAttributes(ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x180005360`
- end: `0x1800054d8`
- name: `?GetAttributes@CSMBHelperClass@@UEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(CSMBHelperClass *__hidden this, unsigned int *, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005360`
- `0x18000a320`
- `0x18000fbe6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800053d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000545a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800053d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000545a`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::GetAttributes(CSMBHelperClass *this, unsigned int *a2, LPVOID *a3)
{
  __int128 v5; // xmm6
  unsigned int v6; // ebx
  __int64 v7; // rbx
  struct tagHELPER_ATTRIBUTE *v8; // rax
  _QWORD *v9; // r14
  const unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbp
  unsigned __int16 *v13; // rax
  __int128 v15; // [rsp+20h] [rbp-68h] BYREF
  __int128 v16; // [rsp+30h] [rbp-58h] BYREF

  v5 = *(_OWORD *)((char *)this + 156);
  v16 = v5;
  if ( !a2 || !a3 || *a3 || *a2 )
    return (unsigned int)-2147024809;
  v15 = 0;
  if ( !memcmp_0(&v16, &v15, 0x10u) )
  {
    v6 = 0;
LABEL_22:
    *a3 = 0;
    *a2 = 0;
    return v6;
  }
  v7 = 144;
  v8 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
  *a3 = v8;
  if ( v8 )
  {
    do
    {
      LOBYTE(v8->pwszName) = 0;
      v8 = (struct tagHELPER_ATTRIBUTE *)((char *)v8 + 1);
      --v7;
    }
    while ( v7 );
    *((_DWORD *)*a3 + 2) = 11;
    v9 = *a3;
    if ( *a3 )
    {
      v10 = L"rootcauseid";
      v11 = 259;
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --v11;
      }
      while ( v11 );
      v6 = v11 == 0 ? 0x80070057 : 0;
      v12 = (259 - v11) & -(__int64)(v11 != 0);
      if ( v11 )
      {
        v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12 + 2);
        *v9 = v13;
        if ( v13 )
        {
          v6 = StringCchCopyW(v13, v12 + 1, L"rootcauseid");
          if ( (v6 & 0x80000000) == 0 )
          {
            *((_OWORD *)*a3 + 1) = v5;
            *a2 = 1;
            return v6;
          }
        }
        else
        {
          v6 = -2147024882;
        }
      }
    }
    else
    {
      v6 = -2147024809;
    }
    if ( *a3 )
    {
      CoTaskMemFree(*(LPVOID *)*a3);
      CoTaskMemFree(*a3);
      goto LABEL_22;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x180005360  mov     rax, rsp
0x180005363  push    rbx
0x180005364  push    rbp
0x180005365  push    rsi
0x180005366  push    rdi
0x180005367  push    r14
0x180005369  push    r15
0x18000536b  sub     rsp, 58h
0x18000536f  movaps  xmmword ptr [rax-48h], xmm6
0x180005373  xor     r15d, r15d
0x180005376  mov     rdi, r8
0x180005379  mov     rsi, rdx
0x18000537c  movups  xmm6, xmmword ptr [rcx+9Ch]
0x180005383  movaps  xmmword ptr [rax-58h], xmm6
0x180005387  test    rdx, rdx
0x18000538a  jz      loc_1800054BF
0x180005390  test    r8, r8
0x180005393  jz      loc_1800054BF
0x180005399  cmp     [r8], r15
0x18000539c  jnz     loc_1800054BF
0x1800053a2  cmp     [rdx], r15d
0x1800053a5  jnz     loc_1800054BF
0x1800053ab  xorps   xmm0, xmm0
0x1800053ae  lea     r8d, [r15+10h]; Size
0x1800053b2  lea     rdx, [rax-68h]; Buf2
0x1800053b6  lea     rcx, [rax-58h]; Buf1
0x1800053ba  movups  xmmword ptr [rax-68h], xmm0
0x1800053be  call    memcmp_0
0x1800053c3  test    eax, eax
0x1800053c5  jnz     short loc_1800053CF
0x1800053c7  mov     ebx, r15d
0x1800053ca  jmp     loc_1800054B7
0x1800053cf  mov     ebx, 90h
0x1800053d4  mov     ecx, ebx; cb
0x1800053d6  call    cs:__imp_CoTaskMemAlloc
0x1800053dc  mov     [rdi], rax
0x1800053df  test    rax, rax
0x1800053e2  jnz     short loc_1800053EE
0x1800053e4  mov     ebx, 8007000Eh
0x1800053e9  jmp     loc_1800054C4
0x1800053ee  mov     [rax], r15b
0x1800053f1  inc     rax
0x1800053f4  sub     rbx, 1
0x1800053f8  jnz     short loc_1800053EE
0x1800053fa  mov     rax, [rdi]
0x1800053fd  mov     dword ptr [rax+8], 0Bh
0x180005404  mov     r14, [rdi]
0x180005407  test    r14, r14
0x18000540a  jz      loc_180005498
0x180005410  mov     edx, 103h
0x180005415  lea     rax, aRootcauseid; "rootcauseid"
0x18000541c  mov     ecx, edx
0x18000541e  cmp     [rax], r15w
0x180005422  jz      short loc_18000542E
0x180005424  add     rax, 2
0x180005428  sub     rcx, 1
0x18000542c  jnz     short loc_18000541E
0x18000542e  mov     rax, rcx
0x180005431  neg     rax
0x180005434  mov     rax, rcx
0x180005437  sbb     ebx, ebx
0x180005439  sub     rdx, rcx
0x18000543c  not     ebx
0x18000543e  and     ebx, 80070057h
0x180005444  neg     rax
0x180005447  sbb     rbp, rbp
0x18000544a  and     rbp, rdx
0x18000544d  test    rcx, rcx
0x180005450  jz      short loc_18000549D
0x180005452  lea     rcx, ds:2[rbp*2]; cb
0x18000545a  call    cs:__imp_CoTaskMemAlloc
0x180005460  mov     [r14], rax
0x180005463  test    rax, rax
0x180005466  jnz     short loc_18000546F
0x180005468  mov     ebx, 8007000Eh
0x18000546d  jmp     short loc_18000549D
0x18000546f  lea     rdx, [rbp+1]; unsigned __int64
0x180005473  mov     rcx, rax; unsigned __int16 *
0x180005476  lea     r8, aRootcauseid; "rootcauseid"
0x18000547d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005482  mov     ebx, eax
0x180005484  test    eax, eax
0x180005486  js      short loc_18000549D
0x180005488  mov     rax, [rdi]
0x18000548b  movdqu  xmmword ptr [rax+10h], xmm6
0x180005490  mov     dword ptr [rsi], 1
0x180005496  jmp     short loc_1800054C4
0x180005498  mov     ebx, 80070057h
0x18000549d  mov     rcx, [rdi]
0x1800054a0  test    rcx, rcx
0x1800054a3  jz      short loc_1800054C4
0x1800054a5  mov     rcx, [rcx]; pv
0x1800054a8  call    cs:__imp_CoTaskMemFree
0x1800054ae  mov     rcx, [rdi]; pv
0x1800054b1  call    cs:__imp_CoTaskMemFree
0x1800054b7  mov     [rdi], r15
0x1800054ba  mov     [rsi], r15d
0x1800054bd  jmp     short loc_1800054C4
0x1800054bf  mov     ebx, 80070057h
0x1800054c4  movaps  xmm6, [rsp+88h+var_48]
0x1800054c9  mov     eax, ebx
0x1800054cb  add     rsp, 58h
0x1800054cf  pop     r15
0x1800054d1  pop     r14
0x1800054d3  pop     rdi
0x1800054d4  pop     rsi
0x1800054d5  pop     rbp
0x1800054d6  pop     rbx
0x1800054d7  retn
```
