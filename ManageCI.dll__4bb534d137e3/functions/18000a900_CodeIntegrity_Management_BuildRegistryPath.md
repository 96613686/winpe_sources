# CodeIntegrity::Management::BuildRegistryPath

- ea: `0x18000a900`
- end: `0x18000a9be`
- name: `CodeIntegrity::Management::BuildRegistryPath`
- size: `190`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b878`

## callees

- `0x18000a900`
- `0x18000c860`
- `0x18000c888`
- `0x18000c958`
- `0x180028160`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000a9a1`
- `ntdll!RtlInitUnicodeString` at `0x18000a9a1`
- `ntdll!RtlFreeUnicodeString` at `0x18000a9ad`
- `ntdll!RtlFreeUnicodeString` at `0x18000a9ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CodeIntegrity::Management::BuildRegistryPath(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        _UNICODE_STRING *a3)
{
  int v6; // ebx
  int v7; // eax
  const unsigned __int16 *v8; // rdx
  _UNICODE_STRING v9; // xmm1
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  DestinationString = 0;
  v6 = RtlULongToUShort(a1->Length + (unsigned int)a2->Length + 4, &DestinationString.MaximumLength);
  if ( v6 >= 0 )
  {
    DestinationString.Buffer = (PWSTR)SbeAlloc(DestinationString.MaximumLength);
    if ( DestinationString.Buffer )
    {
      v7 = RtlUnicodeStringCat(&DestinationString, a1);
      if ( v7 < 0 || (v7 = RtlUnicodeStringCatString(&DestinationString, v8), v7 < 0) )
      {
        v6 = v7;
      }
      else
      {
        v6 = RtlUnicodeStringCat(&DestinationString, a2);
        if ( v6 >= 0 )
        {
          v9 = DestinationString;
          DestinationString = 0;
          *a3 = v9;
          RtlInitUnicodeString(&DestinationString, 0);
        }
      }
    }
    else
    {
      v6 = -1073741801;
    }
  }
  RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000a900  push    rbx
0x18000a902  push    rbp
0x18000a903  push    rsi
0x18000a904  push    rdi
0x18000a905  sub     rsp, 38h
0x18000a909  mov     rbp, r8
0x18000a90c  mov     rsi, rdx
0x18000a90f  mov     rdi, rcx
0x18000a912  xorps   xmm0, xmm0
0x18000a915  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18000a91a  movzx   r9d, word ptr [rcx]
0x18000a91e  movzx   ecx, word ptr [rdx]
0x18000a921  add     ecx, 4
0x18000a924  add     ecx, r9d; unsigned int
0x18000a927  lea     rdx, [rsp+58h+DestinationString.MaximumLength]; unsigned __int16 *
0x18000a92c  call    ?RtlULongToUShort@@YAJKPEAG@Z; RtlULongToUShort(ulong,ushort *)
0x18000a931  mov     ebx, eax
0x18000a933  test    eax, eax
0x18000a935  js      short loc_18000A9A8
0x18000a937  movzx   ecx, [rsp+58h+DestinationString.MaximumLength]
0x18000a93c  call    SbeAlloc
0x18000a941  mov     [rsp+58h+DestinationString.Buffer], rax
0x18000a946  test    rax, rax
0x18000a949  jnz     short loc_18000A952
0x18000a94b  mov     ebx, 0C0000017h
0x18000a950  jmp     short loc_18000A9A8
0x18000a952  mov     rdx, rdi; struct _UNICODE_STRING *
0x18000a955  lea     rcx, [rsp+58h+DestinationString]; struct _UNICODE_STRING *
0x18000a95a  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x18000a95f  test    eax, eax
0x18000a961  jns     short loc_18000A967
0x18000a963  mov     ebx, eax
0x18000a965  jmp     short loc_18000A9A8
0x18000a967  lea     rcx, [rsp+58h+DestinationString]; struct _UNICODE_STRING *
0x18000a96c  call    ?RtlUnicodeStringCatString@@YAJPEAU_UNICODE_STRING@@PEBG@Z; RtlUnicodeStringCatString(_UNICODE_STRING *,ushort const *)
0x18000a971  test    eax, eax
0x18000a973  js      short loc_18000A963
0x18000a975  mov     rdx, rsi; struct _UNICODE_STRING *
0x18000a978  lea     rcx, [rsp+58h+DestinationString]; struct _UNICODE_STRING *
0x18000a97d  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x18000a982  mov     ebx, eax
0x18000a984  test    eax, eax
0x18000a986  js      short loc_18000A9A8
0x18000a988  movaps  xmm1, xmmword ptr [rsp+58h+DestinationString.Length]
0x18000a98d  xorps   xmm0, xmm0
0x18000a990  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18000a995  movdqu  xmmword ptr [rbp+0], xmm1
0x18000a99a  xor     edx, edx; SourceString
0x18000a99c  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18000a9a1  call    cs:__imp_RtlInitUnicodeString
0x18000a9a7  nop
0x18000a9a8  lea     rcx, [rsp+58h+DestinationString]; UnicodeString
0x18000a9ad  call    cs:__imp_RtlFreeUnicodeString
0x18000a9b3  mov     eax, ebx
0x18000a9b5  add     rsp, 38h
0x18000a9b9  pop     rdi
0x18000a9ba  pop     rsi
0x18000a9bb  pop     rbp
0x18000a9bc  pop     rbx
0x18000a9bd  retn
```
