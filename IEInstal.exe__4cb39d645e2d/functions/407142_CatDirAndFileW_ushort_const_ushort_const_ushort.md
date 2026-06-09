# CatDirAndFileW(ushort const *,ushort const *,ushort * *)

- ea: `0x407142`
- end: `0x407234`
- name: `?CatDirAndFileW@@YGHPBG0PAPAG@Z`
- size: `242`
- prototype: `BOOL __userpurge@<eax>(int@<ecx>, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x403ffd`

## callees

- `0x406a93`
- `0x406b37`
- `0x40707d`
- `0x407142`
- `0x40eb27`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x4071c6`
- `ole32!CoTaskMemAlloc` at `0x4071c6`
- `ole32!CoTaskMemFree` at `0x40720e`
- `ole32!CoTaskMemFree` at `0x407219`
- `ole32!CoTaskMemFree` at `0x407224`
- `ole32!CoTaskMemFree` at `0x40720e`
- `ole32!CoTaskMemFree` at `0x407219`
- `ole32!CoTaskMemFree` at `0x407224`

## pseudocode

```c
BOOL __userpurge CatDirAndFileW@<eax>(
        int a1@<ecx>,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  char *v4; // edi
  char *v5; // esi
  char *v6; // ebx
  int v7; // eax
  int v8; // eax
  char *v9; // eax
  const unsigned __int16 *v11; // [esp+0h] [ebp-20h]
  unsigned int v12; // [esp+0h] [ebp-20h]
  const char *v13; // [esp+0h] [ebp-20h]
  char **v14; // [esp+4h] [ebp-1Ch]
  char *v15; // [esp+4h] [ebp-1Ch]
  unsigned __int16 **v16; // [esp+4h] [ebp-1Ch]
  BOOL v17; // [esp+10h] [ebp-10h]
  unsigned int v18; // [esp+14h] [ebp-Ch] BYREF
  LPVOID pv; // [esp+18h] [ebp-8h] BYREF
  size_t Size; // [esp+1Ch] [ebp-4h]

  v4 = 0;
  v17 = 0;
  v5 = 0;
  pv = 0;
  v18 = 0;
  v6 = 0;
  Size = 2;
  if ( a1 )
  {
    v7 = WSZtoSZ((unsigned int)&pv, v11, v14);
    v4 = (char *)pv;
    if ( v7 < 0 )
      goto LABEL_8;
    Size = strlen((const char *)pv) + 2;
  }
  v8 = WSZtoSZ((unsigned int)&v18, v11, v14);
  v5 = (char *)v18;
  if ( v8 >= 0 )
  {
    Size += strlen((const char *)v18);
    v9 = (char *)CoTaskMemAlloc(Size);
    v6 = v9;
    if ( v9 )
    {
      memset(v9, 0, Size);
      if ( CatDirAndFileA(v5, v4, (const char *)Size, v6, v12, v15) )
        v17 = SZtoWSZ((unsigned int)a2, v13, v16) >= 0;
    }
  }
LABEL_8:
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v6 )
    CoTaskMemFree(v6);
  return v17;
}

```

## disassembly

```asm
0x407142  mov     edi, edi
0x407144  push    ebp
0x407145  mov     ebp, esp
0x407147  sub     esp, 14h
0x40714a  push    ebx
0x40714b  push    esi; unsigned __int16 **
0x40714c  push    edi; char *
0x40714d  xor     edi, edi
0x40714f  mov     [ebp+var_10], 0
0x407156  xor     esi, esi
0x407158  mov     [ebp+pv], edi
0x40715b  mov     eax, edx
0x40715d  mov     [ebp+var_C], esi
0x407160  xor     ebx, ebx
0x407162  mov     [ebp+var_14], eax
0x407165  mov     [ebp+Size], 2
0x40716c  test    ecx, ecx
0x40716e  jz      short loc_40719D
0x407170  lea     eax, [ebp+pv]
0x407173  mov     edx, ecx
0x407175  push    eax; unsigned int
0x407176  call    ?WSZtoSZ@@YGJIPBGPAPAD@Z; WSZtoSZ(uint,ushort const *,char * *)
0x40717b  mov     edi, [ebp+pv]
0x40717e  test    eax, eax
0x407180  js      loc_407209
0x407186  mov     ecx, edi
0x407188  lea     edx, [ecx+1]
0x40718b  mov     al, [ecx]
0x40718d  inc     ecx
0x40718e  test    al, al
0x407190  jnz     short loc_40718B
0x407192  sub     ecx, edx
0x407194  lea     eax, [ecx+2]
0x407197  mov     [ebp+Size], eax
0x40719a  mov     eax, [ebp+var_14]
0x40719d  lea     ecx, [ebp+var_C]
0x4071a0  mov     edx, eax
0x4071a2  push    ecx; unsigned int
0x4071a3  call    ?WSZtoSZ@@YGJIPBGPAPAD@Z; WSZtoSZ(uint,ushort const *,char * *)
0x4071a8  mov     esi, [ebp+var_C]
0x4071ab  test    eax, eax
0x4071ad  js      short loc_407209
0x4071af  mov     ecx, esi
0x4071b1  lea     edx, [ecx+1]
0x4071b4  mov     al, [ecx]
0x4071b6  inc     ecx
0x4071b7  test    al, al
0x4071b9  jnz     short loc_4071B4
0x4071bb  mov     eax, [ebp+Size]
0x4071be  sub     ecx, edx
0x4071c0  add     eax, ecx
0x4071c2  push    eax; cb
0x4071c3  mov     [ebp+Size], eax
0x4071c6  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x4071cc  mov     ebx, eax
0x4071ce  test    ebx, ebx
0x4071d0  jz      short loc_407209
0x4071d2  push    [ebp+Size]; Size
0x4071d5  push    0; Val
0x4071d7  push    ebx; void *
0x4071d8  call    _memset
0x4071dd  add     esp, 0Ch
0x4071e0  mov     edx, esi
0x4071e2  mov     ecx, edi
0x4071e4  push    ebx; char *
0x4071e5  push    [ebp+Size]; char *
0x4071e8  call    ?CatDirAndFileA@@YGHPBD0KPAD@Z; CatDirAndFileA(char const *,char const *,ulong,char *)
0x4071ed  test    eax, eax
0x4071ef  jz      short loc_407209
0x4071f1  push    [ebp+arg_0]; unsigned int
0x4071f4  mov     edx, ebx
0x4071f6  call    ?SZtoWSZ@@YGJIPBDPAPAG@Z; SZtoWSZ(uint,char const *,ushort * *)
0x4071fb  mov     ecx, [ebp+var_10]
0x4071fe  xor     edx, edx
0x407200  inc     edx
0x407201  test    eax, eax
0x407203  cmovns  ecx, edx
0x407206  mov     [ebp+var_10], ecx
0x407209  test    edi, edi
0x40720b  jz      short loc_407214
0x40720d  push    edi; pv
0x40720e  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x407214  test    esi, esi
0x407216  jz      short loc_40721F
0x407218  push    esi; pv
0x407219  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x40721f  test    ebx, ebx
0x407221  jz      short loc_40722A
0x407223  push    ebx; pv
0x407224  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x40722a  mov     eax, [ebp+var_10]
0x40722d  pop     edi
0x40722e  pop     esi
0x40722f  pop     ebx
0x407230  leave
0x407231  retn    4
```
