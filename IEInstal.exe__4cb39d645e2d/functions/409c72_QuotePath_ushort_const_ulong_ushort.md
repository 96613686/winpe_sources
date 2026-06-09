# QuotePath(ushort const *,ulong,ushort *)

- ea: `0x409c72`
- end: `0x409d5d`
- name: `?QuotePath@@YGJPBGKPAG@Z`
- size: `235`
- prototype: `int __userpurge@<eax>(int@<edx>, _WORD *@<ecx>, unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x404214`
- `0x409551`

## callees

- `0x409b68`
- `0x409c72`
- `0x40cdbc`
- `0x40eb27`

## pseudocode

```c
int __userpurge QuotePath@<eax>(
        int a1@<edx>,
        _WORD *a2@<ecx>,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  bool v6; // zf
  int v7; // ecx
  int v8; // esi
  unsigned int v9; // ebx
  const wchar_t *v10; // ecx
  int v11; // eax
  int v13; // [esp-4h] [ebp-20h]
  unsigned int *v14; // [esp+0h] [ebp-1Ch]
  unsigned int *v15; // [esp+0h] [ebp-1Ch]
  unsigned int v16; // [esp+4h] [ebp-18h]
  unsigned int v17; // [esp+4h] [ebp-18h]
  int Size; // [esp+Ch] [ebp-10h]
  unsigned __int16 v20[2]; // [esp+14h] [ebp-8h] BYREF
  unsigned int v21; // [esp+18h] [ebp-4h] BYREF

  v13 = 34;
  v6 = *a2 == 34;
  v21 = (unsigned int)a3;
  *(_DWORD *)v20 = a1;
  if ( !v6 )
  {
    v8 = StringCchCopyExW((size_t)L"\"", (unsigned int)&v21, v20, (unsigned __int16 **)0x22, v14, v16);
    if ( v8 < 0 )
      return v8;
    v13 = v7;
  }
  v8 = StringCchCopyExW((size_t)a2, (unsigned int)&v21, v20, (unsigned __int16 **)v13, v14, v16);
  if ( v8 >= 0 )
  {
    v9 = v21;
    v10 = a3 + 1;
    if ( v21 <= (unsigned int)(a3 + 1) || (Size = 2 * a1, v21 >= (unsigned int)&a3[a1]) || *(_WORD *)(v21 - 2) != 34 )
    {
      v11 = StringCchCopyExW((size_t)L"\"", (unsigned int)&v21, v20, (unsigned __int16 **)(a3 + 1), v15, v17);
      v9 = v21;
      v10 = a3 + 1;
      v8 = v11;
      Size = 2 * a1;
    }
    if ( v8 >= 0 && (*a3 != 34 || v9 <= (unsigned int)v10 || wcschr(v10, 0x22u) != (wchar_t *)(v9 - 2)) )
    {
      memset(a3, 0, Size);
      return -2147024809;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x409c72  mov     edi, edi
0x409c74  push    ebp
0x409c75  mov     ebp, esp
0x409c77  sub     esp, 10h
0x409c7a  push    ebx
0x409c7b  push    esi; unsigned int
0x409c7c  push    edi; unsigned int *
0x409c7d  mov     edi, [ebp+arg_0]
0x409c80  mov     ebx, ecx
0x409c82  push    22h ; '"'
0x409c84  pop     ecx
0x409c85  push    ecx; unsigned __int16 **
0x409c86  cmp     cx, [ebx]
0x409c89  mov     eax, edx
0x409c8b  lea     ecx, [ebp+var_8]
0x409c8e  mov     [ebp+var_C], eax
0x409c91  push    ecx; unsigned __int16 *
0x409c92  lea     ecx, [ebp+var_4]
0x409c95  mov     [ebp+var_4], edi
0x409c98  push    ecx; unsigned int
0x409c99  mov     dword ptr [ebp+var_8], eax
0x409c9c  mov     ecx, edi
0x409c9e  jz      short loc_409CC3
0x409ca0  push    offset asc_401D50; "\""
0x409ca5  call    ?StringCchCopyExW@@YGJPAGIPBGPAPAGPAIK@Z; StringCchCopyExW(ushort *,uint,ushort const *,ushort * *,uint *,ulong)
0x409caa  mov     esi, eax
0x409cac  test    esi, esi
0x409cae  js      loc_409D54
0x409cb4  mov     edx, dword ptr [ebp+var_8]
0x409cb7  lea     eax, [ebp+var_8]
0x409cba  push    ecx; unsigned __int16 **
0x409cbb  mov     ecx, [ebp+var_4]
0x409cbe  push    eax; unsigned __int16 *
0x409cbf  lea     eax, [ebp+var_4]
0x409cc2  push    eax; unsigned int
0x409cc3  push    ebx; cchDest
0x409cc4  call    ?StringCchCopyExW@@YGJPAGIPBGPAPAGPAIK@Z; StringCchCopyExW(ushort *,uint,ushort const *,ushort * *,uint *,ulong)
0x409cc9  mov     esi, eax
0x409ccb  test    esi, esi
0x409ccd  js      loc_409D54
0x409cd3  mov     ebx, [ebp+var_4]
0x409cd6  lea     ecx, [edi+2]
0x409cd9  cmp     ebx, ecx
0x409cdb  jbe     short loc_409CF9
0x409cdd  mov     eax, [ebp+var_C]
0x409ce0  lea     edx, [eax+eax]
0x409ce3  lea     eax, [edx+edi]
0x409ce6  mov     [ebp+Size], edx
0x409ce9  cmp     ebx, eax
0x409ceb  jnb     short loc_409CF9
0x409ced  movzx   eax, word ptr [ebx-2]
0x409cf1  push    22h ; '"'
0x409cf3  pop     edx
0x409cf4  cmp     ax, dx
0x409cf7  jz      short loc_409D24
0x409cf9  mov     edx, dword ptr [ebp+var_8]
0x409cfc  lea     eax, [ebp+var_8]
0x409cff  push    ecx; unsigned __int16 **
0x409d00  push    eax; unsigned __int16 *
0x409d01  lea     eax, [ebp+var_4]
0x409d04  mov     ecx, ebx
0x409d06  push    eax; unsigned int
0x409d07  push    offset asc_401D50; "\""
0x409d0c  call    ?StringCchCopyExW@@YGJPAGIPBGPAPAGPAIK@Z; StringCchCopyExW(ushort *,uint,ushort const *,ushort * *,uint *,ulong)
0x409d11  mov     ebx, [ebp+var_4]
0x409d14  lea     ecx, [edi+2]
0x409d17  mov     esi, eax
0x409d19  mov     eax, [ebp+var_C]
0x409d1c  add     eax, eax
0x409d1e  push    22h ; '"'
0x409d20  mov     [ebp+Size], eax
0x409d23  pop     edx
0x409d24  test    esi, esi
0x409d26  js      short loc_409D54
0x409d28  cmp     [edi], dx
0x409d2b  jnz     short loc_409D41
0x409d2d  cmp     ebx, ecx
0x409d2f  jbe     short loc_409D41
0x409d31  push    edx; Ch
0x409d32  push    ecx; Str
0x409d33  call    _wcschr
0x409d38  pop     ecx
0x409d39  pop     ecx
0x409d3a  lea     ecx, [ebx-2]
0x409d3d  cmp     eax, ecx
0x409d3f  jz      short loc_409D54
0x409d41  push    [ebp+Size]; Size
0x409d44  push    0; Val
0x409d46  push    edi; void *
0x409d47  call    _memset
0x409d4c  add     esp, 0Ch
0x409d4f  mov     esi, 80070057h
0x409d54  pop     edi
0x409d55  mov     eax, esi
0x409d57  pop     esi
0x409d58  pop     ebx
0x409d59  leave
0x409d5a  retn    4
```
