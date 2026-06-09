# ConsoleHandleConnectionRequest

- ea: `0x14001e9b4`
- end: `0x14001eb5c`
- name: `ConsoleHandleConnectionRequest`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001f0e0`

## callees

- `0x140002310`
- `0x14001e9b4`
- `0x14001f07c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001ea17`
- `ntdll!RtlAllocateHeap` at `0x14001ea17`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001eb32`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001eb32`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001eb06`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001eb06`
- `ntdll!RtlFreeHeap` at `0x14001eafa`
- `ntdll!RtlFreeHeap` at `0x14001eafa`
- `ntdll!NtOpenProcess` at `0x14001ea7f`
- `ntdll!NtOpenProcess` at `0x14001ea7f`
- `ntdll!NtClose` at `0x14001eae2`
- `ntdll!NtClose` at `0x14001eae2`

## pseudocode

```c
char __fastcall ConsoleHandleConnectionRequest(_QWORD *a1)
{
  _QWORD *v1; // rdi
  char *Heap; // rax
  char *v4; // rbx
  void *v5; // rax
  HANDLE *v6; // r14
  int v7; // eax
  _QWORD *v8; // rcx
  _CLIENT_ID ClientId; // [rsp+20h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-50h] BYREF
  __int128 v12; // [rsp+60h] [rbp-20h] BYREF
  __int64 v13; // [rsp+70h] [rbp-10h]

  v1 = a1 + 27;
  v13 = 0;
  ClientId = 0;
  memset(&ObjectAttributes, 0, 44);
  v12 = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
  v4 = Heap;
  if ( Heap )
  {
    v5 = (void *)v1[13];
    v6 = (HANDLE *)(v4 + 24);
    *((_QWORD *)v4 + 2) = v5;
    ClientId.UniqueProcess = v5;
    ClientId.UniqueThread = 0;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenProcess((PHANDLE)v4 + 3, 2u, &ObjectAttributes, &ClientId) < 0 )
      *v6 = 0;
    *((_DWORD *)v1 + 2) = 0;
    v1[2] = 24;
    v1[4] = 24;
    v1[3] = &v12;
    v13 = a1[10];
    v12 = (unsigned __int64)v4;
    v7 = CspCompleteConsoleIo(a1, v1);
    a1[26] = 0;
    if ( v7 >= 0 )
    {
      RtlAcquireSRWLockExclusive(a1 + 6);
      v8 = (_QWORD *)a1[9];
      if ( (_QWORD *)*v8 != a1 + 8 )
        __fastfail(3u);
      *((_QWORD *)v4 + 1) = v8;
      *(_QWORD *)v4 = a1 + 8;
      *v8 = v4;
      a1[9] = v4;
      LOBYTE(Heap) = RtlReleaseSRWLockExclusive(a1 + 6);
    }
    else
    {
      if ( *v6 )
        NtClose(*v6);
      LOBYTE(Heap) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    }
  }
  else
  {
    *((_DWORD *)v1 + 2) = -1073741670;
  }
  return (char)Heap;
}

```

## disassembly

```asm
0x14001e9b4  mov     [rsp-18h+arg_8], rbx
0x14001e9b9  mov     [rsp-18h+arg_10], rsi
0x14001e9be  push    rbp
0x14001e9bf  push    rdi
0x14001e9c0  push    r14
0x14001e9c2  mov     rbp, rsp
0x14001e9c5  sub     rsp, 80h
0x14001e9cc  mov     rax, cs:__security_cookie
0x14001e9d3  xor     rax, rsp
0x14001e9d6  mov     [rbp+var_8], rax
0x14001e9da  xorps   xmm0, xmm0
0x14001e9dd  lea     rdi, [rcx+0D8h]
0x14001e9e4  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001e9e8  xor     eax, eax
0x14001e9ea  mov     rsi, rcx
0x14001e9ed  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14001e9f1  mov     [rbp+var_10], rax
0x14001e9f5  xor     edx, edx; Flags
0x14001e9f7  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x14001e9fb  lea     r8d, [rax+20h]; Size
0x14001e9ff  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001ea03  xorps   xmm1, xmm1
0x14001ea06  movups  [rbp+var_20], xmm1
0x14001ea0a  mov     rcx, gs:60h
0x14001ea13  mov     rcx, [rcx+30h]; HeapHandle
0x14001ea17  call    cs:__imp_RtlAllocateHeap
0x14001ea1d  mov     rbx, rax
0x14001ea20  test    rax, rax
0x14001ea23  jnz     short loc_14001EA31
0x14001ea25  mov     dword ptr [rdi+8], 0C000009Ah
0x14001ea2c  jmp     loc_14001EB38
0x14001ea31  mov     rax, [rdi+68h]
0x14001ea35  lea     r14, [rbx+18h]
0x14001ea39  mov     [rbx+10h], rax
0x14001ea3d  lea     r9, [rbp+ClientId]; ClientId
0x14001ea41  xorps   xmm0, xmm0
0x14001ea44  mov     [rbp+ClientId.UniqueProcess], rax
0x14001ea48  mov     rcx, r14; ProcessHandle
0x14001ea4b  mov     [rbp+ClientId.UniqueThread], 0
0x14001ea53  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001ea57  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001ea5e  mov     edx, 2; DesiredAccess
0x14001ea63  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14001ea6b  mov     [rbp+ObjectAttributes.Attributes], 0
0x14001ea72  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14001ea7a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001ea7f  call    cs:__imp_NtOpenProcess
0x14001ea85  test    eax, eax
0x14001ea87  jns     short loc_14001EA90
0x14001ea89  mov     qword ptr [r14], 0
0x14001ea90  mov     ecx, 18h
0x14001ea95  mov     dword ptr [rdi+8], 0
0x14001ea9c  mov     [rdi+10h], rcx
0x14001eaa0  lea     rax, [rbp+var_20]
0x14001eaa4  mov     [rdi+20h], rcx
0x14001eaa8  mov     rdx, rdi
0x14001eaab  mov     [rdi+18h], rax
0x14001eaaf  mov     rcx, rsi
0x14001eab2  mov     rax, [rsi+50h]
0x14001eab6  mov     [rbp+var_10], rax
0x14001eaba  mov     qword ptr [rbp+var_20], rbx
0x14001eabe  mov     qword ptr [rbp+var_20+8], 0
0x14001eac6  call    CspCompleteConsoleIo
0x14001eacb  mov     qword ptr [rsi+0D0h], 0
0x14001ead6  test    eax, eax
0x14001ead8  jns     short loc_14001EB02
0x14001eada  mov     rcx, [r14]; Handle
0x14001eadd  test    rcx, rcx
0x14001eae0  jz      short loc_14001EAE8
0x14001eae2  call    cs:__imp_NtClose
0x14001eae8  mov     rcx, gs:60h
0x14001eaf1  mov     r8, rbx; P
0x14001eaf4  xor     edx, edx; Flags
0x14001eaf6  mov     rcx, [rcx+30h]; HeapHandle
0x14001eafa  call    cs:__imp_RtlFreeHeap
0x14001eb00  jmp     short loc_14001EB38
0x14001eb02  lea     rcx, [rsi+30h]
0x14001eb06  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14001eb0c  lea     rax, [rsi+40h]
0x14001eb10  mov     rcx, [rax+8]
0x14001eb14  cmp     [rcx], rax
0x14001eb17  jz      short loc_14001EB20
0x14001eb19  mov     ecx, 3
0x14001eb1e  int     29h; Win8: RtlFailFast(ecx)
0x14001eb20  mov     [rbx+8], rcx
0x14001eb24  mov     [rbx], rax
0x14001eb27  mov     [rcx], rbx
0x14001eb2a  lea     rcx, [rsi+30h]
0x14001eb2e  mov     [rax+8], rbx
0x14001eb32  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14001eb38  mov     rcx, [rbp+var_8]
0x14001eb3c  xor     rcx, rsp; StackCookie
0x14001eb3f  call    __security_check_cookie
0x14001eb44  lea     r11, [rsp+80h+var_s0]
0x14001eb4c  mov     rbx, [r11+28h]
0x14001eb50  mov     rsi, [r11+30h]
0x14001eb54  mov     rsp, r11
0x14001eb57  pop     r14
0x14001eb59  pop     rdi
0x14001eb5a  pop     rbp
0x14001eb5b  retn
```
