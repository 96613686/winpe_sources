# Dynamo::StateStore::CreateEntry(ushort const *,bool *)

- ea: `0x140043f50`
- end: `0x1400440f9`
- name: `?CreateEntry@StateStore@Dynamo@@UEAA?AV?$unique_ptr@VIStateEntry@Dynamo@@U?$default_delete@VIStateEntry@Dynamo@@@wistd@@@wistd@@PEBGPEA_N@Z`
- size: `425`
- prototype: `_QWORD *__fastcall(HKEY *, _QWORD *, const unsigned __int16 *, _BYTE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004314`
- `0x14000a6e4`
- `0x140043f50`
- `0x140044100`
- `0x14005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140043fd9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140043fd9`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x14004408a`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x14004408a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400440a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400440a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140043feb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140043feb`

## string_xrefs

- `0x14004407d`: `NodeUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall Dynamo::StateStore::CreateEntry(HKEY *a1, _QWORD *a2, const unsigned __int16 *a3, _BYTE *a4)
{
  _QWORD *v8; // rax
  int v9; // r15d
  HKEY v10; // rcx
  HKEY *v11; // rsi
  HKEY *v12; // rbx
  int v13; // eax
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  bool v15; // zf
  int v17; // [rsp+20h] [rbp-10h]
  HLOCAL hMem; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  void (__fastcall ***v20)(_QWORD, __int64); // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  if ( a4 )
    *a4 = 0;
  (*((void (__fastcall **)(HKEY *, _QWORD *))*a1 + 4))(a1, &v20);
  while ( v20 && ((unsigned __int8 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v20)[2])(v20) )
  {
    (*v20)[1](v20, (__int64)&hKey);
    v8 = (_QWORD *)(*(__int64 (__fastcall **)(HKEY, HLOCAL *))(*(_QWORD *)hKey + 56LL))(hKey, &hMem);
    v9 = _o__wcsicmp(a3, *v8);
    if ( hMem )
      LocalFree(hMem);
    if ( !v9 )
    {
      if ( a4 )
        *a4 = 1;
      *a2 = hKey;
      hKey = 0;
      goto LABEL_20;
    }
    v10 = hKey;
    hKey = 0;
    if ( v10 )
      (**(void (__fastcall ***)(HKEY, __int64))v10)(v10, 1);
  }
  v11 = (HKEY *)anonymous_namespace_::CreateUniqueSubKey(&hKey, a1[3]);
  v12 = (HKEY *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  hMem = v12;
  if ( v12 )
  {
    *v12 = (HKEY)&Dynamo::StateEntry::`vftable';
    v12[1] = *v11;
    *v11 = 0;
    v13 = OmaDmRegistrySetString(v12[1], 0, L"NodeUri", a3);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1A,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\stateentry.cpp",
        (const char *)(unsigned int)v13,
        v17);
  }
  else
  {
    v12 = 0;
  }
  *a2 = v12;
  if ( hKey )
    RegCloseKey(hKey);
LABEL_20:
  v14 = v20;
  v15 = v20 == 0;
  v20 = 0;
  if ( !v15 )
    (**v14)(v14, 1);
  return a2;
}

```

## disassembly

```asm
0x140043f50  mov     [rsp-28h+arg_8], rbx
0x140043f55  push    rbp
0x140043f56  push    rsi
0x140043f57  push    rdi
0x140043f58  push    r14
0x140043f5a  push    r15
0x140043f5c  mov     rbp, rsp
0x140043f5f  sub     rsp, 30h
0x140043f63  mov     rbx, r9
0x140043f66  mov     r14, r8
0x140043f69  mov     rdi, rdx
0x140043f6c  mov     rsi, rcx
0x140043f6f  test    r9, r9
0x140043f72  jz      short loc_140043F78
0x140043f74  mov     byte ptr [r9], 0
0x140043f78  mov     rax, [rcx]
0x140043f7b  lea     rdx, [rbp+arg_0]
0x140043f7f  mov     rax, [rax+20h]
0x140043f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043f88  nop
0x140043f89  mov     rcx, [rbp+arg_0]
0x140043f8d  test    rcx, rcx
0x140043f90  jz      loc_140044035
0x140043f96  mov     rax, [rcx]
0x140043f99  mov     rax, [rax+10h]
0x140043f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043fa2  test    al, al
0x140043fa4  jz      loc_140044035
0x140043faa  mov     rcx, [rbp+arg_0]
0x140043fae  mov     rax, [rcx]
0x140043fb1  lea     rdx, [rbp+hKey]
0x140043fb5  mov     rax, [rax+8]
0x140043fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043fbe  nop
0x140043fbf  mov     rcx, [rbp+hKey]
0x140043fc3  mov     rax, [rcx]
0x140043fc6  lea     rdx, [rbp+hMem]
0x140043fca  mov     rax, [rax+38h]
0x140043fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043fd3  mov     rdx, [rax]
0x140043fd6  mov     rcx, r14
0x140043fd9  call    cs:__imp__o__wcsicmp
0x140043fdf  mov     r15d, eax
0x140043fe2  mov     rcx, [rbp+hMem]; hMem
0x140043fe6  test    rcx, rcx
0x140043fe9  jz      short loc_140043FF1
0x140043feb  call    cs:__imp_LocalFree
0x140043ff1  test    r15d, r15d
0x140043ff4  jz      short loc_14004401C
0x140043ff6  mov     rcx, [rbp+hKey]
0x140043ffa  mov     [rbp+hKey], 0
0x140044002  test    rcx, rcx
0x140044005  jz      short loc_140043F89
0x140044007  mov     rax, [rcx]
0x14004400a  mov     edx, 1
0x14004400f  mov     rax, [rax]
0x140044012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044017  jmp     loc_140043F89
0x14004401c  test    rbx, rbx
0x14004401f  jz      short loc_140044024
0x140044021  mov     byte ptr [rbx], 1
0x140044024  mov     rax, [rbp+hKey]
0x140044028  mov     [rdi], rax
0x14004402b  mov     [rbp+hKey], 0
0x140044033  jmp     short loc_1400440AF
0x140044035  mov     rdx, [rsi+18h]; hKey
0x140044039  lea     rcx, [rbp+hKey]; phkResult
0x14004403d  call    _anonymous_namespace___CreateUniqueSubKey
0x140044042  mov     rsi, rax
0x140044045  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004404c  mov     ecx, 10h; unsigned __int64
0x140044051  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140044056  mov     rbx, rax
0x140044059  mov     [rbp+hMem], rax
0x14004405d  test    rax, rax
0x140044060  jz      short loc_14004409A
0x140044062  lea     rax, ??_7StateEntry@Dynamo@@6B@; const Dynamo::StateEntry::`vftable'
0x140044069  mov     [rbx], rax
0x14004406c  mov     rcx, [rsi]
0x14004406f  mov     [rbx+8], rcx
0x140044073  mov     qword ptr [rsi], 0
0x14004407a  mov     r9, r14
0x14004407d  lea     r8, aNodeuri; "NodeUri"
0x140044084  xor     edx, edx
0x140044086  mov     rcx, [rbx+8]
0x14004408a  call    cs:__imp_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x140044090  mov     rcx, [rbp+28h]; this
0x140044094  test    eax, eax
0x140044096  js      short loc_1400440E4
0x140044098  jmp     short loc_14004409C
0x14004409a  xor     ebx, ebx
0x14004409c  mov     [rdi], rbx
0x14004409f  mov     rcx, [rbp+hKey]; hKey
0x1400440a3  test    rcx, rcx
0x1400440a6  jz      short loc_1400440AF
0x1400440a8  call    cs:__imp_RegCloseKey
0x1400440ae  nop
0x1400440af  mov     rcx, [rbp+arg_0]
0x1400440b3  test    rcx, rcx
0x1400440b6  mov     [rbp+arg_0], 0
0x1400440be  jz      short loc_1400440D0
0x1400440c0  mov     rax, [rcx]
0x1400440c3  mov     edx, 1
0x1400440c8  mov     rax, [rax]
0x1400440cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400440d0  mov     rax, rdi
0x1400440d3  mov     rbx, [rsp+30h+arg_8]
0x1400440d8  add     rsp, 30h
0x1400440dc  pop     r15
0x1400440de  pop     r14
0x1400440e0  pop     rdi
0x1400440e1  pop     rsi
0x1400440e2  pop     rbp
0x1400440e3  retn
0x1400440e4  mov     r9d, eax; char *
0x1400440e7  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1400440ee  mov     edx, 1Ah; void *
0x1400440f3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
