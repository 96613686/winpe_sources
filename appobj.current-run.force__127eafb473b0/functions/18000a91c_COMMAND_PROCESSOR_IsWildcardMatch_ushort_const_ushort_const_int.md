# COMMAND_PROCESSOR::IsWildcardMatch(ushort const *,ushort const *,int *)

- ea: `0x18000a91c`
- end: `0x18000ab44`
- name: `?IsWildcardMatch@COMMAND_PROCESSOR@@AEAAJPEBG0PEAH@Z`
- size: `552`
- prototype: `int(COMMAND_PROCESSOR *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008f00`
- `0x18000b400`
- `0x18000b7c0`

## callees

- `0x180001fb0`
- `0x180002610`
- `0x180002e90`
- `0x18000a91c`
- `0x180034cbe`
- `0x180034d00`

## import_xrefs

- `msvcrt!towupper` at `0x18000aa8d`
- `msvcrt!towupper` at `0x18000aa8d`
- `msvcrt!wcsstr` at `0x18000aa4b`
- `msvcrt!wcsstr` at `0x18000aa4b`
- `msvcrt!_wcsupr` at `0x18000aa03`
- `msvcrt!_wcsupr` at `0x18000aa03`
- `msvcrt!_wcsicmp` at `0x18000aae4`
- `msvcrt!_wcsicmp` at `0x18000aae4`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::IsWildcardMatch(
        COMMAND_PROCESSOR *this,
        const unsigned __int8 *a2,
        wint_t *a3,
        int *a4)
{
  unsigned int v7; // ebx
  int v8; // edi
  int v9; // r15d
  wchar_t *v10; // rsi
  wint_t v11; // cx
  int v12; // r14d
  const unsigned __int16 *v13; // r12
  wchar_t *v14; // rax
  __int64 v15; // rcx
  wint_t v16; // ax
  __int64 v17; // rdx
  _BYTE v20[32]; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t *SubStr; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+50h] [rbp-B0h]
  __int16 v23; // [rsp+54h] [rbp-ACh]
  unsigned int v24; // [rsp+58h] [rbp-A8h]
  _BYTE v25[32]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *String; // [rsp+80h] [rbp-80h]
  int v27; // [rsp+88h] [rbp-78h]
  __int16 v28; // [rsp+8Ch] [rbp-74h]
  int v29; // [rsp+90h] [rbp-70h]
  __int16 v30; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[510]; // [rsp+A2h] [rbp-5Eh] BYREF
  __int16 v32; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v33[510]; // [rsp+2A2h] [rbp+1A2h] BYREF

  memset_0(v31, 0, sizeof(v31));
  v23 = 256;
  v30 = 0;
  v7 = 0;
  SubStr = (wchar_t *)&v30;
  v24 = 0;
  v22 = 512;
  memset_0(v33, 0, sizeof(v33));
  v27 = 512;
  String = (wchar_t *)&v32;
  v8 = 0;
  v28 = 256;
  v29 = 0;
  v32 = 0;
  if ( a2 && a3 && a4 )
  {
    v9 = STRU::Copy((STRU *)v25, a2);
    if ( v9 >= 0 )
    {
      v10 = String;
      _wcsupr(String);
      v11 = *a3;
      if ( *a3 )
      {
        v12 = 0;
        v8 = 1;
        v13 = a3;
        while ( v11 )
        {
          if ( v11 == 42 )
          {
            if ( v7 )
            {
              v14 = wcsstr(v10, SubStr);
              if ( !v14 || v12 && v14 != v10 )
                goto LABEL_25;
              v15 = v7;
              v12 = 0;
              v7 = 0;
              v24 = 0;
              v10 = &v14[v15];
              *SubStr = 0;
            }
          }
          else
          {
            if ( v13 == a3 )
              v12 = 1;
            v16 = towupper(v11);
            v9 = STRU::Append((STRU *)v20, v16);
            if ( v9 < 0 )
              goto LABEL_27;
            v7 = v24;
          }
          v11 = *++v13;
        }
        if ( v7 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v10[v17] );
          if ( (unsigned int)v17 < v7 || _wcsicmp(SubStr, &v10[(unsigned int)v17 - (unsigned __int64)v7]) )
LABEL_25:
            v8 = 0;
        }
      }
      else
      {
        LOBYTE(v8) = v29 == 0;
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_27:
  *a4 = v8;
  BUFFER::~BUFFER((BUFFER *)v25);
  BUFFER::~BUFFER((BUFFER *)v20);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a91c  mov     [rsp-8+arg_0], rbx
0x18000a921  push    rbp
0x18000a922  push    rsi
0x18000a923  push    rdi
0x18000a924  push    r12
0x18000a926  push    r13
0x18000a928  push    r14
0x18000a92a  push    r15
0x18000a92c  lea     rbp, [rsp-3B0h]
0x18000a934  sub     rsp, 4B0h
0x18000a93b  mov     rax, cs:__security_cookie
0x18000a942  xor     rax, rsp
0x18000a945  mov     [rbp+3E0h+var_40], rax
0x18000a94c  mov     r13, r8
0x18000a94f  mov     [rsp+4E0h+var_4C0], r9
0x18000a954  mov     rsi, rdx
0x18000a957  lea     rcx, [rbp+3E0h+var_43E]; void *
0x18000a95b  mov     r14d, 1FEh
0x18000a961  xor     edx, edx; Val
0x18000a963  mov     r8d, r14d; Size
0x18000a966  mov     r15, r9
0x18000a969  call    memset_0
0x18000a96e  xor     r12d, r12d
0x18000a971  mov     [rsp+4E0h+var_48C], 100h
0x18000a978  lea     rax, [rbp+3E0h+var_440]
0x18000a97c  mov     [rbp+3E0h+var_440], r12w
0x18000a981  mov     ebx, r12d
0x18000a984  mov     [rsp+4E0h+SubStr], rax
0x18000a989  lea     edi, [r14+2]
0x18000a98d  mov     [rsp+4E0h+var_488], ebx
0x18000a991  mov     r8d, r14d; Size
0x18000a994  mov     [rsp+4E0h+var_490], edi
0x18000a998  xor     edx, edx; Val
0x18000a99a  lea     rcx, [rbp+3E0h+var_23E]; void *
0x18000a9a1  call    memset_0
0x18000a9a6  mov     [rbp+3E0h+var_458], edi
0x18000a9a9  lea     rax, [rbp+3E0h+var_240]
0x18000a9b0  mov     [rbp+3E0h+String], rax
0x18000a9b4  mov     edi, r12d
0x18000a9b7  mov     [rbp+3E0h+var_454], 100h
0x18000a9bd  mov     [rbp+3E0h+var_450], r12d
0x18000a9c1  mov     [rbp+3E0h+var_240], r12w
0x18000a9c9  test    rsi, rsi
0x18000a9cc  jz      loc_18000AAF6
0x18000a9d2  test    r13, r13
0x18000a9d5  jz      loc_18000AAF6
0x18000a9db  test    r15, r15
0x18000a9de  jz      loc_18000AAF6
0x18000a9e4  mov     rdx, rsi; unsigned __int16 *
0x18000a9e7  lea     rcx, [rsp+4E0h+var_480]; this
0x18000a9ec  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a9f1  mov     r15d, eax
0x18000a9f4  test    eax, eax
0x18000a9f6  js      loc_18000AAFC
0x18000a9fc  mov     rsi, [rbp+3E0h+String]
0x18000aa00  mov     rcx, rsi; String
0x18000aa03  call    cs:__imp__wcsupr
0x18000aa09  movzx   ecx, word ptr [r13+0]; C
0x18000aa0e  test    cx, cx
0x18000aa11  jnz     short loc_18000AA20
0x18000aa13  cmp     [rbp+3E0h+var_450], r12d
0x18000aa17  setz    dil
0x18000aa1b  jmp     loc_18000AAFC
0x18000aa20  mov     eax, 1
0x18000aa25  mov     r14d, r12d
0x18000aa28  mov     edi, eax
0x18000aa2a  mov     r12, r13
0x18000aa2d  xor     r8d, r8d
0x18000aa30  test    cx, cx
0x18000aa33  jz      loc_18000AABE
0x18000aa39  cmp     cx, 2Ah ; '*'
0x18000aa3d  jnz     short loc_18000AA86
0x18000aa3f  test    ebx, ebx
0x18000aa41  jz      short loc_18000AAB0
0x18000aa43  mov     rdx, [rsp+4E0h+SubStr]; SubStr
0x18000aa48  mov     rcx, rsi; Str
0x18000aa4b  call    cs:__imp_wcsstr
0x18000aa51  xor     r8d, r8d
0x18000aa54  test    rax, rax
0x18000aa57  jz      loc_18000AAF1
0x18000aa5d  test    r14d, r14d
0x18000aa60  jz      short loc_18000AA6B
0x18000aa62  cmp     rax, rsi
0x18000aa65  jnz     loc_18000AAF1
0x18000aa6b  mov     ecx, ebx
0x18000aa6d  mov     r14d, r8d
0x18000aa70  mov     ebx, r8d
0x18000aa73  mov     [rsp+4E0h+var_488], ebx
0x18000aa77  lea     rsi, [rax+rcx*2]
0x18000aa7b  mov     rcx, [rsp+4E0h+SubStr]
0x18000aa80  mov     [rcx], r8w
0x18000aa84  jmp     short loc_18000AAAE
0x18000aa86  cmp     r12, r13
0x18000aa89  cmovz   r14d, eax
0x18000aa8d  call    cs:__imp_towupper
0x18000aa93  movzx   edx, ax; unsigned __int16
0x18000aa96  lea     rcx, [rsp+4E0h+var_4B8]; this
0x18000aa9b  call    ?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x18000aaa0  xor     r8d, r8d
0x18000aaa3  mov     r15d, eax
0x18000aaa6  test    eax, eax
0x18000aaa8  js      short loc_18000AAFC
0x18000aaaa  mov     ebx, [rsp+4E0h+var_488]
0x18000aaae  mov     eax, edi
0x18000aab0  add     r12, 2
0x18000aab4  movzx   ecx, word ptr [r12]
0x18000aab9  jmp     loc_18000AA30
0x18000aabe  test    ebx, ebx
0x18000aac0  jz      short loc_18000AAFC
0x18000aac2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000aac6  inc     rdx
0x18000aac9  cmp     [rsi+rdx*2], r8w
0x18000aace  jnz     short loc_18000AAC6
0x18000aad0  cmp     edx, ebx
0x18000aad2  jb      short loc_18000AAF1
0x18000aad4  mov     rcx, [rsp+4E0h+SubStr]; String1
0x18000aad9  mov     edx, edx
0x18000aadb  mov     eax, ebx
0x18000aadd  sub     rdx, rax
0x18000aae0  lea     rdx, [rsi+rdx*2]; String2
0x18000aae4  call    cs:__imp__wcsicmp
0x18000aaea  xor     r8d, r8d
0x18000aaed  test    eax, eax
0x18000aaef  jz      short loc_18000AAFC
0x18000aaf1  mov     edi, r8d
0x18000aaf4  jmp     short loc_18000AAFC
0x18000aaf6  mov     r15d, 80070057h
0x18000aafc  mov     rax, [rsp+4E0h+var_4C0]
0x18000ab01  lea     rcx, [rsp+4E0h+var_480]; this
0x18000ab06  mov     [rax], edi
0x18000ab08  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000ab0d  lea     rcx, [rsp+4E0h+var_4B8]; this
0x18000ab12  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000ab17  mov     eax, r15d
0x18000ab1a  mov     rcx, [rbp+3E0h+var_40]
0x18000ab21  xor     rcx, rsp; StackCookie
0x18000ab24  call    __security_check_cookie
0x18000ab29  mov     rbx, [rsp+4E0h+arg_0]
0x18000ab31  add     rsp, 4B0h
0x18000ab38  pop     r15
0x18000ab3a  pop     r14
0x18000ab3c  pop     r13
0x18000ab3e  pop     r12
0x18000ab40  pop     rdi
0x18000ab41  pop     rsi
0x18000ab42  pop     rbp
0x18000ab43  retn
```
