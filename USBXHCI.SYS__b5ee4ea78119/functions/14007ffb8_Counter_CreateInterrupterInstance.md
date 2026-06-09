# Counter_CreateInterrupterInstance

- ea: `0x14007ffb8`
- end: `0x1400800c0`
- name: `Counter_CreateInterrupterInstance`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14007c010`

## callees

- `0x1400450b8`
- `0x140059970`
- `0x14007ffb8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140080058`
- `ntoskrnl!RtlInitUnicodeString` at `0x140080058`
- `ntoskrnl!PcwCreateInstance` at `0x140080095`
- `ntoskrnl!PcwCreateInstance` at `0x140080095`

## pseudocode

```c
NTSTATUS __fastcall Counter_CreateInterrupterInstance(__int64 a1)
{
  NTSTATUS result; // eax
  __int64 v3; // r9
  int Data; // [rsp+20h] [rbp-68h]
  int v5; // [rsp+28h] [rbp-60h]
  struct _PCW_DATA v6; // [rsp+30h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  wchar_t pszDest[16]; // [rsp+50h] [rbp-38h] BYREF

  result = g_WdfDriverUsbXhciContext;
  DestinationString = 0;
  if ( *(_BYTE *)(g_WdfDriverUsbXhciContext + 28) && !*(_QWORD *)(a1 + 88) )
  {
    v3 = *(_QWORD *)(a1 + 8);
    v5 = *(_DWORD *)(a1 + 32);
    Data = *(_DWORD *)(v3 + 176);
    if ( *(_DWORD *)(v3 + 644) == 1 )
      RtlStringCchPrintfW(pszDest, 0x10u, L"%04X.%u.%u", *(unsigned __int16 *)(v3 + 648), Data, v5);
    else
      RtlStringCchPrintfW(pszDest, 0x10u, L"%S.%u.%u", v3 + 704, Data, v5);
    RtlInitUnicodeString(&DestinationString, pszDest);
    v6.Data = (const void *)(a1 + 40);
    v6.Size = 72;
    return PcwCreateInstance((PPCW_INSTANCE *)(a1 + 88), Ctr_Interrupter, &DestinationString, 1u, &v6);
  }
  return result;
}

```

## disassembly

```asm
0x14007ffb8  mov     [rsp+arg_8], rbx
0x14007ffbd  push    rdi
0x14007ffbe  sub     rsp, 80h
0x14007ffc5  mov     rax, cs:__security_cookie
0x14007ffcc  xor     rax, rsp
0x14007ffcf  mov     [rsp+88h+var_18], rax
0x14007ffd4  mov     rax, cs:g_WdfDriverUsbXhciContext
0x14007ffdb  xorps   xmm0, xmm0
0x14007ffde  mov     rbx, rcx
0x14007ffe1  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x14007ffe6  cmp     byte ptr [rax+1Ch], 0
0x14007ffea  jz      loc_1400800A1
0x14007fff0  cmp     qword ptr [rcx+58h], 0
0x14007fff5  jnz     loc_1400800A1
0x14007fffb  mov     r9, [rcx+8]
0x14007ffff  mov     edx, 10h; cchDest
0x140080004  mov     eax, [rcx+20h]
0x140080007  mov     [rsp+88h+var_60], eax
0x14008000b  cmp     dword ptr [r9+284h], 1
0x140080013  mov     ecx, [r9+0B0h]
0x14008001a  mov     dword ptr [rsp+88h+Data], ecx
0x14008001e  lea     rcx, [rsp+88h+pszDest]; pszDest
0x140080023  jnz     short loc_14008003B
0x140080025  movzx   r9d, word ptr [r9+288h]
0x14008002d  lea     r8, a04xUU; "%04X.%u.%u"
0x140080034  call    RtlStringCchPrintfW
0x140080039  jmp     short loc_14008004E
0x14008003b  add     r9, 2C0h
0x140080042  lea     r8, aSUU; "%S.%u.%u"
0x140080049  call    RtlStringCchPrintfW
0x14008004e  lea     rdx, [rsp+88h+pszDest]; SourceString
0x140080053  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x140080058  call    cs:__imp_RtlInitUnicodeString
0x14008005f  nop     dword ptr [rax+rax+00h]
0x140080064  mov     rdx, cs:Ctr_Interrupter; Registration
0x14008006b  lea     rax, [rbx+28h]
0x14008006f  mov     [rsp+88h+var_58.Data], rax
0x140080074  lea     r8, [rsp+88h+DestinationString]; Name
0x140080079  lea     rax, [rsp+88h+var_58]
0x14008007e  mov     [rsp+88h+var_58.Size], 48h ; 'H'
0x140080086  mov     r9d, 1; Count
0x14008008c  mov     [rsp+88h+Data], rax; Data
0x140080091  lea     rcx, [rbx+58h]; Instance
0x140080095  call    cs:__imp_PcwCreateInstance
0x14008009c  nop     dword ptr [rax+rax+00h]
0x1400800a1  mov     rcx, [rsp+88h+var_18]
0x1400800a6  xor     rcx, rsp; StackCookie
0x1400800a9  call    __security_check_cookie
0x1400800ae  mov     rbx, [rsp+88h+arg_8]
0x1400800b6  add     rsp, 80h
0x1400800bd  pop     rdi
0x1400800be  retn
```
