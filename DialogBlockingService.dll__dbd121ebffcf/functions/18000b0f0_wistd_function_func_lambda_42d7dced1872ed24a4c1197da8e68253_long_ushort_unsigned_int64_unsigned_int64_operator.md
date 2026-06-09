# wistd::__function::__func<_lambda_42d7dced1872ed24a4c1197da8e68253_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18000b0f0`
- end: `0x18000b157`
- name: `??R?$__func@V_lambda_42d7dced1872ed24a4c1197da8e68253_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `103`
- prototype: `int __fastcall(__int64, _QWORD *, unsigned int *, unsigned __int64 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000b0f0`
- `0x18000ba00`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000b122`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000b122`

## pseudocode

```c
int __fastcall wistd::__function::__func<_lambda_42d7dced1872ed24a4c1197da8e68253_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3,
        unsigned __int64 **a4)
{
  unsigned __int64 *v4; // rbx
  _QWORD *v6; // rdx
  __int64 v7; // r9
  _QWORD *v8; // rcx
  unsigned int PersistedRegistryLocationW; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v15; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a4;
  v6 = *(_QWORD **)(a1 + 8);
  v7 = *a3;
  v8 = *(_QWORD **)(a1 + 16);
  v15 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(*v8, *v6, *a2, v7);
  v12 = 0;
  if ( PersistedRegistryLocationW != 234 )
    v12 = (const char *)PersistedRegistryLocationW;
  if ( (_DWORD)v12 )
    return wil::details::in1diag3::Return_Win32(retaddr, v10, v11, v12, (unsigned int)&v15);
  *v4 = (unsigned __int64)v15 >> 1;
  return 0;
}

```

## disassembly

```asm
0x18000b0f0  push    rbx
0x18000b0f2  sub     rsp, 30h
0x18000b0f6  mov     rbx, [r9]
0x18000b0f9  mov     rax, rdx
0x18000b0fc  mov     rdx, [rcx+8]
0x18000b100  mov     r9d, [r8]
0x18000b103  lea     r8, [rsp+38h+arg_0]
0x18000b108  mov     rcx, [rcx+10h]
0x18000b10c  mov     [rsp+38h+arg_0], 0
0x18000b114  mov     rdx, [rdx]
0x18000b117  mov     qword ptr [rsp+38h+var_18], r8; unsigned int
0x18000b11c  mov     rcx, [rcx]
0x18000b11f  mov     r8, [rax]
0x18000b122  call    cs:__imp_GetPersistedRegistryLocationW
0x18000b128  xor     r9d, r9d
0x18000b12b  cmp     eax, 0EAh
0x18000b130  cmovnz  r9d, eax; char *
0x18000b134  test    r9d, r9d
0x18000b137  jz      short loc_18000B145
0x18000b139  mov     rcx, [rsp+38h]; this
0x18000b13e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b143  jmp     short loc_18000B151
0x18000b145  mov     eax, [rsp+38h+arg_0]
0x18000b149  shr     rax, 1
0x18000b14c  mov     [rbx], rax
0x18000b14f  xor     eax, eax
0x18000b151  add     rsp, 30h
0x18000b155  pop     rbx
0x18000b156  retn
```
