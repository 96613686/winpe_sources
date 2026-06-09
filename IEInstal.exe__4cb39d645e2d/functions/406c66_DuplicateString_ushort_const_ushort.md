# DuplicateString(ushort const *,ushort * *)

- ea: `0x406c66`
- end: `0x406d2b`
- name: `?DuplicateString@@YGJPBGPAPAG@Z`
- size: `197`
- prototype: `int __fastcall(size_t, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x40777d`

## callees

- `0x402dc4`
- `0x4061f0`
- `0x406c66`
- `0x40eb27`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x406cd5`
- `ole32!CoTaskMemAlloc` at `0x406cd5`
- `ole32!CoTaskMemFree` at `0x406d02`
- `ole32!CoTaskMemFree` at `0x406d02`

## pseudocode

```c
int __fastcall DuplicateString(size_t a1, _DWORD *a2)
{
  _WORD *v2; // eax
  void *v3; // edi
  int v4; // ecx
  int v5; // esi
  unsigned int v6; // eax
  void *v7; // eax
  unsigned int v9; // [esp+0h] [ebp-18h]
  unsigned int v10; // [esp+0h] [ebp-18h]
  unsigned int *v11; // [esp+4h] [ebp-14h]
  const unsigned __int16 *v12; // [esp+4h] [ebp-14h]
  SIZE_T cb; // [esp+14h] [ebp-4h] BYREF

  v2 = (_WORD *)a1;
  v3 = 0;
  if ( !a1 )
    return -2147024809;
  v4 = 2147483646;
  do
  {
    if ( !*v2 )
      break;
    ++v2;
    --v4;
  }
  while ( v4 );
  v5 = -2147024809;
  if ( v4 )
    v5 = 0;
  v6 = v4 != 0 ? 2147483646 - v4 : 0;
  if ( v4 )
  {
    if ( v6 )
    {
      if ( v6 + 1 < v6 )
      {
        v5 = -2147024362;
      }
      else
      {
        cb = 0;
        v5 = ULongMult((unsigned int)&cb, v9, v11);
        if ( v5 >= 0 )
        {
          v7 = CoTaskMemAlloc(cb);
          v3 = v7;
          if ( v7 )
          {
            memset(v7, 0, cb);
            v5 = StringCchCopyW(a1, v10, v12);
            if ( v5 < 0 )
            {
              CoTaskMemFree(v3);
              v3 = 0;
            }
          }
          else
          {
            v5 = -2147024882;
          }
        }
      }
    }
    *a2 = v3;
  }
  return v5;
}

```

## disassembly

```asm
0x406c66  mov     edi, edi
0x406c68  push    ebp
0x406c69  mov     ebp, esp
0x406c6b  sub     esp, 0Ch
0x406c6e  push    ebx
0x406c6f  mov     eax, ecx
0x406c71  mov     [ebp+var_C], edx
0x406c74  push    esi; unsigned __int16 *
0x406c75  xor     ebx, ebx
0x406c77  mov     [ebp+cchDest], eax
0x406c7a  push    edi; unsigned int
0x406c7b  mov     edi, ebx
0x406c7d  test    eax, eax
0x406c7f  jz      loc_406D1F
0x406c85  mov     edx, 7FFFFFFEh
0x406c8a  mov     ecx, edx
0x406c8c  cmp     [eax], bx
0x406c8f  jz      short loc_406C99
0x406c91  add     eax, 2
0x406c94  sub     ecx, 1
0x406c97  jnz     short loc_406C8C
0x406c99  xor     eax, eax
0x406c9b  mov     esi, 80070057h
0x406ca0  test    ecx, ecx
0x406ca2  cmovnz  esi, eax
0x406ca5  sub     edx, ecx
0x406ca7  mov     eax, ecx
0x406ca9  neg     eax
0x406cab  sbb     eax, eax
0x406cad  and     eax, edx
0x406caf  test    ecx, ecx
0x406cb1  jz      short loc_406D24
0x406cb3  test    eax, eax
0x406cb5  jz      short loc_406D18
0x406cb7  lea     ebx, [eax+1]
0x406cba  cmp     ebx, eax
0x406cbc  jb      short loc_406D13
0x406cbe  lea     eax, [ebp+cb]
0x406cc1  mov     [ebp+cb], edi
0x406cc4  push    eax; unsigned int
0x406cc5  mov     ecx, ebx
0x406cc7  call    ?ULongMult@@YGJKKPAK@Z; ULongMult(ulong,ulong,ulong *)
0x406ccc  mov     esi, eax
0x406cce  test    esi, esi
0x406cd0  js      short loc_406D18
0x406cd2  push    [ebp+cb]; cb
0x406cd5  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x406cdb  mov     edi, eax
0x406cdd  test    edi, edi
0x406cdf  jz      short loc_406D0C
0x406ce1  push    [ebp+cb]; Size
0x406ce4  push    0; Val
0x406ce6  push    edi; void *
0x406ce7  call    _memset
0x406cec  add     esp, 0Ch
0x406cef  mov     edx, ebx
0x406cf1  mov     ecx, edi
0x406cf3  push    [ebp+cchDest]; cchDest
0x406cf6  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x406cfb  mov     esi, eax
0x406cfd  test    esi, esi
0x406cff  jns     short loc_406D18
0x406d01  push    edi; pv
0x406d02  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x406d08  xor     edi, edi
0x406d0a  jmp     short loc_406D18
0x406d0c  mov     esi, 8007000Eh
0x406d11  jmp     short loc_406D18
0x406d13  mov     esi, 80070216h
0x406d18  mov     eax, [ebp+var_C]
0x406d1b  mov     [eax], edi
0x406d1d  jmp     short loc_406D24
0x406d1f  mov     esi, 80070057h
0x406d24  pop     edi
0x406d25  mov     eax, esi
0x406d27  pop     esi
0x406d28  pop     ebx
0x406d29  leave
0x406d2a  retn
```
