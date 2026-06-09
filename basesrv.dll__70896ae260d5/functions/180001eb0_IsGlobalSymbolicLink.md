# IsGlobalSymbolicLink

- ea: `0x180001eb0`
- end: `0x180002017`
- name: `IsGlobalSymbolicLink`
- size: `359`
- prototype: `__int64 __fastcall(HANDLE Handle, BOOLEAN *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x180001010`
- `0x180002250`

## callees

- `0x180001eb0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180001f53`
- `ntdll!RtlAllocateHeap` at `0x180001f53`
- `ntdll!RtlFreeHeap` at `0x180001feb`
- `ntdll!RtlFreeHeap` at `0x18000d8fb`
- `ntdll!RtlFreeHeap` at `0x180001feb`
- `ntdll!RtlFreeHeap` at `0x18000d8fb`
- `ntdll!RtlPrefixUnicodeString` at `0x180001fc1`
- `ntdll!RtlPrefixUnicodeString` at `0x180001fc1`
- `ntdll!RtlInitUnicodeString` at `0x180001faa`
- `ntdll!RtlInitUnicodeString` at `0x180001faa`
- `ntdll!NtQueryObject` at `0x180001f19`
- `ntdll!NtQueryObject` at `0x180001f8c`
- `ntdll!NtQueryObject` at `0x180001f19`
- `ntdll!NtQueryObject` at `0x180001f8c`

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
  Heap = 0;
  LODWORD(Size) = 0;
  if ( !a2 || !Handle )
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
0x180001eb0  mov     rax, rsp
0x180001eb3  mov     [rax+8], rbx
0x180001eb7  mov     [rax+18h], rsi
0x180001ebb  push    rdi
0x180001ebc  push    r14
0x180001ebe  push    r15
0x180001ec0  sub     rsp, 60h
0x180001ec4  mov     r14, rdx
0x180001ec7  mov     rbx, rcx
0x180001eca  xorps   xmm0, xmm0
0x180001ecd  movups  xmmword ptr [rax-40h], xmm0
0x180001ed1  xorps   xmm1, xmm1
0x180001ed4  movups  xmmword ptr [rax-30h], xmm1
0x180001ed8  xor     r15d, r15d
0x180001edb  mov     edi, r15d
0x180001ede  mov     [rax-48h], r15
0x180001ee2  mov     [rax+10h], r15d
0x180001ee6  test    rdx, rdx
0x180001ee9  jz      loc_180002010
0x180001eef  test    rcx, rcx
0x180001ef2  jz      loc_180002010
0x180001ef8  mov     [rax-40h], r15d
0x180001efc  mov     [rax-38h], r15
0x180001f00  mov     [rax+10h], r15d
0x180001f04  lea     rax, [rax+10h]
0x180001f08  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180001f0d  xor     r9d, r9d; ObjectInformationLength
0x180001f10  lea     r8, [rsp+78h+ObjectInformation]; ObjectInformation
0x180001f15  lea     edx, [r15+1]; ObjectInformationClass
0x180001f19  call    cs:__imp_NtQueryObject
0x180001f20  nop     dword ptr [rax+rax+00h]
0x180001f25  mov     esi, eax
0x180001f27  mov     ecx, 80000000h
0x180001f2c  add     eax, ecx
0x180001f2e  test    ecx, eax
0x180001f30  jnz     short loc_180001F3E
0x180001f32  cmp     esi, 0C0000004h
0x180001f38  jnz     loc_180001FDA
0x180001f3e  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x180001f46  mov     edx, cs:BaseSrvTag; Flags
0x180001f4c  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x180001f53  call    cs:__imp_RtlAllocateHeap
0x180001f5a  nop     dword ptr [rax+rax+00h]
0x180001f5f  mov     rdi, rax
0x180001f62  mov     [rsp+78h+var_48], rax
0x180001f67  test    rax, rax
0x180001f6a  jz      short loc_180001FD5
0x180001f6c  lea     rax, [rsp+78h+Size]
0x180001f74  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180001f79  mov     r9d, dword ptr [rsp+78h+Size]; ObjectInformationLength
0x180001f81  mov     r8, rdi; ObjectInformation
0x180001f84  mov     edx, 1; ObjectInformationClass
0x180001f89  mov     rcx, rbx; Handle
0x180001f8c  call    cs:__imp_NtQueryObject
0x180001f93  nop     dword ptr [rax+rax+00h]
0x180001f98  mov     esi, eax
0x180001f9a  test    eax, eax
0x180001f9c  js      short loc_180001FDA
0x180001f9e  lea     rdx, SourceString; "\\GLOBAL??\\"
0x180001fa5  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180001faa  call    cs:__imp_RtlInitUnicodeString
0x180001fb1  nop     dword ptr [rax+rax+00h]
0x180001fb6  xor     r8d, r8d; CaseInsensitive
0x180001fb9  mov     rdx, rdi; String2
0x180001fbc  lea     rcx, [rsp+78h+DestinationString]; String1
0x180001fc1  call    cs:__imp_RtlPrefixUnicodeString
0x180001fc8  nop     dword ptr [rax+rax+00h]
0x180001fcd  mov     [r14], al
0x180001fd0  mov     esi, r15d
0x180001fd3  jmp     short loc_180001FDA
0x180001fd5  mov     esi, 0C0000017h
0x180001fda  test    rdi, rdi
0x180001fdd  jz      short loc_180001FF7
0x180001fdf  mov     r8, rdi; P
0x180001fe2  xor     edx, edx; Flags
0x180001fe4  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x180001feb  call    cs:__imp_RtlFreeHeap
0x180001ff2  nop     dword ptr [rax+rax+00h]
0x180001ff7  mov     eax, esi
0x180001ff9  lea     r11, [rsp+78h+var_18]
0x180001ffe  mov     rbx, [r11+20h]
0x180002002  mov     rsi, [r11+30h]
0x180002006  mov     rsp, r11
0x180002009  pop     r15
0x18000200b  pop     r14
0x18000200d  pop     rdi
0x18000200e  retn
0x180002010  mov     eax, 0C000000Dh
0x180002015  jmp     short loc_180001FF9
0x18000d8e0  push    rbp
0x18000d8e2  sub     rsp, 30h
0x18000d8e6  mov     rbp, rdx
0x18000d8e9  mov     r8, [rbp+30h]; P
0x18000d8ed  test    r8, r8
0x18000d8f0  jz      short loc_18000D90F
0x18000d8f2  xor     edx, edx; Flags
0x18000d8f4  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x18000d8fb  call    cs:__imp_RtlFreeHeap
0x18000d902  nop     dword ptr [rax+rax+00h]
0x18000d907  mov     qword ptr [rbp+30h], 0
0x18000d90f  add     rsp, 30h
0x18000d913  pop     rbp
0x18000d914  retn
```
