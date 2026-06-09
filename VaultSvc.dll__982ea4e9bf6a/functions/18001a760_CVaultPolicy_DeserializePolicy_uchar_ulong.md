# CVaultPolicy::DeserializePolicy(uchar *,ulong)

- ea: `0x18001a760`
- end: `0x18001a91e`
- name: `?DeserializePolicy@CVaultPolicy@@QEAAKPEAEK@Z`
- size: `446`
- prototype: `__int64 __fastcall(CVaultPolicy *this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001a134`

## callees

- `0x18001a760`
- `0x18001a924`
- `0x18001aa28`
- `0x18003b7d8`
- `0x18004b43c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a877`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a877`

## pseudocode

```c
__int64 __fastcall CVaultPolicy::DeserializePolicy(CVaultPolicy *this, unsigned __int8 *a2, unsigned int a3)
{
  __int64 v4; // r9
  unsigned int v5; // r8d
  __int128 v6; // xmm0
  __int64 result; // rax
  unsigned __int8 *v8; // rcx
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // edx
  unsigned int v13; // edx
  __int64 v14; // rdi
  char *v15; // r15
  unsigned int v16; // r14d
  HLOCAL v17; // rax
  HLOCAL v18; // rsi
  unsigned __int8 *v19; // [rsp+68h] [rbp+38h] BYREF
  unsigned int v20; // [rsp+70h] [rbp+40h] BYREF

  if ( a3 < 4 )
    return 122;
  v4 = *(unsigned int *)a2;
  *((_DWORD *)this + 2) = v4;
  if ( (_DWORD)v4 != 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1bcaaeb31ffc3bb4f99d800d12d6cb39_Traceguids, v4);
    return 1630;
  }
  v5 = a3 - 4;
  if ( v5 < 0x10 )
    return 122;
  v6 = *(_OWORD *)(a2 + 4);
  v19 = a2 + 20;
  *(_OWORD *)((char *)this + 12) = v6;
  v20 = v5 - 16;
  result = VaultDeserialize(&v19, &v20, (unsigned __int16 **)this + 4);
  if ( (_DWORD)result )
    return result;
  if ( !v20 )
    return 122;
  v8 = v19;
  v9 = v20 - 1;
  *((_BYTE *)this + 44) = *v19;
  if ( !v9 )
    return 122;
  v10 = v9 - 1;
  if ( v10 < 4 )
    return 122;
  v11 = v10 - 4;
  *((_DWORD *)this + 12) = *(_DWORD *)(v8 + 2);
  if ( !v11 )
    return 122;
  v12 = v11 - 1;
  *((_BYTE *)this + 52) = v8[6];
  if ( !v12 )
    return 122;
  v13 = v12 - 1;
  *((_BYTE *)this + 53) = v8[7];
  if ( v13 < 4 )
    return 122;
  *((_DWORD *)this + 10) = *((_DWORD *)v8 + 2);
  if ( v13 - 4 < 4 )
    return 122;
  v14 = *((unsigned int *)v8 + 3);
  v15 = (char *)(v8 + 16);
  v16 = v13 - 8;
  v19 = v8 + 16;
  v20 = v13 - 8;
  if ( (unsigned int)v14 > v13 - 8 )
    return 122;
  if ( (_DWORD)v14 )
  {
    v17 = LocalAlloc(0x40u, (unsigned int)v14);
    v18 = v17;
    if ( !v17 )
      return 14;
    memcpy_0(v17, v15, (unsigned int)v14);
    v19 = (unsigned __int8 *)&v15[v14];
    v20 = v16 - v14;
  }
  else
  {
    v18 = 0;
  }
  *((_DWORD *)this + 14) = v14;
  *((_QWORD *)this + 8) = v18;
  return CVaultGenericPropertyCollection<enum EVaultPropertyId,0>::DeserializeCollection((char *)this + 80, &v19, &v20);
}

```

## disassembly

```asm
0x18001a760  mov     [rsp-28h+arg_0], rbx
0x18001a765  mov     [rsp-28h+arg_18], rsi
0x18001a76a  push    rbp
0x18001a76b  push    rdi
0x18001a76c  push    r12
0x18001a76e  push    r14
0x18001a770  push    r15
0x18001a772  mov     rbp, rsp
0x18001a775  sub     rsp, 30h
0x18001a779  mov     rbx, rcx
0x18001a77c  cmp     r8d, 4
0x18001a780  jb      loc_18001A917
0x18001a786  mov     r9d, [rdx]
0x18001a789  mov     [rcx+8], r9d
0x18001a78d  cmp     r9d, 1
0x18001a791  jnz     loc_18001A8DB
0x18001a797  add     r8d, 0FFFFFFFCh
0x18001a79b  cmp     r8d, 10h
0x18001a79f  jb      loc_18001A917
0x18001a7a5  movups  xmm0, xmmword ptr [rdx+4]
0x18001a7a9  lea     rax, [rdx+14h]
0x18001a7ad  mov     [rbp+arg_8], rax
0x18001a7b1  lea     rdx, [rbp+arg_10]; unsigned int *
0x18001a7b5  lea     eax, [r8-10h]
0x18001a7b9  movdqu  xmmword ptr [rcx+0Ch], xmm0
0x18001a7be  lea     r8, [rcx+20h]; unsigned __int16 **
0x18001a7c2  mov     [rbp+arg_10], eax
0x18001a7c5  lea     rcx, [rbp+arg_8]; unsigned __int8 **
0x18001a7c9  call    ?VaultDeserialize@@YAKAEAPEAEAEAKAEAPEAG@Z; VaultDeserialize(uchar * &,ulong &,ushort * &)
0x18001a7ce  test    eax, eax
0x18001a7d0  jnz     loc_18001A8BE
0x18001a7d6  mov     edx, [rbp+arg_10]
0x18001a7d9  cmp     edx, 1
0x18001a7dc  jb      loc_18001A917
0x18001a7e2  mov     rcx, [rbp+arg_8]
0x18001a7e6  dec     edx
0x18001a7e8  mov     al, [rcx]
0x18001a7ea  mov     [rbx+2Ch], al
0x18001a7ed  cmp     edx, 1
0x18001a7f0  jb      loc_18001A917
0x18001a7f6  dec     edx
0x18001a7f8  cmp     edx, 4
0x18001a7fb  jb      loc_18001A917
0x18001a801  mov     eax, [rcx+2]
0x18001a804  add     edx, 0FFFFFFFCh
0x18001a807  mov     [rbx+30h], eax
0x18001a80a  cmp     edx, 1
0x18001a80d  jb      loc_18001A917
0x18001a813  mov     al, [rcx+6]
0x18001a816  dec     edx
0x18001a818  mov     [rbx+34h], al
0x18001a81b  cmp     edx, 1
0x18001a81e  jb      loc_18001A917
0x18001a824  mov     al, [rcx+7]
0x18001a827  dec     edx
0x18001a829  mov     [rbx+35h], al
0x18001a82c  cmp     edx, 4
0x18001a82f  jb      loc_18001A917
0x18001a835  mov     eax, [rcx+8]
0x18001a838  lea     r14d, [rdx-4]
0x18001a83c  mov     [rbx+28h], eax
0x18001a83f  xorps   xmm0, xmm0
0x18001a842  movups  [rbp+var_10], xmm0
0x18001a846  cmp     r14d, 4
0x18001a84a  jb      loc_18001A917
0x18001a850  mov     edi, [rcx+0Ch]
0x18001a853  lea     r15, [rcx+10h]
0x18001a857  add     r14d, 0FFFFFFFCh
0x18001a85b  mov     [rbp+arg_8], r15
0x18001a85f  mov     [rbp+arg_10], r14d
0x18001a863  cmp     edi, r14d
0x18001a866  ja      loc_18001A917
0x18001a86c  test    edi, edi
0x18001a86e  jz      short loc_18001A8D5
0x18001a870  mov     edx, edi; uBytes
0x18001a872  mov     ecx, 40h ; '@'; uFlags
0x18001a877  call    cs:__imp_LocalAlloc
0x18001a87d  mov     rsi, rax
0x18001a880  test    rax, rax
0x18001a883  jz      loc_18001A910
0x18001a889  mov     r8d, edi; Size
0x18001a88c  mov     rdx, r15; Src
0x18001a88f  mov     rcx, rax; void *
0x18001a892  call    memcpy_0
0x18001a897  lea     rax, [rdi+r15]
0x18001a89b  sub     r14d, edi
0x18001a89e  mov     [rbp+arg_8], rax
0x18001a8a2  mov     [rbp+arg_10], r14d
0x18001a8a6  lea     rcx, [rbx+50h]
0x18001a8aa  mov     [rbx+38h], edi
0x18001a8ad  lea     r8, [rbp+arg_10]
0x18001a8b1  mov     [rbx+40h], rsi
0x18001a8b5  lea     rdx, [rbp+arg_8]
0x18001a8b9  call    ?DeserializeCollection@?$CVaultGenericPropertyCollection@W4EVaultPropertyId@@$0A@@@QEAAKAEAPEAEAEAK@Z; CVaultGenericPropertyCollection<EVaultPropertyId,0>::DeserializeCollection(uchar * &,ulong &)
0x18001a8be  mov     rbx, [rsp+30h+arg_0]
0x18001a8c3  mov     rsi, [rsp+30h+arg_18]
0x18001a8c8  add     rsp, 30h
0x18001a8cc  pop     r15
0x18001a8ce  pop     r14
0x18001a8d0  pop     r12
0x18001a8d2  pop     rdi
0x18001a8d3  pop     rbp
0x18001a8d4  retn
0x18001a8d5  mov     rsi, qword ptr [rbp+var_10+8]
0x18001a8d9  jmp     short loc_18001A8A6
0x18001a8db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8e2  lea     rax, WPP_GLOBAL_Control
0x18001a8e9  cmp     rcx, rax
0x18001a8ec  jz      short loc_18001A909
0x18001a8ee  test    byte ptr [rcx+1Ch], 2
0x18001a8f2  jz      short loc_18001A909
0x18001a8f4  mov     rcx, [rcx+10h]
0x18001a8f8  lea     r8, WPP_1bcaaeb31ffc3bb4f99d800d12d6cb39_Traceguids
0x18001a8ff  mov     edx, 0Ah
0x18001a904  call    WPP_SF_d
0x18001a909  mov     eax, 65Eh
0x18001a90e  jmp     short loc_18001A8BE
0x18001a910  mov     eax, 0Eh
0x18001a915  jmp     short loc_18001A8BE
0x18001a917  mov     eax, 7Ah ; 'z'
0x18001a91c  jmp     short loc_18001A8BE
```
