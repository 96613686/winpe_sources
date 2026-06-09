# BIsParserFeatureReadable(CPrintCoreConfig *,_FEATURE *)

- ea: `0x180030fb8`
- end: `0x180031006`
- name: `?BIsParserFeatureReadable@@YAHPEAVCPrintCoreConfig@@PEAU_FEATURE@@@Z`
- size: `78`
- prototype: `__int64 __fastcall(struct CPrintCoreConfig *this, struct _FEATURE *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180031170`
- `0x180031aa0`
- `0x1800326f8`

## callees

- `0x180030fb8`
- `0x180032cb0`

## pseudocode

```c
_BOOL8 __fastcall BIsParserFeatureReadable(struct CPrintCoreConfig *this, struct _FEATURE *a2)
{
  _DWORD *v3; // rbx

  v3 = (_DWORD *)((char *)a2 + 44);
  if ( (CPrintCoreConfig::GetHelperSettingsFlags(this) & 2) == 0 && *v3 <= 1u )
    return 0;
  if ( (CPrintCoreConfig::GetHelperSettingsFlags(this) & 8) != 0 )
    return 1;
  return *v3 != 2;
}

```

## disassembly

```asm
0x180030fb8  mov     [rsp+arg_0], rbx
0x180030fbd  push    rdi
0x180030fbe  sub     rsp, 20h
0x180030fc2  mov     rdi, rcx
0x180030fc5  lea     rbx, [rdx+2Ch]
0x180030fc9  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180030fce  test    al, 2
0x180030fd0  jnz     short loc_180030FE0
0x180030fd2  cmp     dword ptr [rbx], 0
0x180030fd5  jz      short loc_180030FDC
0x180030fd7  cmp     dword ptr [rbx], 1
0x180030fda  jnz     short loc_180030FE0
0x180030fdc  xor     eax, eax
0x180030fde  jmp     short loc_180030FFB
0x180030fe0  mov     rcx, rdi; this
0x180030fe3  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180030fe8  test    al, 8
0x180030fea  jnz     short loc_180030FF6
0x180030fec  xor     eax, eax
0x180030fee  cmp     dword ptr [rbx], 2
0x180030ff1  setnz   al
0x180030ff4  jmp     short loc_180030FFB
0x180030ff6  mov     eax, 1
0x180030ffb  mov     rbx, [rsp+28h+arg_0]
0x180031000  add     rsp, 20h
0x180031004  pop     rdi
0x180031005  retn
```
