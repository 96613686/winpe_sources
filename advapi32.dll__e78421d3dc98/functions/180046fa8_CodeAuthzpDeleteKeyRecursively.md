# CodeAuthzpDeleteKeyRecursively

- ea: `0x180046fa8`
- end: `0x18004715d`
- name: `CodeAuthzpDeleteKeyRecursively`
- size: `437`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180046530`
- `0x180046fa8`

## callees

- `0x180046fa8`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18004700a`
- `ntdll!NtOpenKey` at `0x18004700a`
- `ntdll!NtClose` at `0x180047145`
- `ntdll!NtClose` at `0x180047145`
- `ntdll!NtDeleteKey` at `0x180047134`
- `ntdll!NtDeleteKey` at `0x180047134`
- `ntdll!NtEnumerateKey` at `0x18004705d`
- `ntdll!NtEnumerateKey` at `0x1800470d7`
- `ntdll!NtEnumerateKey` at `0x18004705d`
- `ntdll!NtEnumerateKey` at `0x1800470d7`
- `ntdll!RtlFreeHeap` at `0x180047093`
- `ntdll!RtlFreeHeap` at `0x18004712a`
- `ntdll!RtlFreeHeap` at `0x180047093`
- `ntdll!RtlFreeHeap` at `0x18004712a`
- `ntdll!RtlAllocateHeap` at `0x18004703b`
- `ntdll!RtlAllocateHeap` at `0x1800470b0`
- `ntdll!RtlAllocateHeap` at `0x18004703b`
- `ntdll!RtlAllocateHeap` at `0x1800470b0`

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
0x180046fa8  mov     [rsp-18h+arg_0], rbx
0x180046fad  push    rbp
0x180046fae  push    rsi
0x180046faf  push    rdi
0x180046fb0  mov     rbp, rsp
0x180046fb3  sub     rsp, 70h
0x180046fb7  xorps   xmm0, xmm0
0x180046fba  mov     [rbp+KeyHandle], 0
0x180046fc2  xor     eax, eax
0x180046fc4  mov     [rbp+arg_8], eax
0x180046fc7  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180046fcb  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180046fcf  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180046fd3  movups  [rbp+var_40], xmm0
0x180046fd7  test    rdx, rdx
0x180046fda  jz      short loc_18004701D
0x180046fdc  cmp     [rdx+8], rax
0x180046fe0  jz      short loc_18004701D
0x180046fe2  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x180046fe6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180046fea  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x180046fee  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180046ff2  mov     edx, 30019h; DesiredAccess
0x180046ff7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180046ffe  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180047005  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004700a  call    cs:__imp_NtOpenKey
0x180047010  test    eax, eax
0x180047012  js      loc_18004714D
0x180047018  mov     sil, 1
0x18004701b  jmp     short loc_180047024
0x18004701d  mov     [rbp+KeyHandle], rcx
0x180047021  xor     sil, sil
0x180047024  mov     rcx, gs:60h
0x18004702d  mov     edi, 100h
0x180047032  mov     r8d, edi; Size
0x180047035  xor     edx, edx; Flags
0x180047037  mov     rcx, [rcx+30h]; HeapHandle
0x18004703b  call    cs:__imp_RtlAllocateHeap
0x180047041  mov     rbx, rax
0x180047044  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180047048  lea     rax, [rbp+arg_8]
0x18004704c  mov     [rsp+70h+ResultLength], rax; ResultLength
0x180047051  mov     r9, rbx; KeyInformation
0x180047054  xor     r8d, r8d; KeyInformationClass
0x180047057  mov     [rsp+70h+Length], edi; Length
0x18004705b  xor     edx, edx; Index
0x18004705d  call    cs:__imp_NtEnumerateKey
0x180047063  cmp     eax, 0C0000023h
0x180047068  jz      short loc_180047071
0x18004706a  cmp     eax, 80000005h
0x18004706f  jnz     short loc_1800470DD
0x180047071  mov     eax, [rbp+arg_8]
0x180047074  cmp     eax, edi
0x180047076  jbe     loc_180047113
0x18004707c  test    rbx, rbx
0x18004707f  jz      short loc_18004709C
0x180047081  mov     rcx, gs:60h
0x18004708a  mov     r8, rbx; P
0x18004708d  xor     edx, edx; Flags
0x18004708f  mov     rcx, [rcx+30h]; HeapHandle
0x180047093  call    cs:__imp_RtlFreeHeap
0x180047099  mov     eax, [rbp+arg_8]
0x18004709c  mov     rcx, gs:60h
0x1800470a5  xor     edx, edx; Flags
0x1800470a7  mov     r8d, eax; Size
0x1800470aa  mov     edi, eax
0x1800470ac  mov     rcx, [rcx+30h]; HeapHandle
0x1800470b0  call    cs:__imp_RtlAllocateHeap
0x1800470b6  mov     rbx, rax
0x1800470b9  test    rax, rax
0x1800470bc  jz      short loc_180047130
0x1800470be  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800470c2  lea     rax, [rbp+arg_8]
0x1800470c6  mov     [rsp+70h+ResultLength], rax; ResultLength
0x1800470cb  mov     r9, rbx; KeyInformation
0x1800470ce  xor     r8d, r8d; KeyInformationClass
0x1800470d1  mov     [rsp+70h+Length], edi; Length
0x1800470d5  xor     edx, edx; Index
0x1800470d7  call    cs:__imp_NtEnumerateKey
0x1800470dd  test    eax, eax
0x1800470df  js      short loc_180047113
0x1800470e1  test    rbx, rbx
0x1800470e4  jz      short loc_180047130
0x1800470e6  mov     rcx, [rbp+KeyHandle]
0x1800470ea  lea     rax, [rbx+10h]
0x1800470ee  mov     qword ptr [rbp+var_40+8], rax
0x1800470f2  lea     rdx, [rbp+var_40]
0x1800470f6  movzx   eax, word ptr [rbx+0Ch]
0x1800470fa  mov     word ptr [rbp+var_40+2], ax
0x1800470fe  movzx   eax, word ptr [rbx+0Ch]
0x180047102  mov     word ptr [rbp+var_40], ax
0x180047106  call    CodeAuthzpDeleteKeyRecursively
0x18004710b  test    eax, eax
0x18004710d  jns     loc_180047044
0x180047113  test    rbx, rbx
0x180047116  jz      short loc_180047130
0x180047118  mov     rcx, gs:60h
0x180047121  mov     r8, rbx; P
0x180047124  xor     edx, edx; Flags
0x180047126  mov     rcx, [rcx+30h]; HeapHandle
0x18004712a  call    cs:__imp_RtlFreeHeap
0x180047130  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180047134  call    cs:__imp_NtDeleteKey
0x18004713a  mov     ebx, eax
0x18004713c  test    sil, sil
0x18004713f  jz      short loc_18004714B
0x180047141  mov     rcx, [rbp+KeyHandle]; Handle
0x180047145  call    cs:__imp_NtClose
0x18004714b  mov     eax, ebx
0x18004714d  mov     rbx, [rsp+70h+arg_0]
0x180047155  add     rsp, 70h
0x180047159  pop     rdi
0x18004715a  pop     rsi
0x18004715b  pop     rbp
0x18004715c  retn
```
