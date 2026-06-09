# Microsoft::Resources::GetPackageRootFromFullName(ushort const *,Microsoft::Resources::StringResult *)

- ea: `0x18001b5fc`
- end: `0x18001b6c0`
- name: `?GetPackageRootFromFullName@Resources@Microsoft@@YAJPEBGPEAVStringResult@12@@Z`
- size: `196`
- prototype: `__int64 __fastcall(Microsoft::Resources *__hidden this, const unsigned __int16 *, struct Microsoft::Resources::StringResult *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001a748`
- `0x18001b830`
- `0x18007b1c0`

## callees

- `0x18000c880`
- `0x18001b5fc`
- `0x180028510`
- `0x18002c8d0`
- `0x1800862f0`

## import_xrefs

- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18001b642`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x1800c1211`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18001b642`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x1800c1211`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c11f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c11f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b6aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c11e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b6aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c11e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b6b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b6b8`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::GetPackageRootFromFullName(
        Microsoft::Resources *this,
        const unsigned __int16 *a2,
        struct Microsoft::Resources::StringResult *a3)
{
  signed int StagedPackagePathByFullName2; // ebx
  _BYTE *v6; // rdi
  bool v7; // sf
  HANDLE v9; // rax
  __int64 v10; // rcx
  SIZE_T v11; // rbx
  HANDLE ProcessHeap; // rax
  _BYTE *v13; // rax
  int v14[4]; // [rsp+20h] [rbp-248h] BYREF
  _BYTE Mem[528]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v14[0] = 260;
  StagedPackagePathByFullName2 = GetStagedPackagePathByFullName2(this, 2, v14, Mem);
  if ( StagedPackagePathByFullName2 == 122 )
  {
    if ( !DefArray_Size(2, (unsigned int)v14[0])
      || (v11 = DefArray_Size(v10, (unsigned int)v14[0]),
          ProcessHeap = GetProcessHeap(),
          v13 = HeapAlloc(ProcessHeap, 8u, v11),
          (v6 = v13) == 0) )
    {
      StagedPackagePathByFullName2 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
        (const char *)0x8007000ELL,
        v14[0]);
      return (unsigned int)StagedPackagePathByFullName2;
    }
    StagedPackagePathByFullName2 = GetStagedPackagePathByFullName2(this, 2, v14, v13);
  }
  else
  {
    v6 = Mem;
  }
  v7 = StagedPackagePathByFullName2 < 0;
  if ( StagedPackagePathByFullName2 > 0 )
  {
    StagedPackagePathByFullName2 = (unsigned __int16)StagedPackagePathByFullName2 | 0x80070000;
    v7 = StagedPackagePathByFullName2 < 0;
  }
  if ( !v7 )
    StagedPackagePathByFullName2 = DefStringResult_SetCopy(*(_QWORD *)a2, v6);
  if ( v6 != Mem )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v6);
  }
  return (unsigned int)StagedPackagePathByFullName2;
}

```

## disassembly

```asm
0x18001b5fc  mov     [rsp+arg_10], rbx
0x18001b601  mov     [rsp+arg_18], rbp
0x18001b606  push    rsi
0x18001b607  push    rdi
0x18001b608  push    r14
0x18001b60a  sub     rsp, 250h
0x18001b611  mov     rax, cs:__security_cookie
0x18001b618  xor     rax, rsp
0x18001b61b  mov     [rsp+268h+var_28], rax
0x18001b623  mov     r14, rdx
0x18001b626  mov     [rsp+268h+var_248], 104h; int
0x18001b62e  mov     ebp, 2
0x18001b633  lea     r9, [rsp+268h+Mem]
0x18001b638  mov     edx, ebp
0x18001b63a  lea     r8, [rsp+268h+var_248]
0x18001b63f  mov     rsi, rcx
0x18001b642  call    cs:__imp_GetStagedPackagePathByFullName2
0x18001b648  mov     ebx, eax
0x18001b64a  cmp     eax, 7Ah ; 'z'
0x18001b64d  jz      loc_1800C11C8
0x18001b653  lea     rdi, [rsp+268h+Mem]
0x18001b658  test    ebx, ebx
0x18001b65a  jle     short loc_18001B667
0x18001b65c  movzx   ebx, bx
0x18001b65f  or      ebx, 80070000h
0x18001b665  test    ebx, ebx
0x18001b667  js      short loc_18001B676
0x18001b669  mov     rcx, [r14]
0x18001b66c  mov     rdx, rdi
0x18001b66f  call    DefStringResult_SetCopy
0x18001b674  mov     ebx, eax
0x18001b676  lea     rax, [rsp+268h+Mem]
0x18001b67b  cmp     rdi, rax
0x18001b67e  jnz     short loc_18001B6AA
0x18001b680  mov     eax, ebx
0x18001b682  mov     rcx, [rsp+268h+var_28]
0x18001b68a  xor     rcx, rsp; StackCookie
0x18001b68d  call    __security_check_cookie
0x18001b692  lea     r11, [rsp+268h+var_18]
0x18001b69a  mov     rbx, [r11+30h]
0x18001b69e  mov     rbp, [r11+38h]
0x18001b6a2  mov     rsp, r11
0x18001b6a5  pop     r14
0x18001b6a7  pop     rdi
0x18001b6a8  pop     rsi
0x18001b6a9  retn
0x18001b6aa  call    cs:__imp_GetProcessHeap
0x18001b6b0  mov     r8, rdi; lpMem
0x18001b6b3  xor     edx, edx; dwFlags
0x18001b6b5  mov     rcx, rax; hHeap
0x18001b6b8  call    cs:__imp_HeapFree
0x18001b6be  jmp     short loc_18001B680
0x1800c11c8  mov     edx, [rsp+268h+var_248]
0x1800c11cc  mov     rcx, rbp
0x1800c11cf  call    _DefArray_Size
0x1800c11d4  test    rax, rax
0x1800c11d7  jz      short loc_1800C121E
0x1800c11d9  mov     edx, [rsp+268h+var_248]
0x1800c11dd  call    _DefArray_Size
0x1800c11e2  mov     rbx, rax
0x1800c11e5  call    cs:__imp_GetProcessHeap
0x1800c11eb  mov     r8, rbx; dwBytes
0x1800c11ee  mov     edx, 8; dwFlags
0x1800c11f3  mov     rcx, rax; hHeap
0x1800c11f6  call    cs:__imp_HeapAlloc
0x1800c11fc  mov     rdi, rax
0x1800c11ff  test    rax, rax
0x1800c1202  jz      short loc_1800C121E
0x1800c1204  mov     r9, rax
0x1800c1207  lea     r8, [rsp+268h+var_248]
0x1800c120c  mov     edx, ebp
0x1800c120e  mov     rcx, rsi
0x1800c1211  call    cs:__imp_GetStagedPackagePathByFullName2
0x1800c1217  mov     ebx, eax
0x1800c1219  jmp     loc_18001B658
0x1800c121e  mov     rcx, [rsp+268h]; this
0x1800c1226  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x1800c122d  mov     ebx, 8007000Eh
0x1800c1232  mov     edx, 0D9h; void *
0x1800c1237  mov     r9d, ebx; char *
0x1800c123a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c123f  nop
0x1800c1240  jmp     loc_18001B680
```
