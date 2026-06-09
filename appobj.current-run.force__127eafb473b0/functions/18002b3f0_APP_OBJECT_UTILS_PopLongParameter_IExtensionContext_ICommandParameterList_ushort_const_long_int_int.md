# APP_OBJECT_UTILS::PopLongParameter(IExtensionContext *,ICommandParameterList *,ushort const *,long *,int,int)

- ea: `0x18002b3f0`
- end: `0x18002b55b`
- name: `?PopLongParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAJHH@Z`
- size: `363`
- prototype: `int(APP_OBJECT_UTILS *__hidden this, struct IExtensionContext *, struct ICommandParameterList *, const unsigned __int16 *, int *, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b250`

## callees

- `0x180001fb0`
- `0x18002b3f0`
- `0x18002b564`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcstol` at `0x18002b4b5`
- `msvcrt!wcstol` at `0x18002b4b5`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_UTILS::PopLongParameter(
        APP_OBJECT_UTILS *this,
        struct IExtensionContext *a2,
        struct ICommandParameterList *a3,
        const unsigned __int16 *a4,
        int *a5)
{
  APP_OBJECT_UTILS *v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  wchar_t *v11; // r14
  int v12; // eax
  wchar_t *EndPtr; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v15; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String; // [rsp+78h] [rbp-88h]
  int v18; // [rsp+80h] [rbp-80h]
  __int16 v19; // [rsp+84h] [rbp-7Ch]
  int v20; // [rsp+88h] [rbp-78h]
  __int16 v21; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[126]; // [rsp+92h] [rbp-6Eh] BYREF

  memset_0(v22, 0, sizeof(v22));
  v18 = 128;
  String = (wchar_t *)&v21;
  v19 = 256;
  v20 = 0;
  v21 = 0;
  EndPtr = 0;
  v15 = 0;
  if ( !a2 || !a5 )
  {
    v10 = -2147024809;
    if ( !a2 )
      goto LABEL_13;
    goto LABEL_11;
  }
  v9 = APP_OBJECT_UTILS::PopParameter(v8, a2, a3, a4, (struct STRU *)v16, 0, 1);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( v9 == -2147024774 )
      v10 = -2147024883;
LABEL_11:
    if ( v10 == -2147024883 )
      goto LABEL_12;
    goto LABEL_13;
  }
  v11 = String;
  v12 = wcstol(String, &EndPtr, 10);
  if ( (unsigned int)(v12 + 0x7FFFFFFF) > 0xFFFFFFFD || EndPtr != &v11[v20] )
  {
    v10 = -2147024883;
LABEL_12:
    *(_QWORD *)&v15 = a4;
    *((_QWORD *)&v15 + 1) = L"[-2147483648,2147483647]";
    (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a2 + 144LL))(
      a2,
      2147942487LL,
      3221226513LL,
      &v15,
      0);
    goto LABEL_13;
  }
  *a5 = v12;
LABEL_13:
  BUFFER::~BUFFER((BUFFER *)v16);
  return v10;
}

```

## disassembly

```asm
0x18002b3f0  mov     [rsp-8+arg_0], rbx
0x18002b3f5  push    rbp
0x18002b3f6  push    rsi
0x18002b3f7  push    rdi
0x18002b3f8  push    r14
0x18002b3fa  push    r15
0x18002b3fc  lea     rbp, [rsp-20h]
0x18002b401  sub     rsp, 120h
0x18002b408  mov     rax, cs:__security_cookie
0x18002b40f  xor     rax, rsp
0x18002b412  mov     [rbp+40h+var_30], rax
0x18002b416  mov     rsi, [rbp+40h+arg_20]
0x18002b41a  lea     rcx, [rbp+40h+var_AE]; void *
0x18002b41e  mov     rdi, rdx
0x18002b421  mov     rbx, r8
0x18002b424  xor     edx, edx; Val
0x18002b426  mov     r15, r9
0x18002b429  lea     r8d, [rdx+7Eh]; Size
0x18002b42d  call    memset_0
0x18002b432  lea     rax, [rbp+40h+var_B0]
0x18002b436  mov     [rbp+40h+var_C0], 80h
0x18002b43d  mov     [rsp+140h+String], rax
0x18002b442  xorps   xmm0, xmm0
0x18002b445  xor     eax, eax
0x18002b447  mov     [rbp+40h+var_BC], 100h
0x18002b44d  mov     [rbp+40h+var_B8], 0
0x18002b454  mov     [rbp+40h+var_B0], ax
0x18002b458  mov     [rsp+140h+EndPtr], rax
0x18002b45d  movups  [rsp+140h+var_F8], xmm0
0x18002b462  test    rdi, rdi
0x18002b465  jz      short loc_18002B4DF
0x18002b467  test    rsi, rsi
0x18002b46a  jz      short loc_18002B4DF
0x18002b46c  mov     [rsp+140h+var_110], 1; int
0x18002b474  mov     r9, r15; unsigned __int16 *
0x18002b477  mov     [rsp+140h+var_118], eax; int
0x18002b47b  mov     r8, rbx; struct ICommandParameterList *
0x18002b47e  lea     rax, [rsp+140h+var_E8]
0x18002b483  mov     rdx, rdi; struct IExtensionContext *
0x18002b486  mov     [rsp+140h+var_120], rax; struct STRU *
0x18002b48b  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18002b490  mov     ebx, eax
0x18002b492  test    eax, eax
0x18002b494  jns     short loc_18002B4A2
0x18002b496  cmp     eax, 8007007Ah
0x18002b49b  jnz     short loc_18002B4E9
0x18002b49d  lea     ebx, [rax-6Dh]
0x18002b4a0  jmp     short loc_18002B4E9
0x18002b4a2  mov     r14, [rsp+140h+String]
0x18002b4a7  lea     rdx, [rsp+140h+EndPtr]; EndPtr
0x18002b4ac  mov     rcx, r14; String
0x18002b4af  mov     r8d, 0Ah; Radix
0x18002b4b5  call    cs:__imp_wcstol
0x18002b4bb  lea     ecx, [rax+7FFFFFFFh]
0x18002b4c1  cmp     ecx, 0FFFFFFFDh
0x18002b4c4  ja      short loc_18002B4D8
0x18002b4c6  mov     ecx, [rbp+40h+var_B8]
0x18002b4c9  lea     rdx, [r14+rcx*2]
0x18002b4cd  cmp     [rsp+140h+EndPtr], rdx
0x18002b4d2  jnz     short loc_18002B4D8
0x18002b4d4  mov     [rsi], eax
0x18002b4d6  jmp     short loc_18002B52C
0x18002b4d8  mov     ebx, 8007000Dh
0x18002b4dd  jmp     short loc_18002B4F1
0x18002b4df  mov     ebx, 80070057h
0x18002b4e4  test    rdi, rdi
0x18002b4e7  jz      short loc_18002B52C
0x18002b4e9  cmp     ebx, 8007000Dh
0x18002b4ef  jnz     short loc_18002B52C
0x18002b4f1  lea     rax, a21474836482147; "[-2147483648,2147483647]"
0x18002b4f8  mov     qword ptr [rsp+140h+var_F8], r15
0x18002b4fd  mov     qword ptr [rsp+140h+var_F8+8], rax
0x18002b502  lea     r9, [rsp+140h+var_F8]
0x18002b507  mov     rax, [rdi]
0x18002b50a  mov     edx, 80070057h
0x18002b50f  mov     r8d, 0C0000411h
0x18002b515  mov     dword ptr [rsp+140h+var_120], 0
0x18002b51d  mov     rcx, rdi
0x18002b520  mov     rax, [rax+90h]
0x18002b527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b52c  lea     rcx, [rsp+140h+var_E8]; this
0x18002b531  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b536  mov     eax, ebx
0x18002b538  mov     rcx, [rbp+40h+var_30]
0x18002b53c  xor     rcx, rsp; StackCookie
0x18002b53f  call    __security_check_cookie
0x18002b544  mov     rbx, [rsp+140h+arg_0]
0x18002b54c  add     rsp, 120h
0x18002b553  pop     r15
0x18002b555  pop     r14
0x18002b557  pop     rdi
0x18002b558  pop     rsi
0x18002b559  pop     rbp
0x18002b55a  retn
```
