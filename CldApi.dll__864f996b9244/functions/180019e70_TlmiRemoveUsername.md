# TlmiRemoveUsername

- ea: `0x180019e70`
- end: `0x180019f40`
- name: `TlmiRemoveUsername`
- size: `208`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180017728`
- `0x180018f70`
- `0x180019f50`

## callees

- `0x180019e70`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180019ec0`
- `ntdll!RtlEqualUnicodeString` at `0x180019ec0`

## pseudocode

```c
unsigned __int64 __fastcall TlmiRemoveUsername(WCHAR *a1, USHORT a2)
{
  unsigned __int64 result; // rax
  char *v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  PWSTR v7; // rdi
  PWSTR Buffer; // rcx
  UNICODE_STRING String1; // [rsp+20h] [rbp-18h] BYREF

  *(_DWORD *)(&String1.MaximumLength + 1) = 0;
  String1.MaximumLength = a2;
  String1.Buffer = a1;
  result = String2.Length;
  String1.Length = String2.Length;
  if ( String2.Length > 2u )
  {
    v3 = (char *)a1 + a2;
    while ( 1 )
    {
      result += (unsigned __int64)a1;
      if ( result >= (unsigned __int64)v3 )
        break;
      if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
      {
        v4 = String2.Length >> 1;
        v5 = (unsigned int)v4;
        if ( (int)v4 - 2 >= 1 )
        {
          v6 = (unsigned __int64)(2 * v4 - 4) >> 1;
          v7 = String1.Buffer + 1;
          while ( v6 )
          {
            *v7++ = 42;
            --v6;
          }
        }
        Buffer = &String1.Buffer[v5 - 2];
      }
      else
      {
        Buffer = String1.Buffer;
      }
      a1 = Buffer + 1;
      String1.MaximumLength -= 2;
      result = String2.Length;
      String1.Buffer = a1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019e70  mov     rax, rsp
0x180019e73  mov     [rax+8], rbx
0x180019e77  mov     [rax+10h], rsi
0x180019e7b  push    rdi
0x180019e7c  sub     rsp, 30h
0x180019e80  mov     dword ptr [rax-14h], 0
0x180019e87  mov     esi, 2
0x180019e8c  mov     [rax-16h], dx
0x180019e90  mov     [rax-10h], rcx
0x180019e94  movzx   eax, cs:String2.Length
0x180019e9b  mov     [rsp+38h+String1.Length], ax
0x180019ea0  cmp     ax, si
0x180019ea3  jbe     loc_180019F30
0x180019ea9  movzx   ebx, dx
0x180019eac  add     rbx, rcx
0x180019eaf  jmp     short loc_180019F28
0x180019eb1  mov     r8b, 1; CaseInsensitive
0x180019eb4  lea     rdx, String2; String2
0x180019ebb  lea     rcx, [rsp+38h+String1]; String1
0x180019ec0  call    cs:__imp_RtlEqualUnicodeString
0x180019ec6  test    al, al
0x180019ec8  jz      short loc_180019F0A
0x180019eca  movzx   ecx, cs:String2.Length
0x180019ed1  shr     ecx, 1
0x180019ed3  mov     edx, ecx
0x180019ed5  lea     eax, [rcx-2]
0x180019ed8  cmp     eax, 1
0x180019edb  jl      short loc_180019EFB
0x180019edd  mov     rdi, [rsp+38h+String1.Buffer]
0x180019ee2  lea     rcx, ds:0FFFFFFFFFFFFFFFCh[rcx*2]
0x180019eea  shr     rcx, 1
0x180019eed  mov     eax, 2Ah ; '*'
0x180019ef2  add     rdi, rsi
0x180019ef5  movzx   eax, ax
0x180019ef8  rep stosw
0x180019efb  mov     rcx, [rsp+38h+String1.Buffer]
0x180019f00  add     rcx, 0FFFFFFFFFFFFFFFCh
0x180019f04  lea     rcx, [rcx+rdx*2]
0x180019f08  jmp     short loc_180019F0F
0x180019f0a  mov     rcx, [rsp+38h+String1.Buffer]
0x180019f0f  add     rcx, rsi
0x180019f12  mov     eax, 0FFFEh
0x180019f17  add     [rsp+38h+String1.MaximumLength], ax
0x180019f1c  movzx   eax, cs:String2.Length
0x180019f23  mov     [rsp+38h+String1.Buffer], rcx
0x180019f28  add     rax, rcx
0x180019f2b  cmp     rax, rbx
0x180019f2e  jb      short loc_180019EB1
0x180019f30  mov     rbx, [rsp+38h+arg_0]
0x180019f35  mov     rsi, [rsp+38h+arg_8]
0x180019f3a  add     rsp, 30h
0x180019f3e  pop     rdi
0x180019f3f  retn
```
