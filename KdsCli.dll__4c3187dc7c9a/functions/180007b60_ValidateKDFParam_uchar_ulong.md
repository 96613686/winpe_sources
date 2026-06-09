# ValidateKDFParam(uchar *,ulong)

- ea: `0x180007b60`
- end: `0x180007c17`
- name: `?ValidateKDFParam@@YAJPEAEK@Z`
- size: `183`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005a24`
- `0x180007354`
- `0x180007c20`

## callees

- `0x180007b60`
- `0x18001a450`

## string_xrefs

- `0x180007bf2`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`

## pseudocode

```c
__int64 __fastcall ValidateKDFParam(unsigned __int8 *a1, unsigned int a2)
{
  unsigned int v2; // r8d
  char v3; // r9
  unsigned int v4; // ebx
  unsigned int v5; // r9d
  unsigned __int8 *v6; // rcx
  int v7; // r10d
  unsigned int v8; // eax
  __int64 v9; // r11

  v2 = 8;
  if ( a2 < 8 )
  {
    v3 = -121;
LABEL_19:
    v4 = -2146893819;
    SidKeyDebugTraceError(5, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx", v3);
    return v4;
  }
  v4 = 0;
  if ( *(_DWORD *)a1 || (v5 = *((_DWORD *)a1 + 1), v5 > 0xA) )
  {
    v3 = -112;
    goto LABEL_19;
  }
  v6 = a1 + 8;
  v7 = 0;
  if ( v5 )
  {
    while ( 1 )
    {
      v8 = v2 + 8;
      if ( v2 + 8 < v2 || a2 < v8 )
        break;
      v9 = *(unsigned int *)v6;
      v2 = v9 + v8;
      if ( (unsigned int)v9 + v8 < v8 || a2 < v2 )
      {
        v3 = -92;
        goto LABEL_19;
      }
      if ( *((_DWORD *)v6 + 1) == 17 )
      {
        v3 = -84;
        goto LABEL_19;
      }
      if ( ++v7 >= v5 )
        goto LABEL_16;
      v6 += v9 + 8;
    }
    v3 = -100;
    goto LABEL_19;
  }
LABEL_16:
  if ( v2 != a2 )
  {
    v3 = -74;
    goto LABEL_19;
  }
  return v4;
}

```

## disassembly

```asm
0x180007b60  push    rbx
0x180007b62  sub     rsp, 20h
0x180007b66  mov     r8d, 8
0x180007b6c  cmp     edx, r8d
0x180007b6f  jnb     short loc_180007B77
0x180007b71  lea     r9d, [r8+7Fh]
0x180007b75  jmp     short loc_180007BF2
0x180007b77  xor     ebx, ebx
0x180007b79  cmp     [rcx], ebx
0x180007b7b  jnz     short loc_180007BEC
0x180007b7d  mov     r9d, [rcx+4]
0x180007b81  cmp     r9d, 0Ah
0x180007b85  ja      short loc_180007BEC
0x180007b87  add     rcx, r8
0x180007b8a  mov     r10d, ebx
0x180007b8d  test    r9d, r9d
0x180007b90  jz      short loc_180007BDF
0x180007b92  lea     eax, [r8+8]
0x180007b96  cmp     eax, r8d
0x180007b99  jb      short loc_180007BD7
0x180007b9b  cmp     edx, eax
0x180007b9d  jb      short loc_180007BD7
0x180007b9f  mov     r11d, [rcx]
0x180007ba2  lea     r8d, [r11+rax]
0x180007ba6  cmp     r8d, eax
0x180007ba9  jb      short loc_180007BCF
0x180007bab  cmp     edx, r8d
0x180007bae  jb      short loc_180007BCF
0x180007bb0  cmp     dword ptr [rcx+4], 11h
0x180007bb4  jz      short loc_180007BC7
0x180007bb6  inc     r10d
0x180007bb9  cmp     r10d, r9d
0x180007bbc  jnb     short loc_180007BDF
0x180007bbe  add     rcx, 8
0x180007bc2  add     rcx, r11
0x180007bc5  jmp     short loc_180007B92
0x180007bc7  mov     r9d, 0ACh
0x180007bcd  jmp     short loc_180007BF2
0x180007bcf  mov     r9d, 0A4h
0x180007bd5  jmp     short loc_180007BF2
0x180007bd7  mov     r9d, 9Ch
0x180007bdd  jmp     short loc_180007BF2
0x180007bdf  cmp     r8d, edx
0x180007be2  jz      short loc_180007C0F
0x180007be4  mov     r9d, 0B6h
0x180007bea  jmp     short loc_180007BF2
0x180007bec  mov     r9d, 90h; unsigned int
0x180007bf2  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007bf9  mov     ecx, 80090005h; unsigned int
0x180007bfe  lea     rdx, aHr; "hr"
0x180007c05  mov     ebx, 80090005h
0x180007c0a  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007c0f  mov     eax, ebx
0x180007c11  add     rsp, 20h
0x180007c15  pop     rbx
0x180007c16  retn
```
