# SRCache_ExpandMacros

- ea: `0x18000e340`
- end: `0x18000e3d9`
- name: `SRCache_ExpandMacros`
- size: `153`
- prototype: `__int64 __fastcall(StateRepository::Macros *, unsigned int, __int64, struct StateRepository::Core::Text *, int, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000940c`
- `0x18000df50`
- `0x18000e340`
- `0x18000e954`

## pseudocode

```c
__int64 __fastcall SRCache_ExpandMacros(
        StateRepository::Macros *a1,
        unsigned int a2,
        __int64 a3,
        struct StateRepository::Core::Text *a4,
        int a5,
        _QWORD *a6)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v10; // [rsp+20h] [rbp-40h] BYREF
  __int64 v11; // [rsp+28h] [rbp-38h]
  unsigned __int16 v12[4]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-28h]
  struct StateRepository::Core::Text *v14; // [rsp+40h] [rbp-20h]
  int v15; // [rsp+48h] [rbp-18h]
  int v16; // [rsp+4Ch] [rbp-14h]
  __int16 v17; // [rsp+50h] [rbp-10h]
  int v18; // [rsp+52h] [rbp-Eh]
  __int16 v19; // [rsp+56h] [rbp-Ah]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  *(_QWORD *)v12 = a2;
  v15 = a5;
  v13 = a3;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v10 = 0;
  v11 = 0;
  v14 = a4;
  v6 = StateRepository::Macros::Expand(a1, v12, (const struct StateRepository::Macros::MacroExpandOptions *)&v10, a4);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = v10;
    v7 = 0;
    v10 = 0;
    v11 = 0;
    *a6 = v8;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srmacros.cpp",
      (const char *)(unsigned int)v6,
      v10);
  }
  StateRepository::Core::Text::Reset((StateRepository::Core::Text *)&v10);
  return v7;
}

```

## disassembly

```asm
0x18000e340  mov     [rsp-8+arg_0], rbx
0x18000e345  push    rbp
0x18000e346  mov     rbp, rsp
0x18000e349  sub     rsp, 60h
0x18000e34d  mov     eax, edx
0x18000e34f  lea     rdx, [rbp+var_30]; unsigned __int16 *
0x18000e353  mov     qword ptr [rbp+var_30], rax
0x18000e357  mov     eax, [rbp+arg_20]
0x18000e35a  mov     [rbp+var_18], eax
0x18000e35d  xor     eax, eax
0x18000e35f  mov     [rbp+var_28], r8
0x18000e363  lea     r8, [rbp+var_40]; struct StateRepository::Macros::MacroExpandOptions *
0x18000e367  mov     [rbp+var_14], eax
0x18000e36a  mov     [rbp+var_10], ax
0x18000e36e  mov     [rbp+var_E], eax
0x18000e371  mov     [rbp+var_A], ax
0x18000e375  mov     [rbp+var_40], rax
0x18000e379  mov     [rbp+var_38], rax
0x18000e37d  mov     [rbp+var_20], r9
0x18000e381  call    ?Expand@Macros@StateRepository@@YAJPEBGAEBUMacroExpandOptions@12@AEAVText@Core@2@@Z; StateRepository::Macros::Expand(ushort const *,StateRepository::Macros::MacroExpandOptions const &,StateRepository::Core::Text &)
0x18000e386  mov     ebx, eax
0x18000e388  test    eax, eax
0x18000e38a  jns     short loc_18000E3A6
0x18000e38c  mov     rcx, [rbp+8]; this
0x18000e390  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x18000e397  mov     r9d, eax; char *
0x18000e39a  mov     edx, 17h; void *
0x18000e39f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e3a4  jmp     short loc_18000E3C3
0x18000e3a6  mov     rcx, [rbp+var_40]
0x18000e3aa  xor     ebx, ebx
0x18000e3ac  mov     rax, [rbp+arg_28]
0x18000e3b0  mov     [rbp+var_40], 0
0x18000e3b8  mov     [rbp+var_38], 0
0x18000e3c0  mov     [rax], rcx
0x18000e3c3  lea     rcx, [rbp+var_40]; this
0x18000e3c7  call    ?Reset@Text@Core@StateRepository@@QEAAXXZ; StateRepository::Core::Text::Reset(void)
0x18000e3cc  mov     eax, ebx
0x18000e3ce  mov     rbx, [rsp+60h+arg_0]
0x18000e3d3  add     rsp, 60h
0x18000e3d7  pop     rbp
0x18000e3d8  retn
```
