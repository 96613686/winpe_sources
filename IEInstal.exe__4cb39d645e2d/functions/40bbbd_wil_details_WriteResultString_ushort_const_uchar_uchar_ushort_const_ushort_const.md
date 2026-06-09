# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x40bbbd`
- end: `0x40bc2a`
- name: `??$WriteResultString@PBG@details@wil@@YGPAEPAE0PBGPAPBG@Z`
- size: `109`
- prototype: `char *__fastcall(_BYTE *Destination, _BYTE *, _WORD *Source, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x40b164`

## callees

- `0x40a9f0`
- `0x40bbbd`

## import_xrefs

- `msvcrt!memcpy_s` at `0x40bbff`
- `msvcrt!memcpy_s` at `0x40bbff`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(
        _BYTE *Destination,
        _BYTE *a2,
        _WORD *Source,
        _DWORD *a4)
{
  rsize_t v6; // eax
  rsize_t v7; // ebx
  wil::details *v9; // [esp+0h] [ebp-10h]
  const unsigned __int16 *v10; // [esp+4h] [ebp-Ch]
  rsize_t v11; // [esp+Ch] [ebp-4h]

  if ( Destination == a2 || !Source || !*Source )
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
  v6 = wil::details::ResultStringSize(v9, v10);
  v7 = a2 - Destination;
  v11 = v6;
  if ( v7 < v6 )
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
  _memcpy_s(Destination, v7, Source, v6);
  if ( a4 )
    *a4 = Destination;
  return &Destination[v11];
}

```

## disassembly

```asm
0x40bbbd  mov     edi, edi
0x40bbbf  push    ebp
0x40bbc0  mov     ebp, esp
0x40bbc2  push    ecx
0x40bbc3  push    ebx
0x40bbc4  push    esi; unsigned __int16 *
0x40bbc5  mov     esi, ecx
0x40bbc7  mov     ebx, edx
0x40bbc9  xor     ecx, ecx
0x40bbcb  push    edi; this
0x40bbcc  cmp     esi, ebx
0x40bbce  jz      short loc_40BC18
0x40bbd0  mov     edi, [ebp+Source]
0x40bbd3  test    edi, edi
0x40bbd5  jz      short loc_40BC18
0x40bbd7  cmp     [edi], cx
0x40bbda  jz      short loc_40BC18
0x40bbdc  mov     ecx, edi
0x40bbde  call    ?ResultStringSize@details@wil@@YGIPBG@Z; wil::details::ResultStringSize(ushort const *)
0x40bbe3  sub     ebx, esi
0x40bbe5  mov     [ebp+var_4], eax
0x40bbe8  cmp     ebx, eax
0x40bbea  jnb     short loc_40BBFB
0x40bbec  mov     eax, [ebp+arg_4]
0x40bbef  test    eax, eax
0x40bbf1  jz      short loc_40BC21
0x40bbf3  mov     dword ptr [eax], 0
0x40bbf9  jmp     short loc_40BC21
0x40bbfb  push    eax; SourceSize
0x40bbfc  push    edi; Source
0x40bbfd  push    ebx; DestinationSize
0x40bbfe  push    esi; Destination
0x40bbff  call    ds:__imp__memcpy_s
0x40bc05  mov     eax, [ebp+arg_4]
0x40bc08  add     esp, 10h
0x40bc0b  test    eax, eax
0x40bc0d  jz      short loc_40BC11
0x40bc0f  mov     [eax], esi
0x40bc11  mov     eax, [ebp+var_4]
0x40bc14  add     eax, esi
0x40bc16  jmp     short loc_40BC23
0x40bc18  mov     eax, [ebp+arg_4]
0x40bc1b  test    eax, eax
0x40bc1d  jz      short loc_40BC21
0x40bc1f  mov     [eax], ecx
0x40bc21  mov     eax, esi
0x40bc23  pop     edi
0x40bc24  pop     esi
0x40bc25  pop     ebx
0x40bc26  leave
0x40bc27  retn    8
```
