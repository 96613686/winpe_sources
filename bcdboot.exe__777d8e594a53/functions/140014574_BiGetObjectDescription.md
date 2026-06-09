# BiGetObjectDescription

- ea: `0x140014574`
- end: `0x14001464a`
- name: `BiGetObjectDescription`
- size: `214`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140013c1c`
- `0x14001474c`
- `0x14001c6e4`
- `0x1400214ec`
- `0x140022258`

## callees

- `0x140014574`
- `0x14001e5e4`
- `0x14001f324`
- `0x14001f980`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140014631`
- `ntdll!RtlFreeHeap` at `0x140014631`

## pseudocode

```c
__int64 __fastcall BiGetObjectDescription(__int64 a1, _DWORD *a2)
{
  void *v3; // rbx
  int v4; // edi
  HANDLE v5; // rcx
  int RegistryValue; // eax
  HANDLE Handle[3]; // [rsp+30h] [rbp-18h] BYREF
  int v9; // [rsp+60h] [rbp+18h] BYREF
  _DWORD *v10; // [rsp+68h] [rbp+20h] BYREF

  Handle[0] = 0;
  v3 = 0;
  v10 = 0;
  v4 = BiOpenKey(a1, L"Description", 131097, Handle);
  if ( v4 >= 0 )
  {
    v5 = Handle[0];
    *a2 = 1;
    v9 = 0;
    RegistryValue = BiGetRegistryValue(v5, L"Type", 0, 4, &v10, &v9);
    v3 = v10;
    v4 = RegistryValue;
    if ( RegistryValue >= 0 )
    {
      if ( v9 == 4 )
        a2[1] = *v10;
      else
        v4 = -1073741788;
    }
  }
  if ( Handle[0] )
    BiCloseKey(Handle[0]);
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140014574  mov     rax, rsp
0x140014577  mov     [rax+8], rbx
0x14001457b  mov     [rax+10h], rdi
0x14001457f  push    r14
0x140014581  sub     rsp, 40h
0x140014585  mov     r14, rdx
0x140014588  mov     qword ptr [rax-18h], 0
0x140014590  xor     ebx, ebx
0x140014592  lea     rdx, aDescription; "Description"
0x140014599  lea     r9, [rax-18h]
0x14001459d  mov     [rax+20h], rbx
0x1400145a1  mov     r8d, 20019h
0x1400145a7  call    BiOpenKey
0x1400145ac  mov     edi, eax
0x1400145ae  test    eax, eax
0x1400145b0  js      short loc_140014608
0x1400145b2  mov     rcx, [rsp+48h+Handle]
0x1400145b7  lea     rax, [rsp+48h+arg_10]
0x1400145bc  mov     [rsp+48h+var_20], rax
0x1400145c1  lea     r9d, [rbx+4]
0x1400145c5  lea     rax, [rsp+48h+arg_18]
0x1400145ca  mov     dword ptr [r14], 1
0x1400145d1  xor     r8d, r8d
0x1400145d4  mov     [rsp+48h+var_28], rax
0x1400145d9  lea     rdx, aType; "Type"
0x1400145e0  mov     [rsp+48h+arg_10], ebx
0x1400145e4  call    BiGetRegistryValue
0x1400145e9  mov     rbx, [rsp+48h+arg_18]
0x1400145ee  mov     edi, eax
0x1400145f0  test    eax, eax
0x1400145f2  js      short loc_140014608
0x1400145f4  cmp     [rsp+48h+arg_10], 4
0x1400145f9  jz      short loc_140014602
0x1400145fb  mov     edi, 0C0000024h
0x140014600  jmp     short loc_140014608
0x140014602  mov     eax, [rbx]
0x140014604  mov     [r14+4], eax
0x140014608  cmp     [rsp+48h+Handle], 0
0x14001460e  jz      short loc_14001461A
0x140014610  mov     rcx, [rsp+48h+Handle]; Handle
0x140014615  call    BiCloseKey
0x14001461a  test    rbx, rbx
0x14001461d  jz      short loc_140014637
0x14001461f  mov     rcx, gs:60h
0x140014628  mov     r8, rbx; P
0x14001462b  xor     edx, edx; Flags
0x14001462d  mov     rcx, [rcx+30h]; HeapHandle
0x140014631  call    cs:__imp_RtlFreeHeap
0x140014637  mov     rbx, [rsp+48h+arg_0]
0x14001463c  mov     eax, edi
0x14001463e  mov     rdi, [rsp+48h+arg_8]
0x140014643  add     rsp, 40h
0x140014647  pop     r14
0x140014649  retn
```
