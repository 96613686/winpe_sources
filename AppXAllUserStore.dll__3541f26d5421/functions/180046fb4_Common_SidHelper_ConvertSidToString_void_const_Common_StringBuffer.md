# Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)

- ea: `0x180046fb4`
- end: `0x180047031`
- name: `?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z`
- size: `125`
- prototype: `int __fastcall(PSID Sid, struct Common::StringBuffer *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002da70`

## callees

- `0x180008550`
- `0x18001a56c`
- `0x180046fb4`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18004701c`
- `ntdll!RtlFreeUnicodeString` at `0x18004701c`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180046fda`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180046fda`

## string_xrefs

- `0x180046fe9`: `onecore\base\appmodel\common\sidhelper.cpp`

## pseudocode

```c
int __fastcall Common::SidHelper::ConvertSidToString(PSID Sid, struct Common::StringBuffer *this)
{
  NTSTATUS v3; // eax
  int v5; // ebx
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !Sid || !this )
    return -2147024809;
  UnicodeString = 0;
  v3 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( v3 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x1E,
             (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
             (const char *)(unsigned int)v3,
             *(int *)&UnicodeString.Length);
  v5 = Common::StringBuffer::SetValue(this, UnicodeString.Buffer, UnicodeString.Length >> 1);
  RtlFreeUnicodeString(&UnicodeString);
  return v5;
}

```

## disassembly

```asm
0x180046fb4  push    rbx
0x180046fb6  sub     rsp, 30h
0x180046fba  mov     rbx, rdx
0x180046fbd  test    rcx, rcx
0x180046fc0  jz      short loc_180047026
0x180046fc2  test    rdx, rdx
0x180046fc5  jz      short loc_180047026
0x180046fc7  xorps   xmm0, xmm0
0x180046fca  mov     rdx, rcx; Sid
0x180046fcd  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x180046fd2  mov     r8b, 1; AllocateDestinationString
0x180046fd5  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0; int
0x180046fda  call    cs:__imp_RtlConvertSidToUnicodeString
0x180046fe0  test    eax, eax
0x180046fe2  jns     short loc_180046FFF
0x180046fe4  mov     rcx, [rsp+38h]; this
0x180046fe9  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\common\\sidhel"...
0x180046ff0  mov     r9d, eax; char *
0x180046ff3  mov     edx, 1Eh; void *
0x180046ff8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180046ffd  jmp     short loc_18004702B
0x180046fff  movzx   r8d, [rsp+38h+UnicodeString.Length]
0x180047005  mov     rcx, rbx; this
0x180047008  mov     rdx, [rsp+38h+UnicodeString.Buffer]; Src
0x18004700d  shr     r8d, 1; unsigned int
0x180047010  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x180047015  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18004701a  mov     ebx, eax
0x18004701c  call    cs:__imp_RtlFreeUnicodeString
0x180047022  mov     eax, ebx
0x180047024  jmp     short loc_18004702B
0x180047026  mov     eax, 80070057h
0x18004702b  add     rsp, 30h
0x18004702f  pop     rbx
0x180047030  retn
```
