# ReadRegistryT<256>::TryOpen(HKEY__ *,ushort const *)

- ea: `0x180026734`
- end: `0x180026859`
- name: `?TryOpen@?$ReadRegistryT@$0BAA@@@SA?AV?$Optional@V?$ReadRegistryT@$0BAA@@@@@PEAUHKEY__@@PEBG@Z`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c648`
- `0x180016bfc`
- `0x18001757c`
- `0x1800184e8`
- `0x180026aa4`

## callees

- `0x180024e6c`
- `0x180026734`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026770`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026770`
- `ADVAPI32!RegOpenKeyExW` at `0x180026768`
- `ADVAPI32!RegOpenKeyExW` at `0x180026768`

## pseudocode

```c
_QWORD *__fastcall ReadRegistryT<256>::TryOpen(_QWORD *a1, HKEY a2, const WCHAR *a3)
{
  LSTATUS v4; // eax
  Private::RegistryBase *Registry; // rax
  _QWORD *v6; // r8
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rbx
  _BYTE v10[8]; // [rsp+38h] [rbp-30h] BYREF
  volatile signed __int32 *v11; // [rsp+40h] [rbp-28h]
  HKEY v12; // [rsp+88h] [rbp+20h] BYREF

  v12 = 0;
  v4 = RegOpenKeyExW(a2, a3, 0, 0x20119u, &v12);
  SetLastError(v4);
  if ( v12 )
  {
    Registry = ReadRegistryT<256>::ReadRegistryT<256>((Private::RegistryBase *)v10, v12, 1);
    v6 = a1 + 1;
    a1[1] = 0;
    a1[3] = &ReadRegistryT<256>::`vbtable';
    a1[2] = 0;
    a1[5] = &IConstHierarchicalStorage::`vftable';
    a1[1] = *(_QWORD *)Registry;
    a1[2] = *((_QWORD *)Registry + 1);
    *(_QWORD *)Registry = 0;
    *((_QWORD *)Registry + 1) = 0;
    *(_QWORD *)((char *)v6 + *(int *)(a1[3] + 4LL) + 16) = &ReadRegistryT<256>::`vftable';
    v7 = *(int *)(a1[3] + 4LL);
    *(_DWORD *)((char *)v6 + v7 + 12) = v7 - 16;
    v8 = v11;
    a1[6] = a1 + 1;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
  }
  else
  {
    a1[6] = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180026734  mov     r11, rsp
0x180026737  mov     [r11+8], rbx
0x18002673b  push    rdi
0x18002673c  sub     rsp, 60h
0x180026740  mov     rdi, rcx
0x180026743  mov     qword ptr [r11+20h], 0
0x18002674b  lea     rcx, [r11+20h]
0x18002674f  mov     rax, r8
0x180026752  mov     r10, rdx
0x180026755  mov     [r11-48h], rcx
0x180026759  mov     rcx, r10; hKey
0x18002675c  mov     r9d, 20119h; samDesired
0x180026762  xor     r8d, r8d; ulOptions
0x180026765  mov     rdx, rax; lpSubKey
0x180026768  call    cs:__imp_RegOpenKeyExW
0x18002676e  mov     ecx, eax; dwErrCode
0x180026770  call    cs:__imp_SetLastError
0x180026776  mov     rdx, [rsp+68h+arg_18]
0x18002677e  test    rdx, rdx
0x180026781  jnz     short loc_18002678C
0x180026783  mov     [rdi+30h], rdx
0x180026787  jmp     loc_18002684B
0x18002678c  mov     r8d, 1
0x180026792  lea     rcx, [rsp+68h+var_30]
0x180026797  call    ??0?$ReadRegistryT@$0BAA@@@IEAA@PEAUHKEY__@@@Z; ReadRegistryT<256>::ReadRegistryT<256>(HKEY__ *)
0x18002679c  lea     r8, [rdi+8]
0x1800267a0  mov     qword ptr [r8], 0
0x1800267a7  lea     rcx, ??_8?$ReadRegistryT@$0BAA@@@7B@; const ReadRegistryT<256>::`vbtable'
0x1800267ae  mov     [r8+10h], rcx
0x1800267b2  lea     rcx, ??_7IConstHierarchicalStorage@@6B@; const IConstHierarchicalStorage::`vftable'
0x1800267b9  mov     qword ptr [r8+8], 0
0x1800267c1  mov     [r8+20h], rcx
0x1800267c5  mov     rcx, [rax]
0x1800267c8  mov     [r8], rcx
0x1800267cb  mov     rcx, [rax+8]
0x1800267cf  mov     [r8+8], rcx
0x1800267d3  mov     qword ptr [rax], 0
0x1800267da  mov     qword ptr [rax+8], 0
0x1800267e2  mov     rax, [r8+10h]
0x1800267e6  movsxd  rcx, dword ptr [rax+4]
0x1800267ea  lea     rax, ??_7?$ReadRegistryT@$0BAA@@@6B@; const ReadRegistryT<256>::`vftable'
0x1800267f1  mov     [rcx+r8+10h], rax
0x1800267f6  mov     rax, [r8+10h]
0x1800267fa  movsxd  rcx, dword ptr [rax+4]
0x1800267fe  lea     edx, [rcx-10h]
0x180026801  mov     [rcx+r8+0Ch], edx
0x180026806  mov     rbx, [rsp+68h+var_28]
0x18002680b  mov     [rdi+30h], r8
0x18002680f  test    rbx, rbx
0x180026812  jz      short loc_18002684B
0x180026814  or      eax, 0FFFFFFFFh
0x180026817  lock xadd [rbx+8], eax
0x18002681c  cmp     eax, 1
0x18002681f  jnz     short loc_18002684B
0x180026821  mov     rax, [rbx]
0x180026824  mov     rcx, rbx
0x180026827  mov     rax, [rax]
0x18002682a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002682f  or      eax, 0FFFFFFFFh
0x180026832  lock xadd [rbx+0Ch], eax
0x180026837  cmp     eax, 1
0x18002683a  jnz     short loc_18002684B
0x18002683c  mov     rax, [rbx]
0x18002683f  mov     rcx, rbx
0x180026842  mov     rax, [rax+8]
0x180026846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002684b  mov     rbx, [rsp+68h+arg_0]
0x180026850  mov     rax, rdi
0x180026853  add     rsp, 60h
0x180026857  pop     rdi
0x180026858  retn
```
