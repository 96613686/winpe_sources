# CFileRtlFOStream::Read(unsigned __int64,void *,unsigned __int64 *)

- ea: `0x140060a00`
- end: `0x140060b78`
- name: `?Read@CFileRtlFOStream@@UEAAJ_KPEAXPEA_K@Z`
- size: `376`
- prototype: `int(CFileRtlFOStream *__hidden this, unsigned __int64, void *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x140002326`
- `0x140060a00`

## import_xrefs

- `ntdll!NtReadFile` at `0x140060a5f`
- `ntdll!NtReadFile` at `0x140060b0b`
- `ntdll!NtReadFile` at `0x140060a5f`
- `ntdll!NtReadFile` at `0x140060b0b`
- `ntdll!NtWaitForSingleObject` at `0x140060a7b`
- `ntdll!NtWaitForSingleObject` at `0x140060b29`
- `ntdll!NtWaitForSingleObject` at `0x140060a7b`
- `ntdll!NtWaitForSingleObject` at `0x140060b29`

## pseudocode

```c
NTSTATUS __fastcall CFileRtlFOStream::Read(CFileRtlFOStream *this, size_t Length, void *a3, unsigned __int64 *a4)
{
  char *Buffer; // rcx
  size_t v8; // rdi
  const void *v9; // rdx
  NTSTATUS result; // eax
  char *v11; // rcx
  NTSTATUS File; // ecx

  Buffer = (char *)*((_QWORD *)this + 2);
  v8 = Length;
  if ( Buffer )
  {
    v9 = (const void *)*((_QWORD *)this + 4);
    if ( v9 )
    {
LABEL_8:
      v11 = &Buffer[*((_QWORD *)this + 3) - (_QWORD)v9];
      if ( v8 > (unsigned __int64)v11 )
        v8 = (size_t)v11;
      memcpy_0(a3, v9, v8);
      *((_QWORD *)this + 4) += v8;
      if ( a4 )
        *a4 = v8;
      return 0;
    }
    result = NtReadFile(
               *((HANDLE *)this + 1),
               0,
               0,
               0,
               (PIO_STATUS_BLOCK)((char *)this + 40),
               Buffer,
               *((_DWORD *)this + 6),
               0,
               0);
    if ( result == 259 )
    {
      result = NtWaitForSingleObject(*((HANDLE *)this + 1), 0, 0);
      if ( result < 0 )
        return result;
      result = *((_DWORD *)this + 10);
    }
    if ( result >= 0 )
    {
      Buffer = (char *)*((_QWORD *)this + 2);
      *((_QWORD *)this + 4) = Buffer;
      v9 = Buffer;
      goto LABEL_8;
    }
  }
  else
  {
    *(_OWORD *)((char *)this + 40) = 0;
    File = NtReadFile(*((HANDLE *)this + 1), 0, 0, 0, (PIO_STATUS_BLOCK)((char *)this + 40), a3, Length, 0, 0);
    if ( File == 259 )
    {
      File = NtWaitForSingleObject(*((HANDLE *)this + 1), 0, 0);
      if ( File >= 0 )
        File = *((_DWORD *)this + 10);
    }
    result = 0;
    if ( File != -1073741807 )
      result = File;
    if ( result >= 0 && a4 )
      *a4 = *((_QWORD *)this + 6);
  }
  return result;
}

```

## disassembly

```asm
0x140060a00  mov     r11, rsp
0x140060a03  mov     [r11+8], rbx
0x140060a07  mov     [r11+10h], rbp
0x140060a0b  mov     [r11+18h], rsi
0x140060a0f  push    rdi
0x140060a10  push    r14
0x140060a12  push    r15
0x140060a14  sub     rsp, 50h
0x140060a18  mov     rbx, rcx
0x140060a1b  mov     rsi, r9
0x140060a1e  mov     rcx, [rcx+10h]
0x140060a22  mov     rbp, r8
0x140060a25  mov     rdi, rdx
0x140060a28  test    rcx, rcx
0x140060a2b  jz      loc_140060AD4
0x140060a31  mov     rdx, [rbx+20h]; Event
0x140060a35  test    rdx, rdx
0x140060a38  jnz     short loc_140060AA5
0x140060a3a  mov     eax, [rbx+18h]
0x140060a3d  lea     r15, [rbx+28h]
0x140060a41  mov     [r11-28h], rdx
0x140060a45  xor     r9d, r9d; ApcContext
0x140060a48  mov     [r11-30h], rdx
0x140060a4c  xor     r8d, r8d; ApcRoutine
0x140060a4f  mov     [rsp+68h+Length], eax; Length
0x140060a53  mov     [r11-40h], rcx
0x140060a57  mov     rcx, [rbx+8]; FileHandle
0x140060a5b  mov     [r11-48h], r15
0x140060a5f  call    cs:__imp_NtReadFile
0x140060a66  nop     dword ptr [rax+rax+00h]
0x140060a6b  cmp     eax, 103h
0x140060a70  jnz     short loc_140060A92
0x140060a72  mov     rcx, [rbx+8]; Handle
0x140060a76  xor     r8d, r8d; Timeout
0x140060a79  xor     edx, edx; Alertable
0x140060a7b  call    cs:__imp_NtWaitForSingleObject
0x140060a82  nop     dword ptr [rax+rax+00h]
0x140060a87  test    eax, eax
0x140060a89  js      loc_140060B5D
0x140060a8f  mov     eax, [r15]
0x140060a92  test    eax, eax
0x140060a94  js      loc_140060B5D
0x140060a9a  mov     rcx, [rbx+10h]
0x140060a9e  mov     [rbx+20h], rcx
0x140060aa2  mov     rdx, rcx; Src
0x140060aa5  mov     rax, [rbx+18h]
0x140060aa9  sub     rax, rdx
0x140060aac  add     rcx, rax
0x140060aaf  cmp     rdi, rcx
0x140060ab2  cmova   rdi, rcx
0x140060ab6  mov     rcx, rbp; void *
0x140060ab9  mov     r8, rdi; Size
0x140060abc  call    memcpy_0
0x140060ac1  add     [rbx+20h], rdi
0x140060ac5  test    rsi, rsi
0x140060ac8  jz      short loc_140060ACD
0x140060aca  mov     [rsi], rdi
0x140060acd  xor     eax, eax
0x140060acf  jmp     loc_140060B5D
0x140060ad4  mov     [rsp+68h+Key], 0; Key
0x140060add  lea     r14, [rbx+28h]
0x140060ae1  mov     [rsp+68h+ByteOffset], 0; ByteOffset
0x140060aea  xorps   xmm0, xmm0
0x140060aed  movups  xmmword ptr [r14], xmm0
0x140060af1  mov     rcx, [rbx+8]; FileHandle
0x140060af5  xor     r9d, r9d; ApcContext
0x140060af8  mov     [rsp+68h+Length], edi; Length
0x140060afc  xor     r8d, r8d; ApcRoutine
0x140060aff  mov     [rsp+68h+Buffer], rbp; Buffer
0x140060b04  xor     edx, edx; Event
0x140060b06  mov     [rsp+68h+IoStatusBlock], r14; IoStatusBlock
0x140060b0b  call    cs:__imp_NtReadFile
0x140060b12  nop     dword ptr [rax+rax+00h]
0x140060b17  mov     ecx, eax
0x140060b19  cmp     eax, 103h
0x140060b1e  jnz     short loc_140060B3E
0x140060b20  mov     rcx, [rbx+8]; Handle
0x140060b24  xor     r8d, r8d; Timeout
0x140060b27  xor     edx, edx; Alertable
0x140060b29  call    cs:__imp_NtWaitForSingleObject
0x140060b30  nop     dword ptr [rax+rax+00h]
0x140060b35  mov     ecx, eax
0x140060b37  test    eax, eax
0x140060b39  js      short loc_140060B3E
0x140060b3b  mov     ecx, [r14]
0x140060b3e  xor     eax, eax
0x140060b40  cmp     ecx, 0C0000011h
0x140060b46  cmovnz  eax, ecx
0x140060b49  mov     ecx, eax
0x140060b4b  test    eax, eax
0x140060b4d  js      short loc_140060B5D
0x140060b4f  test    rsi, rsi
0x140060b52  jz      short loc_140060B5D
0x140060b54  mov     rax, [rbx+30h]
0x140060b58  mov     [rsi], rax
0x140060b5b  mov     eax, ecx
0x140060b5d  lea     r11, [rsp+68h+var_18]
0x140060b62  mov     rbx, [r11+20h]
0x140060b66  mov     rbp, [r11+28h]
0x140060b6a  mov     rsi, [r11+30h]
0x140060b6e  mov     rsp, r11
0x140060b71  pop     r15
0x140060b73  pop     r14
0x140060b75  pop     rdi
0x140060b76  retn
```
