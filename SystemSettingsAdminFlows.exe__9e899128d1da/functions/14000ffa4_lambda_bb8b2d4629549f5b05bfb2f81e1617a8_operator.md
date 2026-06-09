# _lambda_bb8b2d4629549f5b05bfb2f81e1617a8_::operator()

- ea: `0x14000ffa4`
- end: `0x14001008f`
- name: `_lambda_bb8b2d4629549f5b05bfb2f81e1617a8_::operator()`
- size: `235`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x14000ffa4`
- `0x14001f3d4`

## import_xrefs

- `DismApi!DismCloseSession` at `0x14001007c`
- `DismApi!DismCloseSession` at `0x14001007c`
- `DismApi!DismInitialize` at `0x14000ffb9`
- `DismApi!DismInitialize` at `0x14000ffb9`
- `DismApi!DismOpenSession` at `0x14000fffc`
- `DismApi!DismOpenSession` at `0x14000fffc`
- `DismApi!DismEnableFeature` at `0x140010070`
- `DismApi!DismEnableFeature` at `0x140010070`

## string_xrefs

- `0x14000ffca`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`
- `0x14001000d`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`

## pseudocode

```c
__int64 __fastcall lambda_bb8b2d4629549f5b05bfb2f81e1617a8_::operator()(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int v8; // [rsp+78h] [rbp+10h] BYREF

  v2 = DismInitialize(2, 0, 0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v8 = 0;
    v4 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v8);
    v3 = v4;
    if ( v4 >= 0 )
      v3 = DismEnableFeature(v8, *(_QWORD *)(**(_QWORD **)a1 + 8LL), 0, 0, 1, 0, 0, 1, 0, 0, 0);
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEEA,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
        (const char *)(unsigned int)v4,
        v6);
    DismCloseSession(v8);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE2,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
      (const char *)(unsigned int)v2,
      v6);
  }
  return v3;
}

```

## disassembly

```asm
0x14000ffa4  mov     [rsp+arg_0], rbx
0x14000ffa9  push    rdi
0x14000ffaa  sub     rsp, 60h
0x14000ffae  xor     edx, edx
0x14000ffb0  mov     rdi, rcx
0x14000ffb3  xor     r8d, r8d
0x14000ffb6  lea     ecx, [rdx+2]
0x14000ffb9  call    cs:__imp_DismInitialize
0x14000ffbf  mov     ebx, eax
0x14000ffc1  test    eax, eax
0x14000ffc3  jns     short loc_14000FFE3
0x14000ffc5  mov     rcx, [rsp+68h]; this
0x14000ffca  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x14000ffd1  mov     r9d, eax; char *
0x14000ffd4  mov     edx, 0EE2h; void *
0x14000ffd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ffde  jmp     loc_140010082
0x14000ffe3  lea     r9, [rsp+68h+arg_8]
0x14000ffe8  mov     [rsp+68h+arg_8], 0
0x14000fff0  xor     r8d, r8d
0x14000fff3  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x14000fffa  xor     edx, edx
0x14000fffc  call    cs:__imp_DismOpenSession
0x140010002  mov     ebx, eax
0x140010004  test    eax, eax
0x140010006  jns     short loc_140010023
0x140010008  mov     rcx, [rsp+68h]; this
0x14001000d  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x140010014  mov     r9d, eax; char *
0x140010017  mov     edx, 0EEAh; void *
0x14001001c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010021  jmp     short loc_140010078
0x140010023  mov     rax, [rdi]
0x140010026  xor     r9d, r9d
0x140010029  mov     ecx, [rsp+68h+arg_8]
0x14001002d  xor     r8d, r8d
0x140010030  mov     [rsp+68h+var_18], 0
0x140010039  mov     [rsp+68h+var_20], 0
0x140010042  mov     rdx, [rax]
0x140010045  mov     eax, 1
0x14001004a  mov     [rsp+68h+var_28], 0
0x140010053  mov     [rsp+68h+var_30], eax
0x140010057  mov     [rsp+68h+var_38], 0
0x14001005f  mov     rdx, [rdx+8]
0x140010063  mov     [rsp+68h+var_40], 0
0x14001006c  mov     [rsp+68h+var_48], eax
0x140010070  call    cs:__imp_DismEnableFeature
0x140010076  mov     ebx, eax
0x140010078  mov     ecx, [rsp+68h+arg_8]
0x14001007c  call    cs:__imp_DismCloseSession
0x140010082  mov     eax, ebx
0x140010084  mov     rbx, [rsp+68h+arg_0]
0x140010089  add     rsp, 60h
0x14001008d  pop     rdi
0x14001008e  retn
```
