# BiCleanupLoadedStores

- ea: `0x14001b354`
- end: `0x14001b4b5`
- name: `BiCleanupLoadedStores`
- size: `353`
- prototype: `char __fastcall(char)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x14001bb00`
- `0x14001bd44`

## callees

- `0x14001acec`
- `0x14001b354`
- `0x14001b64c`
- `0x14001e5e4`
- `0x14001ee20`
- `0x14001f980`
- `0x14001fb48`
- `0x14001fd7c`
- `0x140020298`

## import_xrefs

- `msvcrt!wcstoul` at `0x14001b402`
- `msvcrt!wcstoul` at `0x14001b402`
- `msvcrt!_wcsnicmp` at `0x14001b3ea`
- `msvcrt!_wcsnicmp` at `0x14001b3ea`
- `ntdll!ZwClose` at `0x14001b49e`
- `ntdll!ZwClose` at `0x14001b49e`
- `ntdll!RtlFreeHeap` at `0x14001b48d`
- `ntdll!RtlFreeHeap` at `0x14001b48d`

## string_xrefs

- `0x14001b398`: `\Registry\Machine`

## pseudocode

```c
char __fastcall BiCleanupLoadedStores(char a1)
{
  char IsWinPEBoot; // r13
  int v3; // eax
  const wchar_t **v4; // rdi
  __int64 i; // rsi
  HANDLE v6; // rbx
  char IsSystemStore; // al
  HANDLE v9[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v10; // [rsp+68h] [rbp+38h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp+40h] BYREF
  PVOID P; // [rsp+78h] [rbp+48h] BYREF

  v9[0] = 0;
  v10 = 0;
  P = 0;
  Handle = 0;
  IsWinPEBoot = BiIsWinPEBoot();
  v3 = BiOpenKeyNonBcd(0, L"\\Registry\\Machine", 983103, &Handle);
  if ( v3 >= 0 )
  {
    v3 = BiEnumerateSubKeys(Handle, &P, &v10);
    v4 = (const wchar_t **)P;
    if ( v3 >= 0 )
    {
      for ( i = 0; (unsigned int)i < v10; i = (unsigned int)(i + 1) )
      {
        v3 = _wcsnicmp(v4[i], L"BCD", 3u);
        if ( !v3 )
        {
          v3 = wcstoul(v4[i] + 3, 0, 10);
          if ( v3 != -1 )
          {
            v3 = BiOpenKey(Handle, v4[i], 131097, v9);
            if ( v3 >= 0 )
            {
              v6 = v9[0];
              IsSystemStore = BiIsSystemStore(v9[0]);
              if ( (a1 & 0x10) != 0 && IsSystemStore )
              {
                LOBYTE(v3) = BcdForciblyUnloadStore(v6);
              }
              else if ( (a1 & 8) != 0 || IsWinPEBoot || !IsSystemStore )
              {
                LOBYTE(v3) = BiUnloadHiveByHandle(v6);
              }
              else
              {
                LOBYTE(v3) = BiCloseKey(v6);
              }
            }
          }
        }
      }
    }
    if ( v4 )
      LOBYTE(v3) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  if ( Handle )
    LOBYTE(v3) = ZwClose(Handle);
  return v3;
}

```

## disassembly

```asm
0x14001b354  mov     [rsp-28h+arg_0], rbx
0x14001b359  push    rbp
0x14001b35a  push    rsi
0x14001b35b  push    rdi
0x14001b35c  push    r12
0x14001b35e  push    r13
0x14001b360  mov     rbp, rsp
0x14001b363  sub     rsp, 30h
0x14001b367  mov     r12d, ecx
0x14001b36a  mov     [rbp+var_10], 0
0x14001b372  mov     [rbp+arg_8], 0
0x14001b379  mov     [rbp+P], 0
0x14001b381  mov     [rbp+Handle], 0
0x14001b389  call    BiIsWinPEBoot
0x14001b38e  lea     r9, [rbp+Handle]
0x14001b392  mov     r8d, 0F003Fh
0x14001b398  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine"
0x14001b39f  xor     ecx, ecx
0x14001b3a1  mov     r13b, al
0x14001b3a4  call    BiOpenKeyNonBcd
0x14001b3a9  test    eax, eax
0x14001b3ab  js      loc_14001B493
0x14001b3b1  mov     rcx, [rbp+Handle]
0x14001b3b5  lea     r8, [rbp+arg_8]
0x14001b3b9  lea     rdx, [rbp+P]
0x14001b3bd  call    BiEnumerateSubKeys
0x14001b3c2  mov     rdi, [rbp+P]
0x14001b3c6  test    eax, eax
0x14001b3c8  js      loc_14001B476
0x14001b3ce  xor     esi, esi
0x14001b3d0  cmp     [rbp+arg_8], esi
0x14001b3d3  jbe     loc_14001B476
0x14001b3d9  mov     rcx, [rdi+rsi*8]; String1
0x14001b3dd  lea     rdx, aBcd; "BCD"
0x14001b3e4  mov     r8d, 3; MaxCount
0x14001b3ea  call    cs:__imp__wcsnicmp
0x14001b3f0  test    eax, eax
0x14001b3f2  jnz     short loc_14001B46B
0x14001b3f4  mov     rcx, [rdi+rsi*8]
0x14001b3f8  lea     r8d, [rax+0Ah]; Radix
0x14001b3fc  add     rcx, 6; String
0x14001b400  xor     edx, edx; EndPtr
0x14001b402  call    cs:__imp_wcstoul
0x14001b408  cmp     eax, 0FFFFFFFFh
0x14001b40b  jz      short loc_14001B46B
0x14001b40d  mov     rdx, [rdi+rsi*8]
0x14001b411  lea     r9, [rbp+var_10]
0x14001b415  mov     rcx, [rbp+Handle]
0x14001b419  mov     r8d, 20019h
0x14001b41f  call    BiOpenKey
0x14001b424  test    eax, eax
0x14001b426  js      short loc_14001B46B
0x14001b428  mov     rbx, [rbp+var_10]
0x14001b42c  mov     rcx, rbx
0x14001b42f  call    BiIsSystemStore
0x14001b434  test    r12b, 10h
0x14001b438  jz      short loc_14001B448
0x14001b43a  test    al, al
0x14001b43c  jz      short loc_14001B448
0x14001b43e  mov     rcx, rbx; Handle
0x14001b441  call    BcdForciblyUnloadStore
0x14001b446  jmp     short loc_14001B46B
0x14001b448  test    r12b, 8
0x14001b44c  jnz     short loc_14001B461
0x14001b44e  test    r13b, r13b
0x14001b451  jnz     short loc_14001B461
0x14001b453  test    al, al
0x14001b455  jz      short loc_14001B461
0x14001b457  mov     rcx, rbx; Handle
0x14001b45a  call    BiCloseKey
0x14001b45f  jmp     short loc_14001B46B
0x14001b461  xor     edx, edx
0x14001b463  mov     rcx, rbx; Handle
0x14001b466  call    BiUnloadHiveByHandle
0x14001b46b  inc     esi
0x14001b46d  cmp     esi, [rbp+arg_8]
0x14001b470  jb      loc_14001B3D9
0x14001b476  test    rdi, rdi
0x14001b479  jz      short loc_14001B493
0x14001b47b  mov     rcx, gs:60h
0x14001b484  mov     r8, rdi; P
0x14001b487  xor     edx, edx; Flags
0x14001b489  mov     rcx, [rcx+30h]; HeapHandle
0x14001b48d  call    cs:__imp_RtlFreeHeap
0x14001b493  cmp     [rbp+Handle], 0
0x14001b498  jz      short loc_14001B4A4
0x14001b49a  mov     rcx, [rbp+Handle]; Handle
0x14001b49e  call    cs:__imp_ZwClose
0x14001b4a4  mov     rbx, [rsp+30h+arg_0]
0x14001b4a9  add     rsp, 30h
0x14001b4ad  pop     r13
0x14001b4af  pop     r12
0x14001b4b1  pop     rdi
0x14001b4b2  pop     rsi
0x14001b4b3  pop     rbp
0x14001b4b4  retn
```
