# PROPERTY_ENTRY::Create(_METADATA_RECORD *)

- ea: `0x18000fd48`
- end: `0x18000fdde`
- name: `?Create@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(PROPERTY_ENTRY *__hidden this, struct _METADATA_RECORD *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800087bc`
- `0x18001015c`
- `0x180011b78`
- `0x180012718`
- `0x180014830`
- `0x180016b1c`
- `0x180019074`
- `0x18001af78`
- `0x180025e78`
- `0x1800278cc`

## callees

- `0x180003402`
- `0x18000fd48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd7d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000fd73`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000fd73`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fd99`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000fd99`

## pseudocode

```c
__int64 __fastcall PROPERTY_ENTRY::Create(PROPERTY_ENTRY *this, struct _METADATA_RECORD *a2)
{
  unsigned int v3; // ebx
  BUFFER *v4; // rsi
  signed int LastError; // eax
  _OWORD *Ptr; // rax

  if ( a2 )
  {
    v4 = (PROPERTY_ENTRY *)((char *)this + 16);
    if ( BUFFER::Resize((PROPERTY_ENTRY *)((char *)this + 16), a2->dwMDDataLen + 40) )
    {
      v3 = 0;
      Ptr = BUFFER::QueryPtr(v4);
      *Ptr = *(_OWORD *)&a2->dwMDIdentifier;
      Ptr[1] = *(_OWORD *)&a2->dwMDDataLen;
      *((_QWORD *)Ptr + 4) = *(_QWORD *)&a2->dwMDDataTag;
      *((_QWORD *)Ptr + 3) = (char *)Ptr + 40;
      memcpy_0((char *)Ptr + 40, a2->pbMDData, a2->dwMDDataLen);
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x18000fd48  mov     [rsp+arg_0], rbx
0x18000fd4d  mov     [rsp+arg_8], rsi
0x18000fd52  push    rdi
0x18000fd53  sub     rsp, 20h
0x18000fd57  mov     rdi, rdx
0x18000fd5a  test    rdx, rdx
0x18000fd5d  jnz     short loc_18000FD66
0x18000fd5f  mov     ebx, 80070057h
0x18000fd64  jmp     short loc_18000FDCC
0x18000fd66  mov     edx, [rdx+10h]
0x18000fd69  lea     rsi, [rcx+10h]
0x18000fd6d  add     edx, 28h ; '('
0x18000fd70  mov     rcx, rsi
0x18000fd73  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000fd79  test    al, al
0x18000fd7b  jnz     short loc_18000FD94
0x18000fd7d  call    cs:__imp_GetLastError
0x18000fd83  mov     ebx, eax
0x18000fd85  test    eax, eax
0x18000fd87  jle     short loc_18000FDCC
0x18000fd89  movzx   ebx, ax
0x18000fd8c  or      ebx, 80070000h
0x18000fd92  jmp     short loc_18000FDCC
0x18000fd94  mov     rcx, rsi
0x18000fd97  xor     ebx, ebx
0x18000fd99  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000fd9f  movups  xmm0, xmmword ptr [rdi]
0x18000fda2  movups  xmmword ptr [rax], xmm0
0x18000fda5  lea     rcx, [rax+28h]; void *
0x18000fda9  movups  xmm1, xmmword ptr [rdi+10h]
0x18000fdad  movups  xmmword ptr [rax+10h], xmm1
0x18000fdb1  movsd   xmm0, qword ptr [rdi+20h]
0x18000fdb6  movsd   qword ptr [rax+20h], xmm0
0x18000fdbb  mov     [rax+18h], rcx
0x18000fdbf  mov     r8d, [rdi+10h]; Size
0x18000fdc3  mov     rdx, [rdi+18h]; Src
0x18000fdc7  call    memcpy_0
0x18000fdcc  mov     rsi, [rsp+28h+arg_8]
0x18000fdd1  mov     eax, ebx
0x18000fdd3  mov     rbx, [rsp+28h+arg_0]
0x18000fdd8  add     rsp, 20h
0x18000fddc  pop     rdi
0x18000fddd  retn
```
