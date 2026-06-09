# Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)

- ea: `0x18002d35c`
- end: `0x18002d3d9`
- name: `?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z`
- size: `125`
- prototype: `__int64 __fastcall(PSID Sid, struct Common::StringBuffer *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180026888`

## callees

- `0x180013728`
- `0x18002d20c`
- `0x18002d35c`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x18002d382`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18002d382`
- `ntdll!RtlFreeUnicodeString` at `0x18002d3c4`
- `ntdll!RtlFreeUnicodeString` at `0x18002d3c4`

## string_xrefs

- `0x18002d391`: `onecore\base\appmodel\common\sidhelper.cpp`

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
0x18002d35c  push    rbx
0x18002d35e  sub     rsp, 30h
0x18002d362  mov     rbx, rdx
0x18002d365  test    rcx, rcx
0x18002d368  jz      short loc_18002D3CE
0x18002d36a  test    rdx, rdx
0x18002d36d  jz      short loc_18002D3CE
0x18002d36f  xorps   xmm0, xmm0
0x18002d372  mov     rdx, rcx; Sid
0x18002d375  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18002d37a  mov     r8b, 1; AllocateDestinationString
0x18002d37d  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0; int
0x18002d382  call    cs:__imp_RtlConvertSidToUnicodeString
0x18002d388  test    eax, eax
0x18002d38a  jns     short loc_18002D3A7
0x18002d38c  mov     rcx, [rsp+38h]; this
0x18002d391  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\common\\sidhel"...
0x18002d398  mov     r9d, eax; char *
0x18002d39b  mov     edx, 1Eh; void *
0x18002d3a0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002d3a5  jmp     short loc_18002D3D3
0x18002d3a7  movzx   r8d, [rsp+38h+UnicodeString.Length]
0x18002d3ad  mov     rcx, rbx; this
0x18002d3b0  mov     rdx, [rsp+38h+UnicodeString.Buffer]; Src
0x18002d3b5  shr     r8d, 1; unsigned int
0x18002d3b8  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18002d3bd  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18002d3c2  mov     ebx, eax
0x18002d3c4  call    cs:__imp_RtlFreeUnicodeString
0x18002d3ca  mov     eax, ebx
0x18002d3cc  jmp     short loc_18002D3D3
0x18002d3ce  mov     eax, 80070057h
0x18002d3d3  add     rsp, 30h
0x18002d3d7  pop     rbx
0x18002d3d8  retn
```
