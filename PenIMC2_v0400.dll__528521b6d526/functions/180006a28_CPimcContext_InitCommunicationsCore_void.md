# CPimcContext::InitCommunicationsCore(void)

- ea: `0x180006a28`
- end: `0x180006b0d`
- name: `?InitCommunicationsCore@CPimcContext@@QEAAJXZ`
- size: `229`
- prototype: `__int64 __fastcall(CPimcContext *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800062a0`
- `0x1800066dc`

## callees

- `0x180006a28`
- `0x180006b10`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180006a76`
- `KERNEL32!MapViewOfFile` at `0x180006aaa`
- `KERNEL32!MapViewOfFile` at `0x180006a76`
- `KERNEL32!MapViewOfFile` at `0x180006aaa`

## pseudocode

```c
__int64 __fastcall CPimcContext::InitCommunicationsCore(HANDLE *this)
{
  HANDLE v2; // rcx
  unsigned int *v3; // rax
  unsigned int v4; // edi
  char *v5; // rax

  if ( !this[7] || !this[8] || !this[9] || (v2 = this[10]) == 0 )
  {
    v4 = -2147482876;
LABEL_11:
    CPimcContext::ShutdownSharedMemoryCommunications((CPimcContext *)this);
    return v4;
  }
  v3 = (unsigned int *)MapViewOfFile(v2, 6u, 0, 0, 0x3Cu);
  this[11] = v3;
  v4 = v3 == 0 ? 0x80000305 : 0;
  if ( v3 )
  {
    v5 = (char *)MapViewOfFile(this[10], 4u, 0, 0, *v3);
    this[12] = v5;
    v4 = v5 == 0 ? 0x80000306 : 0;
    if ( v5 )
    {
      *((_DWORD *)this + 29) = 0;
      this[15] = 0;
      *((_DWORD *)this + 32) = 0;
      this[17] = 0;
      *((_DWORD *)this + 28) = 0;
      this[13] = v5 + 60;
    }
  }
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_11;
  return v4;
}

```

## disassembly

```asm
0x180006a28  mov     [rsp+arg_0], rbx
0x180006a2d  push    rdi
0x180006a2e  sub     rsp, 30h
0x180006a32  cmp     qword ptr [rcx+38h], 0
0x180006a37  mov     rbx, rcx
0x180006a3a  jz      loc_180006AF3
0x180006a40  cmp     qword ptr [rcx+40h], 0
0x180006a45  jz      loc_180006AF3
0x180006a4b  cmp     qword ptr [rcx+48h], 0
0x180006a50  jz      loc_180006AF3
0x180006a56  mov     rcx, [rcx+50h]; hFileMappingObject
0x180006a5a  test    rcx, rcx
0x180006a5d  jz      loc_180006AF3
0x180006a63  xor     r9d, r9d; dwFileOffsetLow
0x180006a66  mov     [rsp+38h+dwNumberOfBytesToMap], 3Ch ; '<'; dwNumberOfBytesToMap
0x180006a6f  xor     r8d, r8d; dwFileOffsetHigh
0x180006a72  lea     edx, [r9+6]; dwDesiredAccess
0x180006a76  call    cs:__imp_MapViewOfFile
0x180006a7c  mov     rcx, rax
0x180006a7f  mov     [rbx+58h], rax
0x180006a83  neg     rcx
0x180006a86  sbb     edi, edi
0x180006a88  not     edi
0x180006a8a  and     edi, 80000305h
0x180006a90  test    rax, rax
0x180006a93  jz      short loc_180006AED
0x180006a95  mov     eax, [rax]
0x180006a97  xor     r9d, r9d; dwFileOffsetLow
0x180006a9a  mov     rcx, [rbx+50h]; hFileMappingObject
0x180006a9e  xor     r8d, r8d; dwFileOffsetHigh
0x180006aa1  mov     [rsp+38h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x180006aa6  lea     edx, [r9+4]; dwDesiredAccess
0x180006aaa  call    cs:__imp_MapViewOfFile
0x180006ab0  mov     rcx, rax
0x180006ab3  mov     [rbx+60h], rax
0x180006ab7  neg     rcx
0x180006aba  sbb     edi, edi
0x180006abc  not     edi
0x180006abe  and     edi, 80000306h
0x180006ac4  test    rax, rax
0x180006ac7  jz      short loc_180006AED
0x180006ac9  and     dword ptr [rbx+74h], 0
0x180006acd  add     rax, 3Ch ; '<'
0x180006ad1  and     qword ptr [rbx+78h], 0
0x180006ad6  and     dword ptr [rbx+80h], 0
0x180006add  and     qword ptr [rbx+88h], 0
0x180006ae5  and     dword ptr [rbx+70h], 0
0x180006ae9  mov     [rbx+68h], rax
0x180006aed  test    edi, edi
0x180006aef  jns     short loc_180006B00
0x180006af1  jmp     short loc_180006AF8
0x180006af3  mov     edi, 80000304h
0x180006af8  mov     rcx, rbx; this
0x180006afb  call    ?ShutdownSharedMemoryCommunications@CPimcContext@@QEAAXXZ; CPimcContext::ShutdownSharedMemoryCommunications(void)
0x180006b00  mov     rbx, [rsp+38h+arg_0]
0x180006b05  mov     eax, edi
0x180006b07  add     rsp, 30h
0x180006b0b  pop     rdi
0x180006b0c  retn
```
