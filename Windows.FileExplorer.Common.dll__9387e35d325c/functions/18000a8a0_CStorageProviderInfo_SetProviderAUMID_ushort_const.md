# CStorageProviderInfo::SetProviderAUMID(ushort const *)

- ea: `0x18000a8a0`
- end: `0x18000aaa2`
- name: `?SetProviderAUMID@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `514`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800077c8`
- `0x18000a8a0`
- `0x18000b9b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a916`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a916`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000aa01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000aa01`

## string_xrefs

- `0x18000aa17`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetProviderAUMID(CStorageProviderInfo *this, const unsigned __int16 *a2)
{
  char *v2; // r14
  const unsigned __int16 *v3; // rbx
  __int64 v4; // rax
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r8
  _WORD *v8; // rax
  int v9; // r15d
  _WORD *v10; // rdx
  unsigned __int64 v11; // rcx
  _WORD *v12; // rcx
  unsigned __int64 v14; // rsi
  LPVOID v15; // rax
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (char *)this + 216;
  v3 = a2;
  if ( !a2 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 216);
    return 0;
  }
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
    goto LABEL_22;
  v7 = *((_QWORD *)this + 29);
  if ( v7 == -1 )
  {
    if ( *((_QWORD *)this + 28) == -1 )
    {
      if ( *(_QWORD *)v2 )
      {
        do
          ++v4;
        while ( *(_WORD *)(*(_QWORD *)v2 + 2 * v4) );
      }
      else
      {
        v4 = 0;
      }
      *((_QWORD *)this + 28) = v4;
    }
    else
    {
      v4 = *((_QWORD *)this + 28);
    }
    v7 = v4 + 1;
    if ( !*(_QWORD *)v2 )
      v7 = 0;
    *((_QWORD *)this + 29) = v7;
  }
  if ( !v7 )
  {
    if ( is_mul_ok(v6, 2u) )
    {
      v8 = CoTaskMemAlloc(2 * v6);
      if ( v8 )
      {
        v9 = 0;
        *((_QWORD *)v2 + 2) = v6;
        *(_QWORD *)v2 = v8;
        *v8 = 0;
      }
      else
      {
        v9 = -2147024882;
      }
      if ( v9 < 0 )
        goto LABEL_35;
      goto LABEL_11;
    }
LABEL_22:
    v9 = -2147024362;
    goto LABEL_23;
  }
  v9 = 0;
  if ( v6 > v7 )
  {
    v14 = 2 * v7;
    if ( is_mul_ok(v7, 2u) )
    {
      if ( v7 > 0x800 )
        v14 = v7 + 2048;
      if ( v6 > v14 )
        v14 = v5 + 1;
      v15 = CoTaskMemRealloc(*(LPVOID *)v2, 2 * v14);
      if ( !v15 )
      {
        v9 = -2147024882;
        goto LABEL_35;
      }
      *((_QWORD *)v2 + 2) = v14;
      *(_QWORD *)v2 = v15;
      goto LABEL_11;
    }
    goto LABEL_22;
  }
LABEL_11:
  if ( v5 != -1 )
  {
    v10 = *(_WORD **)v2;
    if ( v6 > 0x7FFFFFFF )
    {
      *v10 = 0;
    }
    else if ( v5 > 0x7FFFFFFE )
    {
      *v10 = 0;
    }
    else
    {
      v11 = v5;
      do
      {
        if ( !v11 )
          break;
        if ( !*v3 )
          break;
        *v10++ = *v3++;
        --v11;
        --v6;
      }
      while ( v6 );
      v12 = v10 - 1;
      if ( v6 )
        v12 = v10;
      *v12 = 0;
    }
  }
  *((_QWORD *)v2 + 1) = v5;
LABEL_23:
  if ( v9 >= 0 )
    return 0;
LABEL_35:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x350,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v9,
    v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a8a0  push    rbx
0x18000a8a2  push    rbp
0x18000a8a3  push    rsi
0x18000a8a4  push    rdi
0x18000a8a5  push    r14
0x18000a8a7  push    r15
0x18000a8a9  sub     rsp, 28h
0x18000a8ad  lea     r14, [rcx+0D8h]
0x18000a8b4  mov     rbx, rdx
0x18000a8b7  test    rdx, rdx
0x18000a8ba  jz      loc_18000A9B3
0x18000a8c0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000a8c7  mov     rbp, rax
0x18000a8ca  nop     word ptr [rax+rax+00h]
0x18000a8d0  inc     rbp
0x18000a8d3  cmp     word ptr [rdx+rbp*2], 0
0x18000a8d8  jnz     short loc_18000A8D0
0x18000a8da  lea     rdi, [rbp+1]
0x18000a8de  cmp     rdi, rbp
0x18000a8e1  jb      loc_18000A999
0x18000a8e7  mov     r8, [r14+10h]
0x18000a8eb  cmp     r8, rax
0x18000a8ee  jz      loc_18000AA50
0x18000a8f4  test    r8, r8
0x18000a8f7  jnz     loc_18000A9C8
0x18000a8fd  mov     eax, 2
0x18000a902  mov     [rsp+58h+arg_0], r8
0x18000a907  mul     rdi
0x18000a90a  test    rdx, rdx
0x18000a90d  jnz     loc_18000A999
0x18000a913  mov     rcx, rax; cb
0x18000a916  call    cs:__imp_CoTaskMemAlloc
0x18000a91c  test    rax, rax
0x18000a91f  jz      loc_18000A9BD
0x18000a925  xor     r15d, r15d
0x18000a928  mov     [r14+10h], rdi
0x18000a92c  xor     ecx, ecx
0x18000a92e  mov     [r14], rax
0x18000a931  mov     [rax], cx
0x18000a934  test    r15d, r15d
0x18000a937  js      loc_18000AA12
0x18000a93d  test    rdi, rdi
0x18000a940  jz      short loc_18000A993
0x18000a942  mov     rdx, [r14]
0x18000a945  cmp     rdi, 7FFFFFFFh
0x18000a94c  ja      loc_18000AA8E
0x18000a952  cmp     rbp, 7FFFFFFEh
0x18000a959  ja      loc_18000AA98
0x18000a95f  mov     rcx, rbp
0x18000a962  test    rcx, rcx
0x18000a965  jz      short loc_18000A983
0x18000a967  movzx   eax, word ptr [rbx]
0x18000a96a  test    ax, ax
0x18000a96d  jz      short loc_18000A983
0x18000a96f  mov     [rdx], ax
0x18000a972  add     rbx, 2
0x18000a976  add     rdx, 2
0x18000a97a  dec     rcx
0x18000a97d  sub     rdi, 1
0x18000a981  jnz     short loc_18000A962
0x18000a983  test    rdi, rdi
0x18000a986  lea     rcx, [rdx-2]
0x18000a98a  cmovnz  rcx, rdx
0x18000a98e  xor     eax, eax
0x18000a990  mov     [rcx], ax
0x18000a993  mov     [r14+8], rbp
0x18000a997  jmp     short loc_18000A99F
0x18000a999  mov     r15d, 80070216h
0x18000a99f  test    r15d, r15d
0x18000a9a2  js      short loc_18000AA12
0x18000a9a4  xor     eax, eax
0x18000a9a6  add     rsp, 28h
0x18000a9aa  pop     r15
0x18000a9ac  pop     r14
0x18000a9ae  pop     rdi
0x18000a9af  pop     rsi
0x18000a9b0  pop     rbp
0x18000a9b1  pop     rbx
0x18000a9b2  retn
0x18000a9b3  mov     rcx, r14
0x18000a9b6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a9bb  jmp     short loc_18000A9A4
0x18000a9bd  mov     r15d, 8007000Eh
0x18000a9c3  jmp     loc_18000A934
0x18000a9c8  xor     r15d, r15d
0x18000a9cb  cmp     rdi, r8
0x18000a9ce  jbe     loc_18000A93D
0x18000a9d4  mov     eax, 2
0x18000a9d9  mul     r8
0x18000a9dc  mov     rsi, rax
0x18000a9df  test    rdx, rdx
0x18000a9e2  jnz     short loc_18000A999
0x18000a9e4  mov     rcx, rax
0x18000a9e7  sub     rcx, r8
0x18000a9ea  cmp     rcx, 800h
0x18000a9f1  ja      short loc_18000AA3B
0x18000a9f3  mov     rcx, [r14]; pv
0x18000a9f6  cmp     rdi, rsi
0x18000a9f9  cmova   rsi, rdi
0x18000a9fd  lea     rdx, [rsi+rsi]; cb
0x18000aa01  call    cs:__imp_CoTaskMemRealloc
0x18000aa07  test    rax, rax
0x18000aa0a  jnz     short loc_18000AA44
0x18000aa0c  mov     r15d, 8007000Eh
0x18000aa12  mov     rcx, [rsp+58h]; this
0x18000aa17  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000aa1e  mov     r9d, r15d; char *
0x18000aa21  mov     edx, 350h; void *
0x18000aa26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa2b  mov     eax, r15d
0x18000aa2e  add     rsp, 28h
0x18000aa32  pop     r15
0x18000aa34  pop     r14
0x18000aa36  pop     rdi
0x18000aa37  pop     rsi
0x18000aa38  pop     rbp
0x18000aa39  pop     rbx
0x18000aa3a  retn
0x18000aa3b  lea     rsi, [r8+800h]
0x18000aa42  jmp     short loc_18000A9F3
0x18000aa44  mov     [r14+10h], rsi
0x18000aa48  mov     [r14], rax
0x18000aa4b  jmp     loc_18000A93D
0x18000aa50  mov     rcx, [r14+8]
0x18000aa54  cmp     rcx, rax
0x18000aa57  jnz     short loc_18000AA75
0x18000aa59  mov     rcx, [r14]
0x18000aa5c  test    rcx, rcx
0x18000aa5f  jnz     short loc_18000AA65
0x18000aa61  xor     eax, eax
0x18000aa63  jmp     short loc_18000AA6F
0x18000aa65  inc     rax
0x18000aa68  cmp     word ptr [rcx+rax*2], 0
0x18000aa6d  jnz     short loc_18000AA65
0x18000aa6f  mov     [r14+8], rax
0x18000aa73  jmp     short loc_18000AA78
0x18000aa75  mov     rax, rcx
0x18000aa78  lea     r8, [rax+1]
0x18000aa7c  xor     eax, eax
0x18000aa7e  cmp     [r14], rax
0x18000aa81  cmovz   r8, rax
0x18000aa85  mov     [r14+10h], r8
0x18000aa89  jmp     loc_18000A8F4
0x18000aa8e  xor     eax, eax
0x18000aa90  mov     [rdx], ax
0x18000aa93  jmp     loc_18000A993
0x18000aa98  xor     eax, eax
0x18000aa9a  mov     [rdx], ax
0x18000aa9d  jmp     loc_18000A993
```
