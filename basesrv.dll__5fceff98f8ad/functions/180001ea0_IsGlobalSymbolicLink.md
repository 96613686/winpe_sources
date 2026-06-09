# IsGlobalSymbolicLink

- ea: `0x180001ea0`
- end: `0x180002008`
- name: `IsGlobalSymbolicLink`
- size: `360`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x180001010`
- `0x180002240`

## callees

- `0x180001ea0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180001f44`
- `ntdll!RtlAllocateHeap` at `0x180001f44`
- `ntdll!RtlFreeHeap` at `0x180001fdc`
- `ntdll!RtlFreeHeap` at `0x18000dd0b`
- `ntdll!RtlFreeHeap` at `0x180001fdc`
- `ntdll!RtlFreeHeap` at `0x18000dd0b`
- `ntdll!RtlPrefixUnicodeString` at `0x180001fb2`
- `ntdll!RtlPrefixUnicodeString` at `0x180001fb2`
- `ntdll!RtlInitUnicodeString` at `0x180001f9b`
- `ntdll!RtlInitUnicodeString` at `0x180001f9b`
- `ntdll!NtQueryObject` at `0x180001f0a`
- `ntdll!NtQueryObject` at `0x180001f7d`
- `ntdll!NtQueryObject` at `0x180001f0a`
- `ntdll!NtQueryObject` at `0x180001f7d`

## pseudocode

```c
__int64 __fastcall IsGlobalSymbolicLink(HANDLE Handle, BOOLEAN *a2)
{
  UNICODE_STRING *Heap; // rdi
  NTSTATUS Object; // esi
  __int128 ObjectInformation; // [rsp+38h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-30h] BYREF
  SIZE_T Size; // [rsp+88h] [rbp+10h] BYREF

  ObjectInformation = 0;
  DestinationString = 0;
  LODWORD(Size) = 0;
  if ( !a2 )
    return 3221225485LL;
  Heap = 0;
  if ( !Handle )
    return 3221225485LL;
  LODWORD(ObjectInformation) = 0;
  *((_QWORD *)&ObjectInformation + 1) = 0;
  LODWORD(Size) = 0;
  Object = NtQueryObject(Handle, ObjectNameInformation, &ObjectInformation, 0, (PULONG)&Size);
  if ( (int)(Object + 0x80000000) < 0 || Object == -1073741820 )
  {
    Heap = (UNICODE_STRING *)RtlAllocateHeap(BaseSrvHeap, BaseSrvTag, (unsigned int)Size);
    if ( Heap )
    {
      Object = NtQueryObject(Handle, ObjectNameInformation, Heap, Size, (PULONG)&Size);
      if ( Object >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"\\GLOBAL??\\");
        *a2 = RtlPrefixUnicodeString(&DestinationString, Heap, 0);
        Object = 0;
      }
    }
    else
    {
      Object = -1073741801;
    }
  }
  if ( Heap )
    RtlFreeHeap(BaseSrvHeap, 0, Heap);
  return (unsigned int)Object;
}

```

## disassembly

```asm
0x180001ea0  mov     rax, rsp
0x180001ea3  mov     [rax+8], rbx
0x180001ea7  mov     [rax+18h], rsi
0x180001eab  push    rdi
0x180001eac  push    r14
0x180001eae  push    r15
0x180001eb0  sub     rsp, 60h
0x180001eb4  mov     r14, rdx
0x180001eb7  mov     rbx, rcx
0x180001eba  xorps   xmm0, xmm0
0x180001ebd  movups  xmmword ptr [rax-40h], xmm0
0x180001ec1  xorps   xmm1, xmm1
0x180001ec4  movups  xmmword ptr [rax-30h], xmm1
0x180001ec8  xor     r15d, r15d
0x180001ecb  mov     [rax+10h], r15d
0x180001ecf  test    rdx, rdx
0x180001ed2  jz      loc_180002001
0x180001ed8  mov     edi, r15d
0x180001edb  mov     [rax-48h], r15
0x180001edf  test    rcx, rcx
0x180001ee2  jz      loc_180002001
0x180001ee8  mov     [rax-40h], r15d
0x180001eec  mov     [rax-38h], r15
0x180001ef0  mov     [rax+10h], r15d
0x180001ef4  lea     rax, [rax+10h]
0x180001ef8  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180001efd  xor     r9d, r9d; ObjectInformationLength
0x180001f00  lea     r8, [rsp+78h+ObjectInformation]; ObjectInformation
0x180001f05  mov     edx, 1; ObjectInformationClass
0x180001f0a  call    cs:__imp_NtQueryObject
0x180001f11  nop     dword ptr [rax+rax+00h]
0x180001f16  mov     esi, eax
0x180001f18  mov     ecx, 80000000h
0x180001f1d  add     eax, ecx
0x180001f1f  test    ecx, eax
0x180001f21  jnz     short loc_180001F2F
0x180001f23  cmp     esi, 0C0000004h
0x180001f29  jnz     loc_180001FCB
0x180001f2f  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x180001f37  mov     edx, cs:BaseSrvTag; Flags
0x180001f3d  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x180001f44  call    cs:__imp_RtlAllocateHeap
0x180001f4b  nop     dword ptr [rax+rax+00h]
0x180001f50  mov     rdi, rax
0x180001f53  mov     [rsp+78h+var_48], rax
0x180001f58  test    rax, rax
0x180001f5b  jz      short loc_180001FC6
0x180001f5d  lea     rax, [rsp+78h+Size]
0x180001f65  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180001f6a  mov     r9d, dword ptr [rsp+78h+Size]; ObjectInformationLength
0x180001f72  mov     r8, rdi; ObjectInformation
0x180001f75  mov     edx, 1; ObjectInformationClass
0x180001f7a  mov     rcx, rbx; Handle
0x180001f7d  call    cs:__imp_NtQueryObject
0x180001f84  nop     dword ptr [rax+rax+00h]
0x180001f89  mov     esi, eax
0x180001f8b  test    eax, eax
0x180001f8d  js      short loc_180001FCB
0x180001f8f  lea     rdx, SourceString; "\\GLOBAL??\\"
0x180001f96  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180001f9b  call    cs:__imp_RtlInitUnicodeString
0x180001fa2  nop     dword ptr [rax+rax+00h]
0x180001fa7  xor     r8d, r8d; CaseInsensitive
0x180001faa  mov     rdx, rdi; String2
0x180001fad  lea     rcx, [rsp+78h+DestinationString]; String1
0x180001fb2  call    cs:__imp_RtlPrefixUnicodeString
0x180001fb9  nop     dword ptr [rax+rax+00h]
0x180001fbe  mov     [r14], al
0x180001fc1  mov     esi, r15d
0x180001fc4  jmp     short loc_180001FCB
0x180001fc6  mov     esi, 0C0000017h
0x180001fcb  test    rdi, rdi
0x180001fce  jz      short loc_180001FE8
0x180001fd0  mov     r8, rdi; P
0x180001fd3  xor     edx, edx; Flags
0x180001fd5  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x180001fdc  call    cs:__imp_RtlFreeHeap
0x180001fe3  nop     dword ptr [rax+rax+00h]
0x180001fe8  mov     eax, esi
0x180001fea  lea     r11, [rsp+78h+var_18]
0x180001fef  mov     rbx, [r11+20h]
0x180001ff3  mov     rsi, [r11+30h]
0x180001ff7  mov     rsp, r11
0x180001ffa  pop     r15
0x180001ffc  pop     r14
0x180001ffe  pop     rdi
0x180001fff  retn
0x180002001  mov     eax, 0C000000Dh
0x180002006  jmp     short loc_180001FEA
0x18000dcf0  push    rbp
0x18000dcf2  sub     rsp, 30h
0x18000dcf6  mov     rbp, rdx
0x18000dcf9  mov     r8, [rbp+30h]; P
0x18000dcfd  test    r8, r8
0x18000dd00  jz      short loc_18000DD1F
0x18000dd02  xor     edx, edx; Flags
0x18000dd04  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000dd0b  call    cs:__imp_RtlFreeHeap
0x18000dd12  nop     dword ptr [rax+rax+00h]
0x18000dd17  mov     qword ptr [rbp+30h], 0
0x18000dd1f  add     rsp, 30h
0x18000dd23  pop     rbp
0x18000dd24  retn
```
