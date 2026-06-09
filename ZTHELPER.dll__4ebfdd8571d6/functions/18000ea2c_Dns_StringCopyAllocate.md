# Dns_StringCopyAllocate

- ea: `0x18000ea2c`
- end: `0x18000eb14`
- name: `Dns_StringCopyAllocate`
- size: `232`
- prototype: `__int64 __fastcall(const CHAR *, int, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000bfac`
- `0x180012dac`

## callees

- `0x1800014b0`
- `0x18000e470`
- `0x18000e680`
- `0x18000ea2c`
- `0x180012564`
- `0x1800125d4`
- `0x180013544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea76`

## pseudocode

```c
__int64 __fastcall Dns_StringCopyAllocate(const CHAR *a1, int a2, int a3, int a4)
{
  __int64 v6; // rbx
  DWORD v9; // ecx
  unsigned int BufferLengthForStringCopy; // eax
  void *v11; // rax
  void *v12; // rdi
  unsigned int v13; // [rsp+30h] [rbp-48h] BYREF

  LODWORD(v6) = a2;
  v13 = 0;
  if ( g_fVelocityDnsKernelApi )
    return Dns_StringCopyAllocate_New();
  if ( !a1 )
  {
    v9 = 87;
LABEL_5:
    SetLastError(v9);
    return 0;
  }
  if ( !a2 )
  {
    v6 = -1;
    if ( a3 == 1 )
    {
      do
        ++v6;
      while ( *(_WORD *)&a1[2 * v6] );
      LODWORD(v6) = (unsigned __int16)v6;
    }
    else
    {
      do
        ++v6;
      while ( a1[v6] );
    }
  }
  BufferLengthForStringCopy = Dns_GetBufferLengthForStringCopy(a1, v6, a3, a4);
  v13 = BufferLengthForStringCopy;
  if ( !BufferLengthForStringCopy )
  {
    v9 = 13;
    goto LABEL_5;
  }
  v11 = Dns_Allocate(BufferLengthForStringCopy);
  v12 = v11;
  if ( !v11 )
  {
    v9 = 14;
    goto LABEL_5;
  }
  if ( !(unsigned int)Dns_StringCopy(v11, &v13, a1, v6, a3, a4) )
  {
    Dns_Free(v12);
    return 0;
  }
  return (__int64)v12;
}

```

## disassembly

```asm
0x18000ea2c  push    rbx
0x18000ea2e  push    rbp
0x18000ea2f  push    rsi
0x18000ea30  push    rdi
0x18000ea31  push    r14
0x18000ea33  push    r15
0x18000ea35  sub     rsp, 48h
0x18000ea39  mov     rax, cs:__security_cookie
0x18000ea40  xor     rax, rsp
0x18000ea43  mov     [rsp+78h+var_40], rax
0x18000ea48  xor     r15d, r15d
0x18000ea4b  mov     r14d, r9d
0x18000ea4e  cmp     cs:g_fVelocityDnsKernelApi, r15d
0x18000ea55  mov     ebp, r8d
0x18000ea58  mov     ebx, edx
0x18000ea5a  mov     [rsp+78h+var_48], r15d
0x18000ea5f  mov     rsi, rcx
0x18000ea62  jz      short loc_18000EA6E
0x18000ea64  call    Dns_StringCopyAllocate_New
0x18000ea69  jmp     loc_18000EAFA
0x18000ea6e  test    rsi, rsi
0x18000ea71  jnz     short loc_18000EA80
0x18000ea73  lea     ecx, [rsi+57h]; dwErrCode
0x18000ea76  call    cs:__imp_SetLastError
0x18000ea7c  xor     eax, eax
0x18000ea7e  jmp     short loc_18000EAFA
0x18000ea80  test    edx, edx
0x18000ea82  jnz     short loc_18000EAA5
0x18000ea84  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ea88  cmp     ebp, 1
0x18000ea8b  jnz     short loc_18000EA9C
0x18000ea8d  inc     rbx
0x18000ea90  cmp     [rcx+rbx*2], r15w
0x18000ea95  jnz     short loc_18000EA8D
0x18000ea97  movzx   ebx, bx
0x18000ea9a  jmp     short loc_18000EAA5
0x18000ea9c  inc     rbx
0x18000ea9f  cmp     [rcx+rbx], r15b
0x18000eaa3  jnz     short loc_18000EA9C
0x18000eaa5  mov     edx, ebx; cbMultiByte
0x18000eaa7  call    Dns_GetBufferLengthForStringCopy
0x18000eaac  mov     [rsp+78h+var_48], eax
0x18000eab0  test    eax, eax
0x18000eab2  jnz     short loc_18000EAB9
0x18000eab4  lea     ecx, [rax+0Dh]
0x18000eab7  jmp     short loc_18000EA76
0x18000eab9  mov     ecx, eax
0x18000eabb  call    Dns_Allocate
0x18000eac0  mov     rdi, rax
0x18000eac3  test    rax, rax
0x18000eac6  jnz     short loc_18000EACD
0x18000eac8  lea     ecx, [rax+0Eh]
0x18000eacb  jmp     short loc_18000EA76
0x18000eacd  mov     [rsp+78h+var_50], r14d; int
0x18000ead2  lea     rdx, [rsp+78h+var_48]
0x18000ead7  mov     r9d, ebx
0x18000eada  mov     [rsp+78h+var_58], ebp; int
0x18000eade  mov     r8, rsi
0x18000eae1  mov     rcx, rdi; void *
0x18000eae4  call    Dns_StringCopy
0x18000eae9  test    eax, eax
0x18000eaeb  jnz     short loc_18000EAF7
0x18000eaed  mov     rcx, rdi; lpMem
0x18000eaf0  call    Dns_Free
0x18000eaf5  jmp     short loc_18000EA7C
0x18000eaf7  mov     rax, rdi
0x18000eafa  mov     rcx, [rsp+78h+var_40]
0x18000eaff  xor     rcx, rsp; StackCookie
0x18000eb02  call    __security_check_cookie
0x18000eb07  add     rsp, 48h
0x18000eb0b  pop     r15
0x18000eb0d  pop     r14
0x18000eb0f  pop     rdi
0x18000eb10  pop     rsi
0x18000eb11  pop     rbp
0x18000eb12  pop     rbx
0x18000eb13  retn
```
