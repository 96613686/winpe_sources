# CodeAuthzpDeleteKeyRecursively

- ea: `0x18004c854`
- end: `0x18004ca40`
- name: `CodeAuthzpDeleteKeyRecursively`
- size: `492`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004bd04`
- `0x18004c854`

## callees

- `0x18004c854`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18004c8b6`
- `ntdll!NtOpenKey` at `0x18004c8b6`
- `ntdll!NtClose` at `0x18004ca21`
- `ntdll!NtClose` at `0x18004ca21`
- `ntdll!NtDeleteKey` at `0x18004ca0a`
- `ntdll!NtDeleteKey` at `0x18004ca0a`
- `ntdll!NtEnumerateKey` at `0x18004c915`
- `ntdll!NtEnumerateKey` at `0x18004c9a1`
- `ntdll!NtEnumerateKey` at `0x18004c915`
- `ntdll!NtEnumerateKey` at `0x18004c9a1`
- `ntdll!RtlFreeHeap` at `0x18004c951`
- `ntdll!RtlFreeHeap` at `0x18004c9fa`
- `ntdll!RtlFreeHeap` at `0x18004c951`
- `ntdll!RtlFreeHeap` at `0x18004c9fa`
- `ntdll!RtlAllocateHeap` at `0x18004c8ed`
- `ntdll!RtlAllocateHeap` at `0x18004c974`
- `ntdll!RtlAllocateHeap` at `0x18004c8ed`
- `ntdll!RtlAllocateHeap` at `0x18004c974`

## pseudocode

```c
NTSTATUS __fastcall CodeAuthzpDeleteKeyRecursively(void *a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS result; // eax
  char v3; // si
  ULONG Length; // edi
  _WORD *Heap; // rbx
  NTSTATUS v6; // eax
  ULONG v7; // eax
  NTSTATUS v8; // ebx
  __int128 v9; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+28h] BYREF
  HANDLE KeyHandle; // [rsp+A0h] [rbp+30h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  v9 = 0;
  if ( a2 && a2->Buffer )
  {
    ObjectAttributes.RootDirectory = a1;
    ObjectAttributes.ObjectName = a2;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = NtOpenKey(&KeyHandle, 0x30019u, &ObjectAttributes);
    if ( result < 0 )
      return result;
    v3 = 1;
  }
  else
  {
    KeyHandle = a1;
    v3 = 0;
  }
  Length = 256;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x100u);
  do
  {
    v6 = NtEnumerateKey(KeyHandle, 0, KeyBasicInformation, Heap, Length, &ResultLength);
    if ( v6 == -1073741789 || v6 == -2147483643 )
    {
      v7 = ResultLength;
      if ( ResultLength <= Length )
        break;
      if ( Heap )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        v7 = ResultLength;
      }
      Length = v7;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      if ( !Heap )
        goto LABEL_19;
      v6 = NtEnumerateKey(KeyHandle, 0, KeyBasicInformation, Heap, Length, &ResultLength);
    }
    if ( v6 < 0 )
      break;
    if ( !Heap )
      goto LABEL_19;
    *((_QWORD *)&v9 + 1) = Heap + 8;
    WORD1(v9) = Heap[6];
    LOWORD(v9) = Heap[6];
  }
  while ( (int)CodeAuthzpDeleteKeyRecursively(KeyHandle, &v9) >= 0 );
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
LABEL_19:
  v8 = NtDeleteKey(KeyHandle);
  if ( v3 )
    NtClose(KeyHandle);
  return v8;
}

```

## disassembly

```asm
0x18004c854  mov     [rsp-18h+arg_0], rbx
0x18004c859  push    rbp
0x18004c85a  push    rsi
0x18004c85b  push    rdi
0x18004c85c  mov     rbp, rsp
0x18004c85f  sub     rsp, 70h
0x18004c863  xorps   xmm0, xmm0
0x18004c866  mov     [rbp+KeyHandle], 0
0x18004c86e  xor     eax, eax
0x18004c870  mov     [rbp+arg_8], eax
0x18004c873  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18004c877  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18004c87b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18004c87f  movups  [rbp+var_40], xmm0
0x18004c883  test    rdx, rdx
0x18004c886  jz      short loc_18004C8CF
0x18004c888  cmp     [rdx+8], rax
0x18004c88c  jz      short loc_18004C8CF
0x18004c88e  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x18004c892  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004c896  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x18004c89a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18004c89e  mov     edx, 30019h; DesiredAccess
0x18004c8a3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004c8aa  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004c8b1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004c8b6  call    cs:__imp_NtOpenKey
0x18004c8bd  nop     dword ptr [rax+rax+00h]
0x18004c8c2  test    eax, eax
0x18004c8c4  js      loc_18004CA2F
0x18004c8ca  mov     sil, 1
0x18004c8cd  jmp     short loc_18004C8D6
0x18004c8cf  mov     [rbp+KeyHandle], rcx
0x18004c8d3  xor     sil, sil
0x18004c8d6  mov     rcx, gs:60h
0x18004c8df  mov     edi, 100h
0x18004c8e4  mov     r8d, edi; Size
0x18004c8e7  xor     edx, edx; Flags
0x18004c8e9  mov     rcx, [rcx+30h]; HeapHandle
0x18004c8ed  call    cs:__imp_RtlAllocateHeap
0x18004c8f4  nop     dword ptr [rax+rax+00h]
0x18004c8f9  mov     rbx, rax
0x18004c8fc  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18004c900  lea     rax, [rbp+arg_8]
0x18004c904  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18004c909  mov     r9, rbx; KeyInformation
0x18004c90c  xor     r8d, r8d; KeyInformationClass
0x18004c90f  mov     [rsp+70h+Length], edi; Length
0x18004c913  xor     edx, edx; Index
0x18004c915  call    cs:__imp_NtEnumerateKey
0x18004c91c  nop     dword ptr [rax+rax+00h]
0x18004c921  cmp     eax, 0C0000023h
0x18004c926  jz      short loc_18004C92F
0x18004c928  cmp     eax, 80000005h
0x18004c92d  jnz     short loc_18004C9AD
0x18004c92f  mov     eax, [rbp+arg_8]
0x18004c932  cmp     eax, edi
0x18004c934  jbe     loc_18004C9E3
0x18004c93a  test    rbx, rbx
0x18004c93d  jz      short loc_18004C960
0x18004c93f  mov     rcx, gs:60h
0x18004c948  mov     r8, rbx; P
0x18004c94b  xor     edx, edx; Flags
0x18004c94d  mov     rcx, [rcx+30h]; HeapHandle
0x18004c951  call    cs:__imp_RtlFreeHeap
0x18004c958  nop     dword ptr [rax+rax+00h]
0x18004c95d  mov     eax, [rbp+arg_8]
0x18004c960  mov     rcx, gs:60h
0x18004c969  xor     edx, edx; Flags
0x18004c96b  mov     r8d, eax; Size
0x18004c96e  mov     edi, eax
0x18004c970  mov     rcx, [rcx+30h]; HeapHandle
0x18004c974  call    cs:__imp_RtlAllocateHeap
0x18004c97b  nop     dword ptr [rax+rax+00h]
0x18004c980  mov     rbx, rax
0x18004c983  test    rax, rax
0x18004c986  jz      short loc_18004CA06
0x18004c988  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18004c98c  lea     rax, [rbp+arg_8]
0x18004c990  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18004c995  mov     r9, rbx; KeyInformation
0x18004c998  xor     r8d, r8d; KeyInformationClass
0x18004c99b  mov     [rsp+70h+Length], edi; Length
0x18004c99f  xor     edx, edx; Index
0x18004c9a1  call    cs:__imp_NtEnumerateKey
0x18004c9a8  nop     dword ptr [rax+rax+00h]
0x18004c9ad  test    eax, eax
0x18004c9af  js      short loc_18004C9E3
0x18004c9b1  test    rbx, rbx
0x18004c9b4  jz      short loc_18004CA06
0x18004c9b6  mov     rcx, [rbp+KeyHandle]
0x18004c9ba  lea     rax, [rbx+10h]
0x18004c9be  mov     qword ptr [rbp+var_40+8], rax
0x18004c9c2  lea     rdx, [rbp+var_40]
0x18004c9c6  movzx   eax, word ptr [rbx+0Ch]
0x18004c9ca  mov     word ptr [rbp+var_40+2], ax
0x18004c9ce  movzx   eax, word ptr [rbx+0Ch]
0x18004c9d2  mov     word ptr [rbp+var_40], ax
0x18004c9d6  call    CodeAuthzpDeleteKeyRecursively
0x18004c9db  test    eax, eax
0x18004c9dd  jns     loc_18004C8FC
0x18004c9e3  test    rbx, rbx
0x18004c9e6  jz      short loc_18004CA06
0x18004c9e8  mov     rcx, gs:60h
0x18004c9f1  mov     r8, rbx; P
0x18004c9f4  xor     edx, edx; Flags
0x18004c9f6  mov     rcx, [rcx+30h]; HeapHandle
0x18004c9fa  call    cs:__imp_RtlFreeHeap
0x18004ca01  nop     dword ptr [rax+rax+00h]
0x18004ca06  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18004ca0a  call    cs:__imp_NtDeleteKey
0x18004ca11  nop     dword ptr [rax+rax+00h]
0x18004ca16  mov     ebx, eax
0x18004ca18  test    sil, sil
0x18004ca1b  jz      short loc_18004CA2D
0x18004ca1d  mov     rcx, [rbp+KeyHandle]; Handle
0x18004ca21  call    cs:__imp_NtClose
0x18004ca28  nop     dword ptr [rax+rax+00h]
0x18004ca2d  mov     eax, ebx
0x18004ca2f  mov     rbx, [rsp+70h+arg_0]
0x18004ca37  add     rsp, 70h
0x18004ca3b  pop     rdi
0x18004ca3c  pop     rsi
0x18004ca3d  pop     rbp
0x18004ca3e  retn
```
