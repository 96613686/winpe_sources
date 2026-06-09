# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x180018e00`
- end: `0x180018f68`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `360`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800180bc`
- `0x1800194e0`
- `0x1800195d0`

## callees

- `0x180006244`
- `0x180018050`
- `0x180018e00`
- `0x180019098`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `msvcp110_win!?unshift@?$codecvt@DDH@std@@QEBAHAEAHPEAD1AEAPEAD@Z` at `0x180018e99`
- `msvcp110_win!?unshift@?$codecvt@DDH@std@@QEBAHAEAHPEAD1AEAPEAD@Z` at `0x180018e99`
- `msvcrt!fwrite` at `0x180018efd`
- `msvcrt!fwrite` at `0x180018efd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall std::filebuf::_Endwrite(__int64 a1)
{
  void **v3; // r10
  unsigned __int64 v4; // r9
  void **v5; // rdx
  void **v6; // r8
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  char v10; // bl
  void **v11; // rax
  signed __int64 v12; // rdi
  void **v13; // rcx
  void **v14; // [rsp+30h] [rbp-38h] BYREF
  void *Buffer[3]; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int64 v16; // [rsp+50h] [rbp-18h]

  if ( !*(_QWORD *)(a1 + 120) || !*(_BYTE *)(a1 + 129) )
    return 1;
  v14 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFFFFFFLL) == -1 )
    return 0;
  std::string::string(Buffer);
LABEL_6:
  v3 = (void **)Buffer[0];
  v4 = v16;
  while ( 1 )
  {
    v5 = Buffer;
    if ( v4 >= 0x10 )
      v5 = v3;
    v6 = Buffer;
    if ( v4 >= 0x10 )
      v6 = v3;
    v7 = std::codecvt<char,char,int>::unshift(
           *(_QWORD *)(a1 + 120),
           a1 + 132,
           v6,
           (char *)v5 + (unsigned __int64)Buffer[2],
           &v14);
    if ( !v7 )
    {
      *(_BYTE *)(a1 + 129) = 0;
      goto LABEL_16;
    }
    v9 = v7 - 1;
    if ( v9 )
      break;
LABEL_16:
    v11 = Buffer;
    v3 = (void **)Buffer[0];
    v4 = v16;
    if ( v16 >= 0x10 )
      v11 = (void **)Buffer[0];
    v12 = (char *)v14 - (char *)v11;
    if ( v14 != v11 )
    {
      v13 = Buffer;
      if ( v16 >= 0x10 )
        v13 = (void **)Buffer[0];
      if ( v12 != fwrite(v13, 1u, (char *)v14 - (char *)v11, *(FILE **)(a1 + 144)) )
        goto LABEL_14;
      v4 = v16;
      v3 = (void **)Buffer[0];
    }
    if ( !*(_BYTE *)(a1 + 129) )
      goto LABEL_26;
    if ( !v12 )
    {
      std::string::append(Buffer, 8, 0);
      goto LABEL_6;
    }
  }
  if ( v9 != 2 )
  {
LABEL_14:
    v10 = 0;
    goto LABEL_27;
  }
LABEL_26:
  v10 = 1;
LABEL_27:
  LOBYTE(v8) = 1;
  std::string::_Tidy(Buffer, v8, 0);
  return v10;
}

```

## disassembly

```asm
0x180018e00  push    rbp
0x180018e02  push    rbx
0x180018e03  push    rsi
0x180018e04  push    rdi
0x180018e05  mov     rbp, rsp
0x180018e08  sub     rsp, 68h
0x180018e0c  mov     rax, cs:__security_cookie
0x180018e13  xor     rax, rsp
0x180018e16  mov     [rbp+var_10], rax
0x180018e1a  mov     rbx, rcx
0x180018e1d  cmp     qword ptr [rcx+78h], 0
0x180018e22  jz      loc_180018F50
0x180018e28  cmp     byte ptr [rcx+81h], 0
0x180018e2f  jz      loc_180018F50
0x180018e35  mov     [rbp+var_38], 0
0x180018e3d  mov     rax, [rcx]
0x180018e40  or      edx, 0FFFFFFFFh
0x180018e43  mov     rax, [rax+18h]
0x180018e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e4c  cmp     eax, 0FFFFFFFFh
0x180018e4f  jnz     short loc_180018E58
0x180018e51  xor     al, al
0x180018e53  jmp     loc_180018F52
0x180018e58  lea     rcx, [rbp+Buffer]
0x180018e5c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x180018e61  nop
0x180018e62  mov     r10, [rbp+Buffer]
0x180018e66  mov     r9, [rbp+var_18]
0x180018e6a  lea     rdx, [rbp+Buffer]
0x180018e6e  cmp     r9, 10h
0x180018e72  cmovnb  rdx, r10
0x180018e76  mov     r9, [rbp+var_20]
0x180018e7a  lea     r8, [rbp+Buffer]
0x180018e7e  cmovnb  r8, r10
0x180018e82  add     r9, rdx
0x180018e85  lea     rax, [rbp+var_38]
0x180018e89  mov     [rsp+68h+var_48], rax
0x180018e8e  lea     rdx, [rbx+84h]
0x180018e95  mov     rcx, [rbx+78h]
0x180018e99  call    cs:__imp_?unshift@?$codecvt@DDH@std@@QEBAHAEAHPEAD1AEAPEAD@Z; std::codecvt<char,char,int>::unshift(int &,char *,char *,char * &)
0x180018ea0  nop     dword ptr [rax+rax+00h]
0x180018ea5  test    eax, eax
0x180018ea7  jz      short loc_180018EBE
0x180018ea9  sub     eax, 1
0x180018eac  jz      short loc_180018EC5
0x180018eae  cmp     eax, 2
0x180018eb1  jz      loc_180018F3C
0x180018eb7  xor     ebx, ebx
0x180018eb9  jmp     loc_180018F3E
0x180018ebe  mov     byte ptr [rbx+81h], 0
0x180018ec5  lea     rax, [rbp+Buffer]
0x180018ec9  mov     r10, [rbp+Buffer]
0x180018ecd  mov     r9, [rbp+var_18]
0x180018ed1  cmp     r9, 10h
0x180018ed5  cmovnb  rax, r10
0x180018ed9  mov     rdi, [rbp+var_38]
0x180018edd  sub     rdi, rax
0x180018ee0  jz      short loc_180018F16
0x180018ee2  lea     rcx, [rbp+Buffer]
0x180018ee6  cmp     r9, 10h
0x180018eea  cmovnb  rcx, r10; Buffer
0x180018eee  mov     r9, [rbx+90h]; Stream
0x180018ef5  mov     r8, rdi; ElementCount
0x180018ef8  mov     edx, 1; ElementSize
0x180018efd  call    cs:__imp_fwrite
0x180018f04  nop     dword ptr [rax+rax+00h]
0x180018f09  cmp     rdi, rax
0x180018f0c  jnz     short loc_180018EB7
0x180018f0e  mov     r9, [rbp+var_18]
0x180018f12  mov     r10, [rbp+Buffer]
0x180018f16  cmp     byte ptr [rbx+81h], 0
0x180018f1d  jz      short loc_180018F3C
0x180018f1f  test    rdi, rdi
0x180018f22  jnz     loc_180018E6A
0x180018f28  xor     r8d, r8d
0x180018f2b  lea     edx, [rdi+8]
0x180018f2e  lea     rcx, [rbp+Buffer]
0x180018f32  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x180018f37  jmp     loc_180018E62
0x180018f3c  mov     bl, 1
0x180018f3e  xor     r8d, r8d
0x180018f41  mov     dl, 1
0x180018f43  lea     rcx, [rbp+Buffer]
0x180018f47  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180018f4c  mov     al, bl
0x180018f4e  jmp     short loc_180018F52
0x180018f50  mov     al, 1
0x180018f52  mov     rcx, [rbp+var_10]
0x180018f56  xor     rcx, rsp; StackCookie
0x180018f59  call    __security_check_cookie
0x180018f5e  add     rsp, 68h
0x180018f62  pop     rdi
0x180018f63  pop     rsi
0x180018f64  pop     rbx
0x180018f65  pop     rbp
0x180018f66  retn
```
