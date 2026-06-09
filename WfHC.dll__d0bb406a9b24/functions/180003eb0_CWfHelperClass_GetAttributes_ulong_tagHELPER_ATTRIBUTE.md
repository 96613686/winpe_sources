# CWfHelperClass::GetAttributes(ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x180003eb0`
- end: `0x180004062`
- name: `?GetAttributes@CWfHelperClass@@UEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(CWfHelperClass *this, unsigned int *, LPVOID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003eb0`
- `0x180005c60`
- `0x18000c566`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003fc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003fc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000402f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000402f`

## pseudocode

```c
__int64 __fastcall CWfHelperClass::GetAttributes(CWfHelperClass *this, unsigned int *a2, LPVOID *a3)
{
  __int128 v5; // xmm6
  __int64 result; // rax
  __int64 v7; // rbx
  struct tagHELPER_ATTRIBUTE *v8; // rax
  _QWORD *v9; // r15
  const unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // rbp
  unsigned __int16 *v14; // rax
  __int128 Buf2; // [rsp+20h] [rbp-48h] BYREF
  __int128 Buf1; // [rsp+30h] [rbp-38h] BYREF

  v5 = *((_OWORD *)this + 8);
  Buf1 = v5;
  if ( !a2 || !a3 || *a3 || *a2 )
    return 2147942487LL;
  Buf2 = 0;
  if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
  {
    *a3 = 0;
    result = 0;
    *a2 = 0;
    return result;
  }
  v7 = 144;
  v8 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
  *a3 = v8;
  if ( !v8 )
    return 2147942414LL;
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
    v12 = -2147024809;
    if ( v11 )
      v12 = 0;
    v13 = 259 - v11;
    if ( v11 )
    {
      v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v13 + 2);
      *v9 = v14;
      if ( v14 )
      {
        v12 = StringCchCopyW(v14, v13 + 1, L"rootcauseid");
        if ( v12 >= 0 )
        {
          *((_OWORD *)*a3 + 1) = v5;
          *a2 = 1;
          return (unsigned int)v12;
        }
      }
      else
      {
        v12 = -2147024882;
      }
    }
  }
  else
  {
    v12 = -2147024809;
  }
  if ( *a3 )
  {
    CoTaskMemFree(*(LPVOID *)*a3);
    CoTaskMemFree(*a3);
    *a3 = 0;
    *a2 = 0;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180003eb0  push    rbx
0x180003eb2  push    rdi
0x180003eb3  push    r14
0x180003eb5  sub     rsp, 50h
0x180003eb9  movaps  [rsp+68h+var_28], xmm6
0x180003ebe  mov     rdi, r8
0x180003ec1  mov     r14, rdx
0x180003ec4  movups  xmm6, xmmword ptr [rcx+80h]
0x180003ecb  movaps  [rsp+68h+Buf1], xmm6
0x180003ed0  test    rdx, rdx
0x180003ed3  jz      loc_18000404F
0x180003ed9  test    r8, r8
0x180003edc  jz      loc_18000404F
0x180003ee2  cmp     qword ptr [r8], 0
0x180003ee6  jnz     loc_18000404F
0x180003eec  cmp     dword ptr [rdx], 0
0x180003eef  jnz     loc_18000404F
0x180003ef5  xorps   xmm0, xmm0
0x180003ef8  mov     [rsp+68h+arg_8], rsi
0x180003efd  mov     r8d, 10h; Size
0x180003f03  lea     rdx, [rsp+68h+Buf2]; Buf2
0x180003f08  lea     rcx, [rsp+68h+Buf1]; Buf1
0x180003f0d  movups  [rsp+68h+Buf2], xmm0
0x180003f12  call    memcmp_0
0x180003f17  test    eax, eax
0x180003f19  jnz     short loc_180003F29
0x180003f1b  xor     esi, esi
0x180003f1d  mov     ebx, esi
0x180003f1f  mov     [rdi], rsi
0x180003f22  mov     eax, ebx
0x180003f24  mov     [r14], esi
0x180003f27  jmp     short loc_180003F43
0x180003f29  mov     ebx, 90h
0x180003f2e  mov     ecx, ebx; cb
0x180003f30  call    cs:__imp_CoTaskMemAlloc
0x180003f36  mov     [rdi], rax
0x180003f39  test    rax, rax
0x180003f3c  jnz     short loc_180003F56
0x180003f3e  mov     eax, 8007000Eh
0x180003f43  mov     rsi, [rsp+68h+arg_8]
0x180003f48  movaps  xmm6, [rsp+68h+var_28]
0x180003f4d  add     rsp, 50h
0x180003f51  pop     r14
0x180003f53  pop     rdi
0x180003f54  pop     rbx
0x180003f55  retn
0x180003f56  mov     [rsp+68h+arg_10], r15
0x180003f5e  xchg    ax, ax
0x180003f60  mov     byte ptr [rax], 0
0x180003f63  lea     rax, [rax+1]
0x180003f67  sub     rbx, 1
0x180003f6b  jnz     short loc_180003F60
0x180003f6d  mov     rax, [rdi]
0x180003f70  xor     esi, esi
0x180003f72  mov     [rsp+68h+arg_0], rbp
0x180003f77  mov     dword ptr [rax+8], 0Bh
0x180003f7e  mov     r15, [rdi]
0x180003f81  test    r15, r15
0x180003f84  jz      loc_180004016
0x180003f8a  mov     ebp, 103h
0x180003f8f  lea     rax, aRootcauseid; "rootcauseid"
0x180003f96  mov     ecx, ebp
0x180003f98  cmp     [rax], si
0x180003f9b  jz      short loc_180003FA7
0x180003f9d  add     rax, 2
0x180003fa1  sub     rcx, 1
0x180003fa5  jnz     short loc_180003F98
0x180003fa7  test    rcx, rcx
0x180003faa  mov     ebx, 80070057h
0x180003faf  cmovnz  ebx, esi
0x180003fb2  sub     rbp, rcx
0x180003fb5  test    rcx, rcx
0x180003fb8  cmovz   rbp, rsi
0x180003fbc  jz      short loc_18000401B
0x180003fbe  lea     rcx, ds:2[rbp*2]; cb
0x180003fc6  call    cs:__imp_CoTaskMemAlloc
0x180003fcc  mov     [r15], rax
0x180003fcf  test    rax, rax
0x180003fd2  jnz     short loc_180003FDB
0x180003fd4  mov     ebx, 8007000Eh
0x180003fd9  jmp     short loc_18000401B
0x180003fdb  lea     rdx, [rbp+1]; unsigned __int64
0x180003fdf  mov     rcx, rax; unsigned __int16 *
0x180003fe2  lea     r8, aRootcauseid; "rootcauseid"
0x180003fe9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003fee  mov     ebx, eax
0x180003ff0  test    eax, eax
0x180003ff2  js      short loc_18000401B
0x180003ff4  mov     rax, [rdi]
0x180003ff7  mov     rbp, [rsp+68h+arg_0]
0x180003ffc  mov     r15, [rsp+68h+arg_10]
0x180004004  movups  xmmword ptr [rax+10h], xmm6
0x180004008  mov     dword ptr [r14], 1
0x18000400f  mov     eax, ebx
0x180004011  jmp     loc_180003F43
0x180004016  mov     ebx, 80070057h
0x18000401b  mov     rcx, [rdi]
0x18000401e  test    rcx, rcx
0x180004021  jz      short loc_18000403B
0x180004023  mov     rcx, [rcx]; pv
0x180004026  call    cs:__imp_CoTaskMemFree
0x18000402c  mov     rcx, [rdi]; pv
0x18000402f  call    cs:__imp_CoTaskMemFree
0x180004035  mov     [rdi], rsi
0x180004038  mov     [r14], esi
0x18000403b  mov     rbp, [rsp+68h+arg_0]
0x180004040  mov     eax, ebx
0x180004042  mov     r15, [rsp+68h+arg_10]
0x18000404a  jmp     loc_180003F43
0x18000404f  movaps  xmm6, [rsp+68h+var_28]
0x180004054  mov     eax, 80070057h
0x180004059  add     rsp, 50h
0x18000405d  pop     r14
0x18000405f  pop     rdi
0x180004060  pop     rbx
0x180004061  retn
```
