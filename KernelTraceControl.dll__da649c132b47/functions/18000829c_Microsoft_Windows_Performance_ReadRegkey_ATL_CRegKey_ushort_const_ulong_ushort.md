# Microsoft::Windows::Performance::ReadRegkey(ATL::CRegKey *,ushort const *,ulong,ushort *)

- ea: `0x18000829c`
- end: `0x18000839e`
- name: `?ReadRegkey@Performance@Windows@Microsoft@@YAJPEAVCRegKey@ATL@@PEBGKPEAG@Z`
- size: `258`
- prototype: `__int64 __fastcall(HKEY *this, struct ATL::CRegKey *, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800083a0`

## callees

- `0x180006210`
- `0x18000829c`
- `0x180008bd4`
- `0x1800268f4`
- `0x1800268fc`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800082e5`
- `ADVAPI32!RegQueryValueExW` at `0x1800082e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::ReadRegkey(HKEY *this, struct ATL::CRegKey *a2, char *a3)
{
  HKEY v7; // rcx
  DWORD v8; // ebx
  unsigned __int16 *v9; // rax
  char *v10; // rbx
  DWORD Type[10]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+68h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147500037LL;
  v7 = *this;
  cbData = 0;
  v12 = 0;
  if ( !RegQueryValueExW(v7, (LPCWSTR)a2, 0, Type, 0, &cbData) && Type[0] - 1 <= 1 )
  {
    v8 = cbData >> 1;
    v12 = cbData >> 1;
    if ( cbData >> 1 >= 0x40 )
    {
      v12 = v8 + 1;
      v9 = (unsigned __int16 *)operator new[](saturated_mul(v8 + 1, 2u));
      v10 = (char *)v9;
      if ( !v9 )
        return 2147942414LL;
      if ( !(unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)this, (const unsigned __int16 *)a2, v9, &v12) )
        StringCchCopyNW(a3, 64, v10, 0x40u);
      operator delete(v10);
    }
    else
    {
      ATL::CRegKey::QueryStringValue((ATL::CRegKey *)this, (const unsigned __int16 *)a2, (unsigned __int16 *)a3, &v12);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000829c  mov     [rsp+arg_0], rbx
0x1800082a1  push    rbp
0x1800082a2  push    rsi
0x1800082a3  push    rdi
0x1800082a4  sub     rsp, 40h
0x1800082a8  mov     rbp, r8
0x1800082ab  mov     rdi, rdx
0x1800082ae  mov     rsi, rcx
0x1800082b1  test    rdx, rdx
0x1800082b4  jnz     short loc_1800082C0
0x1800082b6  mov     eax, 80004005h
0x1800082bb  jmp     loc_180008391
0x1800082c0  mov     rcx, [rcx]; hKey
0x1800082c3  lea     rax, [rsp+58h+cbData]
0x1800082c8  and     [rsp+58h+cbData], 0
0x1800082cd  lea     r9, [rsp+58h+Type]; lpType
0x1800082d2  xor     ebx, ebx
0x1800082d4  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800082d9  and     [rsp+58h+var_38], rbx
0x1800082de  xor     r8d, r8d; lpReserved
0x1800082e1  mov     [rsp+58h+arg_8], ebx
0x1800082e5  call    cs:__imp_RegQueryValueExW
0x1800082eb  test    eax, eax
0x1800082ed  jnz     loc_18000838F
0x1800082f3  mov     eax, [rsp+58h+Type]
0x1800082f7  dec     eax
0x1800082f9  cmp     eax, 1
0x1800082fc  ja      loc_18000838F
0x180008302  mov     ebx, [rsp+58h+cbData]
0x180008306  xor     eax, eax
0x180008308  shr     ebx, 1
0x18000830a  mov     [rsp+58h+arg_8], ebx
0x18000830e  test    eax, eax
0x180008310  jnz     short loc_18000838F
0x180008312  cmp     ebx, 40h ; '@'
0x180008315  jnb     short loc_18000832C
0x180008317  lea     r9, [rsp+58h+arg_8]; unsigned int *
0x18000831c  mov     r8, rbp; unsigned __int16 *
0x18000831f  mov     rdx, rdi; unsigned __int16 *
0x180008322  mov     rcx, rsi; this
0x180008325  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18000832a  jmp     short loc_18000838F
0x18000832c  inc     ebx
0x18000832e  mov     eax, 2
0x180008333  mov     ecx, ebx
0x180008335  mul     rcx
0x180008338  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000833f  mov     [rsp+58h+arg_8], ebx
0x180008343  cmovo   rax, rcx
0x180008347  mov     rcx, rax; unsigned __int64
0x18000834a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000834f  mov     rbx, rax
0x180008352  test    rax, rax
0x180008355  jnz     short loc_18000835E
0x180008357  mov     eax, 8007000Eh
0x18000835c  jmp     short loc_180008391
0x18000835e  lea     r9, [rsp+58h+arg_8]; unsigned int *
0x180008363  mov     r8, rbx; unsigned __int16 *
0x180008366  mov     rdx, rdi; unsigned __int16 *
0x180008369  mov     rcx, rsi; this
0x18000836c  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x180008371  test    eax, eax
0x180008373  jnz     short loc_180008387
0x180008375  lea     r9d, [rax+40h]; unsigned __int64
0x180008379  mov     r8, rbx; unsigned __int16 *
0x18000837c  mov     edx, r9d; unsigned __int64
0x18000837f  mov     rcx, rbp; unsigned __int16 *
0x180008382  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180008387  mov     rcx, rbx; Block
0x18000838a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000838f  xor     eax, eax
0x180008391  mov     rbx, [rsp+58h+arg_0]
0x180008396  add     rsp, 40h
0x18000839a  pop     rdi
0x18000839b  pop     rsi
0x18000839c  pop     rbp
0x18000839d  retn
```
