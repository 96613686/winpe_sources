# CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(IExtensionContext *,ICommandParameterList *,ushort const * *,int)

- ea: `0x18001d714`
- end: `0x18001d88b`
- name: `?PopSectionNameFromParameters@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEAPEBGH@Z`
- size: `375`
- prototype: `int(CONFIG_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, struct ICommandParameterList *, const unsigned __int16 **, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018fd0`
- `0x180019f48`
- `0x18001a850`
- `0x18001b350`

## callees

- `0x180001fb0`
- `0x18001d714`
- `0x18002b564`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## string_xrefs

- `0x18001d7a7`: `CONFIG.SECTION`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(
        CONFIG_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct ICommandParameterList *a3,
        const unsigned __int16 **a4,
        int a5)
{
  APP_OBJECT_UTILS *v8; // rcx
  int v9; // eax
  APP_OBJECT_UTILS *v10; // rcx
  unsigned int v11; // ebx
  __int16 *v12; // rsi
  __int64 v13; // rax
  __int16 *v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[32]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 *v17; // [rsp+68h] [rbp-98h]
  int v18; // [rsp+70h] [rbp-90h]
  __int16 v19; // [rsp+74h] [rbp-8Ch]
  int v20; // [rsp+78h] [rbp-88h]
  __int16 v21; // [rsp+80h] [rbp-80h] BYREF
  char v22[510]; // [rsp+82h] [rbp-7Eh] BYREF

  v15 = 0;
  memset_0(v22, 0, sizeof(v22));
  v18 = 512;
  v17 = &v21;
  v19 = 256;
  v20 = 0;
  v21 = 0;
  if ( a2 && a3 && a4 )
  {
    v9 = APP_OBJECT_UTILS::PopParameter(v8, a2, a3, L"CONFIG.SECTION", (struct STRU *)v16, 0, 1);
    v11 = v9;
    if ( v9 == -2147023483 )
    {
      v9 = APP_OBJECT_UTILS::PopParameter(v10, a2, a3, L"section", (struct STRU *)v16, a5, 1);
      v11 = v9;
    }
    if ( v9 >= 0 )
    {
      v12 = v17;
      v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int16 *, const unsigned __int16 **))(*(_QWORD *)a2 + 200LL))(
              a2,
              v17,
              a4);
      if ( v11 == -2147023483 )
      {
        v13 = *(_QWORD *)a2;
        v11 = -2147023728;
        v15 = v12;
        (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int16 **, _DWORD))(v13 + 144))(
          a2,
          2147943568LL,
          3221226487LL,
          &v15,
          0);
      }
    }
  }
  else
  {
    v11 = -2147024809;
  }
  BUFFER::~BUFFER((BUFFER *)v16);
  return v11;
}

```

## disassembly

```asm
0x18001d714  push    rbp
0x18001d716  push    rbx
0x18001d717  push    rsi
0x18001d718  push    rdi
0x18001d719  push    r14
0x18001d71b  lea     rbp, [rsp-190h]
0x18001d723  sub     rsp, 290h
0x18001d72a  mov     rax, cs:__security_cookie
0x18001d731  xor     rax, rsp
0x18001d734  mov     [rbp+1B0h+var_30], rax
0x18001d73b  mov     rsi, r8
0x18001d73e  mov     [rsp+2B0h+var_270], 0
0x18001d747  mov     rdi, rdx
0x18001d74a  lea     rcx, [rbp+1B0h+var_22E]; void *
0x18001d74e  xor     edx, edx; Val
0x18001d750  mov     r8d, 1FEh; Size
0x18001d756  mov     r14, r9
0x18001d759  call    memset_0
0x18001d75e  lea     rax, [rbp+1B0h+var_230]
0x18001d762  mov     [rsp+2B0h+var_240], 200h
0x18001d76a  mov     [rsp+2B0h+var_248], rax
0x18001d76f  xor     eax, eax
0x18001d771  mov     [rsp+2B0h+var_23C], 100h
0x18001d778  mov     [rsp+2B0h+var_238], 0
0x18001d780  mov     [rbp+1B0h+var_230], ax
0x18001d784  test    rdi, rdi
0x18001d787  jz      loc_18001D85D
0x18001d78d  test    rsi, rsi
0x18001d790  jz      loc_18001D85D
0x18001d796  test    r14, r14
0x18001d799  jz      loc_18001D85D
0x18001d79f  mov     [rsp+2B0h+var_280], 1; int
0x18001d7a7  lea     r9, aConfigSection; "CONFIG.SECTION"
0x18001d7ae  mov     [rsp+2B0h+var_288], eax; int
0x18001d7b2  mov     r8, rsi; struct ICommandParameterList *
0x18001d7b5  lea     rax, [rsp+2B0h+var_268]
0x18001d7ba  mov     rdx, rdi; struct IExtensionContext *
0x18001d7bd  mov     [rsp+2B0h+var_290], rax; struct STRU *
0x18001d7c2  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001d7c7  mov     ebx, eax
0x18001d7c9  cmp     eax, 80070585h
0x18001d7ce  jnz     short loc_18001D800
0x18001d7d0  mov     eax, [rbp+1B0h+arg_20]
0x18001d7d6  lea     r9, aSection; "section"
0x18001d7dd  mov     [rsp+2B0h+var_280], 1; int
0x18001d7e5  mov     r8, rsi; struct ICommandParameterList *
0x18001d7e8  mov     [rsp+2B0h+var_288], eax; int
0x18001d7ec  mov     rdx, rdi; struct IExtensionContext *
0x18001d7ef  lea     rax, [rsp+2B0h+var_268]
0x18001d7f4  mov     [rsp+2B0h+var_290], rax; struct STRU *
0x18001d7f9  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001d7fe  mov     ebx, eax
0x18001d800  test    eax, eax
0x18001d802  js      short loc_18001D862
0x18001d804  mov     rax, [rdi]
0x18001d807  mov     r8, r14
0x18001d80a  mov     rsi, [rsp+2B0h+var_248]
0x18001d80f  mov     rcx, rdi
0x18001d812  mov     rdx, rsi
0x18001d815  mov     rax, [rax+0C8h]
0x18001d81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d821  mov     ebx, eax
0x18001d823  cmp     eax, 80070585h
0x18001d828  jnz     short loc_18001D862
0x18001d82a  mov     rax, [rdi]
0x18001d82d  lea     r9, [rsp+2B0h+var_270]
0x18001d832  mov     ebx, 80070490h
0x18001d837  mov     [rsp+2B0h+var_270], rsi
0x18001d83c  mov     r8d, 0C00003F7h
0x18001d842  mov     dword ptr [rsp+2B0h+var_290], 0
0x18001d84a  mov     edx, ebx
0x18001d84c  mov     rcx, rdi
0x18001d84f  mov     rax, [rax+90h]
0x18001d856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d85b  jmp     short loc_18001D862
0x18001d85d  mov     ebx, 80070057h
0x18001d862  lea     rcx, [rsp+2B0h+var_268]; this
0x18001d867  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001d86c  mov     eax, ebx
0x18001d86e  mov     rcx, [rbp+1B0h+var_30]
0x18001d875  xor     rcx, rsp; StackCookie
0x18001d878  call    __security_check_cookie
0x18001d87d  add     rsp, 290h
0x18001d884  pop     r14
0x18001d886  pop     rdi
0x18001d887  pop     rsi
0x18001d888  pop     rbx
0x18001d889  pop     rbp
0x18001d88a  retn
```
