# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)

- ea: `0x180008ec8`
- end: `0x180009008`
- name: `?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ`
- size: `320`
- prototype: `__int64(__int64, const wchar_t *, ...)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008bbc`
- `0x18000ab20`
- `0x18000c020`
- `0x18000c2b0`
- `0x18000c4a0`

## callees

- `0x1800020e8`
- `0x180008ec8`
- `0x180009424`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180008f99`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180008f99`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x180008f20`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x180008f20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fc3`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
        __int64 a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 v4; // rcx
  unsigned __int64 *v5; // r15
  unsigned __int64 *v6; // rdi
  int v7; // ebx
  wchar_t *v8; // r14
  unsigned __int64 v9; // rbp
  size_t v10; // rbp
  int v11; // eax
  __int64 v12; // rax
  __int64 v14[9]; // [rsp+20h] [rbp-48h] BYREF
  va_list Args; // [rsp+80h] [rbp+18h] BYREF

  va_start(Args, a2);
  v14[0] = 0;
  v4 = 32;
  v5 = (unsigned __int64 *)(a1 + 16);
  v6 = (unsigned __int64 *)(a1 + 16);
  while ( 1 )
  {
    v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(a1, v4);
    if ( v7 < 0 )
      break;
    v8 = *(wchar_t **)a1;
    v6 = (unsigned __int64 *)(a1 + 16);
    v9 = *(_QWORD *)(a1 + 16);
    _o__set_errno(0);
    if ( v9 )
    {
      if ( v9 > 0x7FFFFFFF )
      {
        *v8 = 0;
LABEL_18:
        v7 = -2147024809;
LABEL_19:
        if ( v7 >= 0 )
        {
          v12 = -1;
          goto LABEL_23;
        }
        break;
      }
      v10 = v9 - 1;
      v11 = vsnwprintf(v8, v10, a2, Args);
      if ( v11 < 0 || v11 > v10 )
      {
        v7 = -2147024774;
        v8[v10] = 0;
      }
      else
      {
        v7 = 0;
        if ( v11 == v10 )
          v8[v10] = 0;
      }
    }
    else
    {
      v7 = -2147024809;
    }
    if ( v7 != -2147024774 )
      goto LABEL_19;
    LODWORD(v14[0]) = 0;
    _o__get_errno(v14);
    if ( LODWORD(v14[0]) == 22 )
      goto LABEL_18;
    v4 = *v6 + 32;
    if ( v4 < *v6 )
    {
      v7 = -2147024362;
      break;
    }
  }
  if ( *(_QWORD *)a1 )
  {
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
  }
  else
  {
    v5 = v6;
  }
  *v5 = 0;
  v12 = 0;
LABEL_23:
  *(_QWORD *)(a1 + 8) = v12;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008ec8  mov     rax, rsp
0x180008ecb  mov     [rax+10h], rdx
0x180008ecf  mov     [rax+18h], r8
0x180008ed3  mov     [rax+20h], r9
0x180008ed7  push    rbx
0x180008ed8  push    rbp
0x180008ed9  push    rsi
0x180008eda  push    rdi
0x180008edb  push    r12
0x180008edd  push    r14
0x180008edf  push    r15
0x180008ee1  sub     rsp, 30h
0x180008ee5  mov     rsi, rcx
0x180008ee8  mov     qword ptr [rax-48h], 0
0x180008ef0  mov     r12, rdx
0x180008ef3  mov     ecx, 20h ; ' '
0x180008ef8  lea     r15, [rsi+10h]
0x180008efc  mov     rdi, r15
0x180008eff  mov     rdx, rcx
0x180008f02  mov     rcx, rsi
0x180008f05  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180008f0a  mov     ebx, eax
0x180008f0c  test    eax, eax
0x180008f0e  js      loc_180008FBB
0x180008f14  mov     r14, [rsi]
0x180008f17  lea     rdi, [rsi+10h]
0x180008f1b  mov     rbp, [rdi]
0x180008f1e  xor     ecx, ecx
0x180008f20  call    cs:__imp__o__set_errno
0x180008f26  test    rbp, rbp
0x180008f29  jz      short loc_180008F7A
0x180008f2b  cmp     rbp, 7FFFFFFFh
0x180008f32  ja      loc_180008FD2
0x180008f38  dec     rbp
0x180008f3b  lea     r9, [rsp+68h+Args]; Args
0x180008f43  mov     rdx, rbp; BufferCount
0x180008f46  mov     r8, r12; Format
0x180008f49  mov     rcx, r14; Buffer
0x180008f4c  call    _vsnwprintf
0x180008f51  test    eax, eax
0x180008f53  js      short loc_180008F6C
0x180008f55  cdqe
0x180008f57  cmp     rax, rbp
0x180008f5a  ja      short loc_180008F6C
0x180008f5c  xor     ebx, ebx
0x180008f5e  cmp     rax, rbp
0x180008f61  jnz     short loc_180008F84
0x180008f63  xor     eax, eax
0x180008f65  mov     [r14+rbp*2], ax
0x180008f6a  jmp     short loc_180008F84
0x180008f6c  xor     eax, eax
0x180008f6e  mov     ebx, 8007007Ah
0x180008f73  mov     [r14+rbp*2], ax
0x180008f78  jmp     short loc_180008F84
0x180008f7a  mov     ebx, 80070057h
0x180008f7f  test    rbp, rbp
0x180008f82  jnz     short loc_180008FD2
0x180008f84  cmp     ebx, 8007007Ah
0x180008f8a  jnz     short loc_180008FDD
0x180008f8c  lea     rcx, [rsp+68h+var_48]
0x180008f91  mov     dword ptr [rsp+68h+var_48], 0
0x180008f99  call    cs:__imp__o__get_errno
0x180008f9f  cmp     dword ptr [rsp+68h+var_48], 16h
0x180008fa4  jz      short loc_180008FD8
0x180008fa6  mov     rax, [rdi]
0x180008fa9  lea     rcx, [rax+20h]
0x180008fad  cmp     rcx, rax
0x180008fb0  jnb     loc_180008EFF
0x180008fb6  mov     ebx, 80070216h
0x180008fbb  mov     rcx, [rsi]; pv
0x180008fbe  test    rcx, rcx
0x180008fc1  jz      short loc_180008FE7
0x180008fc3  call    cs:__imp_CoTaskMemFree
0x180008fc9  mov     qword ptr [rsi], 0
0x180008fd0  jmp     short loc_180008FEA
0x180008fd2  xor     eax, eax
0x180008fd4  mov     [r14], ax
0x180008fd8  mov     ebx, 80070057h
0x180008fdd  test    ebx, ebx
0x180008fdf  js      short loc_180008FBB
0x180008fe1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008fe5  jmp     short loc_180008FF3
0x180008fe7  mov     r15, rdi
0x180008fea  mov     qword ptr [r15], 0
0x180008ff1  xor     eax, eax
0x180008ff3  mov     [rsi+8], rax
0x180008ff7  mov     eax, ebx
0x180008ff9  add     rsp, 30h
0x180008ffd  pop     r15
0x180008fff  pop     r14
0x180009001  pop     r12
0x180009003  pop     rdi
0x180009004  pop     rsi
0x180009005  pop     rbp
0x180009006  pop     rbx
0x180009007  retn
```
