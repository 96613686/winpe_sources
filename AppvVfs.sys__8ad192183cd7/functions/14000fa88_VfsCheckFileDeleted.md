# VfsCheckFileDeleted

- ea: `0x14000fa88`
- end: `0x14000fad7`
- name: `VfsCheckFileDeleted`
- size: `79`
- prototype: `NTSTATUS __fastcall(struct _FLT_INSTANCE *, struct _FILE_OBJECT *, _BYTE *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005dc8`
- `0x14000a8d0`

## callees

- `0x14000fa88`

## import_xrefs

- `FLTMGR!FltQueryInformationFile` at `0x14000fab8`
- `FLTMGR!FltQueryInformationFile` at `0x14000fab8`

## pseudocode

```c
NTSTATUS __fastcall VfsCheckFileDeleted(struct _FLT_INSTANCE *a1, struct _FILE_OBJECT *a2, _BYTE *a3)
{
  NTSTATUS result; // eax
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  v5 = 0;
  result = FltQueryInformationFile(a1, a2, &v5, 8u, FileInternalInformation, 0);
  if ( result == -1073741533 )
  {
    *a3 = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000fa88  mov     rax, rsp
0x14000fa8b  push    rbx
0x14000fa8c  sub     rsp, 30h
0x14000fa90  mov     rbx, r8
0x14000fa93  mov     byte ptr [r8], 0
0x14000fa97  mov     qword ptr [rax-10h], 0
0x14000fa9f  lea     r8, [rax+18h]; FileInformation
0x14000faa3  mov     r9d, 8; Length
0x14000faa9  mov     qword ptr [rax+18h], 0
0x14000fab1  mov     dword ptr [rax-18h], 6
0x14000fab8  call    cs:__imp_FltQueryInformationFile
0x14000fabf  nop     dword ptr [rax+rax+00h]
0x14000fac4  cmp     eax, 0C0000123h
0x14000fac9  jnz     short loc_14000FAD0
0x14000facb  mov     byte ptr [rbx], 1
0x14000face  xor     eax, eax
0x14000fad0  add     rsp, 30h
0x14000fad4  pop     rbx
0x14000fad5  retn
```
