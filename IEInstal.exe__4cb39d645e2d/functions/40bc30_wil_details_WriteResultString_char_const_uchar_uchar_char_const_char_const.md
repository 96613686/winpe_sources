# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x40bc30`
- end: `0x40bc94`
- name: `??$WriteResultString@PBD@details@wil@@YGPAEPAE0PBDPAPBD@Z`
- size: `100`
- prototype: `char *__fastcall(char *Destination, char *, _BYTE *Source, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x40b164`

## callees

- `0x40bc30`

## import_xrefs

- `msvcrt!memcpy_s` at `0x40bc67`
- `msvcrt!memcpy_s` at `0x40bc67`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(char *Destination, char *a2, _BYTE *Source, _DWORD *a4)
{
  unsigned int v6; // edx
  rsize_t v7; // edi
  unsigned int v8; // ebx

  if ( Destination != a2 && Source && *Source && (v6 = strlen(Source), v7 = a2 - Destination, v8 = v6 + 1, v7 >= v6 + 1) )
  {
    _memcpy_s(Destination, v7, Source, v6 + 1);
    if ( a4 )
      *a4 = Destination;
    return &Destination[v8];
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
}

```

## disassembly

```asm
0x40bc30  mov     edi, edi
0x40bc32  push    ebp
0x40bc33  mov     ebp, esp
0x40bc35  push    ebx
0x40bc36  push    esi
0x40bc37  push    edi
0x40bc38  mov     edi, edx
0x40bc3a  mov     esi, ecx
0x40bc3c  cmp     esi, edi
0x40bc3e  jz      short loc_40BC7E
0x40bc40  mov     ecx, [ebp+Source]
0x40bc43  test    ecx, ecx
0x40bc45  jz      short loc_40BC7E
0x40bc47  cmp     byte ptr [ecx], 0
0x40bc4a  jz      short loc_40BC7E
0x40bc4c  mov     edx, ecx
0x40bc4e  lea     ebx, [edx+1]
0x40bc51  mov     al, [edx]
0x40bc53  inc     edx
0x40bc54  test    al, al
0x40bc56  jnz     short loc_40BC51
0x40bc58  sub     edx, ebx
0x40bc5a  sub     edi, esi
0x40bc5c  lea     ebx, [edx+1]
0x40bc5f  cmp     edi, ebx
0x40bc61  jb      short loc_40BC7E
0x40bc63  push    ebx; SourceSize
0x40bc64  push    ecx; Source
0x40bc65  push    edi; DestinationSize
0x40bc66  push    esi; Destination
0x40bc67  call    ds:__imp__memcpy_s
0x40bc6d  mov     eax, [ebp+arg_4]
0x40bc70  add     esp, 10h
0x40bc73  test    eax, eax
0x40bc75  jz      short loc_40BC79
0x40bc77  mov     [eax], esi
0x40bc79  lea     eax, [ebx+esi]
0x40bc7c  jmp     short loc_40BC8D
0x40bc7e  mov     eax, [ebp+arg_4]
0x40bc81  test    eax, eax
0x40bc83  jz      short loc_40BC8B
0x40bc85  mov     dword ptr [eax], 0
0x40bc8b  mov     eax, esi
0x40bc8d  pop     edi
0x40bc8e  pop     esi
0x40bc8f  pop     ebx
0x40bc90  pop     ebp
0x40bc91  retn    8
```
