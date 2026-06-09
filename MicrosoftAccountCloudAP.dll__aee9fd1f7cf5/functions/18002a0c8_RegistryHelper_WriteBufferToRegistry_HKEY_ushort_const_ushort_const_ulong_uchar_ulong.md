# RegistryHelper::WriteBufferToRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x18002a0c8`
- end: `0x18002a21b`
- name: `?WriteBufferToRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAEK@Z`
- size: `339`
- prototype: `__int64 __fastcall(RegistryHelper *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180015468`
- `0x180027ba0`

## callees

- `0x180006e84`
- `0x180024ce8`
- `0x1800267c0`
- `0x180029dc4`
- `0x18002a0c8`
- `0x180032010`

## string_xrefs

- `0x18002a1ae`: `onecoreuap\ds\ext\live\identity\lib\utilitieslite\registryhelper.cpp`
- `0x18002a1e5`: `onecoreuap\ds\ext\live\identity\lib\utilitieslite\registryhelper.cpp`
- `0x18002a1a1`: `RegSetKeyValue() failed. (0x%0x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryHelper::WriteBufferToRegistry(
        RegistryHelper *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7)
{
  HKEY v9; // rdi
  struct IRegistryFunctions *v10; // rsi
  RegistryHelper *v11; // rcx
  int RootKey; // eax
  signed int v13; // ebx
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  signed int v16; // eax
  bool v17; // sf
  int v19; // [rsp+20h] [rbp-58h]
  HKEY v20[4]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  bool v22; // [rsp+80h] [rbp+8h] BYREF
  HKEY v23; // [rsp+88h] [rbp+10h] BYREF

  v23 = a2;
  v9 = a2;
  v10 = (struct IRegistryFunctions *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this);
  v20[0] = 0;
  v20[2] = (HKEY)v10;
  v20[1] = 0;
  v22 = 0;
  RootKey = RegistryHelper::GetRootKey(v11, v10, &v23, &v22, v20);
  v13 = RootKey;
  if ( RootKey < 0 )
  {
    v14 = (unsigned int)RootKey;
    v15 = 189;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\registryhelper.cpp",
      (const char *)v14,
      v19);
    goto LABEL_14;
  }
  if ( v22 )
    v9 = v20[0];
  v16 = (*(__int64 (__fastcall **)(struct IRegistryFunctions *, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int))(*(_QWORD *)v10 + 112LL))(
          v10,
          v9,
          a3,
          a4,
          a5,
          a6,
          a7);
  v13 = v16;
  if ( !v16 )
    goto LABEL_13;
  v19 = v16;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\registryhelper.cpp",
    0xCBu,
    L"RegSetKeyValue() failed. (0x%0x)");
  v17 = v13 < 0;
  if ( v13 > 0 )
  {
    v13 = (unsigned __int16)v13 | 0x80070000;
    v17 = v13 < 0;
  }
  if ( !v17 )
  {
LABEL_13:
    v13 = 0;
    goto LABEL_14;
  }
  if ( v13 != -2147024894 )
  {
    v14 = (unsigned int)v13;
    v15 = 206;
    goto LABEL_12;
  }
  v13 = -2147024894;
LABEL_14:
  Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>((__int64)v20);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002a0c8  mov     [rsp+arg_10], rbx
0x18002a0cd  mov     [rsp+arg_18], rbp
0x18002a0d2  mov     [rsp+arg_8], rdx
0x18002a0d7  push    rsi
0x18002a0d8  push    rdi
0x18002a0d9  push    r14
0x18002a0db  sub     rsp, 60h
0x18002a0df  mov     rbp, r9
0x18002a0e2  mov     r14, r8
0x18002a0e5  mov     rdi, rdx
0x18002a0e8  mov     rcx, [rcx]
0x18002a0eb  mov     rax, [rcx]
0x18002a0ee  mov     rax, [rax+8]
0x18002a0f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0f7  mov     rsi, rax
0x18002a0fa  mov     [rsp+78h+var_38], 0
0x18002a103  mov     [rsp+78h+var_28], rax
0x18002a108  mov     [rsp+78h+var_30], 0
0x18002a111  mov     [rsp+78h+arg_0], 0
0x18002a119  lea     rax, [rsp+78h+var_38]
0x18002a11e  mov     [rsp+78h+var_58], rax; HKEY *
0x18002a123  lea     r9, [rsp+78h+arg_0]; bool *
0x18002a12b  lea     r8, [rsp+78h+arg_8]; HKEY *
0x18002a133  mov     rdx, rsi; struct IRegistryFunctions *
0x18002a136  call    ?GetRootKey@RegistryHelper@@QEAAJPEAVIRegistryFunctions@@AEBQEAUHKEY__@@PEA_NPEAPEAU3@@Z; RegistryHelper::GetRootKey(IRegistryFunctions *,HKEY__ * const &,bool *,HKEY__ * *)
0x18002a13b  mov     ebx, eax
0x18002a13d  test    eax, eax
0x18002a13f  jns     short loc_18002A14E
0x18002a141  mov     r9d, eax
0x18002a144  mov     edx, 0BDh
0x18002a149  jmp     loc_18002A1E5
0x18002a14e  mov     rax, [rsi]
0x18002a151  cmp     [rsp+78h+arg_0], 0
0x18002a159  cmovnz  rdi, [rsp+78h+var_38]
0x18002a15f  mov     ecx, [rsp+78h+arg_30]
0x18002a166  mov     [rsp+78h+var_48], ecx
0x18002a16a  mov     rcx, [rsp+78h+arg_28]
0x18002a172  mov     [rsp+78h+var_50], rcx
0x18002a177  mov     ecx, [rsp+78h+arg_20]
0x18002a17e  mov     dword ptr [rsp+78h+var_58], ecx
0x18002a182  mov     r9, rbp
0x18002a185  mov     r8, r14
0x18002a188  mov     rdx, rdi
0x18002a18b  mov     rcx, rsi
0x18002a18e  mov     rax, [rax+70h]
0x18002a192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a197  mov     ebx, eax
0x18002a199  test    eax, eax
0x18002a19b  jz      short loc_18002A1F8
0x18002a19d  mov     dword ptr [rsp+78h+var_58], eax; int
0x18002a1a1  lea     r9, aRegsetkeyvalue; "RegSetKeyValue() failed. (0x%0x)"
0x18002a1a8  mov     r8d, 0CBh; unsigned int
0x18002a1ae  lea     rdx, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002a1b5  mov     ecx, 2; unsigned __int8
0x18002a1ba  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002a1bf  test    ebx, ebx
0x18002a1c1  jle     short loc_18002A1CE
0x18002a1c3  movzx   ebx, bx
0x18002a1c6  or      ebx, 80070000h
0x18002a1cc  test    ebx, ebx
0x18002a1ce  jns     short loc_18002A1F8
0x18002a1d0  mov     eax, 80070002h
0x18002a1d5  cmp     ebx, eax
0x18002a1d7  jnz     short loc_18002A1DD
0x18002a1d9  mov     ebx, eax
0x18002a1db  jmp     short loc_18002A1FA
0x18002a1dd  mov     r9d, ebx; char *
0x18002a1e0  mov     edx, 0CEh; void *
0x18002a1e5  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002a1ec  mov     rcx, [rsp+78h]; this
0x18002a1f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a1f6  jmp     short loc_18002A1FA
0x18002a1f8  xor     ebx, ebx
0x18002a1fa  lea     rcx, [rsp+78h+var_38]
0x18002a1ff  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x18002a204  mov     eax, ebx
0x18002a206  lea     r11, [rsp+78h+var_18]
0x18002a20b  mov     rbx, [r11+30h]
0x18002a20f  mov     rbp, [r11+38h]
0x18002a213  mov     rsp, r11
0x18002a216  pop     r14
0x18002a218  pop     rdi
0x18002a219  pop     rsi
0x18002a21a  retn
```
