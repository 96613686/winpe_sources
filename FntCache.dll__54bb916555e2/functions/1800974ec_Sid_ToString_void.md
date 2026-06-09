# Sid::ToString(void)

- ea: `0x1800974ec`
- end: `0x180097574`
- name: `?ToString@Sid@@QEBA?AVRefString@DWrite@@XZ`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000bd98`

## callees

- `0x1800217ac`
- `0x18002bf90`
- `0x18002faf0`
- `0x1800974ec`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x180097510`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180097510`
- `ntdll!RtlFreeUnicodeString` at `0x18009753c`
- `ntdll!RtlFreeUnicodeString` at `0x18009753c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Sid::ToString(PSID *a1, _QWORD *a2)
{
  NTSTATUS v3; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+28h] [rbp-20h] BYREF
  int v6; // [rsp+50h] [rbp+8h] BYREF

  UnicodeString.Buffer = 0;
  UnicodeString.Length = 0;
  v3 = RtlConvertSidToUnicodeString(&UnicodeString, *a1, 1u);
  if ( v3 < 0 )
  {
    Exception::Exception((Exception *)&v6, v3 | 0x10000000, v3);
    LogAndThrow<OSException>(&v6, 4475219, 109);
  }
  *a2 = DWrite::RefString::NewData(UnicodeString.Buffer, (unsigned __int64)UnicodeString.Length >> 1);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  return a2;
}

```

## disassembly

```asm
0x1800974ec  push    rbx
0x1800974ee  sub     rsp, 40h
0x1800974f2  mov     rbx, rdx
0x1800974f5  mov     [rsp+48h+UnicodeString.Buffer], 0
0x1800974fe  xor     eax, eax
0x180097500  mov     [rsp+48h+UnicodeString.Length], ax
0x180097505  mov     r8b, 1; AllocateDestinationString
0x180097508  mov     rdx, [rcx]; Sid
0x18009750b  lea     rcx, [rsp+48h+UnicodeString]; UnicodeString
0x180097510  call    cs:__imp_RtlConvertSidToUnicodeString
0x180097516  test    eax, eax
0x180097518  js      short loc_18009754B
0x18009751a  movzx   edx, [rsp+48h+UnicodeString.Length]
0x18009751f  shr     rdx, 1; unsigned __int64
0x180097522  mov     rcx, [rsp+48h+UnicodeString.Buffer]; Src
0x180097527  call    ?NewData@RefString@DWrite@@CAPEAUData@12@PEB_W_K@Z; DWrite::RefString::NewData(wchar_t const *,unsigned __int64)
0x18009752c  mov     [rbx], rax
0x18009752f  cmp     [rsp+48h+UnicodeString.Buffer], 0
0x180097535  jz      short loc_180097542
0x180097537  lea     rcx, [rsp+48h+UnicodeString]; UnicodeString
0x18009753c  call    cs:__imp_RtlFreeUnicodeString
0x180097542  mov     rax, rbx
0x180097545  add     rsp, 40h
0x180097549  pop     rbx
0x18009754a  retn
0x18009754b  mov     edx, eax
0x18009754d  bts     edx, 1Ch; int
0x180097551  mov     r8d, eax; unsigned int
0x180097554  lea     rcx, [rsp+48h+arg_0]; this
0x180097559  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18009755e  mov     edx, 444953h
0x180097563  mov     r8d, 6Dh ; 'm'
0x180097569  lea     rcx, [rsp+48h+arg_0]
0x18009756e  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
```
