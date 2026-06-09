# BLoadOEMPluginModulesInternal

- ea: `0x18003148c`
- end: `0x18003164e`
- name: `BLoadOEMPluginModulesInternal`
- size: `450`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f8f8`

## callees

- `0x180022d54`
- `0x180023190`
- `0x18003148c`
- `0x180031b40`
- `0x1800321e4`
- `0x18005f010`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x1800314e2`
- `KERNEL32!SetErrorMode` at `0x1800314e2`
- `KERNEL32!LoadLibraryExW` at `0x1800314f7`
- `KERNEL32!LoadLibraryExW` at `0x1800314f7`

## pseudocode

```c
__int64 __fastcall BLoadOEMPluginModulesInternal(__int64 a1, __int64 a2, int a3)
{
  int v3; // edi
  __int64 v6; // r15
  __int64 v7; // rbx
  const WCHAR *v8; // rbp
  HMODULE Library; // rax
  unsigned int (__fastcall *v11)(__int64, int *, __int64, int *, int *); // rbp
  unsigned int i; // ebx
  __int64 v13; // rdi
  unsigned int v14; // edx
  int *v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+68h] [rbp+10h] BYREF
  int v17; // [rsp+70h] [rbp+18h] BYREF

  v17 = a3;
  v3 = *(_DWORD *)(a2 + 8);
  v16 = 0;
  v17 = 0;
  if ( v3 )
  {
    v6 = a2 + 24;
    v7 = a2 + 24;
    do
    {
      v8 = *(const WCHAR **)v7;
      if ( *(_QWORD *)v7 )
      {
        SetErrorMode(1u);
        Library = LoadLibraryExW(v8, 0, 8u);
        *(_QWORD *)(v7 + 32) = Library;
        if ( !Library )
          return 0;
        if ( !(unsigned int)BGetOemInterface(a1, (GUID *)v7) )
          *(_QWORD *)(v7 + 72) = 0;
        if ( *(_QWORD *)(v7 + 72) )
        {
          v15 = &v17;
          if ( (int)HComOEMGetInfo(v7, 1u) < 0 || !*(_DWORD *)(v7 + 24) )
            return 0;
        }
        else
        {
          if ( (*(_BYTE *)(v7 + 100) & 1) != 0 )
            v11 = *(unsigned int (__fastcall **)(__int64, int *, __int64, int *, int *))(v7 + 104);
          else
            v11 = (unsigned int (__fastcall *)(__int64, int *, __int64, int *, int *))PGetOemEntrypointAddress(v7, 0);
          if ( !v11
            || !v11(2, &v16, 4, &v17, v15)
            || v16 != 0x10000
            || !((unsigned int (__fastcall *)(__int64, __int64, __int64, int *))v11)(1, v7 + 24, 4, &v17)
            || !*(_DWORD *)(v7 + 24) )
          {
            return 0;
          }
        }
      }
      v7 += 176;
      --v3;
    }
    while ( v3 );
    for ( i = 1; i < *(_DWORD *)(a2 + 8); ++i )
    {
      v13 = v6 + 176LL * i;
      if ( *(_QWORD *)(v13 + 32) && i )
      {
        v14 = 0;
        while ( *(_DWORD *)(176LL * v14 + a2 + 48) != *(_DWORD *)(v13 + 24) )
        {
          if ( ++v14 >= i )
            goto LABEL_28;
        }
        VFreeSinglePluginEntry(v6 + 176LL * i);
        *(_DWORD *)(v13 + 24) = 0;
      }
LABEL_28:
      ;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18003148c  mov     rax, rsp
0x18003148f  mov     [rax+8], rbx
0x180031493  mov     [rax+20h], rbp
0x180031497  mov     [rax+18h], r8d
0x18003149b  push    rsi
0x18003149c  push    rdi
0x18003149d  push    r12
0x18003149f  push    r14
0x1800314a1  push    r15
0x1800314a3  sub     rsp, 30h
0x1800314a7  mov     edi, [rdx+8]
0x1800314aa  mov     rsi, rdx
0x1800314ad  mov     dword ptr [rax+10h], 0
0x1800314b4  mov     r12, rcx
0x1800314b7  mov     dword ptr [rax+18h], 0
0x1800314be  mov     r14d, 1
0x1800314c4  test    edi, edi
0x1800314c6  jz      loc_180031633
0x1800314cc  lea     r15, [rdx+18h]
0x1800314d0  mov     rbx, r15
0x1800314d3  mov     rbp, [rbx]
0x1800314d6  test    rbp, rbp
0x1800314d9  jz      loc_1800315CD
0x1800314df  mov     ecx, r14d; uMode
0x1800314e2  call    cs:__imp_SetErrorMode
0x1800314e9  nop     dword ptr [rax+rax+00h]
0x1800314ee  xor     edx, edx; hFile
0x1800314f0  mov     rcx, rbp; lpLibFileName
0x1800314f3  lea     r8d, [rdx+8]; dwFlags
0x1800314f7  call    cs:__imp_LoadLibraryExW
0x1800314fe  nop     dword ptr [rax+rax+00h]
0x180031503  mov     [rbx+20h], rax
0x180031507  test    rax, rax
0x18003150a  jz      short loc_180031553
0x18003150c  mov     rdx, rbx
0x18003150f  mov     rcx, r12
0x180031512  call    BGetOemInterface
0x180031517  test    eax, eax
0x180031519  jnz     short loc_180031523
0x18003151b  mov     qword ptr [rbx+48h], 0
0x180031523  cmp     qword ptr [rbx+48h], 0
0x180031528  jz      short loc_18003155A
0x18003152a  lea     rax, [rsp+58h+arg_10]
0x18003152f  mov     r9d, 4
0x180031535  lea     r8, [rbx+18h]
0x180031539  mov     [rsp+58h+var_38], rax
0x18003153e  mov     edx, r14d
0x180031541  mov     rcx, rbx
0x180031544  call    HComOEMGetInfo
0x180031549  test    eax, eax
0x18003154b  js      short loc_180031553
0x18003154d  cmp     dword ptr [rbx+18h], 0
0x180031551  jnz     short loc_1800315CD
0x180031553  xor     eax, eax
0x180031555  jmp     loc_180031636
0x18003155a  test    [rbx+64h], r14b
0x18003155e  jz      short loc_180031566
0x180031560  mov     rbp, [rbx+68h]
0x180031564  jmp     short loc_180031573
0x180031566  xor     edx, edx
0x180031568  mov     rcx, rbx
0x18003156b  call    PGetOemEntrypointAddress
0x180031570  mov     rbp, rax
0x180031573  test    rbp, rbp
0x180031576  jz      short loc_180031553
0x180031578  mov     r8d, 4
0x18003157e  lea     r9, [rsp+58h+arg_10]
0x180031583  lea     rdx, [rsp+58h+arg_8]
0x180031588  mov     rax, rbp
0x18003158b  lea     ecx, [r8-2]
0x18003158f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031594  test    eax, eax
0x180031596  jz      short loc_180031553
0x180031598  cmp     [rsp+58h+arg_8], 10000h
0x1800315a0  jnz     short loc_180031553
0x1800315a2  mov     r8d, 4
0x1800315a8  lea     r9, [rsp+58h+arg_10]
0x1800315ad  lea     rdx, [rbx+18h]
0x1800315b1  mov     rax, rbp
0x1800315b4  lea     ecx, [r8-3]
0x1800315b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315bd  test    eax, eax
0x1800315bf  jz      short loc_180031553
0x1800315c1  cmp     dword ptr [rbx+18h], 0
0x1800315c5  jz      short loc_180031553
0x1800315c7  mov     r14d, 1
0x1800315cd  add     rbx, 0B0h
0x1800315d4  add     edi, 0FFFFFFFFh
0x1800315d7  jnz     loc_1800314D3
0x1800315dd  mov     ebx, r14d
0x1800315e0  cmp     [rsi+8], r14d
0x1800315e4  jbe     short loc_180031633
0x1800315e6  mov     eax, ebx
0x1800315e8  imul    rdi, rax, 0B0h
0x1800315ef  add     rdi, r15
0x1800315f2  cmp     qword ptr [rdi+20h], 0
0x1800315f7  jz      short loc_18003162B
0x1800315f9  test    ebx, ebx
0x1800315fb  jz      short loc_18003162B
0x1800315fd  mov     r8d, [rdi+18h]
0x180031601  xor     edx, edx
0x180031603  mov     eax, edx
0x180031605  imul    rcx, rax, 0B0h
0x18003160c  cmp     [rcx+rsi+30h], r8d
0x180031611  jz      short loc_18003161C
0x180031613  add     edx, r14d
0x180031616  cmp     edx, ebx
0x180031618  jb      short loc_180031603
0x18003161a  jmp     short loc_18003162B
0x18003161c  mov     rcx, rdi
0x18003161f  call    ?VFreeSinglePluginEntry@@YAXPEAU_OEM_PLUGIN_ENTRY@@W4BPluginRequestType@@@Z; VFreeSinglePluginEntry(_OEM_PLUGIN_ENTRY *,BPluginRequestType)
0x180031624  mov     dword ptr [rdi+18h], 0
0x18003162b  add     ebx, r14d
0x18003162e  cmp     ebx, [rsi+8]
0x180031631  jb      short loc_1800315E6
0x180031633  mov     eax, r14d
0x180031636  mov     rbx, [rsp+58h+arg_0]
0x18003163b  mov     rbp, [rsp+58h+arg_18]
0x180031640  add     rsp, 30h
0x180031644  pop     r15
0x180031646  pop     r14
0x180031648  pop     r12
0x18003164a  pop     rdi
0x18003164b  pop     rsi
0x18003164c  retn
```
