# BLoadOEMPluginModulesInternal

- ea: `0x180037070`
- end: `0x1800372bc`
- name: `BLoadOEMPluginModulesInternal`
- size: `588`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800280ec`

## callees

- `0x180037070`
- `0x1800372c4`
- `0x18003d00c`
- `0x18005039c`
- `0x180077010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800370e3`
- `KERNEL32!LoadLibraryExW` at `0x1800370e3`
- `KERNEL32!SetErrorMode` at `0x1800370ce`
- `KERNEL32!SetErrorMode` at `0x1800370ce`

## pseudocode

```c
__int64 __fastcall BLoadOEMPluginModulesInternal(__int64 a1, __int64 a2, int a3)
{
  int v3; // ebp
  __int64 v6; // r15
  __int64 v7; // rbx
  const WCHAR *v8; // rdi
  HMODULE Library; // rax
  int v10; // r8d
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int i; // ebx
  unsigned int (__fastcall *v17)(__int64, int *, __int64, int *); // rdi
  __int64 v18; // rdi
  unsigned int j; // edx
  int v20; // [rsp+68h] [rbp+10h] BYREF
  int v21; // [rsp+70h] [rbp+18h] BYREF

  v21 = a3;
  v3 = *(_DWORD *)(a2 + 8);
  v20 = 0;
  v21 = 0;
  if ( v3 )
  {
    v6 = a2 + 24;
    v7 = a2 + 24;
    while ( v3 )
    {
      v8 = *(const WCHAR **)v7;
      if ( *(_QWORD *)v7 )
      {
        SetErrorMode(1u);
        Library = LoadLibraryExW(v8, 0, 8u);
        *(_QWORD *)(v7 + 32) = Library;
        if ( !Library )
          return 0;
        if ( !(unsigned int)BGetOemInterface(a1, v7, v10) )
          *(_QWORD *)(v7 + 72) = 0;
        v11 = *(_QWORD *)(v7 + 72);
        if ( v11 )
        {
          v12 = *(_QWORD *)(v7 + 80) - *(_QWORD *)&IID_IPrintOemUni.Data1;
          if ( !v12 )
            v12 = *(_QWORD *)(v7 + 88) - *(_QWORD *)IID_IPrintOemUni.Data4;
          if ( v12 )
          {
            v13 = *(_QWORD *)(v7 + 80) - *(_QWORD *)&IID_IPrintOemUni2.Data1;
            if ( !v13 )
              v13 = *(_QWORD *)(v7 + 88) - *(_QWORD *)IID_IPrintOemUni2.Data4;
            if ( v13 )
            {
              v14 = *(_QWORD *)(v7 + 80) - *(_QWORD *)&IID_IPrintOemUni3.Data1;
              if ( !v14 )
                v14 = *(_QWORD *)(v7 + 88) - *(_QWORD *)IID_IPrintOemUni3.Data4;
              if ( v14 )
                return 0;
            }
          }
          if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int64, int *))(*(_QWORD *)v11 + 24LL))(
                 v11,
                 1,
                 v7 + 24,
                 4,
                 &v21) < 0
            || !*(_DWORD *)(v7 + 24) )
          {
            return 0;
          }
        }
        else
        {
          if ( (*(_BYTE *)(v7 + 100) & 1) != 0 )
            v17 = *(unsigned int (__fastcall **)(__int64, int *, __int64, int *))(v7 + 104);
          else
            v17 = (unsigned int (__fastcall *)(__int64, int *, __int64, int *))PGetOemEntrypointAddress(v7, 0);
          if ( !v17
            || !v17(2, &v20, 4, &v21)
            || v20 != 0x10000
            || !v17(1, (int *)(v7 + 24), 4, &v21)
            || !*(_DWORD *)(v7 + 24) )
          {
            return 0;
          }
        }
      }
      --v3;
      v7 += 176;
    }
    for ( i = 1; i < *(_DWORD *)(a2 + 8); ++i )
    {
      v18 = v6 + 176LL * i;
      if ( *(_QWORD *)(v18 + 32) )
      {
        for ( j = 0; j < i; ++j )
        {
          if ( *(_DWORD *)(176LL * j + a2 + 48) == *(_DWORD *)(v18 + 24) )
          {
            VFreeSinglePluginEntry(v6 + 176LL * i);
            *(_DWORD *)(v18 + 24) = 0;
            break;
          }
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180037070  mov     rax, rsp
0x180037073  mov     [rax+8], rbx
0x180037077  mov     [rax+20h], rbp
0x18003707b  mov     [rax+18h], r8d
0x18003707f  push    rsi
0x180037080  push    rdi
0x180037081  push    r12
0x180037083  push    r14
0x180037085  push    r15
0x180037087  sub     rsp, 30h
0x18003708b  mov     ebp, [rdx+8]
0x18003708e  mov     rsi, rdx
0x180037091  mov     dword ptr [rax+10h], 0
0x180037098  mov     r12, rcx
0x18003709b  mov     dword ptr [rax+18h], 0
0x1800370a2  mov     r14d, 1
0x1800370a8  test    ebp, ebp
0x1800370aa  jz      loc_1800371C9
0x1800370b0  lea     r15, [rdx+18h]
0x1800370b4  mov     rbx, r15
0x1800370b7  test    ebp, ebp
0x1800370b9  jz      loc_1800371BC
0x1800370bf  mov     rdi, [rbx]
0x1800370c2  test    rdi, rdi
0x1800370c5  jz      loc_1800371AE
0x1800370cb  mov     ecx, r14d; uMode
0x1800370ce  call    cs:__imp_SetErrorMode
0x1800370d5  nop     dword ptr [rax+rax+00h]
0x1800370da  xor     edx, edx; hFile
0x1800370dc  mov     rcx, rdi; lpLibFileName
0x1800370df  lea     r8d, [rdx+8]; dwFlags
0x1800370e3  call    cs:__imp_LoadLibraryExW
0x1800370ea  nop     dword ptr [rax+rax+00h]
0x1800370ef  mov     [rbx+20h], rax
0x1800370f3  test    rax, rax
0x1800370f6  jz      loc_180037269
0x1800370fc  mov     rdx, rbx
0x1800370ff  mov     rcx, r12
0x180037102  call    BGetOemInterface
0x180037107  test    eax, eax
0x180037109  jz      loc_1800371E4
0x18003710f  mov     rcx, [rbx+48h]
0x180037113  test    rcx, rcx
0x180037116  jz      loc_1800371F1
0x18003711c  mov     rax, [rbx+50h]
0x180037120  lea     rdi, [rbx+18h]
0x180037124  sub     rax, qword ptr cs:IID_IPrintOemUni.Data1
0x18003712b  jnz     short loc_180037138
0x18003712d  mov     rax, [rbx+58h]
0x180037131  sub     rax, qword ptr cs:IID_IPrintOemUni.Data4
0x180037138  test    rax, rax
0x18003713b  jz      short loc_18003717B
0x18003713d  mov     rax, [rbx+50h]
0x180037141  sub     rax, qword ptr cs:IID_IPrintOemUni2.Data1
0x180037148  jnz     short loc_180037155
0x18003714a  mov     rax, [rbx+58h]
0x18003714e  sub     rax, qword ptr cs:IID_IPrintOemUni2.Data4
0x180037155  test    rax, rax
0x180037158  jz      short loc_18003717B
0x18003715a  mov     rax, [rbx+50h]
0x18003715e  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data1
0x180037165  jnz     short loc_180037172
0x180037167  mov     rax, [rbx+58h]
0x18003716b  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data4
0x180037172  test    rax, rax
0x180037175  jnz     loc_180037269
0x18003717b  mov     rax, [rcx]
0x18003717e  lea     rdx, [rsp+58h+arg_10]
0x180037183  mov     [rsp+58h+var_38], rdx
0x180037188  mov     r9d, 4
0x18003718e  mov     r8, rdi
0x180037191  mov     edx, r14d
0x180037194  mov     rax, [rax+18h]
0x180037198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003719d  test    eax, eax
0x18003719f  js      loc_180037269
0x1800371a5  cmp     dword ptr [rdi], 0
0x1800371a8  jz      loc_180037269
0x1800371ae  dec     ebp
0x1800371b0  add     rbx, 0B0h
0x1800371b7  jmp     loc_1800370B7
0x1800371bc  mov     ebx, r14d
0x1800371bf  cmp     [rsi+8], r14d
0x1800371c3  ja      loc_180037270
0x1800371c9  mov     eax, r14d
0x1800371cc  mov     rbx, [rsp+58h+arg_0]
0x1800371d1  mov     rbp, [rsp+58h+arg_18]
0x1800371d6  add     rsp, 30h
0x1800371da  pop     r15
0x1800371dc  pop     r14
0x1800371de  pop     r12
0x1800371e0  pop     rdi
0x1800371e1  pop     rsi
0x1800371e2  retn
0x1800371e4  mov     qword ptr [rbx+48h], 0
0x1800371ec  jmp     loc_18003710F
0x1800371f1  test    [rbx+64h], r14b
0x1800371f5  jz      short loc_1800371FD
0x1800371f7  mov     rdi, [rbx+68h]
0x1800371fb  jmp     short loc_18003720A
0x1800371fd  xor     edx, edx
0x1800371ff  mov     rcx, rbx
0x180037202  call    PGetOemEntrypointAddress
0x180037207  mov     rdi, rax
0x18003720a  test    rdi, rdi
0x18003720d  jz      short loc_180037269
0x18003720f  mov     r8d, 4
0x180037215  lea     r9, [rsp+58h+arg_10]
0x18003721a  lea     rdx, [rsp+58h+arg_8]
0x18003721f  mov     rax, rdi
0x180037222  lea     ecx, [r8-2]
0x180037226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003722b  test    eax, eax
0x18003722d  jz      short loc_180037269
0x18003722f  cmp     [rsp+58h+arg_8], 10000h
0x180037237  jnz     short loc_180037269
0x180037239  mov     r8d, 4
0x18003723f  lea     r9, [rsp+58h+arg_10]
0x180037244  lea     rdx, [rbx+18h]
0x180037248  mov     rax, rdi
0x18003724b  lea     ecx, [r8-3]
0x18003724f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037254  test    eax, eax
0x180037256  jz      short loc_180037269
0x180037258  cmp     dword ptr [rbx+18h], 0
0x18003725c  jz      short loc_180037269
0x18003725e  mov     r14d, 1
0x180037264  jmp     loc_1800371AE
0x180037269  xor     eax, eax
0x18003726b  jmp     loc_1800371CC
0x180037270  mov     eax, ebx
0x180037272  imul    rdi, rax, 0B0h
0x180037279  add     rdi, r15
0x18003727c  cmp     qword ptr [rdi+20h], 0
0x180037281  jz      short loc_1800372AF
0x180037283  xor     edx, edx
0x180037285  cmp     edx, ebx
0x180037287  jnb     short loc_1800372AF
0x180037289  mov     eax, edx
0x18003728b  imul    rcx, rax, 0B0h
0x180037292  mov     eax, [rdi+18h]
0x180037295  cmp     [rcx+rsi+30h], eax
0x180037299  jz      short loc_1800372A0
0x18003729b  add     edx, r14d
0x18003729e  jmp     short loc_180037285
0x1800372a0  mov     rcx, rdi
0x1800372a3  call    ?VFreeSinglePluginEntry@@YAXPEAU_OEM_PLUGIN_ENTRY@@W4BPluginRequestType@@@Z; VFreeSinglePluginEntry(_OEM_PLUGIN_ENTRY *,BPluginRequestType)
0x1800372a8  mov     dword ptr [rdi+18h], 0
0x1800372af  add     ebx, r14d
0x1800372b2  cmp     ebx, [rsi+8]
0x1800372b5  jb      short loc_180037270
0x1800372b7  jmp     loc_1800371C9
```
