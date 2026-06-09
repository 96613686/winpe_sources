# FwFieldParserLUserAuthwClaims(ushort const *,_tag_FW_RULE *)

- ea: `0x180019e80`
- end: `0x180019f28`
- name: `?FwFieldParserLUserAuthwClaims@@YAJPEBGPEAU_tag_FW_RULE@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _tag_FW_RULE *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019e80`
- `0x180019f30`

## import_xrefs

- `fwbase!FwFree` at `0x180019ea5`
- `fwbase!FwFree` at `0x180019f13`
- `fwbase!FwFree` at `0x180019ea5`
- `fwbase!FwFree` at `0x180019f13`
- `fwbase!FwAlloc` at `0x180019ec8`
- `fwbase!FwAlloc` at `0x180019ec8`
- `fwbase!FwStringCopy` at `0x180019f08`
- `fwbase!FwStringCopy` at `0x180019f08`

## pseudocode

```c
__int64 __fastcall FwFieldParserLUserAuthwClaims(const unsigned __int16 *a1, struct _tag_FW_RULE *a2)
{
  char *v2; // r14
  __int64 v4; // rcx
  __int64 v6; // rax
  unsigned int v7; // ebp
  __int64 v8; // rax
  __int64 v9; // rdi
  int v10; // ebx
  char v12; // [rsp+68h] [rbp+10h] BYREF

  v2 = (char *)a2 + 368;
  v4 = *((_QWORD *)a2 + 46);
  if ( v4 )
    FwFree(v4);
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  v7 = 2 * ((unsigned int)(3 * v6) >> 2) + 2;
  v8 = FwAlloc(v7);
  v9 = v8;
  if ( v8 )
  {
    v10 = base64decodeU(a1, v8, v7, &v12);
    if ( v10 >= 0 )
    {
      *((_WORD *)a2 + 146) |= 0x1000u;
      v10 = FwStringCopy(v9, v2);
    }
    FwFree(v9);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019e80  push    rbx
0x180019e82  push    rbp
0x180019e83  push    rsi
0x180019e84  push    rdi
0x180019e85  push    r14
0x180019e87  push    r15
0x180019e89  sub     rsp, 28h
0x180019e8d  lea     r14, [rdx+170h]
0x180019e94  mov     rbx, rcx
0x180019e97  mov     rcx, [r14]
0x180019e9a  xor     r15d, r15d
0x180019e9d  mov     rsi, rdx
0x180019ea0  test    rcx, rcx
0x180019ea3  jz      short loc_180019EAB
0x180019ea5  call    cs:__imp_FwFree
0x180019eab  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019eaf  inc     rax
0x180019eb2  cmp     [rbx+rax*2], r15w
0x180019eb7  jnz     short loc_180019EAF
0x180019eb9  lea     eax, [rax+rax*2]
0x180019ebc  shr     eax, 2
0x180019ebf  lea     ebp, ds:2[rax*2]
0x180019ec6  mov     ecx, ebp
0x180019ec8  call    cs:__imp_FwAlloc
0x180019ece  mov     rdi, rax
0x180019ed1  test    rax, rax
0x180019ed4  jnz     short loc_180019EDD
0x180019ed6  mov     ebx, 8007000Eh
0x180019edb  jmp     short loc_180019F19
0x180019edd  lea     r9, [rsp+58h+arg_8]
0x180019ee2  mov     r8d, ebp
0x180019ee5  mov     rdx, rdi
0x180019ee8  mov     rcx, rbx
0x180019eeb  call    base64decodeU
0x180019ef0  mov     ebx, eax
0x180019ef2  test    eax, eax
0x180019ef4  js      short loc_180019F10
0x180019ef6  mov     eax, 1000h
0x180019efb  mov     rdx, r14
0x180019efe  or      [rsi+124h], ax
0x180019f05  mov     rcx, rdi
0x180019f08  call    cs:__imp_FwStringCopy
0x180019f0e  mov     ebx, eax
0x180019f10  mov     rcx, rdi
0x180019f13  call    cs:__imp_FwFree
0x180019f19  mov     eax, ebx
0x180019f1b  add     rsp, 28h
0x180019f1f  pop     r15
0x180019f21  pop     r14
0x180019f23  pop     rdi
0x180019f24  pop     rsi
0x180019f25  pop     rbp
0x180019f26  pop     rbx
0x180019f27  retn
```
