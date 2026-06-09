# APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)

- ea: `0x18002b0cc`
- end: `0x18002b24a`
- name: `?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z`
- size: `382`
- prototype: `int(APP_OBJECT_UTILS *__hidden this, struct IExtensionContext *, struct ICommandParameterList *, const unsigned __int16 *, int *, int, int)`
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017a24`
- `0x180019948`
- `0x18001b350`
- `0x18001b7e4`
- `0x18001ca1c`
- `0x180020fd8`
- `0x180021658`
- `0x180025170`

## callees

- `0x180001fb0`
- `0x18002b0cc`
- `0x18002b564`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002b1a0`
- `msvcrt!_wcsicmp` at `0x18002b1b6`
- `msvcrt!_wcsicmp` at `0x18002b1a0`
- `msvcrt!_wcsicmp` at `0x18002b1b6`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_UTILS::PopBooleanParameter(
        APP_OBJECT_UTILS *this,
        struct IExtensionContext *a2,
        struct ICommandParameterList *a3,
        const unsigned __int16 *a4,
        int *a5,
        int a6,
        int a7)
{
  APP_OBJECT_UTILS *v10; // rcx
  int v11; // esi
  int v12; // eax
  unsigned int v13; // ebx
  _BYTE v15[32]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String1; // [rsp+60h] [rbp-A0h]
  int v17; // [rsp+68h] [rbp-98h]
  __int16 v18; // [rsp+6Ch] [rbp-94h]
  int v19; // [rsp+70h] [rbp-90h]
  __int128 v20; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v21; // [rsp+88h] [rbp-78h]
  __int16 v22; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[126]; // [rsp+92h] [rbp-6Eh] BYREF

  memset_0(v23, 0, sizeof(v23));
  v17 = 128;
  String1 = (wchar_t *)&v22;
  v18 = 256;
  v19 = 0;
  v11 = 1;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  if ( !a2 || !a5 )
  {
    v13 = -2147024809;
    if ( !a2 )
      goto LABEL_13;
LABEL_11:
    if ( v13 == 13 )
    {
      *((_QWORD *)&v20 + 1) = a4;
      *(_QWORD *)&v20 = L"BOOLEAN";
      v21 = L"true,false";
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a2 + 144LL))(
        a2,
        2147942487LL,
        3221226512LL,
        &v20,
        0);
    }
    goto LABEL_13;
  }
  v12 = APP_OBJECT_UTILS::PopParameter(v10, a2, a3, a4, (struct STRU *)v15, 0, a7);
  v13 = v12;
  if ( v12 >= 0 )
  {
    if ( _wcsicmp(String1, L"true") )
    {
      if ( _wcsicmp(String1, L"false") )
        goto LABEL_5;
      v11 = 0;
    }
    *a5 = v11;
    goto LABEL_11;
  }
  if ( v12 == -2147024774 )
LABEL_5:
    v13 = -2147024883;
LABEL_13:
  BUFFER::~BUFFER((BUFFER *)v15);
  return v13;
}

```

## disassembly

```asm
0x18002b0cc  mov     [rsp-8+arg_0], rbx
0x18002b0d1  push    rbp
0x18002b0d2  push    rsi
0x18002b0d3  push    rdi
0x18002b0d4  push    r14
0x18002b0d6  push    r15
0x18002b0d8  lea     rbp, [rsp-20h]
0x18002b0dd  sub     rsp, 120h
0x18002b0e4  mov     rax, cs:__security_cookie
0x18002b0eb  xor     rax, rsp
0x18002b0ee  mov     [rbp+40h+var_30], rax
0x18002b0f2  mov     r14, [rbp+40h+arg_20]
0x18002b0f6  lea     rcx, [rbp+40h+var_AE]; void *
0x18002b0fa  mov     rdi, rdx
0x18002b0fd  mov     rbx, r8
0x18002b100  xor     edx, edx; Val
0x18002b102  mov     r15, r9
0x18002b105  lea     r8d, [rdx+7Eh]; Size
0x18002b109  call    memset_0
0x18002b10e  lea     rax, [rbp+40h+var_B0]
0x18002b112  mov     [rsp+140h+var_D8], 80h
0x18002b11a  mov     [rsp+140h+String1], rax
0x18002b11f  xorps   xmm0, xmm0
0x18002b122  xor     eax, eax
0x18002b124  mov     [rsp+140h+var_D4], 100h
0x18002b12b  mov     [rsp+140h+var_D0], 0
0x18002b133  mov     esi, 1
0x18002b138  mov     [rbp+40h+var_B0], ax
0x18002b13c  mov     [rbp+40h+var_B8], rax
0x18002b140  movups  [rsp+140h+var_C8], xmm0
0x18002b145  test    rdi, rdi
0x18002b148  jz      short loc_18002B1C7
0x18002b14a  test    r14, r14
0x18002b14d  jz      short loc_18002B1C7
0x18002b14f  mov     eax, [rbp+40h+arg_30]
0x18002b155  mov     r9, r15; unsigned __int16 *
0x18002b158  mov     [rsp+140h+var_110], eax; int
0x18002b15c  mov     r8, rbx; struct ICommandParameterList *
0x18002b15f  lea     rax, [rsp+140h+var_100]
0x18002b164  mov     [rsp+140h+var_118], 0; int
0x18002b16c  mov     rdx, rdi; struct IExtensionContext *
0x18002b16f  mov     [rsp+140h+var_120], rax; struct STRU *
0x18002b174  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18002b179  mov     ebx, eax
0x18002b17b  test    eax, eax
0x18002b17d  jns     short loc_18002B194
0x18002b17f  cmp     eax, 8007007Ah
0x18002b184  jnz     loc_18002B21B
0x18002b18a  mov     ebx, 8007000Dh
0x18002b18f  jmp     loc_18002B21B
0x18002b194  mov     rcx, [rsp+140h+String1]; String1
0x18002b199  lea     rdx, aTrue; "true"
0x18002b1a0  call    cs:__imp__wcsicmp
0x18002b1a6  test    eax, eax
0x18002b1a8  jz      short loc_18002B1C2
0x18002b1aa  mov     rcx, [rsp+140h+String1]; String1
0x18002b1af  lea     rdx, aFalse; "false"
0x18002b1b6  call    cs:__imp__wcsicmp
0x18002b1bc  test    eax, eax
0x18002b1be  jnz     short loc_18002B18A
0x18002b1c0  xor     esi, esi
0x18002b1c2  mov     [r14], esi
0x18002b1c5  jmp     short loc_18002B1D1
0x18002b1c7  mov     ebx, 80070057h
0x18002b1cc  test    rdi, rdi
0x18002b1cf  jz      short loc_18002B21B
0x18002b1d1  cmp     ebx, 0Dh
0x18002b1d4  jnz     short loc_18002B21B
0x18002b1d6  lea     rax, aBoolean; "BOOLEAN"
0x18002b1dd  mov     qword ptr [rbp+40h+var_C8+8], r15
0x18002b1e1  mov     qword ptr [rsp+140h+var_C8], rax
0x18002b1e6  lea     r9, [rsp+140h+var_C8]
0x18002b1eb  lea     rax, aTrueFalse; "true,false"
0x18002b1f2  mov     dword ptr [rsp+140h+var_120], 0
0x18002b1fa  mov     [rbp+40h+var_B8], rax
0x18002b1fe  mov     edx, 80070057h
0x18002b203  mov     rax, [rdi]
0x18002b206  mov     r8d, 0C0000410h
0x18002b20c  mov     rcx, rdi
0x18002b20f  mov     rax, [rax+90h]
0x18002b216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b21b  lea     rcx, [rsp+140h+var_100]; this
0x18002b220  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b225  mov     eax, ebx
0x18002b227  mov     rcx, [rbp+40h+var_30]
0x18002b22b  xor     rcx, rsp; StackCookie
0x18002b22e  call    __security_check_cookie
0x18002b233  mov     rbx, [rsp+140h+arg_0]
0x18002b23b  add     rsp, 120h
0x18002b242  pop     r15
0x18002b244  pop     r14
0x18002b246  pop     rdi
0x18002b247  pop     rsi
0x18002b248  pop     rbp
0x18002b249  retn
```
