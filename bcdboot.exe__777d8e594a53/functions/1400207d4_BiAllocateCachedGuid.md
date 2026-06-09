# BiAllocateCachedGuid

- ea: `0x1400207d4`
- end: `0x140020903`
- name: `BiAllocateCachedGuid`
- size: `303`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1400209d0`

## callees

- `0x14001e5e4`
- `0x14001f324`
- `0x14001f980`
- `0x14001fc5c`
- `0x1400207d4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400208dd`
- `ntdll!RtlFreeHeap` at `0x1400208dd`

## string_xrefs

- `0x140020831`: `GuidCache`
- `0x14002087a`: `GuidCache`

## pseudocode

```c
__int64 __fastcall BiAllocateCachedGuid(__int64 a1, _QWORD *a2, _DWORD *a3, __int64 a4)
{
  int v7; // ebx
  int RegistryValue; // eax
  unsigned __int16 *v9; // rdi
  HANDLE v10; // rcx
  unsigned int v12; // [rsp+30h] [rbp-48h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-40h] BYREF
  PVOID P[7]; // [rsp+40h] [rbp-38h] BYREF

  v12 = 0;
  Handle = 0;
  P[0] = 0;
  v7 = BiOpenKey(a1, L"Description", 131103, &Handle);
  if ( v7 >= 0 )
  {
    RegistryValue = BiGetRegistryValue(Handle, L"GuidCache", 0, 3, P, &v12);
    v9 = (unsigned __int16 *)P[0];
    v7 = RegistryValue;
    if ( RegistryValue >= 0 )
    {
      if ( v12 >= 0x18 )
      {
        if ( *((_DWORD *)P[0] + 2) )
        {
          *a2 = *(_QWORD *)P[0] - *((int *)P[0] + 2);
          v10 = Handle;
          *a3 = v9[6];
          *(_DWORD *)a4 = *(_DWORD *)(v9 + 7);
          *(_WORD *)(a4 + 4) = v9[9];
          --*((_DWORD *)v9 + 2);
          v7 = BiSetRegistryValue(v10, L"GuidCache", 0, 3, v9, 24);
        }
        else
        {
          v7 = -2147483622;
        }
      }
      else
      {
        v7 = -1073741789;
      }
    }
    if ( v9 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  }
  if ( Handle )
    BiCloseKey(Handle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400207d4  mov     rax, rsp
0x1400207d7  push    rbx
0x1400207d8  push    rbp
0x1400207d9  push    rdi
0x1400207da  push    r14
0x1400207dc  push    r15
0x1400207de  sub     rsp, 50h
0x1400207e2  mov     r14, r9
0x1400207e5  mov     dword ptr [rax-48h], 0
0x1400207ec  mov     r15, r8
0x1400207ef  mov     qword ptr [rax-40h], 0
0x1400207f7  mov     rbp, rdx
0x1400207fa  mov     qword ptr [rax-38h], 0
0x140020802  lea     r9, [rax-40h]
0x140020806  mov     r8d, 2001Fh
0x14002080c  lea     rdx, aDescription; "Description"
0x140020813  call    BiOpenKey
0x140020818  mov     ebx, eax
0x14002081a  test    eax, eax
0x14002081c  js      loc_1400208E3
0x140020822  mov     rcx, [rsp+78h+Handle]
0x140020827  lea     rax, [rsp+78h+var_48]
0x14002082c  mov     [rsp+78h+var_50], rax
0x140020831  lea     rdx, aGuidcache; "GuidCache"
0x140020838  lea     rax, [rsp+78h+P]
0x14002083d  mov     r9d, 3
0x140020843  xor     r8d, r8d
0x140020846  mov     [rsp+78h+var_58], rax
0x14002084b  call    BiGetRegistryValue
0x140020850  mov     rdi, [rsp+78h+P]
0x140020855  mov     ebx, eax
0x140020857  test    eax, eax
0x140020859  js      short loc_1400208C6
0x14002085b  cmp     [rsp+78h+var_48], 18h
0x140020860  jnb     short loc_140020869
0x140020862  mov     ebx, 0C0000023h
0x140020867  jmp     short loc_1400208C6
0x140020869  cmp     dword ptr [rdi+8], 0
0x14002086d  jnz     short loc_140020876
0x14002086f  mov     ebx, 8000001Ah
0x140020874  jmp     short loc_1400208C6
0x140020876  movsxd  rax, dword ptr [rdi+8]
0x14002087a  lea     rdx, aGuidcache; "GuidCache"
0x140020881  mov     rcx, [rdi]
0x140020884  mov     r9d, 3
0x14002088a  sub     rcx, rax
0x14002088d  mov     dword ptr [rsp+78h+var_50], 18h
0x140020895  mov     [rbp+0], rcx
0x140020899  xor     r8d, r8d
0x14002089c  movzx   eax, word ptr [rdi+0Ch]
0x1400208a0  mov     rcx, [rsp+78h+Handle]
0x1400208a5  mov     [r15], eax
0x1400208a8  mov     eax, [rdi+0Eh]
0x1400208ab  mov     [r14], eax
0x1400208ae  movzx   eax, word ptr [rdi+12h]
0x1400208b2  mov     [r14+4], ax
0x1400208b7  dec     dword ptr [rdi+8]
0x1400208ba  mov     [rsp+78h+var_58], rdi
0x1400208bf  call    BiSetRegistryValue
0x1400208c4  mov     ebx, eax
0x1400208c6  test    rdi, rdi
0x1400208c9  jz      short loc_1400208E3
0x1400208cb  mov     rcx, gs:60h
0x1400208d4  mov     r8, rdi; P
0x1400208d7  xor     edx, edx; Flags
0x1400208d9  mov     rcx, [rcx+30h]; HeapHandle
0x1400208dd  call    cs:__imp_RtlFreeHeap
0x1400208e3  cmp     [rsp+78h+Handle], 0
0x1400208e9  jz      short loc_1400208F5
0x1400208eb  mov     rcx, [rsp+78h+Handle]; Handle
0x1400208f0  call    BiCloseKey
0x1400208f5  mov     eax, ebx
0x1400208f7  add     rsp, 50h
0x1400208fb  pop     r15
0x1400208fd  pop     r14
0x1400208ff  pop     rdi
0x140020900  pop     rbp
0x140020901  pop     rbx
0x140020902  retn
```
