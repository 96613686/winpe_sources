# Counter_CreateCommonBufferInstance

- ea: `0x14007feb8`
- end: `0x14007ffb2`
- name: `Counter_CreateCommonBufferInstance`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140074008`

## callees

- `0x1400450b8`
- `0x140059970`
- `0x14007feb8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14007ff4d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007ff4d`
- `ntoskrnl!PcwCreateInstance` at `0x14007ff8a`
- `ntoskrnl!PcwCreateInstance` at `0x14007ff8a`

## pseudocode

```c
NTSTATUS __fastcall Counter_CreateCommonBufferInstance(PPCW_INSTANCE *a1)
{
  NTSTATUS result; // eax
  PPCW_INSTANCE v3; // r9
  int Data; // [rsp+20h] [rbp-58h]
  struct _PCW_DATA v5; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  wchar_t pszDest[12]; // [rsp+50h] [rbp-28h] BYREF

  result = g_WdfDriverUsbXhciContext;
  DestinationString = 0;
  if ( *(_BYTE *)(g_WdfDriverUsbXhciContext + 28) && !a1[2] )
  {
    v3 = *a1;
    Data = *((_DWORD *)*a1 + 44);
    if ( *((_DWORD *)*a1 + 161) == 1 )
      RtlStringCchPrintfW(pszDest, 0xAu, L"%04X.%u", *((unsigned __int16 *)v3 + 324), Data);
    else
      RtlStringCchPrintfW(pszDest, 0xAu, L"%S.%u", (char *)v3 + 704, Data);
    RtlInitUnicodeString(&DestinationString, pszDest);
    v5.Data = a1[1];
    v5.Size = 16;
    return PcwCreateInstance(a1 + 2, Ctr_CommonBuffer, &DestinationString, 1u, &v5);
  }
  return result;
}

```

## disassembly

```asm
0x14007feb8  mov     [rsp+arg_8], rbx
0x14007febd  push    rdi
0x14007febe  sub     rsp, 70h
0x14007fec2  mov     rax, cs:__security_cookie
0x14007fec9  xor     rax, rsp
0x14007fecc  mov     [rsp+78h+var_10], rax
0x14007fed1  mov     rax, cs:g_WdfDriverUsbXhciContext
0x14007fed8  xorps   xmm0, xmm0
0x14007fedb  mov     rbx, rcx
0x14007fede  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x14007fee3  cmp     byte ptr [rax+1Ch], 0
0x14007fee7  jz      loc_14007FF96
0x14007feed  cmp     qword ptr [rcx+10h], 0
0x14007fef2  jnz     loc_14007FF96
0x14007fef8  mov     r9, [rcx]
0x14007fefb  mov     edx, 0Ah; cchDest
0x14007ff00  lea     rcx, [rsp+78h+pszDest]; pszDest
0x14007ff05  cmp     dword ptr [r9+284h], 1
0x14007ff0d  mov     eax, [r9+0B0h]
0x14007ff14  mov     [rsp+78h+Data], eax
0x14007ff18  jnz     short loc_14007FF30
0x14007ff1a  movzx   r9d, word ptr [r9+288h]
0x14007ff22  lea     r8, a04xU; "%04X.%u"
0x14007ff29  call    RtlStringCchPrintfW
0x14007ff2e  jmp     short loc_14007FF43
0x14007ff30  add     r9, 2C0h
0x14007ff37  lea     r8, aSU; "%S.%u"
0x14007ff3e  call    RtlStringCchPrintfW
0x14007ff43  lea     rdx, [rsp+78h+pszDest]; SourceString
0x14007ff48  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x14007ff4d  call    cs:__imp_RtlInitUnicodeString
0x14007ff54  nop     dword ptr [rax+rax+00h]
0x14007ff59  mov     rax, [rbx+8]
0x14007ff5d  lea     r8, [rsp+78h+DestinationString]; Name
0x14007ff62  mov     rdx, cs:Ctr_CommonBuffer; Registration
0x14007ff69  lea     rcx, [rbx+10h]; Instance
0x14007ff6d  mov     [rsp+78h+var_48.Data], rax
0x14007ff72  mov     r9d, 1; Count
0x14007ff78  lea     rax, [rsp+78h+var_48]
0x14007ff7d  mov     [rsp+78h+var_48.Size], 10h
0x14007ff85  mov     qword ptr [rsp+78h+Data], rax; Data
0x14007ff8a  call    cs:__imp_PcwCreateInstance
0x14007ff91  nop     dword ptr [rax+rax+00h]
0x14007ff96  mov     rcx, [rsp+78h+var_10]
0x14007ff9b  xor     rcx, rsp; StackCookie
0x14007ff9e  call    __security_check_cookie
0x14007ffa3  mov     rbx, [rsp+78h+arg_8]
0x14007ffab  add     rsp, 70h
0x14007ffaf  pop     rdi
0x14007ffb0  retn
```
