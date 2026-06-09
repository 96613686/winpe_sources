# Counter_CreateTransferRingInstance

- ea: `0x140083190`
- end: `0x1400832af`
- name: `Counter_CreateTransferRingInstance`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140082ab4`

## callees

- `0x1400450b8`
- `0x140059970`
- `0x140083190`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140083265`
- `ntoskrnl!RtlInitUnicodeString` at `0x140083265`
- `ntoskrnl!PcwCreateInstance` at `0x14008329e`
- `ntoskrnl!PcwCreateInstance` at `0x14008329e`

## pseudocode

```c
NTSTATUS __fastcall Counter_CreateTransferRingInstance(__int64 *a1, int a2, PPCW_INSTANCE *a3)
{
  NTSTATUS result; // eax
  __int64 v5; // r9
  int Data; // [rsp+20h] [rbp-88h]
  int v7; // [rsp+28h] [rbp-80h]
  int v8; // [rsp+30h] [rbp-78h]
  struct _PCW_DATA v10; // [rsp+40h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-58h] BYREF
  wchar_t pszDest[24]; // [rsp+60h] [rbp-48h] BYREF

  result = g_WdfDriverUsbXhciContext;
  DestinationString = 0;
  if ( *(_BYTE *)(g_WdfDriverUsbXhciContext + 28) && !a3[4] )
  {
    v5 = *a1;
    v8 = *((unsigned __int8 *)a1 + 98);
    v7 = *(unsigned __int16 *)(a1[2] + 132);
    Data = *(_DWORD *)(*a1 + 176);
    if ( *(_DWORD *)(*a1 + 644) == 1 )
      RtlStringCchPrintfW(pszDest, 0x15u, L"%04X.%u.%04X.%02X.%u", *(unsigned __int16 *)(v5 + 648), Data, v7, v8, a2);
    else
      RtlStringCchPrintfW(pszDest, 0x15u, L"%S.%u.%04X.%02X.%u", v5 + 704, Data, v7, v8, a2);
    RtlInitUnicodeString(&DestinationString, pszDest);
    v10.Data = a3;
    v10.Size = 40;
    return PcwCreateInstance(a3 + 4, Ctr_TransferRing, &DestinationString, 1u, &v10);
  }
  return result;
}

```

## disassembly

```asm
0x140083190  mov     [rsp+arg_18], rbx
0x140083195  push    rdi
0x140083196  sub     rsp, 0A0h
0x14008319d  mov     rax, cs:__security_cookie
0x1400831a4  xor     rax, rsp
0x1400831a7  mov     [rsp+0A8h+var_18], rax
0x1400831af  mov     rax, cs:g_WdfDriverUsbXhciContext
0x1400831b6  xorps   xmm0, xmm0
0x1400831b9  mov     rdi, r8
0x1400831bc  mov     r10d, edx
0x1400831bf  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x1400831c4  cmp     byte ptr [rax+1Ch], 0
0x1400831c8  jnz     short loc_1400831EC
0x1400831ca  mov     rcx, [rsp+0A8h+var_18]
0x1400831d2  xor     rcx, rsp; StackCookie
0x1400831d5  call    __security_check_cookie
0x1400831da  mov     rbx, [rsp+0A8h+arg_18]
0x1400831e2  add     rsp, 0A0h
0x1400831e9  pop     rdi
0x1400831ea  retn
0x1400831ec  cmp     qword ptr [r8+20h], 0
0x1400831f1  jnz     short loc_1400831CA
0x1400831f3  mov     r9, [rcx]
0x1400831f6  movzx   edx, byte ptr [rcx+62h]
0x1400831fa  mov     rax, [rcx+10h]
0x1400831fe  mov     [rsp+0A8h+var_70], r10d
0x140083203  cmp     dword ptr [r9+284h], 1
0x14008320b  mov     r8d, [r9+0B0h]
0x140083212  movzx   ecx, word ptr [rax+84h]
0x140083219  mov     [rsp+0A8h+var_78], edx
0x14008321d  mov     edx, 15h; cchDest
0x140083222  mov     [rsp+0A8h+var_80], ecx
0x140083226  lea     rcx, [rsp+0A8h+pszDest]; pszDest
0x14008322b  mov     dword ptr [rsp+0A8h+Data], r8d
0x140083230  jnz     short loc_140083248
0x140083232  movzx   r9d, word ptr [r9+288h]
0x14008323a  lea     r8, a04xU04x02xU; "%04X.%u.%04X.%02X.%u"
0x140083241  call    RtlStringCchPrintfW
0x140083246  jmp     short loc_14008325B
0x140083248  add     r9, 2C0h
0x14008324f  lea     r8, aSU04x02xU; "%S.%u.%04X.%02X.%u"
0x140083256  call    RtlStringCchPrintfW
0x14008325b  lea     rdx, [rsp+0A8h+pszDest]; SourceString
0x140083260  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x140083265  call    cs:__imp_RtlInitUnicodeString
0x14008326c  nop     dword ptr [rax+rax+00h]
0x140083271  mov     rdx, cs:Ctr_TransferRing; Registration
0x140083278  lea     rax, [rsp+0A8h+var_68]
0x14008327d  mov     r9d, 1; Count
0x140083283  mov     [rsp+0A8h+Data], rax; Data
0x140083288  lea     r8, [rsp+0A8h+DestinationString]; Name
0x14008328d  mov     [rsp+0A8h+var_68.Data], rdi
0x140083292  lea     rcx, [rdi+20h]; Instance
0x140083296  mov     [rsp+0A8h+var_68.Size], 28h ; '('
0x14008329e  call    cs:__imp_PcwCreateInstance
0x1400832a5  nop     dword ptr [rax+rax+00h]
0x1400832aa  jmp     loc_1400831CA
```
