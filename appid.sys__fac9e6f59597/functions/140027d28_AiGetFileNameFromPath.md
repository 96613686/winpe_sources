# AiGetFileNameFromPath

- ea: `0x140027d28`
- end: `0x140027dc1`
- name: `AiGetFileNameFromPath`
- size: `153`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140036f60`

## callees

- `0x140002df8`
- `0x140027d28`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!wcsrchr` at `0x140027d8b`
- `ntoskrnl!wcsrchr` at `0x140027d8b`

## pseudocode

```c
__int64 __fastcall AiGetFileNameFromPath(PCUNICODE_STRING SourceString)
{
  unsigned __int16 v2; // si
  __int64 Length; // rax
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  unsigned __int16 v7; // bx
  wchar_t *v8; // rax

  v2 = 0;
  if ( SourceString )
  {
    Length = SourceString->Length;
    if ( (_WORD)Length )
    {
      if ( SourceString->Buffer )
      {
        v4 = (wchar_t *)AiAlloc(Length + 2);
        v5 = v4;
        if ( !v4 )
          return 0;
        if ( RtlStringCbCopyUnicodeString(v4, SourceString->Length + 2LL, SourceString) < 0 )
        {
          AiFree(v5);
          return 0;
        }
        v7 = SourceString->Length >> 1;
        v8 = wcsrchr(v5, 0x5Cu);
        if ( v8 )
          v7 -= ((char *)v8 - (char *)v5 + 2) >> 1;
        v2 = v7;
        AiFree(v5);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140027d28  push    rbx
0x140027d2a  push    rbp
0x140027d2b  push    rsi
0x140027d2c  push    rdi
0x140027d2d  sub     rsp, 28h
0x140027d31  xor     ebp, ebp
0x140027d33  mov     rbx, rcx
0x140027d36  mov     esi, ebp
0x140027d38  test    rcx, rcx
0x140027d3b  jz      short loc_140027DB4
0x140027d3d  movzx   eax, word ptr [rcx]
0x140027d40  test    ax, ax
0x140027d43  jz      short loc_140027DB4
0x140027d45  cmp     [rcx+8], rbp
0x140027d49  jz      short loc_140027DB4
0x140027d4b  lea     rcx, [rax+2]
0x140027d4f  call    AiAlloc
0x140027d54  mov     rdi, rax
0x140027d57  test    rax, rax
0x140027d5a  jnz     short loc_140027D60
0x140027d5c  mov     eax, ebp
0x140027d5e  jmp     short loc_140027DB7
0x140027d60  movzx   edx, word ptr [rbx]
0x140027d63  mov     r8, rbx; SourceString
0x140027d66  add     rdx, 2; cbDest
0x140027d6a  mov     rcx, rdi; pszDest
0x140027d6d  call    RtlStringCbCopyUnicodeString
0x140027d72  mov     rcx, rdi; Str
0x140027d75  test    eax, eax
0x140027d77  jns     short loc_140027D80
0x140027d79  call    AiFree
0x140027d7e  jmp     short loc_140027D5C
0x140027d80  movzx   ebx, word ptr [rbx]
0x140027d83  mov     edx, 5Ch ; '\'; Ch
0x140027d88  shr     bx, 1
0x140027d8b  call    cs:__imp_wcsrchr
0x140027d92  nop     dword ptr [rax+rax+00h]
0x140027d97  test    rax, rax
0x140027d9a  jz      short loc_140027DA9
0x140027d9c  sub     rax, rdi
0x140027d9f  add     rax, 2
0x140027da3  sar     rax, 1
0x140027da6  sub     bx, ax
0x140027da9  mov     rcx, rdi
0x140027dac  movzx   esi, bx
0x140027daf  call    AiFree
0x140027db4  movzx   eax, si
0x140027db7  add     rsp, 28h
0x140027dbb  pop     rdi
0x140027dbc  pop     rsi
0x140027dbd  pop     rbp
0x140027dbe  pop     rbx
0x140027dbf  retn
```
