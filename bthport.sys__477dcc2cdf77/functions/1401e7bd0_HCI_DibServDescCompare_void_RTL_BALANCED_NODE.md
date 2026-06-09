# HCI_DibServDescCompare(void *,_RTL_BALANCED_NODE *)

- ea: `0x1401e7bd0`
- end: `0x1401e7c55`
- name: `?HCI_DibServDescCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(void *, struct _RTL_BALANCED_NODE *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1401e64e4`
- `0x1401e7098`
- `0x1401e76ec`
- `0x1401e8a98`

## callees

- `0x140161f7c`
- `0x1401e7bd0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1401e7c3d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401e7c3d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e7c0c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e7c24`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e7c0c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401e7c24`

## pseudocode

```c
LONG __fastcall HCI_DibServDescCompare(const WCHAR *a1, struct _RTL_BALANCED_NODE *a2)
{
  const WCHAR *p_Right; // rdi
  LONG result; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  p_Right = (const WCHAR *)&a2[-55].Right;
  DestinationString = 0;
  String2 = 0;
  result = BthCompareGuids(a1, &a2[-55].Right);
  if ( !result )
  {
    RtlInitUnicodeString(&DestinationString, a1 + 138);
    RtlInitUnicodeString(&String2, p_Right + 138);
    return RtlCompareUnicodeString(&DestinationString, &String2, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1401e7bd0  mov     [rsp+arg_0], rbx
0x1401e7bd5  push    rdi
0x1401e7bd6  sub     rsp, 40h
0x1401e7bda  lea     rdi, [rdx-520h]
0x1401e7be1  xorps   xmm0, xmm0
0x1401e7be4  xorps   xmm1, xmm1
0x1401e7be7  mov     rdx, rdi
0x1401e7bea  mov     rbx, rcx
0x1401e7bed  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1401e7bf2  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x1401e7bf7  call    BthCompareGuids
0x1401e7bfc  test    eax, eax
0x1401e7bfe  jnz     short loc_1401E7C49
0x1401e7c00  lea     rdx, [rbx+114h]; SourceString
0x1401e7c07  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1401e7c0c  call    cs:__imp_RtlInitUnicodeString
0x1401e7c13  nop     dword ptr [rax+rax+00h]
0x1401e7c18  lea     rdx, [rdi+114h]; SourceString
0x1401e7c1f  lea     rcx, [rsp+48h+String2]; DestinationString
0x1401e7c24  call    cs:__imp_RtlInitUnicodeString
0x1401e7c2b  nop     dword ptr [rax+rax+00h]
0x1401e7c30  xor     r8d, r8d; CaseInSensitive
0x1401e7c33  lea     rdx, [rsp+48h+String2]; String2
0x1401e7c38  lea     rcx, [rsp+48h+DestinationString]; String1
0x1401e7c3d  call    cs:__imp_RtlCompareUnicodeString
0x1401e7c44  nop     dword ptr [rax+rax+00h]
0x1401e7c49  mov     rbx, [rsp+48h+arg_0]
0x1401e7c4e  add     rsp, 40h
0x1401e7c52  pop     rdi
0x1401e7c53  retn
```
