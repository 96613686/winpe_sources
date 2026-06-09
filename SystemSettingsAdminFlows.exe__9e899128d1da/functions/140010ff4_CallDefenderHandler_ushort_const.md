# CallDefenderHandler(ushort const *)

- ea: `0x140010ff4`
- end: `0x140011145`
- name: `?CallDefenderHandler@@YAJPEBG@Z`
- size: `337`
- prototype: `int(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x140005f60`
- `0x14000db18`
- `0x140010ff4`
- `0x14001f3d4`
- `0x14006d0a8`
- `0x14006d140`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400110f2`
- `KERNEL32!LocalFree` at `0x140011132`
- `KERNEL32!LocalFree` at `0x1400110f2`
- `KERNEL32!LocalFree` at `0x140011132`
- `SHELL32!CommandLineToArgvW` at `0x14001100b`
- `SHELL32!CommandLineToArgvW` at `0x14001100b`

## string_xrefs

- `0x1400110e0`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`
- `0x140011118`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CallDefenderHandler(const unsigned __int16 *a1)
{
  const unsigned __int16 **v1; // rdi
  CDefenderHandler *v2; // rax
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rdx
  int v6; // eax
  CDefenderHandler *v7; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int pNumArgs; // [rsp+38h] [rbp+10h] BYREF
  const unsigned __int16 **v12; // [rsp+40h] [rbp+18h]
  CDefenderHandler *v13; // [rsp+48h] [rbp+20h]

  pNumArgs = 0;
  v1 = (const unsigned __int16 **)CommandLineToArgvW(a1, &pNumArgs);
  v12 = v1;
  if ( v1 && pNumArgs >= 1 )
  {
    if ( pNumArgs == 1 )
    {
      v2 = (CDefenderHandler *)operator new(0x210u, (const struct std::nothrow_t *)std::nothrow);
      v13 = v2;
      if ( v2 )
        v2 = CDefenderHandler::CDefenderHandler(v2);
      if ( !v2 )
      {
        v3 = -2147024882;
        v4 = 2147942414LL;
        v5 = 1841;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v5,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
          (const char *)v4,
          v9);
LABEL_22:
        LocalFree(v1);
        return v3;
      }
      v6 = CDefenderHandler::Execute(v2, *v1);
      v3 = v6;
      if ( v6 < 0 )
      {
        v5 = 1842;
LABEL_17:
        v4 = (unsigned int)v6;
        goto LABEL_18;
      }
    }
    else
    {
      if ( pNumArgs != 2 )
      {
        v3 = -2147024809;
        v4 = 2147942487LL;
        v5 = 1852;
        goto LABEL_18;
      }
      v7 = (CDefenderHandler *)operator new(0x210u, (const struct std::nothrow_t *)std::nothrow);
      v13 = v7;
      if ( v7 )
        v7 = CDefenderHandler::CDefenderHandler(v7);
      if ( !v7 )
      {
        v3 = -2147024882;
        v4 = 2147942414LL;
        v5 = 1847;
        goto LABEL_18;
      }
      v6 = CDefenderHandler::SetFeature(v7, *v1, v1[1]);
      v3 = v6;
      if ( v6 < 0 )
      {
        v5 = 1848;
        goto LABEL_17;
      }
    }
    LocalFree(v1);
    return 0;
  }
  v3 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x72C,
    (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
    (const char *)0x80070057LL,
    v9);
  if ( v1 )
    goto LABEL_22;
  return v3;
}

```

## disassembly

```asm
0x140010ff4  mov     [rsp+arg_0], rbx
0x140010ff9  push    rdi; int
0x140010ffa  sub     rsp, 20h
0x140010ffe  mov     [rsp+28h+pNumArgs], 0
0x140011006  lea     rdx, [rsp+28h+pNumArgs]; pNumArgs
0x14001100b  call    cs:__imp_CommandLineToArgvW
0x140011011  mov     rdi, rax
0x140011014  mov     [rsp+28h+arg_10], rax
0x140011019  test    rax, rax
0x14001101c  jz      loc_14001110B
0x140011022  mov     eax, [rsp+28h+pNumArgs]
0x140011026  cmp     eax, 1
0x140011029  jl      loc_14001110B
0x14001102f  jnz     short loc_140011081
0x140011031  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011038  mov     ecx, 210h; unsigned __int64
0x14001103d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140011042  mov     [rsp+28h+arg_18], rax
0x140011047  test    rax, rax
0x14001104a  jz      short loc_140011055
0x14001104c  mov     rcx, rax; this
0x14001104f  call    ??0CDefenderHandler@@QEAA@XZ; CDefenderHandler::CDefenderHandler(void)
0x140011054  nop
0x140011055  test    rax, rax
0x140011058  jnz     short loc_140011069
0x14001105a  mov     ebx, 8007000Eh
0x14001105f  mov     r9d, ebx
0x140011062  mov     edx, 731h
0x140011067  jmp     short loc_1400110DB
0x140011069  mov     rdx, [rdi]; unsigned __int16 *
0x14001106c  mov     rcx, rax; this
0x14001106f  call    ?Execute@CDefenderHandler@@QEAAJPEBG@Z; CDefenderHandler::Execute(ushort const *)
0x140011074  mov     ebx, eax
0x140011076  test    eax, eax
0x140011078  jns     short loc_1400110EF
0x14001107a  mov     edx, 732h
0x14001107f  jmp     short loc_1400110D8
0x140011081  cmp     eax, 2
0x140011084  jnz     short loc_1400110FC
0x140011086  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001108d  mov     ecx, 210h; unsigned __int64
0x140011092  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140011097  mov     [rsp+28h+arg_18], rax
0x14001109c  test    rax, rax
0x14001109f  jz      short loc_1400110AA
0x1400110a1  mov     rcx, rax; this
0x1400110a4  call    ??0CDefenderHandler@@QEAA@XZ; CDefenderHandler::CDefenderHandler(void)
0x1400110a9  nop
0x1400110aa  test    rax, rax
0x1400110ad  jnz     short loc_1400110BE
0x1400110af  mov     ebx, 8007000Eh
0x1400110b4  mov     r9d, ebx
0x1400110b7  mov     edx, 737h
0x1400110bc  jmp     short loc_1400110DB
0x1400110be  mov     r8, [rdi+8]; unsigned __int16 *
0x1400110c2  mov     rdx, [rdi]; unsigned __int16 *
0x1400110c5  mov     rcx, rax; this
0x1400110c8  call    ?SetFeature@CDefenderHandler@@QEAAJPEBG0@Z; CDefenderHandler::SetFeature(ushort const *,ushort const *)
0x1400110cd  mov     ebx, eax
0x1400110cf  test    eax, eax
0x1400110d1  jns     short loc_1400110EF
0x1400110d3  mov     edx, 738h; void *
0x1400110d8  mov     r9d, eax; char *
0x1400110db  mov     rcx, [rsp+28h]; this
0x1400110e0  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400110e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400110ec  nop
0x1400110ed  jmp     short loc_14001112F
0x1400110ef  mov     rcx, rdi; hMem
0x1400110f2  call    cs:__imp_LocalFree
0x1400110f8  xor     eax, eax
0x1400110fa  jmp     short loc_14001113A
0x1400110fc  mov     ebx, 80070057h
0x140011101  mov     r9d, ebx
0x140011104  mov     edx, 73Ch
0x140011109  jmp     short loc_1400110DB
0x14001110b  mov     rcx, [rsp+28h]; this
0x140011110  mov     ebx, 80070057h
0x140011115  mov     r9d, ebx; char *
0x140011118  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x14001111f  mov     edx, 72Ch; void *
0x140011124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011129  nop
0x14001112a  test    rdi, rdi
0x14001112d  jz      short loc_140011138
0x14001112f  mov     rcx, rdi; hMem
0x140011132  call    cs:__imp_LocalFree
0x140011138  mov     eax, ebx
0x14001113a  mov     rbx, [rsp+28h+arg_0]
0x14001113f  add     rsp, 20h
0x140011143  pop     rdi
0x140011144  retn
```
