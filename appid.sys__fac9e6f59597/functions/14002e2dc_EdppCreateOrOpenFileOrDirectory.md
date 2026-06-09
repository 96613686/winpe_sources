# EdppCreateOrOpenFileOrDirectory

- ea: `0x14002e2dc`
- end: `0x14002e3c5`
- name: `EdppCreateOrOpenFileOrDirectory`
- size: `233`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, __int64, __int64, PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x14002e7ec`

## callees

- `0x140005a10`
- `0x14002e2dc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e394`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e3a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e394`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e3a5`
- `ntoskrnl!ZwCreateFile` at `0x14002e371`
- `ntoskrnl!ZwCreateFile` at `0x14002e371`

## pseudocode

```c
__int64 __fastcall EdppCreateOrOpenFileOrDirectory(
        const unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PHANDLE FileHandle)
{
  NTSTATUS v5; // edi
  PVOID v6; // rbx
  void *v7; // rcx
  PVOID P; // [rsp+60h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-40h] BYREF

  P = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  *FileHandle = 0;
  memset(&ObjectAttributes.ObjectName, 0, 32);
  IoStatusBlock = 0;
  v5 = EdppCreateFileObject(a1, &ObjectAttributes, (struct _UNICODE_STRING **)&P);
  if ( v5 >= 0 )
    v5 = ZwCreateFile(FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 6u, 3u, 3u, 0x20u, 0, 0);
  v6 = P;
  if ( P )
  {
    v7 = (void *)*((_QWORD *)P + 1);
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
    ExFreePoolWithTag(v6, 0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002e2dc  mov     rax, rsp
0x14002e2df  mov     [rax+8], rbx
0x14002e2e3  push    rdi
0x14002e2e4  sub     rsp, 0B0h
0x14002e2eb  mov     rbx, [rsp+0B8h+FileHandle]
0x14002e2f3  lea     r8, [rax-58h]; struct _UNICODE_STRING **
0x14002e2f7  xorps   xmm0, xmm0
0x14002e2fa  mov     qword ptr [rax-58h], 0
0x14002e302  lea     rdx, [rax-40h]; struct _OBJECT_ATTRIBUTES *
0x14002e306  movups  xmmword ptr [rax-40h], xmm0
0x14002e30a  mov     qword ptr [rbx], 0
0x14002e311  movups  xmmword ptr [rax-30h], xmm0
0x14002e315  movups  xmmword ptr [rax-20h], xmm0
0x14002e319  movups  xmmword ptr [rax-50h], xmm0
0x14002e31d  call    ?EdppCreateFileObject@@YAJPEBGPEAU_OBJECT_ATTRIBUTES@@PEAPEAU_UNICODE_STRING@@@Z; EdppCreateFileObject(ushort const *,_OBJECT_ATTRIBUTES *,_UNICODE_STRING * *)
0x14002e322  mov     edi, eax
0x14002e324  test    eax, eax
0x14002e326  js      short loc_14002E37F
0x14002e328  mov     [rsp+0B8h+EaLength], 0; EaLength
0x14002e330  lea     r9, [rsp+0B8h+IoStatusBlock]; IoStatusBlock
0x14002e335  mov     [rsp+0B8h+EaBuffer], 0; EaBuffer
0x14002e33e  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x14002e343  mov     [rsp+0B8h+CreateOptions], 20h ; ' '; CreateOptions
0x14002e34b  mov     eax, 3
0x14002e350  mov     [rsp+0B8h+CreateDisposition], eax; CreateDisposition
0x14002e354  mov     edx, 12019Fh; DesiredAccess
0x14002e359  mov     [rsp+0B8h+ShareAccess], eax; ShareAccess
0x14002e35d  mov     rcx, rbx; FileHandle
0x14002e360  mov     [rsp+0B8h+FileAttributes], 6; FileAttributes
0x14002e368  mov     [rsp+0B8h+AllocationSize], 0; AllocationSize
0x14002e371  call    cs:__imp_ZwCreateFile
0x14002e378  nop     dword ptr [rax+rax+00h]
0x14002e37d  mov     edi, eax
0x14002e37f  mov     rbx, [rsp+0B8h+P]
0x14002e384  test    rbx, rbx
0x14002e387  jz      short loc_14002E3B1
0x14002e389  mov     rcx, [rbx+8]; P
0x14002e38d  test    rcx, rcx
0x14002e390  jz      short loc_14002E3A0
0x14002e392  xor     edx, edx; Tag
0x14002e394  call    cs:__imp_ExFreePoolWithTag
0x14002e39b  nop     dword ptr [rax+rax+00h]
0x14002e3a0  xor     edx, edx; Tag
0x14002e3a2  mov     rcx, rbx; P
0x14002e3a5  call    cs:__imp_ExFreePoolWithTag
0x14002e3ac  nop     dword ptr [rax+rax+00h]
0x14002e3b1  mov     rbx, [rsp+0B8h+arg_0]
0x14002e3b9  mov     eax, edi
0x14002e3bb  add     rsp, 0B0h
0x14002e3c2  pop     rdi
0x14002e3c3  retn
```
