# RegistryHelper::GetRootKey(IRegistryFunctions *,HKEY__ * const &,bool *,HKEY__ * *)

- ea: `0x180029dc4`
- end: `0x180029ecd`
- name: `?GetRootKey@RegistryHelper@@QEAAJPEAVIRegistryFunctions@@AEBQEAUHKEY__@@PEA_NPEAPEAU3@@Z`
- size: `265`
- prototype: `__int64 __fastcall(RegistryHelper *__hidden this, struct IRegistryFunctions *, HKEY *, bool *, HKEY *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180029c18`
- `0x180029ed4`
- `0x18002a0c8`

## callees

- `0x180006e84`
- `0x180024ce8`
- `0x180029dc4`
- `0x18002a0a4`
- `0x180032010`

## string_xrefs

- `0x180029e0c`: `onecoreuap\ds\ext\live\identity\lib\utilitieslite\registryhelper.cpp`
- `0x180029e7a`: `onecoreuap\ds\ext\live\identity\lib\utilitieslite\registryhelper.cpp`

## pseudocode

```c
__int64 __fastcall RegistryHelper::GetRootKey(
        RegistryHelper *this,
        struct IRegistryFunctions *a2,
        HKEY *a3,
        bool *a4,
        HKEY *a5)
{
  char v6; // al
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int v10; // eax
  HKEY v11; // rax
  unsigned int v12[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+28h] [rbp-20h]
  struct IRegistryFunctions *v14; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !*a3 || *a3 == HKEY_CURRENT_USER )
  {
    v6 = 1;
    if ( !a5 )
    {
      v7 = -2147024809;
      v8 = 245;
      goto LABEL_8;
    }
  }
  else
  {
    v6 = 0;
  }
  if ( !a4 )
  {
    v7 = -2147467261;
    v8 = 246;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\registryhelper.cpp",
      (const char *)v7,
      v12[0]);
    return v7;
  }
  *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( v6 )
  {
    *(_QWORD *)v12 = 0;
    v14 = a2;
    v13 = 0;
    v10 = (*(__int64 (__fastcall **)(struct IRegistryFunctions *, __int64, unsigned int *))(*(_QWORD *)a2 + 72LL))(
            a2,
            2,
            v12);
    if ( v10 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x103,
             (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\registryhelper.cpp",
             (const char *)v10,
             v12[0]);
      Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>((__int64)v12);
      return v7;
    }
    v11 = *(HKEY *)v12;
    *(_QWORD *)v12 = 0;
    v13 = 0;
    *a5 = v11;
    *a4 = 1;
    Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>((__int64)v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180029dc4  mov     [rsp+arg_0], rbx
0x180029dc9  push    rdi
0x180029dca  sub     rsp, 40h
0x180029dce  mov     rdi, r9
0x180029dd1  mov     r9, rdx
0x180029dd4  mov     rbx, [rsp+48h+arg_20]
0x180029dd9  cmp     qword ptr [r8], 0
0x180029ddd  jz      short loc_180029DFB
0x180029ddf  cmp     qword ptr [r8], 0FFFFFFFF80000001h
0x180029de6  jz      short loc_180029DFB
0x180029de8  xor     al, al
0x180029dea  test    rdi, rdi
0x180029ded  jnz     short loc_180029E27
0x180029def  mov     ebx, 80004003h
0x180029df4  mov     edx, 0F6h
0x180029df9  jmp     short loc_180029E0C
0x180029dfb  mov     al, 1
0x180029dfd  test    rbx, rbx
0x180029e00  jnz     short loc_180029DEA
0x180029e02  mov     ebx, 80070057h
0x180029e07  mov     edx, 0F5h; void *
0x180029e0c  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180029e13  mov     r9d, ebx; char *
0x180029e16  mov     rcx, [rsp+48h]; this
0x180029e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e20  mov     eax, ebx
0x180029e22  jmp     loc_180029EC2
0x180029e27  mov     byte ptr [rdi], 0
0x180029e2a  test    rbx, rbx
0x180029e2d  jz      short loc_180029E36
0x180029e2f  mov     qword ptr [rbx], 0
0x180029e36  test    al, al
0x180029e38  jz      loc_180029EC0
0x180029e3e  mov     qword ptr [rsp+48h+var_28], 0; unsigned int
0x180029e47  mov     [rsp+48h+var_18], r9
0x180029e4c  mov     [rsp+48h+var_20], 0
0x180029e55  mov     rax, [rdx]
0x180029e58  lea     r8, [rsp+48h+var_28]
0x180029e5d  mov     edx, 2
0x180029e62  mov     rcx, r9
0x180029e65  mov     rax, [rax+48h]
0x180029e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e6e  test    eax, eax
0x180029e70  jz      short loc_180029E99
0x180029e72  mov     rcx, [rsp+48h]; this
0x180029e77  mov     r9d, eax; char *
0x180029e7a  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180029e81  mov     edx, 103h; void *
0x180029e86  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180029e8b  mov     ebx, eax
0x180029e8d  lea     rcx, [rsp+48h+var_28]
0x180029e92  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x180029e97  jmp     short loc_180029E20
0x180029e99  mov     rax, qword ptr [rsp+48h+var_28]
0x180029e9e  mov     qword ptr [rsp+48h+var_28], 0
0x180029ea7  mov     [rsp+48h+var_20], 0
0x180029eb0  mov     [rbx], rax
0x180029eb3  mov     byte ptr [rdi], 1
0x180029eb6  lea     rcx, [rsp+48h+var_28]
0x180029ebb  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x180029ec0  xor     eax, eax
0x180029ec2  mov     rbx, [rsp+48h+arg_0]
0x180029ec7  add     rsp, 40h
0x180029ecb  pop     rdi
0x180029ecc  retn
```
