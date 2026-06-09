# SrpFreePlugins

- ea: `0x14001fd60`
- end: `0x14001fe21`
- name: `SrpFreePlugins`
- size: `193`
- prototype: `__int64 __fastcall(PUNICODE_STRING UnicodeString)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140032dc0`
- `0x140036330`

## callees

- `0x14001fd60`
- `0x140020050`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14001fdbf`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001fe09`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001fdbf`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001fe09`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fd83`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fdf3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fd83`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fdf3`

## pseudocode

```c
void __fastcall SrpFreePlugins(PUNICODE_STRING UnicodeString)
{
  PWSTR Buffer; // rcx
  unsigned int i; // esi
  __int64 v4; // rdi
  void *v5; // rcx

  if ( UnicodeString )
  {
    Buffer = UnicodeString[1].Buffer;
    if ( Buffer )
    {
      ExFreePoolWithTag(Buffer, 0);
      UnicodeString[1].Buffer = 0;
    }
    if ( *(_QWORD *)&UnicodeString[2].Length )
    {
      for ( i = 0; i < LODWORD(UnicodeString[2].Buffer); ++i )
      {
        v4 = 48LL * i;
        RtlFreeUnicodeString((PUNICODE_STRING)(v4 + *(_QWORD *)&UnicodeString[2].Length + 16LL));
        SrpFreePolicy(v4 + *(_QWORD *)&UnicodeString[2].Length);
      }
      v5 = *(void **)&UnicodeString[2].Length;
      if ( v5 )
        ExFreePoolWithTag(v5, 0);
      *(_QWORD *)&UnicodeString[2].Length = 0;
      LODWORD(UnicodeString[2].Buffer) = 0;
    }
    RtlFreeUnicodeString(UnicodeString);
  }
}

```

## disassembly

```asm
0x14001fd60  test    rcx, rcx
0x14001fd63  jz      locret_14001FE1F
0x14001fd69  push    rbx
0x14001fd6a  sub     rsp, 20h
0x14001fd6e  mov     rbx, rcx
0x14001fd71  mov     [rsp+28h+arg_0], rbp
0x14001fd76  mov     rcx, [rcx+18h]; P
0x14001fd7a  xor     ebp, ebp
0x14001fd7c  test    rcx, rcx
0x14001fd7f  jz      short loc_14001FD93
0x14001fd81  xor     edx, edx; Tag
0x14001fd83  call    cs:__imp_ExFreePoolWithTag
0x14001fd8a  nop     dword ptr [rax+rax+00h]
0x14001fd8f  mov     [rbx+18h], rbp
0x14001fd93  cmp     [rbx+20h], rbp
0x14001fd97  jz      short loc_14001FE06
0x14001fd99  mov     [rsp+28h+arg_8], rsi
0x14001fd9e  mov     esi, ebp
0x14001fda0  cmp     [rbx+28h], ebp
0x14001fda3  jbe     short loc_14001FDE3
0x14001fda5  mov     [rsp+28h+arg_10], rdi
0x14001fdaa  mov     rcx, [rbx+20h]
0x14001fdae  mov     eax, esi
0x14001fdb0  add     rcx, 10h
0x14001fdb4  lea     rdi, [rax+rax*2]
0x14001fdb8  shl     rdi, 4
0x14001fdbc  add     rcx, rdi; UnicodeString
0x14001fdbf  call    cs:__imp_RtlFreeUnicodeString
0x14001fdc6  nop     dword ptr [rax+rax+00h]
0x14001fdcb  mov     rcx, [rbx+20h]
0x14001fdcf  add     rcx, rdi
0x14001fdd2  call    SrpFreePolicy
0x14001fdd7  inc     esi
0x14001fdd9  cmp     esi, [rbx+28h]
0x14001fddc  jb      short loc_14001FDAA
0x14001fdde  mov     rdi, [rsp+28h+arg_10]
0x14001fde3  mov     rcx, [rbx+20h]; P
0x14001fde7  mov     rsi, [rsp+28h+arg_8]
0x14001fdec  test    rcx, rcx
0x14001fdef  jz      short loc_14001FDFF
0x14001fdf1  xor     edx, edx; Tag
0x14001fdf3  call    cs:__imp_ExFreePoolWithTag
0x14001fdfa  nop     dword ptr [rax+rax+00h]
0x14001fdff  mov     [rbx+20h], rbp
0x14001fe03  mov     [rbx+28h], ebp
0x14001fe06  mov     rcx, rbx; UnicodeString
0x14001fe09  call    cs:__imp_RtlFreeUnicodeString
0x14001fe10  nop     dword ptr [rax+rax+00h]
0x14001fe15  mov     rbp, [rsp+28h+arg_0]
0x14001fe1a  add     rsp, 20h
0x14001fe1e  pop     rbx
0x14001fe1f  retn
```
