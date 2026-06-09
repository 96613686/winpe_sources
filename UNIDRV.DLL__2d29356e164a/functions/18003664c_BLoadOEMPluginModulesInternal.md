# BLoadOEMPluginModulesInternal

- ea: `0x18003664c`
- end: `0x18003688b`
- name: `BLoadOEMPluginModulesInternal`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180027964`

## callees

- `0x18003664c`
- `0x180036894`
- `0x18003be38`
- `0x18004ec64`
- `0x180075010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800366b9`
- `KERNEL32!LoadLibraryExW` at `0x1800366b9`
- `KERNEL32!SetErrorMode` at `0x1800366aa`
- `KERNEL32!SetErrorMode` at `0x1800366aa`

## pseudocode

```c
__int64 __fastcall BLoadOEMPluginModulesInternal(__int64 a1, __int64 a2, int a3)
{
  int v3; // ebp
  __int64 v6; // r15
  __int64 v7; // rbx
  const WCHAR *v8; // rdi
  HMODULE Library; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int i; // ebx
  unsigned int (__fastcall *v16)(__int64, int *, __int64, int *); // rdi
  __int64 v17; // rdi
  unsigned int j; // edx
  int v19; // [rsp+68h] [rbp+10h] BYREF
  int v20; // [rsp+70h] [rbp+18h] BYREF

  v20 = a3;
  v3 = *(_DWORD *)(a2 + 8);
  v19 = 0;
  v20 = 0;
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
        if ( !(unsigned int)BGetOemInterface(a1, v7) )
          *(_QWORD *)(v7 + 72) = 0;
        v10 = *(_QWORD *)(v7 + 72);
        if ( v10 )
        {
          v11 = *(_QWORD *)(v7 + 80) - *(_QWORD *)&IID_IPrintOemUni.Data1;
          if ( !v11 )
            v11 = *(_QWORD *)(v7 + 88) - *(_QWORD *)IID_IPrintOemUni.Data4;
          if ( v11 )
          {
            v12 = *(_QWORD *)(v7 + 80) - *(_QWORD *)&IID_IPrintOemUni2.Data1;
            if ( !v12 )
              v12 = *(_QWORD *)(v7 + 88) - *(_QWORD *)IID_IPrintOemUni2.Data4;
            if ( v12 )
            {
              v13 = *(_QWORD *)(v7 + 80) - *(_QWORD *)&IID_IPrintOemUni3.Data1;
              if ( !v13 )
                v13 = *(_QWORD *)(v7 + 88) - *(_QWORD *)IID_IPrintOemUni3.Data4;
              if ( v13 )
                return 0;
            }
          }
          if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int64, int *))(*(_QWORD *)v10 + 24LL))(
                 v10,
                 1,
                 v7 + 24,
                 4,
                 &v20) < 0
            || !*(_DWORD *)(v7 + 24) )
          {
            return 0;
          }
        }
        else
        {
          if ( (*(_BYTE *)(v7 + 100) & 1) != 0 )
            v16 = *(unsigned int (__fastcall **)(__int64, int *, __int64, int *))(v7 + 104);
          else
            v16 = (unsigned int (__fastcall *)(__int64, int *, __int64, int *))PGetOemEntrypointAddress(v7, 0);
          if ( !v16
            || !v16(2, &v19, 4, &v20)
            || v19 != 0x10000
            || !v16(1, (int *)(v7 + 24), 4, &v20)
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
      v17 = v6 + 176LL * i;
      if ( *(_QWORD *)(v17 + 32) )
      {
        for ( j = 0; j < i; ++j )
        {
          if ( *(_DWORD *)(176LL * j + a2 + 48) == *(_DWORD *)(v17 + 24) )
          {
            VFreeSinglePluginEntry(v6 + 176LL * i);
            *(_DWORD *)(v17 + 24) = 0;
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
0x18003664c  mov     rax, rsp
0x18003664f  mov     [rax+8], rbx
0x180036653  mov     [rax+20h], rbp
0x180036657  mov     [rax+18h], r8d
0x18003665b  push    rsi
0x18003665c  push    rdi
0x18003665d  push    r12
0x18003665f  push    r14
0x180036661  push    r15
0x180036663  sub     rsp, 30h
0x180036667  mov     ebp, [rdx+8]
0x18003666a  mov     rsi, rdx
0x18003666d  mov     dword ptr [rax+10h], 0
0x180036674  mov     r12, rcx
0x180036677  mov     dword ptr [rax+18h], 0
0x18003667e  mov     r14d, 1
0x180036684  test    ebp, ebp
0x180036686  jz      loc_180036799
0x18003668c  lea     r15, [rdx+18h]
0x180036690  mov     rbx, r15
0x180036693  test    ebp, ebp
0x180036695  jz      loc_18003678C
0x18003669b  mov     rdi, [rbx]
0x18003669e  test    rdi, rdi
0x1800366a1  jz      loc_18003677E
0x1800366a7  mov     ecx, r14d; uMode
0x1800366aa  call    cs:__imp_SetErrorMode
0x1800366b0  xor     edx, edx; hFile
0x1800366b2  mov     rcx, rdi; lpLibFileName
0x1800366b5  lea     r8d, [rdx+8]; dwFlags
0x1800366b9  call    cs:__imp_LoadLibraryExW
0x1800366bf  mov     [rbx+20h], rax
0x1800366c3  test    rax, rax
0x1800366c6  jz      loc_180036838
0x1800366cc  mov     rdx, rbx
0x1800366cf  mov     rcx, r12
0x1800366d2  call    BGetOemInterface
0x1800366d7  test    eax, eax
0x1800366d9  jz      loc_1800367B3
0x1800366df  mov     rcx, [rbx+48h]
0x1800366e3  test    rcx, rcx
0x1800366e6  jz      loc_1800367C0
0x1800366ec  mov     rax, [rbx+50h]
0x1800366f0  lea     rdi, [rbx+18h]
0x1800366f4  sub     rax, qword ptr cs:IID_IPrintOemUni.Data1
0x1800366fb  jnz     short loc_180036708
0x1800366fd  mov     rax, [rbx+58h]
0x180036701  sub     rax, qword ptr cs:IID_IPrintOemUni.Data4
0x180036708  test    rax, rax
0x18003670b  jz      short loc_18003674B
0x18003670d  mov     rax, [rbx+50h]
0x180036711  sub     rax, qword ptr cs:IID_IPrintOemUni2.Data1
0x180036718  jnz     short loc_180036725
0x18003671a  mov     rax, [rbx+58h]
0x18003671e  sub     rax, qword ptr cs:IID_IPrintOemUni2.Data4
0x180036725  test    rax, rax
0x180036728  jz      short loc_18003674B
0x18003672a  mov     rax, [rbx+50h]
0x18003672e  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data1
0x180036735  jnz     short loc_180036742
0x180036737  mov     rax, [rbx+58h]
0x18003673b  sub     rax, qword ptr cs:IID_IPrintOemUni3.Data4
0x180036742  test    rax, rax
0x180036745  jnz     loc_180036838
0x18003674b  mov     rax, [rcx]
0x18003674e  lea     rdx, [rsp+58h+arg_10]
0x180036753  mov     [rsp+58h+var_38], rdx
0x180036758  mov     r9d, 4
0x18003675e  mov     r8, rdi
0x180036761  mov     edx, r14d
0x180036764  mov     rax, [rax+18h]
0x180036768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003676d  test    eax, eax
0x18003676f  js      loc_180036838
0x180036775  cmp     dword ptr [rdi], 0
0x180036778  jz      loc_180036838
0x18003677e  dec     ebp
0x180036780  add     rbx, 0B0h
0x180036787  jmp     loc_180036693
0x18003678c  mov     ebx, r14d
0x18003678f  cmp     [rsi+8], r14d
0x180036793  ja      loc_18003683F
0x180036799  mov     eax, r14d
0x18003679c  mov     rbx, [rsp+58h+arg_0]
0x1800367a1  mov     rbp, [rsp+58h+arg_18]
0x1800367a6  add     rsp, 30h
0x1800367aa  pop     r15
0x1800367ac  pop     r14
0x1800367ae  pop     r12
0x1800367b0  pop     rdi
0x1800367b1  pop     rsi
0x1800367b2  retn
0x1800367b3  mov     qword ptr [rbx+48h], 0
0x1800367bb  jmp     loc_1800366DF
0x1800367c0  test    [rbx+64h], r14b
0x1800367c4  jz      short loc_1800367CC
0x1800367c6  mov     rdi, [rbx+68h]
0x1800367ca  jmp     short loc_1800367D9
0x1800367cc  xor     edx, edx
0x1800367ce  mov     rcx, rbx
0x1800367d1  call    PGetOemEntrypointAddress
0x1800367d6  mov     rdi, rax
0x1800367d9  test    rdi, rdi
0x1800367dc  jz      short loc_180036838
0x1800367de  mov     r8d, 4
0x1800367e4  lea     r9, [rsp+58h+arg_10]
0x1800367e9  lea     rdx, [rsp+58h+arg_8]
0x1800367ee  mov     rax, rdi
0x1800367f1  lea     ecx, [r8-2]
0x1800367f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367fa  test    eax, eax
0x1800367fc  jz      short loc_180036838
0x1800367fe  cmp     [rsp+58h+arg_8], 10000h
0x180036806  jnz     short loc_180036838
0x180036808  mov     r8d, 4
0x18003680e  lea     r9, [rsp+58h+arg_10]
0x180036813  lea     rdx, [rbx+18h]
0x180036817  mov     rax, rdi
0x18003681a  lea     ecx, [r8-3]
0x18003681e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036823  test    eax, eax
0x180036825  jz      short loc_180036838
0x180036827  cmp     dword ptr [rbx+18h], 0
0x18003682b  jz      short loc_180036838
0x18003682d  mov     r14d, 1
0x180036833  jmp     loc_18003677E
0x180036838  xor     eax, eax
0x18003683a  jmp     loc_18003679C
0x18003683f  mov     eax, ebx
0x180036841  imul    rdi, rax, 0B0h
0x180036848  add     rdi, r15
0x18003684b  cmp     qword ptr [rdi+20h], 0
0x180036850  jz      short loc_18003687E
0x180036852  xor     edx, edx
0x180036854  cmp     edx, ebx
0x180036856  jnb     short loc_18003687E
0x180036858  mov     eax, edx
0x18003685a  imul    rcx, rax, 0B0h
0x180036861  mov     eax, [rdi+18h]
0x180036864  cmp     [rcx+rsi+30h], eax
0x180036868  jz      short loc_18003686F
0x18003686a  add     edx, r14d
0x18003686d  jmp     short loc_180036854
0x18003686f  mov     rcx, rdi
0x180036872  call    ?VFreeSinglePluginEntry@@YAXPEAU_OEM_PLUGIN_ENTRY@@W4BPluginRequestType@@@Z; VFreeSinglePluginEntry(_OEM_PLUGIN_ENTRY *,BPluginRequestType)
0x180036877  mov     dword ptr [rdi+18h], 0
0x18003687e  add     ebx, r14d
0x180036881  cmp     ebx, [rsi+8]
0x180036884  jb      short loc_18003683F
0x180036886  jmp     loc_180036799
```
