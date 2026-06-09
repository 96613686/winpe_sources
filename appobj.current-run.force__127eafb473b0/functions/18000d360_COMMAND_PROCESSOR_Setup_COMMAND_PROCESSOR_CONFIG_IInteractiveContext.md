# COMMAND_PROCESSOR::Setup(COMMAND_PROCESSOR_CONFIG *,IInteractiveContext *)

- ea: `0x18000d360`
- end: `0x18000d5d9`
- name: `?Setup@COMMAND_PROCESSOR@@UEAAJPEAUCOMMAND_PROCESSOR_CONFIG@@PEAVIInteractiveContext@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(COMMAND_PROCESSOR *__hidden this, struct COMMAND_PROCESSOR_CONFIG *, struct IInteractiveContext *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x18000d360`
- `0x18002b670`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d421`
- `msvcrt!_wcsicmp` at `0x18000d439`
- `msvcrt!_wcsicmp` at `0x18000d451`
- `msvcrt!_wcsicmp` at `0x18000d474`
- `msvcrt!_wcsicmp` at `0x18000d497`
- `msvcrt!_wcsicmp` at `0x18000d4ba`
- `msvcrt!_wcsicmp` at `0x18000d4e1`
- `msvcrt!_wcsicmp` at `0x18000d508`
- `msvcrt!_wcsicmp` at `0x18000d421`
- `msvcrt!_wcsicmp` at `0x18000d439`
- `msvcrt!_wcsicmp` at `0x18000d451`
- `msvcrt!_wcsicmp` at `0x18000d474`
- `msvcrt!_wcsicmp` at `0x18000d497`
- `msvcrt!_wcsicmp` at `0x18000d4ba`
- `msvcrt!_wcsicmp` at `0x18000d4e1`
- `msvcrt!_wcsicmp` at `0x18000d508`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::Setup(
        COMMAND_PROCESSOR *this,
        struct COMMAND_PROCESSOR_CONFIG *a2,
        struct IInteractiveContext *a3)
{
  int v6; // ebx
  wchar_t *v7; // rbx
  const wchar_t *v8; // rdx
  int v9; // eax
  APP_OBJECT_UTILS *v10; // rcx
  int v11; // eax
  _BYTE v13[32]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v14; // [rsp+50h] [rbp-B0h]
  int v15; // [rsp+58h] [rbp-A8h]
  __int16 v16; // [rsp+5Ch] [rbp-A4h]
  int v17; // [rsp+60h] [rbp-A0h]
  __int16 v18; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v19[510]; // [rsp+72h] [rbp-8Eh] BYREF

  memset_0(v19, 0, sizeof(v19));
  v15 = 512;
  v14 = (unsigned __int16 *)&v18;
  v16 = 256;
  v17 = 0;
  v18 = 0;
  if ( !a2 || !*(_QWORD *)a2 )
  {
    v6 = -2147024809;
    goto LABEL_32;
  }
  if ( *((_DWORD *)this + 88) )
  {
    v6 = -2147023649;
    goto LABEL_32;
  }
  if ( a3 )
  {
    *((_QWORD *)this + 43) = a3;
    (*(void (__fastcall **)(struct IInteractiveContext *))(*(_QWORD *)a3 + 8LL))(a3);
  }
  if ( *((_DWORD *)a2 + 6) )
    goto LABEL_19;
  v7 = *(wchar_t **)a2;
  if ( !_wcsicmp(*(const wchar_t **)a2, L"url") || !_wcsicmp(v7, &Str) )
  {
    *((_DWORD *)this + 48) = 0;
    goto LABEL_27;
  }
  if ( _wcsicmp(v7, L"parent") )
  {
    if ( !_wcsicmp(v7, L"app") )
    {
      *((_DWORD *)this + 48) = 2;
      goto LABEL_27;
    }
    if ( !_wcsicmp(v7, L"site") )
    {
      *((_DWORD *)this + 48) = 3;
      goto LABEL_27;
    }
    if ( !_wcsicmp(v7, L"apphost") )
    {
      *((_DWORD *)this + 48) = 4;
      v8 = L"MACHINE/WEBROOT/APPHOST";
      goto LABEL_22;
    }
    if ( _wcsicmp(v7, L"webroot") )
    {
      v9 = _wcsicmp(v7, L"machine");
      *((_DWORD *)this + 48) = 4;
      if ( v9 )
      {
        v11 = APP_OBJECT_UTILS::ResolveConfigPath(v10, *((_DWORD *)this + 49), v7, (struct STRU *)v13);
LABEL_23:
        v6 = v11;
        if ( v11 < 0 )
          goto LABEL_32;
        goto LABEL_27;
      }
      v8 = L"MACHINE";
LABEL_22:
      v11 = STRU::Copy((STRU *)v13, (const unsigned __int8 *)v8);
      goto LABEL_23;
    }
LABEL_19:
    *((_DWORD *)this + 48) = 4;
    v8 = L"MACHINE/WEBROOT";
    goto LABEL_22;
  }
  *((_DWORD *)this + 48) = 1;
LABEL_27:
  v6 = STRU::Copy((COMMAND_PROCESSOR *)((char *)this + 24), (const unsigned __int8 *)v14);
  if ( v6 >= 0 )
  {
    v6 = STRU::Copy((COMMAND_PROCESSOR *)((char *)this + 80), *((const unsigned __int8 **)a2 + 1));
    if ( v6 >= 0 )
    {
      v6 = STRU::Copy((COMMAND_PROCESSOR *)((char *)this + 136), *((const unsigned __int8 **)a2 + 2));
      if ( v6 >= 0 )
      {
        *((_DWORD *)this + 49) = *((_DWORD *)a2 + 6);
        *((_DWORD *)this + 88) = 1;
      }
    }
  }
LABEL_32:
  BUFFER::~BUFFER((BUFFER *)v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d360  mov     [rsp-8+arg_18], rbx
0x18000d365  push    rbp
0x18000d366  push    rsi
0x18000d367  push    rdi
0x18000d368  lea     rbp, [rsp-180h]
0x18000d370  sub     rsp, 280h
0x18000d377  mov     rax, cs:__security_cookie
0x18000d37e  xor     rax, rsp
0x18000d381  mov     [rbp+190h+var_20], rax
0x18000d388  mov     rbx, r8
0x18000d38b  mov     rsi, rdx
0x18000d38e  mov     rdi, rcx
0x18000d391  xor     edx, edx; Val
0x18000d393  mov     r8d, 1FEh; Size
0x18000d399  lea     rcx, [rsp+290h+var_21E]; void *
0x18000d39e  call    memset_0
0x18000d3a3  lea     rax, [rsp+290h+var_220]
0x18000d3a8  mov     [rsp+290h+var_238], 200h
0x18000d3b0  mov     [rsp+290h+var_240], rax
0x18000d3b5  xor     eax, eax
0x18000d3b7  mov     [rsp+290h+var_234], 100h
0x18000d3be  mov     [rsp+290h+var_230], 0
0x18000d3c6  mov     [rsp+290h+var_220], ax
0x18000d3cb  test    rsi, rsi
0x18000d3ce  jz      loc_18000D5A6
0x18000d3d4  cmp     [rsi], rax
0x18000d3d7  jz      loc_18000D5A6
0x18000d3dd  cmp     [rdi+160h], eax
0x18000d3e3  jz      short loc_18000D3EF
0x18000d3e5  mov     ebx, 800704DFh
0x18000d3ea  jmp     loc_18000D5AB
0x18000d3ef  test    rbx, rbx
0x18000d3f2  jz      short loc_18000D40A
0x18000d3f4  mov     [rdi+158h], rbx
0x18000d3fb  mov     rcx, rbx
0x18000d3fe  mov     rax, [rbx]
0x18000d401  mov     rax, [rax+8]
0x18000d405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d40a  cmp     dword ptr [rsi+18h], 0
0x18000d40e  jnz     loc_18000D4EB
0x18000d414  mov     rbx, [rsi]
0x18000d417  lea     rdx, aUrl_1; "url"
0x18000d41e  mov     rcx, rbx; String1
0x18000d421  call    cs:__imp__wcsicmp
0x18000d427  test    eax, eax
0x18000d429  jz      loc_18000D54A
0x18000d42f  lea     rdx, Str; String2
0x18000d436  mov     rcx, rbx; String1
0x18000d439  call    cs:__imp__wcsicmp
0x18000d43f  test    eax, eax
0x18000d441  jz      loc_18000D54A
0x18000d447  lea     rdx, aParent; "parent"
0x18000d44e  mov     rcx, rbx; String1
0x18000d451  call    cs:__imp__wcsicmp
0x18000d457  test    eax, eax
0x18000d459  jnz     short loc_18000D46A
0x18000d45b  mov     dword ptr [rdi+0C0h], 1
0x18000d465  jmp     loc_18000D554
0x18000d46a  lea     rdx, aApp; "app"
0x18000d471  mov     rcx, rbx; String1
0x18000d474  call    cs:__imp__wcsicmp
0x18000d47a  test    eax, eax
0x18000d47c  jnz     short loc_18000D48D
0x18000d47e  mov     dword ptr [rdi+0C0h], 2
0x18000d488  jmp     loc_18000D554
0x18000d48d  lea     rdx, aSite; "site"
0x18000d494  mov     rcx, rbx; String1
0x18000d497  call    cs:__imp__wcsicmp
0x18000d49d  test    eax, eax
0x18000d49f  jnz     short loc_18000D4B0
0x18000d4a1  mov     dword ptr [rdi+0C0h], 3
0x18000d4ab  jmp     loc_18000D554
0x18000d4b0  lea     rdx, aApphost; "apphost"
0x18000d4b7  mov     rcx, rbx; String1
0x18000d4ba  call    cs:__imp__wcsicmp
0x18000d4c0  test    eax, eax
0x18000d4c2  jnz     short loc_18000D4D7
0x18000d4c4  mov     dword ptr [rdi+0C0h], 4
0x18000d4ce  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000d4d5  jmp     short loc_18000D523
0x18000d4d7  lea     rdx, aWebroot; "webroot"
0x18000d4de  mov     rcx, rbx; String1
0x18000d4e1  call    cs:__imp__wcsicmp
0x18000d4e7  test    eax, eax
0x18000d4e9  jnz     short loc_18000D4FE
0x18000d4eb  mov     dword ptr [rdi+0C0h], 4
0x18000d4f5  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x18000d4fc  jmp     short loc_18000D523
0x18000d4fe  lea     rdx, aMachine; "machine"
0x18000d505  mov     rcx, rbx; String1
0x18000d508  call    cs:__imp__wcsicmp
0x18000d50e  mov     dword ptr [rdi+0C0h], 4
0x18000d518  test    eax, eax
0x18000d51a  jnz     short loc_18000D535
0x18000d51c  lea     rdx, aMachine_0; "MACHINE"
0x18000d523  lea     rcx, [rsp+290h+var_260]; this
0x18000d528  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000d52d  mov     ebx, eax
0x18000d52f  test    eax, eax
0x18000d531  js      short loc_18000D5AB
0x18000d533  jmp     short loc_18000D554
0x18000d535  mov     edx, [rdi+0C4h]; int
0x18000d53b  lea     r9, [rsp+290h+var_260]; struct STRU *
0x18000d540  mov     r8, rbx; unsigned __int16 *
0x18000d543  call    ?ResolveConfigPath@APP_OBJECT_UTILS@@QEAAJHPEBGPEAVSTRU@@PEAPEBG1@Z; APP_OBJECT_UTILS::ResolveConfigPath(int,ushort const *,STRU *,ushort const * *,STRU *)
0x18000d548  jmp     short loc_18000D52D
0x18000d54a  mov     dword ptr [rdi+0C0h], 0
0x18000d554  mov     rdx, [rsp+290h+var_240]; unsigned __int16 *
0x18000d559  lea     rcx, [rdi+18h]; this
0x18000d55d  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000d562  mov     ebx, eax
0x18000d564  test    eax, eax
0x18000d566  js      short loc_18000D5AB
0x18000d568  mov     rdx, [rsi+8]; unsigned __int16 *
0x18000d56c  lea     rcx, [rdi+50h]; this
0x18000d570  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000d575  mov     ebx, eax
0x18000d577  test    eax, eax
0x18000d579  js      short loc_18000D5AB
0x18000d57b  mov     rdx, [rsi+10h]; unsigned __int16 *
0x18000d57f  lea     rcx, [rdi+88h]; this
0x18000d586  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000d58b  mov     ebx, eax
0x18000d58d  test    eax, eax
0x18000d58f  js      short loc_18000D5AB
0x18000d591  mov     eax, [rsi+18h]
0x18000d594  mov     [rdi+0C4h], eax
0x18000d59a  mov     dword ptr [rdi+160h], 1
0x18000d5a4  jmp     short loc_18000D5AB
0x18000d5a6  mov     ebx, 80070057h
0x18000d5ab  lea     rcx, [rsp+290h+var_260]; this
0x18000d5b0  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000d5b5  mov     eax, ebx
0x18000d5b7  mov     rcx, [rbp+190h+var_20]
0x18000d5be  xor     rcx, rsp; StackCookie
0x18000d5c1  call    __security_check_cookie
0x18000d5c6  mov     rbx, [rsp+290h+arg_18]
0x18000d5ce  add     rsp, 280h
0x18000d5d5  pop     rdi
0x18000d5d6  pop     rsi
0x18000d5d7  pop     rbp
0x18000d5d8  retn
```
