# CoAllocString(ushort const *,ushort * *)

- ea: `0x4066fc`
- end: `0x40677b`
- name: `?CoAllocString@@YGJPBGPAPAG@Z`
- size: `127`
- prototype: `int __fastcall(unsigned __int16 *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x408a2f`

## callees

- `0x4063af`
- `0x4066fc`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x406740`
- `ole32!CoTaskMemAlloc` at `0x406740`

## pseudocode

```c
int __fastcall CoAllocString(unsigned __int16 *a1, _DWORD *a2)
{
  unsigned __int16 *v2; // esi
  unsigned __int16 *v4; // ecx
  unsigned int v6; // esi
  unsigned int v7; // ebx
  LPVOID v8; // eax
  int v9; // edi
  const unsigned __int16 *v11; // [esp-Ch] [ebp-1Ch]
  unsigned int v12; // [esp-8h] [ebp-18h]
  unsigned __int16 **v13; // [esp-4h] [ebp-14h]
  unsigned int *v14; // [esp+0h] [ebp-10h]
  unsigned int v15; // [esp+4h] [ebp-Ch]

  v2 = a1;
  v4 = a1 + 1;
  while ( *v2++ )
    ;
  *a2 = 0;
  v6 = v2 - v4;
  v7 = v6 + 1;
  if ( v6 + 1 < v6 )
    return -2147024362;
  *a2 = 0;
  if ( !is_mul_ok(2u, v7) )
    return -2147024362;
  v8 = CoTaskMemAlloc(2 * v7);
  *a2 = v8;
  v9 = 0;
  if ( !v8 )
    v9 = -2147024882;
  if ( v9 >= 0 )
    StringCchCopyNExW(a1, v6, v11, v12, v13, v14, v15);
  return v9;
}

```

## disassembly

```asm
0x4066fc  mov     edi, edi
0x4066fe  push    ebp
0x4066ff  mov     ebp, esp
0x406701  push    ecx
0x406702  push    ebx
0x406703  mov     eax, ecx
0x406705  push    esi; unsigned int
0x406706  mov     esi, eax
0x406708  mov     [ebp+var_4], eax
0x40670b  push    edi; unsigned int *
0x40670c  mov     edi, edx
0x40670e  xor     edx, edx
0x406710  lea     ecx, [esi+2]
0x406713  mov     ax, [esi]
0x406716  add     esi, 2
0x406719  cmp     ax, dx
0x40671c  jnz     short loc_406713
0x40671e  sub     esi, ecx
0x406720  mov     [edi], edx
0x406722  sar     esi, 1
0x406724  lea     ebx, [esi+1]
0x406727  cmp     ebx, esi
0x406729  jb      short loc_40676F
0x40672b  push    2
0x40672d  mov     eax, ebx
0x40672f  mov     [edi], edx
0x406731  pop     ecx
0x406732  mul     ecx
0x406734  test    edx, edx
0x406736  ja      short loc_40676F
0x406738  jb      short loc_40673F
0x40673a  cmp     eax, 0FFFFFFFFh
0x40673d  ja      short loc_40676F
0x40673f  push    eax; unsigned __int16 **
0x406740  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x406746  test    eax, eax
0x406748  mov     [edi], eax
0x40674a  mov     ecx, eax
0x40674c  mov     edx, 8007000Eh
0x406751  cmovnz  ecx, eax
0x406754  xor     edi, edi
0x406756  test    eax, eax
0x406758  cmovz   edi, edx
0x40675b  test    edi, edi
0x40675d  js      short loc_406774
0x40675f  sub     esp, 0Ch
0x406762  mov     edx, ebx
0x406764  push    esi; unsigned int
0x406765  push    [ebp+var_4]; unsigned __int16 *
0x406768  call    ?StringCchCopyNExW@@YGJPAGIPBGIPAPAGPAIK@Z; StringCchCopyNExW(ushort *,uint,ushort const *,uint,ushort * *,uint *,ulong)
0x40676d  jmp     short loc_406774
0x40676f  mov     edi, 80070216h
0x406774  mov     eax, edi
0x406776  pop     edi
0x406777  pop     esi
0x406778  pop     ebx
0x406779  leave
0x40677a  retn
```
